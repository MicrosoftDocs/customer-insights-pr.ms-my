---
title: Percubaan Machine Learning Studio (klasik)
description: Gunakan model Machine Learning Studio (klasik) dalam Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2eb44604e72b32292f971754d4f8c4fd1988c697
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555180"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Gunakan model berdasarkan Azure Machine Learning Studio (klasik)

Data yang disatukan dalam Dynamics 365 Customer Insights adalah ialah untuk membina model pembelajaran mesin yang boleh menjana Insights perniagaan tambahan. Customer Insights berintegrasi dengan Machine Learning Studio (klasik) untuk menggunakan model tersuai anda sendiri. Untuk melihat cara model dibangunkan dalam Pembelajaran Mesin Azure berintegrasi dengan Customer Insights, lihat [Percubaan Pembelajaran Mesin Azure](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Prasyarat

- Akses kepada Customer Insights
- Langganan Azure Enterprise Aktif
- [Profil pelanggan yang disatukan](data-unification.md)
- [Eksport entiti kepada storan Blob Azure](export-azure-blob-storage.md) disediakan

## <a name="set-up-machine-learning-studio-classic"></a>Sediakan Machine Learning Studio Klasik

Dalam langkah pertama, kita perlu mencipta ruang kerja dan buka Machine Learning Studio (klasik).

1. Pergi ke[https://www.portal.azure.com](https://www.portal.azure.com/) dan daftar masuk.

1. Pilih **Cipta sumber**.

1. Cari **Ruang Kerja Studio Pembelajaran Mesin** dan pilih **Cipta**.

1. Masukkan butiran yang diperlukan untuk [mencipta ruang kerja](/azure/machine-learning/studio/create-workspace). Pilih **Peringkat penetapan harga pelan Perkhidmatan web** berdasarkan jumlah data yang anda rancang untuk diimport. Untuk prestasi terbaik, pilih **Lokasi** geografi yang paling dekat dengan anda.

1. Selepas mencipta sumber, papan pemuka ruang kerja Studio Pembelajaran Mesin akan dipaparkan. Pilih **Lancarkan Studio Pembelajaran Mesin**.

   ![Antara muka pengguna Studio Pembelajaran Mesin Azure.](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Menggunakan Studio Pembelajaran Mesin Azure

Kini anda boleh mencipta percubaan baharu atau mengimport templat percubaan sedia ada daripada galeri sampel. Terdapat sampel percubaan untuk tiga senario standard:

- [Ramalan pulangan pelanggan](#churn-analysis)

- [Nilai sepanjang hayat pelanggan](#customer-lifetime-value-prediction)

- [Pengesyoran produk atau tindakan terbaik seterusnya](#productrecommendation-or-next-best-action)

1. Jika anda cipta percubaan baharu atau gunakan templat percubaan daripada galeri, anda perlu mengkonfigurasikan sifat **Import Data**. Gunakan pengalaman dipandu atau berikan butiran secara terus untuk mengakses Storan Blob Azure yang mengandungi data anda.  

   ![Percubaan Studio Pembelajaran Mesin Azure.](media/azure-machine-learning-studio-experiment.png)

1. Kini anda boleh membina talian paip pemprosesan tersuai untuk membersihkan dan praproses data, mengektrak ciri, dan melatih model yang sesuai.

1. Uji dan optimumkan prestasi model.

1. Apabila anda berpuas hati dengan kualiti model, pilih **Sediakan perkhidmatan web** > **Perkidmatan Web Ramalan**. Pilihan ini mengimport model yang terlatih dan saluran paip pencirian daripada percubaan latihan kepada perkhidmatan ramalan. Perkhidmatan ramalan boleh mengambil set data input lain dengan skema yang digunakan dalam percubaan latihan untuk membuat ramalan.

   ![Sediakan perkhidmatan web ramalan.](media/predictive-webservice-control.png)

1. Sebaik sahaja percubaan perkhidmatan web ramalan berjaya, anda boleh menggunakannya untuk penjadualan automatik. Untuk membolehkan perkhidmatan web digunakan bersama Customer Insights, pilih **Gunakan Perkhidmatan Web** > **Gunakan Pratonton Perkhidmatan Web [Baharu]**. [Ketahui lebih lanjut tentang menggunakan perkhidmatan web](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Gunakan perkhidmatan web ramalan.](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Model sampel daripada galeri

Kami akan menggunakan senario rekaan Hotel Contoso untuk model dalam artikel ini. Hotel Contoso mengumpul data berikut:

- Data CRM terdiri daripada aktiviti penginapan hotel. Set data termasuk maklumat mengenai tarikh penginapan untuk setiap pelanggan berdaftar. Ia juga mengandungi maklumat mengenai tempahan, jenis bilik, butiran perbelanjaan dan sebagainya. Data bertahan sehingga empat tahun, dari Januari 2014 hingga Januari 2018.
- Profil pelanggan bagi tetamu hotel. Profil ini mengandungi maklumat mengenai setiap pelanggan, termasuk nama, tarikh lahir, alamat pos, jantina dan nombor telefon mereka.
- Penggunaan perkhidmatan yang ditawarkan oleh hotel, seperti spa, dobi, Wi-Fi atau kurier. Maklumat ini dilog untuk setiap pelanggan berdaftar. Lazimnya, penggunaan perkhidmatan dihubungkan dengan penginapan. Dalam sesetengah situasi, perkhidmatan boleh digunakan oleh pelanggan tanpa perlu menginap di hotel.

## <a name="churn-analysis"></a>Analisis Pulangan Pelanggan

Analisis Pulangan Pelanggan diguna pakai untuk bidang perniagaan yang berbeza. Dalam contoh ini, kami akan melihat pulangan pelanggan perkhidmatan, khusus dalam konteks perkhidmatan hotel seperti yang diterangkan di atas. Ia menyediakan contoh kerja talian paip model akhir-hingga-akhir yang boleh digunakan sebagai titik permulaan untuk sebarang jenis model pulangan pelanggan lain.

### <a name="definition-of-churn"></a>Takrifan Pulangan Pelanggan

Takrif pulangan pelanggan boleh berbeza berdasarkan senario. Dalam contoh ini, tetamu yang belum melawat hotel pada tahun lalu harus dilabelkan sebagai yang telah digerakkan.  

Templat percubaan boleh diimport daripada galeri. Pertama, pastikan anda mengimport data untuk **Aktiviti Penginapan Hotel**, **Data Pelanggan** dan **Data Penggunaan Perkhidmatan** dari storan Blob Azure.

   ![Import data untuk model pulangan.](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Pencirian

Berdasarkan definisi pulangan pelanggan, kami terlebih dahulu mengenal pasti ciri mentah yang akan mempengaruhi label. Kemudian, kami memproses ciri mentah ini ke dalam ciri berangka yang boleh digunakan dengan model pembelajaran mesin. Penyepaduan data berlaku dalam Customer Insights supaya kita boleh menyertai jadual ini dengan menggunakan *ID Pelanggan*.

   ![Cantumkan data yang diimport.](media/join-imported-data.png)

Pencirian untuk membina model untuk analisis pulangan pelanggan boleh menjadi sedikit rumit. Data adalah fungsi masa dengan aktiviti hotel baharu yang direkod pada setiap hari. Semasa pencirian, kami mahu menjana ciri statik daripada data dinamik. Dalam situasi ini, kami menjana berbilang ciri daripada aktiviti hotel dengan tingkap gelangsar selama satu tahun. Kami juga meluaskan ciri kategori seperti jenis bilik atau jenis tempahan kepada ciri berasingan menggunakan pengekodan satu panas.  

Senarai terakhir ciri:

| **Nombor**  | **Original_Column**          | **Ciri yang Diterbitkan**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Jenis Bilik                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Jenis Tempahan                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Kategori Pelancongan              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Wang yang Dibelanjakan                | TotalDollarSpent                                                                                                                          |
| 5           | Tarikh Daftar Masuk dan Daftar keluar  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Penggunaan Perkhidmatan                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Pemilihan model

Sekarang kita perlu memilih algoritma optimum untuk digunakan. Dalam situasi ini, kebanyakan ciri adalah berdasarkan ciri kategori. Biasanya, model berasaskan pepohon keputusan berfungsi dengan baik. Jika terdapat hanya ciri berangka, rangkaian neural boleh menjadi pilihan yang lebih baik. Mesin vektor sokongan (SVM) juga merupakan calon baik dalam situasi tersebut; namun, ia memerlukan sedikit penalaan untuk mengekstrak prestasi yang terbaik. Kami memilih **Pepohon Keputusan Digalakkan Kelas Dua** sebagai model pertama pilihan diikuti oleh **SVM Kelas Dua** sebagai model kedua. Azure Machine Learning Studio membolehkan anda melakukan percubaan A/B, jadi ia bermanfaat untuk memulakan dengan dua model dan bukannya satu.

Imej berikut menunjukkan saluran paip latihan dan penilaian model daripada Studio Pembelajaran Mesin Azure:

![Model pulangan dalam Studio Pembelajaran Mesin Azure.](media/azure-machine-learning-model.png)

Kami juga menggunakan teknik yang dipanggil **Kepentingan Ciri Pilih Atur**, aspek penting pengoptimuman model. Model terbina dalam mempunyai sedikit wawasan untuk mempengaruhi sebarang ciri khusus pada ramalan akhir. Kalkulator kepentingan ciri menggunakan algoritma tersuai untuk mengira pengaruh ciri individu pada keputusan untuk model tertentu. Kepentingan ciri ini telah dinormalkan antara +1 hingga -1. Pengaruh negatif bermaksud ciri yang berkaitan mempunyai pengaruh intuitif lawan ke atas hasilnya dan perlu dialih keluar daripada model. Pengaruh positif menunjukkan ciri ini menyumbang secara besar-besaran terhadap ramalan. Nilai ini tidak koefisien korelasi kerana ia adalah metrik yang berbeza. Untuk maklumat lanjut, lihat [Kepentingan Ciri Pilih Atur](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Keseluruhan [percubaan pulangan pelanggan tersedia dalam Galeri AI Azure](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Ramalan nilai sepanjang hayat pelanggan

Pengiraan nilai sepanjang hayat pelanggan (CLTV) merupakan salah satu metrik utama yang boleh digunakan oleh perniagaan untuk menilai dan membahagikan pelanggannya. Untuk perniagaan hotel, penting untuk mengenali pelanggan mereka. Contohnya, memahami faktor yang membentuk pelanggan baik adalah maklumat penting. Ia membantu pengurusan hotel menilai ciri yang mereka perlukan untuk difokuskan dan ditambah baik untuk memuaskan pelanggan yang berbayar tinggi. Keputusan ini boleh memberikan kesan langsung terhadap jualan dan pendapatan.  

### <a name="definition-of-cltv"></a>Takrifan CLTV

Untuk contoh ini, kami mentakrifkan CLTV pelanggan kerana jumlah dolar yang pelanggan dijangka akan belanjakan dalam 365 hari berikutnya. Kami akan menggunakan data sepanjang tiga tahun yang lalu untuk semua pelanggan untuk meramalkan nilai ini.

### <a name="featurization"></a>Pencirian

Dalam hal ini, pencirian akan menjadi agak seperti senario pulangan pelanggan. Walau bagaimanapun, label dan nilai yang diramalkan berbeza daripada ditakrifkan di atas.

### <a name="model-selection"></a>Pemilihan model

Meramalkan CLTV ialah masalah regresi kerana nilai ramalan ialah pemboleh ubah positif yang berterusan. Berdasarkan sifat ciri, kita pilih **Regresi Pepohon Keputusan yang Digalakkan** sebagai satu algoritma dan **Regresi Rangkaian Neural** sebagai algoritma lain untuk melatih model.

## <a name="product-recommendation-or-next-best-action"></a>Pengesyoran produk atau Tindakan Terbaik Seterusnya

Pengesyoran produk dalam senario hotel ditafsirkan sebagai mengesyorkan perkhidmatan yang ditawarkan oleh pihak hotel kepada pelanggan. Tujuannya ialah untuk memilih perkhidmatan yang sesuai untuk pelanggan supaya penggunaannya dimaksimumkan. Ia sama dengan pengesyoran filem untuk pengguna perkhidmatan penstriman video.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Takrifan Pengesyoran produk atau Tindakan Terbaik Seterusnya

Kami mentakrifkan matlamat sebagai memaksimumkan jumlah wang untuk penggunaan perkhidmatan dengan menawarkan perkhidmatan pemadanan terbaik kepada pelanggan hotel yang sesuai dengan kepentingan mereka.

### <a name="featurization"></a>Pencirian

Seperti model pulangan pelanggan, kami menyertai ServiceCustomerID dengan CustomerID hotel untuk membina pengesyoran secara konsisten bagi setiap CustomerID.

![Pencirian model pengesyoran.](media/azure-machine-learning-model-featurization.png)

Data yang bersumberkan tiga entiti dan ciri berbeza diperolehi daripadanya. Pencirian untuk masalah pengesyoran adalah berbeza berbanding dengan senario pulangan pelanggan atau CLTV. Model pengesyoran memerlukan data input dalam bentuk tiga set ciri.

### <a name="model-selection"></a>Pemilihan model

Kami meramalkan produk atau perkhidmatan dengan menggunakan algoritma yang dipanggil **Pengesyor Kotak Padanan Latihan** untuk melatih model pengesyoran.

![Algoritma pengesyoran produk.](media/azure-machine-learning-model-recommendation-algorithm.png)

Tiga port input untuk model **Pengesyor Kotak Padanan Latihan** mengambil data penggunaan perkhidmatan latihan, penerangan pelanggan (pilihan) dan perihalan perkhidmatan. Terdapat tiga cara yang berbeza untuk pemarkahan model. Salah satu adalah untuk penilaian model markah Pulangan Terkumpul Terdiskaun Dinormalkan (NDCG) yang dikira untuk menilai item yang diberi nilai. Dalam percubaan ini, kami mempunyai skor NDCG sebagai 0.97. Dua pilihan yang lain ialah pemarkahan model pada keseluruhan katalog perkhidmatan yang boleh disyorkan atau pemarkahan hanya pada item yang tidak digunakan oleh pengguna sebelum ini.

Melihat selanjutnya mengenai pengagihan pengesyoran pada seluruh katalog perkhidmatan, kami menyedari bahawa telefon, Wi-Fi dan kurier adalah perkhidmatan yang paling utama untuk disyorkan. Ini adalah selaras dengan apa yang kami dapati daripada pengagihan data penggunaan perkhidmatan:

![Output model pengesyoran.](media/azure-machine-learning-model-output.png)

Keseluruhan [percubaan pengesyoran produk boleh diakses dalam Galeri AI Azure.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Mengintegrasikan model tersuai

Untuk menggunakan ramalan ini dalam Customer Insights, anda perlu **mengeksport** ramalan bersama dengan ID pelanggan. [Eksportkannya ke lokasi storan Blob Azure](/azure/storage/common/storage-import-export-data-from-blobs) yang anda eksport data sumber. Perkhidmatan web ramalan boleh dijadualkan berjalan secara kerap dan kemas kini skor.

Data yang dijana oleh model tersuai boleh digunakan untuk memperkaya data pelanggan anda. Untuk mendapatkan maklumat lanjut, lihat [Model pembelajaran mesin tersuai](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]