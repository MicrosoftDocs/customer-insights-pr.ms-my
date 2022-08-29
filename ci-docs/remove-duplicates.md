---
title: Mengalih keluar pendua sebelum menyatukan data
description: Langkah kedua dalam proses penyatuan ialah memilih rekod yang hendak disimpan apabila pendua ditemui.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 3f84c1c149f0befcbe489ccdd8a666ce6d5d798a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304484"
---
# <a name="remove-duplicates-before-unifying-data"></a>Mengalih keluar pendua sebelum menyatukan data

Langkah pilihan dalam penyatuan ini membolehkan anda menyediakan peraturan untuk menghapuskan rekod **pendua dalam** entiti. Penduaan mengenal pasti berbilang rekod untuk pelanggan dan memilih rekod terbaik untuk disimpan (berdasarkan keutamaan cantum asas) atau menggabungkan rekod menjadi satu (berdasarkan keutamaan cantuman lanjutan). Rekod sumber dikaitkan dengan rekod yang digabungkan dengan ID alternatif. Jika peraturan tidak dikonfigurasi, peraturan yang ditentukan sistem digunakan.

## <a name="default-deduplication"></a>Pertindihan lalai

Peraturan yang ditakrifkan sistem terpakai jika tiada peraturan pertindihan ditambah.

- Kunci utama dibahagikan.
  Untuk sebarang rekod dengan kunci primer yang sama, **rekod paling diisi** (yang mempunyai nilai nol paling sedikit) ialah pemenang.
- Mana-mana peraturan padanan entiti silang digunakan untuk entiti.
  Contohnya: Dalam langkah padanan, jika entiti A dipadankan dengan entiti B pada *FullName* dan *DateofBirth*, maka entiti A juga dibahagikan dengan *FullName* dan *DateofBirth*. Oleh kerana *FullName* dan *DateofBirth* adalah kunci yang sah untuk mengenal pasti pelanggan dalam entiti A, kunci ini juga sah untuk mengenal pasti pelanggan pendua dalam entiti A.

## <a name="include-enriched-entities-preview"></a>Termasuk entiti yang diperkaya (pratonton)

Jika anda memperkayakan entiti pada tahap sumber data untuk membantu meningkatkan hasil penyatuan anda, pilih mereka. Untuk maklumat lanjut, lihat [Pengayaan untuk sumber](data-sources-enrichment.md) data.

1. **Pada halaman Rekod** pendua, pilih **Gunakan entiti** diperkaya di bahagian atas halaman.

1. **Daripada anak tetingkap Gunakan entiti** yang diperkaya, pilih satu atau lebih entiti yang diperkaya.

1. Pilih **Selesai**.

## <a name="define-deduplication-rules"></a>Tentukan peraturan pertindihan

