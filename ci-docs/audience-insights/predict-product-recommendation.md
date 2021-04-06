---
title: Ramalan pengesyoran produk
description: Meramalkan produk yang pelanggan mungkin akan beli atau berinteraksi dengannya.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598074"
---
# <a name="product-recommendation-prediction-preview"></a>Ramalan pengesyoran produk (pratonton)

Model pengesyoran produk mencipta set pengesyoran produk ramalan. Pengesyoran adalah berdasarkan tingkah laku pembelian sebelumnya dan pelanggan dengan corak pembelian yang sama. Anda boleh mencipta ramalan pengesyoran produk baru pada halaman **Kecerdasan** > **Ramalan**. Pilih **Ramalan saya** untuk melihat ramalan lain yang telah anda cipta.

Pengesyoran produk mungkin tertakluk kepada undang-undang dan peraturan tempatan serta jangkaan pelanggan, yang model tidak dibina untuk mengambil kira secara khusus.  Sebagai pengguna keupayaan ramalan ini, **anda mesti menyemak pengesyoran sebelum menyampaikannya kepada pelanggan anda** untuk memastikan bahawa anda mematuhi mana-mana undang-undang atau peraturan yang berkenaan, serta jangkaan pelanggan untuk apa yang anda mungkin cadangkan. 

Di samping itu, output model ini akan memberi anda pengesyoran berdasarkan ID produk. Mekanisme penghantaran anda perlu mengambil ID produk yang diramalkan dan memetakannya kepada kandungan yang sesuai untuk pelanggan anda untuk mengambil kira penyetemtemasan, kandungan imej dan kandungan atau tingkah laku khusus perniagaan lain.

## <a name="sample-guide"></a>Panduan Sampel

