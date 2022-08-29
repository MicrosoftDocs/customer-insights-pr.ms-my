---
title: Cipta pandangan disatukan bagi pelanggan anda
description: Lalui proses penyatuan data dengan data anda untuk membuat set data induk tunggal akaun atau profil pelanggan.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304438"
---
# <a name="data-unification-overview"></a>Gambaran keseluruhan penyatuan data

Selepas [menyediakan sumber data](data-sources.md), anda boleh menyatukan data. Penyatuan data membolehkan anda menyatukan sumber data sekali berbeza ke dalam set data induk tunggal yang menyediakan pandangan bersatu data tersebut.

Bagi pengguna individu (B-to-C) di mana data berpusat di sekeliling individu, penyatuan memberikan pandangan bersatu pelanggan anda. Untuk akaun perniagaan (B-to-B) di mana data berpusat di sekitar akaun, penyatuan memberikan pandangan bersatu akaun anda. [Penyatuan kenalan (pratonton)](data-unification-contacts.md) membolehkan kenalan untuk akaun tersebut disatukan secara berasingan dan dikaitkan dengan akaun.

Data boleh disatukan pada entiti tunggal atau berbilang entiti.

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

Proses penyatuan memetakan data pelanggan daripada sumber data anda, mengalih keluar pendua, sepadan dengan data merentas entiti dan mencipta profil bersatu. Penyatuan dilakukan mengikut susunan berikut:

1. [Medan sumber](map-entities.md) (sebelum ini dipanggil Peta): Dalam medan sumber langkah, pilih entiti dan medan untuk dimasukkan dalam proses penyatuan. Petakan medan kepada jenis semantik biasa yang menerangkan tujuan medan.

1. [Rekod](remove-duplicates.md) pendua (sebelum ini sebahagian daripada Padanan): Dalam langkah rekod pendua, secara pilihan menentukan peraturan untuk mengalih keluar rekod pelanggan pendua dari dalam setiap entiti.

1. [Syarat](match-entities.md) yang sepadan (sebelum ini dipanggil Padanan): Dalam langkah keadaan yang sepadan, tentukan peraturan yang sepadan dengan rekod pelanggan antara entiti. Apabila pelanggan ditemui dalam dua atau lebih entiti, satu rekod disatukan dicipta dengan semua lajur dan data daripada setiap entiti.

1. [Medan](merge-entities.md) pelanggan bersepadu (sebelum ini dipanggil Gabung): Dalam bidang pelanggan bersatu langkah, tentukan medan sumber mana yang harus disertakan, dikecualikan atau digabungkan ke dalam profil pelanggan bersatu.  

1. [Semak](review-unification.md) dan buat profil bersatu.

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

Proses penyatuan memetakan data akaun daripada sumber data anda, mengalih keluar pendua, sepadan dengan data merentas entiti dan mencipta profil bersatu. Penyatuan dilakukan mengikut susunan berikut:

1. [Medan sumber](map-entities.md) (sebelum ini dipanggil Peta): Dalam medan sumber langkah, pilih entiti dan medan untuk dimasukkan dalam proses penyatuan akaun. Petakan medan kepada jenis semantik biasa yang menerangkan tujuan medan.

1. [Rekod](remove-duplicates.md) pendua (sebelum ini sebahagian daripada Padanan): Dalam langkah rekod pendua, secara pilihan menentukan peraturan untuk mengalih keluar rekod akaun pendua dari dalam setiap entiti.

1. [Syarat yang sepadan](match-entities.md) (sebelum ini dipanggil Padanan): Dalam langkah syarat yang sepadan, takrifkan peraturan yang sepadan dengan rekod akaun antara entiti. Apabila akaun ditemui dalam dua atau lebih entiti, satu rekod disatukan dicipta dengan semua lajur dan data daripada setiap entiti.

1. [Medan](merge-entities.md) pelanggan bersepadu (sebelum ini dipanggil Gabung): Dalam bidang pelanggan bersatu langkah, tentukan medan sumber mana yang harus disertakan, dikecualikan atau digabungkan ke dalam profil pelanggan bersatu.  

1. [Semak](review-unification.md) dan buat profil bersatu.

Selepas menyatukan akaun, anda boleh menyatukan kenalan (pratonton) [secara](data-unification-contacts.md) pilihan untuk akaun tersebut dan memautkan kenalan bersatu ke akaun disatukan.

---

Selepas melengkapkan penyatuan data, anda boleh secara pilihan:

- [Sediakan hubungan antara entiti](relationships.md) untuk mewujudkan segmen yang canggih.
- [Memperkayakan data](enrichment-hub.md) anda untuk mendapatkan pelbagai cerapan tentang pelanggan anda.
- [Tentukan aktiviti](activities.md) dari beberapa atribut yang ditelan.
- [Membina langkah-langkah](measures.md) untuk lebih memahami tingkah laku pelanggan dan prestasi perniagaan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
