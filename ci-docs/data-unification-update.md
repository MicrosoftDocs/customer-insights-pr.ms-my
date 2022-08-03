---
title: Kemas kini tetapan penyatuan
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
ms.openlocfilehash: 1af7f018abd412c833ff22b3880f0e4508ff4953
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139622"
---
# <a name="update-the-unification-settings"></a>Kemas kini tetapan penyatuan

Untuk menyemak atau mengubah sebarang seting penyatuan sebaik sahaja profil bersatu telah dicipta, lakukan langkah berikut.

1. Pergi ke **Data** > **Unify**.

   :::image type="content" source="media/m3_unified.png" alt-text="Petikan skrin halaman Unify Data selepas data disatukan.":::

   > [!TIP]
   > Jubin **keadaan** pemadanan dipaparkan hanya jika berbilang entiti dipilih.

1. Pilih perkara yang anda mahu kemas kini:
   - [Medan sumber](#edit-source-fields) untuk menambah entiti atau atribut atau mengubah jenis atribut.
   - [Rekod](#manage-deduplication-rules) pendua untuk menguruskan peraturan deduplikasi atau keutamaan cantum.
   - [Syarat](#manage-match-rules) pemadanan untuk mengemas kini peraturan yang sepadan merentas dua atau lebih entiti.
   - [Medan pelanggan bersatu](#manage-unified-fields) untuk menggabungkan atau mengecualikan medan. Anda juga boleh mengumpulkan profil yang berkaitan ke dalam kelompok.

1. Selepas membuat perubahan, pilih pilihan anda yang seterusnya:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Petikan skrin halaman Unify Data Unify dengan opsyen Unify diserlahkan.":::

   - [Jalankan keadaan](#run-matching-conditions) yang sepadan untuk menilai kualiti keadaan padanan anda dengan cepat (deduplication dan peraturan padanan) tanpa mengemas kini profil bersatu. Opsyen **Jalankan keadaan pemadanan sahaja** tidak dipaparkan untuk entiti tunggal.
   - [Menyatukan profil](#run-updates-to-the-unified-customer-profile) pelanggan untuk menjalankan keadaan yang sepadan dan mengemas kini entiti profil pelanggan yang bersatu tanpa memberi kesan kepada kebergantungan (seperti pengayaan, segmen atau langkah). Proses bergantung tidak dijalankan, tetapi akan disegarkan semula seperti [yang ditakrifkan dalam jadual](system.md#schedule-tab) segar semula.
   - [Menyatukan profil dan kebergantungan](#run-updates-to-the-unified-customer-profile) pelanggan untuk menjalankan keadaan yang sepadan dan mengemas kini entiti profil pelanggan yang bersatu dan semua kebergantungan (seperti pengayaan, segmen atau langkah). Semua proses dijalankan semula secara automatik.

## <a name="edit-source-fields"></a>Mengedit medan sumber

Anda tidak boleh mengalih keluar atribut atau entiti jika ia telah disatukan.

1. Pilih **Edit** pada **jubin Medan** sumber.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Petikan skrin halaman Medan sumber menunjukkan bilangan kekunci utama, medan yang dipetakan dan tidak dipetakan":::

   Bilangan medan yang dipetakan dan tidak dipetakan dipaparkan.

1. Pilih **Pilih entiti dan medan** untuk menambah atribut atau entiti lain. Gunakan carian atau tatal untuk mencari dan memilih atribut dan entiti yang anda berminat. Pilih **Guna**.

1. Secara pilihan, anda boleh menukar kekunci utama untuk entiti, jenis atribut dan togol **Pemetaan** pintar hidup atau mati. Untuk maklumat lanjut, lihat [Pilih kekunci utama dan jenis semantik untuk atribut](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Pilih **Seterusnya** untuk membuat perubahan pada peraturan penyahdendaban, atau pilih **Simpan dan tutup** dan kembali ke [Kemas Kini seting](#update-the-unification-settings) penyatuan.

## <a name="manage-deduplication-rules"></a>Urus peraturan deduplication

1. Pilih **Edit** pada **jubin Rekod** pendua.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Petikan skrin halaman Rekod pendua menunjukkan bilangan rekod pendua" lightbox="media/m3_duplicates_edit.png":::

   Bilangan rekod pendua yang ditemui dipaparkan di bawah **Pendua**. Lajur **deduplicated** Rekod menunjukkan entiti mana yang mempunyai rekod pendua dan peratusan rekod pendua.

1. Jika anda menambah entiti yang diperkaya, pilih **Gunakan entiti** yang diperkaya. Untuk maklumat lanjut, lihat [Pengayaan untuk sumber](data-sources-enrichment.md) data.

1. Untuk menguruskan peraturan deduplikasi, pilih mana-mana opsyen berikut:
   - **Cipta peraturan** baharu: Pilih **Tambah peraturan** di bawah entiti yang sesuai. Untuk maklumat lanjut, lihat [Mentakrifkan peraturan](remove-duplicates.md#define-deduplication-rules) deduplication.
   - **Tukar syarat** peraturan: Pilih peraturan dan kemudian **Edit**. Mengubah medan, menambah atau mengalih keluar keadaan atau menambah atau mengalih keluar pengecualian.
   - **Pratonton**: Pilih peraturan dan kemudian **Pratonton** untuk melihat hasil larian terakhir untuk peraturan ini.
   - **Nyahaktifkan peraturan**: Pilih peraturan dan kemudian **Nyahaktifkan** untuk mengekalkan peraturan deduplication sambil mengecualikannya daripada proses pemadanan.
   - **Menduplikasi peraturan**: Pilih peraturan dan kemudian **Pendua** untuk mencipta peraturan yang serupa dengan pengubahsuaian.
   - **Padamkan peraturan**: Pilih peraturan dan kemudian **Padam**.

1. Untuk menukar keutamaan cantum, pilih entiti. Anda hanya boleh menukar keutamaan jika peraturan dicipta.
   1. Pilih **Edit keutamaan** cantum dan ubah **pilihan Rekod untuk disimpan**.
   1. Untuk mengubah keutamaan cantuman pada atribut individu entiti, pilih **Lanjutan** dan buat perubahan yang diperlukan.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Petikan skrin keutamaan cantum lanjutan menunjukkan e-mel terkini dan alamat paling lengkap":::

   1. Pilih **Selesai**.

1. Pilih **Seterusnya** untuk membuat perubahan pada keadaan yang sepadan, atau pilih **Simpan dan tutup** dan kembali ke [Kemas Kini seting](#update-the-unification-settings) penyatuan.

## <a name="manage-match-rules"></a>Urus peraturan padanan

Anda boleh mengkonfigurasikan semula dan menambah baik kebanyakan parameter padanan. Anda tidak boleh menambah atau memadam entiti. Peraturan padanan tidak terpakai kepada satu entiti.

1. Pilih **Edit** pada **jubin Keadaan** padanan.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Petikan skrin halaman peraturan dan syarat padanan dengan statistik." lightbox="media/m3_match_edit.png":::

   Halaman memaparkan tertib padanan dan peraturan yang ditakrifkan dan statistik berikut:
   - **Rekod sumber unik** menunjukkan bilangan rekod sumber individu yang diproses dalam jalanan padanan yang terakhir.
   - **Rekod yang dipadankan dan tidak dipadankan** menyerlahkan bilangan rekod unik yang kekal selepas memproses peraturan padanan.
   - **Rekod yang dipadankan sahaja** menunjukkan bilangan padanan merentasi semua pasangan padanan anda.

1. Untuk melihat hasil semua peraturan dan skornya, pilih **Lihat larian** terakhir. Hasil dipaparkan, termasuk ID kenalan alternatif. Anda boleh memuat turun hasilnya.

1. Untuk melihat hasil dan skor peraturan tertentu, pilih peraturan dan kemudian **Pratonton**. Keputusan dipaparkan. Anda boleh memuat turun hasilnya.

1. Untuk melihat hasil syarat tertentu pada peraturan, pilih peraturan dan kemudian **Edit**. Pada anak tetingkap Edit, pilih **Pratonton** di bawah syarat. Anda boleh memuat turun hasilnya.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Perwakilan grafik bagi rekod yang tidak sepadan dan sepadan termasuk senarai data.":::

1. Jika anda menambah entiti yang diperkaya, pilih **Gunakan entiti** yang diperkaya. Untuk maklumat lanjut, lihat [Pengayaan untuk sumber](data-sources-enrichment.md) data.

1. Untuk menguruskan peraturan, pilih mana-mana opsyen berikut:
   - **Cipta peraturan** baharu: Pilih **Tambah peraturan** di bawah entiti yang sesuai. Untuk maklumat lanjut, lihat [Mentakrifkan peraturan untuk pasangan](match-entities.md#define-rules-for-match-pairs) padanan.
   - **Tukar tertib peraturan** anda jika anda mentakrifkan berbilang peraturan: Seret dan lepaskan peraturan ke dalam tertib yang anda inginkan. Untuk maklumat lanjut, lihat [Tentukan tertib](match-entities.md#specify-the-match-order) padanan.
   - **Tukar syarat** peraturan: Pilih peraturan dan kemudian **Edit**. Mengubah medan, menambah atau mengalih keluar keadaan atau menambah atau mengalih keluar pengecualian.
   - **Nyahaktifkan peraturan**: Pilih peraturan dan kemudian **Nyahaktifkan** untuk mengekalkan peraturan padanan sambil mengecualikannya daripada proses pemadanan.
   - **Menduplikasi peraturan**: Pilih peraturan dan kemudian **Pendua** untuk mencipta peraturan yang serupa dengan pengubahsuaian.
   - **Padamkan peraturan**: Pilih peraturan dan kemudian **Padam**.

1. Pilih **Seterusnya** untuk membuat perubahan pada medan bersatu, atau pilih **Simpan dan tutup** dan kembali ke [Kemas Kini seting](#update-the-unification-settings) penyatuan.

## <a name="manage-unified-fields"></a>Uruskan medan bersatu

1. Pilih **Edit** pada **jubin Medan** pelanggan Disatukan.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Petikan skrin medan pelanggan Disatukan":::

1. Semak semula medan gabungan dan dikecualikan, dan buat sebarang perubahan mengikut keperluan. Tambah atau edit kekunci CustomerID atau profil kumpulan ke dalam kelompok. Untuk maklumat lanjut, lihat [Menyatukan medan](merge-entities.md) pelanggan.

1. Pilih **Seterusnya** untuk menyemak seting penyatuan dan [mengemas kini profil dan kebergantungan](#run-updates-to-the-unified-customer-profile) yang bersatu, atau pilih **Simpan dan tutup** dan kembali ke [Kemas kini seting](#update-the-unification-settings) penyatuan untuk membuat lebih banyak perubahan.

## <a name="run-matching-conditions"></a>Jalankan keadaan yang sepadan

Jalankan keadaan yang sepadan menjalankan deduplication dan peraturan padanan sahaja dan mengemas kini *entiti Deduplication_** dan *ConflationMatchPair*.

1. **Daripada halaman Unify Data** > **Unify**, pilih **Jalankan syarat yang sepadan sahaja**.

   Jubin **rekod** pendua dan **keadaan** padanan menunjukkan **status Beratur** atau **Segar Semula**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Apabila proses pemadanan selesai, pilih **Edit** pada **jubin Keadaan** padanan.

   :::image type="content" source="media/match-KPIs.png" alt-text="Petikan skrin metrik utama yang dipangkas pada halaman Padanan dengan bilangan dan butiran.":::

1. Untuk membuat perubahan, lihat [Menguruskan peraturan](#manage-deduplication-rules) penyahduplikasi atau [Menguruskan peraturan](#manage-match-rules) padanan.

1. Jalankan proses padanan sekali lagi atau [jalankan kemas kini ke profil](#run-updates-to-the-unified-customer-profile) pelanggan.

## <a name="run-updates-to-the-unified-customer-profile"></a>Jalankan kemas kini ke profil pelanggan yang bersatu

1. **Daripada halaman Penyatuan** > **Data**, pilih:

   - **Menyatukan profil** pelanggan: Jalankan syarat yang sepadan dan kemas kini entiti profil pelanggan bersatu tanpa menjejaskan kebergantungan (seperti pengayaan, segmen atau langkah). Proses bergantung tidak dijalankan, tetapi akan disegarkan semula seperti [yang ditakrifkan dalam jadual](system.md#schedule-tab) segar semula.

   - **Menyatukan profil dan kebergantungan** pelanggan: Menjalankan keadaan yang sepadan dan mengemas kini profil bersatu dan semua kebergantungan. Semua proses dijalankan semula secara automatik. Selepas semua proses hiliran selesai, profil pelanggan mencerminkan data yang dikemas kini.

   Rekod pendua, syarat pemadanan dan **jubin medan** pelanggan Disatukan menunjukkan **status Beratur** atau **Segar Semula**.**·** **·**

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Hasil paparan larian yang berjaya pada **halaman Unify** menunjukkan bilangan profil pelanggan bersatu.
