---
title: Cerapan segmen untuk segmen sedia ada
description: Dapatkan cerapan pada segmen sedia ada untuk melihat perbezaan dan persamaan.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 526b593ba9b038de3d3c27f6a7683ca76b3f2319
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643218"
---
# <a name="segment-insights-preview"></a>Wawasan segmen (pratonton)

Temui maklumat dan wawasan tambahan sekitar segmen sedia ada anda. Ketahui apa yang membezakan dua segmen atau apa persamaan mereka.

## <a name="segment-overlap"></a>Bertindih bahagian

Analisa bertindih segmen menunjukkan bilangan dan pelanggan mana yang biasa dengan dua atau lebih segmen. Contohnya, cara segmen pelanggan yang kerap bertindih dengan segmen yang mengandungi pelanggan yang berpuas hati dengan perkhidmatan atau produk anda.
Anda juga boleh menganalisis cara perubahan bertindih untuk atribut tertentu.

### <a name="run-an-overlap-analysis"></a>Jalankan analisis bertindih

1. Pergi ke **Segmen** dan pilih tab **wawasan (pratonton)**.

1. Pilih **Baharu** dan pilih pilihan **Bertindih** dalam anak tetingkap **Pilih Jenis Wawasan**.

1. Pilih segmen kepentingan dan pilih **Seterusnya**.

1. Secara alternatif, pilih satu atau lebih medan kepentingan untuk menganalisis pertindihan bagi setiap nilai medan yang mungkin dan pilih **Seterusnya**.

1. Berikan nama untuk anda analisis bertindih, nama paparan pilihan dan perihalan.

1. Pilih **Simpan** untuk memulakan analisis. Analisis bertindih sudah bersedia apabila status berubah daripada Menyegar semula kepada Berjaya.

### <a name="view-and-optimize-an-overlap-analysis"></a>Pandangan dan optimumkan analisis bertindih

Selepas melengkapkan analisis, cari butiran mengenai wawasan ini dalam **Segmen** > **Wawasan (pratonton)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Butiran cerapan segmen bertindih.":::

Pilih wawasan untuk melihat hasil analisis:

- Bilangan ahli bertindih segmen yang dipilih untuk analisis.
- Bilangan ahli yang termasuk dalam salah satu segmen tetapi tidak berada dalam segmen yang lain.
- Jika anda memilih medan semasa mengkonfigurasikan analisis bertindih, anda akan dapati mereka dalam tab yang berkaitan. Anda boleh menggunakan penapis juntai bawah untuk memilih mana-mana tahap atribut kepentingan dan jadual di bahagian bawah akan menunjukkan data yang sepadan.

## <a name="segment-differentiators"></a>Pembezaan bahagian

Pembezaan segmen membantu anda ketahui apa yang membezakan segmen daripada seluruh pelanggan anda atau daripada segmen lain. Anda hanya perlu memilih segmen dan sistem akan mengenal pasti atribut dan langkah profil yang membezakan segmen yang dipilih.

### <a name="run-a-differentiator-analysis"></a>Jalankan analisis pembezaan

1. Pergi ke **Segmen** dan pilih tab **wawasan (pratonton)**.

1. Pilih **Baharu** dan pilih pilihan **Bertindih** dalam anak tetingkap **Pilih Jenis Wawasan**.

1. Pilih segmen yang anda mahu analisis sebagai **Segmen utama** dan pilih **Seterusnya**.

1. Pilih **Semua pelanggan** atau **Segmen kedua** untuk membandingkan dengan segmen utama anda dan pilih **Seterusnya**.

1. Secara alternatif, pilih satu atau lebih medan kepentingan untuk fokus analisis pada atribut tertentu dan pilih **Seterusnya**.

1. Berikan nama untuk anda analisis bertindih, nama paparan pilihan dan perihalan.

1. Pilih **Simpan** untuk memulakan analisis. Analisis bertindih sudah bersedia apabila status berubah daripada Menyegar semula kepada Berjaya.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Pandangan dan optimumkan analisis pembezaan

Selepas melengkapkan analisis, cari butiran mengenai wawasan ini dalam **Segmen** > **Wawasan (pratonton)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Butiran cerapan pembeza segmen.":::

Pilih wawasan untuk melihat hasil analisis. Analisis pembezaan termasuk dua tab. Tab **Atribut** menyenaraikan atribut profil dianggap sebagai pembezaan. Tab **Langkah** menyenaraikan pembezaan. Setiap tab merangkumi butiran berikut:

- Kedudukan senarai pembezaan, diisih oleh skor perbezaan.
- **Skor perbezaan** untuk setiap pembezaan. Skor perbezaan mewakili darjah perbezaan atribut antara dua segmen. Semakin tinggi skor perbezaan, lebih banyak atribut berbeza antara kedua-dua segmen. Pilih skor untuk membuka anak tetingkap **Skor perbezaan** dengan pengagihan nilai untuk atribut tersebut.

## <a name="manage-segment-insights"></a>Uruskan wawasan segmen

Anda boleh menggunakan pilihan berikut pada wawasan anda daripada bar perintah:

- **Kembali** untuk mengembalikan senarai wawasan
- **Segar semula** untuk menjalankan analisis sekali lagi
- **Padam** untuk alih keluar wawasan ini


[!INCLUDE [footer-include](includes/footer-banner.md)]