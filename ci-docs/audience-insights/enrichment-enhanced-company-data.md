---
title: Peningkatan data syarikat
description: Memperkaya dan menormalkan data syarikat dengan model Microsoft.
ms.date: 11/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: d11700c87f31cedc40d32b201251d8a9e2e2c312
ms.sourcegitcommit: dfc4843cc78857f1e3ca49d7b938e3ba77969169
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/15/2021
ms.locfileid: "7813929"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Pengayaan profil syarikat dengan data syarikat yang dipertingkatkan

Gunakan model Microsoft dan data syarikat yang disusun untuk membetulkan, menambah dan menyeragamkan profil syarikat anda. Kami akan menggunakan [format Model Data Biasa untuk ketepatan dan pandangan yang lebih](/common-data-model/schema/core/applicationcommon/account) baik.

## <a name="how-we-enhance-company-data"></a>Cara kami meningkatkan data syarikat

Model kami melalui proses dua langkah untuk meningkatkan profil syarikat. Pertama, ia menormalkan nama syarikat. Sebagai contoh, *Microsoft Corp* akan diperbetulkan dan diseragamkan kepada *Microsoft Corporation*. Ia cuba mencari padanan dalam data syarikat terkompil Microsoft. Jika padanan ditemui, kami memperkayakan profil syarikat dengan maklumat daripada data syarikat kami yang disusun, termasuk nama syarikat.


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

Terdapat beberapa batasan dengan data yang dipertingkatkan. Item dalam senarai di bawah tidak disokong oleh model.

1.  Sahkan identiti syarikat. Kami tidak mengesahkan sama ada input adalah organisasi sedia ada atau syarikat menggunakan output sebagai nama standardnya.
2.  Meliputi syarikat secara komprehensif di seluruh dunia. Data syarikat yang disusun Microsoft mempunyai liputan global, tetapi menawarkan kebanyakan liputan di Australia, Kanada, United Kingdom, dan Amerika Syarikat.
3.  Menyeragamkan alamat syarikat di seluruh dunia. Kami kini menyokong penyeragaman alamat di negara atau rantau ini: Australia, Kanada, Perancis, Jerman, Itali, Jepun, United Kingdom dan Amerika Syarikat.
4.  Menjamin ketepatan atau kesegaran data. Oleh kerana maklumat perniagaan sering berubah, kami tidak dapat menjamin bahawa data syarikat yang dipertingkatkan yang disediakan sentiasa tepat atau terkini.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan**.

1. Pilih **Memperkayakan data saya** pada jubin data syarikat **dipertingkatkan**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Jubin pengayaan dalam hab pengayaan untuk data syarikat.":::

1. Pilih **Set data pelanggan** dan pilih entiti yang mengandungi alamat yang anda mahu perkayakan. Anda boleh memilih entiti *Pelanggan* untuk memperkayakan alamat dalam semua profil pelanggan anda atau memilih entiti segmen untuk memperkayakan alamat hanya dalam profil pelanggan yang terkandung dalam segmen itu.

1. Pilih jenis medan daripada profil syarikat anda yang patut digunakan untuk dipadankan dengan data syarikat terkompil Microsoft. Pemilihan ini akan mempengaruhi medan pemetaan yang anda boleh akses dalam langkah seterusnya.

1.  Petakan medan syarikat daripada entiti pelanggan bersatu anda. Semakin banyak pengecam dan medan utama yang anda petakan, lebih banyak kemungkinan kadar padanan yang lebih tinggi.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Langkah pemetaan data apabila mengkonfigurasi pengayaan syarikat.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. Berikan nama untuk pengayaan dan entiti output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

## <a name="enrichment-results"></a>Keputusan pengayaan

Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah. Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab). Masa pemprosesan bergantung pada saiz data pelanggan anda.

Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**. Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.

Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.

## <a name="next-steps"></a>Langkah seterusnya

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
