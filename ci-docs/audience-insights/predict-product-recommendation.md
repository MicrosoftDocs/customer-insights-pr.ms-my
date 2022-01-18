---
title: Ramalan pengesyoran produk
description: Meramalkan produk yang pelanggan mungkin akan beli atau berinteraksi dengannya.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 62b829b6ca3074e0ca52fb52584b74572bb05f05
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967850"
---
# <a name="product-recommendation-prediction-preview"></a>Ramalan pengesyoran produk (pratonton)

Model pengesyoran produk mencipta set pengesyoran produk ramalan. Pengesyoran adalah berdasarkan tingkah laku pembelian sebelumnya dan pelanggan dengan corak pembelian yang sama. Anda boleh mencipta ramalan pengesyoran produk baru pada halaman **Kecerdasan** > **Ramalan**. Pilih **Ramalan saya** untuk melihat ramalan lain yang telah anda cipta.

Pengesyoran produk mungkin tertakluk kepada undang-hukum tempatan dan peraturan dan jangkaan pelanggan, yang mana model yang tidak dibina secara khusus diambil kira.  Sebagai pengguna keupayaan ramalan ini, **anda perlu menyemak pengesyoran sebelum dihantar kepada pelanggan anda** untuk memastikan bahawa anda mematuhi sebarang undang-undang atau peraturan yang berkaitan, dan jangkaan pelanggan untuk apa yang anda akan syorkan. 

Di samping itu, output model ini akan memberi anda pengesyoran berdasarkan ID produk. Mekanisme penghantaran anda perlu memetakan ID produk yang diramalkan kepada kandungan yang sesuai untuk pelanggan anda ke akaun untuk penyetempatan, kandungan imej dan kandungan perniagaan tertentu atau tingkah laku lain.

## <a name="sample-guide"></a>Panduan Sampel

