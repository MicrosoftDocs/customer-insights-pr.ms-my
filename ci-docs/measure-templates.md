---
title: Cipta langkah daripada templat
description: Tentukan langkah menggunakan templat untuk kes penggunaan biasa.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170784"
---
# <a name="create-measures-from-templates"></a>Cipta langkah daripada templat

Gunakan templat yang dipratentukan bagi langkah-langkah [yang biasa digunakan](measures.md) untuk menciptanya. Templat dibina pada data yang dipetakan daripada entit *Aktiviti Disatukan*. Oleh itu, pastikan anda telah mengkonfigurasikan [aktiviti pelanggan](activities.md) sebelum anda mencipta langkah daripada templat.

Templat ukuran hanya disokong dalam persekitaran untuk **pelanggan individu**. Untuk mencipta langkah tersuai atau mencipta langkah untuk B-ke-B, lihat [Gunakan pembina ukuran](measure-builder.md).

Templat langkah yang tersedia:
- Purata nilai transaksi (ATV)
- Jumlah nilai transaksi
- Purata hasil harian
- Purata hasil bulanan
- Purata hasil tahunan
- Kiraan transaksi
- Mata kesetiaan diperoleh
- Mata kesetiaan ditebus
- Baki mata kesetiaan
- Jangka hayat pelanggan aktif
- Tempoh keahlian kesetiaan
- Masa sejak pembelian terakhir

## <a name="build-a-new-measure-using-a-template"></a>Bina ukuran baru menggunakan templat

1. Pergi ke **Langkah-langkah**.

1. Pilih **Baharu** dan pilih **Pilih templat**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Syot layar menu juntai bawah apabila mencipta ukuran baharu dengan serlahkan pada templat.":::

1. Cari templat yang sesuai dengan keperluan anda dan pilih **Pilih templat**.

1. Semak data yang diperlukan dan pilih **Mari bermula** jika anda mempunyai semua data di tempatnya.

1. Pilih **Edit butiran** di sebelah Ukur nama. Berikan nama untuk ukuran itu. Secara pilihan, tambah [tag](work-with-tags-columns.md#manage-tags) pada ukuran.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Kotak dialog Edit butiran butiran.":::

1. Pilih **Selesai**.

1. **Dalam seksyen Tetapkan tempoh** masa, tentukan rangka masa data. Pilih jika anda mahu ukuran baharu untuk merangkumi keseluruhan set data dengan memilih **Sepanjang masa**, atau jika anda mahu ukuran itu memberikan tumpuan kepada **Tempoh masa tertentu**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Tangkapan skrin menunjukkan bahagian tempoh masa apabila mengkonfigurasikan langkah daripada templat.":::

1. Dalam bahagian seterusnya, pilih **Tambah data** untuk memilih aktiviti dan memetakan data yang sepadan daripada entiti *Aktiviti Disatukan* anda.

    1. Langkah 1 daripada 2: Di bawah **Jenis aktiviti**, pilih jenis entiti yang anda mahu gunakan. Untuk **Aktiviti**, pilih entiti yang anda ingin petakan, kemudian pilih **Berikut**.
    1. Langkah 2 daripada 2: Pilih atribut daripada entiti *Aktiviti Disatukan* untuk komponen yang diperlukan oleh formula. Contohnya, untuk nilai transaksi Purata, ia merupakan atribut yang mewakili nilai Transaksi. Untuk **Cap masa** Aktiviti, pilih atribut daripada *entiti Aktiviti* Disatukan yang mewakili tarikh dan masa aktiviti.
    1. Pilih **Simpan**.

    Apabila pemetaan data berjaya, status menunjukkan **Lengkap** dan nama aktiviti dan atribut yang dipetakan dipaparkan.

1. Pilih **Jalankan** untuk mengira hasil ukuran. Pilih **Simpan draf** jika anda ingin mengekalkan konfigurasi semasa dan jalankan ukuran kemudian. Halaman **Langkah** dipaparkan.

## <a name="next-step"></a>Langkah seterusnya

Gunakan langkah sedia ada untuk mencipta [segmen](segments.md) pelanggan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