Jika anda berminat untuk mencuba ciri ini tetapi tidak mempunyai data untuk melengkapkan keperluan di bawah, anda boleh [membuat pelaksanaan sampel](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.
- Pengetahuan perniagaan untuk memahami jenis produk berbeza untuk perniagaan anda dan cara pelanggan anda berinteraksi dengan mereka. Kami menyokong mengesyorkan produk yang telah dibeli sebelum oleh pelanggan anda atau pengesyoran untuk produk baru.
- Data tentang transaksi, pembelian dan sejarah mereka:
    - Pengecam transaksi untuk membezakan pembelian atau transaksi.
    - Pengecam pelanggan untuk memetakan transaksi kepada pelanggan anda.
    - Tarikh peristiwa transaksi yang menentukan tarikh transaksi berlaku.
    - (Pilihan) Maklumat ID produk untuk transaksi.
    - (Pilihan) Jika transaksi adalah pulangan atau tidak.
    - Skema data semantik memerlukan maklumat berikut:
        - **ID transaksi:** Pengecam unik bagi pembelian atau transaksi.
        - **Tarikh transaksi:** Tarikh pembelian atau transaksi.
        - **Nilai transaksi:** Jumlah nilai berangka bagi pembelian atau transaksi.
        - **ID produk unik:** ID produk atau perkhidmatan yang dibeli jika data anda berada pada peringkat baris item.
        - (Pilihan) **Pembelian atau pulangan:** Medan benar/palsu yang mengenal pasti sama ada transaksi tersebut adalah pulangan atau tidak. Jika **Nilai transaksi** adalah negatif, kami juga akan menggunakan maklumat ini untuk simpulkan pulangan.


## <a name="create-a-product-recommendation-prediction"></a>Cipta ramalan pengesyoran produk

1. Dalam Customer Insights, pergi ke **Kepintaran** > **Ramalan**.

1. Pilih jubin **Model pengesyoran produk (pratonton)** dan pilih **Gunakan model ini**.
   > [!div class="mx-imgBorder"]
   > ![Jubin model Pengesyoran Produk dengan butang Gunakan model ini](media/product-recommendation-usethismodel.PNG "Jubin model Pengesyoran Produk dengan butang Gunakan model ini")

1. Semak maklumat tentang keperluan model. Jika anda mempunyai data yang diperlukan, pilih **Bermula**.

### <a name="name-model"></a>Model nama

1. Berikan nama untuk model bagi membezakannya daripada model lain.

1. Masukkan nama untuk entiti output menggunakan huruf dan nombor sahaja, tanpa sebarang ruang. Itulah nama yang entiti model akan gunakan. Kemudian pilih **Seterusnya**.

### <a name="define-product-recommendation-configuration"></a>Tentukan konfigurasi pengesyoran produk

1. Tetapkan **Bilangan produk** yang anda ingin cadangkan kepada pelanggan. Nilai ini bergantung kepada cara kaedah penghantaran anda mengisi data. Jika anda boleh mengesyorkan tiga produk, tetapkan nilai ini dengan sewajarnya.
   
   >[!TIP]
   > Anda boleh memilih **Simpan dan tutup** pada bila-bila masa untuk menyimpan ramalan sebagai draf. Anda akan menemui draf ramalan dalam tab **Ramalan saya**.

1. Pilih jika anda ingin **Cadangkan produk yang telah dibeli oleh pelanggan baru-baru ini**.

1. Jika anda telah memilih untuk *tidak* mengesyorkan produk yang dibeli baru-baru ini, tetapkan **Tetingkap lihat kembali**. Tetapan ini menentukan tempoh masa model mempertimbangkan sebelum mengesyorkan produk kepada pengguna semula. Sebagai contoh, nyatakan pelanggan membeli komputer riba setiap 2 tahun. Tetingkap ini akan melihat sejarah pembelian sejak 2 tahun yang lalu, dan jika mereka menemui item, item akan ditapis daripada pengesyoran.

1. Pilih **Seterusnya**

### <a name="add-required-data"></a>Tambah data yang diperlukan

1. Pilih **Tambah data** untuk **Sejarah transaksi pelanggan** dan pilih entiti yang menyediakan maklumat sejarah transaksi/pembelian seperti yang diterangkan dalam [prasyarat](#prerequisites).

1. Petakan medan semantik kepada atribut dalam entiti sejarah pembelian anda dan pilih **Seterusnya**. Untuk perihalan medan, lihatlah [prasyarat](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Takrifkan perhubungan entiti](media/product-recommendation-purchasehistorymapping.PNG "Halaman sejarah pembelian menunjukkan atribut semantik yang dipetakan ke medan dalam entiti sejarah pembelian terpilih")

1. Jika medan tidak diisi, konfigurasikan hubungan daripada entiti sejarah pembelian anda kepada entiti *Pelanggan*.
    1. Pilih **Entiti sejarah pembelian**.
    1. Pilih **Medan** yang mengenal pasti pelanggan dalam entiti sejarah pembelian. Ia perlu dikaitkan kepada ID pelanggan utama bagi entiti *Pelanggan* anda.
    1. Pilih **Entiti pelanggan** yang memadankan entiti pelanggan utama anda.
    1. Masukkan nama yang menghuraikan perhubungan.
       > [!div class="mx-imgBorder"]
       > ![Halaman sejarah pembelian menunjukkan penciptaan hubungan kepada pelanggan](media/model-purchase-join.png "Halaman sejarah pembelian menunjukkan penciptaan hubungan kepada pelanggan")

1. Pilih **Simpan**.

1. Pilih **Seterusnya**.

### <a name="set-schedule-and-review-configuration"></a>Tetapkan jadual dan konfigurasi ulasan

1. Tetapkan kekerapan untuk melatih semula model anda. Tetapan ini penting untuk mengemas kini ketepatan ramalan ketika data baharu diimport ke dalam Customer Insights. Kebanyakan perniagaan boleh melatih semula sekali setiap bulan dan mendapatkan ketepatan yang baik untuk ramalan mereka.

1. Pilih **Seterusnya**.

1. Semak semula konfigurasi. Anda boleh kembali ke mana-mana bahagian konfigurasi ramalan dengan memilih **Edit** di bawah nilai yang ditunjukkan. Atau anda boleh memilih langkah konfigurasi daripada penunjuk kemajuan.

1. Jika semua nilai dikonfigurasikan dengan betul, pilih **Simpan dan jalankan** untuk memulakan proses ramalan. Pada tab **Langganan saya**, anda boleh melihat status ramalan anda. Proses mungkin mengambil masa beberapa jam untuk dilengkapkan bergantung kepada amaun data yang digunakan dalam ramalan.

## <a name="review-a-prediction-status-and-results"></a>Semak semula status dan hasil ramalan

1. Pergi ke tab **Ramalan saya** pada **Kecerdasan** > **Ramalan**.
   > [!div class="mx-imgBorder"]
   > ![Pandangan halaman Ramalan Saya](media/product-recommendation-mypredictions.PNG "Pandangan halaman Ramalan Saya")

1. Pilih ramalan yang anda mahu semak semula.
   - **Nama ramalan:** Nama ramalan yang disediakan apabila menciptanya.
   - **Jenis ramalan:** Jenis model yang digunakan untuk ramalan
   - **Entiti output:** Nama entiti untuk menyimpan output ramalan. Anda boleh menemui entiti dengan nama ini pada **Data** > **Entiti**.
   - **Medan ramalan:** Medan ini diisikan hanya untuk beberapa jenis ramalan, dan tidak digunakan dalam ramalan pulangan.
   - **Status:** Status semasa jalanan ramalan.
        - **Dibaris gilir:** Ramalan pada masa ini menunggu proses lain untuk berjalan.
        - **Menyegar semula:** Ramalan pada masa ini menjalankan peringkat pemprosesan "skor" untuk menghasilkan hasil yang akan mengalir ke dalam entiti output.
        - **Gagal:** ramalan telah gagal. Pilih **Log** untuk butiran lanjut.
        - **Berjaya:** ramalan telah berjaya. Pilih **Pandangan** di bawah elipsis menegak untuk menyemak semula langganan
   - **Diedit:** Tarikh konfigurasi untuk ramalan telah diubah.
   - **Terakhir disegar semula:** Tarikh ramalan menyegar semula hasil dalam entiti output.

1. Pilih elipsis menegak di sebelah ramalan yang anda mahu semak semula hasilnya dan pilih **Pandangan**.
   > [!div class="mx-imgBorder"]
   > ![Pandangan pilihan dalam elipsis menegak untuk ramalan termasuk edit, segar semula, pandangan, log dan padam](media/product-recommendation-verticalellipses.PNG "Pandangan pilihan dalam elipsis menegak untuk ramalan termasuk edit, segar semula, pandangan, log dan padam")

1. Terdapat tiga bahagian utama data dalam halaman hasil:
    1. **Melatih prestasi model:** A, B atau C ialah skor yang mungkin. Skor ini menunjukkan prestasi ramalan dan boleh membantu anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entiti output.
        - Skor ditentukan berdasarkan peraturan yang berikut:
            - **A** Model ini akan dianggap kualiti **A** jika metrik "Kejayaan @ K" adalah sekurang-kurangnya 10% lebih garis dasar. 
            - **B** Model ini akan dianggap kualiti **B** jika metrik "Kejayaan @ K" adalah 0 hingga 10% lebih daripada garis dasar.
            - **C** Model ini akan dianggap kualiti **C** jika metrik "Kejayaan @ K" adalah kurang daripada garis dasar.
               
               > [!div class="mx-imgBorder"]
               > ![Pandangan hasil prestasi model](media/product-recommendation-modelperformance.PNG "Pandangan hasil prestasi model")
            - **Garis dasar**: Model ini mengambil produk yang paling disyorkan oleh kiraan pembelian merentasi semua pelanggan, dan menggunakan peraturan yang dipelajari yang dikenal pasti oleh model untuk mencipta satu set pengesyoran untuk pelanggan. Ramalan kemudiannya dibandingkan dengan produk teratas, seperti yang dikira oleh bilangan pelanggan yang telah membeli produk tersebut. Jika pelanggan mempunyai sekurang-kurangnya satu produk dalam produk yang disyorkan yang juga dilihat dalam produk yang dibeli teratas, mereka dianggap sebagai sebahagian daripada garis dasar. Jika terdapat 10 pelanggan ini yang mempunyai produk yang disyorkan yang dibeli daripada 100 jumlah pelanggan, garis dasar akan menjadi 10%.
            - **Kejayaan @ K**: Menggunakan satu set pengesahan tempoh masa transaksi, pengesyoran dicipta untuk semua pelanggan dan dibandingkan dengan set pengesahan transaksi. Sebagai contoh, dalam tempoh 12 bulan, bulan 12 mungkin diketepikan sebagai set pengesahan data. Jika model meramalkan sekurang-kurangnya satu perkara yang anda akan membeli dalam bulan 12 berdasarkan apa yang dipelajari daripada 11 bulan sebelumnya, pelanggan akan meningkatkan metrik "Kejayaan @ K".
    
    1. **Produk yang paling dicadangkan (dengan penghitungan):** 5 produk teratas yang diramalkan untuk pelanggan anda.
       > [!div class="mx-imgBorder"]
       > ![Graf menunjukkan 5 produk teratas yang paling disyorkan](media/product-recommendation-topproducts.PNG "Graf menunjukkan 5 produk teratas yang paling disyorkan")
    
    1. **Pengesyoran produk keyakinan tinggi:** Sampel pengesyoran yang diberikan kepada pelanggan anda bahawa model ini percaya mungkin akan dibeli oleh pelanggan.
       > [!div class="mx-imgBorder"]
       > ![Senarai menunjukkan cadangan keyakinan tinggi untuk set pelanggan individu yang terpilih](media/product-recommendation-highconfidence.PNG "Senarai menunjukkan cadangan keyakinan tinggi untuk set pelanggan individu yang terpilih")

## <a name="fix-a-failed-prediction"></a>Betulkan ramalan yang gagal

1. Pergi ke tab **Ramalan saya** pada **Kecerdasan** > **Ramalan**.

1. Pilih ramalan yang anda ingin lihat log ralatnya dan pilih **Log**.

1. Semak semula semua ralat. Terdapat beberapa jenis ralat yang boleh berlaku dan ia menghuraikan keadaan yang menyebabkan ralat tersebut. Contohnya, ralat bahawa data tidak mencukupi untuk meramal secara tepat pada lazimnya diselesaikan dengan memuatkan data tambahan ke dalam Customer Insights.

## <a name="refresh-a-prediction"></a>Segar semula ramalan

Ramalan menyegar semula secara automatik pada jadual yang sama [jadualkan segar semula data anda](system.md#schedule-tab) seperti yang dikonfigurasikan dalam tetapan.

1. Pergi ke tab **Ramalan saya** pada **Kecerdasan** > **Ramalan**.

1. Pilih elipsis menegak di sebelah ramalan yang anda mahu segar semula.

1. Pilih **Segar Semula**.

## <a name="delete-a-prediction"></a>Padamkan ramalan

Memadam ramalan juga akan mengalih keluar entiti outputnya.

1. Pergi ke tab **Ramalan saya** pada **Kecerdasan** > **Ramalan**.

1. Pilih elipsis menegak di sebelah ramalan yang anda mahu padamkan.

1. Pilih **Padam**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]