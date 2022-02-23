---
title: Data Wawasan Pelanggan dalam Microsoft Dataverse
description: Gunakan entiti Wawasan Pelanggan sebagai jadual dalam Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866945"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Bekerja dengan data Wawasan Pelanggan dalam Microsoft Dataverse

Wawasan Pelanggan menyediakan pilihan untuk menjadikan entiti output tersedia dalam [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Integrasi ini membolehkan perkongsian data yang mudah dan pembangunan tersuai melalui kod rendah / tiada pendekatan kod. Entiti output akan tersedia sebagai jadual dalam Dataverse. Jadual ini mendayakan senario seperti [aliran kerja automatik melalui](/power-automate/getting-started) Power Automate, aplikasi [dipacu model](/powerapps/maker/model-driven-apps/) dan aplikasi kanvas melalui [Power](/powerapps/maker/canvas-apps/) Apps. Anda boleh menggunakan data untuk sebarang aplikasi lain yang berdasarkan jadual Dataverse. Pelaksanaan semasa kebanyakannya menyokong carian tempat data daripada entiti cerapan khalayak yang tersedia dapat diambil untuk ID pelanggan yang ditetapkan.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Lampirkan persekitaran Dataverse pada Wawasan Pelanggan

**Organisasi dengan persekitaran Dataverse sedia ada**

Organisasi yang telah menggunakan Dataverse boleh [menggunakan salah satu persekitaran Dataverse sedia ada mereka apabila pentadbir menyediakan wawasan](create-environment.md) khalayak. Dengan menyediakan URL ke persekitaran Dataverse, ia melekat pada persekitaran cerapan khalayak baharu mereka. Untuk memastikan prestasi yang terbaik, Wawasan Pelanggan dan persekitaran Dataverse mesti dihoskan di rantau yang sama.

**Organisasi baharu**

Jika anda mencipta organisasi baharu apabila menyediakan Wawasan Pelanggan, anda akan mendapat persekitaran Dataverse baharu secara automatik.

> [!NOTE]
> Jika organisasi anda sudah menggunakan Dataverse dalam penyewa mereka, penting untuk diingat bahawa [penciptaan persekitaran Dataverse dikawal oleh pentadbir](/power-platform/admin/control-environment-creation.md) . Sebagai contoh, jika anda menyediakan persekitaran wawasan khalayak baharu dengan akaun organisasi anda dan pentadbir telah melumpuhkan penciptaan persekitaran percubaan Dataverse untuk semua orang kecuali pentadbir, anda tidak boleh mencipta persekitaran percubaan baharu.
> 
> Persekitaran percubaan Dataverse yang dicipta dalam Wawasan Pelanggan mempunyai storan 3 GB yang tidak akan dikira terhadap kapasiti keseluruhan yang berhak kepada penyewa. Langganan berbayar mendapat hak Dataverse 15 GB untuk pangkalan data dan 20 GB untuk storan fail.

## <a name="output-entities"></a>Entiti output

Sesetengah entiti output daripada wawasan khalayak tersedia sebagai jadual dalam Dataverse. Bahagian di bawah menerangkan skema yang dijangka bagi jadual ini.

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
|EntityName        | Jalur        | Nama entiti dalam cerapan khalayak. Contohnya: `contact1`        |
|AlternateValue    |Jalur         |ID alternatif yang dipetakan kepada ID pelanggan. Contoh: `cntid_1078`         |
|KeyRing           | Teks berbilang baris        | Nilai JSON  </br> Sample: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"kekunci":[" cntid_1078"]}]       |
|CustomerId         | String        | ID profil pelanggan yang disatukan.         |
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
| SegmentProvider      | String       | Aplikasi yang menerbitkan segmen. Lalai: Cerapan khalayak         |
| SegmentMembershipType | String       | Jenis pelanggan rekod keahlian segmen ini. Menyokong pelbagai jenis seperti Pelanggan, Kenalan atau Akaun. Lalai: Pelanggan  |
| Segmen       | Rentetan JSON  | Senarai segmen unik profil pelanggan adalah ahli      |
| msdynci_identifier  | String   | Pengenalpasti unik rekod keahlian segmen. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID deterministik yang dijana daripada`msdynci_identifier`          |
