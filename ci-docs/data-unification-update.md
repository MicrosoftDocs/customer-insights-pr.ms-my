---
title: Kemas kini seting penyatuan
description: Kemas kini peraturan pendua, peraturan padanan atau medan bersatu dalam seting penyatuan.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: a7cf06c07e4b95b848a55dfe5fe0b09397fe744e
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245605"
---
# <a name="update-the-unification-settings"></a>Kemas kini seting penyatuan

Untuk menyemak semula atau mengubah sebarang seting penyatuan sebaik sahaja profil bersatu telah dicipta, lakukan langkah berikut.

1. Pergi ke **Penyatuan Data** > **·**.

   :::image type="content" source="media/m3_unified.png" alt-text="Petikan skrin halaman Penyatuan Data selepas data disatukan.":::

   > [!TIP]
   > Jubin **syarat** Pemadanan dipaparkan hanya jika berbilang entiti dipilih.

1. Pilih perkara yang anda mahu kemas kini:
   - [Medan sumber](#edit-source-fields) untuk menambah entiti atau atribut atau mengubah jenis atribut.
   - [Rekod](#manage-deduplication-rules) pendua untuk menguruskan peraturan penyahduplikasi atau keutamaan cantuman.
   - [Syarat](#manage-match-rules) pemadanan untuk mengemas kini peraturan padanan merentas dua atau lebih entiti.
   - [Medan pelanggan bersepadu](#manage-unified-fields) untuk menggabungkan atau mengecualikan medan. Anda juga boleh mengumpulkan profil yang berkaitan ke dalam kelompok.

1. Selepas membuat perubahan anda, pilih pilihan anda yang seterusnya:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Petikan skrin halaman Penyatuan Data dengan opsyen Penyatuan diserlahkan.":::

   - [Jalankan syarat](#run-matching-conditions) pemadanan untuk menilai kualiti keadaan padanan anda dengan cepat (peraturan penyahduplikasi dan padanan) tanpa mengemas kini profil bersatu. Opsyen **Jalankan syarat padanan sahaja** tidak dipaparkan untuk entiti tunggal.
   - [Menyatukan profil](#run-updates-to-the-unified-customer-profile) pelanggan untuk menjalankan syarat yang sepadan dan mengemas kini entiti profil pelanggan yang bersatu tanpa memberi kesan kepada kebergantungan (seperti pengayaan, segmen atau langkah). Proses bergantung tidak dijalankan, tetapi akan disegarkan semula seperti [yang ditakrifkan dalam jadual](schedule-refresh.md) segar semula.
   - [Menyatukan profil pelanggan dan kebergantungan](#run-updates-to-the-unified-customer-profile) untuk menjalankan syarat yang sepadan dan mengemas kini entiti profil pelanggan yang bersatu dan semua kebergantungan (seperti pengayaan, segmen atau langkah). Semua proses dijalankan semula secara automatik.

## <a name="edit-source-fields"></a>Edit medan sumber

Anda tidak boleh mengalih keluar atribut atau entiti jika ia telah disatukan.

1. Pilih **Edit** pada **jubin Medan** sumber.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Petikan skrin halaman Medan sumber menunjukkan bilangan kekunci utama, medan yang dipetakan dan belum dipetakan":::

   Bilangan paparan medan yang dipetakan dan belum dipetakan.

1. Pilih **Pilih entiti dan medan** untuk menambah atribut atau entiti lain. Gunakan carian atau tatal untuk mencari dan memilih atribut dan entiti yang anda berminat. Pilih **Guna**.

1. Secara pilihan, anda boleh menukar kunci utama untuk entiti, jenis atribut dan menogol **pemetaan** pintar hidup atau mati. Untuk maklumat lanjut, lihat [Memilih kekunci utama dan jenis semantik untuk atribut](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Pilih **Seterusnya** untuk membuat perubahan kepada peraturan penyahduplikasi, atau pilih **Simpan dan tutup** dan kembali ke [Kemas kini seting](#update-the-unification-settings) penyatuan.

## <a name="manage-deduplication-rules"></a>Urus peraturan penyahduplikasi

1. Pilih **Edit** pada **jubin Rekod** pendua.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Petikan skrin halaman Rekod pendua menunjukkan bilangan rekod pendua" lightbox="media/m3_duplicates_edit.png":::

   Bilangan rekod pendua yang ditemui dipaparkan di bawah **Pendua**. Lajur **deduplicated** Rekod menunjukkan entiti yang mempunyai rekod pendua dan peratusan rekod pendua.

1. Jika anda menambah entiti yang diperkaya, pilih **Gunakan entiti** yang diperkaya. Untuk maklumat lanjut, lihat [Memperkayakan sumber](data-sources-enrichment.md) data.

1. Untuk menguruskan peraturan penyahduplikasi, pilih mana-mana opsyen berikut:
   - **Cipta peraturan** baru: Pilih **Tambah peraturan** di bawah entiti yang sesuai. Untuk maklumat lanjut, lihat [Mentakrifkan peraturan](remove-duplicates.md#define-deduplication-rules) penyahduplikasi.
   - **Tukar syarat** peraturan: Pilih peraturan dan kemudian **Edit**. Mengubah medan, menambah atau mengalih keluar syarat atau menambah atau mengalih keluar pengecualian.
   - **Pratonton**: Pilih peraturan dan kemudian **Pratonton** untuk melihat hasil larian terakhir untuk peraturan ini.
   - **Nyahaktifkan peraturan**: Pilih peraturan dan kemudian **Nyahaktifkan** untuk mengekalkan peraturan penyahduplikasi sambil mengecualikannya daripada proses pemadanan.
   - **Pendua peraturan**: Pilih peraturan dan kemudian **Pendua** untuk mencipta peraturan yang sama dengan pengubahsuaian.
   - **Padamkan peraturan**: Pilih peraturan dan kemudian **Padam**.

1. Untuk mengubah keutamaan cantum, pilih entiti. Anda hanya boleh menukar keutamaan jika peraturan dicipta.
   1. Pilih **Edit keutamaan** cantum dan ubah **opsyen Rekod untuk disimpan**.
   1. Untuk mengubah keutamaan cantum pada atribut individu entiti, pilih **Lanjutan** dan buat perubahan yang diperlukan.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Petikan skrin keutamaan cantum lanjutan menunjukkan e-mel terkini dan alamat yang paling lengkap":::

   1. Pilih **Selesai**.

1. Pilih **Seterusnya** untuk membuat perubahan kepada keadaan yang sepadan, atau pilih **Simpan dan tutup** dan kembali ke [Kemas kini seting](#update-the-unification-settings) penyatuan.

## <a name="manage-match-rules"></a>Urus peraturan padanan

Anda boleh mengkonfigurasikan semula dan menambah baik kebanyakan parameter padanan. Anda tidak boleh menambah atau memadam entiti. Peraturan padanan tidak digunakan pada satu entiti.

1. Pilih **Edit** pada **jubin Keadaan** padanan.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Petikan skrin halaman Padankan peraturan dan syarat dengan statistik." lightbox="media/m3_match_edit.png":::

   Halaman memaparkan tertib padanan dan peraturan tertakrif dan statistik berikut:
   - **Rekod sumber unik** menunjukkan bilangan rekod sumber individu yang diproses dalam jalanan padanan yang terakhir.
   - **Rekod yang dipadankan dan tidak dipadankan** menyerlahkan bilangan rekod unik yang kekal selepas memproses peraturan padanan.
   - **Rekod yang dipadankan sahaja** menunjukkan bilangan padanan merentasi semua pasangan padanan anda.

1. Untuk melihat keputusan semua peraturan dan skornya, pilih **Lihat larian** terakhir. Hasilnya dipaparkan, termasuk ID kenalan alternatif. Anda boleh memuat turun hasilnya.

1. Untuk melihat hasil dan skor peraturan tertentu, pilih peraturan dan kemudian **Pratonton**. Keputusan dipaparkan. Anda boleh memuat turun hasilnya.

1. Untuk melihat hasil keadaan tertentu pada peraturan, pilih peraturan dan kemudian **Edit**. Pada anak tetingkap Edit, pilih **Pratonton** di bawah syarat. Anda boleh memuat turun hasilnya.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Perwakilan grafik rekod yang tidak sepadan dan sepadan termasuk senarai data.":::

1. Jika anda menambah entiti yang diperkaya, pilih **Gunakan entiti** yang diperkaya. Untuk maklumat lanjut, lihat [Memperkayakan sumber](data-sources-enrichment.md) data.

1. Untuk menguruskan peraturan, pilih mana-mana opsyen berikut:
   - **Cipta peraturan** baru: Pilih **Tambah peraturan** di bawah entiti yang sesuai. Untuk maklumat lanjut, lihat [Mentakrifkan peraturan untuk pasangan](match-entities.md#define-rules-for-match-pairs) padanan.
   - **Tukar tertib peraturan** anda jika anda mentakrifkan berbilang peraturan: Seret dan lepaskan peraturan ke dalam tertib yang anda inginkan. Untuk maklumat lanjut, lihat [Menentukan tertib](match-entities.md#specify-the-match-order) padanan.
   - **Tukar syarat** peraturan: Pilih peraturan dan kemudian **Edit**. Mengubah medan, menambah atau mengalih keluar syarat atau menambah atau mengalih keluar pengecualian.
   - **Nyahaktifkan peraturan**: Pilih peraturan dan kemudian **Nyahaktifkan** untuk mengekalkan peraturan padanan sambil mengecualikannya daripada proses pemadanan.
   - **Pendua peraturan**: Pilih peraturan dan kemudian **Pendua** untuk mencipta peraturan yang sama dengan pengubahsuaian.
   - **Padamkan peraturan**: Pilih peraturan dan kemudian **Padam**.

1. Pilih **Seterusnya** untuk membuat perubahan pada medan bersatu, atau pilih **Simpan dan tutup** dan kembali ke [Kemas kini seting](#update-the-unification-settings) penyatuan.

## <a name="manage-unified-fields"></a>Urus medan bersatu

1. Pilih **Edit** pada jubin Medan klien **disatukan**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Petikan skrin medan klien Disatukan":::

1. Semak medan gabungan dan dikecualikan, dan buat sebarang perubahan mengikut keperluan. Tambah atau edit kekunci CustomerID atau profil kumpulan ke dalam kelompok. Untuk maklumat lanjut, lihat [Menyatukan medan](merge-entities.md) pelanggan.

1. Pilih **Seterusnya** untuk menyemak semula seting penyatuan dan [kemas kini profil dan kebergantungan](#run-updates-to-the-unified-customer-profile) bersatu, atau pilih **Simpan dan tutup** dan kembali ke [Kemas kini tetapan](#update-the-unification-settings) penyatuan untuk membuat lebih banyak perubahan.

## <a name="run-matching-conditions"></a>Jalankan syarat padanan

Jalankan syarat pemadanan menjalankan peraturan deduplikasi dan padanan sahaja dan mengemas kini *entiti Deduplication_** dan *ConflationMatchPair*.

1. **Daripada halaman Penyatuan** > **Data**, pilih **Jalankan syarat pemadanan sahaja**.

   Rekod **pendua** dan **jubin syarat** Padanan menunjukkan **status Baris** Gilir atau **Menyegar Semula**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Apabila proses pemadanan selesai, pilih **Edit** pada **jubin Syarat** Pemadanan.

   :::image type="content" source="media/match-KPIs.png" alt-text="Petikan skrin metrik utama yang dipangkas pada halaman Padanan dengan bilangan dan butiran.":::

1. Untuk membuat perubahan, lihat [Menguruskan peraturan](#manage-deduplication-rules) penyahduplikasi atau [Menguruskan peraturan](#manage-match-rules) padanan.

1. Jalankan proses padanan sekali lagi atau [jalankan kemas kini ke profil](#run-updates-to-the-unified-customer-profile) pelanggan.

## <a name="run-updates-to-the-unified-customer-profile"></a>Jalankan kemas kini ke profil pelanggan bersatu

1. **Daripada halaman Penyatuan** > **Data**, pilih:

   - **Menyatukan profil** pelanggan: Menjalankan syarat yang sepadan dan mengemas kini entiti profil pelanggan yang disatukan tanpa memberi kesan kepada kebergantungan (seperti pengayaan, segmen atau langkah). Proses bergantung tidak dijalankan, tetapi akan disegarkan semula seperti [yang ditakrifkan dalam jadual](schedule-refresh.md) segar semula.

   - **Menyatukan profil pelanggan dan kebergantungan**: Menjalankan syarat yang sepadan dan mengemas kini profil bersatu dan semua kebergantungan. Semua proses dijalankan semula secara automatik. Selepas semua proses hiliran telah selesai, profil pelanggan mencerminkan data yang dikemas kini.

   Rekod **pendua**, **syarat** Pemadanan dan **jubin medan** klien Disatukan menunjukkan **status Baris** Gilir atau **Menyegar Semula**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Hasil paparan larian yang berjaya pada **halaman Unify** yang menunjukkan bilangan profil pelanggan bersatu.
