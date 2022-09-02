---
title: Eksport log diagnostik (pratonton)
description: Ketahui cara menghantar log ke Microsoft Azure Monitor.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: c573c46fda895d36d29712e75fe28b261c9b399a
ms.sourcegitcommit: 0b5bfe0145dbd325fa518df4561d6a0a9a352264
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/25/2022
ms.locfileid: "9352812"
---
# <a name="export-diagnostic-logs-preview"></a>Eksport log diagnostik (pratonton)

Majukan log daripada Wawasan Pelanggan menggunakan Azure Monitor. Azure Monitor resource logs membolehkan anda memantau dan menghantar log ke [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) atau menstrimnya ke [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

Wawasan Pelanggan menghantar log acara berikut:

- **Peristiwa Audit**
  - **APIEvent** - membolehkan penjejakan perubahan melalui Dynamics 365 Customer Insights UI.
- **Acara Operasi**
  - **WorkflowEvent** - membolehkan anda menyediakan [sumber](data-sources.md) data, [menyatukan](data-unification.md), [memperkayakan](enrichment-hub.md) dan [mengeksport](export-destinations.md) data ke dalam sistem lain. Langkah-langkah ini boleh dilakukan secara individu (contohnya, mencetuskan eksport tunggal). Mereka juga boleh menjalankan orkestra (contohnya, penyegaran data dari sumber data yang mencetuskan proses penyatuan, yang akan menarik pengayaan dan mengeksport data ke dalam sistem lain). Untuk maklumat lanjut, lihat [Skema](#workflow-event-schema) Aliran KerjaEvent.
  - **APIEvent** - menghantar semua panggilan API contoh pelanggan kepada Dynamics 365 Customer Insights. Untuk maklumat lanjut, lihat [Skema](#api-event-schema) APIEvent.

## <a name="set-up-the-diagnostic-settings"></a>Menyediakan seting diagnostik

### <a name="prerequisites"></a>Prasyarat

- Langganan [Azure yang aktif](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Keizinan](permissions.md#admin) pentadbir dalam Wawasan Pelanggan.
- Sumber yang sah pada Azure yang mengikuti [keperluan](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) destinasi untuk Azure Storage, Azure Event Hub atau Azure Log Analytics.
- [Peranan Penyumbang dan Pentadbir](/azure/role-based-access-control/role-assignments-portal) Capaian Pengguna pada sumber destinasi pada Azure. Sumber boleh menjadi Azure Data Lake Storage akaun, Azure Event Hub atau ruang kerja Azure Log Analytics. Keizinan ini diperlukan semasa mengkonfigurasi tetapan diagnostik dalam Wawasan Pelanggan, tetapi ia boleh diubah selepas persediaan yang berjaya.
- Sekurang-kurangnya **peranan Pembaca** pada kumpulan sumber sumber itu dimiliki.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Menyediakan diagnostik dengan Azure Monitor

1. Dalam Wawasan Pelanggan, pergi ke **Sistem** > **Pentadbir** dan pilih tab **Diagnostik**.

1. Pilih **Tambah destinasi**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Sambungan diagnostik.":::

1. Berikan nama dalam **medan Nama untuk destinasi** diagnostik.

1. **Pilih jenis** Sumber (Akaun Storan, Hab Acara atau Analisis Log).

1. **Pilih kumpulan** Langganan **,** Sumber dan **Sumber** untuk sumber destinasi. Lihat [Konfigurasi pada sumber](#configuration-on-the-destination-resource) destinasi untuk kebenaran dan maklumat log.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung ke sistem** untuk menyambung ke sumber destinasi. Log mula muncul di destinasi selepas 15 minit, jika API sedang digunakan dan menjana peristiwa.

## <a name="configuration-on-the-destination-resource"></a>Konfigurasi pada sumber destinasi

Berdasarkan pilihan jenis sumber anda, perubahan berikut berlaku secara automatik:

### <a name="storage-account"></a>Akaun storan

Prinsipal perkhidmatan Wawasan Pelanggan mendapat **kebenaran Penyumbang** Akaun Storan pada sumber yang dipilih dan mencipta dua bekas di bawah ruang nama yang dipilih:

- `insight-logs-audit` mengandungi **peristiwa audit**
- `insight-logs-operational`**mengandungi peristiwa operasi**

### <a name="event-hub"></a>Hab Peristiwa

Prinsipal perkhidmatan Wawasan Pelanggan mendapat **keizinan Pemilik** Data Azure Event Hubs pada sumber dan mencipta dua Hab Acara di bawah ruang nama yang dipilih:

- `insight-logs-audit` mengandungi **peristiwa audit**
- `insight-logs-operational`**mengandungi peristiwa operasi**

### <a name="log-analytics"></a>Analisis Log

Prinsipal perkhidmatan Wawasan Pelanggan mendapat **kebenaran Penyumbang** Analisis Log pada sumber tersebut. Log tersedia di bawah **Pengurusan Log Jadual** > **Log pada ruang kerja Log Analitis** > **yang** dipilih. **Kembangkan penyelesaian Pengurusan** Log dan cari `CIEventsAudit` jadual dan `CIEventsOperational` jadual.

- `CIEventsAudit` mengandungi **peristiwa audit**
- `CIEventsOperational`**mengandungi peristiwa operasi**

**Di bawah tetingkap Pertanyaan**, kembangkan **penyelesaian Audit** dan cari contoh pertanyaan yang disediakan dengan mencari `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Mengalih keluar destinasi diagnostik

1. Pergi ke **Sistem** > **Pentadbir** dan pilih tab **Diagnostik**.

1. Pilih destinasi diagnostik dalam senarai.

   > [!TIP]
   > Mengalih keluar destinasi menghentikan pemajuan log tetapi tidak memadamkan sumber pada langganan Azure. Untuk memadamkan sumber dalam Azure, pilih pautan dalam **lajur Tindakan** untuk membuka portal Azure untuk sumber yang dipilih dan padamkannya di sana. Kemudian padamkan destinasi diagnostik.

1. **Dalam lajur Tindakan**, pilih ikon **Padam**.

1. Sahkan pemadaman untuk mengalih keluar destinasi dan hentikan pemajuan log.

## <a name="log-categories-and-event-schemas"></a>Kategori log dan skema acara

[Pada masa ini peristiwa](apis.md) API dan peristiwa aliran kerja disokong dan kategori dan skema berikut digunakan.
Skema log mengikuti [skema](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema) biasa Azure Monitor.

### <a name="categories"></a>Kategori

Wawasan Pelanggan menyediakan dua kategori:

- **Peristiwa audit**: [Peristiwa](#api-event-schema) API untuk mengesan perubahan konfigurasi pada perkhidmatan. `POST|PUT|DELETE|PATCH` operasi masuk ke dalam kategori ini.
- **Acara operasi**: [Peristiwa](#api-event-schema) API atau [peristiwa](#workflow-event-schema) aliran kerja yang dijana semasa menggunakan perkhidmatan.  Contohnya, `GET` permintaan atau peristiwa pelaksanaan aliran kerja.

## <a name="event-schemas"></a>Skema acara

Peristiwa API dan peristiwa aliran kerja mempunyai struktur umum, tetapi dengan beberapa perbezaan. Untuk maklumat lanjut, lihat [skema](#api-event-schema) peristiwa API atau [skema](#workflow-event-schema) peristiwa aliran kerja.

### <a name="api-event-schema"></a>Skema acara API

| Medan             | Jenis Data  | Diperlukan/Pilihan | Description       | Contoh        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Cap Masa | Wajib          | Cap waktu acara (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Wajib          | ResourceId contoh yang memancarkan peristiwa itu         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Wajib          | Nama operasi yang diwakili oleh acara ini.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Wajib          | Kategori log acara. Sama ada `Operational` atau `Audit`. Semua POST / PUT / PATCH / DELETE Permintaan HTTP ditandakan dengan `Audit`, segala-galanya dengan `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Wajib          | Status acara. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Pilihan          | Status keputusan acara. Jika operasi sepadan dengan panggilan REST API, ia adalah kod status HTTP.        | `200`             |
| `durationMs`      | Panjang      | Pilihan          | Tempoh operasi dalam milisaat.     | `133`     |
| `callerIpAddress` | String    | Pilihan          | Alamat IP pemanggil, jika operasi sepadan dengan panggilan API yang datang daripada alamat IP yang tersedia secara umum.                                                 | `144.318.99.233`         |
| `identity`        | String    | Pilihan          | Objek JSON menerangkan identiti pengguna atau aplikasi yang melakukan operasi.       | Lihat [Bahagian Identiti](#identity-schema)  .     |  
| `properties`      | String    | Pilihan          | Objek JSON dengan lebih banyak sifat kepada kategori peristiwa tertentu.      | Lihat [Bahagian](#api-properties-schema) sifat.    |
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
| `Authorization.UserRole`      | Peranan yang diperuntukkan untuk pengguna atau aplikasi. Untuk maklumat lanjut, lihat [keizinan](permissions.md) pengguna.                                     |
| `Authorization.RequiredRoles` | Peranan yang diperlukan untuk melakukan operasi. `Admin` peranan dibenarkan untuk melakukan semua operasi.                                                    |
| `Claims`                      | Tuntutan pengguna atau aplikasi token web JSON (JWT). Hartanah tuntutan berbeza-beza bagi setiap organisasi dan Azure Active Directory konfigurasi. |

#### <a name="api-properties-schema"></a>Skema sifat API

[Acara](apis.md) API mempunyai sifat berikut.

| Medan                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Sentiasa `ApiEvent`, menandakan acara log sebagai acara API.                                                                 |
| `properties.userAgent`       | Ejen pelayar menghantar permintaan atau `unknown`.                                                                        |
| `properties.method`          | Kaedah HTTP: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Laluan relatif permintaan.                                                                                          |
| `properties.origin`          | URI menunjukkan di mana fetch berasal atau `unknown`.                                                                  |
| `properties.operationStatus` | `Success` untuk kod Status HTTP < 400 <br> `ClientError` untuk kod Status HTTP < 500 <br> `Error` untuk Status HTTP >= 500 |
| `properties.tenantId`        | ID Organisasi                                                                                                        |
| `properties.tenantName`      | Nama organisasi.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId daripada pemanggil.                                                                         |
| `properties.instanceId`      | Wawasan Pelanggan `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Skema peristiwa aliran kerja

Aliran kerja mengandungi berbilang langkah. [Menelan sumber](data-sources.md) data, [menyatukan](data-unification.md), [memperkaya](enrichment-hub.md) dan [mengeksport](export-destinations.md) data. Semua langkah tersebut boleh dijalankan secara individu atau dirancang dengan proses berikut.

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
| AtributMeasures | [Segmen dan Langkah](segments.md)      |
| EntitiMeasures    | [Segmen dan Langkah](segments.md)      |
| Langkah          | [Segmen dan Langkah](segments.md)      |
| Pembahagian      | [Segmen dan Langkah](segments.md)      |
| Pengayaan        | [Pengayaan](enrichment-hub.md)                                          |
| Risikan      | [Ramalan](predictions-overview.md)                                          |
| AiBuilder         | [Ramalan](predictions-overview.md)                                          |
| Wawasan          | [Ramalan](predictions-overview.md)                                          |
| Export            | [Eksport](export-destinations.md)                                          |
| Pengurusan Model   | [Ramalan](custom-models.md)                                           |
| Perhubungan      | [Penyatuan data](relationships.md)                                           |

#### <a name="field-description"></a>Perihalan medan

| Medan           | Jenis Data  | Diperlukan/Pilihan | Description                                                                                                                                                   | Contoh                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Cap Masa | Wajib          | Cap waktu acara (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Wajib          | ResourceId contoh yang memancarkan acara itu.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Wajib          | Nama operasi yang diwakili oleh acara ini. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Lihat [Jenis](#operation-types) Operasi untuk rujukan. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Wajib          | Kategori log acara. Sentiasa `Operational` untuk peristiwa Aliran Kerja                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Wajib          | Status acara. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Panjang      | Pilihan          | Tempoh operasi dalam milisaat.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Pilihan          | Objek JSON dengan lebih banyak sifat kepada kategori peristiwa tertentu.                                                                                        | Lihat sub seksyen [Sifat Aliran Kerja](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Wajib          | Tahap keterukan peristiwa.                                                                                                                                  | `Informational`, `Warning` atau `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Skema sifat aliran kerja

Peristiwa aliran kerja mempunyai sifat berikut.

| Medan              | Workflow | Tugas | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ya      | Ya  | Sentiasa `WorkflowEvent`, menandakan peristiwa sebagai peristiwa aliran kerja.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ya      | Ya  | Pengecam aliran kerja dijalankan. Semua aliran kerja dan peristiwa tugas dalam pelaksanaan aliran kerja mempunyai perkara yang sama `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ya      | Ya  | Pengecam pengendalian, lihat [Jenis operasi](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Ya      | No   | Aliran kerja sahaja. Bilangan tugas yang dicetuskan oleh aliran kerja.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ya      | No   | Tidak wajib Peristiwa aliran kerja sahaja. ObjectId Azure Active Directory [pengguna yang](/azure/marketplace/find-tenant-object-id#find-user-object-id) mencetuskan aliran kerja, lihat juga `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ya      | No   | `full` atau `incremental` segar semula.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ya      | No   | `OnDemand` atau `Scheduled`                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ya      | No   | `Running` atau `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ya      | Ya  | Cap Waktu UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ya      | Ya  | Cap Waktu UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ya      | Ya  | Cap Waktu UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ya      | Ya  | Wawasan Pelanggan`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Ya  | - Untuk OperationType = `Export`, pengecam ialah panduan konfigurasi eksport. <br> - Untuk OperationType = `Enrichment`, ia adalah panduan pengayaan <br> - Untuk OperationType `Measures` dan `Segmentation`, pengecam ialah nama entiti. |
| `properties.friendlyName`                    | No       | Ya  | Nama mesra pengguna eksport atau entiti yang diproses.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ya  | Tidak wajib Mesej ralat dengan butiran lanjut.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ya  | Tidak wajib Untuk Jenis `Export` Operasi sahaja. Mengenal pasti jenis eksport. Untuk maklumat lanjut, lihat [gambaran keseluruhan destinasi](export-destinations.md) eksport.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ya  | Tidak wajib Untuk Jenis `Export` Operasi sahaja. Mengandungi senarai entiti yang dikonfigurasi dalam eksport.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ya  | Tidak wajib Untuk Jenis `Export` Operasi sahaja. Mesej terperinci untuk eksport.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ya  | Tidak wajib Untuk Jenis `Segmentation` Operasi sahaja. Menunjukkan jumlah ahli segmen tersebut.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
