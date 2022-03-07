---
title: Perkayakan profil pelanggan dengan data lokasi dari Azure Maps
description: Maklumat umum tentang pengayaan pihak pertama Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: cb1c0778a398ef6d338ce6cf9e199eae0c344a5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226460"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Pengayaan profil pelanggan dengan Azure Maps (pratonton)

Azure Maps memberikan data dan perkhidmatan khusus lokasi untuk menyampaikan pengalaman berdasarkan data georuang dengan kecerdasan lokasi terbina dalam. Perkhidmatan pengayaan data Azure Maps meningkatkan ketepatan maklumat lokasi tentang pelanggan anda. Ini membawa keupayaan seperti penormalan alamat dan pengekstrakan latitud dan longitud pada Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasikan pengayaan data Azure Maps, prasyarat berikut mesti dipenuhi:

- Anda mesti mempunyai langganan Azure Maps yang aktif. Untuk mendapatkan langganan, anda boleh [mendaftar atau mendapatkan percubaan percuma](https://azure.microsoft.com/services/azure-maps/).

- Azure Maps [sambungan](connections.md) tersedia, *atau* anda mempunyai keizinan [pentadbir](permissions.md#administrator) dan kekunci API Azure Maps yang aktif.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan**. 

1. Pada jubin **Lokasi**, pilih **Perkayakan data saya**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Jubin Azure Maps.":::

1. Pilih [sambungan](connections.md) daripada senarai juntai bawah. Hubungi pentadbir jika tiada sambungan Azure Maps yang tersedia. Jika anda pentadbir, anda boleh [mengkonfigurasikan sambungan untuk Azure Maps](#configure-the-connection-for-azure-maps). 

1. Pilih **Seterusnya** untuk mengesahkan pemilihan.

1. Pilih **Set data pelanggan** yang mahu anda perkayakan dengan data lokasi daripada Azure Maps. Anda boleh memilih entiti **Pelanggan** untuk memperkaya semua profil pelanggan anda yang disatukan, atau memilih entiti segmen untuk memperkaya profil pelanggan yang terkandung dalam segmen tersebut sahaja.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Tangkapan skrin apabila memilih set data pelanggan.":::

1. Pilih sama ada anda mahu memetakan medan pada alamat utama dan/atau sekunder. Anda boleh menentukan pemetaan medan untuk kedua-dua alamat dan memperkaya profil untuk kedua-dua alamat secara berasingan &mdash;contohnya, untuk alamat rumah dan alamat perniagaan. Pilih **Seterusnya**.

1. Tentukan jenis medan daripada profil anda yang disatukan untuk digunakan bagi data lokasi yang sepadan daripada Azure Maps. Medan **Jalan 1** dan **Kod Zip/Poskod** diperlukan untuk alamat utama atau sekunder yang dipilih. Untuk ketepatan padanan yang lebih tinggi, anda boleh menambahkan lebih banyak medan.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Halaman konfigurasi pengayaan Azure Maps.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. Menilai sama ada anda mahu mengubah suai **Tetapan Lanjutan**. Ini disediakan untuk memberikan fleksibiliti maksimum bagi mengendalikan kes penggunaan lanjutan, tetapi nilai lalai akan mencukupi dalam kebanyakan kes:
   - **Jenis alamat**: Tingkah laku lalai ialah pengayaan akan mengembalikan padanan alamat terbaik walaupun tidak lengkap. Untuk mendapatkan alamat yang lengkap sahaja&mdash;contohnya, alamat yang merangkumi nombor rumah&mdash;kosongkan semua kotak semak kecuali **Alamat titik**. 
   - **Bahasa**: Secara lalai, alamat dikembalikan dalam bahasa untuk wilayah yang telah ditentukan alamatnya. Untuk menggunakan bahasa alamat yang diseragamkan, pilih bahasa daripada menu juntai bawah. Contohnya, memilih **bahasa Inggeris** akan mengembalikan **Copenhagen, Denmark** dan bukannya **København, Danmark**.

1. Berikan nama untuk pengayaan.

1. Semak pilihan anda, kemudian pilih **Simpan pengayaan**.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurasikan sambungan untuk Azure Maps

Anda perlu menjadi pentadbir dalam cerapan khalayak untuk mengkonfigurasikan sambungan. Pilih **Tambah sambungan** apabila mengkonfigurasikan pengayaan, atau pergi ke **Pentadbir** > **Sambungan** dan pilih **Sediakan** pada jubin Azure Maps.

1. Dalam kotak **Nama paparan**, masukkan nama untuk sambungan.

1. Berikan kekunci API Azure Maps yang sah.

1. Semak dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi.

1. Selepas melengkapkan pengesahan, pilih **Simpan**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Halaman konfigurasi sambungan Azure Maps.":::

## <a name="enrichment-results"></a>Keputusan pengayaan

Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah. Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab). Masa pemprosesan akan bergantung pada saiz data pelanggan anda dan masa respons API.

Selepas proses pengayaan selesai, anda boleh pratonton data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**. Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.

Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.

## <a name="next-steps"></a>Langkah seterusnya

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data pada Azure Maps, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif yang berpotensi seperti Data Peribadi. Microsoft akan memindahkan data tersebut atas arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa Azure Maps memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk mendapatkan maklumat lanjut, pergi ke [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
