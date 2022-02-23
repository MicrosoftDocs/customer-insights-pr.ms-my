---
title: Cipta dan urus tindakan
description: Takrifkan ukuran untuk menganalisis dan mencerminkan prestasi perniagaan anda.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f6be11bd97be71bc0c3a58eaee4d8ed45f535877
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732737"
---
# <a name="define-and-manage-measures"></a>Takrifkan dan urus tindakan

Langkah ini membantu anda untuk lebih memahami tingkah laku pelanggan dan prestasi perniagaan. Mereka melihat nilai yang relevan daripada [profil disatukan](data-unification.md). Contohnya, perniagaan ingin melihat *jumlah perbelanjaan setiap pelanggan* untuk memahami sejarah pembelian pelanggan individu atau mengukur *jumlah jualan syarikat* untuk memahami hasil peringkat agregat dalam keseluruhan perniagaan.  

Ukuran dicipta menggunakan pembina ukuran, platform pertanyaan data dengan pelbagai pengendali dan pilihan pemetaan yang mudah. Ia membolehkan anda menapis data, mengumpulkan hasil, mengesan [laluan perhubungan entiti](relationships.md) dan pratonton output.

Gunakan pembina ukuran untuk merancang aktiviti perniagaan dengan bertanya pada data pelanggan dan mendapatkan wawasan. Sebagai contoh, mencipta ukuran *jumlah perbelanjaan setiap pelanggan* dan *jumlah pulangan setiap pelanggan* membantu mengenal pasti kumpulan pelanggan yang mempunyai perbelanjaan tinggi tetapi pulangan tinggi. Anda boleh [mencipta segmen](segments.md) untuk memacu tindakan terbaik seterusnya. 

## <a name="build-your-own-measure-from-scratch"></a>Bina ukuran anda sendiri dari mula

Bahagian ini membimbing anda mencipta ukuran baharu dari awal. Anda boleh membina ukuran dengan atribut data daripada entiti data yang mempunyai persediaan perhubungan untuk berhubung dengan entiti profil pelanggan disatukan.

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

1. Dalam wawasan khalayak, pergi ke **Ukuran**.

1. Pilih **Baharu** dan pilih **Bina yang anda sendiri**.

1. Pilih **Edit nama** dan berikan **Nama** untuk langkah itu. 

1. Dalam kawasan konfigurasi, pilih fungsi pengagregatan daripada menu juntai bawah **Pilih Fungsi**. Fungsi pengagregatan termasuk: 
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
   1. Anda juga boleh memilih atribut data daripada ukuran sedia ada dengan memilih tab **Ukuran** atau anda boleh mencari nama entiti atau ukuran. 
   1. Pilih **Tambah** untuk menambah atribut terpilih pada ukuran.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Pilih atribut untuk digunakan dalam pengiraan.":::

1. Untuk membina lebih banyak ukuran rumit, anda boleh menambah lebih banyak atribut atau menggunakan operator matematik dalam fungsi ukuran anda.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Cipta ukuran rumit dengan operator matematik.":::

1. Untuk menambah penapis, pilih **Penapis** dalam kawasan konfigurasi. 
  
   1. Dalam bahagian **Tambah atribut** anak tetingkap **Penapis**, pilih atribut yang mahu anda gunakan untuk mencipta penapis.
   1. Tetapkan operator penapis untuk mentakrifkan penapis bagi setiap atribut yang dipilih.
   1. Pilih **Gunakan** untuk menambah penapis terpilih pada ukuran.

1. Untuk menambah dimensi pilih **Dimensi** dalam kawasan konfigurasi. Dimensi akan ditunjukkan sebagai lajur dalam mengukur entiti output.
 
   1. Pilih **Edit dimensi** untuk menambah atribut data yang anda mahu kumpulkan nilai ukuran. Sebagai contoh, bandar atau jantina. Secara lalai, dimensi *CustomerID* dipilih untuk mencipta *ukuran peringkat pelanggan*. Anda boleh mengalih keluar dimensi lalai jika anda mahu mencipta *ukuran peringkat perniagaan*.
   1. Pilih **Selesai** untuk menambah dimensi pada ukuran.

1. Jika terdapat nilai dalam data anda yang anda perlu ganti dengan integer, pilih **Peraturan**. Konfigurasikan peraturan dan pastikan anda memilih hanya nombor keseluruhan sebagai pengganti. Sebagai contoh, gantikan *nol* dengan *0*.

