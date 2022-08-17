---
title: Alih keluar pendua sebelum menyatukan data
description: Langkah kedua dalam proses penyatuan adalah memilih rekod mana yang hendak disimpan apabila pendua ditemui.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 7f4829cfc14af623f724c6594e834f3fac1c15a9
ms.sourcegitcommit: 10dcfc32eaf8ec0903be96136dca7bb4e250276a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/01/2022
ms.locfileid: "9213638"
---
# <a name="remove-duplicates-before-unifying-data"></a>Alih keluar pendua sebelum menyatukan data

Langkah pilihan dalam penyatuan ini membolehkan anda menyediakan peraturan untuk menghapuskan rekod **pendua dalam** entiti. Deduplication mengenal pasti berbilang rekod untuk pelanggan dan memilih rekod terbaik untuk disimpan (berdasarkan keutamaan cantuman asas) atau menggabungkan rekod menjadi satu (berdasarkan keutamaan cantuman lanjutan). Rekod sumber dikaitkan dengan rekod yang digabungkan dengan ID alternatif. Jika peraturan tidak dikonfigurasikan, peraturan takrifan sistem digunakan.

## <a name="default-deduplication"></a>Penyahlangganan lalai

Peraturan yang ditentukan sistem digunakan jika tiada peraturan penyahduplikasi ditambah.

- Kekunci utama adalah deduplicated.
  Untuk sebarang rekod dengan kunci utama yang sama, **rekod Paling diisi** (yang mempunyai nilai nol paling sedikit) ialah pemenang.
- Sebarang peraturan padanan rentas entiti digunakan pada entiti.
  Sebagai contoh: Dalam langkah padanan, jika entiti A dipadankan dengan entiti B pada FullName *dan* DateofBirth *, maka entiti A juga diduplikasi oleh* FullName *dan* DateofBirth *·*. Kerana *FullName* dan *DateofBirth* adalah kunci yang sah untuk mengenal pasti pelanggan dalam entiti A, kunci ini juga sah untuk mengenal pasti pelanggan pendua dalam entiti A.

## <a name="include-enriched-entities-preview"></a>Sertakan entiti yang diperkaya (pratonton)

Jika anda memperkayakan entiti pada tahap sumber data untuk membantu meningkatkan hasil penyatuan anda, pilihnya. Untuk maklumat lanjut, lihat [Memperkayakan sumber](data-sources-enrichment.md) data.

1. **Pada halaman Rekod** pendua, pilih **Gunakan entiti** yang diperkaya di bahagian atas halaman.

1. **Daripada anak tetingkap Gunakan entiti** yang diperkaya, pilih satu atau lebih entiti yang diperkaya.

1. Pilih **Selesai**.

## <a name="define-deduplication-rules"></a>Tentukan peraturan deduplikasi

