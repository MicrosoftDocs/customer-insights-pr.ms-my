---
title: Pengayaan dengan pengayaan pihak ketiga HERE Technologies
description: Maklumat umum tentang pengayaan pihak ketiga HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305305"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Pengayaan profil pelanggan dengan HERE Technologies (pratonton)

HERE Technologies adalah syarikat platform lokasi yang menyediakan data dan perkhidmatan yang mengutamakan lokasi. Dengan perkhidmatan pengayaan data HERE Technologies, anda boleh membina pemahaman lokasi yang lebih tepat tentang pelanggan anda dengan normalisasi alamat, latitud serta pengekstrakan longitud dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi pengayaan HERE Technologies, prasyarat berikut mesti dipenuhi:

- Anda mempunyai langganan HERE Technologies yang aktif. Untuk mendapatkan langganan, anda boleh [mendaftar di sini](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) atau [hubungi HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) secara terus. [Ketahui lebih lanjut tentang Pengayaan Lokasi HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- [Sambungan](connections.md) HERE tersedia *atau* anda mempunyai keizinan [pentadbir](permissions.md#administrator) dan kekunci API HERE Technologies.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan**. 

1. Pilih **Perkayakan data saya** pada jubin HERE Technologies dan pilih **Mari bermula**.

   > [!div class="mx-imgBorder"]
   > ![Jubin HERE Technologies](media/HERE-tile.png "Jubin HERE Technologies")

1. Pilih [sambungan](connections.md) daripada senarai juntai bawah. Hubungi pentadbir jika tiada sambungan tersedia. Jika anda seorang pentadbir, anda boleh mencipta sambungan dengan memilih **Tambah sambungan**. Pilih **HERE Technologies** daripada senarai juntai bawah. 

1. Pilih **Sambung ke HERE Technologies** untuk mengesahkan pilihan.

1.  Pilih **Seterusnya** dan pilih **Set data pelanggan** yang anda mahu perkayakan dengan data lokasi daripada HERE Technologies. Anda boleh memilih entiti **Pelanggan** untuk memperkayakan semua profil pelanggan anda atau pilih entiti segmen untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Tangkapan skrin apabila memilih set data pelanggan.":::

1. Pilih jika anda mahu memetakan medan kepada alamat utama dan/atau kedua. Anda boleh menentukan pemetaan medan untuk kedua-dua alamat dan memperkayakan profil untuk kedua-dua alamat secara berasingan. Contohnya, jika terdapat alamat rumah dan perniagaan. Pilih **Seterusnya**.

1. Takrifkan medan daripada profil disatukan yang perlu anda gunakan untuk mencari pemadanan data lokasi yang sepadan daripada HERE Technologies. Medan **Jalan 1** dan **Poskod** diperlukan untuk alamat utama dan/atau sekunder yang dipilih. Untuk ketepatan padanan yang lebih tinggi, lebih banyak medan boleh ditambah.

   > [!div class="mx-imgBorder"]
   > ![Halaman konfigurasi pengayaan HERE Technologies](media/enrichment-HERE-configuration.png "Halaman konfigurasi pengayaan HERE Technologies")

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. Berikan nama untuk pengayaan. 

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurasikan sambungan untuk HERE Technologies 

Anda perlu menjadi pentadbir untuk mengkonfigurasikan sambungan. Pilih **Tambah sambungan** apabila mengkonfigurasikan pengayaan *atau* pergi ke **Pentadbir** > **Sambungan** dan pilih **Sediakan** pada jubin HERE Technologies.

1. Masukkan nama untuk sambungan dalam kotak **Nama paparan**.

1. Sediakan kekunci API HERE Technologies yang sah.

1. Semak dan berikan persetujuan anda untuk **privasi dan pematuhan Data** dengan memilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi.

1. Selepas melengkapkan pengesahan, pilih **Simpan**.

   > [!div class="mx-imgBorder"]
   > ![Halaman konfigurasi sambungan HERE Technologies](media/enrichment-HERE-connection.png "Halaman konfigurasi sambungan HERE Technologies")

## <a name="enrichment-results"></a>Keputusan pengayaan

Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah. Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab). Masa pemprosesan akan bergantung pada saiz data pelanggan anda dan masa respons API daripada HERE Technologies.

Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**. Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.

Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.

## <a name="next-steps"></a>Langkah seterusnya

Bina di atas data pelanggan anda yang diperkaya. Cipta [segmen](segments.md) dan [langkah](measures.md) dan juga [eksport data](export-destinations.md) untuk menyampaikan pengalaman yang diperibadikan kepada pelanggan anda.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke HERE Technologies, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa HERE Technologies memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
