---
title: Padan entiti untuk penyatuan data
description: Padan entiti untuk mencipta profil pelanggan disatukan.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: ab4ab0dba1bd91b1893cd4b16b8d51381d5b6ef8
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376933"
---
# <a name="match-entities"></a>Padankan entiti

Peringkat pemadanan menentukan bagaimana untuk menggabungkan set data anda kepada set data profil pelanggan disatukan. siSelepas melengkapkan [langkah peta](map-entities.md) dalam proses penyatuan data, anda bersedia untuk memadankan entiti anda. Peringkat pemadanan memerlukan sekurang-kurangnya dua entiti dipetakan.

Halaman padanan terdiri daripada tiga bahagian: 
- Metrik utama yang meringkaskan bilangan rekod yang dipadankan
- Urutan padanan dan peraturan untuk padanan silang entiti
- Peraturan untuk penyahduplikasi entiti sepadan

## <a name="specify-the-match-order"></a>Tentukan pesanan padanan

Setiap padanan menyatukan dua atau lebih entiti ke dalam satu entiti yang disatukan. Pada masa yang sama, ia menyimpan rekod pelanggan yang unik. Perintah padanan menunjukkan urutan di mana sistem cuba memadankan rekod.

> [!IMPORTANT]
> Entiti yang anda pilih sebagai entiti utama anda akan bertindak sebagai asas bagi set data profil anda yang disatukan. Entiti tambahan yang dipilih semasa peringkat pemadanan akan ditambah ke entiti ini. Ini tidak bermakna entiti bersatu akan menyertakan *semua* data yang disertakan dalam entiti ini.
>
> Terdapat dua pertimbangan yang boleh membantu anda memilih hierarki entiti anda:
>
> - Pilih entiti dengan data profil yang paling lengkap dan boleh dipercayai tentang pelanggan anda sebagai entiti utama.
> - Pilih entiti yang mempunyai beberapa atribut yang sama dengan entiti lain (contohnya, nama, nombor telefon atau alamat e-mel) sebagai entiti utama.

1. Pergi ke **Data** > **Satukan** > **Padanan** dan pilih **Tetapkan pesanan** untuk memulakan fasa perlawanan.
1. Pilih **Pesanan entiti**. Sebagai contoh, pilih **eCommerce:eCommerceContacts** sebagai entiti utama dan **LoyaltyScheme:loyCustomers** sebagai entiti kedua. 
1. Untuk mempunyai setiap rekod dalam entiti sebagai pelanggan unik dan dipadankan dengan setiap entiti berikut, pilih **Sertakan semua**.
1. Pilih **Selesai**. 

Selepas menentukan tertib padanan, pasangan padanan yang ditakrifkan dipaparkan dalam bahagian Butiran rekod yang sepadan pada **DataUnifyMatch** **·** > **.** > **·** Metrik utama kosong sehingga proses padanan selesai.

:::image type="content" source="media/match-page.png" alt-text="Petikan skrin halaman Padanan dalam kawasan Satukan proses penyatuan data.":::
  
Entiti utama *eCommerce:eCommerceContacts* dipadankan dengan entiti seterusnya *LoyaltyScheme:loyCustomers*. Set data yang terhasil daripada langkah padanan pertama dipadankan dengan entiti berikut jika anda mempunyai lebih daripada dua entiti.

## <a name="define-rules-for-match-pairs"></a>Tentukan peraturan untuk pasangan padanan

Peraturan padanan menentukan logik bagaimana sepasang entiti akan dipadankan.

Amaran **Peraturan keperluan** bersebelahan dengan nama entiti mencadangkan bahawa tiada peraturan padanan ditakrifkan untuk pasangan padanan. 

:::image type="content" source="media/match-rule-add.png" alt-text="Petikan skrin bahagian Butiran rekod yang dipadankan dengan kawalan untuk menambah peraturan yang diserlahkan.":::

1. Pilih **Tambah peraturan** di bawah entiti dalam **seksyen Butiran** rekod yang dipadankan untuk mentakrifkan peraturan padanan.

