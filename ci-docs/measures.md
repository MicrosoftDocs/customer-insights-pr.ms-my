---
title: Ukuran gambaran keseluruhan
description: Ketahui cara langkah membantu menganalisis dan mencerminkan prestasi perniagaan anda.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170832"
---
# <a name="measures-overview"></a>Ukuran gambaran keseluruhan

Langkah ini membantu anda untuk lebih memahami tingkah laku pelanggan dan prestasi perniagaan. Mereka melihat nilai yang relevan daripada [profil disatukan](data-unification.md). Contohnya, perniagaan ingin melihat *jumlah perbelanjaan setiap pelanggan* untuk memahami sejarah pembelian pelanggan individu atau mengukur *jumlah jualan syarikat* untuk memahami hasil peringkat agregat dalam keseluruhan perniagaan.

Buat langkah untuk merancang aktiviti perniagaan dengan menanya data pelanggan dan mengekstrak cerapan. Sebagai contoh, buat ukuran jumlah *perbelanjaan setiap pelanggan* dan *jumlah pulangan setiap pelanggan* untuk membantu mengenal pasti sekumpulan pelanggan dengan perbelanjaan yang tinggi namun pulangan yang tinggi. Kemudian, [buat segmen](segments.md) berdasarkan langkah-langkah ini untuk mendorong tindakan terbaik seterusnya.

## <a name="create-a-measure"></a>Cipta ukuran

Pilih cara membuat ukuran berdasarkan khalayak sasaran anda.

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

- Dari awal dengan pembina ukuran: [Bina sendiri](measure-builder.md).
- Daripada langkah yang biasa digunakan: [Gunakan templat yang dipratentukan](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

Dari awal dengan pembina ukuran: [Bina sendiri](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Menguruskan langkah-langkah sedia ada

Pergi ke **halaman Langkah** untuk melihat langkah yang anda cipta, status, jenis ukuran dan kali terakhir data disegar semula. Anda boleh mengisih senarai langkah mengikut mana-mana lajur atau menggunakan kotak carian untuk mencari ukuran yang anda ingin uruskan.

Pilih di sebelah ukuran untuk melihat tindakan yang tersedia. Pilih nama ukuran untuk melihat output dan muat turun fail CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Tindakan untuk menguruskan langkah tunggal."lightbox="media/measures-actions.png":::

- **Edit** ukuran untuk menukar sifatnya.
- **Segar semula** langkah untuk memasukkan data terkini.
- **Nama semula** langkah.
- **Mengaktifkan** atau **Menyahaktifkan** ukuran. Langkah-langkah tidak aktif tidak akan disegarkan semula semasa segar semula yang [dijadualkan dan mempunyai Status](system.md#schedule-tab) yang **disenaraikan sebagai** Dilangkau **, menunjukkan bahawa segar semula tidak** dicuba.
- **Tag** untuk [menguruskan tag](work-with-tags-columns.md#manage-tags) untuk ukuran.
- **Padam** langkah.
- **Lajur** untuk [menyesuaikan lajur](work-with-tags-columns.md#customize-columns) yang dipaparkan.
- **Tapis** untuk [menapis pada tag](work-with-tags-columns.md#filter-on-tags).
- **Cari nama** untuk dicari mengikut ukuran nama.

## <a name="refresh-measures"></a>Langkah-langkah segar semula

Langkah-langkah boleh disegarkan semula pada jadual automatik atau disegarkan secara manual atas permintaan. Untuk menyegar semula satu atau lebih langkah secara manual, pilihnya dan pilih **Segar Semula**. Untuk [menjadualkan segar semula](system.md#schedule-tab) automatik, pergi ke **Jadual** > **Sistem** > **Pentadbir**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
