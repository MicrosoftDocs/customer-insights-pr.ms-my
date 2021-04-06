---
title: Cipta dan urus segmen
description: Cipta bahagian pelanggan untuk mengumpul mereka berasaskan pelbagai atribut.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597065"
---
# <a name="create-and-manage-segments"></a>Cipta dan urus segmen

Segmen membolehkan anda mengumpulkan pelanggan berdasarkan atribut demografi, transaksi atau tingkah laku. Anda boleh menggunakan segmen untuk kempen promosi sasaran, aktiviti jualan dan tindakan sokongan pelanggan untuk mencapai matlamat perniagaan anda.

Anda boleh menakrif penapis kompleks dalam entiti Profil Pelanggan dan entiti yang berkaitan. Setiap segmen, selepas pemprosesan, mencipta set rekod pelanggan yang boleh anda eksport dan ambil tindakan padanya. Sesetengah [had perkhidmatan](service-limits.md) diguna pakai.

Melainkan jika dinyatakan sebaliknya, semua segmen merupakan **Segmen dinamik**, yang disegar semula pada jadual berulang.

Contoh berikut menunjukkan keupayaan pembahagian. Kami telah menentukan segmen untuk pelanggan yang mengarahkan sekurang-kurangnya $500 barangan dalam 90 hari yang lalu *dan* yang terlibat dalam panggilan khidmat pelanggan yang telah dipertingkatkan.

> [!div class="mx-imgBorder"]
> ![Berbilang kumpulan](media/segmentation-group1-2.png "Berbilang kumpulan")

## <a name="create-a-new-segment"></a>Cipta bahagian baharu

Segmen diuruskan pada halaman **Segmen**.

1. Dalam cerapan khalayak, pergi ke halaman **Segmen**.

1. Pilih **Baharu** > **Segmen kosong**.

1. Dalam anak tetingkap **Bahagian baharu**, pilih jenis bahagian dan berikan **Nama**.

   Secara pilihan, berikan nama paparan, dan description yang membantu mengenal pasti bahagian.

1. Pilih **Seterusnya** untuk mendapatkan halaman **Pembina bahagian** di mana anda menakrif kumpulan. Kumpulan ialah set pelanggan.

1. Pilih entiti yang merangkumi atribut yang anda mahu dibahagikan.

1. Pilih atribut untuk segmen mengikut. Atribut ini boleh mempunyai salah satu daripada empat jenis nilai: berangka, rentetan, tarikh atau Boolean.

1. Pilih operator dan nilai untuk atribut yang dipilih.

   > [!div class="mx-imgBorder"]
   > ![Penapis kumpulan tersuai](media/customer-group-numbers.png "Penapis kumpulan pelanggan")

   |Nombor |Definisi  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operator         |
   |4    |Nilai         |

8. Jika entiti disambungkan kepada entiti pelanggan disatukan melalui [perhubungan](relationships.md), anda perlu mentakrifkan laluan perhubungan untuk mencipta segmen yang sah. Tambah entiti daripada laluan perhubungan sehingga anda boleh memilih entiti **Pelanggan : CustomerInsights** daripada juntai bawah. Kemudian, pilih **Semua rekod** untuk setiap syarat.

   > [!div class="mx-imgBorder"]
   > ![Laluan perhubungan semasa penciptaan segmen](media/segments-multiple-relationships.png "Laluan perhubungan semasa penciptaan segmen")

1. Secara lalai, segmen menjana entiti output yang mengandungi semua atribut profil pelanggan yang sepadan dengan penapis yang ditentukan. Jika segmen berdasarkan entiti lain daripada entiti *Pelanggan*, anda boleh menambahkan lebih banyak atribut daripada entiti tersebut kepada entiti output. Pilih **Atribut projek** untuk memilih atribut yang akan ditambah pada entiti output.  

   
   Contoh: Segmen berdasarkan entiti yang mengandungi data aktiviti pelanggan yang berkaitan dengan entiti *Pelanggan*. Segmen mencari semua pelanggan yang memanggil meja bantuan dalam masa 60 hari yang lalu. Anda boleh memilih untuk menambah tempoh panggilan dan bilangan panggilan kepada semua rekod pelanggan yang sepadan dalam entiti output. Maklumat ini mungkin berguna untuk menghantar e-mel dengan pautan berguna ke artikel bantuan dalam talian dan soalan lazim kepada pelanggan yang sering membuat panggilan.

