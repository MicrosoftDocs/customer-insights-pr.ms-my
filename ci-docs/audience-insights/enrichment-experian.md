---
title: Pengayaan dengan Experian pengayaan pihak ketiga
description: Maklumat umum tentang pengayaan pihak ketiga Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896384"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Perkayakan profil pelanggan dengan demografik daripada Experian (pratonton)

Experian adalah peneraju global dalam pelaporan kredit pengguna dan perniagaan serta perkhidmatan pemasaran. Dengan perkhidmatan pengayaan data Experian, anda boleh membina pemahaman lebih mendalam mengenai pelanggan anda dengan memperkayakan profil pelanggan anda dengan data demografi seperti saiz isi rumah, pendapatan dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasikan Experian, prasyarat berikut mesti dipenuhi:

- Anda mempunyai langganan Experian yang aktif. Untuk mendapatkan langganan, [hubungi Experian](https://www.experian.com/marketing-services/contact) secara terus. [Ketahui lanjut tentang Pengayaan Data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Sambungan Experian telah dikonfigurasikan oleh pentadbir *atau* anda mempunyai keizinan [pentadbir](permissions.md#administrator). Anda juga memerlukan ID pengguna, ID Parti dan Nombor Model untuk akaun Pengangkutan Selamat (ST) yang Didayakan oleh SSH yang dicipta oleh Experian untuk anda.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Perkayakan data saya** pada jubin Experian.

   > [!div class="mx-imgBorder"]
   > ![Jubin Experian](media/experian-tile.png "Jubin Experian")
   > 

1. Pilih [sambungan](connections.md) daripada menu juntai bawah. Hubungi pentadbir jika tiada sambungan tersedia. Jika anda seorang pentadbir, anda boleh mencipta sambungan dengan memilih **Tambah sambungan** dan memilih Experian daripada menu juntai bawah. 

1. Pilih **Sambung ke Experian** untuk mengesahkan pilihan penyambungan.

1.  Pilih **Seterusnya** dan pilih **Set data pelanggan** yang anda mahu perkayakan dengan data demografi daripada Experian. Anda boleh memilih entiti **Pelanggan** untuk memperkayakan semua profil pelanggan anda atau pilih entiti segmen untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Tangkapan skrin apabila memilih set data pelanggan.":::

1. Pilih **Seterusnya** dan tentukan jenis medan daripada profil anda yang disatukan yang perlu digunakan untuk mencari data demografi yang sepadan daripada Experian. Sekurang-kurangnya salah satu medan **Nama dan alamat**, **Telefon** atau **E-mel** diperlukan. Untuk mendapatkan ketepatan padanan yang lebih tinggi, maksimum dua medan lain boleh ditambah. Pemilihan ini akan mempengaruhi medan pemetaan yang anda boleh akses dalam langkah seterusnya.

    > [!TIP]
    > Lebih atribut pengecam kunci yang dihantar kepada Experian mungkin akan menghasilkan kadar padanan yang lebih tinggi.

1. Pilih **Seterusnya** untuk memulakan pemetaan medan.

1. Tentukan jenis medan daripada profil anda yang disatukan yang perlu digunakan untuk mencari data demografi yang sepadan daripada Experian. Medan yang diperlukan ditandakan.

1. Berikan nama untuk pengayaan dan nama untuk entiti output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

## <a name="configure-the-connection-for-experian"></a>Konfigurasikan sambungan untuk Experian 

Anda perlu menjadi pentadbir untuk mengkonfigurasikan sambungan. Pilih **Tambah sambungan** apabila mengkonfigurasikan pengayaan *atau* pergi ke **Pentadbir** > **Sambungan** dan pilih **Sediakan** pada jubin Experian.

1. Pilih **Mulakan**.

1. Masukkan nama untuk sambungan dalam kotak **Nama paparan**.

1. Masukkan ID Pengguna, ID Parti dan Nombor Model yang sah untuk akaun Pengangkutan Selamat Experian anda.

1. Semak dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi.

1. Selepas melengkapkan pengesahan, pilih **Simpan**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Anak tetingkap konfigurasi sambungan Experian.":::

## <a name="enrichment-results"></a>Keputusan pengayaan

Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah. Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab). Masa pemprosesan akan bergantung pada saiz data pelanggan anda dan proses pengayaan yang ditetapkan untuk akaun anda oleh Experian.

Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**. Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.

Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.

## <a name="next-steps"></a>Langkah seterusnya

Bina di atas data pelanggan anda yang diperkaya. Cipta [segmen](segments.md), [ukur](measures.md) dan juga [eksport data](export-destinations.md) untuk menghantar pengalaman diperibadikan kepada pelanggan anda.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Experian, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Experian memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
