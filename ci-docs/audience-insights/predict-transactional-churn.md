---
title: Transaksi churn ramalan (mengandungi video)
description: Ramalkan sama ada pelanggan mempunyai risiko kerana tidak lagi membeli produk atau perkhidmatan anda.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 9aa208ad94dcb6b1e0f110a3f974c56de00bbd07
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355670"
---
# <a name="transaction-churn-prediction"></a>Ramalan pulangan transaksi

Ramalan pulangan transaksi membantu meramal jika pelanggan tidak lagi akan membeli produk atau perkhidmatan anda dalam tetingkap masa tertentu. Anda boleh mencipta ramalan pulangan baharu pada **Kecerdasan** > **Ramalan**. Pilih **Ramalan saya** untuk melihat ramalan lain yang telah anda cipta. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Untuk persekitaran berdasarkan akaun perniagaan, kita boleh meramalkan pulangan transaksi untuk akaun dan juga kombinasi akaun dan satu lagi tahap maklumat seperti kategori produk. Menambahkan dimensi boleh membantu mengetahui cara berkemungkinan akaun tersebut "Contoso" akan berhenti membeli kategori produk "alat tulis pejabat." Selain itu, untuk akaun perniagaan, kami juga boleh menggunakan AI untuk menjana senarai sebab yang berpotensi mengapa akaun berkemungkinan untuk pulangan untuk kategori maklumat peringkat kedua.

