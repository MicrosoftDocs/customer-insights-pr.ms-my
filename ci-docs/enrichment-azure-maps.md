---
title: Perkayakan profil pelanggan dengan data lokasi dari Azure Maps
description: Maklumat umum tentang pengayaan pihak pertama Azure Maps.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953639"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Pengayaan profil pelanggan dengan Azure Maps (pratonton)

Azure Maps menyediakan data dan perkhidmatan yang berpusatkan lokasi untuk menyampaikan pengalaman berdasarkan data geospatial dengan kecerdasan lokasi terbina dalam. Perkhidmatan pengayaan data Azure Maps meningkatkan ketepatan maklumat lokasi tentang pelanggan anda. Ini membawa keupayaan seperti penormalan alamat dan pengekstrakan latitud dan longitud pada Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prasyarat

- Langganan Azure Maps yang aktif. Untuk mendapatkan langganan, [daftar atau dapatkan percubaan percuma](https://azure.microsoft.com/services/azure-maps/).

- Sambungan [Azure](connections.md) Maps dikonfigurasikan [oleh](#configure-the-connection-for-azure-maps) pentadbir.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurasikan sambungan untuk Azure Maps

Anda mesti menjadi [pentadbir](permissions.md#admin) dalam Wawasan Pelanggan dan mempunyai kekunci API Azure Maps yang aktif.

1. Pilih **Tambah sambungan** apabila mengkonfigurasikan pengayaan, atau pergi ke **Pentadbir** > **Sambungan** dan pilih **Sediakan** pada jubin Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Halaman konfigurasi sambungan Azure Maps.":::

1. Masukkan nama untuk sambungan dan kekunci API Azure Maps yang sah.

1. Semak dan berikan persetujuan anda untuk [privasi dan pematuhan Data](#data-privacy-and-compliance) dengan memilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi dan kemudian pilih **Simpan**.

### <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data pada Azure Maps, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif yang berpotensi seperti Data Peribadi. Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa Peta Azure memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk mendapatkan maklumat lanjut, pergi ke [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya pada **jubin Lokasi** daripada Microsoft Azure Peta.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Jubin Azure Maps.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Berikut**.

1. Pilih sambungan. Hubungi pentadbir jika tiada sambungan tersedia.

1. Pilih **Seterusnya**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang anda ingin memperkayakan dengan data daripada Microsoft. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda sedangkan segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

1. Tentukan jenis medan daripada profil bersatu anda untuk digunakan untuk pemadanan: alamat utama dan/atau sekunder. Anda boleh menentukan pemetaan medan untuk kedua-dua alamat dan memperkayakan profil untuk kedua-dua alamat secara berasingan. Sebagai contoh, untuk alamat rumah dan alamat perniagaan. Pilih **Seterusnya**.

1. Petakan medan anda ke data lokasi daripada Peta Azure. Medan **Jalan 1** dan **Poskod** diperlukan untuk alamat utama dan/atau sekunder yang dipilih. Untuk ketepatan padanan yang lebih tinggi, tambah lebih banyak medan.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Maps attribute mapping.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. Semak **Tetapan** Lanjutan yang menawarkan fleksibiliti maksimum untuk mengendalikan kes penggunaan lanjutan. Walau bagaimanapun, nilai lalai berikut biasanya tidak perlu diubah.

   - **Jenis alamat**: Padanan alamat terbaik kembali walaupun ia tidak lengkap. Untuk mendapatkan alamat yang lengkap sahaja&mdash;contohnya, alamat yang merangkumi nombor rumah&mdash;kosongkan semua kotak semak kecuali **Alamat titik**.
   - **Bahasa**: Alamat kembali dalam bahasa berdasarkan rantau alamat. Untuk menggunakan bahasa alamat yang diseragamkan, pilih bahasa daripada menu juntai bawah. Sebagai contoh, memilih **bahasa Inggeris** mengembalikan **Copenhagen, Denmark** dan bukannya **København, Danmark**.
   - **Bilangan maksimum keputusan**: Bilangan keputusan bagi setiap alamat.

1. Pilih **Seterusnya**.

1. **Berikan Nama** untuk pengayaan dan **nama** entiti Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

## <a name="enrichment-results"></a>Keputusan pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Bilangan pelanggan yang diperkaya oleh lapangan** menyediakan gerudi ke dalam liputan setiap medan yang diperkaya.

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
