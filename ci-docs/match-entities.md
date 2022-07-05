---
title: Padankan syarat untuk penyatuan data
description: Padan entiti untuk mencipta profil pelanggan disatukan.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: 770a18f3a7471714a7e044ae034da168a2601010
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082412"
---
# <a name="match-conditions-for-data-unification"></a>Padankan syarat untuk penyatuan data

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Langkah dalam penyatuan ini mentakrifkan tertib dan peraturan padanan untuk pemadanan merentas entiti. Langkah ini memerlukan sekurang-kurangnya dua entiti.

> [!NOTE]
> Sebaik sahaja anda mencipta syarat padanan anda dan memilih **Seterusnya**, anda tidak boleh mengalih keluar entiti atau atribut yang dipilih. Jika perlu, pilih **Kembali** untuk menyemak entiti dan atribut terpilih sebelum meneruskan.

## <a name="include-enriched-entities-preview"></a>Sertakan entiti yang diperkaya (pratonton)

Jika anda memperkayakan entiti di peringkat sumber data untuk membantu meningkatkan hasil penyatuan anda, pilihnya. Untuk maklumat lanjut, lihat [Pengayaan untuk sumber data](data-sources-enrichment.md). Jika anda memilih entiti yang diperkaya pada **halaman Rekod** pendua, anda tidak perlu memilihnya lagi.

1. **Pada halaman Keadaan** pemadanan, pilih **Gunakan entiti** yang diperkaya di bahagian atas halaman.

1. **Daripada anak tetingkap Gunakan entiti** yang diperkaya, pilih satu atau lebih entiti yang diperkaya.

1. Pilih **Selesai**.

## <a name="specify-the-match-order"></a>Tentukan pesanan padanan

Setiap padanan menyatukan dua atau lebih entiti ke dalam satu entiti yang disatukan. Pada masa yang sama, ia menyimpan rekod pelanggan yang unik. Perintah padanan menunjukkan urutan di mana sistem cuba memadankan rekod.

> [!IMPORTANT]
> Entiti pertama dalam senarai dipanggil entiti utama. Entiti utama berfungsi sebagai asas untuk set data profil bersatu anda. Entiti tambahan yang dipilih akan ditambah ke entiti ini.
>
> Pertimbangan penting:
>
> - Pilih entiti dengan data profil yang paling lengkap dan boleh dipercayai mengenai pelanggan anda sebagai entiti utama.
> - Pilih entiti yang mempunyai beberapa atribut yang sama dengan entiti lain (contohnya, nama, nombor telefon atau alamat e-mel) sebagai entiti utama.

1. **Pada halaman Keadaan** pemadanan, gunakan anak panah bergerak ke atas dan ke bawah untuk mengalihkan entiti mengikut tertib yang anda inginkan, atau seret dan lepaskannya. Sebagai contoh, pilih **Kenalan:eCommerce** sebagai entiti utama dan **CustomerLoyalty:Kesetiaan** sebagai entiti kedua.

1. Untuk mempunyai setiap rekod dalam entiti sebagai pelanggan unik tanpa mengira jika padanan ditemui, pilih **Sertakan semua rekod**. Sebarang rekod dalam entiti ini yang tidak sepadan dengan rekod dalam mana-mana entiti lain dimasukkan ke dalam profil bersatu. Rekod yang tidak mempunyai padanan dipanggil singletons.
  
Entiti *utama Kenalan:eCommerce* dipadankan dengan entiti *seterusnya CustomerLoyalty:Loyalty*. Set data yang terhasil daripada langkah padanan pertama dipadankan dengan entiti berikut jika anda mempunyai lebih daripada dua entiti.

:::image type="content" source="media/m3_match.png" alt-text="Petikan skrin tertib padanan yang dipilih untuk entiti." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Tentukan peraturan untuk pasangan padanan

Peraturan padanan menentukan logik bagaimana sepasang entiti akan dipadankan. Peraturan terdiri daripada satu atau lebih syarat.

Amaran di sebelah nama entiti bermakna tiada peraturan padanan ditakrifkan untuk pasangan padanan.

1. Pilih **Tambah peraturan** untuk pasangan entiti untuk mentakrifkan peraturan padanan.

