---
title: Audit Dynamics 365 Customer Insights dengan Azure Monitor
description: Ketahui cara menghantar log ke Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 2e0801c2b6af591e48a7df485a8523903c07617c
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354419"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Log pemajuan Dynamics 365 Customer Insights dengan Azure Monitor (Preview)

Dynamics 365 Customer Insights menyediakan integrasi langsung dengan Azure Monitor. Azure Monitor resource logs membolehkan anda memantau dan menghantar log ke [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), atau menstrimkannya ke [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

Wawasan Pelanggan dihantar log peristiwa berikut:

- **Aktiviti Audit**
  - **APIEvent** - membolehkan pengesanan perubahan dilakukan melalui Dynamics 365 Customer Insights UI.
- **Acara Operasi**
  - **WorkflowEvent** - Aliran Kerja membolehkan seseorang untuk menyediakan [Sumber](data-sources.md) Data, [menyatukan](data-unification.md) dan [memperkayakan](enrichment-hub.md) dan akhirnya [mengeksport](export-destinations.md) data ke dalam sistem lain. Semua langkah tersebut boleh dilakukan secara individu (contohnya mencetuskan eksport tunggal) atau disusun (cth. segar semula data dari sumber data yang mencetuskan proses penyatuan yang akan menarik pengayaan tambahan dan setelah selesai mengeksport data ke dalam sistem lain). Untuk maklumat lanjut, lihat [WorkflowEvent Schema](#workflow-event-schema).
  - **APIEvent** - semua API panggilan kepada tika pelanggan untuk Dynamics 365 Customer Insights. Untuk maklumat lanjut, lihat [SKEMA APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Sediakan seting diagnostik

### <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi diagnostik dalam Wawasan Pelanggan, prasyarat berikut mesti dipenuhi:

- Anda mempunyai Langganan [Azure yang aktif](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Anda mempunyai [keizinan Pentadbir](permissions.md#administrator) dalam Wawasan Pelanggan.
- Anda mempunyai **peranan Pentadbir** Penyumbang **dan** Capaian Pengguna pada sumber destinasi di Azure. Sumber boleh menjadi akaun Storan Azure, Hab Acara Azure atau ruang kerja Azure Log Analytics. Untuk maklumat lanjut, lihat [Menambah atau mengalih keluar tugasan peranan Azure menggunakan portal](/azure/role-based-access-control/role-assignments-portal) Azure.
- [Destination requirements](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) for Azure Storage, Azure Event Hub atau Azure Log Analytics met.
- Anda mempunyai sekurang-kurangnya **peranan Pembaca** pada kumpulan sumber sumber yang dimiliki oleh sumber.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Sediakan diagnostics with Azure Monitor

1. Dalam Wawasan Pelanggan, pilih **SystemDiagnostik** > **untuk** melihat destinasi diagnostik yang dikonfigurasikan tika ini.

1. Pilih **Tambah destinasi**.

   > [!div class="mx-imgBorder"]
   > ![Sambungan diagnostik](media/diagnostics-pane.png "Sambungan diagnostik")

1. Sediakan nama dalam **medan Nama untuk destinasi** diagnostik.

1. **Pilih Penyewa** langganan Azure dengan sumber destinasi dan pilih **log masuk**.

1. **Pilih jenis** Sumber (Akaun storan, Hab Acara atau analisis log).

1. **Pilih Langganan** untuk sumber destinasi.

1. **Pilih kumpulan** Sumber untuk sumber destinasi.

1. **Pilih Sumber**.

1. **Sahkan kenyataan privasi dan pematuhan** Data.

1. Pilih **Sambung ke sistem** untuk menyambung ke sumber destinasi. Log mula muncul di destinasi selepas 15 minit, jika API sedang digunakan dan menjana peristiwa.

### <a name="remove-a-destination"></a>Alih keluar destinasi

1. Pergi ke **SystemDiagnostik** > **·**.

1. Pilih destinasi diagnostik dalam senarai.

1. **Dalam lajur Tindakan**, pilih **ikon Padam**.

1. Sahkan pemadaman untuk menghentikan pemajuan log. Sumber pada langganan Azure tidak akan dipadamkan. Anda boleh memilih pautan dalam **lajur Tindakan** untuk membuka portal Azure untuk sumber yang dipilih dan memadamkannya di sana.

## <a name="log-categories-and-event-schemas"></a>Log kategori dan skema peristiwa

Pada masa ini [acara](apis.md) API dan acara aliran kerja disokong dan kategori dan skema berikut digunakan.
Skema log mengikuti [skema biasa Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategori

Wawasan Pelanggan menyediakan dua kategori:

- **Peristiwa audit**: [Peristiwa](#api-event-schema) API untuk menjejak perubahan konfigurasi pada perkhidmatan. `POST|PUT|DELETE|PATCH` operasi masuk ke dalam kategori ini.
- **Acara operasi**: [Peristiwa](#api-event-schema) API atau [peristiwa](#workflow-event-schema) aliran kerja yang dijana semasa menggunakan perkhidmatan.  Sebagai contoh, `GET` permintaan atau peristiwa pelaksanaan aliran kerja.

## <a name="configuration-on-the-destination-resource"></a>Konfigurasi pada sumber destinasi

Berdasarkan pilihan anda pada jenis sumber, langkah-langkah berikut akan digunakan secara automatik:

### <a name="storage-account"></a>Akaun storan

Prinsipal perkhidmatan Wawasan Pelanggan mendapat **keizinan Penyumbang** Akaun Storan pada sumber yang dipilih dan mencipta dua bekas di bawah ruang nama yang dipilih:

- `insight-logs-audit` mengandungi **peristiwa audit**
- `insight-logs-operational` mengandungi **peristiwa operasi**

### <a name="event-hub"></a>Hab Peristiwa

Prinsipal perkhidmatan Customer Insights mendapat **kebenaran Pemilik** Data Hab Peristiwa Azure pada sumber dan akan mencipta dua Hab Peristiwa di bawah ruang nama yang dipilih:

- `insight-logs-audit` mengandungi **peristiwa audit**
- `insight-logs-operational` mengandungi **peristiwa operasi**

### <a name="log-analytics"></a>Analitis Log

Prinsipal perkhidmatan Wawasan Pelanggan mendapat **kebenaran Penyumbang** Analitis Log pada sumber. Log akan tersedia di bawah **Pengurusan** > **LogsTablesLog** > **pada** ruang kerja Analitis Log yang dipilih. **Kembangkan penyelesaian Pengurusan** Log dan cari `CIEventsAudit` dan `CIEventsOperational` jadual.

- `CIEventsAudit` mengandungi **peristiwa audit**
- `CIEventsOperational` mengandungi **peristiwa operasi**

**Di bawah tetingkap Pertanyaan**, kembangkan **penyelesaian Audit** dan cari pertanyaan contoh yang disediakan dengan mencari `CIEvents`.

## <a name="event-schemas"></a>Skema peristiwa

Acara API dan acara aliran kerja mempunyai struktur dan butiran yang sama di mana ia berbeza, lihat [skema](#api-event-schema) peristiwa API atau [skema](#workflow-event-schema) peristiwa aliran kerja.

### <a name="api-event-schema"></a>Skema acara API

| Medan             | Jenis Data  | Diperlukan/Pilihan | Description       | Contoh        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Cap Masa | Wajib          | Cap waktu acara (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Wajib          | ResourceId bagi tika yang dipancarkan peristiwa         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Wajib          | Nama operasi yang diwakili oleh peristiwa ini.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Wajib          | Kategori log peristiwa. Sama ada `Operational` atau `Audit`. Semua Post/ PUT / PATCH / DELETE Permintaan HTTP ditandakan dengan `Audit`, segala-galanya dengan`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Wajib          | Status peristiwa. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Pilihan          | Status keputusan peristiwa. Jika operasi sepadan dengan panggilan API REST, ia ialah kod status HTTP.        | `200`             |
| `durationMs`      | Panjang      | Pilihan          | Tempoh operasi dalam milisaat.     | `133`     |
| `callerIpAddress` | String    | Pilihan          | Alamat IP pemanggil, jika operasi sepadan dengan panggilan API yang datang daripada alamat IP yang tersedia secara umum.                                                 | `144.318.99.233`         |
| `identity`        | String    | Pilihan          | JSON membantah menerangkan identiti pengguna atau aplikasi yang melakukan operasi.       | Lihat [Bahagian Identiti](#identity-schema).     |  |
| `properties`      | String    | Pilihan          | JSON objek dengan lebih banyak sifat kepada kategori peristiwa tertentu.      | Lihat [Bahagian Sifat](#api-properties-schema).    |
| `level`           | String    | Wajib          | Tahap keterukan peristiwa.    | `Informational`, `Warning`, `Error`, atau `Critical`.           |
| `uri`             | String    | Pilihan          | Permintaan mutlak URI.    |               |

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
| `Authorization.UserRole`      | Peranan yang diuntukkan untuk pengguna atau aplikasi. Untuk maklumat lanjut, lihat [keizinan](permissions.md) pengguna.                                     |
| `Authorization.RequiredRoles` | Peranan yang diperlukan untuk melakukan operasi. `Admin` dibenarkan untuk melakukan semua operasi.                                                    |
| `Claims`                      | Tuntutan token web pengguna atau aplikasi JSON (JWT). Sifat tuntutan berbeza-beza mengikut organisasi dan Azure Active Directory konfigurasi. |

#### <a name="api-properties-schema"></a>Skema sifat API

[Peristiwa](apis.md) API mempunyai sifat berikut.

| Medan                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Sentiasa `ApiEvent`, menandakan peristiwa log sebagai peristiwa API.                                                                 |
| `properties.userAgent`       | Ejen pelayar menghantar permintaan atau `unknown`.                                                                        |
| `properties.method`          | Kaedah HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Laluan relatif permintaan.                                                                                          |
| `properties.origin`          | URI menunjukkan dari mana diambil berasal atau `unknown`.                                                                  |
| `properties.operationStatus` | `Success` untuk kod Status HTTP < 400 <br> `ClientError` untuk kod Status HTTP < 500 <br> `Error` untuk Status HTTP >= 500 |
| `properties.tenantId`        | ID Organisasi                                                                                                        |
| `properties.tenantName`      | Nama organisasi.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId pemanggil.                                                                         |
| `properties.instanceId`      | Wawasan Pelanggan`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Skema peristiwa aliran kerja

Aliran kerja mengandungi berbilang langkah. [Sumber data](data-sources.md) Ingest, [menyatukan](data-unification.md), [memperkayakan](enrichment-hub.md), dan [mengeksport](export-destinations.md) data. Semua langkah tersebut boleh berjalan secara individu atau diatur dengan proses berikut. 

#### <a name="operation-types"></a>Jenis operasi

| JenisOperasi     | Kumpulkan                                     |
| ----------------- | ----------------------------------------- |
| Pengingesan         | [Sumber data](data-sources.md)           |
| DataPreparation   | [Sumber data](data-sources.md)           |
| Petakan               | [Penyatuan data](data-unification.md)   |
| Padankan             | [Penyatuan data](data-unification.md)   |
| Gabungkan             | [Penyatuan data](data-unification.md)   |
| ProfilStore      | [Profil pelanggan](customer-profiles.md) |
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
| `time`          | Cap Masa | Wajib          | Cap waktu acara (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Wajib          | ResourceId dari contoh yang memancarkan peristiwa.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Wajib          | Nama operasi yang diwakili oleh peristiwa ini. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Lihat [Jenis](#operation-types) Operasi untuk rujukan. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Wajib          | Kategori log peristiwa. Sentiasa `Operational` untuk peristiwa Aliran Kerja                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Wajib          | Status peristiwa. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Panjang      | Pilihan          | Tempoh operasi dalam milisaat.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Pilihan          | JSON objek dengan lebih banyak sifat kepada kategori peristiwa tertentu.                                                                                        | Lihat sub seksyen [Sifat Aliran Kerja](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Wajib          | Tahap keterukan peristiwa.                                                                                                                                  | `Informational`, `Warning` atau `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Skema sifat aliran kerja

Peristiwa aliran kerja mempunyai sifat berikut.

| Medan              | Workflow | Tugas | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ya      | Ya  | Sentiasa `WorkflowEvent`, menandakan peristiwa sebagai peristiwa aliran kerja.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ya      | Ya  | Pengenalpasti aliran kerja berjalan. Semua aliran kerja dan peristiwa tugas dalam pelaksanaan aliran kerja mempunyai yang sama `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ya      | Ya  | Pengenalpasti operasi, lihat [Jenis operasi]. (#operation-jenis)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Ya      | No   | Aliran kerja sahaja. Bilangan tugas yang dicetuskan oleh aliran kerja.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ya      | No   | Tidak wajib Peristiwa aliran kerja sahaja. ObjekId Azure Active Directory [pengguna](/azure/marketplace/find-tenant-object-id#find-user-object-id) yang mencetuskan aliran kerja, lihat juga `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ya      | No   | `full` atau `incremental` segar semula.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ya      | No   | `OnDemand` atau `Scheduled`                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ya      | No   | `Running` atau `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ya      | Ya  | Cap Waktu UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ya      | Ya  | Cap Waktu UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ya      | Ya  | Cap Waktu UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ya      | Ya  | Wawasan Pelanggan`instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Ya  | - Untuk OperasiType = `Export`, pengecam adalah guid konfigurasi eksport. <br> - Untuk OperasiType = `Enrichment`, itu adalah guid dari pengayaan <br> - Untuk OperasiType `Measures` dan `Segmentation`, pengecam adalah nama entiti. |
| `properties.friendlyName`                    | No       | Ya  | Nama mesra pengguna eksport atau entiti yang diproses.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ya  | Tidak wajib Mesej ralat dengan butiran lanjut.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ya  | Tidak wajib Untuk Jenis Operasi `Export` sahaja. Mengenal pasti jenis eksport. Untuk maklumat lanjut, lihat [gambaran keseluruhan destinasi](export-destinations.md) eksport.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ya  | Tidak wajib Untuk Jenis Operasi `Export` sahaja. Mengandungi senarai entiti yang dikonfigurasi dalam eksport.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ya  | Tidak wajib Untuk Jenis Operasi `Export` sahaja. Mesej terperinci untuk eksport.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ya  | Tidak wajib Untuk Jenis Operasi `Segmentation` sahaja. Menunjukkan jumlah bilangan ahli segmen.                                                                                                                                                    |
