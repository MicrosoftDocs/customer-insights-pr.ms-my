---
title: Ramalan churn transaksi (mengandungi video)
description: Ramalkan sama ada pelanggan mempunyai risiko kerana tidak lagi membeli produk atau perkhidmatan anda.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610523"
---
# <a name="predict-transaction-churn"></a>Pulangan transaksi ramalan

Ramalan pulangan transaksi membantu meramal jika pelanggan tidak lagi akan membeli produk atau perkhidmatan anda dalam tetingkap masa tertentu.

Anda mesti mempunyai pengetahuan perniagaan untuk memahami apa maksud churn untuk perniagaan anda. Kami menyokong definisi pulangan berasaskan masa yang bermaksud pelanggan dianggap sebagai telah mendapat pulangan selepas tempoh tiada pembelian.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Untuk persekitaran berdasarkan akaun perniagaan, kita boleh meramalkan pulangan transaksi untuk akaun dan juga kombinasi akaun dan satu lagi tahap maklumat seperti kategori produk. Sebagai contoh, menambah dimensi boleh membantu menentukan kemungkinan akaun "Contoso" akan berhenti membeli kategori produk "alat tulis pejabat." Selain itu, untuk akaun perniagaan, kami juga boleh menggunakan AI untuk menjana senarai sebab yang berpotensi mengapa akaun berkemungkinan untuk pulangan untuk kategori maklumat peringkat kedua.

> [!TIP]
> Cuba ramalan churn transaksi menggunakan data sampel: [Panduan sampel ramalan churn transaksi](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md).
- Sekurang-kurangnya 10 profil pelanggan, lebih baik daripada 1,000 pelanggan unik.
- Pengecam Pelanggan, pengecam unik untuk memadankan transaksi dengan pelanggan anda.
- Data transaksi sekurang-kurangnya dua kali ganda tetingkap masa yang dipilih seperti dua hingga tiga tahun sejarah transaksi. Sebaik-baiknya sekurang-kurangnya dua transaksi bagi setiap pelanggan. Sejarah transaksi mesti termasuk:
  - **ID** Transaksi: Pengecam unik pembelian atau transaksi.
  - **Tarikh** Transaksi: Tarikh pembelian atau transaksi.
  - **Nilai transaksi**: Mata wang atau jumlah nilai berangka transaksi.
  - **ID** produk unik: ID produk atau perkhidmatan yang dibeli jika data anda berada pada tahap item baris.
  - **Sama ada transaksi ini adalah pulangan**: Medan benar / palsu yang mengenal pasti sama ada transaksi itu adalah pulangan atau tidak. **Sekiranya Nilai transaksi** negatif, kami menyimpulkan pulangan.
- Data aktiviti pelanggan:
  - Pengecam Pelanggan, pengecam unik untuk memetakan aktiviti kepada pelanggan anda.
  - **Kekunci primer:** Pengecam unik untuk sesuatu aktiviti. Contohnya, lawatan laman web atau rekod penggunaan yang menunjukkan pelanggan telah mencuba sampel produk anda.
  - **Cap Waktu:** Tarikh dan masa acara yang dikenal pasti oleh kunci utama.
  - **Acara:** Nama acara yang anda ingin gunakan. Contohnya, medan yang dipanggil "UserAction" di dalam stor runcit mungkin kupon yang digunakan oleh pelanggan.
  - **Butiran:** Maklumat terperinci tentang peristiwa. Contohnya, medan yang dipanggil "CouponValue" dalam stor runcit mungkin nilai mata wang kupon tersebut.
- Kurang daripada 20% nilai yang hilang dalam medan data entiti yang disediakan

Untuk akaun perniagaan (B-to-B), tambah data pelanggan yang sejajar dengan atribut yang lebih statik untuk memastikan model berfungsi dengan baik:
- **CustomerID:** Pengecam unik untuk pelanggan.
- **Tarikh Dicipta:** Tarikh pelanggan pada mulanya ditambah.
- **Negeri atau Wilayah:** Lokasi negeri atau wilayah pelanggan.
- **Negara:** Negara pelanggan.
- **Industri:** Jenis industri pelanggan. Sebagai contoh, medan yang dipanggil "Industri" di dalam pemanggang kopi mungkin menunjukkan jika pelanggan adalah runcit.
- **Klasifikasi:** Pengkategorian pelanggan untuk perniagaan anda. Sebagai contoh, medan yang dipanggil "ValueSegment" dalam pemanggang kopi mungkin merupakan peringkat pelanggan berdasarkan saiz pelanggan.

