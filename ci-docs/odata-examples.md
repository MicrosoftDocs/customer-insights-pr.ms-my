---
title: Contoh OData untuk Dynamics 365 Customer Insights API
description: Contoh yang biasa digunakan untuk Protokol Data Terbuka (OData) untuk bertanya API Wawasan Pelanggan untuk menyemak data.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cdadd72bfe4272d8d83d923baaa6fd40d008473b
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808472"
---
# <a name="odata-query-examples"></a>Contoh pertanyaan OData

Protokol Data Terbuka (OData) ialah protokol akses data yang dibina pada protokol teras seperti HTTP. Ia menggunakan metodologi yang biasa diterima seperti REST untuk web. Terdapat pelbagai jenis perpustakaan dan alat yang boleh digunakan untuk menggunakan perkhidmatan OData.

Artikel ini menyenaraikan beberapa pertanyaan contoh yang sering diminta untuk membantu anda membina pelaksanaan anda sendiri berdasarkan [API Wawasan Pelanggan](apis.md).

Anda perlu mengubah suai sampel pertanyaan untuk menjadikannya berfungsi pada persekitaran sasaran: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` di manakah {instanceId} GUID persekitaran Wawasan Pelanggan yang ingin anda tanya. Operasi [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) membolehkan anda mencari {InstanceId} akses kepada anda.
- {CID}: GUID rekod pelanggan yang bersatu. Contoh: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Pengenalpasti kunci utama rekod pelanggan dalam sumber data. Contoh: `CNTID_1002`
- {DSname}: String dengan nama entiti sumber data yang akan ditelan ke Wawasan Pelanggan. Contoh: `Website_contacts`.
- {SegmentName}: Rentetan dengan nama entiti output segmen dalam Wawasan Pelanggan. Contoh: `Male_under_40`.

## <a name="customer"></a>Dihormati

Jadual berikut mengandungi satu set pertanyaan sampel untuk *entiti Pelanggan*.

|Jenis pertanyaan |Contoh  | Nota  |
|---------|---------|---------|
|ID pelanggan tunggal     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Kekunci alternatif    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Kekunci alternatif berterusan dalam entiti pelanggan bersatu       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Masuk    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Kekunci alternatif + Dalam   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Carian  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Mengembalikan 10 hasil teratas untuk rentetan carian      |
|Keahlian segmen  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Mengembalikan nombor pratetap baris daripada entiti pembahagian.      |

## <a name="unified-activity"></a>Aktiviti bersatu

Jadual berikut mengandungi satu set pertanyaan sampel untuk *entiti UnifiedActivity*.

|Jenis pertanyaan |Contoh  | Nota  |
|---------|---------|---------|
|Aktiviti CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Menyenaraikan aktiviti profil pelanggan tertentu |
|Tempoh masa aktiviti    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktiviti profil pelanggan dalam jangka masa       |
|Jenis aktiviti    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktiviti mengikut nama paparan     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Pengisihan aktiviti    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Mengisih aktiviti menaik atau menurun       |
|Aktiviti diperluaskan daripada keahlian segmen  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Contoh lain

Jadual berikut mengandungi satu set pertanyaan sampel untuk entiti lain.

|Jenis pertanyaan |Contoh  | Nota  |
|---------|---------|---------|
|Langkah-langkah CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Jenama CID yang diperkaya    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Kepentingan CID yang diperkaya    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Kembangkan     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Pertanyaan OData tidak disokong

Pertanyaan berikut tidak disokong oleh Wawasan Pelanggan:

- `$filter` pada entiti sumber yang ditelan. Anda hanya boleh menjalankan pertanyaan $filter pada entiti sistem yang dicipta oleh Wawasan Pelanggan.
- `$expand``$search` daripada pertanyaan. Contoh: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` daripada `$select` jika hanya subset atribut dipilih. Contoh: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` jenama yang diperkaya atau pertalian minat untuk pelanggan tertentu. Contoh: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Pertanyaan ramalan entiti output model melalui kekunci alternatif. Contoh: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
