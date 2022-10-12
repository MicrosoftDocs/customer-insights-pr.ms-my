---
title: Ramaln nilai sepanjang hayat pelanggan (CLV)
description: Meramalkan potensi pendapatan untuk pelanggan aktif pada masa akan datang.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610385"
---
# <a name="predict-customer-lifetime-value-clv"></a>Ramaln nilai sepanjang hayat pelanggan (CLV)

Meramalkan nilai potensi (pendapatan) yang akan dibawa oleh pelanggan aktif individu kepada perniagaan anda melalui tempoh masa depan yang ditakrifkan. Ramalan ini membantu anda:

- Kenal pasti pelanggan bernilai tinggi dan proses wawasan ini.
- Buat segmen pelanggan strategik berdasarkan nilai potensi mereka untuk menjalankan kempen yang diperibadikan dengan jualan, pemasaran, dan usaha sokongan yang disasarkan.
- Membimbing pembangunan produk dengan memberi tumpuan kepada ciri-ciri yang meningkatkan nilai pelanggan.
- Mengoptimumkan strategi jualan atau pemasaran dan memperuntukkan belanjawan dengan lebih tepat untuk jangkauan pelanggan.
- Mengiktiraf dan memberi ganjaran kepada pelanggan bernilai tinggi melalui program kesetiaan atau ganjaran.

Tentukan maksud CLV untuk perniagaan anda. Kami menyokong ramalan CLV berasaskan transaksi. Nilai pelanggan yang diramalkan adalah berdasarkan sejarah transaksi perniagaan. Pertimbangkan untuk mencipta beberapa model dengan pilihan input yang berbeza-beza dan bandingkan hasil model untuk melihat senario model mana yang paling sesuai dengan keperluan perniagaan anda.

