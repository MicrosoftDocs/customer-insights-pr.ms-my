---
title: Gambaran keseluruhan langkah
description: Ketahui cara langkah-langkah membantu menganalisis dan mencerminkan prestasi perniagaan anda.
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
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245384"
---
# <a name="measures-overview"></a>Gambaran keseluruhan langkah

Langkah ini membantu anda untuk lebih memahami tingkah laku pelanggan dan prestasi perniagaan. Mereka melihat nilai yang relevan daripada [profil disatukan](data-unification.md). Contohnya, perniagaan ingin melihat *jumlah perbelanjaan setiap pelanggan* untuk memahami sejarah pembelian pelanggan individu atau mengukur *jumlah jualan syarikat* untuk memahami hasil peringkat agregat dalam keseluruhan perniagaan.

Cipta langkah untuk merancang aktiviti perniagaan dengan bertanya data pelanggan dan mengekstrak cerapan. Sebagai contoh, buat ukuran *jumlah perbelanjaan setiap pelanggan* dan *jumlah pulangan setiap pelanggan* untuk membantu mengenal pasti sekumpulan pelanggan dengan perbelanjaan yang tinggi namun pulangan yang tinggi. Kemudian, [buat segmen](segments.md) berdasarkan langkah-langkah ini untuk mendorong tindakan terbaik seterusnya.

## <a name="create-a-measure"></a>Cipta ukuran

Pilih cara membuat ukuran berdasarkan khalayak sasaran anda.

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

- Dari awal dengan pembina ukuran: [Bina sendiri](measure-builder.md).
- Daripada langkah yang biasa digunakan: [Gunakan templat yang dipratentukan](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

Dari awal dengan pembina ukuran: [Bina sendiri](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Urus langkah sedia ada

Pergi ke **halaman Ukuran** untuk melihat ukuran yang anda cipta, status, jenis ukuran dan kali terakhir data disegarkan semula. Anda boleh mengisih senarai langkah mengikut mana-mana lajur atau menggunakan kotak carian untuk mencari ukuran yang anda ingin uruskan.

Pilih di sebelah ukuran untuk melihat tindakan yang tersedia. Pilih nama ukuran untuk pratonton output dan muat turun fail CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Tindakan untuk menguruskan langkah tunggal."lightbox="media/measures-actions.png":::

- **Edit** langkah untuk menukar sifatnya.
- **Segar semula** ukuran untuk memasukkan data terkini.
- **Nama semula** langkah.
- **Mengaktifkan** atau **Nyahaktifkan** ukuran. Langkah tidak aktif tidak akan disegar semula semasa [segar semula](schedule-refresh.md) yang dijadualkan dan **Status** disenaraikan sebagai **Dilangkau**, menunjukkan bahawa segar semula tidak dicuba.
- **Tag** untuk [menguruskan tag](work-with-tags-columns.md#manage-tags) untuk ukuran.
- **Padam** langkah.
- **Lajur** untuk [menyesuaikan lajur](work-with-tags-columns.md#customize-columns) yang dipaparkan.
- **Tapis** untuk [menapis pada tag](work-with-tags-columns.md#filter-on-tags).
- **Cari nama** untuk dicari mengikut nama ukuran.

## <a name="refresh-measures"></a>Langkah-langkah segar semula

Langkah-langkah boleh disegarkan semula pada jadual automatik atau disegarkan secara manual atas permintaan. Untuk menyegar semula satu atau lebih langkah secara manual, pilihnya dan pilih **Segar Semula**. Untuk [menjadualkan segar semula](schedule-refresh.md) automatik, pergi ke **Jadual** > **Sistem** > **Pentadbir**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
