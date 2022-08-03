---
title: Gambaran keseluruhan penyatuan data
description: Melalui proses penyatuan data dengan data anda untuk mencipta satu set data profil pelanggan bersatu.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139512"
---
# <a name="data-unification-overview"></a>Gambaran keseluruhan penyatuan data

Selepas [menyediakan sumber data](data-sources.md), anda boleh menyatukan data. Penyatuan data membolehkan anda menyatukan sumber data sekali berbeza ke dalam set data induk tunggal yang menyediakan pandangan bersatu data tersebut. Bagi pengguna individu (B-to-C) di mana data berpusat pada individu, penyatuan memberikan pandangan bersatu pelanggan anda. Untuk akaun perniagaan (B-to-B) di mana data berpusat di sekitar akaun, penyatuan menyediakan paparan disatukan akaun anda.

Data boleh disatukan pada satu entiti atau berbilang entiti. Penyatuan dilakukan mengikut urutan berikut:

1. [Medan sumber](map-entities.md) (sebelum ini dipanggil Peta): Dalam langkah medan sumber, pilih entiti dan medan untuk disertakan dalam proses penyatuan. Peta medan ke jenis semantik biasa yang menerangkan tujuan medan.

1. [Rekod](remove-duplicates.md) pendua (sebelum ini sebahagian daripada Padanan): Dalam langkah rekod pendua, tentukan peraturan secara pilihan untuk mengalih keluar rekod pelanggan pendua dari dalam setiap entiti.

1. [Keadaan](match-entities.md) pemadanan (sebelum ini dipanggil Padanan): Dalam langkah keadaan yang sepadan, tentukan peraturan yang sepadan dengan rekod pelanggan antara entiti. Apabila pelanggan ditemui dalam dua atau lebih entiti, satu rekod yang disatukan dicipta dengan semua lajur dan data daripada setiap entiti.

1. [Medan pelanggan](merge-entities.md) disatukan (sebelum ini dipanggil Cantum): Dalam langkah medan pelanggan bersatu, tentukan medan sumber yang harus disertakan, dikecualikan atau digabungkan menjadi profil pelanggan yang bersatu.  

1. [Semak](review-unification.md) dan buat profil bersatu.

Selepas melengkapkan penyatuan data, anda boleh memilih:

- [Sediakan hubungan antara entiti](relationships.md) untuk mencipta segmen yang canggih.
- [Memperkayakan data](enrichment-hub.md) anda untuk mendapatkan pelbagai cerapan yang lebih luas tentang pelanggan anda.
- [Tentukan aktiviti](activities.md) dari beberapa atribut yang ditelan.
- [Bina langkah-langkah](measures.md) untuk lebih memahami tingkah laku pelanggan dan prestasi perniagaan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
