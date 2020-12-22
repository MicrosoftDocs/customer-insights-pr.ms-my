---
title: Padan entiti untuk penyatuan data
description: Padan entiti untuk mencipta profil pelanggan disatukan.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406475"
---
# <a name="match-entities"></a>Padankan entiti

Selepas melengkapkan peringkat pemetaan, anda sudah bersedia untuk memadankan entiti anda. Peringkat pemadanan menentukan bagaimana untuk menggabungkan set data anda kepada set data profil pelanggan disatukan. Peringkat pemadanan memerlukan sekurang-kurangnya [dua entiti dipetakan](map-entities.md).

## <a name="specify-the-match-order"></a>Tentukan pesanan padanan

Pergi ke **Satukan** > **Padan** dan pilih **Tetapkan pesanan** untuk memulakan peringkat pemadanan.

Setiap padanan menyatukan dua atau lebih entiti ke entiti tunggal, sementara meneruskan setiap rekod pelanggan unik. Dalam contoh berikut, kami memilih tiga entiti: **ContactCSV: TestData** sebagai entiti **Utama**, **WebAccountCSV: TestData** sebagai **Entity 2**, dan **CallRecordSmall: TestData** sebagai **Entity 3**. Diagram di atas pemilihan menerangkan bagaimana pesanan padanan akan dilaksanakan.

> [!div class="mx-imgBorder"]
> ![Edit pesanan padanan data](media/configure-data-match-order-edit-page.png "Edit pesanan padanan data")
  
Entiti **Utama** dipadankan dengan **Entity 2**. Set data yang terhasil daripada padanan pertama dipadankan dengan **Entity 3**.
Dalam contoh ini, kami hanya memilih dua padanan, tetapi sistem boleh menyokong lebih banyak.

> [!IMPORTANT]
> Entiti yang anda pilih sebagai entiti **Utama** anda akan bertindak sebagai asas bagi set data induk disatukan. Entiti tambahan yang dipilih semasa peringkat pemadanan akan ditambah ke entiti ini. Pada masa yang sama, ini tidak bermakna yang entiti disatukan akan merangkumi *semua* data yang dimasukkan ke dalam entiti ini.
>
> Terdapat dua pertimbangan yang boleh membantu anda memilih hierarki entiti anda:
>
> - Apakah entiti yang anda pertimbangkan untuk mempunyai data paling lengkap dan boleh dipercayai tentang pelanggan anda?
> - Adakah entiti yang baru anda kenal pasti mempunyai atribut yang juga dikongsi oleh entiti lain, (sebagai contoh, nama, nombor telefon, atau alamat e-mel)? Jika tidak, pilih entiti kedua paling anda percayai.

Pilih **Selesai** untuk menyimpan pesanan padanan anda.

## <a name="define-rules-for-your-first-match-pair"></a>Takrif peraturan untuk pasangan padanan pertama anda

Selepas menentukan pesanan padanan, anda akan dapat melihat padanan yang ditakrifkan pada halaman **Padan**. Jubin di bahagian atas skrin akan menjadi kosong sehingga anda menjalankan pesanan padanan anda.

> [!div class="mx-imgBorder"]
> ![Tarifkan peraturan](media/configure-data-match-need-rules.png "Tarifkan peraturan")

Amaran **Perlukan Peraturan** mencadangkan tiada peraturan padanan ditakrifkan untuk pasangan padanan. Peraturan padanan menentukan logik bagaimana sepasang entiti akan dipadankan.

1. Untuk menakrifkan peraturan pertama anda, buka anak tetingkap **Definisi Peraturan** dengan memilih baris padanan yang berkaitan dalam jadual padanan (1) dan kemudian pilih **Cipta peraturan baharu** (2).

   > [!div class="mx-imgBorder"]
   > ![Cipta peraturan baharu](media/configure-data-match-new-rule2.png "Cipta peraturan baharu")