1. Pada halaman **Rekod pendua**, pilih entiti dan pilih **Tambah peraturan** untuk mentakrifkan peraturan duplikasi.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Petikan skrin halaman Rekod pendua dengan entiti diserlahkan dan Peraturan tambah dipaparkan"  lightbox="media/m3_duplicates_showmore.png":::

   1. **Dalam anak tetingkap Tambah peraturan**, masukkan maklumat berikut:
      - **Pilih medan**: Pilih daripada senarai medan yang tersedia daripada entiti yang anda ingin semak untuk pendua. Pilih medan yang mungkin unik untuk setiap pelanggan tunggal. Contohnya, alamat e-mel atau gabungan nama, bandar dan nombor telefon.
      - **Normalkan**: Pilih daripada pilihan normalisasi berikut untuk atribut yang dipilih.
        - **Angka**: Menukar sistem angka lain, seperti angka Rom, kepada angka Arab. *VIII* menjadi *8*.
        - **Simbol**: Mengalih keluar semua simbol dan aksara khas. *Head&Shoulder* menjadi *HeadShoulder*.
        - **Teks kepada huruf kecil: Menukar semua aksara kepada huruf** kecil. *SEMUA HURUF BESAR dan Huruf Besar Kecil* menjadi *semua huruf besar dan huruf besar kecil*.
        - **Jenis (Telefon, Nama, Alamat, Organisasi)**: Menyeragamkan nama, tajuk, nombor telefon, alamat, dll.
        - **Unikod kepada ASCII**: Menukar tatatanda unicode kepada aksara ASCII. */u00B2* menjadi *2*.
        - **Ruang putih**: Mengalih keluar semua ruang. *Hello World* menjadi *HelloWorld*.
      - **Ketepatan**: Tetapkan tahap ketepatan untuk digunakan bagi syarat ini.
        - **Asas**: Pilih daripada *Rendah (30%)*, *Sederhana (60%)*, *Tinggi (80%)*, dan *Tepat (100%)*. Pilih **Tepat** untuk memadankan rekod yang sepadan dengan 100 peratus sahaja.
        - **Tersuai**: Tetapkan peratusan yang perlu dipadankan oleh rekod. Sistem hanya akan sepadan dengan rekod yang melepasi ambang ini.
      - **Nama**: Nama untuk peraturan.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Petikan skrin anak tetingkap tambah peraturan untuk mengalih keluar pendua.":::

   1. Secara pilihan, pilih **Tambah** > **syarat** untuk menambah lebih banyak syarat pada peraturan. Syarat yang disambungkan dengan logik DAN operator dengan itu hanya dilaksanakan jika semua syarat dipenuhi.

   1. Secara pilihan, **Tambah** > **pengecualian** untuk [menambah pengecualian kepada peraturan](match-entities.md#add-exceptions-to-a-rule). Pengecualian digunakan untuk menangani kes-kes positif palsu yang jarang berlaku dan negatif palsu.

   1. Pilih **Selesai** untuk mencipta peraturan.

1. Secara pilihan, [tambah lebih banyak peraturan](#define-deduplication-rules).

1. Pilih entiti kemudian **Edit keutamaan** cantum.

1. **Dalam anak tetingkap keutamaan** Cantum:
   1. Pilih salah satu daripada tiga pilihan untuk menentukan rekod yang hendak disimpan jika pendua ditemui:
      - **Paling terisi**: Kenal pasti rekod dengan medan atribut yang paling terisi sebagai rekod pemenang. Ia merupakan pilihan gabungan lalai.
      - **Paling terkini**: Mengenal pasti rekod pemenang berdasarkan paling terkini. Memerlukan medan tarikh atau angka untuk mentakrifkan yang terkini.
      - **Kurang terkini**: Mengenal pasti rekod pemenang berdasarkan kurang terkini. Memerlukan medan tarikh atau angka untuk mentakrifkan yang terkini.

      Sekiranya seri, rekod pemenang adalah yang mempunyai MAX (PK) atau nilai kunci utama yang lebih besar.

   1. Secara pilihan, untuk menentukan keutamaan cantuman pada atribut individu bagi sesebuah entiti, pilih **Lanjutan** di bahagian bawah anak tetingkap. Sebagai contoh, anda boleh memilih untuk menyimpan e-mel terkini DAN alamat yang paling lengkap daripada rekod yang berbeza. Kembangkan entiti untuk melihat semua atributnya dan menentukan pilihan mana yang akan digunakan untuk atribut individu. Jika anda memilih pilihan berasaskan recency, anda juga perlu menentukan medan tarikh / masa yang mentakrifkan recency.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Anak tetingkap keutamaan cantum lanjutan menunjukkan e-mel terkini dan alamat lengkap":::

   1. Pilih **Selesai** untuk menggunakan keutamaan cantuman anda.

1. Selepas mentakrifkan peraturan pertindihan dan cantumkan keutamaan, pilih **Seterusnya**.
  
> [!div class="nextstepaction"]
> [Langkah seterusnya untuk satu entiti: Menyatukan medan](merge-entities.md)

> [!div class="nextstepaction"]
> [Langkah seterusnya untuk berbilang entiti: Syarat yang sepadan](match-entities.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
