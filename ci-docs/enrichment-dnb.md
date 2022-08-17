---
title: Enrich profil syarikat dengan Dun & Bradstreet (pratonton)
description: Maklumat umum mengenai pengayaan pihak ketiga Dun & Bradstreet.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237915"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Enrich profil syarikat dengan Dun & Bradstreet (pratonton)

Dun & Bradstreet menyediakan data komersial, analisis, dan pandangan untuk perniagaan. Ia membolehkan pelanggan dengan profil pelanggan yang disatukan untuk syarikat mengayakan data mereka. Pengayaan termasuk atribut seperti nombor DUNS, saiz syarikat, lokasi, industri dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

- Lesen Dun & Bradstreet [yang aktif](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Profil pelanggan bersepadu](customer-profiles.md) untuk syarikat.
- Projek Dun & Bradstreet [ditubuhkan](#set-up-your-dun--bradstreet-project).
- Sambungan Dun & Bradstreet [...](connections.md)[dikonfigurasikan](#configure-a-connection-for-dun--bradstreet) oleh pentadbir.

## <a name="set-up-your-dun--bradstreet-project"></a>Sediakan projek Dun & Bradstreet anda

Sebagai pengguna berlesen Dun & Bradstreet, anda boleh menubuhkan projek di [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Log masuk ke [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Untuk mendapatkan kelayakan, pulihkan [kata laluan](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights) anda.

1. Muat turun [fail](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) templat csv kami yang akan digunakan untuk memetakan medan Wawasan Pelanggan ke medan Dun & Bradstreet yang sepadan.

1. Muat naik fail dalam **langkah Muat naik data** pengalaman penciptaan projek Dun & Bradstreet.

1. Pilih titik mendatar di bawah sumber **yang berkaitan** dalam projek Dun & Bradstreet yang baru dibuat untuk melihat pilihan yang tersedia.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Tangkapan skrin titik dalam projek Dun & Bradstreet.":::

1. Pilih **Dapatkan butiran** S3. Simpan maklumat ini di tempat yang selamat. Anda memerlukannya untuk [menyediakan sambungan untuk pengayaan](#configure-a-connection-for-dun--bradstreet) dalam Wawasan Pelanggan.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Petikan skrin pemilihan maklumat s3 dalam projek Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurasikan sambungan untuk Dun & Bradstreet

Anda mesti menjadi pentadbir [dalam](permissions.md#admin) Wawasan Pelanggan dan mempunyai kelayakan dari Dun & Bradstreet Connect.

1. Pilih **Tambah sambungan** apabila mengkonfigurasi pengayaan atau pergi ke **Sambungan** > **Pentadbir** dan pilih **Sediakan** pada jubin Dun & Bradstreet.

1. Masukkan nama untuk sambungan.

1. Sediakan kelayakan Dun & Bradstreet yang sah dan butiran *projek Dun & Bradstreet Wilayah, laluan folder Drop, dan nama* folder Drop. Anda [mendapat maklumat](#set-up-your-dun--bradstreet-project) ini dari projek Dun & Bradstreet.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi dan kemudian pilih **Simpan**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Halaman konfigurasi sambungan Dun & Bradstreet.":::

## <a name="supported-countries-or-regions"></a>Negara atau rantau yang disokong

Kami kini menyokong pilihan negara/rantau berikut: Kanada (Bahasa Inggeris) atau Amerika Syarikat (Bahasa Inggeris).

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya pada **data** Syarikat untuk jubin Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Petikan skrin jubin Dun & Bradstreet.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Seterusnya**.

1. Pilih sambungan dan sahkan. Hubungi pentadbir jika tiada sambungan tersedia.

1. Pilih **Seterusnya**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang ingin anda pengayaan dengan data syarikat dari Dun & Bradstreet. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda manakala segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

1. Tentukan jenis medan daripada profil bersatu anda untuk digunakan untuk memadankan data syarikat daripada Dun & Bradstreet. Sekurang-kurangnya salah satu medan **Nama dan alamat**, **Telefon** atau **E-mel** diperlukan.

1. Pilih **Seterusnya**

1. Petakan medan anda ke data syarikat dari Dun & Bradstreet. Sama ada **nombor DUNS atau** Nama syarikat **dan** bidang Negara **diperlukan**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Anak tetingkap pemetaan medan Dun & Bradstreet.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. **Sediakan Nama** untuk pengayaan dan **nama** entiti Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
