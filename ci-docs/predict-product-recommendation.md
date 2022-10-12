---
title: Ramal pengesyoran produk
description: Meramalkan produk yang pelanggan mungkin akan beli atau berinteraksi dengannya.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610293"
---
# <a name="predict-product-recommendations"></a>Ramal pengesyoran produk

Model pengesyoran produk mencipta set pengesyoran produk ramalan. Pengesyoran adalah berdasarkan tingkah laku pembelian sebelumnya dan pelanggan dengan corak pembelian yang sama. Model ini adalah untuk pengguna individu (B-to-C).

Anda mesti mempunyai pengetahuan perniagaan mengenai pelbagai jenis produk untuk perniagaan anda dan bagaimana pelanggan anda berinteraksi dengan mereka. Kami menyokong mengesyorkan produk yang telah dibeli sebelum oleh pelanggan anda atau pengesyoran untuk produk baru.

Pengesyoran produk mungkin tertakluk kepada undang-hukum tempatan dan peraturan dan jangkaan pelanggan, yang mana model yang tidak dibina secara khusus diambil kira. Oleh itu, **anda mesti menyemak cadangan sebelum menyampaikannya kepada pelanggan** anda untuk memastikan bahawa anda mematuhi mana-mana undang-undang atau peraturan yang berkenaan, dan jangkaan pelanggan untuk apa yang anda cadangkan.

Output model ini memberikan cadangan berdasarkan ID produk. Mekanisme penghantaran anda mesti memetakan ID produk yang diramalkan kepada kandungan yang sesuai untuk pelanggan anda mengambil kira penyetempatan, kandungan imej dan kandungan atau tingkah laku khusus perniagaan yang lain.