1. Dalam anak tetingkap **Cipta peraturan**, konfigurasikan syarat untuk peraturan.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Petikan skrin peraturan padanan yang dibuka dengan syarat-syarat yang ditambah.":::

   - **Entiti/Medan (baris pertama)**: Pilih entiti dan atribut yang berkaitan untuk menentukan sifat rekod yang mungkin unik kepada pelanggan. Contohnya, nombor telefon atau alamat e-mel. Elakkan padanan mengikut atribut jenis aktiviti. Contohnya, ID pembelian mungkin tidak akan sepadan dalam jenis rekod lain.

   - **Entiti/Medan (baris kedua)** : Pilih atribut yang berkaitan dengan atribut entiti yang dinyatakan dalam baris pertama.

   - **Normalkan**: Pilih daripada pilihan normalisasi berikut untuk atribut yang dipilih. 
     - Angka: Tukar sistem angka lain, seperti angka Rom, kepada angka Arab. *VIII* menjadi *8*.
     - Simbol: Alih keluar semua simbol dan aksara khas. *Head&Shoulder* menjadi *HeadShoulder*.
     - Teks kepada huruf kecil: Tukar semua aksara kepada huruf kecil. *SEMUA HURUF BESAR dan Huruf Besar Kecil* menjadi *semua huruf besar dan huruf besar kecil*.
     - Taip (Telefon, Nama, Alamat, Organisasi): Menyeragamkan nama, tajuk, nombor telefon, alamat, dll. 
     - Unikod kepada ASCII: Tukar notasi unikod kepada aksara ASCII. */u00B2* menjadi *2*.
     - Ruang kosong: Alih keluar semua ruang. *Hello World* menjadi *HelloWorld*.

   - **Ketepatan**: Tetapkan tahap ketepatan untuk digunakan bagi syarat ini. 
     - **Asas**: Pilih daripada *Rendah*, *Sederhana*, *Tinggi* dan *Tepat*. Pilih **Tepat** untuk hanya padankan rekod yang sepadan dengan 100 peratus. Pilih satu daripada tahap lain untuk memadankan rekod yang tidak 100 peratus sama.
     - **Tersuai**: Tetapkan peratusan yang perlu dipadankan oleh rekod. Sistem hanya akan sepadan dengan rekod yang melepasi ambang ini.

1. Berikan **Nama** untuk peraturan.