> [!NOTE]
> Untuk perniagaan yang mempunyai kekerapan pembelian pelanggan yang tinggi (setiap beberapa minggu), anda disyorkan untuk memilih tetingkap ramalan yang lebih pendek dan definisi pulangan. Untuk kekerapan pembelian rendah (setiap beberapa bulan atau sekali setahun), pilih tetingkap ramalan lebih panjang dan definisi pulangan.

## <a name="create-a-transaction-churn-prediction"></a>Mencipta ramalan pulangan transaksi

1. Pergi ke **Ramalan** > **Perisikan**.

1. Pada tab **Cipta**, pilih **Gunakan model** pada **jubin model** churn Pelanggan.

1. Pilih **Transaksi** untuk jenis churn dan kemudian **Bermula**.

1. **Namakan model ini** dan **Nama entiti output** untuk membezakannya daripada model atau entiti lain.

1. Pilih **Seterusnya**.

### <a name="define-customer-churn"></a>Takrifkan pulangan pelanggan

Pilih **Simpan draf** pada bila-bila masa untuk menyimpan ramalan sebagai draf. Draf ramalan dipaparkan dalam tab **Ramalan** saya.

1. Setkan **tetingkap** ramalan. Sebagai contoh, ramalkan risiko pulangan untuk pelanggan anda sepanjang 90 hari yang akan datang untuk menyelaraskan usaha pengekalan pemasaran anda. Meramalkan risiko pulangan untuk tempoh masa yang lebih panjang atau lebih pendek boleh menjadikan lebih sukar untuk menangani faktor dalam profil risiko pulangan anda, tetapi ia bergantung kepada keperluan perniagaan khusus anda.

1. Masukkan bilangan hari untuk mentakrifkan churn dalam **medan definisi** Churn. Sebagai contoh, jika pelanggan tidak membuat pembelian dalam tempoh 30 hari yang lalu, mereka mungkin dianggap sebagai churned untuk perniagaan anda.

1. Pilih **Seterusnya**.

### <a name="add-purchase-history"></a>Tambah sejarah pembelian

1. Pilih **Tambah data** untuk **sejarah** transaksi Pelanggan.

1. Pilih jenis aktiviti semantik, **SalesOrder** atau **SalesOrderLine**, yang mengandungi maklumat sejarah transaksi. Jika aktiviti belum disediakan, pilih **di sini** dan buatnya.

1. Di bawah **Aktiviti**, jika atribut aktiviti dipetakan secara semantik apabila aktiviti dicipta, pilih atribut atau entiti tertentu yang ingin anda fokuskan pengiraan. Jika pemetaan semantik tidak berlaku, pilih **Edit dan petakan** data anda.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Anak tetingkap sisi menunjukkan pemilihan aktiviti tertentu di bawah jenis semantik.":::

1. Pilih **Seterusnya** dan semak atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Tambah lebih banyak aktiviti atau pilih **Seterusnya**.

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Tambah data tambahan (pilihan)

1. Pilih **Tambah data** untuk **aktiviti** Pelanggan.

1. Pilih jenis aktiviti semantik yang mengandungi data yang anda ingin gunakan. Jika aktiviti belum disediakan, pilih **di sini** dan buatnya.

1. Di bawah **Aktiviti**, jika atribut aktiviti dipetakan secara semantik apabila aktiviti dicipta, pilih atribut atau entiti tertentu yang ingin anda fokuskan pengiraan. Jika pemetaan semantik tidak berlaku, pilih **Edit dan petakan** data anda.

1. Pilih **Seterusnya** dan semak atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Pilih **Seterusnya**

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

### <a name="select-prediction-level"></a>Pilih tahap ramalan

Kebanyakan ramalan dicipta pada tahap pelanggan. Dalam sesetengah keadaan, ia mungkin tidak cukup perincian untuk menangani keperluan perniagaan anda. Gunakan ciri ini untuk meramalkan churn untuk cawangan pelanggan, sebagai contoh, dan bukannya untuk pelanggan secara keseluruhan.

1. Pilih **Pilih entiti untuk peringkat** menengah. Jika pilihan tidak tersedia, pastikan anda telah melengkapkan bahagian sebelum ini.

1. Kembangkan entiti yang anda mahu pilih peringkat kedua daripada atau gunakan kotak penapis carian untuk menapis pilihan yang dipilih.

