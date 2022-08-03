---
title: Urus indeks carian & penapis untuk profil pelanggan
description: Cari maklumat dengan cepat tentang profil pelanggan disatukan dan tapis untuk atribut tertentu.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187920"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Urus indeks carian & penapis untuk profil pelanggan

Hasil penyatuan data pelanggan anda adalah entiti Pelanggan *yang* memberikan pandangan bersatu ke dalam jumlah asas pelanggan anda. Untuk pengguna mencari maklumat mengenai pelanggan atau kumpulan pelanggan tertentu dengan cepat [, pentadbir mesti mengkonfigurasi](customer-profiles.md) keupayaan Carian **dan** Penapis **untuk** halaman Pelanggan **.**

   :::image type="content" source="media/search-filter.png" alt-text="Penapis carian":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Mentakrifkan atribut boleh dicari dan medan berindeks

Jika ini kali pertama anda mentakrifkan atribut yang boleh dicari sebagai pentadbir, tentukan medan berindeks terlebih dahulu. Kami mencadangkan anda memilih semua atribut yang pengguna boleh mencari dan menapis pelanggan pada halaman **Pelanggan**. Hanya atribut yang wujud dalam *entiti Pelanggan* yang dicipta semasa proses penyatuan data boleh ditentukan.

1. Pergi ke **Pelanggan** dan pilih **Indeks** Carian & penapis.

1. Pilih **+ Tambah**.

1. Pilih atribut dalam senarai yang anda ingin tambah sebagai medan berindeks dan klik **Gunakan**.

1. Untuk menambah lebih banyak atribut, pilih **Tambah**. Untuk mengalih keluar atribut yang dipilih, pilih atribut dan kemudian **Padam**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Cari & tapis halaman indeks.":::

1. Pilih **Jalankan** setelah anda bersedia untuk menggunakan tetapan carian dan penapis anda. Selepas perubahan diproses, lihatnya dalam [kad pelanggan pada halaman](customer-profiles.md) Pelanggan.

## <a name="define-filtering-options-for-a-given-attribute"></a>Mentakrifkan opsyen penapisan untuk atribut yang diberikan

Sediakan medan yang boleh digunakan untuk menapis pelanggan pada **halaman Pelanggan**.

1. Pergi ke **Pelanggan** dan pilih **Indeks** Carian & penapis.

1. Pilih atribut dan **Tambah Penapis**. Tentukan bilangan hasil dan urutan di mana ia akan dianjurkan. Bergantung pada jenis data atribut, salah satu anak tetingkap berikut muncul.

   - Atribut jenis rentetan: Tentukan bilangan hasil yang diingini pada **anak tetingkap penapis** Rentetan dan dasar tertib yang akan disusun.

   - Atribut jenis berangka: Tentukan selang yang disertakan pada **anak tetingkap penapis** Nombor dan dasar tertib yang akan disusun.

   - Atribut jenis tarikh: Tentukan selang yang disertakan pada **anak tetingkap penapis** Tarikh dan dasar pesanan yang akan disusun.

1. Pilih **OK**. Ulangi untuk semua atribut yang anda ingin tapis.

1. Pilih **Jalankan** setelah anda bersedia untuk menggunakan tetapan carian dan penapis anda. Selepas perubahan diproses, lihatnya dalam [kad pelanggan pada halaman](customer-profiles.md) Pelanggan.

## <a name="view-indexed-customer-fields"></a>Lihat medan pelanggan berindeks

Halaman **indeks** Carian & penapis memaparkan maklumat berikut:

- **Nama**: Mewakili nama atribut seperti yang muncul dalam *entiti Pelanggan*.
- **Jenis data**: Menentukan sama ada jenis data ialah rentetan, nombor atau tarikh.
- **Disertakan dalam carian**: Menentukan sama ada atribut ini boleh digunakan untuk mencari pelanggan pada halaman **Pelanggan** menggunakan medan **Carian**.
- **Tambah Penapis**: Kawalan untuk mentakrifkan cara atribut ini boleh digunakan untuk menapis pada halaman **Pelanggan**.

## <a name="next-steps"></a>Langkah-langkah berikutnya

Semak [halaman profil disatukan](customer-profiles.md) untuk mencari profil atau gunakan medan diindekskan untuk melihat subset semua profil disatukan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
