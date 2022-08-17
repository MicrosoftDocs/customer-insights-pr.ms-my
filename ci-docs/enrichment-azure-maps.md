---
title: Memperkayakan profil pelanggan dengan data lokasi daripada Peta Azure (pratonton)
description: Maklumat umum tentang pengayaan pihak pertama Azure Maps.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238053"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Memperkayakan profil pelanggan dengan data lokasi daripada Peta Azure (pratonton)

Azure Maps menyediakan data dan perkhidmatan berpusatkan lokasi untuk menyampaikan pengalaman berdasarkan data geospatial dengan kecerdasan lokasi terbina dalam. Perkhidmatan pengayaan data Azure Maps meningkatkan ketepatan maklumat lokasi tentang pelanggan anda. Ini membawa keupayaan seperti penormalan alamat dan pengekstrakan latitud dan longitud pada Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prasyarat

- Langganan Peta Azure yang aktif. Untuk mendapatkan langganan, [daftar atau dapatkan percubaan percuma](https://azure.microsoft.com/services/azure-maps/).

- Sambungan [Peta](connections.md) [Azure dikonfigurasikan](#configure-the-connection-for-azure-maps) oleh pentadbir.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurasikan sambungan untuk Azure Maps

Anda mesti menjadi pentadbir [dalam](permissions.md#admin) Wawasan Pelanggan dan mempunyai kekunci API Peta Azure yang aktif.

1. Pilih **Tambah sambungan** apabila mengkonfigurasikan pengayaan, atau pergi ke **Pentadbir** > **Sambungan** dan pilih **Sediakan** pada jubin Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Halaman konfigurasi sambungan Azure Maps.":::

1. Masukkan nama untuk sambungan dan kekunci API Peta Azure yang sah.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi dan kemudian pilih **Simpan**.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya pada **jubin Lokasi** daripada Microsoft Azure Peta.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Jubin Azure Maps.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Seterusnya**.

1. Pilih sambungan. Hubungi pentadbir jika tiada sambungan tersedia.

1. Pilih **Seterusnya**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang anda ingin perkayakan dengan data daripada Microsoft. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda manakala segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

1. Tentukan jenis medan daripada profil bersatu anda untuk digunakan untuk pemadanan: alamat utama dan/atau sekunder. Anda boleh menentukan pemetaan medan untuk kedua-dua alamat dan memperkayakan profil untuk kedua-dua alamat secara berasingan. Contohnya, untuk alamat rumah dan alamat perniagaan. Pilih **Seterusnya**.

1. Petakan medan anda ke data lokasi daripada Peta Azure. Medan **Jalan 1** dan **Poskod** diperlukan untuk alamat utama dan/atau sekunder yang dipilih. Untuk ketepatan padanan yang lebih tinggi, tambah lebih banyak medan.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Pemetaan atribut Peta Azure.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. Semak **Tetapan** Lanjutan yang menawarkan fleksibiliti maksimum untuk mengendalikan kes penggunaan lanjutan. Walau bagaimanapun, nilai lalai berikut biasanya tidak perlu diubah.

   - **Jenis alamat**: Padanan alamat terbaik kembali walaupun ia tidak lengkap. Untuk mendapatkan alamat yang lengkap sahaja&mdash;contohnya, alamat yang merangkumi nombor rumah&mdash;kosongkan semua kotak semak kecuali **Alamat titik**.
   - **Bahasa**: Alamat kembali dalam bahasa berdasarkan rantau alamat. Untuk menggunakan bahasa alamat yang diseragamkan, pilih bahasa daripada menu juntai bawah. Sebagai contoh, memilih **bahasa Inggeris** mengembalikan **Copenhagen, Denmark** dan bukannya **København, Danmark**.
   - **Bilangan keputusan** maksimum: Bilangan keputusan bagi setiap alamat.

1. Pilih **Seterusnya**.

1. **Sediakan Nama** untuk pengayaan dan **nama** entiti Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Bilangan **pelanggan yang diperkaya oleh lapangan** menyediakan gerudi ke dalam liputan setiap bidang yang diperkaya.

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
