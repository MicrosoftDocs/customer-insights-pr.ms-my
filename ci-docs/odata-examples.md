---
title: Contoh pertanyaan OData untuk API Wawasan Pelanggan
description: Contoh yang biasa digunakan untuk Protokol Data Terbuka (OData) untuk menanyakan API Wawasan Pelanggan untuk menyemak data.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387213"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Contoh pertanyaan OData untuk API Wawasan Pelanggan

Protokol Data Terbuka (OData) ialah protokol capaian data yang dibina berdasarkan protokol teras seperti HTTP. Ia menggunakan kaedah yang biasa diterima seperti REST untuk web. Terdapat pelbagai jenis perpustakaan dan alat yang boleh digunakan untuk menggunakan perkhidmatan OData.

Untuk membantu anda membina pelaksanaan anda sendiri berdasarkan [API](apis.md) Wawasan Pelanggan, semak beberapa pertanyaan contoh yang sering diminta.

Ubah suai sampel pertanyaan untuk menjadikannya berfungsi pada persekitaran sasaran:

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` di mana {instanceId} GUID persekitaran Wawasan Pelanggan yang anda ingin tanya. Operasi [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) membolehkan anda mencari akses kepada {InstanceId} anda.
- {CID}: GUID rekod pelanggan bersatu. Contoh: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Pengecam kunci utama rekod pelanggan dalam sumber data. Contoh: `CNTID_1002`
- {DSname}: Rentetan dengan nama entiti sumber data yang akan ditelan dengan Wawasan Pelanggan. Contoh: `Website_contacts`.
- {SegmentName}: Rentetan dengan nama entiti output bagi segmen dalam Wawasan Pelanggan. Contoh: `Male_under_40`.

## <a name="customer"></a>Dihormati

Contoh pertanyaan untuk *entiti Pelanggan* .

|Jenis pertanyaan |Contoh  | Nota  |
|---------|---------|---------|
|ID pelanggan tunggal     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|kekunci alternatif    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Kekunci alternatif berterusan dalam entiti pelanggan bersatu       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Masuk    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|kekunci alternatif + Dalam   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Carian  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Mengembalikan 10 hasil teratas untuk rentetan carian      |
|Keahlian segmen  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Mengembalikan bilangan baris yang dipraset daripada entiti segmentasi.      |
|Keahlian segmen untuk pelanggan | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Mengembalikan profil pelanggan jika mereka adalah ahli segmen yang diberikan     |

## <a name="unified-activity"></a>Aktiviti bersepadu

Contoh pertanyaan untuk *entiti UnifiedActivity* .

|Jenis pertanyaan |Contoh  | Nota  |
|---------|---------|---------|
|Aktiviti CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Menyenaraikan aktiviti profil pelanggan tertentu |
|Tempoh masa aktiviti    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktiviti profil pelanggan dalam tempoh masa       |
|Jenis aktiviti    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktiviti mengikut nama paparan     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Pengisihan aktiviti    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Isih aktiviti menaik atau menurun       |
|Aktiviti diperluaskan daripada keahlian segmen  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Contoh lain

Contoh pertanyaan untuk entiti lain.

|Jenis pertanyaan |Contoh  | Nota  |
|---------|---------|---------|
|Langkah-langkah CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Jenama CID yang diperkaya    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Kepentingan cid yang diperkaya    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Dalam Klausa + Kembangkan     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Tidak disokong pertanyaan OData

Pertanyaan berikut tidak disokong oleh Wawasan Pelanggan:

- `$filter` pada entiti sumber yang ditelan. Anda hanya boleh menjalankan pertanyaan $filter mengenai entiti sistem yang dicipta oleh Wawasan Pelanggan.
- `$expand``$search` daripada pertanyaan. Contoh: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` daripada `$select` jika hanya subset atribut dipilih. Contoh: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` jenama yang diperkaya atau pertalian minat untuk pelanggan tertentu. Contoh: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Pertanyaan ramalan entiti output model melalui kekunci alternatif. Contoh: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
