---
title: Cari pelanggan serupa dengan AI (mengandungi video)
description: Cari segmen pelanggan yang serupa dengan kepintaran buatan.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: de337ae989558c81fff25a6ff7cca01890ed306b
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934851"
---
# <a name="similar-customers-preview"></a>Pelanggan yang serupa (pratonton)

Ciri ini membenarkan anda mencari pelanggan yang serupa dalam asas pelanggan menggunakan kepintaran buatan. Anda perlu mempunyai sekurang-kurangnya satu segmen dicipta untuk menggunakan ciri ini. Mengembangkan kriteria segmen sedia ada membantu mencari pelanggan yang serupa kepada segmen itu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Cari pelanggan yang serupa* menggunakan tujuan automatik untuk menilai data dan membuat ramalan berasaskan pada data itu dan dengan itu mempunyai keupayaan untuk digunakan sebagai kaedah profiling seperti istilah yang ditakrifkan oleh Peraturan Perlindungan Data Umum (“GDPR”). Pelanggan menggunakan ciri ini untuk memproses data berkemungkinan tertakluk pada GDPR atau undang-undang atau peraturan yang lain. Anda bertanggungjawab untuk memastikan bahawa penggunaan Dynamics 365 Customer Insights anda, termasuk ramalan, mematuhi semua undang-undang dan peraturan yang berkaitan, termasuk undang-undang yang berkaitan dengan privasi, data peribadi, data biometrik, perlindungan data dan kerahsiaan komunikasi.

## <a name="finding-similar-customers"></a>Mencari pelanggan yang serupa

1. Dalam Insights khalayak, pergi ke **Segmen** dan pilih segmen yang anda mahu jadikan asas segmen baharu anda. Itu adalah *segmen sumber* anda.

1. Dalam bar tindakan, pilih **Cari pelanggan yang serupa**.

1. Semak nama yang dicadangkan untuk segmen baharu anda dan ubahkannya jika perlu.

1. Semak medan yang menakrifkan segmen baharu anda. Medan ini menakrifkan asas pada sistem yang akan cuba mencari pelanggan yang serupa ke segmen sumber anda. Sistem akan memilih medan yang disyorkan secara lalai.
  Medan yang boleh mengurangkan prestasi model dengan ketara dikecualikan secara automatik:
  
   - Medan dengan jenis data berikut: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Medan dengan kekardinalan (bilangan elemen dalam medan) kurang daripada 2 atau lebih daripada 30

1. Pilih jika anda mahu memasukkan **Semua pelanggan** atau hanya pelanggan dalam **Segmen sedia ada tertentu** dalam segmen baharu anda.

1. Kecualikan pelanggan dalam segmen sumber anda dengan memilih kotak semak **Kecualikan semua dalam segmen sumber**.

1. Sistem mencadangkan masukkan hanya 20% saiz khalayak sasaran dalam output anda. Edit ambang bila diperlukan. Meningkatkan ambang akan mengurangkan ketepatan.

1. Pilih **Jalankan** pada bahagian bawah halaman untuk memulakan tugas pengelasan perduaan (kaedah pembelajaran mesin) yang menganalisis set data.

## <a name="view-the-similar-segment"></a>Lihat segmen yang serupa

Selepas memproses segmen yang serupa, anda akan menemui segmen baharu disenaraikan pada halaman **Segmen**.

> [!div class="mx-imgBorder"]
> ![Segmen pelanggan yang serupa.](media/expanded-segment.png "Segmen pelanggan yang serupa")

Pilih **Pandangan** dalam bar tindakan untuk membuka butiran segmen. Pandangan ini mengandungi maklumat tentang pengedaran merentas [skor persamaan](#about-similarity-scores). Anda juga menemui nilai skor persamaan dalam **Pratonton ahli segment**.

## <a name="use-the-output-of-a-similar-segment"></a>Gunakan output segmen yang serupa

Anda boleh [bekerja dengan output segmen yang serupa](segments.md) seperti yang anda lakukan dengan segmen lain. Contohnya, eksport segmen atau bina ukuran.

## <a name="refresh-and-edit-a-similar-segment"></a>Segar semula dan edit segmen yang serupa

Untuk menyegar semula segmen yang serupa, pilihnya pada halaman **Segmen** dan pilih **Segar semula** dalam bar tindakan.

Mengedit segmen yang serupa akan memproses semula data anda. Segmen yang dicipta terdahulu dikemas kini dengan data yang disegar semula.    
Untuk mengedit segmen yang serupa, pilihnya pada halaman **Segmen** dan pilih **Edit** dalam bar tindakan. Gunakan perubahan anda dan pilih **Jalankan** untuk memulakan pemprosesan.

## <a name="delete-a-similar-segment"></a>Padam segmen yang serupa

Pilih segmen pada halaman **Segmen** dan pilih **Padam** dalam bar tindakan. Kemudian sahkan pemadaman anda.

## <a name="about-similarity-scores"></a>Tentang skor persamaan

Model pembelajaran mesin pengelasan perduaan memperuntukkan skor kepada pelanggan dalam segmen yang serupa. Skor berasaskan pada persamaan kepada pelanggan dalam segmen sumber.

- Skor persamaan di bawah 0.55 adalah pelanggan yang diklasifikasikan oleh sistem sebagai *tidak serupa* kepada pelanggan dalam segmen sumber
- Skor persamaan antara 0.55 – 0.7 diklasifikasikan sebagai *agak serupa*
- Skor persamaan antara 0.7 – 0.85 diklasifikasikan sebagai *serupa*
- Skor persamaan antara 0.85 – 1 adalah pelanggan yang diklasifikasikan oleh sistem sebagai *sangat serupa*

Pelanggan dengan skor persamaan di bawah 0.4 tidak termasuk dalam output model. Sistem tidak mempertimbangkannya sebagai tidak cukup serupa kepada segmen sumber.


[!INCLUDE[footer-include](../includes/footer-banner.md)]