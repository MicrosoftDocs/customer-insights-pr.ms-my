---
title: Semak semula penyatuan data
description: Semak semula langkah penyatuan data, cipta profil pelanggan yang disatukan dan semak semula keputusan
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303978"
---
# <a name="review-data-unification"></a>Semak semula penyatuan data

Semak semula ringkasan perubahan, cipta profil bersatu dan semak semula keputusan.

## <a name="review-and-create-customer-profiles"></a>Semak semula dan cipta profil pelanggan

Langkah terakhir dalam proses penyatuan ini menunjukkan ringkasan langkah-langkah dalam proses dan menyediakan peluang untuk membuat perubahan sebelum anda mencipta profil bersatu.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Tangkapan skrin Semak dan buat profil pelanggan.":::

1. Pilih **Edit** pada mana-mana langkah penyatuan data untuk menyemak semula dan membuat sebarang perubahan.

1. Jika anda berpuas hati dengan pilihan anda, pilih **Buat profil** pelanggan (atau **Cipta profil** akaun untuk B-to-B). Halaman **Penyatuan** dipaparkan semasa profil pelanggan bersatu sedang dibuat.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Petikan skrin halaman Penyatuan dengan jubin menunjukkan Beratur atau Segar Semula.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritma penyatuan mengambil sedikit masa untuk diselesaikan dan anda tidak boleh mengubah konfigurasi sehingga selesai.

## <a name="view-the-results-of-data-unification"></a>Melihat hasil penyatuan data

Selepas penyatuan, **halaman Penyatuan** > **Data** menunjukkan bilangan profil pelanggan bersatu (atau profil akaun untuk B-to-B). Hasil setiap langkah dalam proses penyatuan dipaparkan pada setiap jubin. Contohnya, **medan** Sumber menunjukkan bilangan atribut dipetakan (medan) dan **Rekod** pendua menunjukkan bilangan rekod pendua yang ditemui.

:::image type="content" source="media/m3_unified.png" alt-text="Petikan skrin halaman Penyatuan Data selepas data disatukan.":::

> [!TIP]
> Jubin **Syarat** pemadanan dipaparkan hanya jika berbilang entiti dipilih.

Kami mengesyorkan agar anda menyemak keputusan, terutamanya kualiti peraturan [perlawanan anda](data-unification-update.md#manage-match-rules) dan memperhalusinya jika perlu.

Apabila diperlukan, [buat perubahan pada tetapan](data-unification-update.md) penyatuan dan jalankan semula profil bersatu.

### <a name="verify-output-entities-from-data-unification"></a>Sahkan entiti output daripada penyatuan data

Pergi ke **Entiti** > **Data** untuk mengesahkan entiti output.

Entiti profil pelanggan bersatu, yang dipanggil *Pelanggan*, dipaparkan dalam bahagian **Profil**. Larian penyatuan pertama yang berjaya mewujudkan entiti Pelanggan *yang bersatu*. Semua larian seterusnya mengembangkan entiti itu.

Entiti pertindihan dan konflasi dicipta dan dipaparkan dalam bahagian **Sistem**. Entiti yang didedikasikan untuk setiap entiti sumber dicipta dengan nama **Deduplication_DataSource_Entity**. Entiti **ConflationMatchPairs** mengandungi maklumat mengenai padanan silang entiti.

Entiti output penyahduplikasi mengandungi maklumat berikut:
- ID / Kekunci
  - Kekunci primer dan medan ID Alternatif. Medan ID Alternatif terdiri daripada semua ID alternatif yang dikenal pasti untuk rekod.
  - Medan Deduplication_GroupId menunjukkan kumpulan atau kluster yang dikenal pasti dalam sesebuah entiti yang mengumpulkan semua rekod yang serupa berdasarkan medan penyahduplikasi yang ditetapkan. Ia digunakan untuk tujuan pemprosesan sistem. Jika tiada peraturan penyahduplikasi secara manual yang ditetapkan dan peraturan penyahduplikasi yang ditakrifkan sistem diguna pakai, anda tidak akan menemui medan ini dalam entiti keluaran penyahduplikasi.
  - Deduplication_WinnerId: Medan ini mengandungi ID pemenang daripada kumpulan atau kluster yang dikenal pasti. Jika Deduplication_WinnerId adalah sama dengan nilai penting Utama untuk rekod, ia bermaksud bahawa rekod ialah rekod pemenang.
- Medan yang digunakan untuk mentakrifkan peraturan penyahduplikasi.
- Medan Peraturan dan Skor untuk menunjukkan yang peraturan penyahduplikasi telah diguna pakai dan skor yang dikembalikan oleh algoritma sepadan.

## <a name="next-step"></a>Langkah Seterusnya

- Untuk B-to-B, secara pilihan melakukan [penyatuan](data-unification-contacts.md) kenalan.

- Untuk B-to-C, konfigurasikan [aktiviti](activities.md), [pengayaan](enrichment-hub.md), [hubungan](relationships.md) atau [langkah-langkah](measures.md) untuk mendapatkan lebih banyak cerapan tentang pelanggan anda.

[!INCLUDE[footer-include](includes/footer-banner.md)]
