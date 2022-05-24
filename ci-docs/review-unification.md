---
title: Semak semula penyatuan data
description: Semak langkah penyatuan data, cipta profil pelanggan bersatu dan semak semula keputusan
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/11/2022
ms.locfileid: "8743034"
---
# <a name="review-data-unification"></a>Semak semula penyatuan data

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Langkah terakhir dalam proses penyatuan ini menunjukkan ringkasan langkah-langkah dalam proses dan memberi peluang untuk membuat perubahan sebelum anda membuat profil bersatu.

:::image type="content" source="media/m3_review.png" alt-text="Petikan skrin Semak dan Buat profil pelanggan.":::

## <a name="review-the-data-unification-steps"></a>Semak semula langkah penyatuan data

1. Pilih **Edit** pada mana-mana langkah penyatuan data untuk menyemak dan membuat sebarang perubahan.

1. Jika anda berpuas hati dengan pilihan anda, pilih **Buat profil pelanggan**. Halaman **Unify** dipaparkan semasa profil pelanggan bersatu sedang dicipta. Algoritma penyatuan mengambil sedikit masa untuk diselesaikan dan anda tidak boleh menukar konfigurasi sehingga ia selesai.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Apabila proses penyatuan selesai, entiti profil pelanggan bersatu, yang dipanggil *Pelanggan*, disenaraikan di **halaman Entiti** di **bahagian Profil**. Larian penyatuan pertama yang berjaya mewujudkan entiti Pelanggan *bersatu*. Semua yang seterusnya berjalan mengembangkan entiti itu.

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