2. Dalam anak tetingkap **Edit Peraturan**, konfigurasikan syarat untuk peraturan itu. Setiap syarat diwakili oleh dua baris yang termasuk pilihan mandatori.

   > [!div class="mx-imgBorder"]
   > ![Anak tetingkap peraturan baharu](media/configure-data-match-new-rule-condition.png "Anak tetingkap peraturan baharu")

   Entiti/Medan (pertama) - Atribut yang akan digunakan untuk padanan daripada entiti padanan pertama. Contoh boleh termasuk nombor telefon atau alamat e-mel. Pilih atribut yang berkemungkinan besar unik kepada pelanggan.

   > [!TIP]
   > Elak memadankan pada asas atribut jenis-aktiviti. Dalam kata lain, jika atribut kelihatan seperti aktiviti, jadi ia mungkin kriteria yang lemah untuk dipadankan.  

   Entiti/Medan (Kedua) - Atribut yang akan digunakan untuk padanan daripada entiti pasangan padanan kedua.

   Menormalkan - **Kaedah penormalan**: Pelbagai pilihan penormalan tersedia untuk atribut terpilih. Contohnya, mengalih keluar tanda baca atau mengalih keluar ruang

   Untuk penormalan nama Organisasi (Pratonton), anda juga boleh memilih **Jenis (Telefon, Nama, Organisasi)**

   > [!div class="mx-imgBorder"]
   > ![Penormalan-B2B](media/match-normalization-b2b.png "Penormalan-B2B")

   Paras kejituan - Paras kejituan yang akan digunakan untuk syarat ini. Menetapkan paras kejituan untuk syarat padanan boleh mempunyai dua jenis: **Asas** dan **Tersuai**.  
   - Asas: Menyediakan anda dengan empat pilihan untuk dipilih: Rendah, Sederhana, Tinggi, dan Tepat. Pilih **Tepat** untuk hanya memadankan rekod yang 100 peratus sepadan. Pilih satu daripada tahap lain untuk memadankan rekod yang tidak 100 peratus sama.
   - Tersuai: Gunakan penggelongsor untuk menakrifkan peratus tersuai yang diperlukan oleh rekod untuk memadankan atau memasukkan nilai dalam medan **Tersuai**. Sistem akan hanya memadankan rekod yang memintas ambang ini sebagai pasangan padanan tergabung. Nilai pada penggelongsor adalah antara 0 dan 1. Oleh itu 0.64 mewakili 64 peratus.

3. Pilih **Selesai** untuk menyimpan peraturan.

### <a name="add-multiple-conditions"></a>Menambah berbilang syarat

Untuk memadankan entiti anda jika berbilang syarat dipenuhi, tambah lebih banyak syarat yang dipaut melalui operator DAN.

1. Pada anak tetingkap **Edit peraturan**, pilih **Tambah syarat**. Anda juga boleh memadam syarat dengan memilih butang alih keluar di sebelah syarat sedia ada.

2. Pilih **Selesai** untuk menyimpan peraturan.

## <a name="add-multiple-rules"></a>Menambah berbilang peraturan

Setiap syarat yang digunakan pada pasangan tunggal atribut, manakala peraturan mewakili set syarat. Untuk memadankan entiti anda dengan set atribut yang berbeza, anda boleh menambah lebih banyak peraturan.

1. Dalam wawasan khalayak, pergi ke **Data** > **Unify** > **Padan**.

2. Pilih entiti yang anda mahu kemas kini dan pilih **Tambah peraturan**.

