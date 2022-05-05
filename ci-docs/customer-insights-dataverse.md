---
title: Data Customer Insights dalam Microsoft Dataverse
description: Gunakan entiti Customer Insights sebagai jadual dalam Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 85995cbd7f797810bfb6ecdc8a24d56542f0b5a9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643080"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Gunakan data Customer Insights dalam Microsoft Dataverse

Customer Insights menyediakan pilihan untuk menjadikan entiti output tersedia dalam [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Integrasi ini membolehkan perkongsian data yang mudah dan pembangunan tersuai melalui pendekatan kod rendah / tanpa kod. Entiti [output](#output-entities) tersedia sebagai jadual dalam Dataverse persekitaran. Anda boleh menggunakan data untuk sebarang aplikasi lain berdasarkan Dataverse jadual. Jadual ini membolehkan senario seperti aliran kerja automatik melalui Power Automate atau membina aplikasi dengan Power Apps. Pelaksanaan semasa terutamanya menyokong carian di mana data daripada entiti Wawasan Pelanggan yang tersedia boleh diambil untuk ID pelanggan yang diberikan.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Lampirkan persekitaran Dataverse kepada Customer Insights

**Organisasi sedia ada**

Pentadbir boleh mengkonfigurasi Wawasan Pelanggan untuk [menggunakan persekitaran Dataverse sedia ada](create-environment.md) apabila mereka mencipta persekitaran Wawasan Pelanggan. Dengan menyediakan URL kepada Dataverse persekitaran, ia dilampirkan pada persekitaran Wawasan Pelanggan baharu mereka. Wawasan Pelanggan dan Dataverse persekitaran mesti dihoskan di rantau yang sama. 

Jika anda tidak mahu menggunakan persekitaran sedia ada Dataverse, sistem mencipta persekitaran baharu untuk data Wawasan Pelanggan dalam penyewa anda. 

> [!NOTE]
> Jika organisasi anda sudah menggunakan Dataverse penyewa mereka, adalah penting untuk diingat bahawa [Dataverse penciptaan persekitaran dikawal oleh pentadbir](/power-platform/admin/control-environment-creation). Contohnya, jika anda menyediakan persekitaran Wawasan Pelanggan baharu dengan akaun organisasi anda dan pentadbir telah menyahdayakan penciptaan Dataverse persekitaran percubaan untuk semua orang kecuali pentadbir, anda tidak boleh mencipta persekitaran percubaan baharu.
> 
> Persekitaran percubaan Dataverse yang dicipta dalam Customer Insights mempunyai 3 GB storan yang tidak akan mengira kapasiti keseluruhan yang diterima oleh penyewa. Langganan berbayar akan mendapat kelayakan Dataverse sebanyak 15 GB untuk pangkalan data dan 20 GB untuk storan fail.

**Organisasi baharu**

Jika anda mencipta organisasi baru apabila menyediakan Wawasan Pelanggan, sistem mencipta persekitaran baru Dataverse dalam organisasi anda secara automatik untuk anda.

## <a name="output-entities"></a>Entiti output

Sesetengah entiti output daripada Wawasan Pelanggan tersedia sebagai jadual dalam Dataverse. Bahagian di bawah menerangkan skema yang dijangka bagi jadual ini.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Pengayaan](#enrichment)
- [Ramalan](#prediction)
- [Keahlian segmen](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Jadual ini mengandungi profil pelanggan yang disatukan daripada Customer Insights. Skema untuk profil pelanggan yang disatukan bergantung pada entiti dan atribut yang digunakan dalam proses gabungan. Skema profil pelanggan biasanya mengandungi subset atribut daripada [definisi Common Data Model bagi CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Jadual AlternateKey mengandungi kunci entiti, yang mengambil bahagian dalam proses penyatuan.

|Column  |Jenis  |Penerangan  |
|---------|---------|---------|
|DataSourceName    |Jalur         | Nama sumber data. Contohnya: `datasource5`        |
|EntityName        | String        | Nama entiti dalam Wawasan Pelanggan. Contohnya: `contact1`        |
|AlternateValue    |String         |ID alternatif yang dipetakan kepada ID pelanggan. Contoh: `cntid_1078`         |
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
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Keahlian segmen

Jadual ini mengandungi maklumat keahlian segmen profil pelanggan.

| Column        | Taip | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID Profil Pelanggan        |
| SegmentProvider      | String       | Apl yang menerbitkan segmen.      |
| SegmentMembershipType | String       | Jenis pelanggan rekod keahlian segmen ini. Menyokong pelbagai jenis seperti Pelanggan, Kenalan atau Akaun. Lalai: Pelanggan  |
| Segmen       | Rentetan JSON  | Senarai segmen unik profil pelanggan adalah ahli      |
| msdynci_identifier  | String   | Pengenalpasti unik rekod keahlian segmen. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID penentu dijana daripada`msdynci_identifier`          |
