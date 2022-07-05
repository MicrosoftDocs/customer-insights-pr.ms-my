---
title: Buat langkah-langkah baru dengan pembina ukuran
description: Bina langkah dari awal untuk menganalisis metrik utama tentang perniagaan anda.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: f3ec86806074a12c1107648303ed2d65e97ebc69
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083021"
---
# <a name="create-new-measures-with-the-measure-builder"></a>Buat langkah-langkah baru dengan pembina ukuran

Artikel ini menerangkan cara membuat ukuran [baru](measures.md) dari awal. Pembina ukuran membolehkan anda menentukan pengiraan menggunakan operator matematik, fungsi pengagregatan, dan penapis. Anda boleh membina ukuran dengan atribut daripada entiti yang berkaitan dengan entiti Pelanggan *bersatu*.

Mewujudkan langkah-langkah dalam persekitaran B-to-C dan B-to-B berfungsi dengan cara yang sama. Walau bagaimanapun, jika persekitaran [B-ke-B menggunakan akaun dengan hierarki](relationships.md#set-up-account-hierarchies), anda boleh memilih untuk mengagregatkan ukuran tersebut merentas sub-akaun yang berkaitan.

Anda juga boleh membuat ukuran dengan cepat dengan memilih daripada satu set langkah yang biasa digunakan dan dipratentukan. Untuk maklumat lanjut, lihat [Menggunakan templat untuk membina ukuran](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

Anda boleh membuat langkah-langkah pada tahap pelanggan individu (atribut pelanggan, ukuran pelanggan) atau pada tahap perniagaan / organisasi (ukuran perniagaan). Atribut pelanggan dan ukuran pelanggan adalah dua jenis yang membolehkan anda mengesan prestasi setiap pelanggan. Sebagai contoh, jumlah perbelanjaan oleh setiap pelanggan. Langkah-langkah perniagaan membolehkan anda mengesan prestasi setiap perniagaan. Sebagai contoh, jumlah pendapatan oleh syarikat.

- Atribut pelanggan: Menjana output sebagai atribut baru, yang disimpan sebagai lajur baru dalam entiti yang dijana sistem bernama *Customer_Measure*. Apabila menyegarkan atribut pelanggan, semua atribut pelanggan lain dalam *entiti Customer_Measure* menyegarkan semula secara serentak. Di samping itu, atribut pelanggan ditunjukkan dalam kad profil pelanggan. Setelah dijalankan atau disimpan, atribut pelanggan anda tidak boleh mengubahnya kepada ukuran pelanggan.

- Ukuran pelanggan: Menjana output sebagai entitinya sendiri dan anda tidak boleh mengubahnya kepada atribut pelanggan sebaik sahaja dijalankan atau disimpan. Langkah-langkah pelanggan tidak dipaparkan dalam kad profil pelanggan.

- Langkah perniagaan: Menjana output sebagai entitinya sendiri dan dipaparkan pada halaman utama persekitaran Wawasan Pelanggan anda.

1. Pergi ke **Langkah-langkah**.

1. Pilih **Baharu** dan pilih **Bina yang anda sendiri**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Skrin konfigurasi kosong untuk ukuran B-ke-C." lightbox="media/measure-b2c.png":::

1. Untuk menjejak prestasi peringkat perniagaan, togol **jenis** Ukur kepada **tahap** Perniagaan. **Aras pelanggan** dipilih secara lalai. **Tahap pelanggan** menambah *atribut CustomerId* secara automatik pada Dimensi manakala **tahap** Perniagaan mengalih keluarnya secara automatik.

1. Dalam kawasan konfigurasi, pilih fungsi pengagregatan daripada **menu juntai bawah Pilih fungsi**. Fungsi pengagregatan termasuk:
   - **Sum**
   - **Purata**
   - **Bilangan**
   - **Kira Unik**
   - **Maksimum**
   - **Min**
   - **Pertama**: mengambil kira nilai pertama bagi rekod data
   - **Terakhir**: ambil nilai terakhir yang ditambah ke rekod data
   - **ArgMax**: mencari rekod data yang memberikan nilai maksimum dari fungsi sasaran
   - **ArgMin**: mencari rekod data yang memberikan nilai minimum daripada fungsi sasaran

1. Pilih **Tambah atribut** untuk memilih data yang anda perlukan untuk mencipta ukuran ini.

   1. Pilih tab **Atribut**.
   1. Entiti data: Pilih entiti yang termasuk atribut yang anda mahu ukur.
   1. Atribut data: Pilih atribut yang anda mahu gunakan dalam fungsi pengagregatan untuk mengira ukuran. Anda hanya boleh memilih satu atribut pada satu masa.
   1. Anda juga boleh memilih atribut data daripada ukuran sedia ada dengan memilih tab **Ukuran** atau anda boleh mencari nama entiti atau ukuran.
   1. Pilih **Tambah** untuk menambah atribut terpilih pada ukuran.

1. Untuk membina lebih banyak ukuran rumit, anda boleh menambah lebih banyak atribut atau menggunakan operator matematik dalam fungsi ukuran anda.

1. Untuk menambah penapis, pilih **Penapis** dalam kawasan konfigurasi. Menggunakan penapis hanya akan menggunakan rekod yang sepadan dengan penapis untuk mengira ukuran.
  
   1. Dalam bahagian **Tambah atribut** anak tetingkap **Penapis**, pilih atribut yang mahu anda gunakan untuk mencipta penapis.
   1. Tetapkan operator penapis untuk mentakrifkan penapis bagi setiap atribut yang dipilih.
   1. Pilih **Gunakan** untuk menambah penapis terpilih pada ukuran.

1. Pilih **Dimensi** untuk memilih lebih banyak medan yang ditambah sebagai lajur pada entiti output ukur.

   1. Pilih **Edit dimensi** untuk menambah atribut data yang anda mahu kumpulkan nilai ukuran. Sebagai contoh, bandar atau jantina.
   > [!TIP]
   > Jika anda memilih **tahap** Pelanggan sebagai **jenis Ukur,** atribut *Id Pelanggan* telah ditambah. Jika anda mengalih keluar atribut, **Togol jenis** Ukur ke **tahap** Perniagaan.
   1. Pilih **Selesai** untuk menambah dimensi pada ukuran.

1. Jika terdapat nilai dalam data anda yang anda perlu ganti dengan integer, pilih **Peraturan**. Konfigurasikan peraturan dan pastikan anda memilih hanya nombor keseluruhan sebagai pengganti. Sebagai contoh, gantikan *nol* dengan *0*.

1. Jika terdapat berbilang laluan antara entiti data yang anda petakan dengan entiti *Pelanggan*, anda perlu memilih salah satu daripada [laluan perhubungan entiti](relationships.md) yang dikenal pasti. Hasil ukuran mungkin berbeza-beza bergantung pada laluan yang dipilih.

   1. Pilih **Laluan perhubungan** dan pilih laluan entiti yang sepatutnya boleh digunakan untuk mengenal pasti ukuran anda. Jika hanya terdapat laluan tunggal kepada entiti *Pelanggan*, kawalan ini tidak akan ditunjukkan.
   1. Pilih **Selesai** untuk menggunakan pilihan anda.

1. Untuk menambah lebih banyak pengiraan untuk ukuran, pilih **Pengiraan baharu**. Anda hanya boleh menggunakan entiti pada laluan entiti yang sama untuk pengiraan baharu. Lebih banyak pengiraan akan ditunjukkan sebagai lajur baharu dalam mengukur entiti output.

1. Pilih elipsis menegak (&vellip;) pada pengiraan kepada **Pendua**, **Namakan Semula** atau **Alih keluar** pengiraan daripada ukuran.

1. Dalam kawasan **Pratonton**, anda akan melihat skema data bagi entiti output ukuran, termasuk penapis dan dimensi. Pratonton bertindak balas secara dinamik kepada perubahan dalam konfigurasi.

1. Pilih **Edit butiran** di sebelah ukuran Tidak Bertajuk. Berikan nama untuk ukuran itu. Secara pilihan, tambah [tag](work-with-tags-columns.md#manage-tags) pada ukuran.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Kotak dialog Edit butiran butiran.":::

1. Pilih **Jalankan** untuk mengira hasil bagi langkah yang dikonfigurasikan. Pilih **Simpan dan tutup** jika anda mahu menyimpan konfigurasi semasa dan jalankan ukuran kemudian.

1. Pergi ke **Langkah** untuk melihat langkah yang baharu dicipta dalam senarai.

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

Anda boleh membuat langkah-langkah pada tahap akaun individu (ukuran pelanggan) atau pada tahap semua akaun (ukuran perniagaan).

- Ukuran pelanggan: Menjana output sebagai entitinya sendiri. Langkah-langkah pelanggan tidak dipaparkan dalam kad profil pelanggan.

- Langkah perniagaan: Menjana output sebagai entitinya sendiri dan dipaparkan pada halaman utama persekitaran Wawasan Pelanggan anda.

1. Pergi ke **Langkah-langkah**.

1. Pilih **Baharu**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Skrin konfigurasi kosong untuk ukuran B-ke-B.":::

1. Dalam kawasan konfigurasi, pilih fungsi pengagregatan daripada **menu juntai bawah Pilih fungsi**. Fungsi pengagregatan termasuk:
   - **Sum**
   - **Purata**
   - **Bilangan**
   - **Kira Unik**
   - **Maksimum**
   - **Min**
   - **Pertama**: mengambil kira nilai pertama bagi rekod data
   - **Terakhir**: ambil nilai terakhir yang ditambah ke rekod data

1. Pilih **Tambah atribut** untuk memilih data yang anda perlukan untuk mencipta ukuran ini.

   1. Pilih tab **Atribut**.
   1. Entiti data: Pilih entiti yang termasuk atribut yang anda mahu ukur.
   1. Atribut data: Pilih atribut yang anda mahu gunakan dalam fungsi pengagregatan untuk mengira ukuran. Anda hanya boleh memilih satu atribut pada satu masa.
   1. Anda juga boleh memilih atribut data daripada ukuran sedia ada dengan memilih tab **Ukuran** atau anda boleh mencari nama entiti atau ukuran.
   1. Pilih **Tambah** untuk menambah atribut terpilih pada ukuran.

1. Untuk membina lebih banyak ukuran rumit, anda boleh menambah lebih banyak atribut atau menggunakan operator matematik dalam fungsi ukuran anda.

1. Untuk menambah penapis, pilih **Penapis** dalam kawasan konfigurasi. Menggunakan penapis hanya akan menggunakan rekod yang sepadan dengan penapis untuk mengira ukuran.
  
   1. Dalam bahagian **Tambah atribut** anak tetingkap **Penapis**, pilih atribut yang mahu anda gunakan untuk mencipta penapis.
   1. Tetapkan operator penapis untuk mentakrifkan penapis bagi setiap atribut yang dipilih.
   1. Pilih **Gunakan** untuk menambah penapis terpilih pada ukuran.

1. Pilih **Dimensi** untuk memilih lebih banyak medan yang ditambah sebagai lajur pada entiti output ukur.

   1. Pilih **Edit dimensi** untuk menambah atribut data yang anda mahu kumpulkan nilai ukuran. Sebagai contoh, bandar atau jantina.
      > [!TIP]
      > Jika anda memilih **tahap** Pelanggan sebagai **jenis Ukur,** atribut *Id Pelanggan* telah ditambah. Jika anda mengalih keluar atribut, **Jenis** ukuran bertukar kepada **tahap** Perniagaan.
   1. Pilih **Selesai** untuk menambah dimensi pada ukuran.

1. Jika terdapat nilai dalam data anda yang anda perlu ganti dengan integer, pilih **Peraturan**. Konfigurasikan peraturan dan pastikan anda memilih hanya nombor keseluruhan sebagai pengganti. Sebagai contoh, gantikan *nol* dengan *0*.

1. Anda boleh menggunakan **Sub akaun gulung atas**, togol jika anda [menggunakan akaun dengan hierarki](relationships.md#set-up-account-hierarchies).
   - Jika ia ditetapkan kepada **Matikan** ukuran dikira untuk setiap akaun. Setiap akaun mendapat hasil sendiri.
   - Jika ia ditetapkan kepada **Hidupkan**, pilih **Edit** untuk memilih hierarki akaun mengikut kepada hierarki yang diinges. Ukuran ini hanya akan menghasilkan satu hasil kerana ia diagregat dengan sub akaun.

1. Jika terdapat berbilang laluan antara entiti data yang anda petakan dengan entiti *Pelanggan*, anda perlu memilih salah satu daripada [laluan perhubungan entiti](relationships.md) yang dikenal pasti. Hasil ukuran mungkin berbeza-beza bergantung pada laluan yang dipilih.

   1. Pilih **Laluan perhubungan** dan pilih laluan entiti yang sepatutnya boleh digunakan untuk mengenal pasti ukuran anda. Jika hanya terdapat laluan tunggal kepada entiti *Pelanggan*, kawalan ini tidak akan ditunjukkan.
   1. Pilih **Selesai** untuk menggunakan pilihan anda.

1. Pilih elipsis menegak (&vellip;) pada pengiraan kepada **Pendua**, **Namakan Semula** atau **Alih keluar** pengiraan daripada ukuran.

1. Dalam kawasan **Pratonton**, anda akan melihat skema data bagi entiti output ukuran, termasuk penapis dan dimensi. Pratonton bertindak balas secara dinamik kepada perubahan dalam konfigurasi.

1. Pilih **Edit butiran** di sebelah ukuran Tidak Bertajuk. Berikan nama untuk ukuran itu. Secara pilihan, tambah [tag](work-with-tags-columns.md#manage-tags) pada ukuran.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Kotak dialog Edit butiran butiran.":::

1. Pilih **Jalankan** untuk mengira hasil bagi langkah yang dikonfigurasikan. Pilih **Simpan dan tutup** jika anda mahu menyimpan konfigurasi semasa dan jalankan ukuran kemudian.

1. Pergi ke **Langkah** untuk melihat langkah yang baharu dicipta dalam senarai.
