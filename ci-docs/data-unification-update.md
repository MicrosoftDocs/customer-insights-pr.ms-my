---
title: Mengemas kini tetapan penyatuan pelanggan, akaun atau kenalan
description: Kemas kini peraturan pendua, peraturan padanan atau medan bersatu dalam tetapan penyatuan pelanggan atau akaun.
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392482"
---
# <a name="update-unification-settings"></a>Mengemas kini seting penyatuan

Untuk menyemak semula atau mengubah sebarang seting penyatuan sebaik sahaja profil bersatu dicipta, lakukan langkah berikut.

1. Pergi ke **Data** > **Penyatuan**.

   Untuk pelanggan individu (B-to-C), **halaman Penyatuan** memaparkan bilangan profil dan jubin pelanggan bersatu untuk setiap langkah penyatuan.

   :::image type="content" source="media/m3_unified.png" alt-text="Petikan skrin halaman Penyatuan Data selepas data disatukan." lightbox="media/m3_unified.png":::

   Untuk akaun perniagaan (B-to-B), **halaman Penyatuan** memaparkan bilangan profil dan jubin akaun bersatu untuk setiap langkah penyatuan akaun. Jika kenalan disatukan, bilangan profil kenalan disatukan dan jubin untuk setiap langkah penyatuan kenalan dipaparkan. Pilih jubin yang sesuai di bawah **Menyatukan Akaun** atau **Menyatukan Kenalan (pratonton)** bergantung pada perkara yang anda ingin kemas kini.

   :::image type="content" source="media/b2b_unified.png" alt-text="Petikan skrin halaman Penyatuan Data selepas akaun dan data kenalan disatukan." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Jubin **Syarat** pemadanan dipaparkan hanya jika berbilang entiti dipilih.