1. [Tambah lebih banyak syarat](#add-conditions-to-a-rule) atau pilih **Selesai** untuk memuktamadkan peraturan.

1. Secara pilihan, [tambah lebih banyak peraturan](#add-rules-to-a-match-pair).

1. Pilih **Simpan** untuk menggunakan perubahan anda.

### <a name="add-conditions-to-a-rule"></a>Tambah syarat peraturan

Untuk memadankan entiti hanya jika atribut memenuhi berbilang syarat, tambah lebih banyak syarat pada peraturan padanan. Syarat yang disambungkan dengan logik DAN operator dengan itu hanya dilaksanakan jika semua syarat dipenuhi.

1. Pergi ke **Data** > **Satukan** > **Padanan** dan pilih **Edit** pada peraturan yang anda mahu tambah syarat.

1. Pada anak tetingkap **Edit peraturan**, pilih **Tambah syarat**.

1. Pilih **Selesai** untuk menyimpan peraturan.

### <a name="add-rules-to-a-match-pair"></a>Tambah peraturan pada pasangan padanan

Peraturan padanan mewakili set syarat. Untuk memadankan entiti mengikut syarat berdasarkan berbilang atribut, tambah lebih banyak peraturan.

1.  Pergi ke **Data** > **Satukan** > **Padanan** dan pilih **Tambah peraturan** pada entiti yang anda mahu tambah peraturan.

2. Ikuti langkah-langkah dalam [Tentukan peraturan untuk pasangan padanan](#define-rules-for-match-pairs).

> [!NOTE]
> Urutan peraturan diambil kira. Algoritma yang sepadan cuba dipadankan berdasarkan peraturan pertama anda dan terus ke peraturan kedua hanya jika tiada perlawanan dikenal pasti dengan peraturan pertama.

### <a name="change-the-entity-order-in-match-rules"></a>Tukar pesanan entiti dalam peraturan padanan

Anda boleh menyusun semula entiti untuk peraturan padanan untuk mengubah tertib yang diproses. Peraturan yang berkonflik disebabkan oleh pesanan yang ditukar akan dialih keluar. Anda perlu mencipta semula peraturan yang dialih keluar dengan konfigurasi dikemas kini.

1. Pergi ke **Data** > **Satukan** > **Padankan** dan pilih **Edit**.

1. Dalam anak tetingkap **Peraturan edit**, pilih kawalan **Alih ke atas/ke bawah** atau seret dan lepaskan entiti untuk menukar pesanan.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Pilihan untuk mengubah dalam entiti pesanan yang diproses dalam fasa padanan.":::

1. Pilih **Selesai** untuk menyimpan peraturan.

## <a name="define-deduplication-on-a-match-entity"></a>Takrifkan penyahpenduaan pada entiti padan

Selain daripada [peraturan padanan silang entiti](#define-rules-for-match-pairs), anda juga boleh menentukan peraturan penyahduplikasi. *Penyahduplikasi* ialah satu proses lain semasa memadankan rekod. Ia mengenal pasti rekod duplikasi dan menggabungkan rekod tersebut ke dalam satu rekod. Rekod sumber dikaitkan dengan rekod yang digabungkan dengan ID alternatif.

Rekod deduplicated digunakan dalam proses pemadanan merentas entiti. Deduplication berlaku pada entiti individu dan boleh dikonfigurasikan untuk setiap entiti yang digunakan dalam pasangan padanan.

Menentukan peraturan nyahpenduaan adalah tidak wajib. Jika tidak ada peraturan yang dikonfigurasikan, peraturan yang ditakrifkan sistem digunakan. Mereka menggabungkan semua rekod ke dalam satu rekod sebelum menghantar data entiti kepada padanan silang entiti untuk prestasi yang dipertingkatkan.

### <a name="add-deduplication-rules"></a>Tambah peraturan nyahpenduaan

1. Pergi ke **Data** > **Satukan** > **Padanan**.

1. **Dalam seksyen Butiran** rekod Deduplicated, pilih **Setkan entiti**. Sekiranya peraturan penyahduplikasi telah dicipta, pilih **Edit**.

1. Dalam anak tetingkap **Keutamaan gabungan**, pilih entiti yang anda mahu jalankan penyahduplikasi.

   1. Tentukan cara menggabungkan rekod duplikasi dan pilih salah satu daripada tiga pilihan:
      - **Paling terisi**: Kenal pasti rekod dengan medan atribut yang paling terisi sebagai rekod pemenang. Ia merupakan pilihan gabungan lalai.
      - **Paling terkini**: Mengenal pasti rekod pemenang berdasarkan paling terkini. Memerlukan medan tarikh atau angka untuk mentakrifkan yang terkini.
      - **Kurang terkini**: Mengenal pasti rekod pemenang berdasarkan kurang terkini. Memerlukan medan tarikh atau angka untuk mentakrifkan yang terkini.

   1. Secara pilihan, untuk mentakrifkan peraturan deduplikasi pada atribut individu entiti, pilih **Lanjutan**. Sebagai contoh, anda boleh memilih untuk menyimpan e-mel terkini DAN alamat paling lengkap daripada rekod yang berbeza. Kembangkan entiti untuk melihat semua atributnya dan tentukan pilihan yang hendak digunakan untuk atribut individu. Jika anda memilih pilihan berasaskan recency, anda juga perlu menentukan medan tarikh/masa yang mentakrifkan recency. 
 
      > [!div class="mx-imgBorder"]
      > ![Langkah 1 peraturan nyahduplikasi.](media/match-selfconflation.png "Langkah 1 peraturan nyahpenduaan")

   1. Pilih **Selesai** untuk menggunakan keutamaan cantum anda untuk penyahdendaban.
 
1. Sebaik sahaja entiti dipilih dan keutamaan gabungan ditetapkan, pilih **Tambah peraturan** untuk mentakrifkan peraturan penyahduplikasi pada peringkat entiti.
   - **Pilih medan** menyenaraikan semua medan yang tersedia daripada entiti tersebut. Pilih medan yang anda mahu semak untuk duplikasi. Pilih medan yang mungkin unik untuk setiap pelanggan tunggal. Contohnya, alamat e-mel atau gabungan nama, bandar dan nombor telefon.
   - Tentukan tetapan normalisasi dan ketepatan.
   - Takrifkan lebih banyak syarat dengan memilih **Tambah syarat**.
 
   > [!div class="mx-imgBorder"]
   > ![Langkah 2 peraturan nyahduplikasi.](media/match-selfconflation-rules.png "Langkah 2 peraturan nyahpenduaan")

  Anda boleh mencipta berbilang peraturan nyahpenduaan untuk entiti. 

1. Jalankan proses pemadanan sekarang mengumpulkan rekod berdasarkan syarat yang ditakrifkan dalam peraturan nyahpenduaan. Selepas mengumpulkan rekod, dasar penggabungan digunakan untuk mengenal pasti rekod pemenang.

1. Rekod pemenang ini kemudian diserahkan kepada pemadanan silang entiti, bersama dengan rekod bukan pemenang (contohnya, ID alternatif) untuk meningkatkan kualiti pemadanan.

1. Sebarang peraturan padanan tersuai yang ditakrifkan menulis ganti peraturan penyahduplikasi. Jika peraturan nyahpenduaan mengenal pasti padanan rekod dan peraturan padanan tersuai ditetapkan untuk tidak sepadan dengan rekod tersebut, kedua-dua rekod ini tidak akan dipadankan.

1. Selepas [menjalankan proses](#run-the-match-process) padanan, anda akan melihat statistik deduplication dalam jubin metrik utama.

### <a name="deduplication-output-as-an-entity"></a>Penyahduplikasi output sebagai entiti

Proses penyahduplikasi mencipta entiti baharu untuk setiap entiti daripada pasangan padanan untuk mengenal pasti rekod yang dinyahduplikasikan. Entiti ini boleh ditemui bersama dengan **ConflationMatchPairs:CustomerInsights** dalam bahagian **Sistem** di halaman **Entiti**, dengan nama **Deduplication_DataSource_Entity**.

Entiti output penyahduplikasi mengandungi maklumat berikut:
- ID / Kekunci
  - Medan penting utama dan medan ID alternatif. Medan ID alternatif terdiri daripada semua ID alternatif yang dikenal pasti untuk rekod.
  - Medan Deduplication_GroupId menunjukkan kumpulan atau kluster yang dikenal pasti dalam sesebuah entiti yang mengumpulkan semua rekod yang serupa berdasarkan medan penyahduplikasi yang ditetapkan. Ia digunakan untuk tujuan pemprosesan sistem. Jika tiada peraturan penyahduplikasi secara manual yang ditetapkan dan peraturan penyahduplikasi yang ditakrifkan sistem diguna pakai, anda tidak akan menemui medan ini dalam entiti keluaran penyahduplikasi.
  - Deduplication_WinnerId: Medan ini mengandungi ID pemenang daripada kumpulan atau kluster yang dikenal pasti. Jika Deduplication_WinnerId adalah sama dengan nilai penting Utama untuk rekod, ia bermaksud bahawa rekod ialah rekod pemenang.
- Medan yang digunakan untuk mentakrifkan peraturan penyahduplikasi.
- Medan Peraturan dan Skor untuk menunjukkan yang peraturan penyahduplikasi telah diguna pakai dan skor yang dikembalikan oleh algoritma sepadan.
 
## <a name="include-enriched-entities-preview"></a>Sertakan entiti yang diperkaya (Pratonton)

Jika anda memperkayakan entiti pada peringkat sumber data, pilihnya sebelum menjalankan proses padanan. Entiti yang diperkaya dapat meningkatkan hasil penyatuan anda. Untuk maklumat lanjut, lihat [Pengayaan untuk sumber](data-sources-enrichment.md) data. 

Entiti yang diperkaya mengandungi medan sumber data asal dan medan yang diperkaya. Oleh itu, jika anda memilih untuk bekerja dengan entiti yang diperkaya, konfigurasi yang sedia ada tidak terjejas. Walau bagaimanapun, anda mungkin perlu mengemas kini peraturan padanan untuk menggunakan medan yang diperkaya.

1. Pergi ke **DataUnifyMatch** > **·** > **dan** pilih **Gunakan entiti** yang diperkaya di bahagian atas halaman.

1. **Daripada anak tetingkap Gunakan entiti** yang diperkaya, pilih satu atau lebih entiti yang diperkaya.

1. Pilih **Selesai**. Di mana sahaja entiti sumber digunakan (seperti perintah atau peraturan padanan), ia secara automatik ditukar kepada entiti yang diperkaya.
  
## <a name="run-the-match-process"></a>Jalankan proses padanan

Dengan peraturan padanan yang dikonfigurasikan, termasuk peraturan pemadanan silang entiti dan penyahduplikasi, anda boleh menjalankan proses padanan. 

Pergi ke **Data** > **Satukan** > **Padanan** dan pilih **Jalankan** untuk memulakan proses. Algoritma yang sepadan mengambil sedikit masa untuk dilengkapkan dan anda tidak boleh mengubah konfigurasi sehingga ia selesai. Untuk membuat perubahan, anda boleh membatalkan jalanan. Pilih status kerja dan pilih **Batalkan kerja** pada anak tetingkap **Butiran kemajuan**.

Anda akan menemui hasil jalanan yang berjaya, entiti profil pelanggan yang disatukan, di halaman **Entiti**. Entiti pelanggan anda yang disatukan anda dipanggil **Pelanggan** dalam bahagian **Profil**. Jalanan padanan pertama yang berjaya mencipta entiti *Pelanggan* yang disatukan. Semua jalanan padanan yang berikutnya melanjutkan entiti itu.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Semak semula dan sahkan padanan anda

Pergi ke **Data** > **Satukan** > **Padanan** untuk menilai kualiti pasangan padanan anda dan memperhalusi pasangan tersebut jika perlu.

Jubin di bahagian atas halaman menunjukkan metrik utama, meringkaskan bilangan rekod dan duplikasi yang dipadankan.

:::image type="content" source="media/match-KPIs.png" alt-text="Petikan skrin metrik utama yang dipangkas pada halaman Padanan dengan bilangan dan butiran.":::

- **Rekod sumber unik** menunjukkan bilangan rekod sumber individu yang diproses dalam jalanan padanan yang terakhir.
- **Rekod yang dipadankan dan tidak dipadankan** menyerlahkan bilangan rekod unik yang kekal selepas memproses peraturan padanan.
- **Rekod yang dipadankan sahaja** menunjukkan bilangan padanan merentasi semua pasangan padanan anda.

Anda boleh menilai hasil dan peraturan setiap pasangan padanan dalam jadual **Butiran rekod yang dipadankan**. Bandingkan bilangan rekod yang datang daripada pasangan padanan menentang peratusan rekod yang berjaya dipadankan.

Semak peraturan pasangan padanan untuk melihat peratusan rekod yang berjaya dipadankan di peringkat peraturan. Pilih elipsis (...) dan kemudian pilih **Pratonton padanan** untuk melihat semua rekod ini di peringkat peraturan. Kami mengesyorkan agar anda melihat beberapa rekod untuk mengesahkan bahawa rekod tersebut dipadankan dengan betul.

Cuba ambang ketepatan yang berbeza berdasarkan syarat untuk mencari nilai optimum.

  1. Pilih elipsis (...) untuk peraturan yang anda mahu cuba dan pilih **Edit**.

  2. Tukar nilai ketepatan dalam syarat yang anda mahu semak semula.

  3. Pilih **Pratonton** untuk melihat bilangan rekod yang dipadankan dan tidak dipadankan untuk syarat yang dipilih.

## <a name="manage-match-rules"></a>Urus peraturan padanan

Anda boleh mengkonfigurasikan semula dan menambah baik kebanyakan parameter padanan.

:::image type="content" source="media/match-rules-management.png" alt-text="Syot layar menu juntai bawah dengan pilihan peraturan yang sepadan.":::

- **Ubah pesanan peraturan anda** jika anda menakrifkan berbilang peraturan. Anda boleh menyusun semula peraturan padanan dengan memilih pilihan **Alih ke Atas** dan **Alih ke Bawah** atau dengan seret dan lepas.

- **Tukar syarat peraturan** dengan memilih **Edit** dan pilih medan yang berbeza.

- **Menyahaktifkan peraturan** untuk mengekalkan peraturan perlawanan semasa mengecualikan daripada proses pemadanan.

- **Duplikasikan peraturan anda** jika anda telah mentakrifkan peraturan padanan dan ingin mencipta peraturan yang sama dengan pengubahsuaian, pilih **Duplikasikan**.

- **Padamkan peraturan** dengan memilih simbol **Padam**.

## <a name="advanced-options"></a>Opsyen lanjutan

### <a name="add-exceptions-to-a-rule"></a>Menambah pengecualian pada peraturan

Dalam kebanyakan kes, pemadanan entiti membawa kepada profil pengguna unik dengan data yang disatukan. Untuk menangani kes-kes positif palsu dan negatif palsu secara dinamik, anda boleh menentukan pengecualian untuk peraturan padanan. Pengecualian digunakan selepas memproses peraturan perlawanan dan mengelakkan pemadanan semua rekod, yang memenuhi kriteria pengecualian.

Sebagai contoh, jika peraturan padanan anda menggabungkan nama akhir, bandar dan tarikh lahir, sistem akan mengenal pasti kembar dengan nama akhir yang sama yang tinggal di bandar yang sama dengan profil yang sama. Anda boleh menentukan pengecualian yang tidak sepadan dengan profil jika nama pertama dalam entiti yang anda gabungkan tidak sama.

1. Pergi ke **Data** > **Satukan** > **Padanan** dan pilih **Edit** pada peraturan yang anda mahu tambah syarat.

1. **Dalam anak tetingkap Edit peraturan**, pilih **Tambah pengecualian**.

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

1. Pergi ke **Data** > **Satukan** > **Padanan** dan pilih **Padanan tersuai** dalam bahagian **Butiran rekod yang dipadankan**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Petikan skrin bahagian peraturan padanan dengan kawalan Padanan tersuai yang diserlahkan.":::

1. **Dalam anak tetingkap Tersuai**, pergi ke **tab Rekod**.

1. Pilih pilihan padanan tersuai daripada juntai **bawah jenis** tersuai dan pilih **Muat turun templat**. Anda memerlukan templat berasingan untuk setiap pilihan perlawanan.

1. Buka fail templat yang dimuat turun dan isikan butirannya. Templat mengandungi medan yang menentukan entiti dan entiti nilai kekunci utama yang akan digunakan dalam padanan tersuai. Contohnya, jika anda mahukan kunci utama *12345* daripada entiti *Jualan* untuk sentiasa sepadan dengan kunci utama *34567* daripada entiti *Kenalan*, isi templat:
    - Entity1: Jualan
    - Entity1Key: 12345
    - Entity2: Kenalan
    - Entity2Key: 34567

   Fail templat yang sama boleh menentukan rekod padanan tersuai daripada berbilang entiti.
   
   Jika anda mahu menentukan pemadanan tersuai untuk penyahduplikasi pada entiti, menyediakan entiti yang sama dengan kedua-dua Entity1 dan Entity2 dan menetapkan nilai kunci utama yang berbeza.

1. Selepas menambah semua penggantian, simpan fail templat.

1. Pergi ke **Data** > **Sumber data** dan inges fail templat sebagai entiti baharu.

1. Selepas memuat naik fail dan entiti tersedia, pilih pilihan **Padanan tersuai** semula. Anda akan dapat melihat pilihan untuk menentukan entiti yang anda hendak masukkan. Pilih entiti yang diperlukan dari menu lungsur dan pilih **Selesai**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Petikan skrin dialog untuk memilih penggantian bagi senario padanan tersuai.":::

1. Menggunakan padanan tersuai bergantung pada opsyen padanan yang anda mahu gunakan. 

   - Untuk **Sentiasa padankan** atau **Jangan sekali-kali sepadan**, teruskan ke langkah seterusnya.
   - Untuk **pintasan** tersuai atau **pemetaan** Alias, pilih **Edit** pada peraturan padanan sedia ada atau cipta peraturan baru. Dalam juntai bawah Normalisasi, pilih **opsyen Pintasan** tersuai atau **Pemetaan** Alias dan pilih **Selesai**.

1. Pilih **Simpan** pada halaman **Padanan** untuk menggunakan konfigurasi padanan tersuai.

1. Pilih **Jalankan** pada halaman **Padanan** untuk memulakan proses pemadanan. Peraturan padanan lain yang ditentukan ditulis ganti oleh konfigurasi padanan tersuai.

#### <a name="known-issues"></a>Isu yang diketahui

- Konflik diri tidak menunjukkan data yang dinormalisasi dalam entiti deduplikasi. Walau bagaimanapun, ia menggunakan normalisasi secara dalaman semasa deduplication. Ia adalah dengan reka bentuk untuk semua normalisasi. 
- Jika seting jenis semantik dialih keluar dalam **fasa Peta** apabila peraturan padanan menggunakan pemetaan Alias atau pintasan Tersuai, penormalan tidak akan digunakan. Ia hanya berlaku jika anda mengosongkan jenis semantik selepas mengkonfigurasi normalisasi dalam peraturan perlawanan kerana jenis semantik tidak akan diketahui.


## <a name="next-step"></a>Langkah seterusnya

Selepas melengkapkan proses perlawanan untuk sekurang-kurangnya satu pasangan perlawanan, teruskan ke [**langkah Cantum**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
