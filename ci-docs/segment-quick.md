---
title: Buat segmen mudah dengan segmen cepat
description: Buat segmen mudah pelanggan untuk mengumpulkannya berdasarkan pelbagai atribut.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171162"
---
# <a name="create-simple-segments-with-quick-segments"></a>Buat segmen mudah dengan segmen cepat

Segmen pantas membolehkan anda membina segmen ringkas dengan operator tunggal dengan pantas untuk wawasan yang lebih pantas. Segmen pantas hanya disokong dalam persekitaran untuk **pelanggan individu**.

## <a name="create-a-new-segment-with-quick-segments"></a>Cipta segmen baru dengan segmen pantas

1. Pergi ke **Segmen**.

1. Pilih **Cipta Baru** > **daripada**.
   - Pilih pilihan **Profil** untuk membina segmen yang berasaskan pada entiti *pelanggan disatukan*.
   - Pilih pilihan **Ukuran** untuk membina segmen sekitar ukuran yang anda cipta sebelum ini.
   - Pilih pilihan **Kecerdasan** untuk membina segmen di sekitar salah satu entiti output yang dijana anda menggunakan sama ada keupayaan **Ramalan** atau **Model Tersuai**.

1. Dalam kotak dialog **Segmen pantas baharu**, pilih atribut daripada **Medan** juntai bawah. Berdasarkan pilihan anda, sistem ini menyediakan nilai yang berbeza.
   - Untuk medan kategori, 10 kiraan pelanggan teratas dipaparkan. Pilih **Nilai** dan pilih **Semak Semula**.
   - Untuk atribut berangka, sistem menunjukkan nilai atribut yang berada di bawah persentil setiap pelanggan. Pilih **Operator** dan **Nilai**, kemudian pilih **Semak Semula**.

1. Sistem ini menyediakan **saiz segmen Anggaran**. Pilih sama ada untuk menjana segmen yang telah anda tentukan atau kembali untuk memilih medan lain.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nama dan anggaran untuk segmen pantas.":::

1. **Berikan nama** entiti Nama **dan** Output untuk segmen anda. Secara pilihan, tambah [tag](work-with-tags-columns.md#manage-tags).

1. Pilih **Simpan** untuk mencipta bahagian. Halaman **Segmen** dipaparkan.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Langkah-langkah berikutnya

[Eksport segmen](export-destinations.md) dan terokai [penyepaduan Kad Pelanggan](customer-card-add-in.md) untuk menggunakan segmen dalam aplikasi lain.

[!INCLUDE [footer-include](includes/footer-banner.md)]
