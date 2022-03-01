---
title: Cipta dan edit ukuran
description: Takrif ukuran berkaitan pelanggan untuk menganalisis dan menunjukkan prestasi bagi beberapa bidang perniagaan.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406477"
---
# <a name="define-and-manage-measures"></a>Takrifkan dan urus tindakan

**Ukuran** mewakili penunjuk prestasi utama (KPIs) yang menunjukkan prestasi dan kesihatan bagi bidang perniagaan tertentu. Wawasan khalayak memberikan pengalaman intuitif untuk membina pelbagai jenis langkah, menggunakan pembina pertanyaan yang tidak memerlukan anda untuk kod atau mengesahkan langkah anda secara manual. Anda boleh menjejak ukuran perniagaan anda pada halaman **Laman Utama**, lihat ukuran untuk pelanggan tertentu pada **Kad Pelanggan**, dan guna ukuran untuk menakrifkan bahagian pada halaman **Bahagian**.

## <a name="create-a-measure"></a>Cipta ukuran

Bahagian ini membimbing anda mencipta ukuran daripada awal. Anda boleh membina ukuran dengan data daripada berbilang sumber data yang disambungkan melalui entiti Pelanggan. Sesetengah [had perkhidmatan](service-limits.md) diguna pakai.

1. Dalam wawasan khalayak, pergi ke **Ukuran**.

2. Pilih **Ukuran baharu**.

3. Pilih ukuran **Jenis**:

   - **Atribut Pelanggan**: Medan tunggal bagi setiap pelanggan yang menunjukkan skor, nilai, atau keadaan bagi pelanggan. Atribut pelanggan dicipta sebagai atribut dalam entiti dijana sistem dipanggil **Ukuran_Pelanggan**.

   - **Ukuran pelanggan**: Wawasan pada tingkah laku pelanggan dengan pecahan mengikut dimensi terpilih. Entiti baharu dijana untuk setiap ukuran, berpotensi dengan berbilang rekod bagi setiap pelanggan.

   - **Ukuran perniagaan**: Jejak prestasi dan kesihatan perniagaan anda. Ukuran perniagaan boleh mempunyai dua output yang berbeza: output numerik yang ditunjukkan pada halaman **Laman Utama** atau entiti baharu yang anda temui pada halaman **Entiti**.

4. Berikan **Nama** dan **Nama paparan** optional, kemudian pilih **Seterusnya**.

5. Pada bahagian **Entiti**, pilih entiti pertama daripada senarai juntai bawah. Pada peringkat ini, Anda perlu membuat keputusan sama ada memerlukan entiti tambahan sebagai sebahagian definisi ukuran anda.

   > [!div class="mx-imgBorder"]
   > ![Definisi ukuran](media/measure-definition.png "Definisi langkah")

   Untuk menambah lebih banyak entiti, pilih **Tambah entiti** dan pilih entiti yang anda mahu gunakan untuk ukuran.

   > [!NOTE]
   > Anda hanya boleh memilih entiti yang mempunyai hubungan dengan entiti permulaan anda. Untuk maklumat lanjut tentang menakrif perhubungan, lihat [Perhubungan](relationships.md).

6. Secara pilihan, anda boleh mengkonfigurasikan pemboleh ubah. Dalam bahagian **Pemboleh ubah**, pilih **Pemboleh ubah baharu**.

   Pemboleh ubah adalah pengiraan yang dibuat pada setiap rekod pilihan anda. Contohnya, menambah mata jualan (POS) dan jualan dalam talian untuk setiap rekod pelanggan anda.

7. Berikan **Nama** untuk pemboleh ubah.

8. Dalam kawasan **Ungkapan**, pilih medan untuk memulakan pengiraan anda.

9. Taip ungkapan dalam kawasan **Ungkapan** semasa memilih lebih banyak medan untuk dimasukkan dalam pengiraan.

   > [!NOTE]
   > Pada masa ini, hanya ungkapan yang aritmetik disokong. Selain itu, pengiraan pemboleh ubah tidak menyokong entiti daripada [laluan entiti](relationships.md) yang berbeza.

10. Pilih **Selesai**.

