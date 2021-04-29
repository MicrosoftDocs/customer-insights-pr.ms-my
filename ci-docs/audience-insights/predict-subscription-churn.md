---
title: Ramalan pulangan langganan
description: Meramal sama ada pelanggan berada dalam risiko kerana tidak lagi menggunakan produk atau perkhidmatan langganan syarikat anda.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b6bf4f715768b18d69be3bea4085acd96933e8da
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906913"
---
# <a name="subscription-churn-prediction-preview"></a>Ramalan pulangan langganan (pratonton)

Ramalan pulangan langganan membantu meramal sama ada pelanggan berada dalam risiko kerana tidak lagi menggunakan produk atau perkhidmatan langganan syarikat anda. Anda boleh mencipta ramalan pulangan langganan baharu di halaman **Kecerdasan** > **Ramalan**. Pilih **Ramalan saya** untuk melihat ramalan lain yang telah anda cipta.

> [!TIP]
> Cuba tutorial untuk ramalan pulangan langganan menggunakan data sampel: [Panduan sampel ramalan pulangan langganan](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md).
- Pengetahuan perniagaan untuk memahami makna pulangan untuk perniagaan anda. Kami menyokong takrifan pulangan berasaskan masa, bermakna pelanggan dipertimbangkan untuk mempunyai pulangan tempoh masa selepas langganan mereka berakhir.
- Data tentang langganan anda dan sejarahnya:
    - Pengecam langganan untuk membezakan langganan.
    - Pengecam pelanggan untuk memadankan langganan kepada pelanggan anda.
    - Tarikh peristiwa langganan, yang mentakrifkan tarikh mula, tarikh tamat dan tarikh peristiwa langganan berlaku.
    - Maklumat langganan untuk ditakrifkan jika ia langganan berulang dan kekerapan pembaharuannya.
    - Skema data semantik untuk langganan memerlukan maklumat yang berikut:
        - **ID Langganan:** Pengecam unik langganan.
        - **Tarikh Tamat Langganan:** Tarikh tamat tempoh langganan untuk pelanggan.
        - **Tarikh Mula Langganan:** Tarikh mula langganan untuk pelanggan.
        - **Tarikh Transaksi:** Tarikh perubahan langganan berlaku. Contohnya, pelanggan membeli atau membatalkan langganan.
        - **Adakah ia langganan berulang:** Medan benar/palsu boolean yang menentukan sama ada langganan akan diperbaharui dengan ID langganan yang sama tanpa campur tangan pelanggan
        - **Kekerapan pengulangan (dalam bulan):** Untuk langganan berulang, ia merupakan tempoh langganan akan diperbaharui. Ia diwakili dalam bulan. Contohnya, langganan tahunan yang diperbaharui secara automatik untuk pelanggan setiap tahun untuk setahun lagi mempunyai nilai 12.
        - (Pilihan) **Amaun Langganan:** Amaun mata wang yang pelanggan bayar untuk pembaharuan langganan. Ia boleh membantu mengenal pasti corak untuk tahap langganan yang berbeza.
- Data tentang aktiviti pelanggan:
    - Pengecam aktiviti untuk membezakan aktiviti jenis yang sama.
    - Pengecam pelanggan untuk memetakan aktiviti kepada pelanggan anda.
    - Maklumat aktiviti yang mengandungi nama dan tarikh aktiviti.
    - Skema data semantik untuk aktiviti pelanggan termasuk:
        - **Kunci utama:** Pengecam unik untuk aktiviti. Contohnya, lawatan tapak web atau rekod penggunaan yang menunjukkan episod rancangan TV dilihat oleh pelanggan.
        - **Cap masa:** Tarikh dan masa peristiwa dikenal pasti oleh kunci utama.
        - **Peristiwa:** Nama peristiwa yang anda mahu gunakan. Contohnya, medan yang dipanggil "UserAction" dalam perkhidmatan penstriman video boleh mempunyai nilai "Dilihat".
        - **Butiran:** Maklumat terperinci tentang peristiwa. Contohnya, medan yang dipanggil "ShowTitle" dalam perkhidmatan penstriman video boleh mempunyai nilai video yang ditonton pelanggan.
- Ciri data yang disyorkan:
    - Data sejarah yang mencukupi: Data langganan sekurang-kurangnya dua kali ganda tetingkap masa yang dipilih. Sebaik-baiknya, dua hingga tiga tahun data langganan.
    - Status langganan: Data termasuk langganan aktif dan tidak aktif untuk setiap pelanggan supaya terdapat beberapa entri bagi setiap ID pelanggan.
    - Bilangan pelanggan: Sekurang-kurangnya 10 profil pelanggan, sebaik-baiknya lebih daripada 1,000 pelanggan unik. Model ini akan gagal dengan kurang daripada 10 pelanggan dan data sejarah yang tidak mencukupi.
    - Kesempurnaan data: Kurang daripada 20% daripada nilai yang hilang dalam medan data entiti yang disediakan.
   
   > [!NOTE]
   > Pengiraan pengeluaran yang anda mahu kira memerlukan sekurang-kurangnya dua rekod aktiviti untuk 50% daripada pelanggan.

