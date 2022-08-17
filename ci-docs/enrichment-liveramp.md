---
title: Memperkayakan profil pelanggan dengan data identiti daripada LiveRamp (pratonton)
description: Memperkayakan profil pelanggan dengan data LiveRamp.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237823"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Memperkayakan profil pelanggan dengan data identiti daripada LiveRamp (pratonton)

LiveRamp menyediakan resolusi identiti luar talian penentu dan penyatuan data pelanggan. Anda boleh memetakan pengecam peribadi dalam data pelanggan anda ke graf identiti AbiliTec dan menerima ID AbiliTec. Anda kemudian boleh menggunakan ID ini untuk penyatuan data pelanggan anda dengan lebih baik.

## <a name="supported-countriesregions"></a>Negara/rantau yang disokong

Kami kini menyokong memperkayakan profil pelanggan dengan data LiveRamp di Amerika Syarikat sahaja.

## <a name="prerequisites"></a>Prasyarat

- Langganan LiveRamp yang aktif. Untuk mendapatkan langganan, hubungi pasukan akaun LiveRamp anda atau untuk [dynamics@liveramp.com](mailto:dynamics@liveramp.com) mendapatkan maklumat lanjut.

- Langganan AbiliTec yang aktif dengan ID pelanggan dan rahsia untuk mengakses API. Untuk maklumat lanjut, lihat [Hab Pembangun API AbiliTec](https://developers.liveramp.com/abilitec-api/).

- Sambungan [LiveRamp](connections.md)[dikonfigurasikan](#configure-the-connection-for-liveramp) oleh pentadbir.

## <a name="configure-the-connection-for-liveramp"></a>Mengkonfigurasikan sambungan untuk LiveRamp

Anda mesti menjadi pentadbir [dalam](permissions.md#admin) Wawasan Pelanggan dan mempunyai ID dan rahsia klien LiveRamp yang aktif.

1. Pilih **Tambah sambungan** apabila mengkonfigurasi pengayaan, atau pergi ke **Sambungan** > **Pentadbir** dan pilih **Sediakan** pada jubin LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Anak tetingkap konfigurasi untuk menyediakan sambungan ke perkhidmatan LiveRamp AbiliTec.":::

1. Masukkan nama untuk sambungan dan ID klien LiveRamp yang sah dan rahsia.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi dan kemudian pilih **Simpan**.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya pada **identiti** daripada jubin LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Jubin identiti dalam halaman gambaran keseluruhan pengayaan.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Seterusnya**.

1. Pilih sambungan. Hubungi pentadbir jika tiada sambungan tersedia.

1. Pilih **Seterusnya**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang anda ingin besarkan dengan data identiti daripada LiveRamp. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda manakala segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

1. Tentukan jenis medan daripada profil bersatu anda untuk digunakan untuk memadankan data identiti daripada LiveRamp. Sekurang-kurangnya satu daripada medan **Nama dan alamat**, **E-mel** atau **Telefon** diperlukan. Untuk ketepatan padanan yang lebih tinggi, tambah medan lain. Pilih **Seterusnya**.

1. Petakan medan anda ke data pengenalan daripada LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opsyen pemetaan data untuk pengayaan LiveRamp.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. **Sediakan Nama** untuk pengayaan dan **nama** entiti Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Bilangan **pelanggan yang diperkaya oleh lapangan** menyediakan gerudi ke dalam liputan setiap bidang yang diperkaya.

## <a name="next-steps"></a>Langkah-langkah berikutnya

Bina di atas data pelanggan anda yang diperkaya. Gunakan ID AbiliTec untuk menyatukan profil pelanggan ke dalam pandangan berasaskan orang.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
