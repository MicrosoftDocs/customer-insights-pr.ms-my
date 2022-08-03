---
title: Cari pelanggan yang serupa dengan AI (pratonton) (mengandungi video)
description: Cari segmen pelanggan yang serupa dengan kepintaran buatan.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170738"
---
# <a name="find-similar-customers-with-ai-preview"></a>Cari pelanggan yang serupa dengan AI (pratonton)

Cari pelanggan serupa dalam pangkalan pelanggan anda menggunakan kecerdikan buatan. Anda memerlukan sekurang-kurangnya satu segmen yang dibuat untuk menggunakan ciri ini. Memperluaskan kriteria segmen sedia ada membantu mencari pelanggan yang serupa dengan segmen tersebut.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Cari pelanggan* yang serupa menggunakan cara automatik untuk menilai data dan membuat ramalan berdasarkan data tersebut. Oleh itu, ia mempunyai keupayaan untuk digunakan sebagai kaedah pemprofilan, kerana istilah itu ditakrifkan oleh Peraturan Perlindungan Data Umum ("GDPR"). Pelanggan menggunakan ciri ini untuk memproses data berkemungkinan tertakluk pada GDPR atau undang-undang atau peraturan yang lain. Anda bertanggungjawab untuk memastikan bahawa penggunaan Dynamics 365 Customer Insights anda, termasuk ramalan, mematuhi semua undang-undang dan peraturan yang berkaitan, termasuk undang-undang yang berkaitan dengan privasi, data peribadi, data biometrik, perlindungan data dan kerahsiaan komunikasi.

## <a name="find-similar-customers"></a>Cari pelanggan serupa

1. Pergi ke **Segmen** dan pilih segmen yang anda mahu asaskan segmen baharu anda. Itu adalah *segmen sumber* anda.

1. Pilih **Cari pelanggan yang serupa**.

1. Semak nama yang dicadangkan untuk segmen baharu anda dan ubahkannya jika perlu.

1. Secara pilihan, tambah [tag](work-with-tags-columns.md#manage-tags) ke segmen baru.

1. Semak medan yang menakrifkan segmen baharu anda. Medan ini menakrifkan asas pada sistem yang akan cuba mencari pelanggan yang serupa ke segmen sumber anda. Sistem memilih medan yang disyorkan secara lalai. Jika perlu, tambah lebih banyak medan.
  Medan yang boleh mengurangkan prestasi model dengan ketara dikecualikan secara automatik:
  
   - Medan dengan jenis data berikut: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Medan dengan kekardinalan (bilangan elemen dalam medan) kurang daripada 2 atau lebih daripada 30

1. Pilih jika anda ingin memasukkan **Semua pelanggan** kecuali segmen sumber atau hanya pelanggan dalam segmen **yang** berbeza dalam segmen baharu anda.

1. Sistem mencadangkan masukkan hanya 20% saiz khalayak sasaran dalam output anda. Edit ambang bila diperlukan. Meningkatkan ambang akan mengurangkan ketepatan.

1. Sertakan pelanggan dalam segmen sumber anda dengan **memilih kotak semak Sertakan ahli daripada segmen sumber selain pelanggan dengan atribut yang** serupa.

1. Pilih **Jalankan** di bahagian bawah halaman untuk memulakan [tugas](#about-similarity-scores) klasifikasi binari (kaedah Pembelajaran Mesin) yang menganalisis set data.

## <a name="view-the-similar-segment"></a>Lihat segmen yang serupa

Selepas memproses segmen yang serupa, anda akan menemui segmen baharu yang disenaraikan pada **halaman Segmen** dengan jenis **Pengembangan**.

Pilih **Lihat** untuk melihat taburan hasil merentasi [skor](#about-similarity-scores) persamaan dan nilai skor persamaan di bawah **Pratonton ahli segmen**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segmen pelanggan yang serupa.":::

## <a name="manage-a-similar-segment"></a>Urus segmen yang serupa

[Bekerja dengan dan menguruskan segmen](segments.md#manage-existing-segments) yang serupa seperti yang anda lakukan dengan segmen lain. Contohnya, eksport segmen atau bina ukuran.

Edit, segar semula, namakan semula, muat turun dan padamkan segmen yang serupa. Mengedit segmen yang serupa memproses semula data anda. Segmen yang dicipta terdahulu dikemas kini dengan data yang disegar semula.

## <a name="about-similarity-scores"></a>Tentang skor persamaan

Model pembelajaran mesin pengelasan perduaan memperuntukkan skor kepada pelanggan dalam segmen yang serupa. Skor berasaskan pada persamaan kepada pelanggan dalam segmen sumber.

- Skor persamaan di bawah 0.55 adalah pelanggan yang diklasifikasikan oleh sistem sebagai *tidak serupa* kepada pelanggan dalam segmen sumber
- Skor persamaan antara 0.55 – 0.7 diklasifikasikan sebagai *agak serupa*
- Skor persamaan antara 0.7 – 0.85 diklasifikasikan sebagai *serupa*
- Skor persamaan antara 0.85 – 1 adalah pelanggan yang diklasifikasikan oleh sistem sebagai *sangat serupa*

Pelanggan dengan skor persamaan di bawah 0.4 tidak termasuk dalam output model. Sistem tidak mempertimbangkannya sebagai tidak cukup serupa kepada segmen sumber.

[!INCLUDE [footer-include](includes/footer-banner.md)]
