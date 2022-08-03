---
title: Memperkayakan profil syarikat dengan Dun & Bradstreet (pratonton)
description: Maklumat umum mengenai pengayaan pihak ketiga Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 71b35e4295e19c13edadc6548ac79715555e8183
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196037"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Memperkayakan profil syarikat dengan Dun & Bradstreet (pratonton)

Dun & Bradstreet menyediakan data komersial, analisis, dan pandangan untuk perniagaan. Ia membolehkan pelanggan dengan profil pelanggan yang disatukan untuk syarikat mengayakan data mereka. Pengayaan termasuk atribut seperti nombor DUNS, saiz syarikat, lokasi, industri dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

- Lesen Dun & Bradstreet [yang aktif](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Profil pelanggan bersatu](customer-profiles.md) untuk syarikat.
- Projek Dun & Bradstreet [disediakan](#set-up-your-dun--bradstreet-project).
- Sambungan Dun & Bradstreet [...](connections.md)[dikonfigurasikan](#configure-a-connection-for-dun--bradstreet) oleh pentadbir.

## <a name="set-up-your-dun--bradstreet-project"></a>Sediakan projek Dun & Bradstreet anda

Sebagai pengguna berlesen Dun & Bradstreet, anda boleh menyediakan projek di [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Log masuk ke [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Untuk mendapatkan kelayakan, pulihkan [kata laluan](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights) anda.

1. Muat turun [fail](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) templat csv kami yang akan digunakan untuk memetakan medan Wawasan Pelanggan ke medan Dun & Bradstreet yang sepadan.

1. Muat naik fail dalam **langkah Muat naik data** pengalaman penciptaan projek Dun & Bradstreet.

1. Pilih titik mendatar di bawah sumber **yang berkaitan** dalam projek Dun & Bradstreet yang baru dibuat untuk melihat pilihan yang ada.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Tangkapan skrin titik dalam projek Dun & Bradstreet.":::

1. Pilih **Dapatkan butiran** S3. Simpan maklumat ini di tempat yang selamat. Anda memerlukannya untuk [menyediakan sambungan untuk pengayaan](#configure-a-connection-for-dun--bradstreet) dalam Wawasan Pelanggan.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Petikan skrin pemilihan maklumat s3 dalam projek Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurasikan sambungan untuk Dun & Bradstreet

Anda mesti menjadi [pentadbir](permissions.md#admin) dalam Wawasan Pelanggan dan mempunyai kelayakan dari Dun & Bradstreet Connect.

1. Pilih **Tambah sambungan** apabila mengkonfigurasi pengayaan atau pergi ke **Sambungan** > **Pentadbir** dan pilih **Sediakan** pada jubin Dun & Bradstreet.

1. Masukkan nama untuk sambungan.

1. Berikan kelayakan Dun & Bradstreet yang sah dan butiran *projek Dun & Bradstreet Wilayah, Jatuhkan laluan folder, dan Jatuhkan nama* folder. Anda [mendapat maklumat](#set-up-your-dun--bradstreet-project) ini dari projek Dun & Bradstreet.

1. Semak dan berikan persetujuan anda untuk [privasi dan pematuhan Data](#data-privacy-and-compliance) dengan memilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi dan kemudian pilih **Simpan**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Halaman konfigurasi sambungan Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Dun & Bradstreet, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa Dun & Bradstreet memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.

## <a name="supported-countries-or-regions"></a>Negara atau rantau yang disokong

Kami kini menyokong pilihan negara/rantau berikut: Kanada (Bahasa Inggeris) atau Amerika Syarikat (Bahasa Inggeris).

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya pada **data** Syarikat untuk jubin Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Tangkapan skrin jubin Dun & Bradstreet.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Berikut**.

1. Pilih sambungan dan sahkan. Hubungi pentadbir jika tiada sambungan tersedia.

1. Pilih **Seterusnya**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang ingin anda memperkayakan dengan data syarikat dari Dun & Bradstreet. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda sedangkan segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

1. Tentukan jenis medan daripada profil bersatu anda untuk digunakan untuk memadankan data syarikat daripada Dun & Bradstreet. Sekurang-kurangnya salah satu medan **Nama dan alamat**, **Telefon** atau **E-mel** diperlukan.

1. Pilih **Seterusnya**

1. Petakan medan anda ke data syarikat dari Dun & Bradstreet. Sama ada **nombor DUNS atau** Nama syarikat **dan** negara **diperlukan**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Anak tetingkap pemetaan medan Dun & Bradstreet.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. **Berikan Nama** untuk pengayaan dan **nama** entiti Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