> [!TIP]
> Cuba CLV ramalan menggunakan data sampel: [Panduan sampel nilai seumur hidup pelanggan (CLV) ramalan](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [keizinan Penyumbang](permissions.md)
- Sekurang-kurangnya 100 pelanggan unik, lebih baik daripada pelanggan 10,000
- Pengecam Pelanggan, pengecam unik untuk memadankan transaksi dengan pelanggan individu
- Sekurang-kurangnya satu tahun sejarah transaksi, sebaik-baiknya dua hingga tiga tahun. Sebaik-baiknya, sekurang-kurangnya dua hingga tiga transaksi setiap ID pelanggan, sebaik-baiknya merentasi berbilang tarikh. Sejarah transaksi mesti termasuk:
  - **ID Transaksi**: Pengecam unik bagi setiap transaksi
  - **Tarikh transaksi**: Cap tarikh atau masa bagi setiap transaksi
  - **Amaun transaksi**: Nilai kewangan (contohnya, hasil atau margin untung) bagi setiap transaksi
  - **Label yang ditugaskan kepada pulangan**: Nilai boolean benar/palsu menandakan sama ada transaksi itu adalah pulangan
  - **ID** Produk: ID Produk produk yang terlibat dalam transaksi
- Data tentang aktiviti pelanggan:
  - **Kekunci primer**: Pengecam unik untuk aktiviti
  - **Cap** Waktu: Tarikh dan masa acara yang dikenal pasti oleh kunci utama
  - **Acara (nama aktiviti)**: Nama acara yang anda ingin gunakan
  - **Butiran (amaun atau nilai)**: Butiran tentang aktiviti pelanggan
- Data tambahan seperti:
  - Aktiviti web: Sejarah lawatan laman web atau sejarah e-mel
  - Aktiviti kesetiaan: Sejarah akruan dan penebusan mata ganjaran kesetiaan
  - Khidmat pelanggan log: Panggilan perkhidmatan, aduan atau sejarah pemulangan
  - Maklumat profil pelanggan
- Kurang daripada 20% nilai hilang dalam medan yang diperlukan

> [!NOTE]
> Hanya satu entiti sejarah transaksi boleh dikonfigurasi. Sekiranya terdapat banyak entiti pembelian atau transaksi, gabungkannya Power Query sebelum pengambilan data.

## <a name="create-a-customer-lifetime-value-prediction"></a>Cipta ramalan Nilai Sepanjang Hayat Pelanggan (CLV)

Pilih **Simpan draf** pada bila-bila masa untuk menyimpan ramalan sebagai draf. Draf ramalan dipaparkan dalam tab **Ramalan** saya.

1. Pergi ke **Ramalan** > **Perisikan**.

1. Pada tab **Cipta**, pilih **Gunakan model** pada **jubin Nilai** Sepanjang Hayat Pelanggan.

1. Pilih **Mulakan**.

1. **Namakan model ini** dan **Nama entiti output** untuk membezakannya daripada model atau entiti lain.

1. Pilih **Seterusnya**.

### <a name="define-model-preferences"></a>Takrifkan keutamaan model

1. Tetapkan **Tempoh masa ramalan** untuk menentukan sejauh mana ke masa depan anda mahu meramalkan CLV. Secara lalai, unit ini ditetapkan sebagai bulan.

   > [!TIP]
   > Untuk meramalkan CLV dengan tepat untuk tempoh masa yang ditetapkan, diperlukan tempoh data sejarah yang setanding. Sebagai contoh, jika anda ingin meramalkan CLV untuk 12 bulan akan datang, mempunyai sekurang-kurangnya 18 - 24 bulan data sejarah.

1. Tetapkan tempoh masa di mana pelanggan mesti mempunyai sekurang-kurangnya satu transaksi untuk dianggap aktif. Model ini hanya meramalkan CLV untuk **pelanggan** Aktif.
   - **Biarkan model mengira selang pembelian (disyorkan)**: Model menganalisis data anda dan menentukan tempoh masa berdasarkan pembelian sejarah.
   - **Tetapkan selang secara** manual: Tempoh masa untuk definisi pelanggan aktif anda.

1. Tentukan persentil **pelanggan** bernilai tinggi.
    - **Pengiraan model (disyorkan)**: Model menggunakan peraturan 80/20. Peratusan pelanggan yang menyumbang kepada 80% pendapatan kumulatif untuk perniagaan anda dalam tempoh sejarah dianggap sebagai pelanggan bernilai tinggi. Biasanya, kurang daripada 30-40% pelanggan menyumbang kepada 80% pendapatan kumulatif. Walau bagaimanapun, nombor ini mungkin berbeza bergantung pada perniagaan dan industri anda.
    - **Peratus pelanggan** aktif teratas: Persentil khusus untuk pelanggan bernilai tinggi. Sebagai contoh, masukkan **25** untuk menentukan pelanggan bernilai tinggi sebagai 25% teratas pelanggan yang membayar masa depan.

    Jika perniagaan anda mentakrifkan pelanggan bernilai tinggi dengan cara yang berbeza, [beritahu kami kerana kami ingin mendengar](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Pilih **Seterusnya**.

### <a name="add-required-data"></a>Tambah data yang diperlukan

1. Pilih **Tambah data** untuk **sejarah** transaksi Pelanggan.

1. Pilih jenis aktiviti semantik, **SalesOrder** atau **SalesOrderLine**, yang mengandungi sejarah transaksi. Jika aktiviti belum disediakan, pilih **di sini** dan buatnya.

1. Di bawah **Aktiviti**, jika atribut aktiviti dipetakan secara semantik apabila aktiviti dicipta, pilih atribut atau entiti tertentu yang ingin anda fokuskan pengiraan. Jika pemetaan semantik tidak berlaku, pilih **Edit dan petakan** data anda.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Menambah data yang diperlukan untuk model CLV":::

1. Pilih **Seterusnya** dan semak atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Tambah lebih banyak aktiviti atau pilih **Seterusnya**.

### <a name="add-optional-activity-data"></a>Tambah data aktiviti pilihan

Data mencerminkan interaksi pelanggan utama (seperti log web, khidmat pelanggan dan peristiwa) menambahkan konteks kepada rekod transaksi. Lebih banyak corak ditemui dalam data aktiviti pelanggan anda boleh meningkatkan ketepatan ramalan.

1. Pilih **Tambah data** di bawah **Wawasan model Boost dengan data** aktiviti tambahan.

1. Pilih jenis aktiviti yang sepadan dengan jenis aktiviti pelanggan yang anda tambah. Jika aktiviti belum disediakan, pilih **di sini** dan buatnya.

1. Di bawah **Aktiviti**, jika atribut aktiviti dipetakan apabila aktiviti dicipta, pilih atribut atau entiti tertentu yang ingin anda tumpukan pengiraan. Jika pemetaan tidak berlaku, pilih **Edit** dan petakan data anda.

1. Pilih **Seterusnya** dan semak atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Pilih **Seterusnya**.

1. [Tambah data](#add-optional-customer-data) pelanggan pilihan atau pilih **Seterusnya** dan pergi ke [Tetapkan jadual](#set-update-schedule) kemas kini.

### <a name="add-optional-customer-data"></a>Menambah data pelanggan pilihan

Pilih daripada 18 atribut profil pelanggan yang biasa digunakan untuk disertakan sebagai input kepada model. Atribut ini boleh membawa kepada hasil model yang lebih diperibadikan, relevan dan boleh diambil tindakan untuk kes penggunaan perniagaan anda.

Sebagai contoh: Contoso Coffee ingin meramalkan nilai seumur hidup pelanggan untuk menyasarkan pelanggan bernilai tinggi dengan tawaran peribadi yang berkaitan dengan pelancaran mesin espresso baru mereka. Contoso menggunakan model CLV dan menambah semua 18 atribut profil pelanggan untuk melihat faktor mana yang mempengaruhi pelanggan bernilai tertinggi mereka. Mereka mendapati lokasi pelanggan adalah faktor yang paling berpengaruh untuk pelanggan-pelanggan ini.
Dengan maklumat ini, mereka menganjurkan acara tempatan untuk pelancaran mesin espresso dan bekerjasama dengan vendor tempatan untuk tawaran peribadi dan pengalaman istimewa di acara tersebut. Tanpa maklumat ini, Contoso mungkin hanya menghantar e-mel pemasaran generik dan terlepas peluang untuk memperibadikan segmen tempatan pelanggan bernilai tinggi mereka.

1. Pilih **Tambah data** di bawah **Wawasan model Boost lebih jauh dengan data** pelanggan tambahan.

1. Untuk **Entiti**, pilih **Pelanggan: Pandangan Pelanggan** untuk memilih profil pelanggan bersatu yang dipetakan ke data atribut pelanggan. Untuk **ID** Pelanggan, pilih **System.Customer.CustomerId**.

1. Petakan lebih banyak medan jika data tersedia dalam profil pelanggan disatukan anda.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Contoh medan dipetakan untuk data profil pelanggan.":::

1. Pilih **Simpan**.

1. Pilih **Seterusnya**.

### <a name="set-update-schedule"></a>Tetapkan jadual kemas kini

1. Pilih kekerapan untuk melatih semula model anda berdasarkan data terkini. Tetapan ini penting untuk mengemas kini ketepatan ramalan kerana data baru ditelan ke dalam Wawasan Pelanggan. Kebanyakan perniagaan boleh melatih semula sekali setiap bulan dan mendapatkan ketepatan yang baik untuk ramalan mereka.

1. Pilih **Seterusnya**.

### <a name="review-and-run-the-model-configuration"></a>Semak dan jalankan konfigurasi model

Langkah **Semak semula dan jalankan** menunjukkan ringkasan konfigurasi dan menyediakan peluang untuk membuat perubahan sebelum anda mencipta ramalan.

1. Pilih **Edit** pada sebarang langkah untuk menyemak semula dan membuat sebarang perubahan.

1. Jika anda berpuas hati dengan pilihan anda, pilih **Simpan dan jalankan** untuk mula menjalankan model. Pilih **Selesai**. Tab **Ramalan** saya dipaparkan semasa ramalan sedang dicipta. Proses mungkin mengambil masa beberapa jam untuk dilengkapkan bergantung kepada amaun data yang digunakan dalam ramalan.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Lihat keputusan ramalan

1. Pergi ke **Ramalan** > **Perisikan**.

1. Dalam tab **Ramalan** saya, pilih ramalan yang anda ingin lihat.

Terdapat tiga bahagian utama data dalam halaman hasil.

- **Prestasi model latihan**: Gred A, B, atau C menunjukkan prestasi ramalan dan boleh membantu anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entiti output.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imej kotak maklumat skor model dengan gred A.":::

  Wawasan Pelanggan menilai prestasi model AI dalam meramalkan pelanggan bernilai tinggi berbanding model asas.

  Gred ditentukan berdasarkan peraturan berikut:
  - **A** apabila model ini meramalkan secara tepat sekurang-kurangnya 5% lebih banyak pelanggan bernilai tinggi berbanding dengan model garis dasar.
  - **B** apabila model ini meramalkan secara tepat antara 0-5% lebih banyak pelanggan bernilai tinggi berbanding dengan model garis dasar.
  - **C** apabila model ini meramalkan secara tepat kurang pelanggan bernilai tinggi berbanding dengan model garis dasar.
  
  Pilih [**Ketahui tentang skor**](#learn-about-the-score) ini untuk membuka **anak tetingkap Penarafan** Model yang menunjukkan butiran lanjut tentang prestasi model AI dan model garis dasar. Ia akan membantu anda memahami metrik prestasi model asas dengan lebih baik dan bagaimana gred prestasi model akhir diperolehi. Model asas menggunakan pendekatan berasaskan bukan AI untuk mengira nilai seumur hidup pelanggan berdasarkan pembelian sejarah yang dibuat oleh pelanggan.

- **Nilai pelanggan mengikut persentil**: Pelanggan bernilai rendah dan bernilai tinggi dipaparkan dalam carta. Letakkan penuding di atas bar dalam histogram untuk melihat bilangan pelanggan dalam setiap kumpulan dan CLV purata kumpulan itu. Secara pilihan, [buat segmen pelanggan](prediction-based-segment.md) berdasarkan ramalan CLV mereka.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Nilai pelanggan mengikut persentil untuk model CLV":::

- **Faktor paling berpengaruh**: Pelbagai faktor dipertimbangkan semasa mencipta ramalan CLV anda berdasarkan data input yang diberikan kepada model AI. Setiap faktor mempunyai kepentingannya yang dikira untuk ramalan teragregat yang dicipta oleh model. Gunakan faktor ini untuk membantu mengesahkan hasil ramalan anda. Faktor-faktor ini juga memberi lebih banyak pandangan mengenai faktor-faktor yang paling berpengaruh yang menyumbang ke arah meramalkan CLV di semua pelanggan anda.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Faktor paling berpengaruh untuk model CLV":::

### <a name="learn-about-the-score"></a>Ketahui tentang skor

Formula standard yang digunakan untuk mengira CLV mengikut model garis dasar:

 _**CLV untuk setiap pelanggan** = Purata pembelian bulanan yang dibuat oleh pelanggan dalam tetingkap pelanggan aktif * Bilangan bulan dalam tempoh ramalan CLV * Kadar pengekalan keseluruhan semua pelanggan_

Model AI dibandingkan dengan model asas berdasarkan pada dua metrik prestasi model.
  
- **Kadar kejayaan dalam meramalkan pelanggan bernilai tinggi**

  Lihat perbezaan dalam meramalkan pelanggan bernilai tinggi menggunakan model AI berbanding model asas. Sebagai contoh, kadar kejayaan 84% bermakna bahawa daripada semua pelanggan bernilai tinggi dalam data latihan, model AI dapat menangkap 84% secara tepat. Kami kemudian membandingkan kadar kejayaan ini dengan kadar kejayaan model asas untuk melaporkan perubahan relatif. Nilai ini digunakan untuk menugaskan gred kepada model.

- **Metrik ralat**

  Lihat prestasi keseluruhan model dari segi kesilapan dalam meramalkan nilai masa depan. Kami menggunakan metrik Ralat Dikuasakan Min Punca (RMSE) keseluruhan untuk menilai kesilapan ini. RMSE ialah cara standard untuk mengukur kesilapan model dalam meramalkan data kuantitatif. RMSE model AI dibandingkan dengan RMSE model asas dan perbezaan relatif dilaporkan.

Model AI mengutamakan kedudukan pelanggan yang tepat mengikut nilai yang mereka bawa ke perniagaan anda. Jadi, hanya kadar kejayaan meramalkan pelanggan bernilai tinggi digunakan untuk mendapatkan gred model akhir. Metrik RMSE sensitif kepada orang luar. Dalam senario di mana anda mempunyai peratusan kecil pelanggan dengan nilai pembelian yang sangat tinggi, metrik RMSE keseluruhan mungkin tidak memberikan gambaran penuh prestasi model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
