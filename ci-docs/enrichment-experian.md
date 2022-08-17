---
title: Memperkaya profil pelanggan dengan demografi daripada Experian (pratonton)
description: Maklumat umum tentang pengayaan pihak ketiga Experian.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238007"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Memperkaya profil pelanggan dengan demografi daripada Experian (pratonton)

Experian ialah peneraju global dalam pelaporan kredit pengguna dan perniagaan serta perkhidmatan pemasaran. Dengan perkhidmatan pengayaan data Experian, anda boleh membina pemahaman yang lebih mendalam tentang pelanggan anda dengan memperkaya profil pelanggan anda menggunakan data demografi seperti saiz isi rumah, pendapatan dan banyak lagi.

## <a name="supported-countriesregions"></a>Negara/rantau yang disokong

Pada masa ini, kami menyokong pengayaan profil pelanggan di Amerika Syarikat sahaja.

## <a name="prerequisites"></a>Prasyarat

- Langganan aktif Experian. Untuk mendapatkan langganan, [hubungi Experian](https://www.experian.com/marketing-services/contact) secara terus. [Ketahui lebih lanjut tentang Pengayaan Data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Sambungan Experian [...](connections.md)[dikonfigurasikan](#configure-the-connection-for-experian) oleh pentadbir.

- Experian ID Pengguna, ID Parti dan Nombor Model untuk akaun Pengangkutan Selamat (ST) didayakan SSH anda yang Experian dicipta untuk anda.

## <a name="configure-the-connection-for-experian"></a>Konfigurasikan sambungan untuk Experian

Anda mesti menjadi pentadbir [dalam](permissions.md#admin) Wawasan Pelanggan dan mempunyai Experian ID Pengguna, ID Parti dan Nombor Model.

1. Pilih **Tambah sambungan** apabila mengkonfigurasi pengayaan, atau pergi ke **Sambungan** > **Pentadbir** dan pilih **Sediakan** pada Experian jubin.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Anak tetingkap konfigurasi sambungan Experian.":::

1. Masukkan nama untuk sambungan dan ID Pengguna, ID Parti dan Nombor Model yang sah untuk akaun Pengangkutan Selamat anda Experian.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi dan kemudian pilih **Simpan**.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya pada **Demografi** daripada Experian jubin.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian jubin dalam halaman gambaran keseluruhan pengayaan.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Seterusnya**.

1. Pilih sambungan. Hubungi pentadbir jika tiada sambungan tersedia.

1. Pilih **Seterusnya**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang anda ingin memperkayakan dengan data demografi dari Experian. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda manakala segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Tangkapan skrin apabila memilih set data pelanggan.":::

1. Tentukan jenis medan daripada profil bersatu anda untuk digunakan untuk memadankan data demografi daripada Experian. Sekurang-kurangnya salah satu medan **Nama dan alamat**, **Telefon** atau **E-mel** diperlukan. Untuk ketepatan padanan yang lebih tinggi, tambah medan lain. Pilih **Seterusnya**.

1. Petakan medan anda ke data demografi dari Experian.

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. **Sediakan Nama** untuk pengayaan dan **nama** entiti Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Bilangan **pelanggan yang diperkaya oleh lapangan** menyediakan gerudi ke dalam liputan setiap bidang yang diperkaya.

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
