---
title: Ramalan pulangan transaksi
description: Ramalkan sama ada pelanggan mempunyai risiko kerana tidak lagi membeli produk atau perkhidmatan anda.
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af461d290c69687fb47bacfcff446a0c62978383
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268329"
---
# <a name="transactional-churn-prediction-preview"></a>Ramalan pulangan transaksi (pratonton)

Ramalan pulangan transaksi membantu meramal jika pelanggan tidak lagi akan membeli produk atau perkhidmatan anda dalam tetingkap masa tertentu. Anda boleh mencipta ramalan pulangan baharu pada **Kecerdasan** > **Ramalan**. Pilih **Ramalan saya** untuk melihat ramalan lain yang telah anda cipta.

> [!TIP]
> Cuba tutorial untuk ramalan pulangan transaksi menggunakan data sampel: [Panduan sampel (pratonton) ramalan pulangan transaksi](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.
- Pengetahuan perniagaan untuk memahami makna pulangan untuk perniagaan anda. Kami menyokong definisi pulangan berasaskan masa yang bermaksud pelanggan dianggap sebagai telah mendapat pulangan selepas tempoh tiada pembelian.
- Data mengenai transaksi/pembelian anda dan sejarah mereka:
    - Pengecam transaksi untuk membezakan pembelian/transaksi.
    - Pengecam pelanggan untuk memadankan transaksi kepada pelanggan anda.
    - Tarikh peristiwa transaksi, yang mentakrifkan tarikh transaksi berlaku.
    - Skema data semantik untuk pembelian/transaksi memerlukan maklumat berikut:
        - **ID transaksi:** Pengecam unik bagi pembelian atau transaksi.
        - **Tarikh Transaksi:** Tarikh pembelian atau transaksi.
        - **Nilai transaksi:** Jumlah mata wang/nilai berangka bagi transaksi/item.
        - (Pilihan) **ID produk unik:** ID produk atau perkhidmatan yang dibeli jika data anda berada pada peringkat baris item.
        - (Pilihan) **Sama ada transaksi ini adalah pulangan:** Medan benar/palsu yang mengenal pasti sama ada transaksi tersebut adalah pulangan atau tidak. Jika **Nilai transaksi** adalah negatif, kami juga akan menggunakan maklumat ini untuk simpulkan pulangan.
- (Pilihan) Data mengenai aktiviti pelanggan:
    - Pengecam aktiviti untuk membezakan aktiviti jenis yang sama.
    - Pengecam pelanggan untuk memetakan aktiviti kepada pelanggan anda.
    - Maklumat aktiviti yang mengandungi nama dan tarikh aktiviti.
    - Skema data semantik untuk aktiviti pelanggan termasuk:
        - **Kunci utama:** Pengecam unik untuk aktiviti. Contohnya, lawatan laman web atau rekod penggunaan yang menunjukkan pelanggan telah mencuba sampel produk anda.
        - **Cap masa:** Tarikh dan masa peristiwa dikenal pasti oleh kunci utama.
        - **Peristiwa:** Nama peristiwa yang anda mahu gunakan. Contohnya, medan yang dipanggil "UserAction" di dalam stor runcit mungkin kupon yang digunakan oleh pelanggan.
        - **Butiran:** Maklumat terperinci tentang peristiwa. Contohnya, medan yang dipanggil "CouponValue" dalam stor runcit mungkin nilai mata wang kupon tersebut.

## <a name="create-a-transactional-churn-prediction"></a>Cipta ramalan pulangan transaksi

1. Dalam Customer Insights, pergi ke **Kepintaran** > **Ramalan**.

1. Pilih jubin **Model pulangan pelanggan (pratonton)** dan pilih **Gunakan model ini**.
   
1. Dalam anak tetingkap **Model pulangan pelanggan**, pilih **Transaksi** dan pilih **Mari Bermula**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Syot layar dengan pilihan transaksi yang dipilih dalam anak tetingkap model Pulangan pelanggan.":::

### <a name="name-model"></a>Model nama

1. Berikan nama untuk model bagi membezakannya daripada model lain.

1. Berikan nama untuk entiti output menggunakan huruf dan nombor sahaja, tanpa sebarang ruang. Itulah nama yang entiti model akan gunakan. 

1. Pilih **Seterusnya**.

### <a name="define-customer-churn"></a>Takrifkan pulangan pelanggan

1. Tetapkan tetingkap hari untuk meramalkan pulangan bagi **Mengenal pasti pelanggan yang boleh memberikan pulangan dalam medan** seterusnya. Sebagai contoh, ramalkan risiko pulangan untuk pelanggan anda sepanjang 90 hari yang akan datang untuk menyelaraskan usaha pengekalan pemasaran anda. Meramalkan risiko pulangan untuk tempoh masa yang lebih panjang atau lebih pendek boleh menjadikan lebih sukar untuk menangani faktor dalam profil risiko pulangan anda, tetapi ia bergantung kepada keperluan perniagaan khusus anda. 
   >[!TIP]
   > Anda boleh memilih **Simpan dan tutup** pada bila-bila masa untuk menyimpan ramalan sebagai draf. Anda akan menemui ramalan draf dalam tab **Ramalan saya** untuk meneruskan.

1. Masukkan bilangan hari untuk mentakrifkan pulangan dalam **Pelanggan telah mendapat pulangan jika mereka tidak membuat pembelian dalam:** medan. Sebagai contoh, jika pelanggan tidak membuat pembelian dalam tempoh 30 hari yang lalu, mereka mungkin dianggap sebagai telah memberikan pulangan untuk perniagaan anda. 

1. Pilih **Seterusnya** untuk teruskan

### <a name="add-required-data"></a>Tambah data yang diperlukan

1. Pilih **Tambah data** untuk **Sejarah pembelian** dan pilih entiti yang menyediakan maklumat sejarah transaksi/pembelian seperti yang diterangkan dalam [prasyarat](#prerequisites).

1. Petakan medan semantik kepada atribut dalam entiti sejarah pembelian anda dan pilih **Seterusnya**. Untuk perihalan medan, lihatlah [prasyarat](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Petakan medan semantik entiti pembelian.":::

1. Jika medan di bawah tidak diisi, konfigurasikan hubungan daripada entiti sejarah pembelian anda kepada entiti pelanggan.
    1. Pilih **Entiti sejarah pembelian**.
    1. Pilih **Medan** yang mengenal pasti pelanggan dalam entiti sejarah pembelian. Ia perlu dikaitkan kepada ID pelanggan utama bagi entiti Pelanggan anda.
    1. Pilih **Entiti pelanggan** yang memadankan entiti pelanggan utama anda.
    1. Masukkan nama yang menghuraikan perhubungan.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Halaman sejarah pembelian menunjukkan penciptaan hubungan kepada pelanggan.":::
   
1. Pilih **Seterusnya**.

1. Secara alternatif, pilih **Tambah data** untuk **Aktiviti pelanggan**. Pilih entiti yang menyediakan maklumat aktiviti pelanggan seperti yang diterangkan dalam prasyarat.

1. Petakan medan semantik kepada atribut dalam entiti aktiviti pelanggan anda dan pilih **Seterusnya**. Untuk perihalan medan, lihatlah [prasyarat](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Petakan medan pelanggan untuk data transaksi.":::

1. Pilih jenis aktiviti yang sepadan dengan jenis aktiviti pelanggan yang anda konfigurasikan. Pilih **Cipta baharu** dan pilih jenis aktiviti tersedia atau cipta jenis baharu.

1. Anda perlu mengkonfigurasikan perhubungan daripada entiti aktiviti pelanggan anda kepada entiti Pelanggan.
    1. Pilih medan yang mengenal pasti pelanggan dalam jadual aktiviti pelanggan. Ia boleh berkait secara langsung dengan ID pelanggan utama entiti pelanggan anda.
    1. Pilih entiti Pelanggan yang memadankan entiti Pelanggan utama anda
    1. Masukkan nama yang menghuraikan perhubungan.

1. Pilih **Simpan**.

1. Jika anda mempunyai sebarang aktiviti pelanggan lain yang anda mahu sertakan, ulangi langkah di atas.

1. Pilih **Seterusnya**.

### <a name="set-schedule-and-review-configuration"></a>Tetapkan jadual dan konfigurasi ulasan

1. Tetapkan kekerapan untuk melatih semula model anda. Tetapan ini adalah penting untuk mengemas kini ketepatan ramalan kerana data baru telah dimasukkan. Kebanyakan perniagaan boleh melatih semula sekali setiap bulan dan mendapatkan ketepatan yang baik untuk ramalan mereka.

1. Pilih **Seterusnya**.

1. Semak semula konfigurasi ramalan. Anda boleh kembali ke langkah awal dengan memilih **Edit** di bawah nilai yang ditunjukkan. Atau anda boleh memilih langkah konfigurasi daripada penunjuk kemajuan.

1. Jika semua nilai dikonfigurasikan dengan betul, pilih **Simpan dan jalankan** untuk memulakan proses ramalan. Pada tab **Langganan saya**, anda boleh melihat status ramalan anda. Proses mungkin mengambil masa beberapa jam untuk dilengkapkan bergantung kepada amaun data yang digunakan dalam ramalan.

## <a name="review-a-prediction-status-and-results"></a>Semak semula status dan hasil ramalan

1. Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.

1. Pilih ramalan yang anda mahu semak semula.
   - **Nama ramalan:** Nama ramalan yang diberikan apabila menciptanya.
   - **Jenis ramalan:** Jenis model yang digunakan untuk ramalan
   - **Entiti output:** Nama entiti untuk menyimpan output ramalan. Anda boleh menemui entiti dengan nama ini pada **Data** > **Entiti**.
   - **Medan ramalan:** Medan ini diisikan hanya untuk beberapa jenis ramalan, dan tidak digunakan dalam ramalan pulangan.
   - **Status:** Status jalanan ramalan.
        - **Dibariskan:** Ramalan sedang menunggu proses lain untuk berjalan.
        - **Menyegarkan semula**: Ramalan sedang berjalan untuk menghasilkan keputusan yang akan mengalir ke dalam entiti output.
        - **Gagal:** Jalanan ramalan gagal. [Ulasan log](#troubleshoot-a-failed-prediction) untuk maklumat lanjut.
        - **Berjaya:** Ramalan telah berjaya. Pilih **Pandangan** di bawah elipsis menegak untuk menyemak semula langganan
   - **Diedit:** Tarikh konfigurasi untuk ramalan telah diubah.
   - **Terakhir disegar semula:** Tarikh ramalan menyegar semula hasil dalam entiti output.

1. Pilih elipsis menegak di sebelah ramalan yang anda mahu semak semula hasilnya dan pilih **Pandangan**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Lihat kawalan untuk melihat keputusan ramalan.":::   

1. Terdapat tiga bahagian utama data dalam halaman hasil:
    1. **Melatih prestasi model:** A, B atau C ialah skor yang mungkin. Skor ini menunjukkan prestasi ramalan dan boleh membantu anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entiti output. Skor ditentukan berdasarkan peraturan yang berikut:
         
         - **A** apabila model meramalkan dengan tepat sekurang-kurangnya 50% daripada jumlah ramalan dan apabila peratusan ramalan yang tepat untuk pelanggan yang telah memberikan pulangan adalah lebih besar daripada kadar garis dasar sekurang-kurangnya 10%.
            
         - **B** apabila model meramalkan dengan tepat sekurang-kurangnya 50% daripada jumlah ramalan dan apabila peratusan ramalan yang tepat untuk pelanggan yang telah memberikan pulangan adalah sehingga 10% lebih besar daripada garis dasar.
            
         - **C** apabila model meramalkan dengan tepat kurang 50% daripada jumlah ramalan atau apabila peratusan ramalan yang tepat untuk pelanggan yang telah memberikan pulangan adalah kurang daripada garis dasar.
               
         - **Garis dasar** mengambil input tetingkap masa ramalan untuk model (contohnya, satu tahun) dan model mencipta bahagian masa yang berbeza dengan membahagikannya kepada 2 sehingga ia mencapai satu bulan atau kurang. Ia menggunakan bahagian ini untuk mewujudkan satu peraturan perniagaan bagi pelanggan yang belum membeli dalam tempoh masa ini. Pelanggan ini dianggap sebagai yang memberi pulangan. Peraturan perniagaan berasaskan masa dengan keupayaan tertinggi untuk meramalkan siapa yang mungkin memberikan pulangan dipilih sebagai model garis dasar.
            
    1. **Kemungkinan untuk pulangan (bilangan pelanggan):** Kumpulan pelanggan berdasarkan risiko pulangan mereka yang diramalkan. Data ini boleh membantu anda kemudian jika anda mahu mencipta segmen pelanggan dengan risiko pulangan yang tinggi. Segmen seperti ini dapat membantu memahami tempat penggalan anda yang sepatutnya bagi keahlian segmen.
       
    1. **Faktor paling mempengaruhi:** Terdapat banyak faktor yang diambil kira apabila mencipta ramalan anda. Setiap faktor mempunyai kepentingannya yang dikira untuk ramalan teragregat yang dicipta oleh model. Anda boleh menggunakan faktor ini untuk membantu mengesahkan hasil ramalan anda. Atau anda boleh menggunakan maklumat ini kemudian untuk [mencipta segmen](segments.md) yang dapat membantu mempengaruhi risiko pulangan untuk pelanggan.

## <a name="troubleshoot-a-failed-prediction"></a>Selesaikan ramalan yang gagal

1. Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.

1. Pilih elipsis menegak bersebelahan dengan ramalan yang anda mahu lihat log ralatnya.

1. Pilih **Log**.

1. Semak semula semua ralat. Terdapat beberapa jenis ralat yang boleh berlaku dan ia menghuraikan keadaan yang menyebabkan ralat tersebut. Contohnya, ralat bahawa data tidak mencukupi untuk meramal secara tepat pada lazimnya diselesaikan dengan memuatkan data tambahan ke dalam Customer Insights.

## <a name="refresh-a-prediction"></a>Segar semula ramalan

Ramalan akan menyegar semula secara automatik pada [jadual yang sama data anda menyegar semula](system.md#schedule-tab) seperti yang dikonfigurasikan dalam tetapan. Anda boleh juga menyegarkannya semula secara manual.

1. Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.

1. Pilih elipsis menegak di sebelah ramalan yang anda mahu segar semula.

1. Pilih **Segar Semula**.

## <a name="delete-a-prediction"></a>Padamkan ramalan

Memadamkan ramalan juga mengalih keluar entiti outputnya.

1. Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.

1. Pilih elipsis menegak di sebelah ramalan yang anda mahu padamkan.

1. Pilih **Padam**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]