1. **Dalam anak tetingkap Tambah peraturan**, konfigurasikan syarat untuk peraturan.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Petikan skrin anak tetingkap Tambah peraturan.":::

   - **Pilih Entiti/Medan (baris pertama)**: Pilih entiti berkaitan dan atribut untuk menentukan sifat rekod yang mungkin unik kepada pelanggan. Contohnya, nombor telefon atau alamat e-mel. Elakkan padanan mengikut atribut jenis aktiviti. Contohnya, ID pembelian mungkin tidak akan sepadan dalam jenis rekod lain.

   - **Pilih Entiti/Medan (baris kedua)**: Pilih atribut yang berkaitan dengan atribut entiti yang ditentukan dalam baris pertama.

   - **Normalkan**: Pilih daripada pilihan normalisasi berikut untuk atribut yang dipilih.
     - **Numeral**: Menukar sistem angka lain, seperti angka Rom, kepada angka Arab. *VIII* menjadi *8*.
     - **Simbol**: Mengalih keluar semua simbol dan aksara khas. *Head&Shoulder* menjadi *HeadShoulder*.
     - **Teks kepada huruf kecil**: Menukar semua aksara kepada huruf kecil. *SEMUA HURUF BESAR dan Huruf Besar Kecil* menjadi *semua huruf besar dan huruf besar kecil*.
     - **Taip (Telefon, Nama, Alamat, Organisasi)**: Menyeragamkan nama, tajuk, nombor telefon, alamat dan organisasi.
     - **Unikod kepada ASCII**: Menukar notasi unikod kepada aksara ASCII. */u00B2* menjadi *2*.
     - **Ruang putih**: Mengalih keluar semua ruang. *Hello World* menjadi *HelloWorld*.

   - **Ketepatan**: Tetapkan tahap ketepatan untuk digunakan bagi syarat ini.
     - **Asas**: Pilih daripada *Rendah (30%)*, *Sederhana (60%)*, *Tinggi (80%)*, dan *Tepat (100%)*. Pilih **Tepat** untuk hanya padankan rekod yang sepadan dengan 100 peratus.
     - **Tersuai**: Tetapkan peratusan yang perlu dipadankan oleh rekod. Sistem hanya akan sepadan dengan rekod yang melepasi ambang ini.

   - **Nama**: Nama untuk peraturan.

1. Untuk memadankan entiti hanya jika atribut memenuhi berbilang syarat, pilih **Tambah** > **syarat** untuk menambah lebih banyak syarat pada peraturan padanan. Syarat yang disambungkan dengan logik DAN operator dengan itu hanya dilaksanakan jika semua syarat dipenuhi.