## <a name="create-a-subscription-churn-prediction"></a>Cipta ramalan pulangan langganan

1. Dalam wawasan khalayak, pergi ke **Kecerdasan** > **Ramalan**.
1. Pilih jubin **Model pulangan langganan (pratonton)** dan pilih **Gunakan model ini**.
   > [!div class="mx-imgBorder"]
   > ![Jubin model Pulangan Langganan dengan butang Gunakan model ini](media/subscription-churn-usethismodel.PNG "Jubin model Pulangan Langganan dengan butang Gunakan model ini")

### <a name="name-model"></a>Namakan model

1. Berikan nama untuk model bagi membezakannya daripada model lain.
1. Berikan nama untuk entiti output menggunakan huruf dan nombor sahaja, tanpa sebarang ruang. Itulah nama yang entiti model akan gunakan. Kemudian pilih **Seterusnya**.

### <a name="define-customer-churn"></a>Takrifkan pulangan pelanggan

1. Masukkan bilangan **Hari sejak langganan berakhir** yang perniagaan anda pertimbangkan pelanggan akan berada dalam keadaan mempunyai pulangan. Tempoh ini pada lazimnya disukai untuk aktiviti perniagaan seperti tawaran atau usaha pemasaran lain yang cuba mengelakkan kerugian pelanggan.
1. Masukkan bilangan **Hari yang dijangkakan untuk meramalkan pengeluaran** bagi menetapkan tetingkap untuk ramalan pengeluarannya. Contohnya, untuk meramal risiko pengeluaran untuk pelanggan anda dalam tempoh 90 hari yang akan datang bagi menyelaraskan usaha pengekalan pemasaran anda. Meramalkan risiko pulangan untuk tempoh masa yang lebih lama atau lebih singkat boleh menjadikannya lebih sukar untuk menangani faktor-faktor dalam profil risiko pulangan, bergantung kepada keperluan perniagaan khusus anda. Pilih **Seterusnya** untuk teruskan
   >[!TIP]
   > Anda boleh memilih **Simpan dan tutup** pada bila-bila masa untuk menyimpan ramalan sebagai draf. Anda akan menemui ramalan draf dalam tab **Ramalan saya** untuk meneruskan.

### <a name="add-required-data"></a>Tambah data yang diperlukan