1. Pilih **Simpan** untuk menyimpan bahagian anda. Bahagian anda akan disimpan dan diproses jika semua keperluan disahkan. Jika tidak, ia akan disimpan sebagai draf.

1. Pilih **Kembali ke segmen** untuk kembali ke halaman **Segmen**.

## <a name="manage-existing-segments"></a>Mengurus bahagian sedia ada

Pada halaman **Bahagian**, anda boleh melihat semua bahagian yang anda simpan dan mengurusnya.

Setiap segmen diwakili oleh baris yang menyertakan maklumat tambahan tentang segmen.

Anda boleh menyusun segmen dalam lajur dengan memilih tajuk lajur.

Gunakan kotak **Cari** di sudut kanan atas untuk menapis segmen.

> [!div class="mx-imgBorder"]
> ![Pilihan untuk menguruskan segmen sedia ada](media/segments-selected-segment.png "Pilihan untuk menguruskan segmen sedia ada")

Tindakan yang berikut tersedia apabila anda memilih segmen:

- **Lihat** butiran segmen, termasuk trend kiraan ahli pratonton ahli segmen.
- **Edit** segmen untuk mengubah sifatnya.
- **Cipta duplikasi** segmen. Anda boleh memilih untuk mengedit sifat dengan serta-merta atau hanya menyimpan duplikasi.
- **Segar semula** segmen untuk memasukkan data terkini.
- **Aktifkan** atau **Nyahaktifkan** segmen. Segmen mempunyai dua keadaan yang mungkin - aktif atau tidak aktif. Keadaan ini berguna apabila mengedit segmen. Untuk segmen tidak aktif, takrifan segmen wujud tetapi ia tidak mengandungi sebarang pelanggan lagi. Apabila anda mengaktifkan segmen, keadaannya berubah daripada 'tidak aktif' kepada 'aktif" dan ia mula mencari pelanggan yang sepadan dengan takrifan segmen. Jika [segar semula berjadual](system.md#schedule-tab) dikonfigurasikan, segmen yang tidak aktif mempunyai **Status** yang disenaraikan sebagai **Dilangkau**, menunjukkan bahawa segar semula tidak pernah dicuba. Apabila segmen yang tidak aktif diaktifkan, ia akan menyegar semula dan akan disertakan dalam segar semula berjadual.
  Secara alternatif, anda boleh menggunakan kefungsian **Jadual kemudian** dalam juntai bawah **Aktifkan/Nyahaktifkan** untuk menetapkan tarikh dan masa pada masa depan untuk pengaktifan dan penyahaktifan segmen tertentu.
- **Nama semula** segmen.
- **Muat turun** senarai ahli sebagai fail .CSV.
- Pilihan **Tambahkan pada** menghantar senarai ID Pelanggan dalam segmen untuk pemprosesan dalam aplikasi lain.
- **Padamkan** segmen.

## <a name="refresh-segments"></a>Segar semula segmen

Anda boleh memuatkan semula semua segmen serentak dengan memilih **Muat semula semua** pada halaman **Segmen** atau anda boleh memuatkan semula satu atau berbilang segmen apabila anda memilihnya dan memilih **Muat semula** daripada pilihan. Sebagai alternatif, anda boleh mengkonfigurasi segar semula pada **Pentadbir** > **Sistem** > **Jadual**.

> [!TIP]
> Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies). Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja. Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.

## <a name="download-and-export-segments"></a>Muat turun dan mengeksport segmen

Anda boleh memuat turun segmen anda ke fail CSV atau eksportnya ke Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Muat turun segmen ke fail CSV