1. Secara pilihan, pertimbangkan pilihan lanjutan seperti [pengecualian](#add-exceptions-to-a-rule) atau [syarat](#specify-custom-match-conditions) padanan tersuai.

1. Pilih **Selesai** untuk memuktamadkan peraturan.

1. Secara pilihan, [tambah lebih banyak peraturan](#add-rules-to-a-match-pair).

1. Klik **Seterusnya**.

> [!div class="nextstepaction"]
> [Langkah seterusnya: Menyatukan medan](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Tambah peraturan pada pasangan padanan

Peraturan padanan mewakili set syarat. Untuk memadankan entiti mengikut syarat berdasarkan berbilang atribut, tambah lebih banyak peraturan.

1. Pilih **Tambah peraturan** pada entiti yang anda ingin tambahkan peraturan.

1. Ikuti langkah-langkah dalam [Tentukan peraturan untuk pasangan padanan](#define-rules-for-match-pairs).

> [!NOTE]
> Urutan peraturan diambil kira. Algoritma yang sepadan cuba memadankan rekod pelanggan yang diberikan berdasarkan peraturan pertama anda dan terus ke peraturan kedua hanya jika tiada padanan dikenal pasti dengan peraturan pertama.

## <a name="advanced-options"></a>Opsyen lanjutan

### <a name="add-exceptions-to-a-rule"></a>Menambah pengecualian pada peraturan

Dalam kebanyakan kes, padanan entiti membawa kepada profil pelanggan yang unik dengan data yang disatukan. Untuk menangani kes-kes positif palsu dan negatif palsu secara dinamik, anda boleh menentukan pengecualian untuk peraturan padanan. Pengecualian digunakan selepas memproses peraturan perlawanan dan mengelakkan pemadanan semua rekod, yang memenuhi kriteria pengecualian.

Sebagai contoh, jika peraturan padanan anda menggabungkan nama akhir, bandar dan tarikh lahir, sistem akan mengenal pasti kembar dengan nama akhir yang sama yang tinggal di bandar yang sama dengan profil yang sama. Anda boleh menentukan pengecualian yang tidak sepadan dengan profil jika nama pertama dalam entiti yang anda gabungkan tidak sama.

1. **Dalam anak tetingkap Edit peraturan**, pilih **Tambah** > **tambah pengecualian**.

1. Tentukan kriteria pengecualian.

1. Pilih **Selesai** untuk menyimpan peraturan.

### <a name="specify-custom-match-conditions"></a>Tentukan syarat padanan tersuai

Anda boleh menentukan syarat yang mengatasi logik padanan lalai. Terdapat empat pilihan yang ada:

|Pilihan  |Description |Contoh  |
|---------|---------|---------|
|Sentiasa padan     | Mentakrifkan nilai yang sentiasa dipadankan.         |  Sentiasa sepadan dengan *Mike* dan *MikeR*.       |
|Tidak boleh padan     | Mentakrifkan nilai yang tidak pernah sepadan.        | Jangan pernah menandingi *John* dan *Jonathan*.        |
|Pintasan tersuai     | Mentakrifkan nilai yang harus selalu diabaikan oleh sistem dalam fasa padanan. |  Abaikan nilai *11111* dan *Tidak Diketahui* semasa perlawanan.        |
|Pemetaan alias    | Menentukan nilai yang harus dipertimbangkan oleh sistem sebagai nilai yang sama.         | Anggap *Joe* sama dengan *Yusuf*.        |

1. Pilih **Tersuai**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Butang tersuai":::

1. Pilih jenis **Tersuai dan pilih** Muat turun templat **.** Anda memerlukan templat berasingan untuk setiap pilihan perlawanan.

1. Buka fail templat yang dimuat turun dan isikan butirannya. Templat mengandungi medan yang menentukan entiti dan entiti nilai kekunci utama yang akan digunakan dalam padanan tersuai. Contohnya, jika anda mahukan kunci utama *12345* daripada entiti *Jualan* untuk sentiasa sepadan dengan kunci utama *34567* daripada entiti *Kenalan*, isi templat:
    - Entity1: Jualan
    - Entity1Key: 12345
    - Entity2: Kenalan
    - Entity2Key: 34567

   Fail templat yang sama boleh menentukan rekod padanan tersuai daripada berbilang entiti.

   Jika anda mahu menentukan pemadanan tersuai untuk penyahduplikasi pada entiti, menyediakan entiti yang sama dengan kedua-dua Entity1 dan Entity2 dan menetapkan nilai kunci utama yang berbeza.

1. Selepas menambah semua penggantian, simpan fail templat.

1. Pergi ke **Data** > **Sumber data** dan inges fail templat sebagai entiti baharu.

1. Selepas memuat naik fail, pilih **Pilihan Tersuai** sekali lagi. Pilih entiti yang diperlukan dari menu lungsur dan pilih **Selesai**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Petikan skrin dialog untuk memilih penggantian bagi senario padanan tersuai.":::

1. Menggunakan padanan tersuai bergantung pada opsyen padanan yang anda mahu gunakan.

   - Untuk **Sentiasa padankan** atau **Jangan sekali-kali sepadan**, teruskan ke langkah seterusnya.
   - Untuk **pemetaan** Pintasan **atau** Alias, pilih **Edit** pada peraturan padanan sedia ada atau cipta peraturan baru. Dalam juntai bawah Normalisasi, pilih **opsyen Pintasan** tersuai atau **Pemetaan** Alias dan pilih **Selesai**.

1. Pilih **Selesai** pada **anak tetingkap Tersuai** untuk menggunakan konfigurasi padanan tersuai.

> [!div class="nextstepaction"]
> [Langkah seterusnya: Menyatukan medan](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
