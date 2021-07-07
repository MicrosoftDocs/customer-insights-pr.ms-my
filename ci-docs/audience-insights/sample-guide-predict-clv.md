---
title: Panduan sampel ramalan nilai sepanjang hayat pelanggan
description: Gunakan panduan sampel ini untuk mencuba model ramalan nilai sepanjang hayat pelanggan.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306360"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Panduan sampel ramalan nilai sepanjang hayat pelanggan (CLV)

Panduan ini akan menerangkan kepada anda contoh akhir ramalan nilai sepanjang hayat Pelanggan (CLV) dalam Customer Insights menggunakan data sampel.

## <a name="scenario"></a>Senario

Contoso ialah sebuah syarikat yang menghasilkan mesin kopi dan kopi berkualiti tinggi. Mereka menjual produk melalui laman web Contoso Coffee mereka. Syarikat ingin memahami nilai (hasil) yang boleh dijana oleh pelanggan mereka dalam tempoh 12 bulan akan datang. Mengetahui nilai yang diharapkan pelanggan mereka dalam tempoh 12 bulan akan datang akan membantu mereka mengemudi usaha pemasaran mereka ke atas pelanggan bernilai tinggi.

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam cerapan khalayak.
- Kami mengesyorkan agar anda melaksanakan langkah berikut [dalam persekitaran baharu](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tugas 1 - Inges data

Semak artikel [tentang pengingesan data](data-sources.md) dan [mengimport sumber data menggunakan penyambung Power Query](connect-power-query.md). Maklumat berikut menganggap anda membiasakan diri dengan pengingesan data secara umum.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inges data pelanggan daripada platform e-Dagang

1. Cipta sumber data bernama **e-Dagang**, pilih pilihan import dan pilih penyambung **Teks/CSV**.

1. Masukkan URL untuk kenalan e-Dagang [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Semasa mengedit data, pilih **Ubah** dan kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **DateOfBirth**: Tarikh
   - **CreatedOn**: Zon waktu tarikh

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tarikh lahir kepada tarikh ini.":::

1. Dalam medan 'Nama' pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**

1. **Simpan** sumber data.

### <a name="ingest-online-purchase-data"></a>Inges data pembelian dalam talian

1. Tambahkan set data lain pada sumber data **e-Dagang** yang sama. Pilih penyambung **Teks/CSV** semula.

1. Masukkan URL untuk data **Pembelian Dalam Talian** https://aka.ms/ciadclassonline.

1. Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **PurchasedOn** : Tarikh/Masa
   - **TotalPrice** : Mata Wang

1. Dalam medan **Nama** pada anak tetingkap sisi, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**.

1. **Simpan** sumber data.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingest data pelanggan daripada skema kesetiaan

1. Cipta sumber data bernama **LoyaltyScheme**, pilih pilihan import dan pilih penyambung **Teks/CSV**.

1. Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscustomerloyalty.

1. Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **DateOfBirth**: Tarikh
   - **RewardsPoints**: Nombor Bulat
   - **CreatedOn**: Tarikh/Masa

1. Dalam medan **Nama** pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **loyCustomers**.

1. **Simpan** sumber data.

### <a name="ingest-customer-data-from-website-reviews"></a>Inges data pelanggan daripada ulasan laman web

1. Cipta sumber data bernama **Laman Web**, pilih pilihan import dan pilih penyambung **Text/CSV**.

1. Masukkan URL untuk kenalan e-Dagang https://aka.ms/CI-ILT/WebReviews.

1. Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:

   - **ReviewRating**: Nombor perpuluhan
   - **ReviewDate**: Tarikh

1. Dalam medan 'Nama' pada anak tetingkap sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **Ulasan**.

1. **Simpan** sumber data.

## <a name="task-2---data-unification"></a>Tugas 2 - Penyatuan data

Selepas pengingesan data, kami kini memulakan proses penyatuan data untuk mencipta profil pelanggan yang disatukan. Untuk mendapatkan maklumat lanjut, lihat [Penyatuan data](data-unification.md).

### <a name="map"></a>Petakan

1. Selepas menginges data, petakan kenalan daripada data e-Dagang dan Kesetiaan kepada jenis data umum. Pergi ke **Data** > **Satukan** > **Peta**.

1. Pilih entiti yang mewakili profil pelanggan – **eCommerceContacts** dan **loyCustomers**. Kemudian, pilih **Guna**.

   ![menyatukan sumber data e-Dagang dan kesetiaan.](media/unify-ecommerce-loyalty.png)

1. Pilih **ContactId** sebagai kunci utama untuk **eCommerceContacts** dan **LoyaltyID** sebagai kunci utama untuk **loyCustomers**.

   ![Menyatukan LoyaltyId sebagai kunci utama.](media/unify-loyaltyid.png)

1. Pilih **Simpan**.

### <a name="match"></a>Padankan

1. Pergi ke tab **Padanan** dan pilih **Tetapkan Urutan**.

1. Dalam senarai juntai bawah **Utama**, pilih **eCommerceContacts : eCommerce** sebagai sumber utama dan sertakan semua rekod.

1. Dalam senarai juntai bawah **Entiti 2**, pilih **loyCustomers : LoyaltyScheme** dan sertakan semua rekod.

   ![Menyatukan padanan e-Dagang dan Kesetiaan.](media/unify-match-order.png)

1. Pilih **Tambah peraturan**

1. Tambah syarat pertama anda menggunakan FullName.

   - Untuk eCommerceContacts pilih **FullName** dalam menu juntai bawah.
   - Untuk loyCustomers pilih **FullName** dalam menu juntai bawah.
   - Pilih juntai bawah **Menormalkan** dan pilih **Jenis (Telefon, Nama, Alamat,...)**.
   - Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.

1. Masukkan nama **FullName, Email** untuk peraturan baharu.

   - Tambah syarat kedua untuk alamat e-mel dengan memilih **Tambah Syarat**
   - Untuk entiti eCommerceContacts, pilih **EMail** dalam menu juntai bawah.
   - Untuk entiti loyCustomers, pilih **EMail** dalam menu juntai bawah.
   - Biarkan Menormalkan kosong.
   - Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.

   ![Menyatukan peraturan padanan untuk nama dan e-mel.](media/unify-match-rule.png)

1. Pilih **Selesai**.

1. Pilih **Simpan** dan **Jalankan**.

### <a name="merge"></a>Gabungkan

1. Pergi ke tab **Gabungan**.

1. Pada **ContactId** untuk entiti **loyCustomers**, tukar nama paparan kepada **ContactIdLOYALTY** untuk membezakannya daripada ID lain yang diinges.

   ![namakan semula contactid daripada ID kesetiaan.](media/unify-merge-contactid.png)

1. Pilih **Simpan** dan **Jalankan proses gabungan dan hiliran**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Tugas 3 - Konfigurasi ramalan nilai sepanjang hayat pelanggan

Dengan profil pelanggan yang disatukan ditetapkan, kami kini boleh menjalankan ramalan nilai sepanjang hayat pelanggan. Untuk langkah-langkah terperinci, lihat [Ramalan Nilai Sepanjang Hayat (pratonton)](predict-customer-lifetime-value.md).

1. Pergi ke **Kecerdasan**  > **Ramalan** dan pilih **Model nilai sepanjang hayat pelanggan**.

1. Pergi melalui maklumat dalam anak tetingkap sisi dan pilih **Mari Bermula**.

1. Namakan model **Ramalan OOB eCommerce CLV** dan entiti output **OOBeCommerceCLVPrediction**.

1. Tentukan keutamaan model untuk model CLV:
   - **Tempoh masa ramalan**: **12 bulan atau 1 tahun**. Tetapan ini menentukan sejauh mana masa depan untuk meramalkan nilai sepanjang hayat pelanggan.
   - **Pelanggan aktif**: Tentukan maksud pelanggan aktif untuk perniagaan anda. Tetapkan tempoh masa sejarah yang pelanggan mesti mempunyai sekurang-kurangnya satu transaksi untuk dianggap aktif. Model hanya akan meramalkan CLV untuk pelanggan aktif. Pilih antara membiarkan model mengira tempoh masa berdasarkan data transaksi sejarah atau berikan tempoh masa tertentu. Dalam panduan sampel ini, kami **membiarkan model mengira selang pembelian**, yang merupakan pilihan lalai.
   - **Pelanggan bernilai tinggi**: Tentukan pelanggan bernilai tinggi sebagai seperseratusan pelanggan teratas yang membayar. Model menggunakan input ini untuk memberikan hasil yang sesuai dengan definisi perniagaan pelanggan bernilai tinggi anda. Anda boleh memilih untuk membiarkan model menentukan pelanggan bernilai tinggi. Ia menggunakan peraturan heuristik yang menjumlahkan seperseratusan. Anda juga boleh menentukan pelanggan bernilai tinggi sebagai seperseratusan pelanggan teratas yang membayar pada masa depan. Dalam panduan sampel ini, kami menentukan pelanggan bernilai tinggi secara manual sebagai **30% teratas pelanggan yang aktif membayar** dan pilih **Seterusnya**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Keutamaan melangkah dalam pengalaman berpandu untuk model CLV.":::

1. Dalam langkah **Data yang Diperlukan**, pilih **Tambah data** untuk menyediakan data sejarah transaksi.

1. Tambah entiti **eCommercePurchases: e-Dagang** dan petakan atribut yang diperlukan oleh model:
   - ID transaksi: eCommerce.eCommercePurchases.PurchaseId
   - Tarikh transaksi: eCommerce.eCommercePurchases.PurchasedOn
   - Amaun transaksi: eCommerce.eCommercePurchases.TotalPrice
   - ID produk: eCommerce.eCommercePurchases.ProductId

1. Pilih **Seterusnya**.

1. Sediakan perhubungan antara entiti **eCommercePurchases: eCommerce** dengan **eCommerceContacts: eCommerce**.

1. Langkah **Data tambahan (pilihan)** membolehkan anda menambah lebih banyak data aktiviti pelanggan. Data ini boleh membantu untuk mendapatkan lebih banyak cerapan untuk interaksi pelanggan dengan perniagaan anda, yang boleh menyumbang kepada CLV. Menambah interaksi pelanggan utama seperti log web, log khidmat pelanggan atau sejarah program ganjaran boleh meningkatkan ketepatan ramalan. Pilih **Tambah data** untuk menyertakan lebih banyak data aktiviti pelanggan.

1. Tambah entiti aktiviti pelanggan dan petakan nama medan ke medan sepadan yang diperlukan oleh model:
   - Entiti aktiviti pelanggan: Reviews:Website
   - Kunci utama: Website.Reviews.ReviewId
   - Cap masa: Website.Reviews.ReviewDate
   - Peristiwa (nama aktiviti): Website.Reviews.ActivityTypeDisplay
   - Butiran (amaun atau nilai): Website.Reviews.ReviewRating

1. Pilih **Seterusnya** dan konfigurasikan aktiviti dan perhubungan antara data transaksi dengan data pelanggan:  
   - Jenis aktiviti: Pilih yang sedia ada
   - Label aktiviti: Semak
   - Label yang sepadan: Website.Reviews.UserId
   - Entiti pelanggan: eCommerceContacts:eCommerce
   - Perhubungan: WebsiteReviews

1. Pilih **Seterusnya** untuk menetapkan jadual model.

   Model perlu melatih dengan kerap untuk mempelajari corak baharu apabila terdapat data baharu yang diinges. Untuk contoh ini, pilih **Bulanan**.

1. Selepas menyemak semula semua butiran, pilih **Simpan dan Jalankan**.

## <a name="task-4---review-model-results-and-explanations"></a>Tugas 4 - Semak semula hasil dan penerangan model

Biarkan model melengkapkan latihan dan pemarkahan data. Seterusnya, anda boleh menyemak hasil dan penjelasan model CLV. Untuk mendapatkan maklumat lanjut, lihat [Semak semula status dan keputusan ramalan](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Tugas 5 - Cipta segmen pelanggan bernilai tinggi

Menjalankan model mencipta entiti baharu, yang disenaraikan pada **Data** > **Entiti**. Anda boleh mencipta segmen pelanggan baharu berdasarkan entiti yang dicipta oleh model.

1. Pergi ke **Segmen**. 

1. Pilih **Baharu** dan pilih **Cipta daripada** > **Kecerdasan**.

   ![Mencipta segmen dengan output model.](media/segment-intelligence.png)

1. Pilih entiti **OOBeCommerceCLVPrediction** dan tentukan segmen:
  - Medan: CLVScore
  - Operator: lebih daripada
  - Nilai: 1500

1. Pilih **Semak** dan **Simpan** segmen.

Anda kini mempunyai segmen yang mengenal pasti pelanggan yang diramalkan untuk menjana lebih daripada $1500 pendapatan dalam tempoh 12 bulan akan datang. Segmen ini akan dikemas kini secara dinamik jika lebih banyak data diinges.

Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).