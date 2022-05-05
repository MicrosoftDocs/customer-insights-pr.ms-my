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
ms.openlocfilehash: 18fc072d129be6b4fc5470b1057f592dc2638216
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643033"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Log pemajuan masuk Dynamics 365 Customer Insights dengan Azure Monitor (Preview)

Dynamics 365 Customer Insights menyediakan integrasi langsung dengan Azure Monitor. Azure Monitor resource log membolehkan anda memantau dan menghantar log ke [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), atau menstrimnya ke [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

Wawasan Pelanggan menghantar log peristiwa berikut:

- **Peristiwa Audit**
  - **APIEvent** - membolehkan penjejakan perubahan dilakukan melalui Dynamics 365 Customer Insights UI.
- **Acara Operasi**
  - **WorkflowEvent** - Aliran Kerja membolehkan seseorang menyediakan [Sumber](data-sources.md) Data, [menyatukan](data-unification.md) dan [memperkayakan](enrichment-hub.md) dan akhirnya [mengeksport](export-destinations.md) data ke dalam sistem lain. Semua langkah tersebut boleh dilakukan secara individu (contohnya mencetuskan eksport tunggal) atau diatur (contohnya segar semula data daripada sumber data yang mencetuskan proses penyatuan yang akan menarik pengayaan tambahan dan sekali dilakukan mengeksport data ke dalam sistem lain). Untuk maklumat lanjut, lihat [Aliran KerjaEvent Schema](#workflow-event-schema).
  - **APIEvent** - semua panggilan API kepada pelanggan contoh ke Dynamics 365 Customer Insights. Untuk maklumat lanjut, lihat [APIEvent Schema](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Sediakan seting diagnostik

### <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi diagnostik dalam Wawasan Pelanggan, prasyarat berikut mesti dipenuhi:

- Anda mempunyai Langganan [Azure yang aktif](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Anda mempunyai [keizinan Pentadbir](permissions.md#admin) dalam Wawasan Pelanggan.
- Anda mempunyai **peranan Pentadbir** Penyumbang **dan** Akses Pengguna pada sumber destinasi di Azure. Sumber boleh menjadi akaun Azure Storage, Azure Event Hub, atau ruang kerja Azure Log Analytics. Untuk maklumat lanjut, lihat [Menambah atau mengalih keluar tugasan peranan Azure menggunakan portal](/azure/role-based-access-control/role-assignments-portal) Azure.
- [Keperluan destinasi](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) untuk Azure Storage, Azure Event Hub, atau Azure Log Analytics met.
- Anda mempunyai sekurang-kurangnya **peranan Pembaca** pada kumpulan sumber yang dimiliki oleh sumber.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Sediakan diagnostik dengan Azure Monitor

1. Dalam Wawasan Pelanggan, pilih **SistemDiagnostik** > **untuk** melihat destinasi diagnostik yang dikonfigurasikan contoh ini.

1. Pilih **Tambah destinasi**.

   > [!div class="mx-imgBorder"]
   > ![Sambungan diagnostik](media/diagnostics-pane.png "Sambungan diagnostik")

1. Berikan nama dalam **medan Destinasi** Nama untuk diagnostik.

1. **Pilih Penyewa** langganan Azure dengan sumber destinasi dan pilih **log masuk**.

1. **Pilih jenis** Sumber (Akaun penyimpanan, Hab Acara, atau analisis log).

1. **Pilih Langganan** untuk sumber destinasi.

1. **Pilih kumpulan** Sumber untuk sumber destinasi.

1. **Pilih Sumber**.

1. Sahkan kenyataan **privasi dan pematuhan** Data.

1. Pilih **Sambung ke sistem** untuk menyambung ke sumber destinasi. Log mula muncul di destinasi selepas 15 minit, jika API sedang digunakan dan menjana peristiwa.

### <a name="remove-a-destination"></a>Alih keluar destinasi

1. Pergi ke **SistemDiagnostik** > **·**.

1. Pilih destinasi diagnostik dalam senarai.

1. **Dalam lajur Tindakan**, pilih **ikon Padam**.

1. Sahkan penghapusan untuk menghentikan pemajuan log. Sumber pada langganan Azure tidak akan dipadamkan. Anda boleh memilih pautan dalam **lajur Tindakan** untuk membuka portal Azure untuk sumber yang dipilih dan memadamkannya di sana.

## <a name="log-categories-and-event-schemas"></a>Kategori log dan skema acara

Pada masa ini [acara](apis.md) API dan peristiwa aliran kerja disokong dan kategori dan skema berikut digunakan.
Skema log mengikut [skema biasa Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategori

Wawasan Pelanggan menyediakan dua kategori:

- **Peristiwa audit**: [Peristiwa](#api-event-schema) API untuk mengesan perubahan konfigurasi pada perkhidmatan. `POST|PUT|DELETE|PATCH` operasi masuk ke dalam kategori ini.
- **Peristiwa** operasi: [Peristiwa](#api-event-schema) API atau [peristiwa](#workflow-event-schema) aliran kerja yang dijana semasa menggunakan perkhidmatan.  Sebagai contoh, `GET` permintaan atau peristiwa pelaksanaan aliran kerja.

## <a name="configuration-on-the-destination-resource"></a>Konfigurasi pada sumber destinasi

Berdasarkan pilihan anda pada jenis sumber, langkah-langkah berikut akan digunakan secara automatik:

### <a name="storage-account"></a>Akaun storan

Prinsipal perkhidmatan Wawasan Pelanggan mendapat **keizinan Penyumbang** Akaun Storan pada sumber yang dipilih dan mencipta dua bekas di bawah ruang nama yang dipilih:

- `insight-logs-audit` mengandungi **peristiwa audit**
- `insight-logs-operational` mengandungi **peristiwa operasi**

### <a name="event-hub"></a>Hab Peristiwa

Prinsipal perkhidmatan Wawasan Pelanggan mendapat **keizinan Pemilik** Data Azure Event Hubs pada sumber dan akan mencipta dua Hab Acara di bawah ruang nama yang dipilih:

- `insight-logs-audit` mengandungi **peristiwa audit**
- `insight-logs-operational` mengandungi **peristiwa operasi**

### <a name="log-analytics"></a>Analitis Log

Prinsipal perkhidmatan Wawasan Pelanggan mendapat **kebenaran Penyumbang Analitis** Log pada sumber. Log akan tersedia di bawah **Pengurusan** > **LogsTablesLog** > **pada** ruang kerja Analisis Log yang dipilih. Kembangkan **penyelesaian Pengurusan** Log dan cari `CIEventsAudit` dan `CIEventsOperational` jadual.

- `CIEventsAudit` mengandungi **peristiwa audit**
- `CIEventsOperational` mengandungi **peristiwa operasi**

**Di bawah tetingkap Pertanyaan**, kembangkan **penyelesaian Audit** dan cari contoh pertanyaan yang disediakan dengan mencari `CIEvents`.

## <a name="event-schemas"></a>Skema peristiwa

Peristiwa API dan peristiwa aliran kerja mempunyai struktur dan butiran yang sama di mana ia berbeza, lihat [Skema](#api-event-schema) peristiwa API atau [skema](#workflow-event-schema) peristiwa aliran kerja.

### <a name="api-event-schema"></a>API event schema

| Medan             | DataType  | Diperlukan/Pilihan | Description       | Contoh        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Cap Masa | Wajib          | Cap masa acara (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Wajib          | ResourceId dari contoh yang memancarkan peristiwa         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Wajib          | Nama operasi yang diwakili oleh peristiwa ini.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Wajib          | Kategori log acara. Sama ada `Operational` atau `Audit`. Semua Permintaan HTTP POST/PUT/PATCH/DELETE ditandakan dengan `Audit`, segala-galanya dengan`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Wajib          | Status acara. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Pilihan          | Status keputusan acara. Jika operasi sepadan dengan panggilan API REST, ia adalah kod status HTTP.        | `200`             |
| `durationMs`      | Panjang      | Pilihan          | Tempoh operasi dalam milisaat.     | `133`     |
| `callerIpAddress` | String    | Pilihan          | Alamat IP pemanggil, jika operasi sepadan dengan panggilan API yang datang dari alamat IP yang tersedia secara umum.                                                 | `144.318.99.233`         |
| `identity`        | String    | Pilihan          | Objek JSON menerangkan identiti pengguna atau aplikasi yang melakukan operasi.       | Lihat [Bahagian Identiti](#identity-schema).     |  
| `properties`      | String    | Pilihan          | Objek JSON dengan lebih banyak sifat kepada kategori peristiwa tertentu.      | Lihat [Bahagian Sifat](#api-properties-schema).    |
| `level`           | String    | Wajib          | Tahap keterukan acara.    | `Informational`, `Warning`, `Error`, atau `Critical`.           |
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
| `Authorization.UserRole`      | Peranan yang diperuntukkan untuk pengguna atau aplikasi. Untuk maklumat lanjut, lihat [keizinan](permissions.md) pengguna.                                     |
| `Authorization.RequiredRoles` | Peranan yang diperlukan untuk melakukan operasi. `Admin` peranan dibenarkan untuk melakukan semua operasi.                                                    |
| `Claims`                      | Tuntutan pengguna atau aplikasi JSON token web (JWT). Sifat tuntutan berbeza mengikut organisasi dan Azure Active Directory konfigurasi. |

#### <a name="api-properties-schema"></a>SIFAT API schema

[Peristiwa](apis.md) API mempunyai sifat berikut.

| Medan                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Sentiasa `ApiEvent`, menandakan peristiwa log sebagai peristiwa API.                                                                 |
| `properties.userAgent`       | Ejen pelayar menghantar permintaan atau `unknown`.                                                                        |
| `properties.method`          | Kaedah HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Laluan relatif permintaan.                                                                                          |
| `properties.origin`          | URI menunjukkan dari mana pengambilan datang atau `unknown`.                                                                  |
| `properties.operationStatus` | `Success` untuk kod Status HTTP < 400 <br> `ClientError` untuk kod Status HTTP < 500 <br> `Error` untuk > Status HTTP= 500 |
| `properties.tenantId`        | ID Organisasi                                                                                                        |
| `properties.tenantName`      | Nama organisasi.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjekId pemanggil.                                                                         |
| `properties.instanceId`      | Wawasan Pelanggan`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Skema peristiwa aliran kerja

Aliran kerja mengandungi berbilang langkah. [Ingest sumber](data-sources.md) data, [menyatukan](data-unification.md), [memperkayakan](enrichment-hub.md) dan [mengeksport](export-destinations.md) data. Semua langkah tersebut boleh dijalankan secara individu atau diatur dengan proses berikut. 

#### <a name="operation-types"></a>Jenis operasi

| JenisOperasi     | Kumpulkan                                     |
| ----------------- | ----------------------------------------- |
| Pengingesan         | [Sumber data](data-sources.md)           |
| DataPreparation   | [Sumber data](data-sources.md)           |
| Petakan               | [Penyatuan data](data-unification.md)   |
| Padankan             | [Penyatuan data](data-unification.md)   |
| Gabungkan             | [Penyatuan data](data-unification.md)   |
| Kedai Profil      | [Profil pelanggan](customer-profiles.md) |
| Carian            | [Profil pelanggan](customer-profiles.md) |
| Aktiviti          | [Aktiviti](activities.md)                  |
| AtributMeasures | [Segmen dan Langkah-langkah](segments.md)      |
| EntityMeasures    | [Segmen dan Langkah-langkah](segments.md)      |
| Langkah          | [Segmen dan Langkah-langkah](segments.md)      |
| Pembahagian      | [Segmen dan Langkah-langkah](segments.md)      |
| Pengayaan        | [Pengayaan](enrichment-hub.md)                                          |
| Risikan      | [Ramalan](predictions-overview.md)                                          |
| AiBuilder         | [Ramalan](predictions-overview.md)                                          |
| Wawasan          | [Ramalan](predictions-overview.md)                                          |
| Export            | [Eksport](export-destinations.md)                                          |
| Pengurusan Model   | [Ramalan](custom-models.md)                                           |
| Perhubungan      | [Penyatuan data](relationships.md)                                           |

#### <a name="field-description"></a>Penerangan medan

| Medan           | DataType  | Diperlukan/Pilihan | Description                                                                                                                                                   | Contoh                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Cap Masa | Wajib          | Cap masa acara (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Wajib          | ResourceId dari contoh yang memancarkan peristiwa.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Wajib          | Nama operasi yang diwakili oleh peristiwa ini. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Lihat [Jenis](#operation-types) Operasi untuk rujukan. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Wajib          | Kategori log acara. Sentiasa `Operational` untuk peristiwa Aliran Kerja                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Wajib          | Status acara. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Panjang      | Pilihan          | Tempoh operasi dalam milisaat.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Pilihan          | Objek JSON dengan lebih banyak sifat kepada kategori peristiwa tertentu.                                                                                        | Lihat sifat sub seksyen [Aliran Kerja](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Wajib          | Tahap keterukan acara.                                                                                                                                  | `Informational`, `Warning` atau `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Skema sifat aliran kerja

Peristiwa aliran kerja mempunyai sifat berikut.

| Medan              | Workflow | Tugas | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ya      | Ya  | Sentiasa `WorkflowEvent`, menandakan peristiwa sebagai peristiwa aliran kerja.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ya      | Ya  | Pengenalpasti aliran kerja berjalan. Semua aliran kerja dan peristiwa tugas dalam pelaksanaan aliran kerja mempunyai yang sama `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ya      | Ya  | Pengenalpasti operasi, lihat [Jenis](#operation-types) operasi.                                                                                                                                                                               |
| `properties.tasksCount`                      | Ya      | No   | Aliran kerja sahaja. Bilangan tugas yang dicetuskan oleh aliran kerja.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ya      | No   | Tidak wajib Peristiwa aliran kerja sahaja. ObjekId Azure Active Directory [pengguna](/azure/marketplace/find-tenant-object-id#find-user-object-id) yang mencetuskan aliran kerja, lihat juga `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ya      | No   | `full` atau `incremental` segar semula.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ya      | No   | `OnDemand` atau `Scheduled`                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ya      | No   | `Running` atau `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ya      | Ya  | Cap Masa UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ya      | Ya  | Cap Masa UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ya      | Ya  | Cap Masa UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ya      | Ya  | Wawasan Pelanggan`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Ya  | - Untuk OperationType = `Export`, pengecam adalah panduan konfigurasi eksport. <br> - Untuk OperasiJenis = `Enrichment`, itu adalah panduan pengayaan <br> - Untuk OperationType `Measures` dan `Segmentation`, pengecam adalah nama entiti. |
| `properties.friendlyName`                    | No       | Ya  | Nama mesra pengguna eksport atau entiti yang diproses.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ya  | Tidak wajib Mesej ralat dengan butiran lanjut.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ya  | Tidak wajib Untuk OperationType `Export` sahaja. Mengenal pasti jenis eksport. Untuk maklumat lanjut, lihat [gambaran keseluruhan destinasi](export-destinations.md) eksport.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ya  | Tidak wajib Untuk OperationType `Export` sahaja. Mengandungi senarai entiti yang dikonfigurasi dalam eksport.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ya  | Tidak wajib Untuk OperationType `Export` sahaja. Mesej terperinci untuk eksport.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ya  | Tidak wajib Untuk OperationType `Segmentation` sahaja. Menunjukkan jumlah bilangan ahli segmen.                                                                                                                                                    |