1. Pilih **Tambahkan data** untuk **Sejarah langganan** dan pilih entiti yang menyediakan maklumat sejarah langganan seperti yang dihuraikan dalam [prasyarat](#prerequisites).
1. Jika medan di bawah tidak berisi, konfigurasikan perhubungan daripada entiti sejarah langganan untuk entiti Pelanggan.
    1. Pilih **Entiti sejarah langganan**.
    1. Pilih **Medan** yang mengenal pasti pelanggan dalam entiti sejarah langganan. Ia perlu dikaitkan kepada ID pelanggan utama bagi entiti Pelanggan anda.
    1. Pilih **Entiti pelanggan** yang memadankan entiti pelanggan utama anda.
    1. Masukkan nama yang menghuraikan perhubungan.
       > [!div class="mx-imgBorder"]
       > ![Halaman sejarah langganan yang menunjukkan penciptaan perhubungan dengan pelanggan](media/subscription-churn-subscriptionhistoryrelationship.PNG "Halaman sejarah langganan yang menunjukkan penciptaan perhubungan dengan pelanggan")
1. Pilih **Seterusnya**.
1. Petakan medan semantik untuk atribut dalam entiti sejarah langganan dan pilih **Simpan**. Untuk perihalan medan, lihatlah [prasyarat](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Halaman sejarah langganan yang menunjukkan atribut semantik yang dipetakan kepada medan dalam entiti sejarah langganan yang dipilih](media/subscription-churn-subscriptionhistorymapping.PNG "Halaman sejarah langganan yang menunjukkan atribut semantik yang dipetakan kepada medan dalam entiti sejarah langganan yang dipilih")
1. Pilih **Tambahkan data** untuk **Aktiviti pelanggan** dan pilih entiti yang menyediakan maklumat aktiviti pelanggan seperti yang dihuraikan dalam prasyarat.
1. Pilih jenis aktiviti yang sepadan dengan jenis aktiviti pelanggan yang anda konfigurasikan.  Pilih **Cipta baharu** dan berikan nama jika anda tidak melihat pilihan yang memadankan jenis aktiviti yang anda perlukan.
1. Anda perlu mengkonfigurasikan perhubungan daripada entiti aktiviti pelanggan anda kepada entiti Pelanggan.
    1. Pilih medan yang mengenal pasti pelanggan dalam jadual aktiviti pelanggan, yang boleh dikaitkan secara langsung kepada ID pelanggan utama bagi entiti Pelanggan anda.
    1. Pilih entiti Pelanggan yang memadankan entiti Pelanggan utama anda
    1. Masukkan nama yang menghuraikan perhubungan.
1. Pilih **Seterusnya**.
1. Petakan medan semantik untuk atribut dalam entiti aktiviti pelanggan dan pilih **Simpan**. Untuk perihalan medan, lihatlah [prasyarat](#prerequisites).
1. (Pilihan) Jika anda mempunyai sebarang aktiviti pelanggan lain yang anda ingin sertakan, ulangi langkah di atas.
   > [!div class="mx-imgBorder"]
   > ![Takrifkan perhubungan entiti](media/subscription-churn-customeractivitiesmapping.PNG "Halaman aktiviti pelanggan yang menunjukkan atribut semantik yang dipetakan kepada medan dalam entiti aktiviti pelanggan yang dipilih")
1. Pilih **Seterusnya**.

### <a name="set-schedule-and-review-configuration"></a>Tetapkan jadual dan konfigurasi ulasan

1. Tetapkan kekerapan untuk melatih semula model anda. Tetapan ini adalah penting untuk mengemas kini ketepatan ramalan kerana data baru telah dimasukkan dalam wawasan khalayak. Kebanyakan perniagaan boleh melatih semula sekali setiap bulan dan mendapatkan ketepatan yang baik untuk ramalan mereka.
1. Pilih **Seterusnya**.
1. Semak semula konfigurasi. Anda boleh kembali ke mana-mana bahagian konfigurasi ramalan dengan memilih **Edit** di bawah nilai yang ditunjukkan. Atau anda boleh memilih langkah konfigurasi daripada penunjuk kemajuan.
1. Jika semua nilai dikonfigurasikan dengan betul, pilih **Simpan dan jalankan** untuk memulakan proses ramalan. Pada tab **Langganan saya**, anda boleh melihat status ramalan anda. Proses mungkin mengambil masa beberapa jam untuk dilengkapkan bergantung kepada amaun data yang digunakan dalam ramalan.

## <a name="review-a-prediction-status-and-results"></a>Semak semula status dan hasil ramalan

1. Pergi ke tab **Ramalan saya** pada **Kecerdasan** > **Ramalan**.
   > [!div class="mx-imgBorder"]
   > ![Pandangan halaman Ramalan Saya](media/subscription-churn-mypredictions.PNG "Pandangan halaman Ramalan Saya")
1. Pilih ramalan yang anda mahu semak semula.
   - **Nama ramalan:** Nama ramalan yang disediakan apabila menciptanya.
   - **Jenis ramalan:** Jenis model yang digunakan untuk ramalan
   - **Entiti output:** Nama entiti untuk menyimpan output ramalan. Anda boleh menemui entiti dengan nama ini pada **Data** > **Entiti**.    
     Dalam entiti output, *ChurnScore* adalah kebarangkalian yang diramalkan untuk pulangan dan *IsChurn* adalah label binari berdasarkan *ChurnScore* dengan ambang 0.5. Ambang lalai mungkin tidak berfungsi untuk senario anda. [Cipta segmen baharu](segments.md#create-a-new-segment) dengan ambang pilihan anda.
   - **Medan yang diramal:** Medan ini diisi hanya untuk beberapa jenis ramalan dan tidak digunakan dalam ramalan pulangan langganan.
   - **Status:** Status semasa jalanan ramalan.
        - **Dibaris gilir:** Ramalan pada masa ini menunggu proses lain untuk berjalan.
        - **Menyegar semula:** Ramalan pada masa ini menjalankan peringkat pemprosesan "skor" untuk menghasilkan hasil yang akan mengalir ke dalam entiti output.
        - **Gagal:** ramalan telah gagal. Pilih **Log** untuk butiran lanjut.
        - **Berjaya:** ramalan telah berjaya. Pilih **Pandangan** di bawah elipsis menegak untuk menyemak semula langganan
   - **Diedit:** Tarikh konfigurasi untuk ramalan telah diubah.
   - **Terakhir disegar semula:** Tarikh ramalan menyegar semula hasil dalam entiti output.
1. Pilih elipsis menegak di sebelah ramalan yang anda mahu semak semula hasilnya dan pilih **Pandangan**.
   > [!div class="mx-imgBorder"]
   > ![Pandangan pilihan dalam elipsis menegak untuk ramalan termasuk edit, segar semula, pandangan, log dan padam](media/subscription-churn-verticalellipses.PNG "Pandangan pilihan dalam elipsis menegak untuk ramalan termasuk edit, segar semula, pandangan, log dan padam")
1. Terdapat tiga bahagian utama data dalam halaman hasil:
    1. **Melatih prestasi model:** A, B atau C ialah skor yang mungkin. Skor ini menunjukkan prestasi ramalan dan boleh membantu anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entiti output.
        - Skor ditentukan berdasarkan peraturan yang berikut:
            - **A** apabila model diramal dengan tepat sekurang-kurangnya 50% daripada jumlah ramalan dan apabila peratus ramalan yang tepat untuk pelanggan yang pulangannya lebih besar daripada kadar peratusan pulangan terdahulu dengan sekurang-kurangnya 10% daripada kadar peratusan pulangan terdahulu.
            - **B** apabila model diramal dengan tepat sekurang-kurangnya 50% daripada jumlah ramalan dan apabila peratus ramalan yang tepat untuk pelanggan yang pulangannya sehingga 10% lebih besar daripada kadar peratusan pulangan terdahulu bagi kadar peratusan pulangan terdahulu.
            - **C** apabila model diramal dengan tepat kurang daripada 50% jumlah ramalan atau apabila peratus ramalan yang tepat untuk pelanggan yang pulangannya kurang daripada kadar purata pulangan terdahulu.
               > [!div class="mx-imgBorder"]
               > ![Pandangan hasil prestasi model](media/subscription-churn-modelperformance.PNG "Pandangan hasil prestasi model")
    1. **Kemungkinan untuk pulangan (bilangan pelanggan):** Kumpulan pelanggan berdasarkan risiko pulangan mereka yang diramalkan. Data ini boleh membantu anda kemudian jika anda mahu mencipta segmen pelanggan dengan risiko pulangan yang tinggi. Segmen seperti ini dapat membantu memahami tempat penggalan anda yang sepatutnya bagi keahlian segmen.
       > [!div class="mx-imgBorder"]
       > ![Graf yang menunjukkan taburan hasil pulangan, dibahagikan kepada julat dari 0-100%](media/subscription-churn-resultdistribution.PNG "Graf yang menunjukkan taburan hasil pulangan, dibahagikan kepada julat dari 0-100%")
    1. **Faktor paling mempengaruhi:** Terdapat banyak faktor yang diambil kira apabila mencipta ramalan anda. Setiap faktor mempunyai kepentingannya yang dikira untuk ramalan teragregat yang dicipta oleh model. Anda boleh menggunakan faktor ini untuk membantu mengesahkan hasil ramalan anda. Atau anda boleh menggunakan maklumat ini kemudian untuk [mencipta segmen](segments.md) yang dapat membantu mempengaruhi risiko pulangan untuk pelanggan.
       > [!div class="mx-imgBorder"]
       > ![Senarai yang menunjukkan faktor yang mempengaruhi dan kepentingannya dalam meramal hasil pulangan](media/subscription-churn-influentialfactors.PNG "Senarai yang menunjukkan faktor yang mempengaruhi dan kepentingannya dalam meramal hasil pulangan")

## <a name="fix-a-failed-prediction"></a>Betulkan ramalan yang gagal

1. Pergi ke tab **Ramalan saya** pada **Kecerdasan** > **Ramalan**.
1. Pilih ramalan yang anda ingin lihat log ralatnya dan pilih **Log**.
   > [!div class="mx-imgBorder"]
   > ![Pandangan bar menu hasil termasuk butang tutup, edit model dan log](media/subscription-churn-logsbutton.PNG "Pandangan bar menu hasil termasuk butang tutup, edit model dan log")
1. Semak semula semua ralat. Terdapat beberapa jenis ralat yang boleh berlaku dan ia menghuraikan keadaan yang menyebabkan ralat tersebut. Contohnya, ralat yang tidak mencukupi data untuk meramal secara tepat biasanya diselesaikan dengan memuatkan data tambahan.

## <a name="refresh-a-prediction"></a>Segar semula ramalan

Ramalan akan menyegar semula secara automatik pada [jadual yang sama data anda menyegar semula](system.md#schedule-tab) seperti yang dikonfigurasikan dalam tetapan.

1. Pergi ke tab **Ramalan saya** pada **Kecerdasan** > **Ramalan**.
1. Pilih elipsis menegak di sebelah ramalan yang anda mahu segar semula.
1. Pilih **Segar Semula**.

## <a name="delete-a-prediction"></a>Padamkan ramalan

1. Pergi ke tab **Ramalan saya** pada **Kecerdasan** > **Ramalan**.
1. Pilih elipsis menegak di sebelah ramalan yang anda mahu padamkan.
1. Pilih **Padam**.

> [!NOTE]
> Memadam ramalan akan mengalih keluar entiti outputnya.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
