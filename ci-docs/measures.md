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
ms.openlocfilehash: 880c06bffcfa269151d96cb4c597eed4832fc61b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083126"
---
# <a name="measures-overview"></a>Ukuran gambaran keseluruhan

Langkah ini membantu anda untuk lebih memahami tingkah laku pelanggan dan prestasi perniagaan. Mereka melihat nilai yang relevan daripada [profil disatukan](data-unification.md). Contohnya, perniagaan ingin melihat *jumlah perbelanjaan setiap pelanggan* untuk memahami sejarah pembelian pelanggan individu atau mengukur *jumlah jualan syarikat* untuk memahami hasil peringkat agregat dalam keseluruhan perniagaan.  

Langkah-langkah dibuat [menggunakan pembina](measure-builder.md) ukuran, platform pertanyaan data dengan pelbagai pengendali dan pilihan pemetaan mudah. Ia membolehkan anda menapis data, mengumpulkan hasil, mengesan [laluan perhubungan entiti](relationships.md) dan pratonton output. Anda boleh [menggunakan templat yang dipratentukan](measure-templates.md) untuk mengkonfigurasi langkah yang biasa digunakan dengan cekap.

Gunakan pembina ukuran untuk merancang aktiviti perniagaan dengan bertanya pada data pelanggan dan mendapatkan wawasan. Sebagai contoh, mencipta ukuran *jumlah perbelanjaan setiap pelanggan* dan *jumlah pulangan setiap pelanggan* membantu mengenal pasti kumpulan pelanggan yang mempunyai perbelanjaan tinggi tetapi pulangan tinggi. Anda boleh [membuat segmen](segments.md) berdasarkan langkah-langkah ini untuk mendorong tindakan terbaik seterusnya.

## <a name="manage-your-measures"></a>Urus tindakan anda

Anda boleh mendapatkan senarai langkah pada halaman **Langkah**.

Anda akan menemui maklumat tentang jenis ukuran, pencipta, tarikh penciptaan, status dan keadaan. Apabila anda memilih ukuran daripada senarai, anda boleh pratonton output dan memuat turun fail CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Tindakan untuk menguruskan langkah tunggal."lightbox="media/measures-actions.png":::

Tindakan berikut tersedia apabila anda memilih ukuran:

- **Edit** konfigurasi langkah.
- **Menduplikasikan** ukuran. Anda boleh memilih untuk mengedit sifat dengan serta-merta atau hanya menyimpan duplikasi.
- **Segar semula** ukuran berdasarkan data terkini. Untuk menyegar semula semua langkah anda pada masa yang sama, pilih semua langkah dan kemudian **Segar Semula**.
- **Nama semula** langkah.
- **Aktifkan** atau **Nyahaktifkan**. Langkah tidak aktif tidak akan dapat disegar semula semasa [segar semula yang dijadualkan](system.md#schedule-tab).
- **Tag** untuk [menguruskan tag](work-with-tags-columns.md#manage-tags) untuk segmen.
- **Padam** langkah.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Langkah seterusnya

Anda boleh menggunakan langkah sedia ada untuk mencipta [segmen pelanggan](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