3. Ikuti prosedur seperti yang digariskan dalam [Takrif peraturan untuk pasangan padanan pertama anda](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Mengambil kira pesanan peraturan. Algoritma pemadanan cuba memadankan asas peraturan pertama anda dan seterusnya peraturan kedua jika tiada padanan dikenal pasti di bawah peraturan pertama.

## <a name="define-deduplication-on-a-match-entity"></a>Takrifkan penyahpenduaan pada entiti padan

Berserta menetapkan peraturan pemadanan entiti silang seperti yang diterangkan dalam bahagian di atas, anda juga boleh menetapkan peraturan penyahpenduaan. *Penyahpenduaan* adalah proses. Ia mengenal pasti rekod pendua, menggabungkannya ke dalam satu rekod dan menghubungkan semua rekod sumber kepada rekod yang digabungkan dengan ID alternatif kepada rekod yang digabungkan.

Selepas rekod dinyahpendua dikenal pasti, rekod tersebut akan digunakan dalam proses pemadanan silang entiti. Nyahpenduaan dilaksanakan pada peringkat entiti dan boleh digunakan pada setiap entiti yang digunakan dalam proses Pemadanan.

### <a name="add-deduplication-rules"></a>Tambah peraturan nyahpenduaan

1. Dalam wawasan khalayak, pergi ke **Data** > **Unify** > **Padan**.

1. Dalam bahagian **Pendua yang digabungkan**, pilih **Tetapkan entiti**.

1. Dalam bahagian **Keutamaan gabungan**, pilih entiti yang anda mahu gunakan nyahpenduaan.

1. Tentukan cara untuk menggabungkan rekod pendua dan pilih salah satu daripada tiga pilihan gabungan:
   - *Paling terisi*: Mengenal pasti rekod dengan atribut yang paling terisi sebagai rekod pemenang. Ini ialah pilihan gabungan lalai.
   - *Paling terkini*: Mengenal pasti rekod pemenang berdasarkan paling terkini. Memerlukan medan tarikh atau angka untuk mentakrifkan yang terkini.
   - *Kurang terkini*: Mengenal pasti rekod pemenang berdasarkan kurang terkini. Memerlukan medan tarikh atau angka untuk mentakrifkan yang terkini.
 
   > [!div class="mx-imgBorder"]
   > ![Langkah 1 peraturan nyahpenduaan](media/match-selfconflation.png "Langkah 1 peraturan nyahpenduaan")
 
1. Sebaik sahaja entiti dipilih dan keutamaan gabungannya ditetapkan, pilih **Cipta peraturan baharu** untuk mentakrifkan peraturan nyahpenduaan pada peringkat entiti.
   - **Pilih medan** menyenaraikan semua medan tersedia daripada entiti yang anda mahu nyahpendua data sumber.
   - Tentukan tetapan normalisasi dan ketepatan dengan cara yang sama seperti yang ditetapkan dalam pemadanan silang entiti.
   - Anda boleh mentakrifkan syarat tambahan dengan memilih **Tambah syarat**.
 
   > [!div class="mx-imgBorder"]
   > ![Langkah 2 peraturan nyahpenduaan](media/match-selfconflation-rules.png "Langkah 2 peraturan nyahpenduaan")

  Anda boleh mencipta berbilang peraturan nyahpenduaan untuk entiti. 

1. Jalankan proses pemadanan sekarang mengumpulkan rekod berdasarkan syarat yang ditakrifkan dalam peraturan nyahpenduaan. Selepas mengumpulkan rekod, dasar penggabungan digunakan untuk mengenal pasti rekod pemenang.

1. Rekod pemenang ini kemudian diserahkan kepada pemadanan silang entiti.

1. Sebarang peraturan padanan tersuai yang ditakrifkan untuk sentiasa padan dan tidak sepadan menolak peraturan nyahpenduaan. Jika peraturan nyahpenduaan mengenal pasti padanan rekod dan peraturan padanan tersuai ditetapkan untuk tidak sepadan dengan rekod tersebut, kedua-dua rekod ini tidak akan dipadankan.

1. Selepas menjalankan proses padanan, anda akan melihat statistik nyahpenduaan.
   
> [!NOTE]
> Menentukan peraturan nyahpenduaan adalah tidak wajib. Jika tidak ada peraturan yang dikonfigurasikan, peraturan yang ditakrifkan sistem digunakan. Ia meruntuhkan semua rekod yang berkongsi kombinasi nilai yang sama (padanan tepat) daripada kunci utama dan medan dalam peraturan pemadanan ke dalam rekod tunggal sebelum menghantar data entiti kepada pemadanan silang entiti untuk prestasi dipertingkat dan kewarasan sistem.

## <a name="run-your-match-order"></a>Jalankan pesanan padanan anda

Selepas mentakrifkan peraturan padanan, termasuk peraturan pemadanan silang entiti dan nyahpenduaan, anda boleh menjalankan pesanan padanan. Pada halaman **Padan**, pilih **Jalankan** untuk memulakan proses. Algoritma pemadanan mungkin mengambil sedikit masa untuk selesai. Anda tidak boleh mengubah sifat pada halaman **Padan** sehingga proses padanan selesai. Anda akan menemui entiti profil pelanggan disatukan yang dicipta pada halaman **Entiti**. Entiti pelanggan disatukan anda dikenal sebagai **ConflationMatchPairs : CustomerInsights**.

Untuk membuat perubahan tambahan dan jalankan semula langkah, anda boleh membatalkan padanan dalam kemajuan. Pilih teks **Menyegarkan semula ...** dan pilih **Batal kerja** di bahagian bawah bahagian tetingkap yang muncul.

Apabila proses padanan selesai, teks **Menyegarkan semula ...** akan ditukar kepada **Berjaya** dan anda boleh menggunakan semua fungsi halaman sekali lagi.

Proses padanan pertama menghasilkan penciptaan entiti induk disatukan. Semua padanan seterusnya dijalankan dalam pengembangan entiti itu.

> [!TIP]
> Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies). Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja. Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.