1. Dalam cerapan khalayak, pergi ke halaman **Segmen**.

2. Pilih elipsis dalam jubin segmen tertentu.

3. Pilih **Muat Turun sebagai CSV** daripada tindakan senarai juntai bawah.

### <a name="export-segments-to-dynamics-365-sales"></a>Eksport segmen ke Dynamics 365 Sales

Sebelum mengeksport segmen ke Dynamics 365 Sales, pentadbir perlu [mencipta destinasi eksport](export-destinations.md) untuk Dynamics 365 Sales.

1. Dalam cerapan khalayak, pergi ke halaman **Segmen**.

2. Pilih elipsis dalam jubin segmen tertentu.

3. Pilih **Tambah** daripada tindakan senarai juntai bawah dan pilih destinasi eksport yang anda mahu hantarkan data.

## <a name="draft-mode-for-segments"></a>Mod draf untuk bahagian

Jika tidak semua keperluan untuk bahagian diproses dipenuhi, anda boleh menyimpan bahagian sebagai draf dan mengaksesnya daripada halaman **Bahagian**.

Ia akan disimpan sebagai segmen tidak aktif dan tidak boleh diaktifkan sehingga ia sah.

## <a name="add-more-conditions-to-a-group"></a>Menambah lebih banyak syarat ke kumpulan

Untuk menambahkan lebih banyak syarat ke kumpulan, anda boleh menggunakan dua operator logik:

- Operator **DAN**: Kedua-dua syarat mesti dipenuhi sebagai sebahagian proses pembahagian. Pilihan ini adalah paling berguna apabila anda menakrif syarat dalam entiti yang berbeza.

- Operator **ATAU**: Salah satu syarat perlu dipenuhi sebagai sebahagian daripada proses pembahagian. Pilihan ini paling berguna apabila anda menakrif berbilang syarat untuk entiti yang sama.

   > [!div class="mx-imgBorder"]
   > ![Operator ATAU di mana salah satu syarat perlu dipenuhi](media/segmentation-either-condition.png "Operator ATAU di mana salah satu syarat perlu dipenuhi")

Pada masa ini berkemungkinan untuk menyarang operator **ATAU** di bawah operator **DAN**, tetapi tidak sebaliknya.

## <a name="combine-multiple-groups"></a>Menggabungkan berbilang kumpulan

Setiap kumpulan menghasilkan set pelanggan khusus. Anda boleh menggabungkan kumpulan ini untuk memasukkan pelanggan yang diperlukan untuk kes perniagaan anda.

1. Dalam cerapan khalayak, pergi ke halaman **Segmen** dan pilih satu segmen.

2. Pilih **Tambah Kumpulan**.

   > [!div class="mx-imgBorder"]
   > ![Kumpulan pelanggan tambah kumpulan](media/customer-group-add-group.png "Kumpulan pelanggan tambah kumpulan")

3. Pilih salah satu pengendali set berikut: **Kesatuan**, **Silang** atau **Kecuali**.

   > [!div class="mx-imgBorder"]
   > ![Kumpulan pelanggan tambah kesatuan](media/customer-group-union.png "Kumpulan pelanggan tambah kesatuan")

   Pilih operasi set untuk mentakrifkan kumpulan baharu. Simpan kumpulan yang berbeza untuk menentukan data yang dapat dikekalkan:

   - **Kesatuan** menyatukan dua kumpulan.

   - **Bersilang** dua kumpulan bertindih. Hanya data yang *umum* pada kedua-dua kumpulan dikekalkan dalam kumpulan disatukan.

   - **Kecuali** menggabungkan dua kumpulan. Hanya data dalam kumpulan A yang *tidak umum* pada data dalam kumpulan B dikekalkan.

## <a name="view-processing-history-and-segment-members"></a>Lihat sejarah pemprosesan dan ahli bahagian

anda boleh melihat penyatuan data tentang bahagian dengan menyemak semula butirannya.