1. Pilih perkara yang anda mahu kemas kini:
   - [Medan sumber](#edit-source-fields) untuk menambah atribut atau entiti atau mengubah jenis atribut. Untuk mengalih keluar atribut, lihat [Alih keluar medan](#remove-a-unified-field) bersatu. Untuk mengalih keluar entiti, lihat [Alih keluar entiti](#remove-a-unified-entity) bersatu.
   - [Menduplikasi rekod](#manage-deduplication-rules) untuk menguruskan peraturan pertindihan atau keutamaan cantuman.
   - [Syarat](#manage-match-rules) yang sepadan untuk mengemas kini peraturan padanan merentasi dua atau lebih entiti.
   - [Bidang pelanggan bersatu](#manage-unified-fields) untuk menggabungkan atau mengecualikan bidang. Anda juga boleh mengumpulkan profil yang berkaitan ke dalam kluster.
   - [Bidang](#manage-semantic-fields-for-unified-contacts) semantik untuk menguruskan jenis semantik untuk bidang hubungan bersatu.
   - [Perhubungan](#manage-contact-and-account-relationships) untuk menguruskan kenalan ke perhubungan akaun.

1. Selepas membuat perubahan anda, pilih pilihan anda yang seterusnya:

   - [Jalankan syarat](#run-matching-conditions) yang sepadan untuk menilai dengan cepat kualiti syarat padanan anda (pertindihan dan peraturan perlawanan) tanpa mengemas kini profil bersatu. Pilihan **Syarat pemadanan Jalankan sahaja** tidak dipaparkan untuk entiti tunggal.
   - [Menyatukan profil](#run-updates-to-the-unified-profile) untuk menjalankan keadaan yang sepadan dan mengemas kini entiti profil bersatu tanpa menjejaskan kebergantungan (seperti pengayaan, segmen atau langkah). Proses bergantung tidak dijalankan tetapi akan disegar semula seperti [yang ditakrifkan dalam jadual](schedule-refresh.md) segar semula.
   - [Menyatukan profil dan kebergantungan untuk menjalankan keadaan yang](#run-updates-to-the-unified-profile) sepadan, mengemas kini entiti profil bersatu, dan mengemas kini semua kebergantungan (seperti pengayaan, segmen atau langkah). Semua proses disusun semula secara automatik. Dalam B-to-B, penyatuan dijalankan pada kedua-dua akaun dan entiti hubungan yang mengemas kini profil bersatu.

## <a name="edit-source-fields"></a>Mengedit medan sumber

1. Pilih **Edit** pada **jubin medan** Sumber.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Petikan skrin halaman medan Sumber menunjukkan bilangan kekunci primer, medan dipetakan dan dinyahlap":::

   Bilangan paparan medan yang dipetakan dan tidak dipetakan.

1. Untuk menambah atribut atau entiti lain, pilih **Pilih Entiti dan medan**.

1. Secara pilihan, anda boleh menukar kunci primer untuk entiti, jenis atribut dan togol **Pemetaan** pintar hidup atau mati. Untuk maklumat lanjut, lihat [Pilih medan](map-entities.md) sumber.

1. Pilih **Berikut** untuk membuat perubahan pada peraturan pertindihan atau pilih **Simpan dan tutup** dan kembali ke [Kemas kini seting](#update-unification-settings) penyatuan.

### <a name="remove-a-unified-field"></a>Mengalih keluar medan bersatu

Untuk mengalih keluar medan yang telah disatukan, medan mesti dialih keluar daripada sebarang kebergantungan seperti segmen, ukuran, pengayaan atau perhubungan.

1. Setelah semua kebergantungan untuk medan telah dialih keluar, pergi ke **Penyatuan** > **Data**.

1. Pilih **Edit** pada **jubin Medan** Pelanggan Disatukan.

1. Pilih semua kejadian medan kemudian pilih **Kecualikan**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Petikan skrin halaman medan Disatukan menunjukkan medan terpilih dan butang Kecualikan":::

1. Pilih **Selesai** untuk mengesahkan kemudian pilih **Simpan dan tutup**.

   > [!TIP]
   > Jika anda melihat mesej "Tidak dapat menyimpan penyatuan. Sumber yang ditentukan tidak boleh diubah suai atau dipadamkan kerana kebergantungan hiliran", maka medan itu masih digunakan dalam pergantungan hiliran.

1. Jika medan digunakan dalam peraturan untuk rekod pendua atau syarat yang sepadan, lakukan langkah berikut. Jika tidak, pergi ke langkah seterusnya.
   1. Pilih **Edit** pada **jubin Rekod** pendua.
   1. Alih keluar medan daripada semua peraturan yang digunakan dalam, jika ada, kemudian pilih **Seterusnya**.
   1. **Pada halaman Syarat** sepadan, alih keluar medan daripada semua peraturan yang digunakan dalam, jika ada, kemudian pilih **Simpan dan tutup**.
   1. Pilih **Menyatukan** > **Profil dan** Kebergantungan Pelanggan Penyatuan. Tunggu penyatuan selesai sebelum pergi ke langkah seterusnya.

1. Pilih **Edit** pada **jubin medan** Sumber.

1. Pilih **Pilih entiti dan medan** dan kosongkan kotak semak di sebelah setiap kejadian medan.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Petikan skrin bagi kotak dialog Pilih entiti dan medan menunjukkan kotak semak yang dikosongkan":::

1. Pilih **Guna**.

1. Pilih **Simpan dan tutup**.

1. Pilih **Menyatukan** > **Profil pelanggan dan kebergantungan** untuk mengemas kini profil bersatu.

### <a name="remove-a-unified-entity"></a>Alih keluar entiti bersatu

Untuk menghapuskan entiti yang telah disatukan, entiti mesti dikeluarkan dari sebarang kebergantungan seperti segmen, langkah, pengayaan atau hubungan.

1. Setelah semua kebergantungan untuk entiti telah dialih keluar, pergi ke **Penyatuan** > **Data**.

1. Pilih **Edit** pada **jubin Medan** Pelanggan Disatukan.

1. Pilih semua medan untuk entiti kemudian pilih **Kecualikan**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Petikan skrin medan Disatukan dengan semua medan untuk entiti dipilih dan butang Kecualikan":::

1. Pilih **Selesai** untuk mengesahkan kemudian pilih **Simpan dan tutup**.

   > [!TIP]
   > Jika anda melihat mesej "Tidak dapat menyimpan penyatuan. Sumber yang ditentukan tidak boleh diubah suai atau dipadamkan kerana kebergantungan hiliran", maka entiti itu masih digunakan dalam pergantungan hiliran.

1. Pilih **Edit** pada **jubin Rekod** pendua.

1. Alih keluar semua peraturan daripada entiti, jika ada, kemudian pilih **Seterusnya**.

1. Pada halaman **Syarat** sepadan, pilih entiti kemudian pilih **Padam**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Petikan skrin syarat padanan dengan entiti dipilih dan butang Padam":::

1. Pilih **Simpan dan tutup**.

1. Pilih **Edit** pada **jubin medan** Sumber.

1. Pilih **Pilih entiti dan medan** dan kosongkan kotak semak di sebelah entiti.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Petikan skrin kotak dialog Pilih entiti dan medan dengan kotak semak entiti dikosongkan":::

1. Pilih **Guna**.

1. Pilih **Simpan dan tutup**.

1. Pilih **Menyatukan** > **Profil pelanggan dan kebergantungan** untuk mengemas kini profil bersatu.

## <a name="manage-deduplication-rules"></a>Menguruskan peraturan pertindihan

1. Pilih **Edit** pada **jubin Rekod** pendua.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Petikan skrin halaman Rekod pendua menunjukkan bilangan rekod pendua" lightbox="media/m3_duplicates_edit.png":::

   Bilangan rekod pendua yang ditemui dipaparkan di bawah **Pendua**. Lajur **rekod pendua** menunjukkan entiti mana yang mempunyai rekod pendua dan peratusan rekod pendua.

1. Untuk menggunakan entiti yang diperkaya, pilih **Gunakan entiti** yang diperkaya. Untuk maklumat lanjut, lihat [Pengayaan untuk sumber](data-sources-enrichment.md) data.

1. Untuk menguruskan peraturan pertindihan, pilih mana-mana opsyen berikut:
   - **Cipta peraturan** baharu: Pilih **Tambah peraturan** di bawah entiti yang sesuai. Untuk maklumat lanjut, lihat [Menentukan peraturan](remove-duplicates.md#define-deduplication-rules) pertindihan.
   - **Tukar syarat** peraturan: Pilih peraturan kemudian **Edit**. Ubah medan, tambah atau alih keluar syarat atau tambah atau alih keluar pengecualian.
   - **Pratonton**: Pilih peraturan kemudian **Pratonton** untuk melihat hasil larian terakhir bagi peraturan ini.
   - **Nyahaktifkan peraturan**: Pilih peraturan kemudian **Nyahaktifkan** untuk mengekalkan peraturan pendua sambil mengecualikannya daripada proses pemadanan.
   - **Pendua peraturan**: Pilih peraturan dan kemudian **Pendua** untuk mencipta peraturan yang serupa dengan pengubahsuaian.
   - **Padamkan peraturan**: Pilih peraturan kemudian **Padam**.

1. Untuk menukar keutamaan cantum, pilih entiti. Anda hanya boleh menukar keutamaan jika peraturan dicipta.
   1. Pilih **Edit keutamaan** cantum dan ubah **opsyen Simpan Rekod**.
   1. Untuk menukar keutamaan gabungan pada atribut individu entiti, pilih **Lanjutan** dan buat perubahan yang diperlukan.

   1. Pilih **Selesai**.

1. Pilih **Berikut** untuk membuat perubahan pada syarat yang sepadan atau pilih **Simpan dan tutup** dan kembali ke [Kemas kini seting](#update-unification-settings) penyatuan.

## <a name="manage-match-rules"></a>Urus peraturan padanan

Anda boleh mengkonfigurasikan semula dan menambah baik kebanyakan parameter padanan. Anda tidak boleh menambah atau memadam entiti. Peraturan perlawanan tidak digunakan pada satu entiti.

1. Pilih **Edit** pada **jubin Syarat** sepadan.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Petikan skrin halaman Padankan peraturan dan syarat dengan statistik." lightbox="media/m3_match_edit.png":::

   Halaman memaparkan tertib padanan dan peraturan takrifan serta statistik berikut:
   - **Rekod** sumber unik menunjukkan bilangan rekod sumber individu yang diproses dalam larian padanan terakhir.
   - **Rekod yang dipadankan dan tidak dipadankan** menyerlahkan bilangan rekod unik yang kekal selepas memproses peraturan perlawanan.
   - **Rekod yang dipadankan hanya** menunjukkan bilangan padanan merentas semua pasangan perlawanan anda.

1. Untuk melihat keputusan semua peraturan dan skornya, pilih **Lihat larian** terakhir. Paparan hasil, termasuk ID kenalan alternatif. Anda boleh memuat turun hasilnya.

1. Untuk melihat hasil dan skor peraturan tertentu, pilih peraturan kemudian **Pratonton**. Paparan keputusan. Anda boleh memuat turun hasilnya.

1. Untuk melihat hasil syarat tertentu pada peraturan, pilih peraturan kemudian **Edit**. Pada anak tetingkap Edit, pilih **Pratonton** di bawah syarat. Anda boleh memuat turun hasilnya.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Perwakilan grafik bagi rekod yang tidak dapat ditandingi dan dipadankan termasuk senarai data.":::

1. Jika anda menambah entiti yang diperkaya, pilih **Gunakan entiti** yang diperkaya. Untuk maklumat lanjut, lihat [Pengayaan untuk sumber](data-sources-enrichment.md) data.

1. Untuk menguruskan peraturan, pilih mana-mana opsyen berikut:
   - **Cipta peraturan** baharu: Pilih **Tambah peraturan** di bawah entiti yang sesuai. Untuk maklumat lanjut, lihat [Menentukan peraturan untuk pasangan padanan](match-entities.md#define-rules-for-match-pairs).
   - **Ubah tertib peraturan** anda jika anda mentakrifkan berbilang peraturan: Seret dan lepaskan peraturan mengikut tertib yang anda inginkan. Untuk maklumat lanjut, lihat [Menentukan tertib](match-entities.md#specify-the-match-order) padanan.
   - **Tukar syarat** peraturan: Pilih peraturan kemudian **Edit**. Ubah medan, tambah atau alih keluar syarat atau tambah atau alih keluar pengecualian.
   - **Nyahaktifkan peraturan**: Pilih peraturan kemudian **Nyahaktifkan** untuk mengekalkan peraturan padanan sambil mengecualikannya daripada proses pemadanan.
   - **Pendua peraturan**: Pilih peraturan dan kemudian **Pendua** untuk mencipta peraturan yang serupa dengan pengubahsuaian.
   - **Padamkan peraturan**: Pilih peraturan kemudian **Padam**.

1. Pilih **Berikut** untuk membuat perubahan pada medan bersatu atau pilih **Simpan dan tutup** dan kembali ke [Seting penyatuan](#update-unification-settings) Kemas Kini.

## <a name="manage-unified-fields"></a>Menguruskan medan bersatu

1. Pilih **Edit** pada **jubin Medan** Pelanggan Disatukan.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Petikan skrin medan pelanggan Disatukan":::

1. Semak medan gabungan dan dikecualikan dan buat sebarang perubahan mengikut keperluan. Tambah atau edit kunci ID Pelanggan atau profil kumpulan ke dalam kelompok. Untuk maklumat lanjut, lihat [Menyatukan medan](merge-entities.md) pelanggan.

1. Untuk pelanggan atau akaun, pilih **Seterusnya** untuk menyemak dan [mengemas kini profil dan kebergantungan](#run-updates-to-the-unified-profile) bersatu. Atau pilih **Simpan dan tutup** dan kembali ke [Kemas Kini seting](#update-unification-settings) penyatuan untuk membuat lebih banyak perubahan.

   Untuk kenalan, pilih **Seterusnya** untuk menguruskan bidang semantik. Atau pilih **Simpan dan tutup** dan kembali ke [Kemas Kini seting](#update-unification-settings) penyatuan untuk membuat lebih banyak perubahan.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Menguruskan bidang semantik untuk kenalan bersatu

1. Pilih **Edit** pada **jubin medan** Semantik.

1. Untuk menukar jenis semantik untuk medan bersatu, pilih jenis baru. Untuk maklumat lanjut, lihat [Menentukan medan semantik untuk kenalan](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts) bersatu.

1. Pilih **Berikut** untuk menguruskan akaun dan perhubungan kenalan atau pilih **Simpan dan tutup** serta kembali ke [Seting penyatuan](#update-unification-settings) Kemas Kini untuk membuat lebih banyak perubahan.

## <a name="manage-contact-and-account-relationships"></a>Urus perhubungan kenalan dan akaun

1. Pilih **Edit** pada **jubin Perhubungan**.

1. Untuk mengubah perhubungan kenalan dan akaun, ubah sebarang maklumat berikut:

   - **Kunci asing daripada entiti** hubungan: Pilih atribut yang menghubungkan entiti hubungan anda ke akaun.
   - **Untuk akaun entiti**: Pilih entiti akaun yang dikaitkan dengan kenalan.

1. Pilih **Berikut** untuk menyemak semula seting penyatuan dan [mengemas kini profil dan kebergantungan bersatu](#run-updates-to-the-unified-profile) atau pilih **Simpan dan tutup** dan kembali ke [Seting](#update-unification-settings) penyatuan Kemas Kini untuk membuat lebih banyak perubahan.

## <a name="run-matching-conditions"></a>Menjalankan syarat yang sepadan

Jalankan syarat padanan menjalankan peraturan pendua dan padanan sahaja dan mengemas kini *entiti Deduplication_** dan *ConflationMatchPair*.

1. Daripada halaman **Penyatuan** > **Data**, pilih **Jalankan syarat yang sepadan sahaja**.

   Jubin **Rekod** Pendua dan **Syarat** sepadan menunjukkan **status Baris gilir** atau **Segar Semula**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Apabila proses pemadanan selesai, pilih **Edit** pada **jubin Syarat** sepadan.

   :::image type="content" source="media/match-KPIs.png" alt-text="Petikan skrin metrik utama yang dipangkas pada halaman Padanan dengan bilangan dan butiran.":::

1. Untuk membuat perubahan, lihat [Menguruskan peraturan](#manage-deduplication-rules) penduaan atau [Menguruskan peraturan](#manage-match-rules) padanan.

1. Jalankan proses perlawanan sekali lagi atau [jalankan kemas kini pada profil](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Menjalankan kemas kini pada profil bersatu

- Untuk menjalankan syarat yang sepadan dan mengemas kini entiti *profil bersatu tanpa* menjejaskan kebergantungan (seperti kad pelanggan, pengayaan, segmen atau langkah), pilih **Menyatukan profil** pelanggan. Untuk akaun, pilih **Menyatukan akaun** > **Menyatukan profil**. Untuk kenalan, pilih **Menyatukan kenalan (pratonton)** > **Menyatukan profil**. Proses bergantung tidak dijalankan tetapi akan disegar semula seperti [yang ditakrifkan dalam jadual](schedule-refresh.md) segar semula.
- Untuk menjalankan syarat yang sepadan, kemas kini profil bersatu dan jalankan semua kebergantungan, pilih **Menyatukan profil pelanggan dan kebergantungan**. Semua proses disusun semula secara automatik. Untuk akaun dan kenalan, pilih **Menyatukan akaun** > **Menyatukan profil dan kebergantungan**. Syarat yang sepadan dijalankan untuk kedua-dua akaun dan kenalan yang mengemas kini kedua-dua profil bersatu dan semua kebergantungan lain dijalankan.

Semua jubin kecuali **medan Sumber menunjukkan** Beratur **atau** Menyegar **Semula**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Hasil paparan larian yang berjaya pada **halaman Penyatuan** menunjukkan bilangan profil bersatu.
