---
title: Pengayaan dengan pengayaan pihak ketiga Experian
description: Maklumat umum tentang pengayaan pihak ketiga Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fabc3cc9faf4e11f46c396782b561ef61cd0f6d5
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618532"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Memperkaya profil pelanggan dengan demografi daripada Experian (pratonton)

Experian ialah peneraju global dalam pelaporan kredit pengguna dan perniagaan serta perkhidmatan pemasaran. Dengan perkhidmatan pengayaan data Experian, anda boleh membina pemahaman yang lebih mendalam tentang pelanggan anda dengan memperkaya profil pelanggan anda menggunakan data demografi seperti saiz isi rumah, pendapatan dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasikan Experian, prasyarat berikut mesti dipenuhi:

- Anda mesti mempunyai langganan Experian yang aktif. Untuk mendapatkan langganan, [hubungi Experian](https://www.experian.com/marketing-services/contact) secara terus. [Ketahui lebih lanjut tentang Pengayaan Data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Sambungan Experian telah dikonfigurasikan oleh pentadbir *atau* anda mempunyai keizinan [pentadbir](permissions.md#administrator). Anda juga memerlukan ID Pengguna, ID Pihak dan Nombor Model untuk akaun Pengangkutan Selamat (ST) didayakan SSH anda yang Experian cipta untuk anda.

## <a name="supported-countriesregions"></a>Negara/rantau yang disokong

Pada masa ini, kami menyokong pengayaan profil pelanggan di Amerika Syarikat sahaja.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Perkayakan data saya** pada jubin Experian.

   > [!div class="mx-imgBorder"]
   > ![Jubin Experian.](media/experian-tile.png "Experian tile")
   > 

1. Pilih [sambungan](connections.md) daripada senarai juntai bawah. Hubungi pentadbir jika tiada sambungan tersedia. Jika anda seorang pentadbir, anda boleh mencipta sambungan dengan memilih **Tambah sambungan** dan memilih Experian daripada senarai juntai bawah. 

1. Pilih **Sambung kepada Experian** untuk mengesahkan pilihan sambungan.

1.  Pilih **Seterusnya** dan pilih **Set data pelanggan** yang anda mahu perkayakan dengan data demografi daripada Experian. Anda boleh memilih entiti **Pelanggan** untuk memperkayakan semua profil pelanggan anda atau pilih entiti segmen untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Tangkapan skrin apabila memilih set data pelanggan.":::

1. Pilih **Seterusnya** dan tentukan jenis medan daripada profil anda yang disatukan harus digunakan untuk mencari data demografi yang sepadan daripada Experian. Sekurang-kurangnya salah satu medan **Nama dan alamat**, **Telefon** atau **E-mel** diperlukan. Untuk mendapatkan ketepatan padanan yang lebih tinggi, maksimum dua medan lain boleh ditambah. Pemilihan ini akan mempengaruhi medan pemetaan yang anda boleh akses dalam langkah seterusnya.

    > [!TIP]
    > Lebih banyak atribut pengecam utama dihantar kepada Experian mungkin menghasilkan kadar padanan yang lebih tinggi.

1. Pilih **Seterusnya** untuk memulakan pemetaan medan.

1. Tentukan jenis medan daripada profil anda yang disatukan yang harus digunakan untuk mencari data demografi yang sepadan daripada Experian. Medan yang diperlukan ditandakan.

1. Berikan nama untuk pengayaan dan nama untuk entiti output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

## <a name="configure-the-connection-for-experian"></a>Konfigurasikan sambungan untuk Experian 

Anda perlu menjadi pentadbir untuk mengkonfigurasikan sambungan. Pilih **Tambah sambungan** apabila mengkonfigurasikan pengayaan *atau* pergi ke **Pentadbir** > **Sambungan** dan pilih **Sediakan** pada jubin Experian.

1. Pilih **Mulakan**.

1. Masukkan nama untuk sambungan dalam kotak **Nama paparan**.

1. Masukkan ID Pengguna, ID Pihak, dan Nombor Model yang sah untuk akaun Pengangkutan Selamat Experian anda.

1. Semak dan berikan persetujuan anda untuk **privasi dan pematuhan Data** dengan memilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi.

1. Selepas melengkapkan pengesahan, pilih **Simpan**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Anak tetingkap konfigurasi sambungan Experian.":::

## <a name="enrichment-results"></a>Keputusan pengayaan

Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah. Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab). Masa pemprosesan akan bergantung pada saiz data pelanggan anda dan proses pengayaan yang disediakan untuk akaun anda oleh Experian.

Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**. Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.

Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.

## <a name="next-steps"></a>Langkah seterusnya

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data kepada Experian, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif yang berpotensi seperti Data Peribadi. Microsoft akan memindahkan data tersebut atas arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa Experian memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
