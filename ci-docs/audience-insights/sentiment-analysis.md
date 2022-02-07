---
title: Analisis sentimen untuk maklum balas pelanggan
description: Ketahui cara menggunakan model analisis sentimen pada maklum balas pelanggan dalam Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
---

# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Menganalisis sentimen dalam maklum balas pelanggan (Pratonton)

Pelanggan mengharapkan produk, perkhidmatan, dan pengalaman berkualiti tinggi hari ini. Terutamanya pelanggan yang berkongsi maklum balas mereka. Sangat mencabar bagi organisasi untuk menganalisis peningkatan jumlah data tanpa menurunkan ketepatan dan kos buruh yang lebih tinggi. Dynamics 365 Customer Insights menawarkan model analisis sentimen untuk maklum balas pelanggan yang membolehkan organisasi menganalisis data mereka dengan lebih tepat dan pada kos yang lebih rendah.

Analisis sentimen membolehkan anda mensintesis sentimen pelanggan dan mengenal pasti aspek perniagaan sebagai peluang untuk penambahbaikan. Ciri Wawasan Pelanggan ini membantu anda memahami perkara yang berfungsi dengan baik dan perkara yang anda perlukan untuk menangani. Fokus pada bidang perniagaan yang paling relevan dan berkesan untuk meningkatkan pengalaman untuk pelanggan anda. Pada akhirnya, ia boleh membantu anda untuk memandu tindakan perniagaan yang membolehkan pengalaman yang menghasilkan kepuasan dan kesetiaan pelanggan yang tinggi.

## <a name="overview"></a>Gambaran keseluruhan

Ciri analisis sentimen menjana dua pandangan yang diperolehi bagi setiap ID pelanggan. Skor sentimen (daripada -5 hingga 5) dan senarai aspek perniagaan yang berkenaan (bidang perniagaan) bersama-sama membantu anda lebih memahami maklum balas pelanggan. 

Maklumat ini boleh membantu anda mencapai hasil berikut: 
- Dapatkan gambaran keseluruhan sentimen pelanggan terhadap jenama atau organisasi
- Kenal pasti pelanggan dengan sentimen negatif untuk menumpukan kempen dan penglibatan anda dan mengoptimumkan pulangan yang lebih tinggi  
- Kenal pasti aspek perniagaan dengan isu-isu yang ditunjukkan oleh pelanggan  
- Pelanggan segmen berdasarkan sentimen mereka untuk menjalankan kempen yang diperibadikan dengan usaha jualan, pemasaran dan sokongan yang disasarkan
- Optimumkan operasi perniagaan dengan menangani bidang kebimbangan atau peluang yang disebutkan oleh pelanggan
- Mengiktiraf aspek perniagaan yang baik dan memberi ganjaran kepada pelanggan gembira melalui program kesetiaan dan promosi

Untuk memastikan bahawa anda boleh mempercayai hasil model, kami memberikan maklumat yang telus tentang bagaimana model membuat keputusan. Anda akan mendapat senarai perkataan yang mempengaruhi keputusan model untuk menetapkan skor sentimen tertentu atau aspek perniagaan kepada komen maklum balas.  

Kami menggunakan dua **model Pemprosesan Bahasa Semula Jadi (NLP):** Yang pertama memberikan setiap maklum balas komen skor sentimen. Model kedua mengaitkan setiap maklum balas dengan semua aspek perniagaan yang berkenaan. Model ini dilatih pada data awam dari sumber di media sosial, runcit, restoran, produk pengguna, dan industri automotif.    
  
Aspek perniagaan yang telah ditetapkan untuk model untuk dikaitkan dengan data maklum balas termasuk:
-   Pengurusan akaun
-   Daftar keluar dan pembayaran
-   Sokongan pelanggan
-   Pengambilan dalam kedai
-   Penghantaran dan pengambilan pembungkusan
-   Pra-pesanan
-   Harga
-   Privasi dan keselamatan
-   Promosi dan ganjaran
-   Resit dan waranti
-   Pertukaran pengembalian dan pembatalan
-   Ketepatan pemenuhan
-   Kualiti laman web/aplikasi

> [!NOTE]
> Pada masa ini, kami hanya menyokong analisis sentimen mengenai maklum balas pelanggan Bahasa Inggeris. Lebih banyak bahasa akan disokong pada masa akan datang. Jika maklum balas dalam bahasa lain dimuat naik, model masih akan mengembalikan hasil. Walau bagaimanapun, keputusan ini tidak akan tepat. 

