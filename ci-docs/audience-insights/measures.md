---
title: Cipta dan urus tindakan
description: Takrifkan ukuran untuk menganalisis dan mencerminkan prestasi perniagaan anda.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269939"
---
# <a name="define-and-manage-measures"></a>Takrifkan dan urus tindakan

Ukuran membantu anda untuk lebih memahami tingkah laku pelanggan dan prestasi perniagaan dengan mendapatkan nilai yang relevan dari [profil disatukan](data-unification.md). Contohnya, sebuah perniagaan ingin melihat *jumlah perbelanjaan setiap pelanggan* untuk memahami sejarah pembelian pelanggan individu. Atau ukuran *jumlah jualan keseluruhan syarikat* untuk memahami perolehan peringkat agregat dalam keseluruhan perniagaan.  

Ukuran dicipta menggunakan pembina ukuran, platform pertanyaan data dengan pelbagai pengendali dan pilihan pemetaan yang mudah. Ia membolehkan anda menapis data, mengumpulkan hasil, mengesan [laluan perhubungan entiti](relationships.md) dan pratonton output.

Gunakan pembina ukuran untuk merancang aktiviti perniagaan dengan bertanya pada data pelanggan dan mendapatkan wawasan. Sebagai contoh, mencipta ukuran *jumlah perbelanjaan setiap pelanggan* dan *jumlah pulangan setiap pelanggan* membantu mengenal pasti kumpulan pelanggan yang mempunyai perbelanjaan tinggi tetapi pulangan tinggi. Anda boleh [mencipta segmen](segments.md) untuk memacu tindakan terbaik seterusnya. 

## <a name="create-a-measure"></a>Cipta ukuran

Bahagian ini membimbing anda mencipta ukuran baharu dari awal. Anda boleh membina ukuran dengan atribut data daripada entiti data yang mempunyai persediaan untuk berhubung dengan entiti Pelanggan. 

1. Dalam wawasan khalayak, pergi ke **Ukuran**.

1. Pilih **Baharu**.

1. Pilih **Edit nama** dan berikan **Nama** untuk langkah itu. 
   > [!NOTE]
   > Jika konfigurasi ukuran baharu anda hanya mempunyai dua medan, sebagai contog, CustomerID dan satu pengiraan, output akan ditambah sebagai lajur baharu kepada entiti yang dijana oleh sistem yang dipanggil Customer_Measure. Dan anda akan dapat melihat nilai ukuran dalam profil pelanggan disatukan. Ukuran lain akan menjana entiti mereka sendiri.

1. Dalam kawasan konfigurasi, pilih fungsi pengagregatan daripada menu ke bawah **Pilih Fungsi**. Fungsi pengagregatan termasuk: 
   - **Sum**
   - **Purata**
   - **Bilangan**
   - **Kira Unik**
   - **Maksimum**
   - **Min**
   - **Pertama**: mengambil kira nilai pertama bagi rekod data
   - **Terakhir**: ambil nilai terakhir yang ditambah ke rekod data

   :::image type="content" source="media/measure-operators.png" alt-text="Operator untuk mengukur pengiraan.":::

1. Pilih **Tambah atribut** untuk memilih data yang anda perlukan untuk mencipta ukuran ini.
   
   1. Pilih tab **Atribut**. 
   1. Entiti data: Pilih entiti yang termasuk atribut yang anda mahu ukur. 
   1. Atribut data: Pilih atribut yang anda mahu gunakan dalam fungsi pengagregatan untuk mengira ukuran. Anda hanya boleh memilih satu atribut pada satu masa.
   1. Anda juga boleh memilih atribut data daripada ukuran sedia ada dengan memilih tab **Ukuran**. Atau, anda boleh mencari nama entiti atau ukuran. 
   1. Pilih **Tambah** untuk menambah atribut terpilih pada ukuran.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Pilih atribut untuk digunakan dalam pengiraan.":::

1. Untuk membina lebih banyak ukuran rumit, anda boleh menambah lebih banyak atribut atau menggunakan operator matematik dalam fungsi ukuran anda.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Cipta ukuran rumit dengan operator matematik.":::

