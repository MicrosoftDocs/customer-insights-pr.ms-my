---
title: Mencipta profil kenalan bersatu (pratonton)
description: Lalui proses penyatuan data untuk mencipta set data induk tunggal kenalan.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305076"
---
# <a name="create-a-unified-contact-profile-preview"></a>Mencipta profil kenalan bersatu (pratonton)

Selepas [menyatukan akaun](map-entities.md) perniagaan, anda boleh menyatukan kenalan untuk akaun tersebut secara pilihan dan memautkan kenalan disatukan ke akaun disatukan. Proses penyatuan kenalan memetakan data kenalan daripada berbilang sumber data, mengalih keluar pendua, sepadan dengan data merentas entiti, menyediakan pemetaan semantik, mewujudkan perhubungan antara kenalan dan akaun, dan kemudian mencipta profil kenalan bersatu.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Beberapa langkah pertama adalah sama dengan langkah penyatuan akaun.

## <a name="prerequisites"></a>Prasyarat

Rekod akaun dan kenalan mesti mempunyai kunci unik (dipanggil kunci asing) yang menghubungkannya. Sebagai contoh, ID akaun yang wujud dalam rekod akaun dan rekod hubungan yang menghubungkan akaun dan kenalan bersama.

## <a name="preview-limitations"></a>Pratonton pengehadan

- Kenalan tanpa pautan ke akaun digugurkan.
- Jika akaun diduplikasikan, rekod pemenang dikenal pasti berdasarkan keutamaan cantuman. Rekod kalah tidak dipilih dan oleh itu digugurkan. Kenalan yang dikaitkan dengan rekod kehilangan digugurkan.
- Akaun boleh mempunyai berbilang kenalan tetapi kenalan dipautkan ke satu akaun.
- Atribut kenalan yang dipetakan dalam langkah pemetaan semantik adalah satu-satunya atribut yang boleh dipaparkan pada kad Pelanggan. Walau bagaimanapun, 17 atribut boleh didapati.

## <a name="select-source-fields"></a>Pilih medan sumber

1. Di bawah **Menyatukan kenalan (pratonton)**, pilih **Mari bermula**.

1. [Pilih entiti dan medan](map-entities.md) untuk sumber data kenalan anda, termasuk kekunci utama dan jenis atribut.

1. Pilih **Seterusnya**.

## <a name="remove-duplicate-records"></a>Mengalih keluar rekod pendua

1. Secara pilihan, [tentukan peraturan](remove-duplicates.md) pertindihan untuk entiti terpilih anda.

1. Pilih **Seterusnya**.

## <a name="match-conditions"></a>Syarat perlawanan

1. [Tentukan susunan perlawanan dan peraturan](match-entities.md) untuk pemadanan silang entiti.

1. Pilih **Seterusnya**.

## <a name="unify-contact-fields"></a>Menyatukan medan kenalan

1. [Menggabungkan dan mengecualikan medan kenalan](merge-entities.md).

1. Pilih **Seterusnya**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Takrifkan medan semantik untuk kenalan disatukan

Langkah ini dalam proses penyatuan memetakan medan hubungan bersatu anda kepada jenis semantik. Dalam B-to-B, kad pelanggan menunjukkan akaun. Apabila kad dipilih, semua kenalan yang dikaitkan dengan paparan akaun. Medan yang anda petakan dalam langkah ini ialah medan yang akan dipaparkan pada kad.

1. Pilih jenis semantik yang memetakan ke setiap medan bersatu. Pilih **Tiada** jika jenis semantik tidak tersedia.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Petikan skrin halaman bidang Semantik untuk menentukan jenis semantik." lightbox="media/semantic_mapping.png":::

1. Selepas memetakan semua medan bersatu, pilih **Seterusnya**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Mengesetkan perhubungan antara kenalan dan akaun

Langkah ini dalam proses penyatuan menghubungkan data kenalan anda ke data akaun yang sepadan.

1. Untuk setiap entiti, masukkan maklumat berikut:

   - **Kunci asing daripada entiti** hubungan: Pilih atribut yang menghubungkan entiti hubungan anda ke akaun.
   - **Untuk akaun entiti**: Pilih entiti akaun yang dikaitkan dengan kenalan.

   :::image type="content" source="media/contact_relationship.png" alt-text="Petikan skrin halaman Perhubungan untuk menyambungkan kenalan dan entiti akaun.":::

1. Pilih **Seterusnya**.

## <a name="review-contact-unification"></a>Semak penyatuan kenalan

Semak semula ringkasan perubahan, cipta profil bersatu dan semak semula keputusan.

### <a name="review-and-create-contact-profiles"></a>Semak semula dan cipta profil kenalan