1. Pilih atribut yang anda mahu gunakan sebagai tahap kedua kemudian pilih **Tambah**.

1. Pilih **Seterusnya**.

> [!NOTE]
> Entiti yang tersedia dalam bahagian ini ditunjukkan kerana mereka mempunyai perhubungan dengan entiti yang anda pilih dalam bahagian sebelumnya. Jika anda tidak nampak entiti yang anda mahu tambah, pastikan ia mempunyai perhubungan sah yang wujud dalam **Perhubungan**. Hanya satu ke satu dan perhubungan banyak ke satu adalah sah untuk konfigurasi ini.

### <a name="add-additional-data-optional"></a>Tambah data tambahan (pilihan)

1. Pilih **Tambah data** untuk **aktiviti** Pelanggan.

1. Pilih jenis aktiviti semantik yang mengandungi data yang anda ingin gunakan. Jika aktiviti belum disediakan, pilih **di sini** dan buatnya.

1. Di bawah **Aktiviti**, jika atribut aktiviti dipetakan secara semantik apabila aktiviti dicipta, pilih atribut atau entiti tertentu yang ingin anda fokuskan pengiraan. Jika pemetaan semantik tidak berlaku, pilih **Edit dan petakan** data anda.

1. Pilih **Seterusnya** dan semak atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Pilih **Seterusnya**

1. Secara pilihan, pilih **Tambah data** untuk **Data pelanggan**.

1. Peta atribut semantik ke medan dalam data pelanggan anda sendiri sebagaimana dikenal pasti. Data dalam medan yang digunakan tidak perlu diubah selalu untuk memastikan prestasi terbaik model. Sebagai contoh, memilih medan untuk "Pengelasan" yang ditukar setiap bulan hanya akan mempunyai nilai terakhir yang digunakan dalam ramalan, walaupun sejarah nilai yang sama mungkin tidak digunakan kepada pelanggan apabila membina corak ramalan.

1. Pilih **Seterusnya**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Menyediakan senarai pilihan akaun penanda aras