## <a name="review-and-validate-your-matches"></a>Semak semula dan sahkan padanan anda

Nilaikan kualiti pasangan padanan anda dan perhalusinya:

- Pada halaman **Padan**, anda akan menemui dua jubin menunjukkan wawasan awal tentang data anda.

  - **Pelanggan unik**: menunjukkan bilangan profil unik yang dikenal pasti oleh sistem.
  - **Pemadanan rekod**: menunjukkan bilangan padanan dalam semua pasangan padanan anda.

- Dalam jadual **Pesanan padanan**, anda boleh menilai hasil bagi setiap pasangan padanan dengan membandingkan bilangan rekod yang diperoleh daripada entiti pasangan-padanan terhadap peratusan padanan rekod yang berjaya.

- Dalam seksyen **Peraturan** untuk entiti dalam jadual **Pesanan padanan**, anda akan menemui peratusan pemadanan rekod yang berjaya pada peringkat peraturan. Dengan memilih simbol jadual di sebelah peraturan, anda boleh melihat semua rekod pada peringkat peraturan. Kami mengesyorkan supaya anda menyemak semula subset rekod untuk menilai yang ia dipadankan dengan betul.

- Eksperimen dengan ambang kejituan yang berbeza sekitar syarat anda untuk mengenal pasti nilai optimum.

  1. Pilih elipsis (...) untuk peraturan pasangan padanan yang anda mahu eksperimen dan pilih **Edit**.

  2. Pilih syarat yang anda mahu eksperimen. Setiap kriteria diwakili oleh satu baris dalam anak tetingkap **Peraturan padanan**.

  3. Apa yang anda akan lihat pada halaman **Pratonton kriteria** bergantung kepada paras kejituan yang anda pilih untuk syarat. Cari billangan rekod yang sepadan dan tidak sepadan untuk syarat yang dipilih.

     Dapatkan pemahaman menyeluruh tentang kesan bagi paras ambang yang berbeza. Anda boleh membandingkan berapa banyak rekod yang akan dipadankan di bawah setiap paras ambang , dan lihat rekod di bawah setiap pilihan. Pilih setiap jubin dan semak data dalam seksyen jadual.

## <a name="optimize-your-matches"></a>Optimumkan padanan anda

Tingkatkan kualiti dengan mengkonfigurasi semula sesetengah parameter padanan anda:

- **Ubah pesanan padanan** dengan memilih **Edit** dan ubah medan pesanan padanan.

  > [!div class="mx-imgBorder"]
  > ![Edit data pesanan padanan](media/configure-data-match-order-edit.png "Edit pesanan padanan data")

- **Ubah pesanan peraturan anda** jika anda menakrifkan berbilang peraturan. Anda boleh memesan semula peraturan padanan dengan memilih pilihan **Gerak Ke Atas** dan **Gerak ke Bawah** dalam grid peraturan padanan.

  > [!div class="mx-imgBorder"]
  > ![Ubah pesanan peraturan](media/configure-data-change-rule-order.png "Ubah pesanan peraturan")

- **Duplikasi peraturan anda** jika anda telah menakrifkan peraturan padanan dan mahu mencipta peraturan yang sama dengan pengubahsuaian. Berbuat demikian dengan memilih **Duplikasi**.

  > [!div class="mx-imgBorder"]
  > ![Duplikasi peraturan](media/configure-data-duplicate-rule.png "Duplikasi peraturan")

