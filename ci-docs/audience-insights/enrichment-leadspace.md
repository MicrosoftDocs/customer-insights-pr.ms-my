---
title: Pengayaan profil syarikat dengan ruang pengayaan pihak ketiga Leadspace
description: Maklumat umum tentang pengayaan pihak ketiga Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 0db0c984f6bf9f7ded0704b6fa0caf39c7dace3a
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376795"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Pengayaan profil syarikat dengan Leadspace (pratonton)

Leadspace adalah sebuah syarikat sains data yang menyediakan Platform Data Pelanggan niaga-ke-niaga. Ia mendayakan persekitaran dengan profil pelanggan disatukan berdasarkan akaun untuk memperkayakan data mereka. Memperkayakan *Profil pelanggan* dengan atribut seperti saiz syarikat, lokasi atau industri. Memperkayakan *Profil kenalan* dengan atribut ciri seperti tajuk, persona atau pengesahan e-mel.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasikan Leadspace, prasyarat yang berikut mesti dipenuhi:

- Anda mempunyai lesen Leadspace yang aktif.
- Anda mempunyai [profil pelanggan disatukan](customer-profiles.md) berdasarkan pada akaun.
- Sambungan Leadspace telah dikonfigurasikan oleh pentadbir atau anda mempunyai keizinan [pentadbir](permissions.md#admin) dan "kunci kekal" (dirujuk sebagai **token Leadspace**). Hubungi [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) secara langsung untuk maklumat mengenai produk mereka.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan**.

1. Pilih **Perkayakan data saya** pada jubin Leadspace dan pilih **Mari bermula**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Petikan skrin jubin Leadspace.":::

1. Pilih [sambungan](connections.md) daripada senarai juntai bawah. Hubungi pentadbir jika tiada sambungan tersedia. Jika anda seorang pentadbir, anda boleh mencipta sambungan dengan memilih **Tambah sambungan** dan memilih **Leadspace**. 

1. Pilih **Sambung ke Leadspace** untuk mengesahkan sambungan.

1. Pilih **Seterusnya** dan pilih **Set data pelanggan** yang anda mahu perkayakan dengan data syarikat daripada Leadspace. Anda boleh memilih entiti **Pelanggan** untuk memperkayakan semua profil pelanggan anda atau pilih entiti segmen untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Tangkapan skrin apabila memilih set data pelanggan.":::

1. Pilih **Seterusnya** dan tentukan jenis medan daripada profil anda yang disatukan yang digunakan untuk mencari data demografi yang sepadan daripada Leadspace. Medan **Nama syarikat** diperlukan. Untuk ketepatan padanan yang lebih tinggi hingga dua medan yang lain, **Tapak web syarikat** dan **Lokasi syarikat** boleh ditambah.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Anak tetingkap pemetaan medan Leadspace.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. Pilih kotak semak jika anda mempunyai *Profil kenalan* yang anda mahu perkayakan. Cerapan khalayak akan secara automatik memetakan medan yang diperlukan.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Pengayaan rekod kenalan Leadspace.":::
 
1. Berikan nama untuk pengayaan dan pilih **Simpan pengayaan** selepas menyemak pilihan anda.


## <a name="configure-the-connection-for-leadspace"></a>Konfigurasikan sambungan untuk Leadspace 

Anda perlu menjadi pentadbir untuk mengkonfigurasikan sambungan. Pilih **Tambah sambungan** apabila mengkonfigurasikan pengayaan *atau* pergi ke **Pentadbir** > **Sambungan** dan pilih **Sediakan** pada jubin Leadspace.

1. Pilih **Mulakan**. 

1. Masukkan nama untuk sambungan dalam kotak **Nama paparan**.

1. Berikan token Leadspace yang sah.

1. Semak dan berikan persetujuan anda untuk **privasi dan pematuhan Data** dengan memilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi.

1. Selepas melengkapkan pengesahan, pilih **Simpan**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Halaman konfigurasi sambungan Leadspace.":::

## <a name="enrichment-results"></a>Keputusan pengayaan

Selepas penyegaran semula pengayaan, anda boleh mengulas data syarikat yang baru diperkayakan di bawah [Pengayaan saya](enrichment-hub.md). Anda boleh menemui masa kemas kini terakhir dan bilangan profil yang diperkayakan.

Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.

Untuk maklumat lanjut, lihat [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Langkah seterusnya


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Leadspace, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Leadspace memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
