---
title: Cipta dan urus segmen
description: Cipta bahagian pelanggan untuk mengumpul mereka berasaskan pelbagai atribut.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064948"
---
# <a name="create-and-manage-segments"></a>Cipta dan urus segmen

Takrifkan penapis kompleks sekitar entiti pelanggan disatukan dan entiti yang berkaitan. Setiap segmen, selepas pemprosesan, mencipta set rekod pelanggan yang boleh anda eksport dan ambil tindakan padanya. Segmen diuruskan pada halaman **Segmen**. 

Contoh berikut menunjukkan keupayaan pembahagian. Kami telah menentukan segmen untuk pelanggan yang mengarahkan sekurang-kurangnya $500 barangan dalam 90 hari yang lalu *dan* yang terlibat dalam panggilan khidmat pelanggan yang telah dipertingkatkan.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Tangkapan skrin bagi UI pembina segmen dengan dua kumpulan yang menentukan segmen pelanggan.":::

## <a name="create-a-new-segment"></a>Cipta bahagian baharu

Terdapat berbilang cara untuk mencipta segmen baharu. Bahagian ini menerangkan cara mencipta *segmen kosong* daripada mula. Anda juga boleh mencipta *segmen pantas* berdasarkan pada entiti sedia ada atau menggunakan model pembelajaran mesin untuk mendapatkan *segmen yang dicadangkan*. Maklumat lanjut: [Gambaran keseluruhan segmen](segments.md).

Semasa mencipta segmen, anda boleh menyimpan draf. Ia akan disimpan sebagai segmen tidak aktif dan tidak boleh diaktifkan setelah selesai dengan konfigurasi yang sah.

1. Pergi ke halaman **Bahagian**.

1. Pilih **Baharu** > **Segmen kosong**.

