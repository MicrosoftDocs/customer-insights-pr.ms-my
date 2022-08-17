---
title: Memperkayakan profil pelanggan dengan TEKNOLOGI SINI (pratonton)
description: Maklumat umum tentang pengayaan pihak ketiga HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237869"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Memperkayakan profil pelanggan dengan TEKNOLOGI SINI (pratonton)

HERE Technologies adalah syarikat platform lokasi yang menyediakan data dan perkhidmatan yang mengutamakan lokasi. Perkhidmatan pengayaan data HERE Technologies meningkatkan ketepatan maklumat lokasi mengenai pelanggan anda. Ia menyediakan normalisasi alamat, pengekstrakan latitud dan longitud, dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

- Langganan TEKNOLOGI SINI yang aktif. Untuk mendapatkan langganan, [daftar di sini](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) atau [hubungi HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) secara langsung. [Ketahui lebih lanjut tentang Pengayaan Lokasi HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Sambungan [DI](connections.md) SINI [dikonfigurasikan](#configure-the-connection-for-here-technologies) oleh pentadbir.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurasikan sambungan untuk HERE Technologies

Anda mesti menjadi pentadbir [dalam](permissions.md#admin) Wawasan Pelanggan dan mempunyai kunci API TEKNOLOGI SINI yang aktif.

1. Pilih **Tambah sambungan** apabila mengkonfigurasi pengayaan, atau pergi ke **Sambungan** > **Pentadbir** dan pilih **Sediakan** pada jubin TEKNOLOGI SINI.

1. Masukkan nama untuk sambungan dan kekunci API TEKNOLOGI SINI yang sah.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi dan kemudian pilih **Simpan**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Halaman konfigurasi sambungan HERE Technologies.":::

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya pada **jubin Lokasi** daripada HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Jubin HERE Technologies.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Seterusnya**.

1. Pilih sambungan. Hubungi pentadbir jika tiada sambungan tersedia.

1. Pilih **Seterusnya**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang anda ingin perkayakan dengan data daripada TEKNOLOGI SINI. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda manakala segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

1. Tentukan jenis medan daripada profil bersatu anda untuk digunakan untuk pemadanan: alamat utama dan/atau sekunder. Anda boleh menentukan pemetaan medan untuk kedua-dua alamat dan memperkayakan profil untuk kedua-dua alamat secara berasingan. Contohnya, untuk alamat rumah dan alamat perniagaan. Pilih **Seterusnya**.

1. Petakan medan anda ke data dari TEKNOLOGI SINI. Medan **Jalan 1** dan **Poskod** diperlukan untuk alamat utama dan/atau sekunder yang dipilih. Untuk ketepatan padanan yang lebih tinggi, tambah lebih banyak medan.

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. **Sediakan Nama** untuk pengayaan dan **nama** entiti Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Bilangan **pelanggan yang diperkaya oleh lapangan** menyediakan gerudi ke dalam liputan setiap bidang yang diperkaya.

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
