---
title: Cari dan tapis profil pelanggan
description: Cari maklumat dengan cepat tentang profil pelanggan disatukan dan tapis untuk atribut tertentu.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e17d745974958b73683f1f9406c5ae95f2cbcb3c
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732045"
---
# <a name="customer-profiles-search--filter-index"></a>Profil pelanggan: Indeks carian & tapis

Hasil daripada menyatukan data pelanggan anda ialah entiti Profil Pelanggan yang menyediakan pandangan disatukan ke dalam jumlah dasar pelanggan anda. Untuk [mendapatkan maklumat dengan pantas mengenai pelanggan atau kumpulan pelanggan tertentu](customer-profiles.md), anda boleh mengkonfigurasi keupayaan [Carian](customer-profiles.md) dan [Penapis](customer-profiles.md) pada halaman [Pelanggan](customer-profiles.md). Baca untuk mengetahui cara pentadbir boleh mengedit atribut pada halaman **Indeks carian & penapis**, yang tersedia kepada pengguna untuk carian dan penapisan.

   :::image type="content" source="media/search-filter.png" alt-text="Penapis carian":::

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Tambah medan dan tentukan atribut

Jika ia ialah kali pertama anda mentakrifkan atribut yang boleh dicari sebagai pentadbir, anda perlu mentakrifkan medan berindeks terlebih dahulu. Kami mencadangkan anda memilih semua atribut yang pengguna boleh mencari dan menapis pelanggan pada halaman **Pelanggan**. Anda hanya boleh menentukan atribut yang wujud di dalam entiti Profil Pelanggan yang anda cipta semasa proses penyatuan data.

1. Buka halaman **Pelanggan** dan pilih **Cari & indeks penapis**.

2. Pilih **+ Tambah** untuk menentukan medan yang berindeks.

3. Pilih atribut di dalam senarai yang anda mahu tambah sebagai medan berindeks. Anda sentiasa boleh tambah lebih banyak atribut dengan memilih **Tambah**. Anda juga boleh mengalih keluar sebarang atribut yang dipilih dengan memilih simbol **Alih Keluar**.

## <a name="explore-the-indexed-customer-fields-table"></a>Terokai jadual medan pelanggan Berindeks

Maklumat berikut ditunjukkan di dalam jadual.

- **Nama**: Mewakili nama atribut yang muncul dalam entiti Profil Pelanggan.
- **Jenis data**: Menentukan sama ada jenis data ialah rentetan, nombor atau tarikh.
- **Disertakan dalam carian**: Menentukan sama ada atribut ini boleh digunakan untuk mencari pelanggan pada halaman **Pelanggan** menggunakan medan **Carian**.
- **Tambah Penapis**: Kawalan untuk mentakrifkan cara atribut ini boleh digunakan untuk menapis pada halaman **Pelanggan**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Mengedit pilihan penapisan untuk atribut yang diberikan

Menu **Penapis** pada halaman **Pelanggan** boleh termasuk bilangan peringkat atribut (contohnya, menapis pelanggan berdasarkan kumpulan umur berbeza).

1. Pilih **Tambah Penapis** untuk atribut tertentu pada halaman **Indeks Carian & penapis**. Anda boleh mentakrifkan bilangan keputusan dan arahan yang akan diaturkan. Bergantung pada jenis data atribut, salah satu daripada anak tetingkap berikut muncul.

- Atribut jenis rentetan: Tentukan bilangan keputusan yang dikehendaki pada anak tetingkap **Pilihan penapis rentetan** dan dasar pesanan yang akan diaturkan.

- Atribut jenis berangka: Tentukan selang yang termasuk pada anak tetingkap **Pilihan penapis nombor** dan dasar pesanan yang akan diaturkan.

- Atribut jenis tarikh:  Tentukan selang yang termasuk pada anak tetingkap **Pilihan penapis tarikh** dan dasar pesanan yang akan diaturkan.

2. Pilih **Simpan** untuk menggunakan perubahan anda.

3. Pilih **Jalankan** sebaik sahaja anda bersedia untuk menggunakan tetapan anda. Selepas perubahan diproses, anda boleh mencarinya dalam [kad pelanggan pada halaman Pelanggan](customer-profiles.md). 

## <a name="next-steps"></a>Langkah seterusnya

Semak [halaman profil disatukan](customer-profiles.md) untuk mencari profil atau gunakan medan diindekskan untuk melihat subset semua profil disatukan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