Pada halaman **Bahagian**, pilih bahagian yang anda mahu semak semula.

Bahagian atas halaman termasuk graf trend yang menggambarkan perubahan dalam kiraan ahli. Tuding pada titik data untuk melihat kiraan ahli pada tarikh tertentu.

Anda boleh mengemas kini tempoh masa bagi visualisasi.

> [!div class="mx-imgBorder"]
> ![Julat masa bahagian](media/segment-time-range.png "Julat masa bahagian")

Bahagian bawah mengandungi senarai ahli bahagian.

> [!NOTE]
> Medan yang muncul dalam senarai adalah berasaskan pada atribut bagi entiti segmen anda.
>
>Senarai ialah pratonton bagi pemadanan ahli bahagian dan menunjukkan 100 rekod pertama bahagian anda supaya anda boleh segera menilainya dan menyemak semula definisinya jika perlu. Untuk melihat semua rekod yang sepadan, anda perlu [mengeksport bahagian](export-destinations.md).

## <a name="quick-segments"></a>Segmen pantas

Sebagai tambahan kepada pembina segmen, terdapat satu lagi laluan untuk mencipta segmen. Segmen pantas membolehkan anda membina segmen ringkas dengan operator tunggal dengan cepat dan dengan cerapan segera.

1. Pada halaman **Segmen**, pilih **Baharu** > **Cipta dengan cepat daripada**.

   - Pilih pilihan **Profil** untuk membina bahagian yang berasaskan pada entiti Pelanggan disatukan.
   - Pilih pilihan **Ukuran** untuk membina segment dalam setiap jenis ukuran atribut pelanggan yang telah anda cipta sebelum ini pada halaman **Ukuran**.
   - Pilih pilihan **Kecerdasan** untuk membina segmen di sekitar salah satu entiti output yang dijana anda menggunakan sama ada keupayaan **Ramalan** atau **Model Tersuai**.

2. Dalam kotak dialog **Segmen pantas baharu**, pilih atribut daripada **Medan** juntai bawah.

3. Sistem akan memberikan wawasan tambahan yang membantu anda mencipta bahagian yang lebih baik untuk pelanggan anda.
   - Untuk medan kategori, kami akan menunjukkan 10 kiraan pelanggan teratas. Pilih **Nilai** dan pilih **Semak Semula**.

   - Untuk atribut numerik, sistem akan menunjukkan apakah nilai atribut yang jatuh dalam setiap persentil pelanggan. Pilih **Operator** dan **Nilai**, kemudian pilih **Semak Semula**.

4. Sistem akan memberikan anda **saiz bahagian yang dianggarkan**. Anda boleh memilih sama ada untuk menjana bahagian yang anda takrif, atau kunjungi semula terlebih dahulu untuk mendapatkan saiz bahagian yang berbeza.

    > [!div class="mx-imgBorder"]
    > ![Nama dan anggaran bagi bahagian pantas](media/quick-segment-name.png "Nama dan anggaran bagi bahagian pantas")

5. Berikan **Nama** untuk bahagian anda. Secara pilihan, berikan **Nama paparan**.

6. Pilih **Simpan** untuk mencipta bahagian.

7. Selepas bahagian selesai diproses, anda boleh melihatnya seperti bahagian lain yang anda cipta.

Untuk senario berikut, kami menyarankan penggunaan pembina bahagian berbanding keupayaan bahagian yang disyorkan:

- Mencipta bahagian dengan penapis pada medan kategori di mana operator berbeza daripada operator **Is**
- Mencipta bahagian dengan penapis pada medan numerik di mana operator berbeza daripada operator **Antara**, **Lebih daripada**, dan **Kurang daripada**
- Cipta segmen dengan penapis pada medan jenis tarikh

## <a name="next-steps"></a>Langkah seterusnya

[Eksport bahagian](export-destinations.md) dan teroka [Kad Pelanggan](customer-card-add-in.md) dan [Penyambung](export-power-bi.md) untuk mendapatkan wawasan pada peringkat pelanggan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]