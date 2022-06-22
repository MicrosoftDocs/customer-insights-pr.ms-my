---
title: Semak semula penyatuan data
description: Semak langkah penyatuan data, cipta profil pelanggan bersatu dan semak semula keputusan
ms.date: 06/02/2022
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
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844097"
---
# <a name="review-data-unification"></a>Semak semula penyatuan data

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Langkah terakhir dalam proses penyatuan ini menunjukkan ringkasan langkah-langkah dalam proses dan memberi peluang untuk membuat perubahan sebelum anda membuat profil bersatu.

:::image type="content" source="media/m3_review.png" alt-text="Petikan skrin Semak dan Buat profil pelanggan.":::

## <a name="review-the-data-unification-steps"></a>Semak semula langkah penyatuan data

1. Pilih **Edit** pada mana-mana langkah penyatuan data untuk menyemak dan membuat sebarang perubahan.

1. Jika anda berpuas hati dengan pilihan anda, pilih **Buat profil pelanggan**. Halaman **Unify** dipaparkan semasa profil pelanggan bersatu sedang dicipta. Semua jubin kecuali **Medan sumber** menunjukkan **status Beratur** atau **Menyegar Semula**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Petikan skrin halaman Unify dengan jubin menunjukkan Dibaris gilir atau Segar Semula.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritma penyatuan mengambil sedikit masa untuk diselesaikan dan anda tidak boleh menukar konfigurasi sehingga ia selesai. Apabila proses penyatuan selesai, entiti profil pelanggan bersatu, yang dipanggil *Pelanggan*, disenaraikan di **halaman Entiti** di **bahagian Profil**. Larian penyatuan pertama yang berjaya mewujudkan entiti Pelanggan *bersatu*. Semua yang seterusnya berjalan mengembangkan entiti itu.

## <a name="review-the-results-of-data-unification"></a>Mengkaji semula keputusan penyatuan data

Selepas penyatuan, **halaman Unify** > **Data** menunjukkan bilangan profil pelanggan bersatu. Hasil setiap langkah dalam proses penyatuan dipaparkan pada setiap jubin. Sebagai contoh, **medan** Sumber menunjukkan bilangan atribut yang dipetakan (medan) dan **Rekod** pendua menunjukkan bilangan rekod pendua yang ditemui.

:::image type="content" source="media/m3_unified.png" alt-text="Petikan skrin halaman Unify Data selepas data disatukan.":::

> [!TIP]
> Jubin **keadaan** pemadanan dipaparkan hanya jika berbilang entiti dipilih.

Kami mengesyorkan agar anda menyemak keputusan, terutamanya kualiti peraturan [padanan anda](data-unification-update.md#manage-match-rules) dan memperhalusinya jika perlu.

Apabila diperlukan, [buat perubahan pada tetapan](data-unification-update.md) penyatuan dan jalankan semula profil bersatu.

## <a name="next-step"></a>Langkah Seterusnya

Konfigurasikan [aktiviti](activities.md), [pengayaan](enrichment-hub.md)[, hubungan](relationships.md) atau [langkah-langkah](measures.md) untuk mendapatkan lebih banyak cerapan tentang pelanggan anda.

[!INCLUDE[footer-include](includes/footer-banner.md)]
