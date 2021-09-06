---
title: Pengayaan profil syarikat dengan ruang pengayaan pihak ketiga Leadspace
description: Maklumat umum tentang pengayaan pihak ketiga Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 34b73b37670ed45e2c31ea164c0788b793bee433829ce21317c83903f3fca1fe
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031714"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Pengayaan profil syarikat dengan Leadspace (pratonton)

Leadspace ialah syarikat sains data yang menyediakan Platform Data Pelanggan B2B. Ia membolehkan pelanggan dengan profil pelanggan yang disatukan untuk syarikat mengayakan data mereka. Pengayaan termasuk lebih banyak atribut seperti saiz syarikat, lokasi, industri dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasikan Leadspace, prasyarat yang berikut mesti dipenuhi:

- Anda mempunyai lesen Leadspace yang aktif.
- Anda mempunyai [profil pelanggan yang disatukan](customer-profiles.md) untuk syarikat.
- Sambungan Leadspace telah dikonfigurasikan oleh pentadbir atau anda mempunyai keizinan [pentadbir](permissions.md#administrator) dan "kunci kekal" (dirujuk sebagai **token Leadspace**). Hubungi [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) secara langsung untuk maklumat mengenai produk mereka.

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

Bina di atas data pelanggan anda yang diperkaya. Cipta [segmen](segments.md) dan [langkah](measures.md) dan juga [eksport data](export-destinations.md) untuk menyampaikan pengalaman yang diperibadikan kepada pelanggan anda.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Leadspace, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Leadspace memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