11. Dalam bahagian **Definisi ukuran**, anda akan menakrif bagaimana entiti yang dipilih dan pemboleh ubah dikira diagregat dalam entiti ukuran atau atribut baharu.

12. Pilih **Dimensi baharu**. Anda boleh memikirkan dimensi sebagai fungsi *himpun mengikut*. Output data untuk entiti atau atribut Ukuran anda akan dihimpun mengikut semua dimensi yang ditakrif oleh anda.

    > [!div class="mx-imgBorder"]
    > ![Pilih kitaran agregat](media/measures-businessreport-measure-definition2.png "Pilih kitaran agregat")

    Pilih atau masukkan maklumat berikut sebagai sebahagian definisi dimensi anda:

    - **Entiti**: Jika anda menakrif entiti Ukuran, ia hendaklah memasukkan sekurang-kurangnya satu atribut. Jika anda menakrifkan atribut Ukuran, ia hendaklah memasukkan sekurang-kurangnya satu atribut secara lalai. Pemilihan ini adalah tentang memilih entiti yang memasukkan atribut itu.
    - **Medan**: Pilih atribut tertentu untuk dimasukkan sama ada dalam entiti atau atribut Ukuran anda.
    - **Baldi**: Pilih sama ada anda mahu mengumpulkan data secara harian, bulanan, atau tahunan. Ia adalah pilihan yang diperlukan hanya jika anda telah memilih atribut jenis Tarikh.
    - **Sebagai**: Takrifkan nama medan baharu anda.
    - **Nama paparan**: Takrifkan nama paparan medan anda.

    > [!NOTE]
    > Ukuran perniagaan anda akan disimpan sebagai entiti nombor tunggal dan akan dipaparkan pada halaman **Laman Utama** melainkan anda menambah lebih banyak dimensi pada ukuran anda. Selepas menambah lebih banyak dimensi, ukuran *tidak* akan ditunjukkan pada halaman **Laman Utama**.

13. Secara pilihan, tambah fungsi pengagregatan. Sebarang pengagregatan yang anda cipta hasilnya dalam nilai baharu antara entiti atau atribut Ukuran anda. Fungsi pengagregatan yang disokong ialah: **Minimum**, **Maksimum**, **Purata**, **Median**, **Jumlah**, **Unik Kiraan**, **Pertama** (mengambil rekod pertama bagi nilai dimensi), dan **Akhir** (mengambil kira rekod terakhir ditambah pada nilai dimensi).

14. Pilih **Simpan** untuk menggunakan perubahan anda pada ukuran.

## <a name="manage-your-measures"></a>Urus tindakan anda

Selepas mencipta sekurang-kurangnya satu ukuran, anda akan melihat senarai ukuran pada halaman **Langkah**.

Anda akan menemui maklumat tentang jenis ukuran, pencipta, tarikh dan masa penciptaan, tarikh dan masa edit terakhir, status (sama ada ukuran aktif, tidak aktif, atau gagal), dan tarikh dan masa penyegaran semula terakhir. Apabila anda memilih tindakan daripada senarai, anda boleh melihat pratonton output.

Untuk menyegarkan semula semua tindakan pada masa yang sama, pilih **Segar semula semua** tanpa memilih tindakan khusus.

> [!div class="mx-imgBorder"]
> ![Tindakan untuk mengurus langkah tunggal](media/measure-actions.png "Tindakan untuk mengurus langkah tunggal")

Secara alternatif, pilih tindakan daripada senarai dan lakukan salah satu daripada tindakan berikut:

- Pilih nama langkah untuk melihat butiran.
- **Edit** konfigurasi langkah.
- **Nama semula** langkah.
- **Padam** langkah.
- Pilih elipsis (...) dan kemudian **Segar semula** untuk memulakan proses segar semula untuk tindakan.
- Pilih elipsis (...) dan kemudian **Muat turun** untuk mendapatkan Fail .CSV tindakan.

> [!TIP]
> Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies). Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja. Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.

## <a name="next-step"></a>Langkah seterusnya

Anda boleh menggunakan ukuran sedia ada untuk mencipta bahagian pelanggan pertama pada halaman **Bahagian**. Untuk maklumat lanjut, lihat [Bahagian](segments.md).