> [!TIP]
> Cuba tutorial untuk transaksi churn ramalan menggunakan data sampel: [Transaksi churn ramalan panduan sampel](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Prasyarat

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.
- Pengetahuan perniagaan untuk memahami makna pulangan untuk perniagaan anda. Kami menyokong definisi pulangan berasaskan masa yang bermaksud pelanggan dianggap sebagai telah mendapat pulangan selepas tempoh tiada pembelian.
- Data mengenai transaksi/pembelian anda dan sejarah mereka:
    - Pengecam transaksi untuk membezakan pembelian/transaksi.
    - Pengecam pelanggan untuk memadankan transaksi kepada pelanggan anda.
    - Tarikh peristiwa transaksi, yang mentakrifkan tarikh transaksi berlaku.
    - Skema data semantik untuk pembelian/transaksi memerlukan maklumat berikut:
        - **ID Transaksi**: Pengecam unik bagi pembelian atau transaksi.
        - **Tarikh Transaksi**: Tarikh pembelian atau transaksi.
        - **Nilai transaksi**: Nilai mata wang/berangka bagi transaksi/item.
        - (Pilihan) **ID produk unik**: ID produk atau perkhidmatan yang dibeli jika data anda berada pada peringkat baris item.
        - (Pilihan) **Sama ada transaksi ini adalah pulangan**: Medan benar/palsu yang mengenal pasti jika transaksi tersebut ialah pulangan atau tidak. Jika **Nilai transaksi** adalah negatif, kami juga akan menggunakan maklumat ini untuk simpulkan pulangan.
- (Pilihan) Data mengenai aktiviti pelanggan:
    - Pengecam aktiviti untuk membezakan aktiviti jenis yang sama.
    - Pengecam pelanggan untuk memetakan aktiviti kepada pelanggan anda.
    - Maklumat aktiviti yang mengandungi nama dan tarikh aktiviti.
    - Skema data semantik untuk aktiviti pelanggan termasuk:
        - **Kunci utama:** Pengecam unik untuk aktiviti. Contohnya, lawatan laman web atau rekod penggunaan yang menunjukkan pelanggan telah mencuba sampel produk anda.
        - **Cap masa:** Tarikh dan masa peristiwa dikenal pasti oleh kunci utama.
        - **Peristiwa:** Nama peristiwa yang anda mahu gunakan. Contohnya, medan yang dipanggil "UserAction" di dalam stor runcit mungkin kupon yang digunakan oleh pelanggan.
        - **Butiran:** Maklumat terperinci tentang peristiwa. Contohnya, medan yang dipanggil "CouponValue" dalam stor runcit mungkin nilai mata wang kupon tersebut.

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.
- Pengetahuan perniagaan untuk memahami makna pulangan untuk perniagaan anda. Kami menyokong definisi pulangan berasaskan masa yang bermaksud pelanggan dianggap sebagai telah mendapat pulangan selepas tempoh tiada pembelian.
- Data mengenai transaksi/pembelian anda dan sejarah mereka:
    - Pengecam transaksi untuk membezakan pembelian/transaksi.
    - Pengecam pelanggan untuk memadankan transaksi kepada pelanggan anda.
    - Tarikh peristiwa transaksi, yang mentakrifkan tarikh transaksi berlaku.
    - Skema data semantik untuk pembelian/transaksi memerlukan maklumat berikut:
        - **ID Transaksi**: Pengecam unik bagi pembelian atau transaksi.
        - **Tarikh Transaksi**: Tarikh pembelian atau transaksi.
        - **Nilai transaksi**: Nilai mata wang/berangka bagi transaksi/item.
        - (Pilihan) **ID produk unik**: ID produk atau perkhidmatan yang dibeli jika data anda berada pada peringkat baris item.
        - (Pilihan) **Sama ada transaksi ini adalah pulangan**: Medan benar/palsu yang mengenal pasti jika transaksi tersebut ialah pulangan atau tidak. Jika **Nilai transaksi** adalah negatif, kami juga akan menggunakan maklumat ini untuk simpulkan pulangan.
- (Pilihan) Data mengenai aktiviti pelanggan:
    - Pengecam aktiviti untuk membezakan aktiviti jenis yang sama.
    - Pengecam pelanggan untuk memetakan aktiviti kepada pelanggan anda.
    - Maklumat aktiviti yang mengandungi nama dan tarikh aktiviti.
    - Skema data semantik untuk aktiviti pelanggan termasuk:
        - **Kunci utama:** Pengecam unik untuk aktiviti. Contohnya, lawatan laman web atau rekod penggunaan yang menunjukkan pelanggan telah mencuba sampel produk anda.
        - **Cap masa:** Tarikh dan masa peristiwa dikenal pasti oleh kunci utama.
        - **Peristiwa:** Nama peristiwa yang anda mahu gunakan. Contohnya, medan yang dipanggil "UserAction" di dalam stor runcit mungkin kupon yang digunakan oleh pelanggan.
        - **Butiran:** Maklumat terperinci tentang peristiwa. Contohnya, medan yang dipanggil "CouponValue" dalam stor runcit mungkin nilai mata wang kupon tersebut.
- (Pilihan) Data tentang pelanggan anda:
    - Data ini sepatutnya sejajar ke arah lebih banyak atribut statik untuk memastikan model melakukan yang terbaik.
    - Skema data semantik untuk data pelanggan termasuk:
        - **CustomerID:** Pengecam unik untuk pelanggan.
        - **Tarikh Dicipta:** Tarikh pelanggan telah ditambah pada awalnya.
        - **Negeri atau Wilayah:** Negeri atau lokasi wilayah pelanggan.
        - **Negara:** Negara pelanggan.
        - **Industri:** Jenis industri pelanggan. Sebagai contoh, medan yang dipanggil "Industri" di dalam pemanggang kopi mungkin menunjukkan jika pelanggan adalah runcit.
        - **Pengelasan:** Pengkategorian pelanggan untuk perniagaan anda. Sebagai contoh, medan yang dipanggil "ValueSegment" dalam pemanggang kopi mungkin merupakan peringkat pelanggan berdasarkan saiz pelanggan.

---

- Ciri data yang disyorkan:
    - Data sejarah yang mencukupi: Data transaksi sekurang-kurangnya dua kali ganda tetingkap masa yang dipilih. Sebaik-baiknya, dua hingga tiga tahun sejarah transaksi. 
    - Berbilang pembelian bagi setiap pelanggan: Sesuai sekurang-kurangnya dua urus niaga bagi setiap pelanggan.
    - Bilangan pelanggan: Sekurang-kurangnya 10 profil pelanggan, sebaik-baiknya lebih daripada 1,000 pelanggan unik. Model ini akan gagal dengan kurang daripada 10 pelanggan dan data sejarah yang tidak mencukupi.
    - Kesempurnaan data: Kurang daripada 20% daripada nilai yang hilang dalam medan data entiti yang disediakan.

> [!NOTE]
> Untuk perniagaan yang mempunyai kekerapan pembelian pelanggan yang tinggi (setiap beberapa minggu), anda disyorkan untuk memilih tetingkap ramalan yang lebih pendek dan definisi pulangan. Untuk kekerapan pembelian rendah (setiap beberapa bulan atau sekali setahun), pilih tetingkap ramalan lebih panjang dan definisi pulangan.

## <a name="create-a-transaction-churn-prediction"></a>Mencipta ramalan pulangan transaksi

1. Dalam Customer Insights, pergi ke **Kepintaran** > **Ramalan**.

1. **Pilih jubin model** churn Pelanggan dan pilih **Gunakan model ini**.

1. Dalam anak tetingkap **Model pulangan pelanggan**, pilih **Transaksi** dan pilih **Mari Bermula**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Syot layar dengan transaksi dipilih pilihan dalam tetingkap model pulangan Pelanggan.":::
 
### <a name="name-model"></a>Model nama

1. Berikan nama untuk model bagi membezakannya daripada model lain.

1. Berikan nama untuk entiti output menggunakan huruf dan nombor sahaja, tanpa sebarang ruang. Itulah nama yang entiti model akan gunakan. 

1. Pilih **Seterusnya**.

### <a name="define-customer-churn"></a>Takrifkan pulangan pelanggan

1. **Tetapkan tetingkap ramalan**. Sebagai contoh, ramalkan risiko pulangan untuk pelanggan anda sepanjang 90 hari yang akan datang untuk menyelaraskan usaha pengekalan pemasaran anda. Meramalkan risiko pulangan untuk tempoh masa yang lebih panjang atau lebih pendek boleh menjadikan lebih sukar untuk menangani faktor dalam profil risiko pulangan anda, tetapi ia bergantung kepada keperluan perniagaan khusus anda.
   >[!TIP]
   > Anda boleh memilih **Simpan draf** pada bila-bila masa untuk menyimpan ramalan sebagai draf. Anda akan menemui ramalan draf dalam tab **Ramalan saya** untuk meneruskan.

1. Masukkan bilangan hari untuk mentakrifkan churn dalam **medan definisi** Churn. Sebagai contoh, jika pelanggan tidak membuat pembelian dalam tempoh 30 hari yang lalu, mereka mungkin dianggap sebagai telah memberikan pulangan untuk perniagaan anda. 

1. Pilih **Seterusnya** untuk teruskan.

### <a name="add-required-data"></a>Tambah data yang diperlukan

1. Pilih **Tambah data** dan pilih jenis aktiviti pada anak tetingkap sisi yang mengandungi transaksi yang diperlukan atau maklumat sejarah pembelian.

1. Di bawah **Pilih aktiviti**, pilih aktiviti tertentu daripada jenis aktiviti yang dipilih yang anda mahu pengiraan difokuskan.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Anak tetingkap sisi menunjukkan pemilihan aktiviti tertentu di bawah jenis semantik.":::

   Jika anda belum memetakan aktiviti pada jenis semantik lagi, pilih **Edit** untuk berbuat demikian. Pengalaman berpandu untuk memetakan aktiviti semantik terbuka. Petakan data anda kepada medan yang sepadan dalam jenis aktiviti yang dipilih.

1. Petakan atribut semantik pada medan yang diperlukan untuk menjalankan model. Jika medan di bawah tidak diisikan, konfigurasikan hubungan daripada entiti sejarah pembelian anda kepada entiti *Pelanggan*. Pilih **Simpan**.

1. **Dalam langkah Tambah data** yang diperlukan, pilih **Berikut** untuk meneruskan jika anda tidak mahu menambah lebih banyak aktiviti.


# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Tambah data tambahan (pilihan)

Konfigurasikan hubungan daripada entiti aktiviti pelanggan anda kepada entiti *Pelanggan*.

1. Pilih medan yang mengenal pasti pelanggan dalam jadual aktiviti pelanggan. Ia boleh berkait secara langsung dengan ID pelanggan utama entiti *Pelanggan* anda.

1. Pilih entiti yang merupakan entiti *Pelanggan* utama anda.

1. Masukkan nama yang menghuraikan perhubungan.

#### <a name="customer-activities"></a>Aktiviti pelanggan

1. Secara alternatif, pilih **Tambah data** untuk **Aktiviti pelanggan**.

1. Pilih jenis aktiviti semantik yang mengandungi data yang anda mahu gunakan, kemudian pilih satu atau lebih aktiviti dalam bahagian **Aktiviti**.

1. Pilih jenis aktiviti yang sepadan dengan jenis aktiviti pelanggan yang anda konfigurasikan. Pilih **Cipta baharu** dan pilih jenis aktiviti tersedia atau cipta jenis baharu.

1. Pilih **Seterusnya**, kemudian **Simpan**.

1. Jika anda mempunyai sebarang aktiviti pelanggan lain yang anda mahu sertakan, ulangi langkah di atas.

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

### <a name="select-prediction-level"></a>Pilih tahap ramalan

Kebanyakan ramalan dicipta pada tahap pelanggan. Dalam sesetengah keadaan, ia mungkin tidak cukup perincian untuk menangani keperluan perniagaan anda. Anda boleh menggunakan ciri ini untuk meramalkan pulangan untuk cawangan pelanggan, sebagai contoh, bukannya untuk pelanggan secara keseluruhan.

1. Untuk mencipta ramalan pada peringkat lebih banyak butiran daripada pelanggan, pilih **Pilih entiti untuk peringkat kedua**. Jika pilihan tidak tersedia, pastikan anda telah melengkapkan bahagian sebelum ini.

1. Kembangkan entiti yang anda mahu pilih peringkat kedua daripada atau gunakan kotak penapis carian untuk menapis pilihan yang dipilih.

1. Pilih atribut yang anda mahu gunakan sebagai tahap kedua kemudian pilih **Tambah**.

1. Pilih **Seterusnya**.

> [!NOTE]
> Entiti yang tersedia dalam bahagian ini ditunjukkan kerana mereka mempunyai perhubungan dengan entiti yang anda pilih dalam bahagian sebelumnya. Jika anda tidak nampak entiti yang anda mahu tambah, pastikan ia mempunyai perhubungan sah yang wujud dalam **Perhubungan**. Hanya satu ke satu dan perhubungan banyak ke satu adalah sah untuk konfigurasi ini.

### <a name="add-additional-data-optional"></a>Tambah data tambahan (pilihan)

Konfigurasikan hubungan daripada entiti aktiviti pelanggan anda kepada entiti *Pelanggan*.

1. Pilih medan yang mengenal pasti pelanggan dalam jadual aktiviti pelanggan. Ia boleh berkait secara langsung dengan ID pelanggan utama entiti *Pelanggan* anda.

1. Pilih entiti yang merupakan entiti *Pelanggan* utama anda.

1. Masukkan nama yang menghuraikan perhubungan.

#### <a name="customer-activities"></a>Aktiviti pelanggan

1. Secara alternatif, pilih **Tambah data** untuk **Aktiviti pelanggan**.

1. Pilih jenis aktiviti semantik yang mengandungi data yang anda mahu gunakan, kemudian pilih satu atau lebih aktiviti dalam bahagian **Aktiviti**.

1. Pilih jenis aktiviti yang sepadan dengan jenis aktiviti pelanggan yang anda konfigurasikan. Pilih **Cipta baharu** dan pilih jenis aktiviti tersedia atau cipta jenis baharu.

1. Pilih **Seterusnya**, kemudian **Simpan**.

1. Jika anda mempunyai sebarang aktiviti pelanggan lain yang anda mahu sertakan, ulangi langkah di atas.

#### <a name="customers-data"></a>Data pelanggan

1. Secara pilihan, pilih **Tambah data** untuk **Data pelanggan**.

1. Peta atribut semantik ke medan dalam data pelanggan anda sendiri sebagaimana dikenal pasti. Data dalam medan yang digunakan tidak perlu diubah selalu untuk memastikan prestasi terbaik model. Sebagai contoh, memilih medan untuk "Pengelasan" yang ditukar setiap bulan hanya akan mempunyai nilai terakhir yang digunakan dalam ramalan, walaupun sejarah nilai yang sama mungkin tidak digunakan kepada pelanggan apabila membina corak ramalan.

1. Pilih **Seterusnya**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Menyediakan senarai pilihan akaun penanda aras

Tambah senarai pelanggan dan akaun perniagaan anda yang anda mahu gunakan sebagai penanda aras. Anda akan mendapat [butiran untuk akaun penanda aras ini](#review-a-prediction-status-and-results) termasuk skor pulangan mereka dan ciri paling berpengaruh yang menjejaskan ramalan pulangan mereka.

1. Pilih **+ Tambah pelanggan**.

1. Pilih pelanggan yang bertindak sebagai penanda aras.

1. Pilih **Seterusnya** untuk teruskan.

---

### <a name="set-schedule-and-review-configuration"></a>Tetapkan jadual dan konfigurasi ulasan

1. Tetapkan kekerapan untuk melatih semula model anda. Tetapan ini adalah penting untuk mengemas kini ketepatan ramalan kerana data baru telah dimasukkan. Kebanyakan perniagaan boleh melatih semula sekali setiap bulan dan mendapatkan ketepatan yang baik untuk ramalan mereka.

1. Pilih **Seterusnya**.

1. Semak semula konfigurasi ramalan. Anda boleh kembali ke langkah awal dengan memilih **Edit** di bawah nilai yang ditunjukkan. Atau anda boleh memilih langkah konfigurasi daripada penunjuk kemajuan.

1. Jika semua nilai dikonfigurasikan dengan betul, pilih **Simpan dan jalankan** untuk memulakan proses ramalan. Pada tab **Langganan saya**, anda boleh melihat status ramalan anda. Proses mungkin mengambil masa beberapa jam untuk dilengkapkan bergantung kepada amaun data yang digunakan dalam ramalan.

## <a name="review-a-prediction-status-and-results"></a>Semak semula status dan hasil ramalan

1. Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.

1. Pilih ramalan yang anda mahu semak semula.
   - **Nama ramalan**: Nama ramalan yang diberikan semasa menciptanya.
   - **Jenis ramalan**: Jenis model yang digunakan untuk ramalan
   - **Entiti output**: Nama entiti untuk menyimpan output ramalan. Anda boleh menemui entiti dengan nama ini pada **Data** > **Entiti**.
     Dalam entiti output, *ChurnScore* adalah kebarangkalian yang diramalkan untuk pulangan dan *IsChurn* adalah label binari berdasarkan *ChurnScore* dengan ambang 0.5. Ambang lalai mungkin tidak berfungsi untuk senario anda. [Cipta segmen baharu](segments.md#create-a-new-segment) dengan ambang pilihan anda.
     Tidak semua pelanggan semestinya pelanggan aktif. Sebahagian daripada mereka mungkin tidak mempunyai apa-apa aktiviti untuk jangka masa panjang dan dianggap sebagai sudah dipulangkan, berdasarkan kepada definisi pulangan anda. Meramalkan risiko pulangan untuk pelanggan yang sudah pun membuat pulangan tidak berguna kerana mereka bukan khalayak yang minat.
   - **Medan ramalan**: Medan ini diisikan hanya untuk beberapa jenis ramalan dan tidak digunakan dalam ramalan pulangan.
   - **Status**: Status jalanan ramalan.
        - **Dibariskan**: Ramalan sedang menunggu proses lain untuk berjalan.
        - **Menyegarkan semula**: Ramalan sedang berjalan untuk menghasilkan hasil yang akan mengalir ke dalam entiti output.
        - **Gagal**: Jalanan ramalan gagal. [Ulasan log](manage-predictions.md#troubleshoot-a-failed-prediction) untuk maklumat lanjut.
        - **Berjaya**: Ramalan telah berjaya. Pilih **Pandangan** di bawah elipsis menegak untuk menyemak semula langganan
   - **Diedit**: Tarikh konfigurasi untuk ramalan telah diubah.
   - **Terakhir disegar semula**: Tarikh ramalan menyegar semula hasil dalam entiti output.

1. Pilih elipsis menegak di sebelah ramalan yang anda mahu semak semula hasilnya dan pilih **Pandangan**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Lihat kawalan untuk melihat keputusan ramalan.":::

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

1. Terdapat tiga bahagian utama data dalam halaman hasil:
   - **Melatih prestasi model**: A, B atau C ialah skor yang berkemungkinan. Skor ini menunjukkan prestasi ramalan dan boleh membantu anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entiti output. Skor ditentukan berdasarkan peraturan yang berikut: 
        - **A** apabila model meramalkan dengan tepat sekurang-kurangnya 50% daripada jumlah ramalan dan apabila peratusan ramalan yang tepat untuk pelanggan yang telah memberikan pulangan adalah lebih besar daripada kadar garis dasar sekurang-kurangnya 10%.
            
        - **B** apabila model meramalkan dengan tepat sekurang-kurangnya 50% daripada jumlah ramalan dan apabila peratusan ramalan yang tepat untuk pelanggan yang telah memberikan pulangan adalah sehingga 10% lebih besar daripada garis dasar.
            
        - **C** apabila model meramalkan dengan tepat kurang 50% daripada jumlah ramalan atau apabila peratusan ramalan yang tepat untuk pelanggan yang telah memberikan pulangan adalah kurang daripada garis dasar.
               
        - **Garis dasar** mengambil input tetingkap masa ramalan untuk model (contohnya, satu tahun) dan model mencipta pecahan masa yang berbeza dengan membahagikannya kepada 2 sehingga ia mencapai satu bulan atau kurang. Ia menggunakan bahagian ini untuk mewujudkan satu peraturan perniagaan bagi pelanggan yang belum membeli dalam tempoh masa ini. Pelanggan ini dianggap sebagai yang memberi pulangan. Peraturan perniagaan berasaskan masa dengan keupayaan tertinggi untuk meramalkan siapa yang mungkin memberikan pulangan dipilih sebagai model garis dasar.
            
    - **Kecenderungan untuk pulangan (bilangan pelanggan)**: Kumpulan pelanggan berdasarkan risiko pulangan mereka yang diramalkan. Data ini boleh membantu anda kemudian jika anda mahu mencipta segmen pelanggan dengan risiko pulangan yang tinggi. Segmen seperti ini dapat membantu memahami tempat penggalan anda yang sepatutnya bagi keahlian segmen.
       
    - **Faktor paling mempengaruhi**: Terdapat banyak faktor yang diambil kira apabila mencipta ramalan anda. Setiap faktor mempunyai kepentingannya yang dikira untuk ramalan teragregat yang dicipta oleh model. Anda boleh menggunakan faktor ini untuk membantu mengesahkan keputusan ramalan anda atau anda boleh menggunakan maklumat ini kemudian untuk [mencipta segmen](segments.md) yang boleh membantu mempengaruhi risiko pulangan untuk pelanggan.


# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

1. Terdapat tiga bahagian utama data dalam halaman hasil:
   - **Melatih prestasi model**: A, B atau C ialah skor yang berkemungkinan. Skor ini menunjukkan prestasi ramalan dan boleh membantu anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entiti output. Skor ditentukan berdasarkan peraturan yang berikut: 
        - **A** apabila model meramalkan dengan tepat sekurang-kurangnya 50% daripada jumlah ramalan dan apabila peratusan ramalan yang tepat untuk pelanggan yang telah memberikan pulangan adalah lebih besar daripada kadar garis dasar sekurang-kurangnya 10%.
            
        - **B** apabila model meramalkan dengan tepat sekurang-kurangnya 50% daripada jumlah ramalan dan apabila peratusan ramalan yang tepat untuk pelanggan yang telah memberikan pulangan adalah sehingga 10% lebih besar daripada garis dasar.
            
        - **C** apabila model meramalkan dengan tepat kurang 50% daripada jumlah ramalan atau apabila peratusan ramalan yang tepat untuk pelanggan yang telah memberikan pulangan adalah kurang daripada garis dasar.
               
        - **Garis dasar** mengambil input tetingkap masa ramalan untuk model (contohnya, satu tahun) dan model mencipta pecahan masa yang berbeza dengan membahagikannya kepada 2 sehingga ia mencapai satu bulan atau kurang. Ia menggunakan bahagian ini untuk mewujudkan satu peraturan perniagaan bagi pelanggan yang belum membeli dalam tempoh masa ini. Pelanggan ini dianggap sebagai yang memberi pulangan. Peraturan perniagaan berasaskan masa dengan keupayaan tertinggi untuk meramalkan siapa yang mungkin memberikan pulangan dipilih sebagai model garis dasar.
            
    - **Kecenderungan untuk pulangan (bilangan pelanggan)**: Kumpulan pelanggan berdasarkan risiko pulangan mereka yang diramalkan. Data ini boleh membantu anda kemudian jika anda mahu mencipta segmen pelanggan dengan risiko pulangan yang tinggi. Segmen seperti ini dapat membantu memahami tempat penggalan anda yang sepatutnya bagi keahlian segmen.
       
    - **Faktor paling mempengaruhi**: Terdapat banyak faktor yang diambil kira apabila mencipta ramalan anda. Setiap faktor mempunyai kepentingannya yang dikira untuk ramalan teragregat yang dicipta oleh model. Anda boleh menggunakan faktor ini untuk membantu mengesahkan keputusan ramalan anda atau anda boleh menggunakan maklumat ini kemudian untuk [mencipta segmen](segments.md) yang boleh membantu mempengaruhi risiko pulangan untuk pelanggan.


1. Untuk akaun perniagaan, anda akan menemui halaman maklumat **Analisis ciri yang berpengaruh**. Ia mengandungi empat seksyen data:

    - Item yang dipilih dalam tetingkap kanan menentukan kandungan pada halaman ini. Pilih item daripada **Pelanggan teratas** atau **Pelanggan penanda aras**. Kedua-dua senarai disusun mengikut nilai yang berkurangan daripada skor pulangan, sama ada skor hanya untuk pelanggan atau skor gabungan untuk pelanggan dan peringkat kedua seperti kategori produk.
        
        - **Pelanggan teratas** : Senarai 10 pelanggan yang berada di risiko tertinggi pulangan dan risiko paling rendah pulangan berdasarkan skor pulangan mereka. 
        - **Pelanggan penanda aras** : Senarai hingga 10 pelanggan yang dipilih semasa mengkonfigurasi model.
 
    - **Skor pulangan:** Menunjukkan skor pulangan untuk item terpilih dalam tetingkap kanan.
    
    - **Pengagihan risiko pulangan:** Menunjukkan pengagihan risiko pulangan merentasi pelanggan dan persentil dalam mana pelanggan yang terpilih. 
    
    - **Ciri teratas meningkat dan mengurangkan risiko pulangan:** Untuk item terpilih dalam tetingkap kanan, lima ciri teratas yang meningkat dan menurun risiko pulangan disenaraikan. Untuk setiap ciri yang berpengaruh, anda mendapati nilai ciri untuk item tersebut dan pengaruh pada skor pulangan. Nilai purata setiap ciri merentas segmen pelanggan yang rendah, sederhana dan pulangan tinggi juga ditunjukkan. Ia membantu untuk kontekstual lebih baik nilai ciri yang paling berpengaruh untuk item terpilih dan bandingkan dengan segmen pelanggan rendah, sederhana dan pulangan tinggi.

       - Rendah: akaun atau gabungan akaun dan peringkat kedua dengan skor pulangan antara 0 dan 0.33
       - Sederhana: akaun atau gabungan akaun dan peringkat kedua dengan skor pulangan antara 0.33 dan 0.66
       - Tinggi: akaun atau gabungan akaun dan peringkat kedua dengan skor pulangan lebih besar daripada 0.66
    
       Apabila anda meramalkan pulangan pada peringkat akaun, semua akaun dianggap dalam mendapatkan nilai ciri purata untuk segmen pulangan. Untuk ramalan pulangan pada peringkat kedua untuk setiap akaun, pemerolehan segmen pulangan bergantung pada peringkat kedua item yang dipilih dalam tetingkap sisi. Sebagai contoh, jika item mempunyai peringkat kedua kategori produk = bekalan pejabat, kemudian hanya item yang mempunyai bekalan pejabat sebagai kategori produk dipertimbangkan apabila mendapatkan nilai ciri purata untuk segmen pulangan. Logik ini digunakan untuk memastikan perbandingan saksama nilai ciri item dengan nilai purata merentas segmen rendah, sederhana dan pulangan tinggi.

       Dalam sesetengah kes, nilai purata segmen rendah, sederhana atau pulangan tinggi adalah kosong atau tidak tersedia kerana tidak ada item yang dimiliki oleh segmen pulangan yang sepadan berdasarkan definisi di atas.
       
       > [!NOTE]
       > Pentafsiran nilai di bawah purata lajur rendah, sederhana dan tinggi adalah berbeza untuk ciri kategori seperti negara atau industri. Oleh kerana idea nilai ciri "purata", tidak diguna pakai pada ciri kategori, nilai dalam lajur ini ialah perkadaran pelanggan dalam segmen pulangan rendah, sederhana atau tinggi yang mempunyai nilai yang sama dengan ciri kategori yang sama berbanding dengan item yang dipilih dalam panel tepi.

---

## <a name="manage-predictions"></a>Urus ramalan

Ada kemungkinan untuk mengoptimumkan, menyelesaikan masalah, menyegarkan semula atau memadam ramalan. Semak laporan kebolehgunaan data input untuk mengetahui cara membuat ramalan lebih cepat dan lebih dipercayai. Untuk maklumat lanjut, pergi ke [Urus ramalan](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
