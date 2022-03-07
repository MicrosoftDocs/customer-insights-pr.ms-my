---
title: Buat langkah-langkah dari templat
description: Tentukan langkah menggunakan templat untuk kes penggunaan biasa.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 0fe846691825b93732cbbe6d1c942a79e4a3934f
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359961"
---
# <a name="use-a-template-to-build-a-measure"></a>Gunakan templat untuk membina langkah

Anda boleh menggunakan templat yang telah dipratentkan langkah [yang biasa digunakan](measures.md) untuk menciptanya. Penerangan terperinci mengenai templat dan pengalaman berpandu membantu anda dengan penciptaan langkah yang cekap. Templat dibina pada data yang dipetakan daripada entit *Aktiviti Disatukan*. Oleh itu, pastikan anda telah mengkonfigurasikan [aktiviti pelanggan](activities.md) sebelum anda mencipta langkah daripada templat.

Untuk mencipta langkah tersuai, lihat [Gunakan pembina ukuran untuk mencipta ukuran dari awal](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

Templat langkah yang tersedia: 
- Purata nilai transaksi (ATV)
- Jumlah nilai transaksi
- Purata hasil harian
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

1. Dalam anak tetingkap **Edit nama**, tetapkan nama untuk langkah anda dan entiti output. 

1. Pilih **Selesai**.

1. Dalam bahagian **Tetapkan tempoh masa**, takrifkan tempoh masa data untuk digunakan. Pilih jika anda mahu ukuran baharu untuk merangkumi keseluruhan set data dengan memilih **Sepanjang masa**, atau jika anda mahu ukuran itu memberikan tumpuan kepada **Tempoh masa tertentu**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Tangkapan skrin menunjukkan bahagian tempoh masa apabila mengkonfigurasikan langkah daripada templat.":::

1. Dalam bahagian seterusnya, pilih **Tambah data** untuk memilih aktiviti dan memetakan data yang sepadan daripada entiti *Aktiviti Disatukan* anda.

    1. Langkah 1 daripada 2: Di bawah **Jenis aktiviti**, pilih jenis entiti yang anda mahu gunakan. Untuk **Aktiviti**, pilih entiti yang anda mahu petakan.
    1. Langkah 2 daripada 2: Pilih atribut daripada entiti *Aktiviti Disatukan* untuk komponen yang diperlukan oleh formula. Contohnya, untuk nilai transaksi Purata, ia merupakan atribut yang mewakili nilai Transaksi. Untuk **Cap waktu aktiviti**, pilih atribut daripada entiti Aktiviti Disatukan yang mewakili tarikh dan masa aktiviti.
   
1. Sebaik sahaja pemetaan data berjaya, anda boleh melihat status sebagai **Lengkap** dan nama aktiviti dan atribut yang dipetakan.

1. Anda kini boleh memilih **Jalankan** untuk mengira keputusan ukuran. Untuk memperhalusi kemudian, pilih **Simpan draf**.

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

Ciri ini hanya tersedia untuk ukuran yang dicipta dalam persekitaran dengan pelanggan individu sebagai khalayak sasaran utama.

---
