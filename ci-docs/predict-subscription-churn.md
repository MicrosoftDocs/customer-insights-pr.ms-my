---
title: Meramalkan churn langganan (mengandungi video)
description: Meramal sama ada pelanggan berada dalam risiko kerana tidak lagi menggunakan produk atau perkhidmatan langganan syarikat anda.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610247"
---
# <a name="predict-subscription-churn"></a>Ramal pulangan langganan

Meramal sama ada pelanggan berada dalam risiko kerana tidak lagi menggunakan produk atau perkhidmatan langganan syarikat anda. Data langganan termasuk langganan aktif dan tidak aktif untuk setiap pelanggan supaya terdapat berbilang entri bagi setiap ID pelanggan.

Anda mesti mempunyai pengetahuan perniagaan untuk memahami apa maksud churn untuk perniagaan anda. Kami menyokong definisi churn berasaskan masa, yang bermaksud pelanggan dianggap telah menghasilkan tempoh masa selepas langganan mereka berakhir.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Cuba ramalan churn langganan menggunakan data sampel: [Langganan churn ramalan panduan sampel](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md).
- Sekurang-kurangnya 10 profil pelanggan, lebih baik daripada 1,000 pelanggan unik.
- Pengecam Pelanggan, pengecam unik untuk memadankan langganan kepada pelanggan anda.
- Data langganan sekurang-kurangnya dua kali ganda tetingkap masa yang dipilih. Sebaik-baiknya, dua hingga tiga tahun data langganan. Sejarah langganan mesti termasuk:
  - **ID Langganan:** Pengecam unik langganan.
  - **Tarikh Tamat Langganan:** Tarikh langganan tamat tempoh untuk pelanggan.
  - **Tarikh Mula Langganan:** Tarikh langganan bermula untuk pelanggan.
  - **Tarikh Transaksi:** Tarikh perubahan langganan berlaku. Contohnya, pelanggan membeli atau membatalkan langganan.
  - **Adakah langganan berulang:** Medan benar/palsu Boolean yang menentukan sama ada langganan akan diperbaharui dengan ID langganan yang sama tanpa campur tangan pelanggan.
  - **Kekerapan Perulangan (dalam bulan):** Untuk langganan berulang, bulan langganan akan diperbaharui. Contohnya, langganan tahunan yang diperbaharui secara automatik untuk pelanggan setiap tahun untuk setahun lagi mempunyai nilai 12.
  - **Amaun** Langganan: Jumlah mata wang yang dibayar oleh pelanggan untuk pembaharuan langganan. Ia boleh membantu mengenal pasti corak untuk tahap langganan yang berbeza.
- Sekurang-kurangnya dua rekod aktiviti untuk 50% pelanggan yang anda ingin kira churn untuk. Aktiviti pelanggan mesti termasuk:
  - **Kekunci primer:** Pengecam unik untuk sesuatu aktiviti. Contohnya, lawatan tapak web atau rekod penggunaan yang menunjukkan episod rancangan TV dilihat oleh pelanggan.
  - **Cap Waktu:** Tarikh dan masa acara yang dikenal pasti oleh kunci utama.
  - **Acara:** Nama acara yang anda ingin gunakan. Contohnya, medan yang dipanggil "UserAction" dalam perkhidmatan penstriman video boleh mempunyai nilai "Dilihat".
  - **Butiran:** Maklumat terperinci tentang peristiwa. Contohnya, medan yang dipanggil "ShowTitle" dalam perkhidmatan penstriman video boleh mempunyai nilai video yang ditonton pelanggan.
- Kurang daripada 20% nilai hilang dalam medan data entiti yang disediakan.

## <a name="create-a-subscription-churn-prediction"></a>Cipta ramalan pulangan langganan

Pilih **Simpan draf** pada bila-bila masa untuk menyimpan ramalan sebagai draf. Draf ramalan dipaparkan dalam tab **Ramalan** saya.

1. Pergi ke **Ramalan** > **Perisikan**.

1. Pada tab **Cipta**, pilih **Gunakan model** pada **jubin model** churn Pelanggan.

1. Pilih **Langganan** untuk jenis churn kemudian **Bermula**.

1. **Namakan model ini** dan **Nama entiti output** untuk membezakannya daripada model atau entiti lain.

1. Pilih **Seterusnya**.

### <a name="define-customer-churn"></a>Takrifkan pulangan pelanggan

1. Masukkan bilangan **Hari sejak langganan berakhir** yang perniagaan anda pertimbangkan pelanggan akan berada dalam keadaan mempunyai pulangan. Tempoh ini biasanya dikaitkan dengan aktiviti perniagaan seperti tawaran atau usaha pemasaran lain yang cuba mengelakkan kehilangan pelanggan.

1. Masukkan bilangan **Hari untuk menyiasat masa depan untuk meramalkan churn**. Sebagai contoh, ramalkan risiko pulangan untuk pelanggan anda sepanjang 90 hari yang akan datang untuk menyelaraskan usaha pengekalan pemasaran anda. Meramalkan risiko pulangan untuk tempoh masa yang lebih lama atau lebih singkat boleh menjadikannya lebih sukar untuk menangani faktor-faktor dalam profil risiko pulangan, bergantung kepada keperluan perniagaan khusus anda.

1. Pilih **Seterusnya**.

### <a name="add-required-data"></a>Tambah data yang diperlukan

1. Pilih **Tambah data** untuk **sejarah** Langganan.

