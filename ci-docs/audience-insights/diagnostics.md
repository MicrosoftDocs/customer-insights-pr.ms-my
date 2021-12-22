---
title: Audit Dynamics 365 Customer Insights dengan Azure Monitor
description: Ketahui cara menghantar log ke Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: d962c359d70a068fcf939b61e340f86de088b419
ms.sourcegitcommit: 0c3c473e0220de9ee3c1f1ee1825de0b3b3663c3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920873"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Log masuk Dynamics 365 Customer Insights dengan Azure Monitor (Pratonton)

Dynamics 365 Customer Insights menyediakan integrasi langsung dengan Azure Monitor. Azure Monitor log sumber membolehkan anda memantau dan menghantar log ke [Azure Storage, Azure Log Analytics, atau](https://azure.microsoft.com/services/storage/)[menstrimkannya](/azure/azure-monitor/logs/log-analytics-overview) ke [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

Wawasan Pelanggan menghantar log peristiwa berikut:

- **Acara Audit**
  - **APIEvent** - membolehkan penjejakan perubahan dilakukan melalui Dynamics 365 Customer Insights UI.
- **Aktiviti Operasi**
  - **WorkflowEvent** - Aliran Kerja membolehkan seseorang menyediakan [Sumber Data](data-sources.md), [menyatukan.](data-unification.md) dan [memperkayakan](enrichment-hub.md) dan akhirnya [mengeksport](export-destinations.md) data ke dalam sistem lain. Semua langkah tersebut boleh dilakukan secara individu (cth. mencetuskan eksport tunggal) atau diatur (contohnya segar semula data dari sumber data yang mencetuskan proses penyatuan yang akan menarik pengayaan tambahan dan sekali selesai mengeksport data ke dalam sistem lain). Untuk butiran lanjut lihat [WorkflowEvent Schema](#workflow-event-schema).
  - **APIEvent** - semua panggilan API kepada pelanggan contoh kepada Dynamics 365 Customer Insights. Untuk maklumat lanjut lihat [APIEvent Schema](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Sediakan seting diagnostik

### <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi diagnostik dalam Wawasan Pelanggan, prasyarat berikut mesti dipenuhi:

- Anda mempunyai [Langganan Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) yang aktif.
- Anda mempunyai [keizinan Pentadbir dalam Wawasan](permissions.md#administrator) Pelanggan.
- Anda mempunyai **peranan Penyumbang dan Pentadbir Akses Pengguna pada sumber destinasi di** **Azure**. Sumber boleh menjadi akaun Storan Azure, Hab Peristiwa Azure atau ruang kerja Azure Log Analytics. Untuk maklumat lanjut, lihat [Menambah atau mengalih keluar tugasan peranan Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).
- [Keperluan destinasi](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) untuk Azure Storage, Azure Event Hub atau Azure Log Analytics dipenuhi.
- Anda mempunyai sekurang-kurangnya **peranan Pembaca pada kumpulan sumber yang dimiliki oleh** sumber.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Sediakan diagnostik dengan Azure Monitor

1. Dalam Wawasan Pelanggan, pilih **Diagnostik Sistem untuk melihat destinasi diagnostik yang** > **dikonfigurasikan** tika ini.

1. Pilih **Tambah destinasi**.

   > [!div class="mx-imgBorder"]
   > ![Sambungan diagnostik](media/diagnostics-pane.png "Sambungan diagnostik")

1. Sediakan nama dalam **medan Nama untuk destinasi** diagnostik.

1. Pilih **Penyewa** langganan Azure dengan sumber destinasi dan pilih log **masuk**.

1. Pilih **jenis Sumber** (Akaun storan, Hab Acara atau analisis log).

1. Pilih **Langganan** untuk sumber destinasi.

1. Pilih **kumpulan Sumber** untuk sumber destinasi.

1. Pilih **Sumber**.

1. Sahkan **pernyataan privasi dan pematuhan** Data.

1. Pilih **Sambung ke sistem untuk menyambung ke sumber** destinasi. Log mula muncul di destinasi selepas 15 minit, jika API sedang digunakan dan menjana peristiwa.

### <a name="remove-a-destination"></a>Alih keluar destinasi

1. Pergi ke **Diagnostik Sistem** > **·**.

1. Pilih destinasi diagnostik dalam senarai.

1. Dalam **lajur** Tindakan, pilih **ikon** Padam.

1. Sahkan penghapusan untuk menghentikan pemajuan log. Sumber pada langganan Azure tidak akan dipadamkan. Anda boleh memilih pautan dalam **lajur Tindakan untuk membuka portal Azure untuk sumber yang dipilih dan** memadamkannya di sana.

## <a name="log-categories-and-event-schemas"></a>Kategori log dan skema peristiwa

Pada masa ini [peristiwa API dan peristiwa aliran kerja disokong dan kategori dan skema berikut](apis.md) digunakan.
Skema log mengikuti [skema umum Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategori

Wawasan Pelanggan menyediakan dua kategori:

- **Peristiwa audit** : Peristiwa API untuk mengesan perubahan konfigurasi pada [perkhidmatan](#api-event-schema). `POST|PUT|DELETE|PATCH` operasi masuk ke dalam kategori ini.
- **Peristiwa** operasi: [Peristiwa API atau peristiwa aliran kerja yang dijana semasa menggunakan](#api-event-schema)[perkhidmatan](#workflow-event-schema).  Contohnya, `GET` permintaan atau peristiwa pelaksanaan aliran kerja.

## <a name="configuration-on-the-destination-resource"></a>Konfigurasi pada sumber destinasi

Berdasarkan pilihan anda pada jenis sumber, langkah berikut akan digunakan secara automatik:

### <a name="storage-account"></a>Akaun storan

Prinsipal perkhidmatan Wawasan Pelanggan mendapat **keizinan Penyumbang Akaun Storan pada sumber yang dipilih dan mencipta dua bekas di bawah ruang nama yang** dipilih:

- `insight-logs-audit`**mengandungi peristiwa audit**
- `insight-logs-operational`**mengandungi peristiwa operasi**

### <a name="event-hub"></a>Hab Peristiwa

Prinsipal perkhidmatan Wawasan Pelanggan mendapat **keizinan Pemilik Data Hab Peristiwa Azure pada sumber dan akan mencipta dua Hab Acara di bawah ruang nama** yang dipilih:

- `insight-logs-audit`**mengandungi peristiwa audit**
- `insight-logs-operational`**mengandungi peristiwa operasi**

### <a name="log-analytics"></a>Analisis Log

Prinsipal perkhidmatan Wawasan Pelanggan mendapat **kebenaran Penyumbang Analitis Log** pada sumber tersebut. Log akan tersedia di bawah **Pengurusan Log Jadual Log pada ruang kerja** > **·** > **Analitis** Log yang dipilih. Kembangkan **penyelesaian Pengurusan Log** dan cari `CIEventsAudit` dan `CIEventsOperational` jadual.

- `CIEventsAudit`**mengandungi peristiwa audit**
- `CIEventsOperational`**mengandungi peristiwa operasi**

Di bawah **tetingkap** Pertanyaan, kembangkan penyelesaian Audit dan **cari contoh pertanyaan yang disediakan dengan mencari**`CIEvents`.

## <a name="event-schemas"></a>Skema peristiwa

Peristiwa API dan peristiwa aliran kerja mempunyai struktur dan butiran umum di mana ia berbeza, lihat [skema peristiwa API atau skema peristiwa aliran kerja](#api-event-schema)[...](#workflow-event-schema).

### <a name="api-event-schema"></a>Skema peristiwa API

| Medan             | Jenis Data  | Diperlukan/Pilihan | Description       | Contoh        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Cap Masa | Wajib          | Cap waktu peristiwa (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Wajib          | ResourceId contoh yang memancarkan peristiwa         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Wajib          | Nama operasi yang diwakili oleh peristiwa ini.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Wajib          | Kategori log peristiwa. Sama ada `Operational` atau `Audit`. Semua Permintaan POST / PUT / PATCH / DELETE HTTP ditandakan dengan `Audit`, segala-galanya dengan`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Wajib          | Status peristiwa. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Pilihan          | Status keputusan peristiwa. Jika operasi sepadan dengan panggilan API REST, ia adalah kod status HTTP.        | `200`             |
| `durationMs`      | Panjang      | Pilihan          | Tempoh operasi dalam milisaat.     | `133`     |
| `callerIpAddress` | String    | Pilihan          | Alamat IP pemanggil, jika operasi sepadan dengan panggilan API yang datang dari alamat IP yang tersedia secara umum.                                                 | `144.318.99.233`         |
| `identity`        | String    | Pilihan          | Objek JSON menerangkan identiti pengguna atau aplikasi yang melakukan operasi.       | Lihat [Bahagian](#identity-schema) Identiti.     |  |
| `properties`      | String    | Pilihan          | Objek JSON dengan lebih banyak sifat kepada kategori acara tertentu.      | Lihat [Bahagian](#api-properties-schema) Sifat.    |
| `level`           | String    | Wajib          | Tahap keterukan peristiwa.    | `Informational`, `Warning`, `Error` atau `Critical`.           |
| `uri`             | String    | Pilihan          | URI permintaan mutlak.    |               |

#### <a name="identity-schema"></a>Skema identiti

Objek `identity` JSON mempunyai struktur berikut

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Medan                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Peranan yang diuntukkan untuk pengguna atau aplikasi. Untuk maklumat lanjut, lihat [keizinan pengguna](permissions.md).                                     |
| `Authorization.RequiredRoles` | Peranan yang diperlukan untuk melakukan operasi. `Admin` dibenarkan untuk melakukan semua operasi.                                                    |
| `Claims`                      | Tuntutan token web pengguna atau aplikasi JSON (JWT). Sifat tuntutan berbeza-beza bagi setiap organisasi dan Azure Active Directory konfigurasi. |

#### <a name="api-properties-schema"></a>Skema sifat API

[Peristiwa API](apis.md) mempunyai sifat berikut.

| Medan                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Sentiasa `ApiEvent`, menandakan peristiwa log sebagai peristiwa API.                                                                 |
| `properties.userAgent`       | Ejen pelayar menghantar permintaan atau `unknown`.                                                                        |
| `properties.method`          | Kaedah HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Laluan relatif permintaan.                                                                                          |
| `properties.origin`          | URI menunjukkan dari mana pengambilan berasal atau `unknown`.                                                                  |
| `properties.operationStatus` | `Success` untuk kod Status HTTP < 400 <br> `ClientError` untuk kod Status HTTP < 500 <br> `Error` untuk status HTTP >= 500 |
| `properties.tenantId`        | ID Organisasi                                                                                                        |
| `properties.tenantName`      | Nama organisasi.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId pemanggil.                                                                         |
| `properties.instanceId`      | Wawasan Pelanggan`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Skema peristiwa aliran kerja

Aliran kerja mengandungi berbilang langkah. [Menelan sumber data](data-sources.md), [menyatukan,](data-unification.md)[memperkayakan](enrichment-hub.md), dan mengeksport [data](export-destinations.md). Semua langkah tersebut boleh dijalankan secara individu atau diatur dengan proses berikut. 

#### <a name="operation-types"></a>Jenis operasi

| JenisOperasi     | Kumpulkan                                     |
| ----------------- | ----------------------------------------- |
| Pengingesan         | [Sumber data](data-sources.md)           |
| Persediaan Data   | [Sumber data](data-sources.md)           |
| Petakan               | [Penyatuan data](data-unification.md)   |
| Padankan             | [Penyatuan data](data-unification.md)   |
| Gabungkan             | [Penyatuan data](data-unification.md)   |
| Kedai Profil      | [Profil pelanggan](customer-profiles.md) |
| Carian            | [Profil pelanggan](customer-profiles.md) |
| Aktiviti          | [Aktiviti](activities.md)                  |
| AttributeMeasures | [Segmen dan Langkah](segments.md)      |
| EntityMeasures    | [Segmen dan Langkah](segments.md)      |
| Langkah          | [Segmen dan Langkah](segments.md)      |
| Pembahagian      | [Segmen dan Langkah](segments.md)      |
| Pengayaan        | [Pengayaan](enrichment-hub.md)                                          |
| Risikan      | [Ramalan](predictions-overview.md)                                          |
| AiBuilder         | [Ramalan](predictions-overview.md)                                          |
| Wawasan          | [Ramalan](predictions-overview.md)                                          |
| Export            | [Eksport](export-destinations.md)                                          |
| ModelManagement   | [Ramalan](custom-models.md)                                           |
| Perhubungan      | [Penyatuan data](relationships.md)                                           |

#### <a name="field-description"></a>Perihalan medan

| Medan           | Jenis Data  | Diperlukan/Pilihan | Description                                                                                                                                                   | Contoh                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Cap Masa | Wajib          | Cap waktu peristiwa (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Wajib          | ResourceId contoh yang memancarkan peristiwa itu.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Wajib          | Nama operasi yang diwakili oleh peristiwa ini. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Lihat [Jenis Operasi untuk](#operation-types) rujukan. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Wajib          | Kategori log peristiwa. Sentiasa `Operational` untuk peristiwa Aliran Kerja                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Wajib          | Status peristiwa. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Panjang      | Pilihan          | Tempoh operasi dalam milisaat.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Pilihan          | Objek JSON dengan lebih banyak sifat kepada kategori acara tertentu.                                                                                        | Lihat sub seksyen [Sifat Aliran Kerja](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Wajib          | Tahap keterukan peristiwa.                                                                                                                                  | `Informational`, `Warning` atau `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Skema sifat aliran kerja

Peristiwa aliran kerja mempunyai sifat berikut.

| Medan              | Workflow | Tugas | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ya      | Ya  | Sentiasa `WorkflowEvent`, menandakan peristiwa sebagai peristiwa aliran kerja.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ya      | Ya  | Pengenalpasti aliran kerja. Semua aliran kerja dan peristiwa tugas dalam pelaksanaan aliran kerja mempunyai perkara yang sama `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ya      | Ya  | Pengenalpasti operasi, lihat [Jenis operasi]. (jenis #operation)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Ya      | No   | Aliran kerja sahaja. Bilangan tugas yang mencetuskan aliran kerja.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ya      | No   | Tidak wajib Peristiwa aliran kerja sahaja. Azure Active Directory [ObjekId pengguna](/azure/marketplace/find-tenant-object-id#find-user-object-id) yang mencetuskan aliran kerja, lihat juga `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ya      | No   | `full` atau `incremental` segar semula.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ya      | No   | `OnDemand` atau `Scheduled`                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ya      | No   | `Running` atau `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ya      | Ya  | Setem Masa UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ya      | Ya  | Setem Masa UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ya      | Ya  | Setem Masa UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ya      | Ya  | Wawasan Pelanggan`instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Ya  | - Untuk OperationType = `Export`, pengecam adalah panduan konfigurasi eksport. <br> - Untuk OperationType = `Enrichment`, ia adalah panduan pengayaan <br> - Untuk OperasiType `Measures` dan, pengecam adalah nama `Segmentation` entiti. |
| `properties.friendlyName`                    | No       | Ya  | Nama mesra pengguna eksport atau entiti yang diproses.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ya  | Tidak wajib Mesej ralat dengan butiran lanjut.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ya  | Tidak wajib Untuk OperasiType `Export` sahaja. Kenalpasti jenis eksport. Untuk maklumat lanjut, lihat [gambaran keseluruhan destinasi eksport](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ya  | Tidak wajib Untuk OperasiType `Export` sahaja. Mengandungi senarai entiti yang dikonfigurasi dalam eksport.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ya  | Tidak wajib Untuk OperasiType `Export` sahaja. Mesej terperinci untuk eksport.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ya  | Tidak wajib Untuk OperasiType `Segmentation` sahaja. Menunjukkan jumlah bilangan ahli yang ada dalam segmen ini.                                                                                                                                                    |
