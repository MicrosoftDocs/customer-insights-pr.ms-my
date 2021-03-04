---
title: Pengayaan dengan pengayaan pihak ketiga HERE Technologies
description: Maklumat umum tentang pengayaan pihak ketiga HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269525"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Pengayaan profil pelanggan dengan HERE Technologies (pratonton)

HERE Technologies adalah syarikat platform lokasi yang menyediakan data dan perkhidmatan yang mengutamakan lokasi. Dengan perkhidmatan pengayaan data HERE Technologies, anda boleh membina pemahaman lokasi yang lebih tepat tentang pelanggan anda dengan normalisasi alamat, latitud serta pengekstrakan longitud dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi pengayaan HERE Technologies, prasyarat berikut mesti dipenuhi:

- Anda mempunyai langganan HERE Technologies yang aktif. Untuk mendapatkan langganan, anda boleh [daftar di sini](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) atau [hubungi HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) secara terus. [Ketahui lebih lanjut tentang Pengayaan Lokasi HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Anda mempunyai kunci API HERE Technologies.

- Anda mempunyai keizinan [Pentadbir](permissions.md#administrator).

## <a name="configuration"></a>Konfigurasi

1. Pergi ke **Data** > **Pengayaan**.

1. Pilih **Perkayakan data saya** pada jubin HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![Jubin HERE Technologies](media/HERE-tile.png "Jubin HERE Technologies")

1. Masukkan **Kunci API HERE Technologies** yang aktif. Semak semula dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**. 

1. Sahkan kedua-dua input dengan memilih **Sambung ke HERE**.

1.  Pilih **Tambah data** dan pilih **Set data pelanggan** yang anda ingin perkayakan dengan data lokasi daripada HERE Technologies. Anda boleh memilih entiti **Pelanggan** untuk memperkayakan semua profil pelanggan anda atau pilih entiti segmen untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Tangkapan skrin apabila memilih set data pelanggan.":::

1. Pilih jika anda mahu memetakan medan kepada alamat utama dan/atau kedua. Anda boleh menentukan pemetaan medan bagi kedua-dua alamat (contohnya, alamat rumah dan perniagaan) dan memperkayakan profil untuk kedua-dua alamat secara berasingan. Pilih **Seterusnya**.

1. Takrifkan medan daripada profil disatukan yang perlu anda gunakan untuk mencari pemadanan data lokasi yang sepadan daripada HERE Technologies. Medan **Jalan 1** dan **Poskod** diperlukan untuk alamat utama dan/atau sekunder yang dipilih. Untuk ketepatan padanan yang lebih tinggi, lebih banyak medan boleh ditambah.

   > [!div class="mx-imgBorder"]
   > ![Halaman konfigurasi pengayaan HERE Technologies](media/enrichment-HERE-configuration.png "Halaman konfigurasi pengayaan HERE Technologies")

1. Pilih **Gunakan** untuk melengkapkan pemetaan medan.

## <a name="enrichment-results"></a>Keputusan pengayaan

Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah. Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab). Masa pemprosesan akan bergantung pada saiz data pelanggan anda dan masa respons API daripada HERE Technologies.

Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**. Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.

Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.

## <a name="next-steps"></a>Langkah seterusnya

Bina di atas data pelanggan anda yang diperkaya. Cipta [segmen](segments.md), [ukur](measures.md) dan juga [eksport data](export-destinations.md) untuk menghantar pengalaman diperibadikan kepada pelanggan anda.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke HERE Technologies, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa HERE Technologies memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]