> [!TIP]
> Cuba cadangan produk ramalan menggunakan data sampel: [Cadangan produk ramalan panduan sampel](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [keizinan Penyumbang](permissions.md)
- Sekurang-kurangnya 100 pelanggan, lebih baik daripada 10,000 pelanggan.
- Pengecam Pelanggan, pengecam unik untuk memadankan transaksi dengan pelanggan individu
- Sekurang-kurangnya satu tahun data transaksional, sebaik-baiknya dua hingga tiga tahun untuk memasukkan beberapa bermusim. Sebaik-baiknya, sekurang-kurangnya tiga atau lebih transaksi setiap ID Pelanggan. Sejarah transaksi mesti termasuk:
  - **ID** Transaksi: Pengecam unik pembelian atau transaksi.
  - **Tarikh transaksi**: Tarikh pembelian atau transaksi.
  - **Nilai transaksi**: Nilai berangka pembelian atau transaksi.
  - **ID** produk unik: ID produk atau perkhidmatan yang dibeli jika data anda berada pada tahap item baris.
  - **Pembelian atau pemulangan**: Nilai boolean benar/palsu di mana *benar* mengenal pasti bahawa transaksi adalah pulangan. Jika data Pembelian atau Pemulangan tidak disediakan dalam model dan **Nilai transaksi** adalah negatif, kami menyimpulkan pulangan.
- Entiti data katalog produk untuk digunakan sebagai penapis produk.

> [!NOTE]
> - Model ini memerlukan sejarah transaksi pelanggan anda di mana transaksi adalah sebarang data yang menerangkan interaksi pengguna-produk. Sebagai contoh, membeli produk, mengambil kelas, atau menghadiri acara.
> - Hanya satu entiti sejarah transaksi boleh dikonfigurasi. Sekiranya terdapat banyak entiti pembelian, gabungkannya Power Query sebelum pengambilan data.
> - Jika butiran pesanan dan pesanan adalah entiti yang berbeza, gabungkannya sebelum menggunakan model. Model ini tidak berfungsi dengan hanya ID pesanan atau ID resit dalam entiti.

## <a name="create-a-product-recommendation-prediction"></a>Cipta ramalan pengesyoran produk

Pilih **Simpan draf** pada bila-bila masa untuk menyimpan ramalan sebagai draf. Draf ramalan dipaparkan dalam tab **Ramalan** saya.

1. Pergi ke **Ramalan** > **Perisikan**.

1. Pada tab **Cipta**, pilih **Gunakan model** pada **jubin Cadangan produk (pratonton**).

1. Pilih **Mulakan**.

1. **Namakan model ini** dan **Nama entiti output** untuk membezakannya daripada model atau entiti lain.

1. Pilih **Seterusnya**.

### <a name="define-product-recommendation-preferences"></a>Tentukan keutamaan cadangan produk

1. **Tetapkan Bilangan produk** untuk dicadangkan kepada pelanggan. Nilai ini bergantung kepada cara kaedah penghantaran anda mengisi data.

1. Pilih jika anda ingin memasukkan produk yang pelanggan beli sebelum ini dalam **medan Beli ulangan yang dijangkakan**.

1. **Tetapkan tetingkap** Lihat kembali dengan rangka masa yang dipertimbangkan oleh model sebelum mengesyorkan produk kepada pengguna sekali lagi. Sebagai contoh, nyatakan pelanggan membeli komputer riba setiap dua tahun. Model ini melihat sejarah pembelian selama dua tahun yang lalu, dan jika ia menemui item, item itu ditapis dari cadangan.

1. Pilih **Seterusnya**

### <a name="add-purchase-history"></a>Tambah sejarah pembelian

1. Pilih **Tambah data** untuk **sejarah** transaksi Pelanggan.

1. Pilih jenis **aktiviti semantik SalesOrderLine** yang mengandungi maklumat sejarah transaksi atau pembelian yang diperlukan. Jika aktiviti belum disediakan, pilih **di sini** dan buatnya.

1. Di bawah **Aktiviti**, jika atribut aktiviti dipetakan secara semantik apabila aktiviti dicipta, pilih atribut atau entiti tertentu yang ingin anda fokuskan pengiraan. Jika pemetaan semantik tidak berlaku, pilih **Edit dan petakan** data anda.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Anak tetingkap sisi menunjukkan pemilihan aktiviti tertentu di bawah jenis semantik.":::

1. Pilih **Seterusnya** dan semak atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Pilih **Seterusnya**.

### <a name="add-product-information-and-filters"></a>Tambah maklumat dan penapis produk

Kadang-kadang, hanya produk tertentu yang bermanfaat atau sesuai untuk jenis ramalan yang anda bina. Gunakan penapis produk untuk mengenal pasti subset produk dengan ciri khusus untuk dicadangkan kepada pelanggan anda. Model ini akan menggunakan semua produk yang tersedia untuk mempelajari corak tetapi hanya menggunakan produk yang sepadan dengan penapis produk dalam outputnya.

1. Tambah entiti katalog produk anda yang mengandungi maklumat untuk setiap produk. Petakan maklumat yang diperlukan dan pilih **Simpan**.

1. Pilih **Seterusnya**.

1. Pilih **Penapis produk**:

   - **Tiada penapis** : Gunakan semua produk dalam ramalan pengesyoran produk.

   - **Tentukan penapis produk khusus**: Gunakan produk tertentu dalam ramalan pengesyoran produk. **Dalam anak tetingkap Atribut** katalog produk, pilih atribut daripada entiti katalog produk anda yang anda ingin masukkan dalam penapis.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Anak tetingkap sisi yang menunjukkan dikaitkan dalam entiti katalog produk untuk dipilih untuk penapis produk.":::

1. Pilih jika anda mahu penapis produk digunakan **dan** atau **untuk** menggabungkan pilihan atribut anda secara logik daripada katalog produk.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Konfigurasi sampel untuk penapis produk yang digabungkan dengan penyambung logik DAN.":::

1. Pilih **Seterusnya**.

### <a name="set-update-schedule"></a>Tetapkan jadual kemas kini

1. Pilih kekerapan untuk melatih semula model anda. Tetapan ini penting untuk mengemas kini ketepatan ramalan kerana data baru ditelan ke dalam Wawasan Pelanggan. Kebanyakan perniagaan boleh melatih semula sekali setiap bulan dan mendapatkan ketepatan yang baik untuk ramalan mereka.

1. Pilih **Seterusnya**.

### <a name="review-and-run-the-model-configuration"></a>Semak dan jalankan konfigurasi model

Langkah **Semak semula dan jalankan** menunjukkan ringkasan konfigurasi dan menyediakan peluang untuk membuat perubahan sebelum anda mencipta ramalan.

1. Pilih **Edit** pada sebarang langkah untuk menyemak semula dan membuat sebarang perubahan.

1. Jika anda berpuas hati dengan pilihan anda, pilih **Simpan dan jalankan** untuk mula menjalankan model. Pilih **Selesai**. Tab **Ramalan** saya dipaparkan semasa ramalan sedang dicipta. Proses mungkin mengambil masa beberapa jam untuk dilengkapkan bergantung kepada amaun data yang digunakan dalam ramalan.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Lihat keputusan ramalan

1. Pergi ke **Ramalan** > **Perisikan**.

1. Dalam tab **Ramalan** saya, pilih ramalan yang anda ingin lihat.

Terdapat lima bahagian utama data dalam halaman keputusan.

- **Prestasi model:** Gred A, B atau C menunjukkan prestasi ramalan dan boleh membantu anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entiti output.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Imej hasil prestasi model dengan gred A.":::

  Gred ditentukan berdasarkan peraturan berikut:
  - **A** apabila metrik "Kejayaan @ K" sekurang-kurangnya 10% lebih banyak daripada garis dasar.
  - **B** apabila metrik "Success @ K" adalah 0% hingga 10% lebih daripada garis dasar.
  - **C** apabila metrik "Success @ K" kurang daripada garis dasar.
  - **Baseline**: Produk teratas yang paling disyorkan dengan kiraan pembelian merentasi semua pelanggan + peraturan yang dipelajari yang dikenal pasti oleh model = satu set cadangan untuk pelanggan. Ramalan kemudiannya dibandingkan dengan produk teratas, seperti yang dikira oleh bilangan pelanggan yang telah membeli produk tersebut. Jika pelanggan mempunyai sekurang-kurangnya satu produk dalam produk yang disyorkan yang juga dilihat dalam produk yang dibeli teratas, mereka dianggap sebagai sebahagian daripada garis dasar. Sebagai contoh, jika 10 pelanggan ini mempunyai produk yang disyorkan dibeli daripada 100 jumlah pelanggan, garis dasarnya ialah 10%.
  - **Kejayaan @ K**: Cadangan dibuat untuk semua pelanggan dan dibandingkan dengan set tempoh masa transaksi yang ditetapkan. Contohnya, dalam tempoh 12 bulan, bulan 12 diketepikan sebagai set data pengesahan. Jika model meramalkan sekurang-kurangnya satu perkara yang anda akan membeli dalam bulan 12 berdasarkan apa yang dipelajari daripada 11 bulan sebelumnya, pelanggan akan meningkatkan metrik "Kejayaan @ K".

- **Produk yang paling dicadangkan (dengan selaras):** Lima produk teratas yang diramalkan untuk pelanggan anda.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Graf menunjukkan 5 produk teratas yang paling disyorkan.":::

- **Faktor pengesyoran utama**: Model ini menggunakan sejarah transaksi pelanggan untuk membuat pengesyoran produk. Ia mempelajari corak berdasarkan pembelian masa lalu dan mendapati persamaan antara pelanggan dan produk. Persamaan ini kemudiannya digunakan untuk menjana pengesyoran produk.
  Faktor-faktor berikut boleh mempengaruhi cadangan produk yang dihasilkan oleh model.
  - **Urus niaga lalu**: Produk yang disyorkan adalah berdasarkan corak pembelian masa lalu. Sebagai contoh, model ini boleh mengesyorkan *Surface Arc Mouse* jika seseorang membeli *Surface Book 3* dan *Surface Pen* baru-baru ini. Model ini mengetahui bahawa dari segi sejarah, ramai pelanggan telah membeli *Surface Arc Mouse* selepas membeli *Surface Book 3* dan *Surface Pen*.
  - **Persamaan pelanggan**: Produk yang disyorkan telah dibeli dari segi sejarah oleh pelanggan lain yang menunjukkan corak pembelian yang sama. Sebagai contoh, John disyorkan *Surface Headphones 2* kerana Jennifer dan Brad baru-baru ini membeli *Surface Headphones 2*. Model ini percaya John adalah serupa dengan Jennifer dan Brad kerana mereka mempunyai sejarah corak pembelian yang sama.
  - **Persamaan produk**: Produk yang disyorkan adalah sama dengan produk lain yang dibeli oleh pelanggan sebelum ini. Model ini menganggap dua produk menjadi serupa jika dibeli bersama atau oleh pelanggan yang serupa. Sebagai contoh, seseorang mendapat pengesyoran untuk *Pemacu Storan USB* kerana mereka sebelum ini membeli *USB-C hingga Penyesuai USB* dan model percaya bahawa *Pemacu Storan USB* adalah serupa dengan *USB-C kepada Penyesuai USB* berdasarkan corak pembelian sejarah.

  Setiap pengesyoran produk dipengaruhi oleh satu atau lebih faktor ini. Peratusan pengesyoran yang mana setiap faktor yang mempengaruhi dan memainkan peranan digambarkan dalam carta. Dalam contoh berikut, 100% daripada pengesyoran dipengaruhi oleh transaksi masa lalu, 60% oleh persamaan pelanggan dan 22% oleh persamaan produk. Tuding pada bar dalam carta untuk melihat peratusan yang tepat di tempat faktor yang mempengaruhi menyumbang.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Faktor cadangan utama yang dipelajari oleh model untuk menjana cadangan produk.":::

- **Statistik data**: Gambaran keseluruhan bilangan urus niaga, pelanggan dan produk yang dipertimbangkan oleh model. Ia berdasarkan data input yang digunakan untuk mempelajari corak dan menjana pengesyoran produk.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Statistik data di sekitar data input yang digunakan oleh model untuk mempelajari corak.":::
  
  Model ini menggunakan semua data yang tersedia untuk mempelajari corak. Oleh itu, jika anda menggunakan penapisan produk dalam konfigurasi model, bahagian ini menunjukkan jumlah bilangan produk yang dianalisis oleh model untuk mempelajari corak, yang mungkin berbeza daripada bilangan produk yang sepadan dengan kriteria penapisan yang ditentukan. Penapisan digunakan pada output yang dihasilkan oleh model.

- **Contoh cadangan produk:** Sampel cadangan yang model percaya mungkin dibeli oleh pelanggan. Jika katalog produk ditambahkan, ID produk digantikan dengan nama produk.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Senarai menunjukkan cadangan keyakinan tinggi untuk set pelanggan individu yang terpilih.":::

> [!NOTE]
> Dalam entiti output untuk model ini, *Skor* menunjukkan ukuran kuantitatif cadangan. Model ini mengesyorkan produk yang mempunyai skor yang lebih tinggi ke atas produk yang mempunyai skor yang lebih rendah. Untuk melihat skor, pergi ke **Entiti** > **Data** dan lihat tab data untuk entiti output yang anda takrifkan untuk model ini.

[!INCLUDE [footer-include](includes/footer-banner.md)]