Langkah terakhir dalam proses penyatuan ini menunjukkan ringkasan langkah-langkah dalam proses dan memberikan peluang untuk membuat perubahan sebelum anda mencipta profil kenalan bersatu.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Petikan skrin Semak Semula dan cipta profil kenalan.":::

1. Pilih **Edit** pada mana-mana langkah penyatuan kenalan untuk menyemak semula dan membuat sebarang perubahan.

1. Jika anda berpuas hati dengan pilihan anda, pilih **Cipta profil** kenalan. Halaman **Penyatuan** dipaparkan semasa profil kenalan disatukan sedang dicipta.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Petikan skrin halaman Menyatukan Kenalan dengan jubin menunjukkan Beratur atau Segar Semula.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritma penyatuan mengambil sedikit masa untuk diselesaikan dan anda tidak boleh mengubah konfigurasi sehingga selesai.

### <a name="view-the-results-of-contact-unification"></a>Melihat hasil penyatuan kenalan

Selepas penyatuan selesai, **halaman Penyatuan** > **Data** menunjukkan bilangan profil kenalan bersatu. Hasil setiap langkah dalam proses penyatuan dipaparkan pada setiap jubin. Contohnya, **medan** Sumber menunjukkan bilangan atribut dipetakan (medan) dan **Rekod** pendua menunjukkan bilangan rekod pendua yang ditemui.

:::image type="content" source="media/unified_contacts.png" alt-text="Petikan skrin halaman Penyatuan Data selepas kenalan disatukan.":::

> [!TIP]
> Jubin **Syarat** pemadanan dipaparkan hanya jika berbilang entiti dipilih.

Kami mengesyorkan agar anda menyemak keputusan, terutamanya kualiti peraturan [perlawanan anda](data-unification-update.md#manage-match-rules) dan memperhalusinya jika perlu.

Apabila diperlukan, [buat perubahan pada seting](data-unification-update.md) penyatuan kenalan dan jalankan semula profil bersatu.

### <a name="verify-output-entities-from-data-unification"></a>Sahkan entiti output daripada penyatuan data

Pergi ke **Entiti** > **Data** untuk mengesahkan entiti output.

Entiti profil kenalan bersatu, yang dipanggil *ContactProfile*, dipaparkan dalam bahagian **Entiti** semantik. Larian penyatuan pertama yang berjaya mencipta entiti ContactProfile *bersatu*. Semua larian seterusnya mengembangkan entiti itu.

Entiti *ContactsCustomer* (pratonton) dicipta dan dipaparkan dalam seksyen **Profil**. Entiti ini mengandungi data hubungan tanpa pautan ke akaun. Entiti ini digunakan sebagai input ke dalam pemetaan semantik dan langkah hubungan penyatuan kenalan.

Entiti pertindihan dan konflasi dicipta dan dipaparkan dalam bahagian **Sistem**. Entiti yang didedikasikan untuk setiap entiti sumber dicipta dengan nama **Deduplication_DataSource_Entity**. Entiti **ContactsConflationMatchPairs** mengandungi maklumat mengenai padanan silang entiti.

Entiti output penyahduplikasi mengandungi maklumat berikut:
- ID / Kekunci
  - Kekunci primer dan medan ID Alternatif. Medan ID Alternatif terdiri daripada semua ID alternatif yang dikenal pasti untuk rekod.
  - Medan Deduplication_GroupId menunjukkan kumpulan atau kluster yang dikenal pasti dalam sesebuah entiti yang mengumpulkan semua rekod yang serupa berdasarkan medan penyahduplikasi yang ditetapkan. Ia digunakan untuk tujuan pemprosesan sistem. Jika tiada peraturan penyahduplikasi secara manual yang ditetapkan dan peraturan penyahduplikasi yang ditakrifkan sistem diguna pakai, anda tidak akan menemui medan ini dalam entiti keluaran penyahduplikasi.
  - Deduplication_WinnerId: Medan ini mengandungi ID pemenang daripada kumpulan atau kluster yang dikenal pasti. Jika Deduplication_WinnerId adalah sama dengan nilai penting Utama untuk rekod, ia bermaksud bahawa rekod ialah rekod pemenang.
- Medan yang digunakan untuk mentakrifkan peraturan penyahduplikasi.
- Medan Peraturan dan Skor untuk menunjukkan yang peraturan penyahduplikasi telah diguna pakai dan skor yang dikembalikan oleh algoritma sepadan.

## <a name="next-step"></a>Langkah Seterusnya

Konfigurasikan [aktiviti](activities.md), [pengayaan](enrichment-hub.md) atau [perhubungan](relationships.md) untuk mendapatkan lebih banyak cerapan tentang kenalan anda.
