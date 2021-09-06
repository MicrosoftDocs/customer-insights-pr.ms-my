---
title: Ramalan nilai sepanjang hayat pelanggan (CLV)
description: Meramalkan potensi pendapatan untuk pelanggan aktif pada masa akan datang.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 740d6a5a749e156414b0e80193334051b7f2632fe4d1f4291d74b99250f35bc2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035380"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Ramalan nilai sepanjang hayat pelanggan (CLV) (Pratonton)

Meramalkan nilai potensi (pendapatan) yang akan dibawa oleh pelanggan aktif individu kepada perniagaan anda melalui tempoh masa depan yang ditakrifkan. Ciri ini boleh membantu anda mencapai pelbagai matlamat: 
- Mengenal pasti pelanggan bernilai tinggi dan memproses wawasan ini
- Mencipta segmen pelanggan yang strategik berdasarkan pada nilai potensi mereka untuk menjalankan kempen diperibadikan dengan jualan, pemasaran dan usaha sokongan yang disasarkan
- Membimbing pembangunan produk dengan memberi tumpuan kepada ciri-ciri yang meningkatkan nilai pelanggan
- Mengoptimumkan strategi jualan atau pemasaran dan memperuntukkan belanjawan dengan lebih tepat untuk jangkauan pelanggan
- Mengiktiraf dan memberi ganjaran kepada pelanggan bernilai tinggi melalui program kesetiaan atau ganjaran 

## <a name="prerequisites"></a>Prasyarat

Sebelum bermula, imbas semula maksud CLV untuk perniagaan anda. Pada masa ini, kami menyokong ramalan CLV berasaskan transaksi. Nilai yang diramalkan bagi pelanggan adalah berdasarkan sejarah transaksi perniagaan. Untuk mencipta ramalan, anda memerlukan sekurang-kurangnya keizinan [Penyumbang](permissions.md).

Oleh kerana mengkonfigurasi dan menjalankan model CLV tidak mengambil banyak masa, pertimbangkan untuk mencipta beberapa model dengan pelbagai pilihan input dan membandingkan hasil model untuk melihat senario model yang paling sesuai dengan keperluan perniagaan anda.

###  <a name="data-requirements"></a>Keperluan data

Data berikut diperlukan, dan di tempat yang ditanda pilihan, disyorkan untuk peningkatan prestasi model. Semakin banyak data model boleh memproses, semakin tepat ramalan anda. Oleh itu, kami menggalakkan anda untuk mengambil lebih banyak data aktiviti pelanggan, jika ada.

- Pengecam Pelanggan: Pengecam unik untuk memadankan transaksi kepada pelanggan individu

- Sejarah Transaksi: Log transaksi sejarah dengan skema data semantik di bawah
    - **ID Transaksi**: Pengecam unik bagi setiap transaksi
    - **Tarikh transaksi**: Tarikh, sebaik-baiknya cap masa bagi setiap transaksi
    - **Amaun transaksi**: Nilai kewangan (contohnya, hasil atau margin untung) bagi setiap transaksi
    - **Label yang ditugaskan untuk pulangan**  (pilihan): Nilai boolean menandakan sama ada transaksi adalah pulangan 
    - **ID Produk** (pilihan): ID Produk bagi produk yang terlibat dalam transaksi

- Data tambahan (pilihan), sebagai contoh
    - Aktiviti web: sejarah lawatan tapak web, sejarah e-mel
    - Aktiviti kesetiaan: keakruan mata ganjaran kesetiaan dan sejarah penebusan
    - Log khidmat pelanggan, panggilan perkhidmatan, aduan atau sejarah pengembalian
- Data tentang aktiviti pelanggan (pilihan):
    - Pengecam aktiviti untuk membezakan aktiviti jenis yang sama
    - Pengecam pelanggan untuk memetakan aktiviti kepada pelanggan anda
    - Maklumat aktiviti yang mengandungi nama dan tarikh aktiviti
    - Skema data semantik untuk aktiviti termasuk: 
        - **Kunci utama:**: Pengecam unik untuk aktiviti
        - **Cap masa**: Tarikh dan masa peristiwa yang dikenal pasti oleh kunci utama
        - **Peristiwa (nama aktiviti)**: Nama peristiwa yang anda mahu gunakan
        - **Butiran (amaun atau nilai)**: Butiran tentang aktiviti pelanggan