1. Untuk menambah penapis, pilih **Penapis** dalam kawasan konfigurasi. 
  
   1. Dalam bahagian **Tambah atribut** bagi anak tetingkap **Penapis**, pilih atribut yang anda mahu gunakan untuk mencipta penapis.
   1. Tetapkan operator penapis untuk mentakrifkan penapis bagi setiap atribut yang dipilih.
   1. Pilih **Gunakan** untuk menambah penapis terpilih pada ukuran.

1. Untuk menambah dimensi pilih **Dimensi** dalam kawasan konfigurasi. Dimensi akan ditunjukkan sebagai lajur dalam mengukur entiti output.
   1. Pilih **Edit dimensi** untuk menambah atribut data yang anda mahu kumpulkan nilai ukuran. Sebagai contoh, bandar atau jantina. Secara lalai, dimensi *CustomerID* dipilih untuk mencipta *ukuran peringkat pelanggan*. Anda boleh mengalih keluar dimensi lalai jika anda mahu mencipta *ukuran peringkat perniagaan*.
   1. Pilih **Selesai** untuk menambah dimensi pada ukuran.

1. Jika terdapat berbilang laluan antara entiti data yang anda petakan dan entiti Pelanggan, anda perlu memilih salah satu daripada [laluan perhubungan entiti](relationships.md) yang dikenal pasti. Hasil ukuran mungkin berbeza-beza bergantung pada laluan yang dipilih.
   1. Pilih **Keutamaan data** dan pilih laluan entiti yang sepatutnya boleh digunakan untuk mengenal pasti langkah anda.
   1. Pilih **Selesai** untuk menggunakan pilihan anda. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pilih laluan entiti untuk ukuran.":::

1. Untuk menambah lebih banyak pengiraan untuk ukuran, pilih **Pengiraan baharu**. Anda hanya boleh menggunakan entiti pada laluan entiti yang sama untuk pengiraan baharu. Lebih banyak pengiraan akan ditunjukkan sebagai lajur baharu dalam mengukur entiti output.

1. Pilih **...** pada pengiraan untuk **Duplikasi**, **Nama semula** atau **Alih keluar** pengiraan daripada ukuran.

1. Dalam kawasan **Pratonton**, anda akan melihat skema data bagi entiti output ukuran, termasuk penapis dan dimensi. Pratonton bertindak balas secara dinamik kepada perubahan dalam konfigurasi.

1. Pilih **Jalankan** untuk mengira hasil bagi langkah yang dikonfigurasikan. Pilih **Simpan dan tutup** jika anda mahu menyimpan konfigurasi semasa dan jalankan ukuran kemudian.

1. Pergi ke **Langkah** untuk melihat langkah yang baharu dicipta dalam senarai.

## <a name="manage-your-measures"></a>Urus tindakan anda

Selepas [mencipta ukuran](#create-a-measure), anda akan melihat senarai ukuran pada halaman **Langkah**.

Anda akan menemui maklumat tentang jenis ukuran, pencipta, tarikh penciptaan, status dan keadaan. Apabila anda memilih ukuran daripada senarai, anda boleh pratonton output dan muat turun fail .CSV.

Untuk menyegarkan semula semua tindakan pada masa yang sama, pilih **Segar semula semua** tanpa memilih tindakan khusus.

> [!div class="mx-imgBorder"]
> ![Tindakan untuk mengurus langkah tunggal](media/measure-actions.png "Tindakan untuk mengurus langkah tunggal")

Pilih ukuran daripada senarai untuk pilihan berikut:

- Pilih nama langkah untuk melihat butiran.
- **Edit** konfigurasi langkah.
- **Segar semula** ukuran berdasarkan data terkini.
- **Nama semula** langkah.
- **Padam** langkah.
- **Aktifkan** atau **Nyahaktifkan**. Langkah tidak aktif tidak akan dapat disegar semula semasa [segar semula yang dijadualkan](system.md#schedule-tab).

> [!TIP]
> Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies). Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja. Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.

## <a name="next-step"></a>Langkah seterusnya

Anda boleh menggunakan ukuran sedia ada untuk mencipta [segmen pelanggan](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]