Tambah senarai pelanggan dan akaun perniagaan anda yang anda mahu gunakan sebagai penanda aras. Butiran [untuk akaun](#view-prediction-results) penanda aras ini termasuk skor churn mereka dan ciri-ciri paling berpengaruh yang memberi kesan kepada ramalan churn mereka.

1. Pilih **+ Tambah pelanggan**.

1. Pilih pelanggan yang bertindak sebagai penanda aras.

1. Pilih **Seterusnya**.

---

### <a name="set-update-schedule"></a>Tetapkan jadual kemas kini

1. **Untuk langkah Kemas Kini** data, pilih kekerapan untuk melatih semula model anda. Tetapan ini penting untuk mengemas kini ketepatan ramalan kerana data baru ditelan ke dalam Wawasan Pelanggan. Kebanyakan perniagaan boleh melatih semula sekali setiap bulan dan mendapatkan ketepatan yang baik untuk ramalan mereka.

1. Pilih **Seterusnya**.

### <a name="review-and-run-the-model-configuration"></a>Semak dan jalankan konfigurasi model

Langkah **Semak semula dan jalankan** menunjukkan ringkasan konfigurasi dan menyediakan peluang untuk membuat perubahan sebelum anda mencipta ramalan.

1. Pilih **Edit** pada sebarang langkah untuk menyemak semula dan membuat sebarang perubahan.

1. Jika anda berpuas hati dengan pilihan anda, pilih **Simpan dan jalankan** untuk mula menjalankan model. Pilih **Selesai**. Tab **Ramalan** saya dipaparkan semasa ramalan sedang dicipta. Proses mungkin mengambil masa beberapa jam untuk dilengkapkan bergantung kepada amaun data yang digunakan dalam ramalan.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Lihat keputusan ramalan

1. Pergi ke **Ramalan** > **Perisikan**.

1. Dalam tab **Ramalan** saya, pilih ramalan yang anda ingin lihat.

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

Terdapat tiga bahagian utama data dalam halaman hasil:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

Terdapat tiga bahagian utama data dalam halaman hasil:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

**Halaman maklumat analisis** ciri Berpengaruh mengandungi empat bahagian data:

- Dalam anak tetingkap kanan, pilih item daripada **Pelanggan** teratas atau **pelanggan** Penanda Aras. Kedua-dua senarai disusun mengikut nilai yang berkurangan daripada skor pulangan, sama ada skor hanya untuk pelanggan atau skor gabungan untuk pelanggan dan peringkat kedua seperti kategori produk. Item yang dipilih menentukan kandungan pada halaman ini.

  - **Pelanggan teratas** : Senarai 10 pelanggan yang berada di risiko tertinggi pulangan dan risiko paling rendah pulangan berdasarkan skor pulangan mereka.
  - **Pelanggan penanda aras** : Senarai hingga 10 pelanggan yang dipilih semasa mengkonfigurasi model.

- **Skor pulangan:** Menunjukkan skor pulangan untuk item terpilih dalam tetingkap kanan.

- **Pengedaran risiko Churn:** Menunjukkan pengedaran risiko churn di seluruh pelanggan dan persentil pelanggan terpilih berada.

- **Ciri-ciri teratas meningkatkan dan mengurangkan risiko churn:** Menyenaraikan lima ciri teratas yang meningkat dan mengurangkan risiko churn untuk item yang dipilih dalam anak tetingkap kanan. Menunjukkan nilai ciri untuk item tersebut dan pengaruhnya terhadap skor churn untuk setiap ciri berpengaruh. Nilai purata setiap ciri merentas segmen pelanggan yang rendah, sederhana dan pulangan tinggi juga ditunjukkan. Ia membantu untuk kontekstual lebih baik nilai ciri yang paling berpengaruh untuk item terpilih dan bandingkan dengan segmen pelanggan rendah, sederhana dan pulangan tinggi.

  - Rendah: akaun atau gabungan akaun dan peringkat menengah dengan skor churn antara 0 dan 0.33.
  - Sederhana: akaun atau gabungan akaun dan peringkat menengah dengan skor churn antara 0.33 dan 0.66.
  - Tinggi: akaun atau gabungan akaun dan peringkat menengah dengan skor churn lebih besar daripada 0.66.

  Apabila anda meramalkan pulangan pada peringkat akaun, semua akaun dianggap dalam mendapatkan nilai ciri purata untuk segmen pulangan. Untuk ramalan pulangan pada peringkat kedua untuk setiap akaun, pemerolehan segmen pulangan bergantung pada peringkat kedua item yang dipilih dalam tetingkap sisi. Sebagai contoh, jika item mempunyai tahap sekunder kategori produk (bekalan pejabat), maka hanya item yang mempunyai bekalan pejabat sebagai kategori produk dipertimbangkan apabila memperoleh nilai ciri purata untuk segmen churn. Logik ini digunakan untuk memastikan perbandingan saksama nilai ciri item dengan nilai purata merentas segmen rendah, sederhana dan pulangan tinggi.

  Dalam sesetengah kes, nilai purata segmen rendah, sederhana atau pulangan tinggi adalah kosong atau tidak tersedia kerana tidak ada item yang dimiliki oleh segmen pulangan yang sepadan berdasarkan definisi di atas.

  Pentafsiran nilai di bawah purata lajur rendah, sederhana dan tinggi adalah berbeza untuk ciri kategori seperti negara atau industri. Oleh kerana idea nilai ciri "purata", tidak diguna pakai pada ciri kategori, nilai dalam lajur ini ialah perkadaran pelanggan dalam segmen pulangan rendah, sederhana atau tinggi yang mempunyai nilai yang sama dengan ciri kategori yang sama berbanding dengan item yang dipilih dalam panel tepi.

---

 > [!NOTE]
 > Dalam entiti output untuk model ini, *ChurnScore* menunjukkan kebarangkalian churn dan *IsChurn* yang diramalkan adalah label binari berdasarkan *ChurnScore* dengan ambang 0.5. Jika ambang lalai ini tidak berfungsi untuk senario anda, [cipta segmen](segments.md#create-a-segment) baharu dengan ambang pilihan anda. Tidak semua pelanggan semestinya pelanggan aktif. Sebahagian daripada mereka mungkin tidak mempunyai apa-apa aktiviti untuk jangka masa panjang dan dianggap sebagai sudah dipulangkan, berdasarkan kepada definisi pulangan anda. Meramalkan risiko pulangan untuk pelanggan yang sudah pun membuat pulangan tidak berguna kerana mereka bukan khalayak yang minat.
>
> Untuk melihat skor churn, pergi ke **Entiti** > **Data** dan lihat tab data untuk entiti output yang anda takrifkan untuk model ini.

[!INCLUDE [footer-include](includes/footer-banner.md)]