1. Jika terdapat berbilang laluan antara entiti data yang anda petakan dengan entiti *Pelanggan*, anda perlu memilih salah satu daripada [laluan perhubungan entiti](relationships.md) yang dikenal pasti. Hasil ukuran mungkin berbeza-beza bergantung pada laluan yang dipilih. 
   
   1. Pilih **Laluan perhubungan** dan pilih laluan entiti yang sepatutnya boleh digunakan untuk mengenal pasti ukuran anda. Jika hanya terdapat laluan tunggal kepada entiti *Pelanggan*, kawalan ini tidak akan ditunjukkan.
   1. Pilih **Selesai** untuk menggunakan pilihan anda. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pilih laluan entiti untuk ukuran.":::

1. Untuk menambah lebih banyak pengiraan untuk ukuran, pilih **Pengiraan baharu**. Anda hanya boleh menggunakan entiti pada laluan entiti yang sama untuk pengiraan baharu. Lebih banyak pengiraan akan ditunjukkan sebagai lajur baharu dalam mengukur entiti output.

1. Pilih **...** pada pengiraan untuk **Duplikasi**, **Nama semula** atau **Alih keluar** pengiraan daripada ukuran.

1. Dalam kawasan **Pratonton**, anda akan melihat skema data bagi entiti output ukuran, termasuk penapis dan dimensi. Pratonton bertindak balas secara dinamik kepada perubahan dalam konfigurasi.

1. Pilih **Jalankan** untuk mengira hasil bagi langkah yang dikonfigurasikan. Pilih **Simpan dan tutup** jika anda mahu menyimpan konfigurasi semasa dan jalankan ukuran kemudian.

1. Pergi ke **Langkah** untuk melihat langkah yang baharu dicipta dalam senarai.

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

1. Dalam wawasan khalayak, pergi ke **Ukuran**.

1. Pilih **Baharu** dan pilih **Bina yang anda sendiri**.

1. Pilih **Edit nama** dan berikan **Nama** untuk langkah itu. 

1. Dalam kawasan konfigurasi, pilih fungsi pengagregatan daripada menu juntai bawah **Pilih Fungsi**. Fungsi pengagregatan termasuk: 
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
   1. Anda juga boleh memilih atribut data daripada ukuran sedia ada dengan memilih tab **Ukuran** atau anda boleh mencari nama entiti atau ukuran. 
   1. Pilih **Tambah** untuk menambah atribut terpilih pada ukuran.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Pilih atribut untuk digunakan dalam pengiraan.":::

1. Untuk membina lebih banyak ukuran rumit, anda boleh menambah lebih banyak atribut atau menggunakan operator matematik dalam fungsi ukuran anda.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Cipta ukuran rumit dengan operator matematik.":::

1. Untuk menambah penapis, pilih **Penapis** dalam kawasan konfigurasi. 
  
   1. Dalam bahagian **Tambah atribut** anak tetingkap **Penapis**, pilih atribut yang mahu anda gunakan untuk mencipta penapis.
   1. Tetapkan operator penapis untuk mentakrifkan penapis bagi setiap atribut yang dipilih.
   1. Pilih **Gunakan** untuk menambah penapis terpilih pada ukuran.

1. Untuk menambah dimensi pilih **Dimensi** dalam kawasan konfigurasi. Dimensi akan ditunjukkan sebagai lajur dalam mengukur entiti output.
 
   1. Pilih **Edit dimensi** untuk menambah atribut data yang anda mahu kumpulkan nilai ukuran. Sebagai contoh, bandar atau jantina. Secara lalai, dimensi *CustomerID* dipilih untuk mencipta *ukuran peringkat pelanggan*. Anda boleh mengalih keluar dimensi lalai jika anda mahu mencipta *ukuran peringkat perniagaan*.
   1. Pilih **Selesai** untuk menambah dimensi pada ukuran.

1. Jika terdapat nilai dalam data anda yang anda perlu ganti dengan integer, pilih **Peraturan**. Konfigurasikan peraturan dan pastikan anda memilih hanya nombor keseluruhan sebagai pengganti. Sebagai contoh, gantikan *nol* dengan *0*.

