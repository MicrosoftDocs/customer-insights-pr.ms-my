---
title: Hubungan antara entiti dan laluan entiti
description: Cipta dan urus hubungan antara entiti daripada berbilang sumber data.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406480"
---
# <a name="relationships-between-entities"></a>Perhubungan antara entiti

Perhubungan membantu anda connect entiti dan menjana graf data apabila entiti berkongsi pengecam lazim (kekunci asing) yang boleh menjadi rujukan daripada satu entiti ke entiti yang lain. Entiti yang bersambung membolehkan anda menakrif bahagian dan ukuran berasaskan pada berbilang sumber data.

Terdapat dua jenis perhubungan. Perhubungan sistem tidak boleh diedit, yang dicipta secara automatik, dan perhubungan tersuai yang dicipta dan dikonfigurasikan oleh pengguna.

Semasa proses padan dan gabung, perhubungan sistem dicipta di belakang tabir berasaskan pada pemadanan pintar. Perhubungan ini membantu mengaitkan rekod Profil Pelanggan dengan rekod entiti lain yang sepadan. Diagram berikut menerangkan penciptaan tiga perhubungan sistem apabila entiti pelanggan sepadan dengan entiti tambahan untuk mengeluarkan entiti Profil Pelanggan akhir.

> [!div class="mx-imgBorder"]
> ![Penciptaan perhubungan](media/relationships-entities-merge.png "Penciptaan perhubungan")

- **Perhubungan *CustomerToContact*** dicipta antara entiti Pelanggan dan entiti Kenalan. Entiti Pelanggan memperoleh medan kekunci **Contact_contactId** untuk mengaitkan dengan medan kekunci entiti Kenalan **contactId**.
- **Perhubungan _CustomerToAccount_** dicipta antara entiti Pelanggan dengan entiti Akaun. Entiti Pelanggan memperoleh medan kekunci **Account_accountId** untuk mengaitkan dengan medan kekunci entiti Akaun **accountId**.
- **Perhubungan _CustomerToWebAccount_** dicipta antara entiti Pelanggan dengan entiti WebAccount. Entiti Pelanggan memperoleh medan kekunci **WebAccount_webaccountId** untuk mengaitkan dengan medan kekunci entiti WebAccount **webaccountId**.

## <a name="create-a-relationship"></a>Cipta perhubungan

Takrif perhubungan tersuai pada halaman **Perhubungan**. Setiap perhubungan mengandungi entiti Sumber (entiti yang memegang kekunci asing) dan entiti Sasaran (entiti yang kekunci asing bagi entiti sumber dirujuk).

1. Dalam wawasan khalayak, pergi ke **Data** > **Hubungan**.

2. Pilih **Perhubungan baharu**.

3. Dalam anak tetingkap **Tambah perhubungan**, berikan maklumat berikut:

   > [!div class="mx-imgBorder"]
   > ![Masukkan butiran perhubungan](media/relationships-add.png "Masukkan butiran perhubungan")

   - **Nama perhubungan**: Nama yang menggambarkan tujuan perhubungan (contohnya, **AccountWebLogs**).
   - **Description**: Description bagi perhubungan.
   - **Entiti Sumber**: Pilih entiti yang digunakan sebagai sumber dalam perhubungan (contohnya, WebLog).
   - **Kekardinalan**: Pilih kekardinalan bagi rekod entiti sumber. Contohnya, “banyak” bermaksud rekod Weblog berbilang berkait dengan satu WebAccount.
   - **Medan kekunci sumber**: Ini mewakili medan kekunci asing dalam entiti sumber. Contohnya, WebLog mempunyai medan kekunci asing **accountId**.
   - **Entiti sasaran**: Pilih entiti yang digunakan sebagai sasaran dalam perhubungan (contohnya, WebAccount).
   - **Kekardinalan sasaran**: Pilih kekardinalan rekod entiti sasaran. Contohnya, “satu” bermaksud rekod Weblog berbilang berkait dengan satu WebAccount.
   - **Medan kekunci sasaran**: Medan ini mewakili medan kekunci bagi entiti sasaran. Contohnya, WebAccount mempunyai medan kekunci **accountId**.

> [!NOTE]
> Hanya perhubungan banyak-ke-satu dan satu-ke-satu disokong. Perhubungan banyak-ke-banyak boleh dicipta menggunakan dua perhubungan banyak-ke-satu dan entiti pautan (entiti yang digunakan untuk connect entiti sumber dan entiti sasaran).

## <a name="delete-a-relationship"></a>Memadam perhubungan

1. Dalam wawasan khalayak, pergi ke **Data** > **Hubungan**.

2. Pilih kotak semak untuk perhubungan yang anda mahu padam.

3. Pilih **Padam** pada bahagian atas jadual **Perhubungan**.

4. Sahkan pemadaman anda.

## <a name="next-step"></a>Langkah seterusnya

Perhubungan sistem dan tersuai digunakan untuk mencipta bahagian berasaskan berbilang sumber data yang tidak lagi silo. Untuk maklumat lanjut, lihat [Bahagian](segments.md).