- **Edit peraturan anda** dengan memilih simbol **Edit**. Anda boleh gunakan perubahan berikut:

  - Ubah atribut syarat: Pilih atribut baharu dalam baris syarat tertentu.
  - Ubah ambang syarat: Laraskan penggelongsor kejituan.
  - Ubah kaedah penormalan syarat: Kemas kini kaedah penormalan.

## <a name="specify-your-custom-match-records"></a>Tentukan rekod padanan tersuai anda

Anda boleh menentukan syarat bagi rekod tertentu haruslah sentiasa sepadan atau tidak boleh sepadan. Peraturan ini boleh dimuat naik dalam pukal untuk proses padanan.

1. Pilih pilihan **Padanan tersuai** pada skrin **Pesanan padanan**.

   > [!div class="mx-imgBorder"]
   > ![Cipta padanan tersuai](media/custom-match-create.png "Cipta padanan tersuai")

2. Jika anda tiada entiti dimuat naik, anda akan melihat kota dialog baharu **Padanan tersuai** yang memerlukan anda untuk mengisi beberapa butiran. Jika anda telah menyediakan butiran ini lebih awal, langkau ke langkah 8.

   > [!div class="mx-imgBorder"]
   > ![Kotak dialog padanan tersuai baharu](media/custom-match-new-dialog-box.png "Kotak dialog padanan tersuai baharu")

3. Pilih **Lengkapkan templat** untuk mendapatkan fail templat yang boleh menentukan rekod yang mana daripada entiti yang mana perlu sentiasa sepadan atau tidak boleh sepadan. Anda perlu mengisi rekod "sentiasa sepadan" dan rekod "tidak boleh sepadan" secara berasingan dalam dua fail yang berbeza.

4. Templat mengandungi medan yang menentukan entiti dan entiti nilai kekunci utama yang akan digunakan dalam padanan tersuai. Contohnya, jika anda mahukan kekunci utama 12345 daripada entiti Jualan untuk sentiasa sepadan dengan kekunci utama 34567 daripada entiti Kenalan, anda perlu menentukan seperti berikut:
    - Entity1: Jualan
    - Entity1Key: 12345
    - Entity2: Kenalan
    - Entity2Key: 34567

   Fail templat yang sama boleh menentukan rekod padanan tersuai daripada berbilang entiti.

5. Selepas menambah kesemua penggantian yang anda mahu gunakan, simpan fail templat.

6.Pergi ke **Data** > **Sumber data** dan inges fail templat sebagai entiti baharu. Sebaik sahaja diinges, anda boleh menggunakannya untuk menentukan konfigurasi Padanan.

7. Selepas memuat naik fail dan entiti tersedia, pilih pilihan **Padanan tersuai** semula. Anda akan dapat melihat pilihan untuk menentukan entiti yang anda hendak masukkan. Pilih entiti yang diperlukan daripada menu juntai bawah.

   > [!div class="mx-imgBorder"]
   > ![Penggantian padanan tersuai](media/custom-match-overrides.png "Penggantian padanan tersuai")

8. Pilih entiti yang anda mahu gunakan untuk **Sentiasa sepadan** dan **Tidak boleh sepadan**, pilih **Selesai**.

9. Pilih **Simpan** pada halaman **Padan** untuk konfigurasi pemadanan yang baru anda sediakan.

10. Pilih **Jalankan** pada halaman **Padan** untuk memulakan proses pemadanan, dan konfigurasi padanan tersuai akan berkuat kuasa. Mana-mana peraturan padanan sistem diganti oleh set konfigurasi.

11. Sebaik sahaja pemadanan selesai, anda boleh menentusahkan entiti **ConflationMatchPair** untuk mengesahkan bahawa penggantian telah digunakan dalam padanan penggabungan.

## <a name="next-step"></a>Langkah seterusnya

Selepas proses pemadanan selesai untuk sekurang-kurangnya satu pasangan padanan, anda boleh selesaikan kemungkinan percanggahan dalam data anda dengan menyemak lalu topik [**Gabung**](merge-entities.md).
