---
title: Data Customer Insights dalam Microsoft Dataverse
description: Gunakan entiti Customer Insights sebagai jadual dalam Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 45535a7368b89e19a91f08fcd825bda9d57a8709653104bf4043c29ffa14d0b8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032907"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Gunakan data Customer Insights dalam Microsoft Dataverse

Customer Insights menyediakan pilihan untuk menjadikan entiti output tersedia dalam [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Integrasi ini membolehkan perkongsian data yang mudah dan pembangunan tersuai melalui kod rendah / tiada pendekatan kod. Entiti output akan tersedia sebagai jadual dalam Dataverse. Jadual ini membolehkan senario seperti [aliran kerja automatik melalui Power Automate](/power-automate/getting-started), [aplikasi berpandukan model](/powerapps/maker/model-driven-apps/) dan [aplikasi kanvas](/powerapps/maker/canvas-apps/) melalui Power Apps. Anda boleh menggunakan data untuk sebarang aplikasi lain yang berdasarkan jadual Dataverse. Pelaksanaan semasa kebanyakannya menyokong carian tempat data daripada entiti cerapan khalayak yang tersedia dapat diambil untuk ID pelanggan yang ditetapkan.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Lampirkan persekitaran Dataverse kepada Customer Insights

**Organisasi yang mempunyai persekitaran Dataverse yang sedia ada**

Organisasi yang telah menggunakan Dataverse boleh [menggunakan salah satu persekitaran Dataverse mereka yang sedia ada](get-started-paid.md) apabila pentadbir menyediakan cerapan khalayak. Dengan menyediakan URL kepada persekitaran Dataverse, ia melampirkan persekitaran cerapan khalayak baharu mereka. Untuk memastikan prestasi terbaik, Customer Insights dan persekitaran Dataverse mesti dihoskan di kawasan yang sama.

Untuk melampirkan persekitaran Dataverse, kembangkan **Tetapan lanjutan** apabila mencipta persekitaran cerapan khalayak. Sediakan **URL persekitaran Microsoft Dataverse** dan pilih kotak semak untuk **Dayakan perkongsian data**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt.":::

**Organisasi baharu**

Jika anda mencipta organisasi baharu semasa menyediakan Customer Insights, anda akan mendapat persekitaran Dataverse yang baharu secara automatik.

> [!NOTE]
> Jika organisasi anda sudah menggunakan Dataverse dalam penyewa mereka, penting untuk diingat bahawa [penciptaan persekitaran Dataverse dikawal oleh pentadbir](/power-platform/admin/control-environment-creation.md). Contohnya, jika anda menyediakan persekitaran cerapan khalayak baharu menggunakan akaun organisasi anda dan pentadbir telah menyahdayakan penciptaan persekitaran percubaan Dataverse untuk semua orang kecuali pentadbir, anda tidak boleh mencipta persekitaran percubaan yang baharu.
> 
> Persekitaran percubaan Dataverse yang dicipta dalam Customer Insights mempunyai 3 GB storan yang tidak akan mengira kapasiti keseluruhan yang diterima oleh penyewa. Langganan berbayar akan mendapat kelayakan Dataverse sebanyak 15 GB untuk pangkalan data dan 20 GB untuk storan fail.

## <a name="output-entities"></a>Entiti output

Sesetengah entiti output daripada cerapan khalayak tersedia sebagai jadual dalam Dataverse. Bahagian di bawah menerangkan skema yang dijangka bagi jadual ini.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Pengayaan](#enrichment)
- [Ramalan](#prediction)


### <a name="customerprofile"></a>CustomerProfile

Jadual ini mengandungi profil pelanggan yang disatukan daripada Customer Insights. Skema untuk profil pelanggan yang disatukan bergantung pada entiti dan atribut yang digunakan dalam proses gabungan. Skema profil pelanggan biasanya mengandungi subset atribut daripada [definisi Common Data Model bagi CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Jadual AlternateKey mengandungi kunci entiti, yang mengambil bahagian dalam proses penyatuan.

|Column  |Jenis  |Penerangan  |
|---------|---------|---------|
|DataSourceName    |Jalur         | Nama sumber data. Contohnya: `datasource5`        |
|EntityName        | Jalur        | Nama entiti dalam cerapan khalayak. Contohnya: `contact1`        |
|AlternateValue    |Jalur         |ID alternatif yang dipetakan kepada ID pelanggan. Contoh: `cntid_1078`         |
|KeyRing           | Teks berbilang baris        | Nilai JSON  </br> Sampel: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Jalur        | ID profil pelanggan yang disatukan.         |
|AlternateKeyId     | GUID         |  GUID berketentuan AlternateKey berdasarkan msdynci_identifier       |
|msdynci_identifier |   Jalur      |   `DataSourceName|EntityName|AlternateValue`  </br> Sampel: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Jadual ini mengandungi aktiviti oleh pengguna yang tersedia dalam Customer Insights.

| Column            | Jenis        | Penerangan                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Jalur      | ID Profil Pelanggan                                                                      |
| ActivityId        | Jalur      | ID Dalaman aktiviti pelanggan (kunci utama)                                       |
| SourceEntityName  | Jalur      | Nama entiti sumber                                                                |
| SourceActivityId  | Jalur      | Kunci utama daripada entiti sumber                                                       |
| ActivityType      | Jalur      | Jenis aktiviti semantik atau nama aktiviti tersuai                                        |
| ActivityTimeStamp | DATETIME    | Cap Masa aktiviti                                                                      |
| Gelaran             | Jalur      | Tajuk atau nama aktiviti                                                               |
| Penerangan       | Jalur      | Perihalan aktiviti                                                                     |
| URL               | Jalur      | Pautan ke URL luaran yang khusus untuk aktiviti                                         |
| SemanticData      | Rentetan JSON | Termasuk senarai pasangan nilai utama untuk medan pemetaan semantik yang khusus untuk jenis aktiviti |
| RangeIndex        | Jalur      | Cap masa unix digunakan untuk menyusun garis masa aktiviti dan pertanyaan julat yang berkesan |
| mydynci_unifiedactivityid   | GUID | ID Dalaman aktiviti pelanggan (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Jadual ini mengandungi data output langkah berasaskan atribut pelanggan.

| Column             | Jenis             | Penerangan                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Jalur           | ID profil pelanggan        |
| Ukuran           | Rentetan JSON      | Termasuk senarai pasangan nilai utama untuk nama dan nilai ukuran bagi pelanggan yang ditetapkan | 
| msdynci_identifier | Jalur           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID profil pelanggan |


### <a name="enrichment"></a>Pengayaan

Jadual ini mengandungi output proses pengayaan.

| Column               | Jenis             |  Penerangan                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Jalur           | ID profil pelanggan                                 |
| EnrichmentProvider   | Jalur           | Nama pembekal untuk pengayaan                                  |
| EnrichmentType       | Jalur           | Jenis pengayaan                                      |
| Nilai               | Rentetan JSON      | Senarai atribut yang dihasilkan oleh proses pengayaan |
| msdynci_enrichmentid | GUID             | GUID berketentuan yang dijana daripada msdynci_identifier |
| msdynci_identifier   | Jalur           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Ramalan

Jadual ini mengandungi output ramalan model.

| Column               | Jenis        | Penerangan                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Jalur      | ID Profil Pelanggan                                  |
| ModelProvider        | Jalur      | Nama pembekal model                                      |
| Model                | Jalur      | Nama model                                                |
| Nilai               | Rentetan JSON | Senarai atribut yang dihasilkan oleh model |
| msdynci_predictionid | GUID        | GUID berketentuan yang dijana daripada msdynci_identifier | 
| msdynci_identifier   | Jalur      |  `Model|ModelProvider|CustomerId`                      |
