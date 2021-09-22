---
title: Lihat dan cipta metrik
description: Cara mencipta, mengedit dan memadam metrik.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 97189168e0f5586aad8be8089a1f9e27893c2115c7e805ddaab1efc00e11b860
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034280"
---
# <a name="view-and-create-metrics"></a>Lihat dan cipta metrik

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Metrik membantu dalam memahami tingkah laku pelawat anda. Mereka mengagregat sifat peristiwa dan mengukur statistik dan prestasi sifat web anda.  

Katakan anda menjalankan promosi pemasaran di laman web anda. Anda boleh menggunakan metrik untuk menjejak bilangan pelawat unik atau pengguna yang datang ke laman web anda semasa promosi. Menganalisis metrik membantu anda memahami khalayak laman web anda dengan lebih baik. Menggabungkan metrik dengan [dimensi](dimensions.md) pada [laporan tersuai](custom-reports.md) membolehkan anda mengukur tingkah laku untuk memahami pengguna anda. Contohnya, anda boleh memisahkan pelawat ke dalam kategori baharu dan kembali untuk mengenal pasti perbezaan minat dan niat antara kumpulan.

## <a name="view-metrics"></a>Lihat metrik

Cerapan penglibatan termasuk pengagregatan yang biasa digunakan sifat peristiwa sebagai metrik sistem: 

- Pelawat
- Lawatan
- Pandangan halaman
- Klik

Metrik sistem ini adalah berdasarkan sifat peristiwa sedia ada dalam peristiwa asas.

1. Pergi ke **Data** dalam anak tetingkap navigasi kiri. 
1. Pilih tab **Metrik** untuk melihat senarai semua metrik dalam ruang kerja. 
   > [!NOTE]
   > Metrik janaan sistem adalah baca sahaja. Anda tidak boleh mengubah atau memadam metrik tersebut. Anda hanya boleh mencipta dan mengedit metrik tersuai.

## <a name="create-a-metric"></a>Cipta metrik

Persekitaran dan pentadbir ruang kerja boleh mencipta metrik. Sifat peristiwa mesti dihantar ke ruang kerja sebelum anda mencipta metrik. Anda boleh mencipta metrik berdasarkan sifat peristiwa yang dihantar oleh peristiwa asas atau menggunakan SDK web untuk [menghantar sifat peristiwa tersuai](advanced-SDK-implementation.md).

1. Pergi ke **Data** > **Metrik**.
1. Pilih **Metrik baharu**.

   :::image type="content" source="media/new-metric.png" alt-text="Tambah metrik pada peristiwa.":::

1. Untuk format, pilih jenis data **Integer** atau **Berganda**. Integer ialah nombor bulat. Untuk Berganda, anda boleh memilih antara satu hingga tiga tempat perpuluhan.
1. Dalam anak tetingkap **Pustaka sumber**, cari sifat peristiwa untuk menempatkan metrik.
1. Pilih **tanda tambah (+)** bersebelahan sifat untuk menggunakan tanda tersebut dalam formula. Anda hanya boleh mencipta formula berdasarkan satu sifat. 
1. Pilih salah satu daripada fungsi agregat berikut. 

   - Jumlah: jumlah aritmetik semua nilai 
   - Purata: purata min semua nilai
   - Kiraan: jumlah bilangan nilai
   - Kiraan nilai unik: jumlah bilangan nilai unik

   Selepas mentakrifkan metrik, anda melihat pratonton aktiviti metrik untuk jam terakhir.

1. Pilih **Simpan**. 
1. Masukkan nama untuk metrik dan pilih **Simpan**.

Ia boleh mengambil masa sehingga satu minit untuk metrik sebelum anda boleh menggunakan untuk [mencipta laporan tersuai](custom-reports.md).

## <a name="edit-a-metric"></a>Edit metrik

1. Pergi ke **Data** > **Metrik**.
1. Pilih metrik dalam senarai.
1. Ubah definisi metrik
1. Pilih **Simpan**.

## <a name="change-the-name-of-a-metric"></a>Ubah nama metrik

1. Pergi ke **Data** > **Metrik**.
1. Pilih **Lagi [...]** untuk metrik dan pilih **Edit nama**.
1. Ubah nama. 
1. Pilih **Namakan Semula**.

## <a name="delete-a-metric"></a>Padam metrik

1. Pergi ke **Data** > **Metrik**.
1. Pilih **Lagi [...]** untuk metrik dan pilih **Padam**.

   :::image type="content" source="media/delete-metric.png" alt-text="Padamkan metrik pada peristiwa.":::

1. Pilih **Padam** untuk mengesahkan pemadaman.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