## <a name="prerequisites"></a>Prasyarat

Analisis sentimen adalah berdasarkan data maklum balas teks yang telah melalui [proses penyatuan data](data-unification.md). Kami amat mengesyorkan agar anda [mengkonfigurasikan entiti data maklum balas anda sebagai entiti](map-entities.md#select-primary-key-and-semantic-type-for-attributes) aktiviti jenis semantik (Jenis maklum balas) terlebih dahulu. 

Untuk mengkonfigurasikan model analisis sentimen, anda memerlukan sekurang-kurangnya [keizinan](permissions.md) Penyumbang.

Wawasan Pelanggan boleh memproses sehingga 10 juta rekod maklum balas untuk jangka model tunggal. Model ini boleh menganalisis komen maklum balas sehingga 128 perkataan. Jika komen maklum balas lebih panjang, analisis hanya menganggap perkataan 128 pertama.

### <a name="data-requirements"></a>Keperluan data
  
Atribut data berikut diperlukan:
- ID Pelanggan Bersepadu (UCID) untuk memadankan rekod data maklum balas teks kepada pelanggan individu. ID ini adalah hasil daripada [proses](data-unification.md) penyatuan data.
- ID maklum balas
- Cap waktu maklum balas
- Teks maklum balas   

> [!TIP]
> Analisis sentimen memerlukan maklum balas teks pelanggan anda. Hanya satu entiti maklum balas boleh dikonfigurasikan pada masa ini. Jika terdapat berbilang entiti maklum balas, anda boleh kesatuan mereka Power Query sebelum pengambilan data bermula.

## <a name="configure-a-sentiment-analysis"></a>Konfigurasikan analisis sentimen 

1. Dalam Customer Insights, pergi ke **Kepintaran** > **Ramalan**.

1. **Pada jubin analisis** sentimen pelanggan, pilih **Gunakan model**.

1. **Dalam anak tetingkap analisis sentimen Pelanggan (pratonton),** pilih **Mulakan**.

1. **Dalam langkah Nama** model, berikan **Nama** untuk analisis anda. 

1. **Berikan nama** entiti output aspek Perniagaan dan **nama** entiti output skor Sentimen, kemudian pilih **Berikut**.

1. Dalam langkah Data yang **diperlukan, pilih** Tambah data **.**

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Tambah aliran data dalam model analisis sentimen.":::

1. **Dalam anak tetingkap Tambah data**, pilih Maklum Balas **jenis** semantik daripada senarai.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Langkah konfigurasi untuk memilih aktiviti maklum balas untuk analisis sentimen.":::

1. Pilih aktiviti untuk digunakan bagi analisis sentimen ini, kemudian pilih **Seterusnya**.
 
1. Petakan atribut dalam data anda kepada atribut model. Pilih **Simpan** untuk menggunakan pilihan anda. 

1. Anda melihat status pemetaan data. Pilih **Seterusnya** untuk teruskan. 

1. **Dalam langkah Semak butiran** model anda, sahkan konfigurasi analisis sentimen anda. Anda boleh kembali ke mana-mana bahagian konfigurasi ramalan. Pilih **Simpan dan jalankan** untuk memulakan analisis. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Langkah semak semula untuk model sentimen yang menunjukkan semua item yang dikonfigurasi.":::

1. Pilih **Selesai** untuk meninggalkan pengalaman konfigurasi. Proses ini mungkin mengambil masa beberapa jam untuk diselesaikan bergantung kepada jumlah data yang digunakan. 

## <a name="review-analysis-status"></a>Semak status analisis

1.  Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.
2.  Pilih ramalan yang anda mahu semak semula.
- **Nama ramalan**: Nama ramalan yang diberikan semasa menciptanya.
- **jenis** ramalan: Jenis model yang digunakan untuk ramalan.
- **Entiti output**: Nama entiti untuk menyimpan output ramalan. Pergi ke **Data** > **Entiti** untuk mencari entiti dengan nama ini.
- **Medan ramalan**: Medan ini diisikan hanya untuk beberapa jenis ramalan, dan tidak digunakan dalam ramalan nilai sepanjang hayat pelanggan.
- **Status**: Status jalanan ramalan.
  - **Dibariskan**: Ramalan sedang menunggu proses lain untuk selesai.
  - **Menyegar semula**: Ramalan sedang berjalan untuk mengcipta keputusan yang akan mengalir ke dalam entiti output.
  - **Gagal**: Jalanan ramalan gagal. Ulasan log untuk maklumat lanjut.
  - **Berjaya**: Ramalan telah berjaya. Pilih Lihat di bawah elips menegak untuk menyemak ramalan anda.
- **Diedit**: Tarikh konfigurasi untuk ramalan telah diubah.
- **Disegar semula** terakhir: Tarikh ramalan telah disegar semula hasil dalam entiti output.

## <a name="manage-sentiment-analysis"></a>Urus analisis sentimen

Anda boleh mengoptimumkan, menyelesaikan masalah, menyegar semula atau memadamkan ramalan. Semak laporan kebolehgunaan data input untuk mengetahui cara membuat ramalan lebih cepat dan lebih dipercayai. Untuk mendapatkan maklumat lanjut, lihat [Urus ramalan](manage-predictions.md).

## <a name="review-analysis-results"></a>Hasil analisis semakan
 
1. Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**. 
1. Pilih nama ramalan yang anda ingin semak semula hasil. Dalam kes ini, pilih analisis sentimen yang anda mahu semak. 

### <a name="summary-tab"></a>Tab ringkasan

Terdapat empat bahagian utama data dalam halaman hasil. 

- **Purata skor** sentimen: Membantu anda memahami sentimen keseluruhan merentas semua pelanggan. Skor sentimen dikumpulkan dalam tiga kategori: 
  1.    Negatif (-5 > 2)
  2.    Neutral (-1 > 1)
  3.    Positif (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Perwakilan visual sentimen pelanggan keseluruhan.":::

- **Pengagihan pelanggan mengikut skor** sentimen: Pelanggan dikategorikan kepada kumpulan negatif, neutral dan positif berdasarkan skor sentimen mereka. Tuding pada bar dalam histogram untuk melihat bilangan pelanggan dan skor sentimen purata dalam setiap kumpulan. Data ini boleh membantu anda [membuat segmen pelanggan](segments.md) berdasarkan skor sentimen mereka.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Carta bar menunjukkan sentimen pelanggan merentasi tiga kumpulan sentimen.":::

- **Purata skor sentimen dari masa ke masa**: Sentimen pelanggan mungkin berubah dari masa ke masa. Kami menyediakan trend dalam sentimen pelanggan anda untuk julat masa data anda. Pandangan ini boleh membantu anda mengukur kesan promosi bermusim, pelancaran produk atau campur tangan lain yang terikat dengan masa terhadap sentimen pelanggan. Lihat graf dengan memilih tahun minat daripada menu lungsur. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Carta sejarah dengan skor sentimen dari masa ke masa diwakili sebagai garis.":::
 
- **Sentimen merentas aspek** perniagaan: Jadual ini menyenaraikan purata sentimen merentas aspek perniagaan. Ia boleh membantu anda mengukur aspek perniagaan anda yang sudah memuaskan pelanggan atau aspek yang memerlukan lebih banyak perhatian. Rekod maklum balas yang tidak sejajar dengan mana-mana aspek perniagaan yang disokong dikategorikan di bawah **Lain-lain**. Jadual diisih mengikut abjad secara lalai. Anda boleh mengubah suai pengisihan dengan memilih pengepala jadual.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Senarai aspek perniagaan dengan nilai sentimen yang berkaitan dan bilangan pelanggan yang menyebutnya.":::
 
  Pilih nama aspek perniagaan untuk melihat maklumat tambahan cara aspek perniagaan dikenal pasti oleh model. Terdapat dua bahagian dalam anak tetingkap ini: 

  - **Kata-kata** berpengaruh: Menunjukkan kata-kata teratas yang mempengaruhi pengenalpastian model AI aspek perniagaan dalam maklum balas pelanggan. 
    **Tunjukkan perkataan** yang menyinggung perasaan: Membolehkan anda menyertakan perkataan yang menyinggung perasaan dalam senarai daripada data maklum balas pelanggan asal. Secara lalai, ia dimatikan.  Pelekat perkataan yang menyinggung perasaan dikuasakan oleh model AI dan mungkin tidak dapat mengesan semua kata-kata yang menyinggung perasaan. Kami terus mengerus dan melatih pengelas untuk prestasi optimum. Jika anda mengesan perkataan yang menyinggung perasaan yang tidak ditapis seperti yang dijangkakan, beritahu kami. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Senarai perkataan berpengaruh dengan togol untuk menunjukkan atau menyembunyikan kata-kata yang menyinggung perasaan.":::
 
  - **Sampel maklum** balas: Menunjukkan rekod maklum balas sebenar dalam data anda. Kata-kata dikodkan warna mengikut pengaruh mereka terhadap pengenalpastian aspek perniagaan. 


### <a name="influential-words-analysis-tab"></a>Tab analisis perkataan berpengaruh

Terdapat tiga bahagian maklumat tambahan yang menerangkan bagaimana model sentimen berfungsi.
  
1. **Kata-kata teratas yang menyumbang kepada sentimen** positif: Menunjukkan kata-kata teratas yang mempengaruhi pengenalpastian model AI sentimen positif dalam maklum balas pelanggan.  
2. **Kata-kata teratas yang menyumbang kepada sentimen** negatif: Menunjukkan kata-kata teratas yang mempengaruhi pengenalpastian model AI sentimen negatif dalam maklum balas pelanggan.  
3. **Sampel maklum** balas: Menunjukkan rekod maklum balas sebenar, satu dengan sentimen negatif dan satu dengan sentimen positif. Kata-kata dalam rekod maklum balas diserlahkan mengikut sumbangan mereka kepada skor sentimen yang diberikan. Kata-kata yang menyumbang kepada skor sentimen positif diserlahkan dalam warna hijau. Perkataan yang menyumbang kepada skor negatif diserlahkan dalam warna merah.
   Pilih **Lihat lebih lanjut** untuk memuatkan lebih banyak sampel maklum balas yang memberikan lebih banyak maklumat dan konteks cara model sentimen berfungsi.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Contoh analisis sentimen mengenai maklum balas pelanggan.":::
 
**Tunjukkan perkataan** yang menyinggung perasaan: Membolehkan anda menyertakan perkataan yang menyinggung perasaan dalam senarai daripada data maklum balas pelanggan asal. Secara lalai, ia dimatikan.  Pelekat perkataan yang menyinggung perasaan dikuasakan oleh model AI dan mungkin tidak dapat mengesan semua kata-kata yang menyinggung perasaan. Kami terus mengerus dan melatih pengelas untuk prestasi optimum. Jika anda mengesan perkataan yang menyinggung perasaan yang tidak ditapis seperti yang dijangkakan, beritahu kami. 

## <a name="act-on-analysis-results"></a>Bertindak ke atas keputusan analisis

Anda boleh mula mencipta segmen pelanggan baharu dengan mudah dari halaman hasil analisis sentimen dengan **memilih Buat segmen** di bahagian atas halaman hasil model.

:::image type="content" source="media/create-segment-model.png" alt-text="Bar perintah dengan pilihan pada model ramalan.":::
 
## <a name="potential-bias"></a>Kecenderungan yang berpotensi

Seperti mana-mana ciri yang menggunakan kecerdasan buatan ramalan, anda harus sedar potensi berat sebelah dalam data yang anda gunakan untuk meramalkan sentimen pelanggan. Sebagai contoh, jika anda hanya mengumpul maklum balas secara digital, anda boleh terlepas maklum balas daripada pelanggan yang terutamanya menjalankan perniagaan dengan anda secara peribadi, yang boleh menjejaskan output ciri.

Oleh kerana ciri ini menggunakan cara automatik untuk menilai data dan membuat ramalan berdasarkan data tersebut, oleh itu ia mempunyai keupayaan untuk digunakan sebagai kaedah pemprofilan, kerana istilah itu ditakrifkan oleh Peraturan Perlindungan Data Umum ("GDPR"). Penggunaan anda bagi ciri ini untuk memproses data mungkin tertakluk pada GDPR atau perundangan atau peraturan lain. Anda bertanggungjawab untuk memastikan bahawa penggunaan Dynamics 365 Customer Insights anda, termasuk analisis sentimen, mematuhi semua undang-undang dan peraturan yang berkenaan, termasuk undang-undang yang berkaitan dengan privasi, data peribadi, data biometrik, perlindungan data, dan kerahsiaan komunikasi.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