1. Anda boleh menggunakan **Sub akaun gulung atas**, togol jika anda [menggunakan akaun dengan hierarki](relationships.md#set-up-account-hierarchies).
   - Jika ia ditetapkan kepada **Matikan** ukuran dikira untuk setiap akaun. Setiap akaun mendapat hasil sendiri.
   - Jika ia ditetapkan kepada **Hidupkan**, pilih **Edit** untuk memilih hierarki akaun mengikut kepada hierarki yang diinges. Ukuran ini hanya akan menghasilkan satu hasil kerana ia diagregat dengan sub akaun.

1. Jika terdapat berbilang laluan antara entiti data yang anda petakan dengan entiti *Pelanggan*, anda perlu memilih salah satu daripada [laluan perhubungan entiti](relationships.md) yang dikenal pasti. Hasil ukuran mungkin berbeza-beza bergantung pada laluan yang dipilih. 
   
   1. Pilih **Laluan perhubungan** dan pilih laluan entiti yang sepatutnya boleh digunakan untuk mengenal pasti ukuran anda. Jika hanya terdapat laluan tunggal kepada entiti *Pelanggan*, kawalan ini tidak akan ditunjukkan.
   1. Pilih **Selesai** untuk menggunakan pilihan anda. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pilih laluan entiti untuk ukuran.":::

1. Pilih **...** pada pengiraan untuk **Duplikasi**, **Nama semula** atau **Alih keluar** pengiraan daripada ukuran.

1. Dalam kawasan **Pratonton**, anda akan melihat skema data bagi entiti output ukuran, termasuk penapis dan dimensi. Pratonton bertindak balas secara dinamik kepada perubahan dalam konfigurasi.

1. Pilih **Jalankan** untuk mengira hasil bagi langkah yang dikonfigurasikan. Pilih **Simpan dan tutup** jika anda mahu menyimpan konfigurasi semasa dan jalankan ukuran kemudian.

1. Pergi ke **Langkah** untuk melihat langkah yang baharu dicipta dalam senarai.

---

## <a name="use-a-template-to-build-a-measure"></a>Gunakan templat untuk membina langkah

Anda boleh menggunakan templat pratakrif untuk langkah yang biasa digunakan untuk menciptanya. Penerangan terperinci mengenai templat dan pengalaman berpandu membantu anda dengan penciptaan langkah yang cekap. Templat dibina pada data yang dipetakan daripada entit *Aktiviti Disatukan*. Oleh itu, pastikan anda telah mengkonfigurasikan [aktiviti pelanggan](activities.md) sebelum anda mencipta langkah daripada templat.

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

Anda boleh menggunakan templat pratakrif untuk langkah yang biasa digunakan untuk menciptanya. Penerangan terperinci mengenai templat dan pengalaman berpandu membantu anda dengan penciptaan langkah yang cekap. Templat dibina pada data yang dipetakan daripada entit *Aktiviti Disatukan*. Oleh itu, pastikan anda telah mengkonfigurasikan [aktiviti pelanggan](activities.md) sebelum anda mencipta langkah daripada templat.

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

Prosedur berikut menggariskan langkah untuk membina langkah baharu menggunakan templat.

1. Dalam wawasan khalayak, pergi ke **Ukuran**.

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

   :::image type="content" source="media/measure-template-configured.png" alt-text="Tangkapan skrin konfigurasi templat langkah yang lengkap.":::

1. Anda kini boleh memilih **Jalankan** untuk mengira keputusan ukuran. Untuk memperhalusi kemudian, pilih **Simpan draf**.

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

Ciri ini hanya tersedia untuk ukuran yang dicipta dalam persekitaran dengan pelanggan individu sebagai khalayak sasaran utama.

---

## <a name="manage-your-measures"></a>Urus tindakan anda

Anda boleh mendapatkan senarai langkah pada halaman **Langkah**.

Anda akan menemui maklumat tentang jenis ukuran, pencipta, tarikh penciptaan, status dan keadaan. Apabila anda memilih ukuran daripada senarai, anda boleh pratonton output dan memuat turun fail CSV.

Untuk menyegarkan semula semua tindakan pada masa yang sama, pilih **Segar semula semua** tanpa memilih tindakan khusus.

> [!div class="mx-imgBorder"]
> ![Tindakan untuk menguruskan langkah tunggal.](media/measure-actions.png "Tindakan untuk menguruskan langkah tunggal.")

Pilih ukuran daripada senarai untuk pilihan berikut:

- Pilih nama langkah untuk melihat butiran.
- **Edit** konfigurasi langkah.
- **Segar semula** ukuran berdasarkan data terkini.
- **Nama semula** langkah.
- **Padam** langkah.
- **Aktifkan** atau **Nyahaktifkan**. Langkah tidak aktif tidak akan dapat disegar semula semasa [segar semula yang dijadualkan](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Langkah seterusnya

Anda boleh menggunakan langkah sedia ada untuk mencipta [segmen pelanggan](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
