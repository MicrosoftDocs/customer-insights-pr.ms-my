---
title: Pengayaan profil syarikat dengan ruang pengayaan pihak ketiga Leadspace
description: Maklumat umum tentang pengayaan pihak ketiga Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668734"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Pengayaan profil syarikat dengan Leadspace (pratonton)

Leadspace ialah syarikat sains data yang menyediakan Platform Data Pelanggan B2B. Ia membolehkan pelanggan dengan profil pelanggan yang disatukan untuk syarikat mengayakan data mereka. Pengayaan merangkumi atribut tambahan seperti saiz syarikat, lokasi, industri dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasikan Leadspace, prasyarat yang berikut mesti dipenuhi:

- Anda mempunyai lesen Leadspace yang aktif dan “kunci kekal” (dirujuk sebagai **Token Leadspace**). Hubungi terus [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) untuk butiran tentang produk mereka.
- Anda mempunyai keizinan [Pentadbir](permissions.md#administrator).
- Anda mempunyai [profil pelanggan yang disatukan](customer-profiles.md) untuk syarikat.

## <a name="configuration"></a>Konfigurasi

1. Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan**.

1. Pilih **Perkayakan data saya** pada jubin Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Petikan skrin jubin Leadspace.":::

1. Pilih **Mari Bermula** dan kemudian masukkan **token Leadspace** aktif (kunci kekal). Semak semula dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**. Sahkan kedua-dua input dengan memilih **Sambung ke Leadspace**.

1. Pilih **Peta data** dan takrifkan medan yang hendak digunakan daripada profil disatukan untuk memadankan data syarikat Leadspace. Medan **Nama syarikat** diperlukan. Untuk ketepatan padanan yang lebih tinggi hingga dua medan yang lain, **Tapak web syarikat** dan **Lokasi syarikat** boleh ditambah.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Anak tetingkap pemetaan medan Leadspace.":::
   
1. Pilih **Gunakan** untuk melengkapkan pemetaan medan.

1. Pilih **Jalankan** untuk mengayakan profil syarikat. Tempoh yang diambil oleh pengayaan bergantung kepada bilangan profil pelanggan disatukan.

## <a name="enrichment-results"></a>Keputusan pengayaan

Selepas penyegaran semula pengayaan, anda boleh mengulas data syarikat yang baru diperkayakan di bawah [Pengayaan saya](enrichment-hub.md). Anda boleh menemui masa kemas kini terakhir dan bilangan profil yang diperkayakan.

Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.

Untuk maklumat lanjut, lihat [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Langkah seterusnya

Bina di atas data pelanggan anda yang diperkaya. Cipta [segmen](segments.md), [ukur](measures.md) dan juga [eksport data](export-destinations.md) untuk menghantar pengalaman diperibadikan kepada pelanggan anda.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Leadspace, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Leadspace memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.