Jika anda berminat untuk mencuba ciri ini tetapi tidak mempunyai data untuk melengkapkan keperluan di bawah, anda boleh [membuat pelaksanaan sampel](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.

- Pengetahuan perniagaan untuk memahami jenis produk berbeza untuk perniagaan anda dan cara pelanggan anda berinteraksi dengan mereka. Kami menyokong mengesyorkan produk yang telah dibeli sebelum oleh pelanggan anda atau pengesyoran untuk produk baru.

- Data tentang transaksi, pembelian dan sejarah mereka:
    - Pengecam transaksi untuk membezakan pembelian atau transaksi.
    - Pengecam pelanggan untuk memetakan transaksi kepada pelanggan anda.
    - Tarikh peristiwa transaksi yang menentukan tarikh transaksi berlaku.
    - Maklumat ID produk untuk transaksi.
    - (Pilihan) Entiti data katalog produk untuk menggunakan penapis produk.
    - (Pilihan) Jika transaksi adalah pulangan atau tidak.
    - Skema data semantik memerlukan maklumat berikut:
        - **ID transaksi:** Pengecam unik bagi pembelian atau transaksi.
        - **Tarikh transaksi:** Tarikh pembelian atau transaksi.
        - **Nilai transaksi:** Jumlah nilai berangka bagi pembelian atau transaksi.
        - **ID produk unik:** ID produk atau perkhidmatan yang dibeli jika data anda berada pada peringkat baris item.
        - (Pilihan) **Pembelian atau pulangan:** Medan boolean di mana nilai *benar* mengenal pasti bahawa transaksi adalah pulangan. Jika data Pembelian atau Pulangan tidak diberikan model dan **Nilai transaksi** adalah negatif, kami juga akan menggunakan maklumat ini untuk membuat pulangan.
- Ciri data yang disyorkan:
    - Data sejarah yang mencukupi: Sekurang-kurangnya satu tahun data transaksi, sebaik-baiknya dua hingga tiga tahun hingga termasuk beberapa musim.
    - Berbilang pembelian bagi setiap pelanggan: Tiga atau lebih transaksi bagi setiap ID Pelanggan
    - Bilangan pelanggan: Sekurang-kurangnya 100 pelanggan, sebaik-baiknya lebih daripada 10,000 pelanggan. Model ini akan gagal jika kurang daripada 100 pelanggan.

> [!NOTE]
> - Model ini memerlukan sejarah transaksi pelanggan anda. Takrifan transaksi agak fleksibel. Sebarang data yang menerangkan interaksi produk pengguna boleh berfungsi sebagai input. Sebagai contoh, membeli produk, mengambil kelas, atau menghadiri acara.
> - Hanya satu entiti sejarah transaksi boleh dikonfigurasikan buat masa ini. Jika terdapat berbilang entiti pembelian, Power Query serikatnya sebelum pengingesan data.
> - Jika butiran pesanan dan pesanan adalah entiti yang berbeza, gabungkannya sebelum menggunakan model. Model ini tidak berfungsi dengan hanya ID pesanan atau ID resit dalam entiti.


## <a name="create-a-product-recommendation-prediction"></a>Cipta ramalan pengesyoran produk

1. Dalam Customer Insights, pergi ke **Kepintaran** > **Ramalan**.

1. Pilih jubin **Model pengesyoran produk (pratonton)** dan pilih **Gunakan model ini**.
   > [!div class="mx-imgBorder"]
   > ![Jubin model Pengesyoran Produk dengan butang Gunakan model ini.](media/product-recommendation-usethismodel.PNG "Jubin model Pengesyoran Produk dengan butang Gunakan model ini")

1. Semak maklumat tentang keperluan model. Jika anda mempunyai data yang diperlukan, pilih **Bermula**.

### <a name="name-model"></a>Model nama

1. Berikan nama untuk model bagi membezakannya daripada model lain.

1. Masukkan nama untuk entiti output menggunakan huruf dan nombor sahaja, tanpa sebarang ruang. Itulah nama yang entiti model akan gunakan. Kemudian pilih **Seterusnya**.

### <a name="define-product-recommendation-configuration"></a>Tentukan konfigurasi pengesyoran produk

1. Tetapkan **Bilangan produk** yang anda ingin cadangkan kepada pelanggan. Nilai ini bergantung kepada cara kaedah penghantaran anda mengisi data. Jika anda boleh mengesyorkan tiga produk, tetapkan nilai ini dengan sewajarnya.
   
   >[!TIP]
   > Anda boleh memilih **Simpan draf** pada bila-bila masa untuk menyimpan ramalan sebagai draf. Anda akan menemui draf ramalan dalam tab **Ramalan saya**.

1. Pilih sama ada anda ingin menyertakan produk yang dibeli oleh pelanggan baru-baru ini dalam **medan Ulang pembelian yang** dijangkakan.

1. Setkan **tetingkap Lihat ke belakang**. Tetapan ini menentukan tempoh masa model mempertimbangkan sebelum mengesyorkan produk kepada pengguna semula. Sebagai contoh, nyatakan pelanggan membeli komputer riba setiap dua tahun. Tetingkap ini akan melihat pada sejarah pembelian sejak dua tahun yang lalu, dan jika mereka menemui item, item akan ditapis daripada pengesyoran.

1. Pilih **Seterusnya**

### <a name="add-required-data"></a>Tambah data yang diperlukan

1. Pilih **Tambah data** dan pilih jenis aktiviti pada anak tetingkap sisi yang mengandungi transaksi yang diperlukan atau maklumat sejarah pembelian.

1. Di bawah **Pilih aktiviti**, pilih aktiviti khusus daripada aktiviti terpilih yang anda mahu pengiraan itu difokuskan.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Anak tetingkap sisi menunjukkan pemilihan aktiviti tertentu di bawah jenis semantik.":::

1. Jika anda belum memetakan aktiviti pada jenis semantik lagi, pilih **Edit** untuk berbuat demikian. Pengalaman berpandu untuk memetakan aktiviti semantik terbuka. Petakan data anda kepada medan yang sepadan dalam jenis aktiviti yang dipilih.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Halaman tetapan jenis aktiviti.":::

1. Selepas pemetaan aktiviti pada jenis semantik yang sepadan, pilih **Seterusnya** untuk teruskan 
 
1. Petakan atribut semantik pada medan yang diperlukan untuk menjalankan model.

1. Pilih **Simpan**.

1. Pilih **Seterusnya**.


### <a name="configure-product-filters"></a>Konfigurasikan penapis produk

Kadang-kadang, hanya produk tertentu yang bermanfaat atau sesuai untuk jenis ramalan yang anda bina. Penapis produk membolehkan anda mengenal pasti subset produk dengan ciri-ciri tertentu untuk disyorkan kepada pelanggan anda. Model ini akan menggunakan semua produk yang tersedia untuk mempelajari corak tetapi hanya menggunakan produk yang sepadan dengan penapis produk dalam outputnya.

1. Dalam langkah **Tambah maklumat produk**, tambah katalog produk anda dengan maklumat untuk setiap produk. Peta maklumat yang diperlukan dalam pilih **Seterusnya**.

3. Dalam langkah **Penapis produk**, pilih antara pilihan berikut.

   * **Tiada penapis** : Gunakan semua produk dalam ramalan pengesyoran produk.

   * **Tentukan penapis produk khusus**: Gunakan produk tertentu dalam ramalan pengesyoran produk.

1. Pilih **Seterusnya**.

1. Jika anda memilih untuk menentukan penapis produk, anda perlu menentukannya sekarang. Dalam anak tetingkap **Atribut katalog produk**, pilih atribut daripada *entiti Katalog Produk* anda yang anda mahu sertakan dalam penapis.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Anak tetingkap sisi yang menunjukkan dikaitkan dalam entiti katalog produk untuk dipilih untuk penapis produk.":::

1. Pilih jika anda mahu penapis produk menggunakan penyambung **dan** atau **atau** untuk menggabungkan pilihan atribut anda secara logik daripada katalog produk.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Konfigurasi sampel untuk penapis produk yang digabungkan dengan penyambung logik DAN.":::

1. Pilih **Seterusnya**.

### <a name="set-update-schedule-and-review-configuration"></a>Tetapkan jadual kemas kini dan konfigurasi semakan

1. Tetapkan kekerapan untuk melatih semula model anda. Tetapan ini penting untuk mengemas kini ketepatan ramalan ketika data baharu diimport ke dalam Customer Insights. Kebanyakan perniagaan boleh melatih semula sekali setiap bulan dan mendapatkan ketepatan yang baik untuk ramalan mereka.

1. Pilih **Seterusnya**.

1. Semak semula konfigurasi. Anda boleh kembali ke mana-mana bahagian konfigurasi ramalan dengan memilih **Edit** di bawah nilai yang ditunjukkan. Atau anda boleh memilih langkah konfigurasi daripada penunjuk kemajuan.

1. Jika semua nilai dikonfigurasikan dengan betul, pilih **Simpan dan jalankan** untuk memulakan proses ramalan. Pada tab **Langganan saya**, anda boleh melihat status ramalan anda. Proses mungkin mengambil masa beberapa jam untuk dilengkapkan bergantung kepada amaun data yang digunakan dalam ramalan.

## <a name="review-a-prediction-status-and-results"></a>Semak semula status dan hasil ramalan

1. Pergi ke tab **Ramalan saya** pada **Kecerdasan** > **Ramalan**.
   > [!div class="mx-imgBorder"]
   > ![Pandangan halaman Ramalan Saya.](media/product-recommendation-mypredictions.PNG "Pandangan halaman Ramalan Saya")

1. Pilih ramalan yang anda mahu semak semula.
   - **Nama ramalan:** Nama ramalan yang disediakan apabila menciptanya.
   - **Jenis ramalan:** Jenis model yang digunakan untuk ramalan
   - **Entiti output:** Nama entiti untuk menyimpan output ramalan. Anda boleh menemui entiti dengan nama ini pada **Data** > **Entiti**.    
      *Skor* dalam entiti output ialah langkah kuantitatif untuk pengesyoran. Model ini mengesyorkan produk yang mempunyai skor yang lebih tinggi ke atas produk yang mempunyai skor yang lebih rendah.
   - **Medan ramalan**: Medan ini diisi hanya untuk beberapa jenis ramalan, dan tidak digunakan dalam ramalan Pengesyoran Produk.
   - **Status:** Status semasa jalanan ramalan.
        - **Dibaris gilir:** Ramalan pada masa ini menunggu proses lain untuk berjalan.
        - **Menyegar semula:** Ramalan pada masa ini menjalankan peringkat pemprosesan "skor" untuk menghasilkan hasil yang akan mengalir ke dalam entiti output.
        - **Gagal:** ramalan telah gagal. Pilih **Log** untuk butiran lanjut.
        - **Berjaya:** ramalan telah berjaya. Pilih **Pandangan** di bawah elipsis menegak untuk menyemak semula langganan
   - **Diedit:** Tarikh konfigurasi untuk ramalan telah diubah.
   - **Terakhir disegar semula:** Tarikh ramalan menyegar semula hasil dalam entiti output.

1. Pilih elipsis menegak di sebelah ramalan yang anda mahu semak semula hasilnya dan pilih **Pandangan**.
   > [!div class="mx-imgBorder"]
   > ![Pandangan pilihan dalam menu elipsis menegak untuk ramalan termasuk edit, segar semula, pandangan, log dan padam.](media/product-recommendation-verticalellipses.PNG "Pandangan pilihan dalam elipsis menegak untuk ramalan termasuk edit, segar semula, pandangan, log dan padam")

1. Terdapat lima bahagian utama data dalam halaman keputusan:
    1. **Melatih prestasi model:** A, B atau C ialah skor yang mungkin. Skor ini menunjukkan prestasi ramalan dan boleh membantu anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entiti output.
        - Skor ditentukan berdasarkan peraturan yang berikut:
            - **A** Model ini akan dianggap kualiti **A** jika metrik "Kejayaan @ K" adalah sekurang-kurangnya 10% lebih garis dasar. 
            - **B** Model ini akan dianggap kualiti **B** jika metrik "Kejayaan @ K" adalah 0% hingga 10% lebih daripada garis dasar.
            - **C** Model ini akan dianggap kualiti **C** jika metrik "Kejayaan @ K" adalah 0% hingga 10% kurang daripada garis dasar.
               
               > [!div class="mx-imgBorder"]
               > ![Pandangan hasil prestasi model.](media/product-recommendation-modelperformance.PNG "Pandangan hasil prestasi model")
            - **Garis dasar**: Model ini mengambil produk yang paling disyorkan oleh kiraan pembelian merentasi semua pelanggan, dan menggunakan peraturan yang dipelajari yang dikenal pasti oleh model untuk mencipta satu set pengesyoran untuk pelanggan. Ramalan kemudiannya dibandingkan dengan produk teratas, seperti yang dikira oleh bilangan pelanggan yang telah membeli produk tersebut. Jika pelanggan mempunyai sekurang-kurangnya satu produk dalam produk yang disyorkan yang juga dilihat dalam produk yang dibeli teratas, mereka dianggap sebagai sebahagian daripada garis dasar. Jika terdapat 10 pelanggan ini yang mempunyai produk yang disyorkan yang dibeli daripada 100 jumlah pelanggan, garis dasar akan menjadi 10%.
            - **Kejayaan @ K**: Menggunakan satu set pengesahan tempoh masa transaksi, pengesyoran dicipta untuk semua pelanggan dan dibandingkan dengan set pengesahan transaksi. Sebagai contoh, dalam tempoh 12 bulan, bulan 12 mungkin diketepikan sebagai set pengesahan data. Jika model meramalkan sekurang-kurangnya satu perkara yang anda akan membeli dalam bulan 12 berdasarkan apa yang dipelajari daripada 11 bulan sebelumnya, pelanggan akan meningkatkan metrik "Kejayaan @ K".
    
    1. **Produk yang paling dicadangkan (dengan selaras):** Lima produk teratas yang diramalkan untuk pelanggan anda.
       > [!div class="mx-imgBorder"]
       > ![Graf menunjukkan 5 produk teratas yang paling disyorkan.](media/product-recommendation-topproducts.PNG "Graf menunjukkan 5 produk teratas yang paling disyorkan")
    
    1. **Faktor pengesyoran utama**: Model ini menggunakan sejarah transaksi pelanggan untuk membuat pengesyoran produk. Ia mempelajari corak berdasarkan pembelian masa lalu dan mendapati persamaan antara pelanggan dan produk. Persamaan ini kemudiannya digunakan untuk menjana pengesyoran produk.
    Berikut adalah faktor-faktor yang boleh mempengaruhi pengesyoran produk yang dihasilkan oleh model. 
        - **Transaksi masa lalu** : Corak pembelian pada masa lalu telah digunakan oleh model untuk menjana pengesyoran produk. Sebagai contoh, model ini boleh mengesyorkan _Surface Arc Mouse_ jika seseorang membeli _Surface Book 3_ dan _Surface Pen_ baru-baru ini. Model ini mengetahui bahawa dari segi sejarah, ramai pelanggan telah membeli _Surface Arc Mouse_ selepas membeli _Surface Book 3_ dan _Surface Pen_.
        - **Persamaan pelanggan**: Produk yang disyorkan telah dibeli dari segi sejarah oleh pelanggan lain yang menunjukkan corak pembelian yang sama. Sebagai contoh, John disyorkan _Surface Headphones 2_ kerana Jennifer dan Brad baru-baru ini membeli _Surface Headphones 2_. Model ini percaya John adalah serupa dengan Jennifer dan Brad kerana mereka mempunyai sejarah corak pembelian yang sama.
        - **Persamaan produk**: Produk yang disyorkan adalah sama dengan produk lain yang dibeli oleh pelanggan sebelum ini. Model ini menganggap dua produk menjadi serupa jika dibeli bersama atau oleh pelanggan yang serupa. Sebagai contoh, seseorang mendapat pengesyoran untuk _Pemacu Storan USB_ kerana mereka sebelum ini membeli _USB-C hingga Penyesuai USB_ dan model percaya bahawa _Pemacu Storan USB_ adalah serupa dengan _USB-C kepada Penyesuai USB_ berdasarkan corak pembelian sejarah.

        Setiap pengesyoran produk dipengaruhi oleh satu atau lebih faktor ini. Peratusan pengesyoran yang mana setiap faktor yang mempengaruhi dan memainkan peranan digambarkan dalam carta. Dalam contoh berikut, 100% daripada pengesyoran dipengaruhi oleh transaksi masa lalu, 60% oleh persamaan pelanggan dan 22% oleh persamaan produk. Tuding pada bar dalam carta untuk melihat peratusan yang tepat di tempat faktor yang mempengaruhi menyumbang.

        > [!div class="mx-imgBorder"]
        > ![Faktor pengesyoran utama.](media/product-recommendation-keyrecommendationfactors.png "Faktor pengesyoran utama yang dipelajari oleh model untuk menjana pengesyoran produk")
       
     
   1. **Statistik data**: Memberikan gambaran keseluruhan untuk bilangan transaksi, pelanggan, dan produk model yang dipertimbangkan. Ia berdasarkan data input yang digunakan untuk mempelajari corak dan menjana pengesyoran produk.

      > [!div class="mx-imgBorder"]
      > ![Statistik data.](media/product-recommendation-datastatistics.png "Statistik data di sekeliling data masuk yang digunakan oleh model untuk mempelajari corak")

      Bahagian ini menunjukkan statistik di sekitar titik data yang digunakan oleh model untuk mempelajari corak dan menjana pengesyoran produk. Penapisan, seperti yang dikonfigurasikan dalam konfigurasi model, akan digunakan pada output yang dihasilkan oleh model. Walau bagaimanapun, model ini menggunakan semua data yang tersedia untuk mempelajari corak. Oleh itu, jika anda menggunakan penapisan produk dalam konfigurasi model, bahagian ini akan menunjukkan jumlah produk yang dianalisis model untuk mempelajari corak, yang mungkin berbeza daripada bilangan produk yang sepadan dengan kriteria penapisan yang ditakrifkan.

   1. **Pengesyoran produk keyakinan tinggi:** Sampel pengesyoran yang diberikan kepada pelanggan anda bahawa model ini percaya mungkin akan dibeli oleh pelanggan.    
      Jika katalog produk ditambah, ID produk akan digantikan dengan nama produk. Nama produk memberikan maklumat yang lebih boleh diambil tindakan dan intuitif mengenai ramalan.
       > [!div class="mx-imgBorder"]
       > ![Senarai menunjukkan cadangan keyakinan tinggi untuk set pelanggan individu yang terpilih.](media/product-recommendation-highconfidence.PNG "Senarai menunjukkan cadangan keyakinan tinggi untuk set pelanggan individu yang terpilih")

## <a name="manage-predictions"></a>Urus ramalan

Ada kemungkinan untuk mengoptimumkan, menyelesaikan masalah, menyegarkan semula atau memadam ramalan. Semak laporan kebolehgunaan data input untuk mengetahui cara membuat ramalan lebih cepat dan lebih dipercayai. Untuk mendapatkan maklumat lanjut, lihat [Urus ramalan](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
