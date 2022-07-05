---
title: Memperkayakan profil syarikat dengan data syarikat yang dipertingkatkan
description: Memperkayakan dan menormalkan data syarikat dengan model Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054259"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Memperkayakan profil syarikat dengan data syarikat yang dipertingkatkan

Gunakan model Microsoft dan data syarikat yang disusun untuk membetulkan, menambah dan menyeragamkan profil syarikat anda. Kami akan menggunakan [format](/common-data-model/schema/core/applicationcommon/account) Model Data Biasa untuk ketepatan dan cerapan yang lebih baik.

Anda juga [boleh meningkatkan data syarikat pada sumber](data-sources-enrichment.md) data untuk meningkatkan ketepatan padanan dalam proses penyatuan data.

Bagi syarikat awam di Amerika Syarikat, maklumat seperti pendapatan, ticker saham, industri, dan banyak lagi tersedia.  

## <a name="how-we-enhance-company-data"></a>Bagaimana kami meningkatkan data syarikat

Model kami melalui proses dua langkah untuk meningkatkan profil syarikat. Pertama, ia menormalkan nama syarikat. Sebagai contoh, *Microsoft Corp* akan diperbetulkan dan diseragamkan kepada *Microsoft Corporation*. Ia cuba mencari padanan dalam data syarikat yang disusun Microsoft. Sekiranya terdapat padanan, kami memperkayakan profil syarikat dengan maklumat dari data syarikat kami yang disusun, termasuk nama syarikat.

### <a name="example"></a>Contoh

Maklumat syarikat anda mungkin tidak mengikut format standard dan mengandungi ralat ejaan. Model ini cuba membetulkan isu-isu ini dan membuat maklumat yang konsisten.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Batasan

Model tidak:

- Sahkan identiti syarikat. Kami tidak mengesahkan sama ada input itu adalah organisasi sedia ada atau syarikat menggunakan output sebagai nama standardnya.
- Secara komprehensif merangkumi syarikat di seluruh dunia. Data syarikat yang disusun Microsoft mempunyai liputan global, tetapi menawarkan kebanyakan liputan di Australia, Kanada, United Kingdom dan Amerika Syarikat.
- Standardkan alamat syarikat di seluruh dunia. Kami kini menyokong penyeragaman alamat di negara atau wilayah ini: Australia, Kanada, Perancis, Jerman, Itali, Jepun, United Kingdom, dan Amerika Syarikat.
- Ketepatan jaminan atau kesegaran data. Oleh kerana maklumat perniagaan sering berubah, kami tidak dapat menjamin bahawa data syarikat yang dipertingkatkan yang diberikan sentiasa tepat atau terkini.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya pada **jubin data** syarikat dipertingkatkan.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Jubin pengayaan di hab pengayaan untuk data syarikat.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Berikut**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang ingin anda memperkayakan. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda sedangkan segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

1. Pilih jenis medan daripada profil syarikat anda untuk digunakan untuk dipadankan dengan data syarikat yang dikompil Microsoft. Pemilihan ini akan mempengaruhi medan pemetaan yang anda boleh akses dalam langkah seterusnya.

1. Pilih **Seterusnya**.

1. Petakan medan syarikat anda ke data syarikat daripada Microsoft. Untuk ketepatan padanan yang lebih tinggi, tambah lebih banyak medan.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Langkah pemetaan data apabila mengkonfigurasi pengayaan syarikat.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. **Berikan Nama** untuk pengayaan dan **entiti** Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Kad Gambaran Keseluruhan

Jubin **gambaran keseluruhan** Pelanggan menunjukkan butiran tentang liputan pengayaan

- **Syarikat diproses dan berubah**: Bilangan profil syarikat pelanggan yang berjaya diperkaya.
- **Syarikat diproses dan tidak berubah**: Bilangan profil syarikat pelanggan yang diiktiraf tetapi tidak berubah. Ini biasanya berlaku apabila data input sah dan tidak boleh diperbaiki oleh pengayaan.
- **Syarikat tidak diproses dan tidak berubah**: Bilangan profil syarikat pelanggan yang tidak diiktiraf. Ini biasanya berlaku untuk data input yang tidak sah atau tidak disokong oleh pengayaan.

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