- Ciri data yang disyorkan:
    - Data sejarah yang mencukupi: Sekurang-kurangnya satu tahun data transaksi. Sebaik-baiknya dua hingga tiga tahun data transaksi untuk meramalkan CLV bagi satu tahun.
    - Berbilang pembelian setiap pelanggan: Secara ideal, sekurang-kurangnya dua hingga tiga transaksi setiap ID pelanggan, sebaik-baiknya merentas berbilang tarikh.
    - Bilangan pelanggan: Sekurang-kurangnya 100 pelanggan unik, sebaik-baiknya lebih daripada 10,000 pelanggan. Model ini akan gagal dengan kurang daripada 100 pelanggan dan data sejarah yang tidak mencukupi
    - Kesempurnaan data: Kurang daripada 20% nilai hilang dalam medan yang diperlukan dalam data input   

> [!NOTE]
> - Model ini memerlukan sejarah transaksi pelanggan anda. Hanya satu entiti sejarah transaksi boleh dikonfigurasikan buat masa ini. Jika terdapat berbilang entiti pembelian/transaksi, anda boleh satukannya dalam Power Query sebelum pengingesan data.
> - Untuk data aktiviti pelanggan tambahan (pilihan), bagaimanapun anda boleh menambah sebanyak mungkin entiti aktiviti pelanggan yang anda mahu untuk pertimbangan oleh model.

## <a name="create-a-customer-lifetime-value-prediction"></a>Cipta ramalan Nilai Sepanjang Hayat Pelanggan (CLV)

1. Dalam wawasan khalayak, pergi ke **Kecerdasan** > **Ramalan**.

1. Pilih jubin **Nilai sepanjang hayat pelanggan** dan pilih **Gunakan model**. 

1. Dalam anak tetingkap **Nilai sepanjang hayat pelanggan (pratonton)**, pilih **Mulakan**.

1. **Namakan model ini** dan **Nama entiti output** untuk membezakannya daripada model atau entiti lain.

1. Pilih **Seterusnya**.

### <a name="define-model-preferences"></a>Takrifkan keutamaan model

1. Tetapkan **Tempoh masa ramalan** untuk menentukan sejauh mana ke masa depan anda mahu meramalkan CLV.    
   Secara lalai, unit ini ditetapkan sebagai bulan. Anda boleh mengubahnya kepada tahun untuk melihat lebih jauh pada masa akan datang.

   > [!TIP]
   > Untuk meramalkan CLV dengan tepat bagi tempoh masa yang anda tetapkan, anda memerlukan tempoh setanding data sejarah. Contohnya, jika anda ingin meramalkan CLV untuk 12 bulan akan datang, disyorkan anda mempunyai sekurang-kurangnya 18 – 24 bulan data sejarah.

1. Tentukan maksud **Pelanggan aktif** untuk perniagaan anda. Tetapkan tempoh masa di mana pelanggan mesti mempunyai sekurang-kurangnya satu transaksi untuk dianggap aktif. Model hanya akan meramalkan CLV untuk pelanggan aktif. 
   - **Biarkan model mengira selang pembelian (disyorkan)**: Model menganalisis data anda dan menentukan tempoh masa berdasarkan pada pembelian sejarah.
   - **Tetapkan selang secara manual**: Jika anda mempunyai definisi perniagaan tertentu bagi pelanggan aktif, pilih pilihan ini dan tetapkan tempoh masa dengan sewajarnya.

