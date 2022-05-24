---
title: Pengayaan profil syarikat dengan Dun & Bradstreet
description: Maklumat umum mengenai pengayaan pihak ketiga Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755411"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Pengayaan profil syarikat dengan Dun & Bradstreet (Preview)

Dun & Bradstreet menyediakan data komersial, analisis, dan pandangan untuk perniagaan. Ia membolehkan pelanggan dengan profil pelanggan yang disatukan untuk syarikat mengayakan data mereka. Pengayaan termasuk atribut seperti nombor DUNS, saiz syarikat, lokasi, industri dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi pengayaan Dun & Bradstreet, prasyarat berikut mesti dipenuhi:

- Anda mempunyai lesen Dun & Bradstreet [yang aktif](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- Anda mempunyai [profil pelanggan yang disatukan](customer-profiles.md) untuk syarikat.
- Sambungan Dun & Bradstreet [dikonfigurasikan](connections.md) oleh pentadbir. Anda boleh menciptanya jika anda mempunyai [keizinan pentadbir](permissions.md#admin) dan kelayakan daripada Dun & Bradstreet Connect.

## <a name="setting-up-your-dun--bradstreet-project"></a>Menyediakan projek Dun & Bradstreet anda

Sebagai pengguna berlesen Dun & Bradstreet, anda boleh menyediakan projek di [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).


1. Log masuk ke [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Untuk mendapatkan kelayakan, pulihkan [kata laluan](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights) anda.

1. Muat turun [fail](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) templat csv kami yang akan digunakan untuk memetakan medan Wawasan Pelanggan ke medan Dun & Bradstreet yang sepadan.

1. Muat naik fail dalam **langkah Muat naik data** pengalaman penciptaan projek Dun & Bradstreet.

1. Pilih titik mendatar di bawah sumber **yang berkaitan** dalam projek Dun & Bradstreet yang baru dibuat untuk melihat pilihan yang ada.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Tangkapan skrin titik dalam projek Dun & Bradstreet.":::

1. Pilih **Dapatkan butiran** S3. Simpan maklumat ini di tempat yang selamat. Anda memerlukannya untuk [menyediakan sambungan untuk pengayaan](#configure-a-connection-for-dun--bradstreet) dalam Wawasan Pelanggan.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Petikan skrin pemilihan maklumat s3 dalam projek Dun & Bradstreet.":::

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan**.

1. Pilih **Memperkayakan data** saya pada jubin Dun & Bradstreet dan pilih **Mulakan**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Tangkapan skrin jubin Dun & Bradstreet.":::

1. Pilih [sambungan](connections.md) daripada senarai juntai bawah. Hubungi pentadbir jika tiada sambungan tersedia. Jika anda seorang pentadbir, anda boleh mencipta sambungan. Pilih **Tambah sambungan** dan pilih **Dun & Bradstreet**.

1. Pilih **Sambung ke Dun & Bradstreet** untuk mengesahkan sambungan.

1. Pilih **Seterusnya** dan pilih set **data Pelanggan yang** ingin anda memperkayakan dengan data syarikat dari Dun & Bradstreet. Anda boleh memilih **entiti Pelanggan** untuk memperkayakan semua profil pelanggan anda atau memilih entiti segmen untuk memperkayakan hanya profil pelanggan bersatu yang terkandung dalam segmen tersebut.

1. Pilih **Seterusnya** dan tentukan medan daripada profil bersatu anda digunakan untuk mencari data syarikat yang sepadan daripada Dun & Bradstreet. Sama ada **nombor DUNS atau** Nama syarikat **dan** negara **diperlukan**. Medan negara menyokong [dua atau tiga kod](https://www.iso.org/iso-3166-country-codes.html) negara huruf, nama negara dalam bahasa Inggeris, nama negara dalam bahasa ibunda, dan awalan telefon. Beberapa varian negara biasa termasuk:

- AS: Amerika Syarikat, Amerika Syarikat, Amerika Syarikat, Amerika Syarikat.
- CA: Kanada.
- GB: United Kingdom, UK, Great Britain, GB, United Kingdom Great Britain dan Ireland Utara, United Kingdom Great Britain.
- AU: Australia, Komanwel Australia.
- FR: Perancis, Republik Perancis.
- Jerman, Jerman, Deutschland, Allemagne, Republik Federal Jerman, Republik Jerman, Republik Jerman.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Anak tetingkap pemetaan medan Dun & Bradstreet.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. Berikan nama untuk pengayaan dan pilih **Simpan pengayaan** selepas menyemak pilihan anda.

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurasikan sambungan untuk Dun & Bradstreet

Anda perlu menjadi pentadbir untuk mengkonfigurasikan sambungan. Pilih **Tambah sambungan** apabila mengkonfigurasi pengayaan *atau* pergi ke **Sambungan** > **Pentadbir** dan pilih **Sediakan** pada jubin Dun & Bradstreet.

1. Pilih **Mulakan**.

1. Masukkan nama untuk sambungan dalam kotak **Nama paparan**.

1. Berikan kelayakan Dun & Bradstreet yang sah dan butiran *projek Dun & Bradstreet Wilayah, Jatuhkan laluan folder, dan Jatuhkan nama* folder. Anda [mendapat maklumat](#setting-up-your-dun--bradstreet-project) ini dari projek Dun & Bradstreet.

1. Semak dan berikan persetujuan anda untuk **privasi dan pematuhan Data** dengan memilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi.

1. Selepas melengkapkan pengesahan, pilih **Simpan**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Halaman konfigurasi sambungan Dun & Bradstreet.":::

## <a name="enrichment-results"></a>Keputusan pengayaan

Selepas penyegaran semula pengayaan, anda boleh mengulas data syarikat yang baru diperkayakan di bawah [Pengayaan saya](enrichment-hub.md). Anda boleh menemui masa kemas kini terakhir dan bilangan profil yang diperkayakan.

Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.

## <a name="next-steps"></a>Langkah seterusnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Dun & Bradstreet, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa Dun & Bradstreet memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.

[!INCLUDE[footer-include](includes/footer-banner.md)]
