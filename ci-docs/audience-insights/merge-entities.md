---
title: Gabung entiti dalam penyatuan data
description: Gabung entiti untuk mencipta profil pelanggan disatukan.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406474"
---
# <a name="merge-entities"></a>Gabungkan entiti

Fasa gabung ialah fasa terakhir dalam proses penyatuan data. Tujuannya ialah untuk menyesuaikan data berkonflik. Contoh data berkonflik termasuk nama pelanggan yang ditemui dalam dua set data anda tetapi menunjukkan sedikit berbeza dalam setiap ("Grant Marshall" berbanding "Grant Marshal") atau nombor telefon yang berbeza dalam format (617-803-091X berbanding 617803091X). Menggabungkan titik data berkonflik itu dilakukan secara atribut dengan atribut.

Selepas menyelesaikan [fasa padan](match-entities.md), anda boleh memulakan fasa gabung dengan memilih jubin **Gabung** pada halaman **Satukan**.

## <a name="review-system-recommendations"></a>Semak semula pengesyoran sistem

Pada halaman **Gabung**, anda memilih dan mengecualikan atribut untuk menggabungkan dalam entiti profil pelanggan disatukan anda (hasil daripada proses konfigurasi). Sesetengah atribut digabungkan oleh sistem secara automatik.

### <a name="view-merged-attributes"></a>Lihat atribut yang digabungkan

Untuk melihat atribut yang dimasukkan dalam salah satu atribut yang digabungkan secara automatik, pilih atribut yang digabungkan itu. Dua atribut yang menggubah atribut yang digabungkan dipaparkan dalam dua baris baharu di bawah atribut yang digabungkan.

> [!div class="mx-imgBorder"]
> ![Memilih atribut yang digabungkan](media/configure-data-merge-profile-attributes.png "Pilih atribut yang digabungkan")

### <a name="separate-merged-attributes"></a>Memisahkan atribut yang digabungkan

Untuk memisahkan atau membatalkan gabungan mana-mana atribut yang digabungkan secara automatik, cari atribut dalam jadual **Atribut profil**.

1. Pilih butang elipsis (...).
  
2. Dalam senarai juntai bawah, pilih **Pisahkan medan**.

### <a name="remove-merged-attributes"></a>Alih keluar atribut yang digabungkan

Untuk mengecualikan atribut daripada entiti profil pelanggan terakhir, carinya dalam jadual **Atribut**.

1. Pilih butang elipsis (...).
  
2. Dalam senarai juntai bawah, pilih **Jangan gabungkan**.

   Atribut dipindahkan ke bahagian **Alih keluar daripada rekod pelanggan**.

## <a name="manually-add-a-merged-attribute"></a>Menambah atribut yang digabungkan secara manual

Untuk menambah atribut yang digabung, pergi ke halaman **Gabung**.

1. Pilih **Tambah atribut yang digabungkan**.

2. Berikan **Nama** untuk mengenal pastinya pada halaman **Gabung** kemudian.

3. Secara pilihan, sediakan **Nama paparan** yang akan muncul dalam entiti Profil Pelanggan disatukan.

4. Konfigurasi **Pilih atribut pendua** untuk memilih atribut yang anda mahu gabung daripada entiti yang dipadankan. Anda juga boleh membuat carian untuk atribut.

5. Tetapkan **Kedudukan mengikut kepentingan** untuk mengutamakan satu atribut daripada atribut yang lain. Contohnya, jika entiti *WebAccountCSV* mengandungi data paling tepat tentang atribut *Nama penuh*, anda boleh mengutamakan entiti ini daripada *ContactCSV* dengan memilih *WebAccountCSV*. Hasilnya, *WebAccountCSV* akan dipindahkan ke keutamaan pertama, manakala *ContactCSV* akan dipindahkan ke keutamaan kedua semasa menarik nilai untuk atribut *Nama Penuh*.

## <a name="run-your-merge"></a>Jalankan gabungan anda

Sama ada anda menggabungkan atribut secara manual atau membiarkan sistem menggabungkannya, anda sentiasa boleh menjalankan gabungan anda. Pilih **Jalankan** pada halaman **Gabung** untuk memulakan proses.

> [!div class="mx-imgBorder"]
> ![Simpan dan Jalankan gabungan data](media/configure-data-merge-save-run.png "Simpan dan Jalankan Gabungan Data")

Untuk membuat perubahan tambahan dan jalankan semula langkah, anda boleh membatalkan gabungan dalam kemajuan. Pilih teks **Menyegarkan semula ...** dan pilih **Batal kerja** di bahagian tepi tetingkap yang muncul.

Selepas **Menyegarkan semula ...** teks berubah kepada **Berjaya**, gabungan telah sempurna dan selesaikan konflik dalam data anda mengikut dasar yang anda takrifkan. Atribut gabung dan tidak digabungkan dimasukkan dalam entiti profil disatukan. Atribut yang dikecualikan tidak dimasukkan dalam entiti profil disatukan.

Jika ia bukan kali pertama anda menjalankan dengan berjaya, semua proses hilir, termasuk pengayaan, pensegmenan dan langkah akan dijalankan semula secara automatik. Selepas semua proses hilir telah dijalankan semula, profil pelanggan menunjukkan perubahan yang anda lakukan.

> [!TIP]
> Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies). Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja. Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.

## <a name="next-step"></a>Langkah Seterusnya

Konfigurasikan [aktiviti](activities.md), [pengayaan](enrichment-microsoft-graph.md) atau [perhubungan](relationships.md) untuk mendapatkan wawasan lanjut tentang pelanggan anda.

Jika anda sudah mengkonfigurasi aktiviti, pengayaan atau perhubungan, atau jika anda mentakrifkan segmen, ia akan diproses secara automatik untuk menggunakan data pelanggan terkini.


