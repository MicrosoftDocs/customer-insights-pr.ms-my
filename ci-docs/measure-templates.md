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
ms.openlocfilehash: f6bcdfc45a49c36f22d6ebc6e919f43b27f899d8
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051694"
---
# <a name="create-measures-from-templates"></a>Cipta langkah daripada templat

Anda boleh menggunakan templat yang dipratentukan langkah-langkah [yang biasa digunakan](measures.md) untuk menciptanya. Penerangan terperinci mengenai templat dan pengalaman berpandu membantu anda dengan penciptaan langkah yang cekap. Templat dibina pada data yang dipetakan daripada entit *Aktiviti Disatukan*. Oleh itu, pastikan anda telah mengkonfigurasikan [aktiviti pelanggan](activities.md) sebelum anda mencipta langkah daripada templat.

Untuk mencipta langkah tersuai, lihat [Gunakan pembina ukuran untuk mencipta langkah dari awal](measure-builder.md).

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

1. Pilih **Edit butiran** di sebelah Ukur nama. Berikan nama untuk ukuran itu. Secara pilihan, tambah [tag](work-with-tags-columns.md#manage-tags) pada ukuran.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Kotak dialog Edit butiran butiran.":::

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
