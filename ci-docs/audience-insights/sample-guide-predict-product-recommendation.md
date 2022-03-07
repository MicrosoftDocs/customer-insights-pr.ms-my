---
title: Panduan sampel ramalan pengesyoran produk
description: Gunakan panduan sampel ini untuk mencuba model ramalan pengesyoran produk di luar kotak.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595284"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Panduan sampel untuk ramalan pengesyoran produk (pratonton)

Kami akan menerangkan kepada anda contoh ramalan pengesyoran produk hujung ke hujung menggunakan data sampel yang diberikan di bawah.

## <a name="scenario"></a>Senario

Contoso ialah sebuah syarikat yang menghasilkan mesin kopi dan kopi berkualiti tinggi, yang mereka jual melalui laman web Contoso Coffee mereka. Matlamat mereka ialah untuk memahami produk yang sepatutnya mereka syorkan kepada pelanggan berulang mereka. Mengetahui perkara yang pelanggan lebih **mungkin akan membeli**, boleh membantu mereka menyimpan usaha pemasaran dengan menumpukan perhatian kepada perkara tertentu.

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.
- Kami mengesyorkan agar anda melaksanakan langkah berikut [dalam persekitaran baharu](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tugas 1 - Inges data

Semak semula artikel [tentang pengingesan data](data-sources.md) dan [mengimport sumber data menggunakan penyambung Power Query](connect-power-query.md) secara khusus. Maklumat berikut menganggap anda membiasakan diri dengan pengingesan data secara umum.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inges data pelanggan daripada platform e-Dagang

1. Cipta sumber data bernama **e-Dagang**, pilih pilihan import dan pilih penyambung **Teks/CSV**.

1. Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscontacts.

1. Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **DateOfBirth**: Tarikh
   - **CreatedOn**: Zon waktu tarikh

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tarikh lahir kepada tarikh ini.":::

5. Dalam medan 'Nama' pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**

6. **Simpan** sumber data.

### <a name="ingest-online-purchase-data"></a>Inges data pembelian dalam talian

1. Tambahkan set data lain pada sumber data **e-Dagang** yang sama. Pilih penyambung **Teks/CSV** semula.

1. Masukkan URL untuk data **Pembelian Dalam Talian** https://aka.ms/ciadclassonline.

1. Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **PurchasedOn** : Tarikh/Masa
   - **TotalPrice** : Mata Wang

1. Dalam medan **Nama** pada anak tetingkap sisi, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**.

1. Simpan sumber data.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingest data pelanggan daripada skema kesetiaan

1. Cipta sumber data bernama **LoyaltyScheme**, pilih pilihan import dan pilih penyambung **Teks/CSV**.

1. Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscustomerloyalty.

1. Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **DateOfBirth**: Tarikh
   - **RewardsPoints**: Nombor Bulat
   - **CreatedOn**: Tarikh/Masa

1. Dalam medan **Nama** pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **loyCustomers**.

1. Simpan sumber data.

## <a name="task-2---data-unification"></a>Tugas 2 - Penyatuan data

Selepas menginges data, kini kita memulakan proses **Petaan, Padanan, Gabungan** untuk mencipta profil pelanggan disatukan. Untuk mendapatkan maklumat lanjut, lihat [Penyatuan data](data-unification.md).

### <a name="map"></a>Petakan

1. Selepas menginges data, petakan kenalan daripada data e-Dagang dan Kesetiaan kepada jenis data umum. Pergi ke **Data** > **Satukan** > **Peta**.

2. Pilih entiti yang mewakili profil pelanggan – **eCommerceContacts** dan **loyCustomers**.

   ![menyatukan sumber data e-Dagang dan kesetiaan.](media/unify-ecommerce-loyalty.png)

3. Pilih **ContactId** sebagai kunci utama untuk **eCommerceContacts** dan **LoyaltyID** sebagai kunci utama untuk **loyCustomers**.

   ![Menyatukan LoyaltyId sebagai kunci utama.](media/unify-loyaltyid.png)

### <a name="match"></a>Padankan

1. Pergi ke tab **Padanan** dan pilih **Tetapkan Urutan**.

2. Dalam senarai juntai bawah **Utama**, pilih **eCommerceContacts : e-Dagang** sebagai sumber utama dan menyertakan semua rekod.

3. Dalam senarai juntai bawah **Entiti 2**, pilih **loyCustomers : LoyaltyScheme** dan menyertakan semua rekod.

   ![Menyatukan padanan e-Dagang dan Kesetiaan.](media/unify-match-order.png)

4. Pilih **Cipta peraturan baharu**

5. Tambah syarat pertama anda menggunakan FullName.

   - Untuk eCommerceContacts pilih **FullName** dalam senarai juntai bawah.
   - Untuk loyCustomers, pilih **FullName** dalam senarai juntai bawah.
   - Pilih senarai juntai bawah **Menormalkan** dan pilih **Jenis (Telefon, Nama, Alamat, ...)**.
   - Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.

6. Masukkan nama **FullName, Email** untuk peraturan baharu.

   - Tambah syarat kedua untuk alamat e-mel dengan memilih **Tambah Syarat**
   - Untuk entiti eCommerceContacts, pilih **EMail** dalam senarai juntai bawah.
   - Untuk entiti loyCustomers, pilih **EMail** dalam senarai juntai bawah.
   - Biarkan Menormalkan kosong.
   - Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.

   ![Menyatukan peraturan padanan untuk nama dan e-mel.](media/unify-match-rule.png)

7. Pilih **Simpan** dan **Jalankan**.

### <a name="merge"></a>Gabungkan

1. Pergi ke tab **Gabungan**.

1. Pada **ContactId** untuk entiti **loyCustomers**, tukar nama paparan kepada **ContactIdLOYALTY** untuk membezakannya daripada ID lain yang diinges.

   ![namakan semula contactid daripada ID kesetiaan.](media/unify-merge-contactid.png)

1. Pilih **Simpan** dan **Jalankan** untuk memulakan Proses Gabungan.

## <a name="task-3---configure-product-recommendation-prediction"></a>Tugas 3 - Mengkonfigurasikan ramalan pengesyoran produk

Dengan adanya profil pelanggan disatukan, kini kami dapat menjalankan ramalan pulangan langganan.

1. Pergi ke **Kecerdasan** > **Ramalan** pilih **Pengesyoran produk**.

1. Pilih **Mulakan**.

1. Namakan model **Ramalan Model Pengesyoran Produk OOB** dan entiti output **OOBProductRecommendationModelPrediction**.

1. Takrifkan tiga syarat untuk model:

   - **Bilangan produk**: Tetapkan nilai ini kepada **5**. Tetapan ini mentakrifkan bilangan produk yang anda mahu cadangkan kepada pelanggan anda.

   - **Cadangkan pelanggan produk yang dibeli baru-baru ini?**: Pilih **Ya** untuk menunjukkan bahawa anda mahu sertakan produk dalam pengesyoran yang pelanggan anda telah beli sebelum ini.

   - **Tetingkap lihat kembali:** Pilih sekurang-kurangnya **365 hari**. Tetapan ini menakrifkan sejauh mana model akan melihat kembali pada aktiviti pelanggan untuk menggunakannya sebagai input kepada pengesyoran mereka.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Keutaaman model untuk model pengesyoran produk.":::

1. Pilih **Data yang diperlukan** dan pilih **Tambah data** untuk sejarah pembelian.

1. Tambah entiti **eCommercePurchases : e-Dagang** dan petakan medan daripada e-Dagang kepada medan berkaitan yang diperlukan oleh model.

1. Sertai entiti **eCommercePurchases : e-Dagang** dengan **eCommerceContacts : e-Dagang**.

   ![Sertai entiti e-Dagang.](media/model-purchase-join.png)

1. Pilih **Seterusnya** untuk menetapkan jadual model.

   Model perlu dilatih secara tetap untuk belajar pola baharu apabila terdapat data baharu yang diinges. Untuk contoh ini, pilih **Bulanan**.

1. Selepas menyemak semula semua butiran, pilih **Simpan dan Jalankan**.


## <a name="task-4---review-model-results-and-explanations"></a>Tugas 4 - Semak semula hasil dan penerangan model

Biarkan model melengkapkan latihan dan pemarkahan data. Anda kini boleh menyemak penerangan model pengesyoran pelanggan. Untuk mendapatkan maklumat lanjut, lihat [Semak semula status dan keputusan ramalan](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tugas 5 - Cipta segmen produk yang dibeli tinggi

Menjalankan model pengeluaran mewujudkan entiti baharu yang anda boleh lihat dalam **Data** > **Entiti**.

Anda boleh mencipta segmen baharu berdasarkan entiti yang dicipta oleh model.

1. Pergi ke **Segmen**. Pilih **Baharu** dan pilih **Cipta daripada** > **Kecerdasan**.

   ![Mencipta segmen dengan output model.](media/segment-intelligence.png)

1. Pilih titik tamat **OOBProductRecommendationModelPrediction** dan takrifkan segmen:

   - Medan: ProductID
   - Operatori: Nilai
   - Nilai: Pilih tiga ID produk teratas

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Cipta segmen daripada hasil model.":::

Anda kini mempunyai segmen yang secara dinamik dikemas kini yang mengenal pasti pelanggan yang lebih bersedia untuk membeli tiga produk paling disyorkan 

Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]