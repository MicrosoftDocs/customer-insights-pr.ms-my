---
title: Peningkatan data syarikat
description: Memperkayakan dan menormalkan data syarikat dengan model Microsoft.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e9cf93f28ba6918c72039670e42d26c8aaa7f922
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376364"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Pengayaan profil syarikat dengan data syarikat yang dipertingkatkan

Gunakan model Microsoft dan data syarikat yang disusun untuk membetulkan, menambah dan menyeragamkan profil syarikat anda. Kami akan menggunakan [format](/common-data-model/schema/core/applicationcommon/account) Model Data Biasa untuk ketepatan dan cerapan yang lebih baik.

Anda juga [boleh meningkatkan data syarikat pada sumber](data-sources-enrichment.md) data untuk meningkatkan ketepatan padanan dalam proses penyatuan data. 

## <a name="how-we-enhance-company-data"></a>Bagaimana kami meningkatkan data syarikat

Model kami melalui proses dua langkah untuk meningkatkan profil syarikat. Pertama, ia menormalkan nama syarikat. Sebagai contoh, *Microsoft Corp* akan diperbetulkan dan diseragamkan kepada *Microsoft Corporation*. Ia cuba mencari padanan dalam data syarikat yang disusun Microsoft. Sekiranya terdapat padanan, kami memperkayakan profil syarikat dengan maklumat dari data syarikat kami yang disusun, termasuk nama syarikat.


### <a name="example"></a>Contoh

Maklumat syarikat anda mungkin tidak mengikut format standard dan mengandungi ralat ejaan. Model ini cuba membetulkan isu-isu ini dan mencipta maklumat yang konsisten.

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

1.  Sahkan identiti syarikat. Kami tidak mengesahkan sama ada input itu adalah organisasi sedia ada atau syarikat menggunakan output sebagai nama standardnya.
2.  Secara komprehensif merangkumi syarikat di seluruh dunia. Data syarikat yang disusun Microsoft mempunyai liputan global, tetapi menawarkan kebanyakan liputan di Australia, Kanada, United Kingdom dan Amerika Syarikat.
3.  Standardkan alamat syarikat di seluruh dunia. Kami kini menyokong penyeragaman alamat di negara atau wilayah ini: Australia, Kanada, Perancis, Jerman, Itali, Jepun, United Kingdom, dan Amerika Syarikat.
4.  Ketepatan jaminan atau kesegaran data. Oleh kerana maklumat perniagaan sering berubah, kami tidak dapat menjamin bahawa data syarikat yang dipertingkatkan yang diberikan sentiasa tepat atau terkini.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan**.

1. Pilih **Memperkayakan data** saya pada **jubin data** syarikat dipertingkatkan.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Jubin pengayaan di hab pengayaan untuk data syarikat.":::

1. Pilih **Set data pelanggan** dan pilih entiti yang mengandungi alamat yang anda mahu perkayakan. Anda boleh memilih entiti *Pelanggan* untuk memperkayakan alamat dalam semua profil pelanggan anda atau memilih entiti segmen untuk memperkayakan alamat hanya dalam profil pelanggan yang terkandung dalam segmen itu.

1. Pilih jenis medan daripada profil syarikat anda yang patut digunakan untuk dipadankan dengan data syarikat yang disusun oleh Microsoft. Pemilihan ini akan mempengaruhi medan pemetaan yang anda boleh akses dalam langkah seterusnya.

1.  Petakan medan syarikat dari entiti pelanggan bersatu anda. Semakin banyak pengecam dan medan utama yang anda petakan, semakin banyak kemungkinan kadar padanan yang lebih tinggi.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Langkah pemetaan data apabila mengkonfigurasi pengayaan syarikat.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. Berikan nama untuk pengayaan dan entiti output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

## <a name="enrichment-results"></a>Keputusan pengayaan

Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah. Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab). Masa pemprosesan bergantung pada saiz data pelanggan anda.

Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**. Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.

Anda boleh melihat sampel data yang diperkaya dalam **jubin pratonton** pelanggan Enriched. Pilih **Lihat lebih** lanjut **dan pilih tab Data** untuk mencapai pandangan terperinci bagi setiap profil yang diperkaya.

### <a name="overview-card"></a>Kad Gambaran Keseluruhan

Kad gambaran keseluruhan menunjukkan butiran mengenai liputan pengayaan. 

* **Syarikat diproses dan berubah**: Bilangan profil syarikat pelanggan yang berjaya diperkaya.

* **Syarikat diproses dan tidak berubah**: Bilangan profil syarikat pelanggan yang diiktiraf tetapi tidak berubah. Ini biasanya berlaku apabila data input sah dan tidak boleh diperbaiki oleh pengayaan.

* **Syarikat tidak diproses dan tidak berubah**: Bilangan profil syarikat pelanggan yang tidak diiktiraf. Ini biasanya berlaku untuk data input yang tidak sah atau tidak disokong oleh pengayaan.

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
