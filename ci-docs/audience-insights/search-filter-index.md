---
title: Cari dan tapis profil pelanggan
description: Cari maklumat dengan cepat tentang profil pelanggan disatukan dan tapis untuk atribut tertentu.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406481"
---
# <a name="customer-profiles-search--filter-index"></a>Profil pelanggan: Indeks carian & tapis

Hasil daripada menyatukan data pelanggan anda ialah entiti Profil Pelanggan yang menyediakan pandangan disatukan ke dalam jumlah dasar pelanggan anda. Untuk [mendapatkan maklumat dengan pantas mengenai pelanggan atau kumpulan pelanggan tertentu](customer-profiles.md), anda boleh mengkonfigurasi keupayaan **Carian** dan **Penapis** pada halaman **Pelanggan**. Baca untuk mengetahui cara pentadbir boleh mengedit atribut pada halaman **Indeks carian & penapis**, yang tersedia kepada pengguna untuk carian dan penapisan.

> [!div class="mx-imgBorder"]
> ![Penapis carian](media/search-filter.png "Penapis carian")

## <a name="add-fields-and-specify-attributes"></a>Tambah medan dan tentukan atribut

Jika ia ialah kali pertama anda mentakrifkan atribut yang boleh dicari sebagai pentadbir, anda perlu mentakrifkan medan berindeks terlebih dahulu. Kami mencadangkan anda memilih semua atribut yang pengguna boleh mencari dan menapis pelanggan pada halaman **Pelanggan**. Anda hanya boleh menentukan atribut yang wujud di dalam entiti Profil Pelanggan yang anda cipta semasa proses penyatuan data.

1. Buka halaman **Pelanggan** dan pilih **Cari & indeks penapis**.

> [!NOTE]
> Kami mencipta konfigurasi indeks carian lalai pada atribut yang tersedia dalam entiti Pelanggan daripada jenis semantik yang berikut seperti yang ditakrifkan pada halaman Peta.
> - Nama pertama, Nama keluarga, Nama tengah, Nama tengah orang
> - Nama Organisasi
> - Alamat e-mel
> - Nombor telefon
> - Maklumat lokasi

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

3. Pilih **Jalankan** sebaik sahaja anda bersedia untuk menggunakan tetapan anda.