1. Dalam anak tetingkap **Segmen baharu**, pilih jenis segmen:

   - **Segmen dinamik** [segar semula](segments.md#refresh-segments) pada jadual berulang.
   - **Segmen statik** berjalan sebaik sahaja anda menciptanya.

1. Berikan **Nama entiti output** untuk segmen. Secara pilihan, berikan nama paparan, dan description yang membantu mengenal pasti bahagian.

1. Pilih **Seterusnya** untuk mendapatkan halaman **Pembina bahagian** di mana anda menakrif kumpulan. Kumpulan ialah set pelanggan.

1. Pilih entiti yang merangkumi atribut yang anda mahu dibahagikan.

1. Pilih atribut untuk segmen mengikut. Atribut ini boleh mempunyai salah satu daripada empat jenis nilai: berangka, rentetan, tarikh atau Boolean.

1. Pilih operator dan nilai untuk atribut yang dipilih.

   > [!div class="mx-imgBorder"]
   > ![Penapis kumpulan tersuai](media/customer-group-numbers.png "Penapis kumpulan pelanggan")

   |Nombor |Definisi  |
   |---------|---------|
   |1     |EntitI          |
   |2     |Atribut          |
   |3    |Operator         |
   |4    |Nilai         |

   1. Untuk menambahkan lebih banyak syarat ke kumpulan, anda boleh menggunakan dua operator logik:

      - Operator **DAN**: Kedua-dua syarat mesti dipenuhi sebagai sebahagian proses pembahagian. Pilihan ini adalah paling berguna apabila anda menakrif syarat dalam entiti yang berbeza.

      - Operator **ATAU**: Salah satu syarat perlu dipenuhi sebagai sebahagian daripada proses pembahagian. Pilihan ini paling berguna apabila anda menakrif berbilang syarat untuk entiti yang sama.

      > [!div class="mx-imgBorder"]
      > ![Operator ATAU di mana salah satu syarat perlu dipenuhi](media/segmentation-either-condition.png "Operator ATAU di mana salah satu syarat perlu dipenuhi")

      Pada masa ini berkemungkinan untuk menyarang operator **ATAU** di bawah operator **DAN**, tetapi tidak sebaliknya.

   1. Setiap kumpulan berpadanan dengan set pelanggan. Anda boleh menggabungkan kumpulan untuk memasukkan pelanggan yang diperlukan bagi kes perniagaan anda.    
   Pilih **Tambah Kumpulan**.

      > [!div class="mx-imgBorder"]
      > ![Kumpulan pelanggan tambah kumpulan](media/customer-group-add-group.png "Kumpulan pelanggan tambah kumpulan")

   1. Pilih salah satu operator set: **Kesatuan**, **Bersilang** atau **Kecuali**.

   > [!div class="mx-imgBorder"]
   > ![Kumpulan pelanggan tambah kesatuan](media/customer-group-union.png "Kumpulan pelanggan tambah kesatuan")

   - **Kesatuan** menyatukan dua kumpulan.

   - **Bersilang** dua kumpulan bertindih. Hanya data yang *umum* pada kedua-dua kumpulan dikekalkan dalam kumpulan disatukan.

   - **Kecuali** menggabungkan dua kumpulan. Hanya data dalam kumpulan A yang *tidak umum* pada data dalam kumpulan B dikekalkan.

1. Jika entiti disambungkan kepada entiti pelanggan disatukan melalui [perhubungan](relationships.md), anda perlu mentakrifkan laluan perhubungan untuk mencipta segmen yang sah. Tambah entiti daripada laluan perhubungan sehingga anda boleh memilih entiti **Pelanggan : CustomerInsights** daripada juntai bawah. Kemudian pilih **Semua rekod** untuk setiap langkah.

   > [!div class="mx-imgBorder"]
   > ![Laluan perhubungan semasa penciptaan segmen](media/segments-multiple-relationships.png "Laluan perhubungan semasa penciptaan segmen")

1. Secara lalai, segmen menjana entiti output yang mengandungi semua atribut profil pelanggan yang sepadan dengan penapis yang ditentukan. Jika segmen berdasarkan entiti lain daripada entiti *Pelanggan*, anda boleh menambahkan lebih banyak atribut daripada entiti tersebut kepada entiti output. Pilih **Atribut projek** untuk memilih atribut yang akan ditambah pada entiti output.  
  
   Contoh: Segmen berdasarkan entiti yang mengandungi data aktiviti pelanggan yang berkaitan dengan entiti *Pelanggan*. Segmen mencari semua pelanggan yang memanggil meja bantuan dalam masa 60 hari yang lalu. Anda boleh memilih untuk menambah tempoh panggilan dan bilangan panggilan kepada semua rekod pelanggan yang sepadan dalam entiti output. Maklumat ini mungkin berguna untuk menghantar e-mel dengan pautan berguna ke artikel bantuan dalam talian dan soalan lazim kepada pelanggan yang sering membuat panggilan.

   > [!NOTE]
   > - Atribut yang diunjurkan hanya berfungsi untuk entiti yang mempunyai perhubungan satu dengan banyak dengan entiti pelanggan. Contohnya, seorang pelanggan boleh mempunyai berbilang langganan.
   > - Anda hanya boleh mengunjurkan atribut daripada entiti yang digunakan dalam setiap kumpulan pertanyaan segmen yang anda bangunkan.
   > - Atribut yang diunjurkan diambil kira apabila menggunakan operator set.

1. Pilih **Simpan** untuk menyimpan bahagian anda. Bahagian anda akan disimpan dan diproses jika semua keperluan disahkan. Jika tidak, ia akan disimpan sebagai draf.

1. Pilih **Kembali ke segmen** untuk kembali ke halaman **Segmen**.



## <a name="quick-segments"></a>Segmen pantas

Segmen pantas membolehkan anda membina segmen ringkas dengan operator tunggal dengan pantas untuk wawasan yang lebih pantas.

1. Pada halaman **Segmen**, pilih **Baharu** > **Cipta daripada**.

   - Pilih pilihan **Profil** untuk membina segmen yang berasaskan pada entiti *pelanggan disatukan*.
   - Pilih pilihan **Ukuran** untuk membina segmen sekitar ukuran yang anda buat sebelum ini.
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

## <a name="next-steps"></a>Langkah seterusnya

[Eksport bahagian](export-destinations.md) dan teroka [Kad Pelanggan](customer-card-add-in.md) dan [Penyambung](export-power-bi.md) untuk mendapatkan wawasan pada peringkat pelanggan.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
