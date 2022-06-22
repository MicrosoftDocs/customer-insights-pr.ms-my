---
title: Pengayaan profil syarikat dengan ruang pengayaan pihak ketiga Leadspace
description: Maklumat umum tentang pengayaan pihak ketiga Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ca53f15bd7c71b3b4acb396c4daf52d7c7aff9eb
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954190"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Pengayaan profil syarikat dengan Leadspace (pratonton)

Leadspace adalah sebuah syarikat sains data yang menyediakan Platform Data Pelanggan niaga-ke-niaga. Ia mendayakan persekitaran dengan profil pelanggan disatukan berdasarkan akaun untuk memperkayakan data mereka. Memperkayakan *Profil pelanggan* dengan atribut seperti saiz syarikat, lokasi atau industri. Memperkayakan *Profil kenalan* dengan atribut ciri seperti tajuk, persona atau pengesahan e-mel.

## <a name="prerequisites"></a>Prasyarat

- Lesen Leadspace yang aktif.
- [Profil pelanggan bersatu](customer-profiles.md) berdasarkan akaun.
- Sambungan Ruang Utama [dikonfigurasikan](connections.md) [oleh](#configure-the-connection-for-leadspace) pentadbir. Hubungi [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) secara langsung untuk maklumat mengenai produk mereka.

## <a name="configure-the-connection-for-leadspace"></a>Konfigurasikan sambungan untuk Leadspace

Anda mesti menjadi [pentadbir](permissions.md#admin) dalam Wawasan Pelanggan dan mempunyai "kunci kekal" (dirujuk sebagai **token** Leadspace).

1. Pilih **Tambah sambungan** apabila mengkonfigurasi pengayaan atau pergi ke **Sambungan** > **Pentadbir** dan pilih **Sediakan** pada jubin Ruang Kongsi.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Halaman konfigurasi sambungan Leadspace.":::

1. Masukkan nama untuk sambungan dan token Leadspace yang sah.

1. Semak dan berikan persetujuan anda untuk [privasi dan pematuhan Data](#data-privacy-and-compliance) dengan memilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi dan kemudian pilih **Simpan**.

### <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Leadspace, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Leadspace memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya pada **data** Syarikat daripada jubin Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Petikan skrin jubin Leadspace.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Berikut**.

1. Pilih sambungan. Hubungi pentadbir jika tidak tersedia.

1. Pilih **Seterusnya**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang ingin anda memperkayakan dengan data syarikat dari Leadspace. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda sedangkan segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Tangkapan skrin apabila memilih set data pelanggan.":::

1. Tentukan jenis medan daripada profil bersatu anda untuk digunakan untuk pemadanan: alamat utama dan/atau sekunder. Anda boleh menentukan pemetaan medan untuk kedua-dua alamat dan memperkayakan profil untuk kedua-dua alamat secara berasingan. Sebagai contoh, untuk alamat rumah dan alamat perniagaan. Pilih **Seterusnya**.

1. Petakan medan anda ke data syarikat dari Leadspace. Medan **Nama syarikat** diperlukan. Untuk ketepatan padanan yang lebih tinggi hingga dua medan yang lain, **Tapak web syarikat** dan **Lokasi syarikat** boleh ditambah.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Anak tetingkap pemetaan medan Leadspace.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. Pilih kotak semak jika anda mempunyai *Profil kenalan* yang anda mahu perkayakan. Wawasan Pelanggan akan memetakan medan yang diperlukan secara automatik.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Pengayaan rekod kenalan Leadspace.":::

1. Pilih **Seterusnya**.

1. **Berikan Nama** untuk pengayaan dan **nama** entiti Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

## <a name="enrichment-results"></a>Keputusan pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Untuk maklumat lanjut, lihat [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