1. Pilih jenis **aktiviti semantik Langganan** yang mengandungi maklumat sejarah langganan yang diperlukan. Jika aktiviti belum disediakan, pilih **di sini** dan buatnya.

1. Di bawah **Aktiviti**, jika atribut aktiviti dipetakan secara semantik apabila aktiviti dicipta, pilih atribut atau entiti tertentu yang ingin anda fokuskan pengiraan. Jika pemetaan semantik tidak berlaku, pilih **Edit dan petakan** data anda.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Menambah data yang diperlukan untuk model Churn langganan":::

1. Pilih **Seterusnya** dan semak atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Pilih **Tambah data** untuk **aktiviti** Pelanggan.

1. Pilih jenis aktiviti semantik yang menyediakan maklumat aktiviti pelanggan. Jika aktiviti belum disediakan, pilih **di sini** dan buatnya.

1. Di bawah **Aktiviti**, jika atribut aktiviti dipetakan secara semantik apabila aktiviti dicipta, pilih atribut atau entiti tertentu yang ingin anda fokuskan pengiraan. Jika pemetaan semantik tidak berlaku, pilih **Edit dan petakan** data anda.

1. Pilih **Seterusnya** dan semak atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Tambah lebih banyak aktiviti atau pilih **Seterusnya**.

### <a name="set-update-schedule"></a>Tetapkan jadual kemas kini

1. Pilih kekerapan untuk melatih semula model anda. Tetapan ini penting untuk mengemas kini ketepatan ramalan kerana data baru ditelan dalam Wawasan Pelanggan. Kebanyakan perniagaan boleh melatih semula sekali setiap bulan dan mendapatkan ketepatan yang baik untuk ramalan mereka.

1. Pilih **Seterusnya**.

### <a name="review-and-run-the-model-configuration"></a>Semak dan jalankan konfigurasi model

Langkah **Semak semula dan jalankan** menunjukkan ringkasan konfigurasi dan menyediakan peluang untuk membuat perubahan sebelum anda mencipta ramalan.

1. Pilih **Edit** pada sebarang langkah untuk menyemak semula dan membuat sebarang perubahan.

1. Jika anda berpuas hati dengan pilihan anda, pilih **Simpan dan jalankan** untuk mula menjalankan model. Pilih **Selesai**. Tab **Ramalan** saya dipaparkan semasa ramalan sedang dicipta. Proses mungkin mengambil masa beberapa jam untuk dilengkapkan bergantung kepada amaun data yang digunakan dalam ramalan.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Lihat keputusan ramalan

1. Pergi ke **Ramalan** > **Perisikan**.

1. Dalam tab **Ramalan** saya, pilih ramalan yang anda ingin lihat.

Terdapat tiga bahagian utama data dalam halaman hasil:

- **Prestasi model latihan**: Gred A, B, atau C menunjukkan prestasi ramalan dan boleh membantu anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entiti output.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Imej kotak maklumat skor model dengan gred A.":::

  Gred ditentukan berdasarkan peraturan berikut:
  - **A apabila model dengan tepat meramalkan sekurang-kurangnya 50% daripada jumlah ramalan, dan apabila peratusan ramalan yang** tepat untuk pelanggan yang tergelak lebih besar daripada kadar purata churn sejarah sekurang-kurangnya 10%.
  - **B** apabila model meramalkan dengan tepat sekurang-kurangnya 50% daripada jumlah ramalan, dan apabila peratusan ramalan yang tepat untuk pelanggan yang tergelak adalah sehingga 10% lebih besar daripada kadar purata churn sejarah.
  - **C** apabila model dengan tepat meramalkan kurang daripada 50% daripada jumlah ramalan, atau apabila peratusan ramalan yang tepat untuk pelanggan yang tergelak kurang daripada kadar churn purata sejarah.
  
- **Kecenderungan untuk pulangan (bilangan pelanggan)**: Kumpulan pelanggan berdasarkan risiko pulangan mereka yang diramalkan. Secara pilihan, [buat segmen pelanggan](prediction-based-segment.md) dengan risiko churn yang tinggi. Segmen seperti ini dapat membantu memahami tempat penggalan anda yang sepatutnya bagi keahlian segmen.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Graf yang menunjukkan taburan hasil pulangan, dibahagikan kepada julat dari 0-100%":::

- **Faktor paling mempengaruhi:** Terdapat banyak faktor yang diambil kira apabila mencipta ramalan anda. Setiap faktor mempunyai kepentingannya yang dikira untuk ramalan teragregat yang dicipta oleh model. Gunakan faktor ini untuk membantu mengesahkan hasil ramalan anda. Atau gunakan maklumat ini kemudian untuk [mencipta segmen](.//prediction-based-segment.md) yang boleh membantu mempengaruhi risiko churn untuk pelanggan.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Senarai yang menunjukkan faktor yang mempengaruhi dan kepentingannya dalam meramal hasil pulangan.":::

> [!NOTE]
> Dalam entiti output untuk model ini, *ChurnScore* adalah kebarangkalian churn yang diramalkan dan *IsChurn* adalah label binari berdasarkan *ChurnScore* dengan ambang 0.5. Jika ambang lalai ini tidak berfungsi untuk senario anda, [cipta segmen](segments.md) baharu dengan ambang pilihan anda. Untuk melihat skor churn, pergi ke **Entiti** > **Data** dan lihat tab data untuk entiti output yang anda takrifkan untuk model ini.

[!INCLUDE [footer-include](includes/footer-banner.md)]