1. **Pada halaman Rekod** pendua, pilih entiti dan pilih **Tambah peraturan** untuk mentakrifkan peraturan penyahduplikasi.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Petikan skrin halaman Rekod pendua dengan Tunjukkan lebih diserlahkan":::

   1. Dalam anak tetingkap **Tambah peraturan**, masukkan maklumat berikut:
      - **Pilih medan**: Pilih daripada senarai medan yang tersedia daripada entiti yang anda ingin semak untuk pendua. Pilih medan yang mungkin unik untuk setiap pelanggan tunggal. Contohnya, alamat e-mel atau gabungan nama, bandar dan nombor telefon.
      - **Normalkan**: Pilih daripada pilihan normalisasi berikut untuk atribut yang dipilih.
        - **Angka**: Menukar sistem angka lain, seperti angka Rom, kepada angka Arab. *VIII* menjadi *8*.
        - **Simbol**: Mengalih keluar semua simbol dan aksara khas. *Head&Shoulder* menjadi *HeadShoulder*.
        - **Teks kepada huruf kecil: Menukar semua aksara kepada huruf kecil**. *SEMUA HURUF BESAR dan Huruf Besar Kecil* menjadi *semua huruf besar dan huruf besar kecil*.
        - **Jenis (Telefon, Nama, Alamat, Organisasi)**: Menyeragamkan nama, tajuk, nombor telefon, alamat, dll.
        - **Unicode kepada ASCII**: Menukar notasi unikod kepada aksara ASCII. */u00B2* menjadi *2*.
        - **Ruang putih**: Mengalih keluar semua ruang. *Hello World* menjadi *HelloWorld*.
      - **Ketepatan**: Tetapkan tahap ketepatan untuk digunakan bagi syarat ini.
        - **Asas**: Pilih daripada *Rendah (30%)*, *Sederhana (60%)*, *Tinggi (80%)*, dan *Tepat (100%)*. Pilih **Tepat** untuk hanya memadankan rekod yang sepadan dengan 100 peratus.
        - **Tersuai**: Tetapkan peratusan yang perlu dipadankan oleh rekod. Sistem hanya akan sepadan dengan rekod yang melepasi ambang ini.
      - **Nama**: Nama untuk peraturan.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Petikan skrin anak tetingkap Tambah peraturan untuk mengalih keluar pendua.":::

   1. Secara pilihan, pilih **Tambah** > **syarat** tambah untuk menambah lebih banyak syarat pada peraturan. Syarat yang disambungkan dengan logik DAN operator dengan itu hanya dilaksanakan jika semua syarat dipenuhi.

   1. Secara pilihan, **Tambah** > **pengecualian** untuk [menambah pengecualian kepada peraturan](match-entities.md#add-exceptions-to-a-rule). Pengecualian digunakan untuk menangani kes-kes yang jarang berlaku positif palsu dan negatif palsu.

   1. Pilih **Selesai** untuk mencipta peraturan.

1. Secara pilihan, [tambah lebih banyak peraturan](#define-deduplication-rules).

1. Pilih entiti dan kemudian **Edit keutamaan** cantum.

1. Dalam anak tetingkap **Cantum keutamaan**:
   1. Pilih salah satu daripada tiga opsyen untuk menentukan rekod yang hendak disimpan jika pendua ditemui:
      - **Paling terisi**: Kenal pasti rekod dengan medan atribut yang paling terisi sebagai rekod pemenang. Ia merupakan pilihan gabungan lalai.
      - **Paling terkini**: Mengenal pasti rekod pemenang berdasarkan paling terkini. Memerlukan medan tarikh atau angka untuk mentakrifkan yang terkini.
      - **Kurang terkini**: Mengenal pasti rekod pemenang berdasarkan kurang terkini. Memerlukan medan tarikh atau angka untuk mentakrifkan yang terkini.
      
      Sekiranya berlaku seri, rekod pemenang adalah yang mempunyai MAX (PK) atau nilai utama yang lebih besar.
      
   1. Secara pilihan, untuk mentakrifkan keutamaan cantum pada atribut individu entiti, pilih **Lanjutan** di bahagian bawah anak tetingkap. Sebagai contoh, anda boleh memilih untuk menyimpan e-mel terkini DAN alamat yang paling lengkap daripada rekod yang berbeza. Kembangkan entiti untuk melihat semua atributnya dan tentukan pilihan yang hendak digunakan untuk atribut individu. Jika anda memilih pilihan berasaskan recency, anda juga perlu menentukan medan tarikh/masa yang mentakrifkan recency.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Anak tetingkap keutamaan cantuman lanjutan menunjukkan e-mel terkini dan alamat lengkap":::

   1. Pilih **Selesai** untuk menggunakan keutamaan cantuman anda.

1. Selepas mentakrifkan peraturan deduplikasi dan menggabungkan keutamaan, pilih **Seterusnya**.
  
> [!div class="nextstepaction"]
> [Langkah seterusnya untuk entiti tunggal: Menyatukan medan](merge-entities.md)

> [!div class="nextstepaction"]
> [Langkah seterusnya untuk berbilang entiti: Keadaan yang sepadan](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Penyahduplikasi output sebagai entiti

Proses deduplication mewujudkan entiti deduplicated baru untuk setiap entiti sumber. Entiti ini boleh ditemui bersama dengan **ConflationMatchPairs:CustomerInsights** dalam bahagian **Sistem** di halaman **Entiti**, dengan nama **Deduplication_DataSource_Entity**.

Entiti output penyahduplikasi mengandungi maklumat berikut:

- ID / Kekunci
  - Kekunci utama dan medan ID Alternatif. Medan ID alternatif terdiri daripada semua ID alternatif yang dikenal pasti untuk rekod.
  - Medan Deduplication_GroupId menunjukkan kumpulan atau kluster yang dikenal pasti dalam sesebuah entiti yang mengumpulkan semua rekod yang serupa berdasarkan medan penyahduplikasi yang ditetapkan. Ia digunakan untuk tujuan pemprosesan sistem. Jika tiada peraturan penyahduplikasi secara manual yang ditetapkan dan peraturan penyahduplikasi yang ditakrifkan sistem diguna pakai, anda tidak akan menemui medan ini dalam entiti keluaran penyahduplikasi.
  - Deduplication_WinnerId: Medan ini mengandungi ID pemenang daripada kumpulan atau kluster yang dikenal pasti. Jika Deduplication_WinnerId adalah sama dengan nilai penting Utama untuk rekod, ia bermaksud bahawa rekod ialah rekod pemenang.
- Medan yang digunakan untuk mentakrifkan peraturan penyahduplikasi.
- Medan Peraturan dan Skor untuk menunjukkan yang peraturan penyahduplikasi telah diguna pakai dan skor yang dikembalikan oleh algoritma sepadan.

[!INCLUDE[footer-include](includes/footer-banner.md)]
