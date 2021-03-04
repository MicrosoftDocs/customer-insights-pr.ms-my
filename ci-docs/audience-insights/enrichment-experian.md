---
title: Pengayaan dengan Experian pengayaan pihak ketiga
description: Maklumat umum tentang pengayaan pihak ketiga Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269571"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Perkayakan profil pelanggan dengan demografik daripada Experian (pratonton)

Experian adalah peneraju global dalam pelaporan kredit pengguna dan perniagaan serta perkhidmatan pemasaran. Dengan perkhidmatan pengayaan data Experian, anda boleh membina pemahaman lebih mendalam mengenai pelanggan anda dengan memperkayakan profil pelanggan anda dengan data demografi seperti saiz isi rumah, pendapatan dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasikan Experian, prasyarat berikut mesti dipenuhi:

- Anda mempunyai langganan Experian yang aktif. Untuk mendapatkan langganan, [hubungi Experian](https://www.experian.com/marketing-services/contact) secara terus. [Ketahui lanjut tentang Pengayaan Data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Anda mempunyai ID pengguna, ID Pihak dan Nombor Model untuk akaun Pengangkutan Selamat (ST) didayakan SSH yang telah dicipta oleh Experian untuk anda.
- Anda mempunyai keizinan [Pentadbir](permissions.md#administrator) dalam wawasan khalayak.

## <a name="configuration"></a>Konfigurasi

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Perkayakan data saya** pada jubin Experian.

   > [!div class="mx-imgBorder"]
   > ![Jubin Experian](media/experian-tile.png "Jubin Experian")

1. Pilih **Mari bermula** dan masukkan ID Pengguna, ID Pihak dan Nombor Model untuk akaun Pengangkutan Selamat Experian anda. Semak semula dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**. Sahkan semua input dengan memilih **Gunakan**.

## <a name="map-your-fields"></a>Petakan medan anda

1.  Pilih **Tambah data** dan pilih **Set data pelanggan** yang anda ingin perkayakan dengan data demografi daripada Experian. Anda boleh memilih entiti **Pelanggan** untuk memperkayakan semua profil pelanggan anda atau pilih entiti segmen untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut.

1. Pilih pengecam utama anda daripada **Nama dan Alamat**, **E-mel** atau **Telefon** untuk dihantar ke Experian bagi resolusi identiti.

   > [!TIP]
   > Lebih atribut pengecam kunci yang dihantar kepada Experian mungkin akan menghasilkan kadar padanan yang lebih tinggi.

1. Pilih **Seterusnya** dan petakan atribut yang sepadan daripada entiti pelanggan disatukan anda untuk medan pengecam kunci yang dipilih.

1. Pilih **Tambah atribut** untuk memetakan sebarang atribut tambahan yang anda mahu hantar ke Experian.

1.  Pilih **Simpan** untuk melengkapkan pemetaan medan.

    > [!div class="mx-imgBorder"]
    > ![Memetakan medan Experian](media/experian-field-mapping.png "Memetakan medan Experian")

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