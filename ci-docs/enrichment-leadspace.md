---
title: Memperkayakan profil syarikat dengan Leadspace (pratonton)
description: Maklumat umum tentang pengayaan pihak ketiga Leadspace.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f45fabc036775e11fc439f69513678d0607729d0
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237961"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Memperkayakan profil syarikat dengan Leadspace (pratonton)

Leadspace adalah sebuah syarikat sains data yang menyediakan Platform Data Pelanggan niaga-ke-niaga. Ia mendayakan persekitaran dengan profil pelanggan disatukan berdasarkan akaun untuk memperkayakan data mereka. Memperkayakan *Profil pelanggan* dengan atribut seperti saiz syarikat, lokasi atau industri. Memperkayakan *Profil kenalan* dengan atribut ciri seperti tajuk, persona atau pengesahan e-mel.

## <a name="prerequisites"></a>Prasyarat

- Lesen Leadspace yang aktif.
- [Profil pelanggan disatukan](customer-profiles.md) berdasarkan akaun.
- Sambungan [Leadspace](connections.md) [dikonfigurasikan](#configure-the-connection-for-leadspace) oleh pentadbir. Hubungi [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) secara langsung untuk maklumat mengenai produk mereka.

## <a name="configure-the-connection-for-leadspace"></a>Konfigurasikan sambungan untuk Leadspace

Anda mesti menjadi pentadbir [dalam](permissions.md#admin) Wawasan Pelanggan dan mempunyai "kunci kekal" (dirujuk sebagai **token** Leadspace).

1. Pilih **Tambah sambungan** apabila mengkonfigurasi pengayaan atau pergi ke **Sambungan** > **Pentadbir** dan pilih **Sediakan** pada jubin Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Halaman konfigurasi sambungan Leadspace.":::

1. Masukkan nama untuk sambungan dan token Leadspace yang sah.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi dan kemudian pilih **Simpan**.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya pada **data** Syarikat daripada jubin Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Petikan skrin jubin Leadspace.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Seterusnya**.

1. Pilih sambungan. Hubungi pentadbir jika tiada sambungan tersedia.

1. Pilih **Seterusnya**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang anda ingin perkayakan dengan data syarikat daripada Leadspace. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda manakala segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Tangkapan skrin apabila memilih set data pelanggan.":::

1. Tentukan jenis medan daripada profil bersatu anda untuk digunakan untuk pemadanan: alamat utama dan/atau sekunder. Anda boleh menentukan pemetaan medan untuk kedua-dua alamat dan memperkayakan profil untuk kedua-dua alamat secara berasingan. Contohnya, untuk alamat rumah dan alamat perniagaan. Pilih **Seterusnya**.

1. Petakan medan anda ke data syarikat dari Leadspace. Medan **Nama syarikat** diperlukan. Untuk ketepatan padanan yang lebih tinggi hingga dua medan yang lain, **Tapak web syarikat** dan **Lokasi syarikat** boleh ditambah.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Anak tetingkap pemetaan medan Leadspace.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. Pilih kotak semak jika anda mempunyai *Profil kenalan* yang anda mahu perkayakan. Wawasan Pelanggan akan memetakan medan yang diperlukan secara automatik.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Pengayaan rekod kenalan Leadspace.":::

1. Pilih **Seterusnya**.

1. **Sediakan Nama** untuk pengayaan dan **nama** entiti Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Untuk maklumat lanjut, lihat [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