1. Tentukan peratusan bagi **Pelanggan bernilai tinggi** untuk membolehkan model memberikan hasil yang sesuai dengan definisi perniagaan anda.
    - **Pengiraan model (disyorkan)**: Model menganalisis data anda dan menentukan perkara yang pelanggan bernilai tinggi mungkin jadi untuk perniagaan anda berdasarkan pada sejarah transaksi pelanggan anda. Model ini menggunakan peraturan heuristik (diilhamkan oleh peraturan 80/20 atau prinsip pareto) untuk mencari perkadaran pelanggan bernilai tinggi. Peratusan pelanggan yang menyumbang kepada 80% pendapatan kumulatif untuk perniagaan anda dalam tempoh sejarah dianggap sebagai pelanggan bernilai tinggi. Biasanya, kurang daripada 30-40% pelanggan menyumbang kepada 80% pendapatan kumulatif. Walau bagaimanapun, nombor ini mungkin berbeza bergantung pada perniagaan dan industri anda.    
    - **Peratus pelanggan aktif teratas**: Takrifkan pelanggan bernilai tinggi untuk perniagaan anda sebagai peratusan pelanggan berbayar aktif yang teratas. Sebagai contoh, anda boleh menggunakan pilihan ini untuk menentukan pelanggan bernilai tinggi sebagai 20% teratas daripada pelanggan yang membayar pada masa depan.

    Jika perniagaan anda mentakrifkan pelanggan bernilai tinggi dengan cara yang berbeza, [beritahu kami kerana kami ingin mendengar](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Pilih **Seterusnya** untuk meneruskan ke langkah yang seterusnya.

### <a name="add-required-data"></a>Tambah data yang diperlukan

1. PDalam langkah **Data diperlikan**, pilih **Tambah data** untuk **Sejarah transaksi pelanggan** dan pilih entiti yang menyediakan maklumat sejarah transaksi seperti yang diterangkan dalam [prasyarat](#prerequisites).

1. Petakan medan semantik kepada atribut dalam entiti sejarah pembelian anda dan pilih **Seterusnya**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Imej langkah konfigurasi untuk memetakan atribut data untuk data yang diperlukan.":::
 
1. Jika medan di bawah tidak diisi, konfigurasikan hubungan daripada entiti sejarah pembelian anda kepada entiti *Pelanggan* dan pilih **Simpan**.
    1. Pilih entiti sejarah transaksi.
    1. Pilih medan yang mengecam pelanggan dalam entiti sejarah pembelian. Ia perlu dikaitkan kepada ID pelanggan utama bagi entiti Pelanggan anda.
    1. Pilih entiti yang sepadan entiti pelanggan utama anda.
    1. Masukkan nama yang menghuraikan perhubungan.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Imej langkah konfigurasi untuk menentukan hubungan dengan entiti pelanggan.":::

1. Pilih **Seterusnya**.

### <a name="add-optional-data"></a>Tambah data pilihan

Data mencerminkan interaksi pelanggan utama (seperti log web, khidmat pelanggan dan peristiwa) menambahkan konteks kepada rekod transaksi. Lebih banyak corak ditemui dalam data aktiviti pelanggan anda boleh meningkatkan ketepatan ramalan. 

1. Dalam langkah **Data Tambahan (pilihan)**, pilih **Tambah data**. Pilih entiti aktiviti pelanggan yang menyediakan maklumat aktiviti pelanggan seperti yang diterangkan dalam [prasyarat](#prerequisites).

1. Petakan medan semantik kepada atribut dalam entiti aktiviti pelanggan anda dan pilih **Seterusnya**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Imej langkah konfigurasi untuk memetakan medan untuk data tambahan.":::

1. Pilih jenis aktiviti yang sepadan dengan jenis aktiviti pelanggan yang anda tambah. Pilih daripada jenis aktiviti sedia ada atau tambah jenis aktiviti baharu.

1. Konfigurasikan hubungan daripada entiti aktiviti pelanggan anda kepada entiti *Pelanggan*.
    
    1. Pilih medan yang mengenal pasti pelanggan dalam jadual aktiviti pelanggan. Ia boleh berkait secara langsung dengan ID pelanggan utama entiti *Pelanggan* anda.
    1. Pilih entiti *Pelanggan* yang memadankan entiti *Pelanggan* utama anda.
    1. Masukkan nama yang menghuraikan perhubungan.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Imej langkah dalam aliran konfigurasi untuk menambah data tambahan dan mengkonfigurasi aktiviti dengan contoh yang diisi.":::

1. Pilih **Simpan**.    
    Tambahkan lebih banyak data jika terdapat aktiviti pelanggan lain yang anda mahu sertakan.

1. Pilih **Seterusnya**.

### <a name="set-update-schedule"></a>Tetapkan jadual kemas kini

1. Dalam langkah **Jadual kemas kini data**, pilih kekerapan untuk melatih semula model anda berdasarkan data terkini. Tetapan ini adalah penting untuk mengemas kini ketepatan ramalan kerana data baru telah dimasukkan dalam wawasan khalayak. Kebanyakan perniagaan boleh melatih semula sekali setiap bulan dan mendapatkan ketepatan yang baik untuk ramalan mereka.

1. Pilih **Seterusnya**.

### <a name="review-and-run-the-model-configuration"></a>Semak dan jalankan konfigurasi model

1. Dalam langkah **Semak butiran model anda**, sahkan konfigurasi ramalan. Anda boleh kembali ke mana-mana bahagian konfigurasi ramalan dengan memilih **Edit** di bawah nilai yang ditunjukkan. Anda juga boleh memilih langkah konfigurasi daripada penunjuk kemajuan.

1. Jika semua nilai dikonfigurasikan dengan betul, pilih **Simpan dan jalan** untuk mula menjalankan model. Pada tab **Ramalan saya**, anda boleh melihat status proses ramalan saya. Proses mungkin mengambil masa beberapa jam untuk dilengkapkan bergantung kepada amaun data yang digunakan dalam ramalan.

## <a name="review-prediction-status-and-results"></a>Semak ramalan status dan keputusan

### <a name="review-prediction-status"></a>Semak status ramalan

1.  Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.
2.  Pilih ramalan yang anda mahu semak semula.

- **Nama ramalan**: Nama ramalan yang diberikan semasa menciptanya.
- **Jenis ramalan**: Jenis model yang digunakan untuk ramalan
- **Entiti output**: Nama entiti untuk menyimpan output ramalan. Pergi ke **Data** > **Entiti** untuk mencari entiti dengan nama ini.
- **Medan ramalan**: Medan ini diisikan hanya untuk beberapa jenis ramalan, dan tidak digunakan dalam ramalan nilai sepanjang hayat pelanggan.
- **Status**: Status jalanan ramalan.
    - **Dibariskan**: Ramalan sedang menunggu proses lain untuk selesai.
    - **Menyegar semula**: Ramalan sedang berjalan untuk mengcipta keputusan yang akan mengalir ke dalam entiti output.
    - **Gagal**: Jalanan ramalan gagal. [Ulasan log](manage-predictions.md#troubleshoot-a-failed-prediction) untuk maklumat lanjut.
    - **Berjaya**: Ramalan telah berjaya. Pilih **Lihat** di bawah elips menegak untuk menyemak ramalan anda.
- **Diedit**: Tarikh konfigurasi untuk ramalan telah diubah.
- **Terakhir disegar semula**: Tarikh ramalan menyegar semula hasil dalam entiti output.

### <a name="review-prediction-results"></a>Semak hasil ramalan

1. Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.

1. Pilih ramalan yang anda mahu semak hasilnya.

Terdapat tiga bahagian utama data dalam halaman hasil.

- **Prestasi model latihan**: A, B atau C adalah gred yang mungkin. Gred ini menunjukkan prestasi ramalan dan boleh membantu anda membuat keputusan untuk menggunakan keputusan yang disimpan dalam entiti output. Pilih **Ketahui tentang skor ini** untuk lebih memahami metrik prestasi model asas dan cara gred prestasi model akhir diperolehi.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imej kotak maklumat skor model dengan gred A.":::

  Menggunakan definisi pelanggan bernilai tinggi yang disediakan sambil mengkonfigurasi ramalan, sistem menilai cara model AI yang dilaksanakan dalam meramalkan pelanggan bernilai tinggi berbanding dengan model asas.    

  Gred ditentukan berdasarkan peraturan berikut:
  - **A** apabila model ini meramalkan secara tepat sekurang-kurangnya 5% lebih banyak pelanggan bernilai tinggi berbanding dengan model garis dasar.
  - **B** apabila model ini meramalkan secara tepat antara 0-5% lebih banyak pelanggan bernilai tinggi berbanding dengan model garis dasar.
  - **C** apabila model ini meramalkan secara tepat kurang pelanggan bernilai tinggi berbanding dengan model garis dasar.

  Anak tetingkap **Penarafan model** menunjukkan butiran lanjut tentang prestasi model AI dan model garis dasar. Model asas menggunakan pendekatan berasaskan bukan AI untuk mengira nilai seumur hidup pelanggan berdasarkan pembelian sejarah yang dibuat oleh pelanggan.     
  Formula standard yang digunakan untuk mengira CLV mengikut model garis dasar:    

  _**CLV untuk setiap pelanggan** = Purata pembelian bulanan yang dibuat oleh pelanggan dalam tetingkap pelanggan aktif * Bilangan bulan dalam tempoh ramalan CLV * Kadar pengekalan keseluruhan semua pelanggan*_

  Model AI dibandingkan dengan model asas berdasarkan pada dua metrik prestasi model.
  
  - **Kadar kejayaan dalam meramalkan pelanggan bernilai tinggi**

    Lihat perbezaan dalam meramalkan pelanggan bernilai tinggi menggunakan model AI berbanding model asas. Sebagai contoh, kadar kejayaan 84% bermakna bahawa daripada semua pelanggan bernilai tinggi dalam data latihan, model AI dapat menangkap 84% secara tepat. Kami kemudian membandingkan kadar kejayaan ini dengan kadar kejayaan model asas untuk melaporkan perubahan relatif. Nilai ini digunakan untuk menugaskan gred kepada model.

  - **Metrik ralat**
    
    Metrik lain membolehkan anda menyemak prestasi keseluruhan model dari segi kesilapan dalam meramalkan nilai masa depan. Kami menggunakan metrik Ralat Dikuasakan Min Punca (RMSE) keseluruhan untuk menilai kesilapan ini. RMSE ialah cara standard untuk mengukur kesilapan model dalam meramalkan data kuantitatif. RMSE model AI dibandingkan dengan RMSE model asas dan perbezaan relatif dilaporkan.

  Model AI mengutamakan kedudukan pelanggan yang tepat mengikut nilai yang mereka bawa ke perniagaan anda. Jadi, hanya kadar kejayaan meramalkan pelanggan bernilai tinggi digunakan untuk mendapatkan gred model akhir. Metrik RMSE sensitif kepada orang luar. Dalam senario di mana anda mempunyai peratusan kecil pelanggan dengan nilai pembelian yang sangat tinggi, metrik RMSE keseluruhan mungkin tidak memberikan gambaran penuh prestasi model.   

- **Nilai pelanggan mengikut peratusan**: Menggunakan definisi pelanggan bernilai tinggi anda, pelanggan dikumpulkan menjadi bernilai rendah dan bernilai tinggi, berdasarkan ramalan CLV mereka, dan ditunjukkan dalam carta. Dengan berlegar di atas bar dalam histogram, anda dapat melihat bilangan pelanggan dalam setiap kumpulan dan purata CLV kumpulan itu. Data ini boleh membantu jika anda ingin [mencipta segmen pelanggan](segments.md) berdasarkan pada ramalan CLV mereka.

- **Faktor paling berpengaruh**: Pelbagai faktor dipertimbangkan semasa mencipta ramalan CLV anda berdasarkan data input yang diberikan kepada model AI. Setiap faktor mempunyai kepentingannya yang dikira untuk ramalan teragregat yang dicipta oleh model. Anda boleh menggunakan faktor ini untuk membantu mengesahkan hasil ramalan anda. Faktor-faktor ini juga memberi lebih banyak pandangan mengenai faktor-faktor yang paling berpengaruh yang menyumbang ke arah meramalkan CLV di semua pelanggan anda.

## <a name="manage-predictions"></a>Urus ramalan

Ada kemungkinan untuk mengoptimumkan, menyelesaikan masalah, menyegarkan semula atau memadam ramalan. Semak laporan kebolehgunaan data input untuk mengetahui cara membuat ramalan lebih cepat dan lebih dipercayai. Untuk mendapatkan maklumat lanjut, lihat [Urus ramalan](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
