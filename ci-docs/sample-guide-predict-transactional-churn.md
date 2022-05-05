---
title: Panduan sampel ramalan pulangan transaksi
description: Gunakan panduan sampel ini untuk mencuba model ramalan pulangan transaksi luar kotak.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 05c221c634b8e0f582a6c6d3f4d90e971aa9707e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643747"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Panduan sampel ramalan pulangan transaksi

Panduan ini akan menerangkan kepada anda contoh menyeluruh ramalan Pulangan Transaksi dalam Customer Insights menggunakan data yang disediakan di bawah. Semua data yang digunakan dalam panduan ini bukan data pelanggan sebenar dan merupakan sebahagian daripada set data Contoso yang ditemui dalam persekitaran *Demo* dalam Langganan Customer Insights anda.

## <a name="scenario"></a>Senario

Contoso ialah sebuah syarikat yang menghasilkan mesin kopi dan kopi berkualiti tinggi, yang mereka jual melalui laman web Contoso Coffee mereka. Matlamat mereka adalah untuk mengetahui pelanggan yang biasanya membeli produk mereka secara tetap, akan berhenti menjadi pelanggan aktif dalam masa 60 hari akan datang. Mengetahui pelanggan mereka yang **cenderung untuk memulangkan**, boleh membantu mereka menjimatkan usaha pemasaran dengan memberikan tumpuan dalam mengekalkan mereka.

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.
- Kami mengesyorkan agar anda melaksanakan langkah berikut [dalam persekitaran baharu](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tugas 1 - Inges data

Semak artikel [mengenai pengambilan](data-sources.md) data dan [pengimportan sumber data menggunakan Power Query penyambung](connect-power-query.md) secara khusus. Maklumat berikut menganggap anda membiasakan diri dengan pengingesan data secara umum. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inges data pelanggan daripada platform e-Dagang

1. Cipta sumber data bernama **e-Dagang**, pilih pilihan import dan pilih penyambung **Teks/CSV**.

1. Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscontacts.

1. Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:

   - **DateOfBirth**: Tarikh
   - **CreatedOn**: Zon waktu tarikh

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Tukar Tarikh Lahir kepada Tarikh.":::

1. Dalam medan **Nama** pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**

1. Simpan sumber data.

### <a name="ingest-online-purchase-data"></a>Inges data pembelian dalam talian

1. Tambahkan set data lain pada sumber data **e-Dagang** yang sama. Pilih penyambung **Teks/CSV** semula.

1. Masukkan URL untuk data **Pembelian Dalam Talian** https://aka.ms/ciadclassonline.

1. Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:

   - **PurchasedOn** : Tarikh/Masa
   - **TotalPrice** : Mata Wang
   
1. Dalam medan **Nama** pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**.

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

1. Pilih entiti yang mewakili profil pelanggan – **eCommerceContacts** dan **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="menyatukan sumber data e-Dagang dan kesetiaan.":::

1. Pilih **ContactId** sebagai kunci utama untuk **eCommerceContacts** dan **LoyaltyID** sebagai kunci utama untuk **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Menyatukan LoyaltyId sebagai kunci utama.":::

### <a name="match"></a>Padankan

1. Pergi ke tab **Padanan** dan pilih **Tetapkan Urutan**.

1. Dalam senarai juntai bawah **Utama**, pilih **eCommerceContacts : eCommerce** sebagai sumber utama dan sertakan semua rekod.

1. Dalam senarai juntai bawah **Entiti 2**, pilih **loyCustomers : LoyaltyScheme** dan sertakan semua rekod.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Menyatukan padanan e-Dagang dan Kesetiaan.":::

1. Pilih **Cipta peraturan baharu**

1. Tambah syarat pertama anda menggunakan FullName.

   * Untuk eCommerceContacts pilih **FullName** dalam menu juntai bawah.
   * Untuk loyCustomers pilih **FullName** dalam menu juntai bawah.
   * Pilih senarai juntai bawah **Menormalkan** dan pilih **Jenis (Telefon, Nama, Alamat, ...)**.
   * Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.

1. Masukkan nama **FullName, Email** untuk peraturan baharu.

   * Tambah syarat kedua untuk alamat e-mel dengan memilih **Tambah Syarat**
   * Untuk entiti eCommerceContacts, pilih **EMail** dalam menu juntai bawah.
   * Untuk entiti loyCustomers, pilih **EMail** dalam menu juntai bawah. 
   * Biarkan Menormalkan kosong. 
   * Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Menyatukan peraturan padanan untuk nama dan e-mel.":::

7. Pilih **Simpan** dan **Jalankan**.

### <a name="merge"></a>Gabungkan

1. Pergi ke tab **Gabungan**.

1. Pada **ContactId** untuk entiti **loyCustomers**, tukar nama paparan kepada **ContactIdLOYALTY** untuk membezakannya daripada ID lain yang diinges.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="namakan semula contactid daripada ID kesetiaan.":::

1. Pilih **Simpan** dan **Jalankan** untuk memulakan Proses Gabungan.



## <a name="task-3---configure-transaction-churn-prediction"></a>Tugas 3 - Konfigurasikan ramalan pulangan transaksi

Dengan adanya profil pelanggan disatukan, kini kami dapat menjalankan ramalan pulangan langganan. Untuk langkah terperinci, lihat [artikel ramalan](predict-subscription-churn.md) churn langganan. 

1. Pergi ke **Kecerdasan** > **Teroka** dan pilih untuk menggunakan **Model pulangan pelanggan**.

1. Pilih pilihan **Transaksi** dan pilih **Mari bermula**.

1. Namakan model **Ramalan Pulangan Transaksi e-Dagang OOB** dan entiti output **OOBeCommerceChurnPrediction**.

1. Takrifkan dua syarat untuk model pulangan:

   * **Tetingkap ramalan** : **sekurang-kurangnya 60** hari. Tetapan ini mentakrifkan sejauh mana kita ingin meramalkan pulangan pelanggan pada masa hadapan.

   * **Takrif pulangan** : **sekurang-kurangnya 60** hari. Tempoh tanpa pembelian selepas itu, pelanggan dianggap membuat pulangan.

     :::image type="content" source="media/model-levers.PNG" alt-text="Pilih tuil model Tetingkap Ramalan dan Takrifan Pulangan.":::

1. Pilih **Sejarah Pembelian (diperlukan)** dan pilih **Tambah data** untuk sejarah pembelian.

1. Tambah entiti **eCommercePurchases : e-Dagang** dan petakan medan daripada e-Dagang kepada medan berkaitan yang diperlukan oleh model.

1. Sertai entiti **eCommercePurchases : e-Dagang** dengan **eCommerceContacts : e-Dagang**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Sertai entiti e-Dagang.":::

1. Pilih **Seterusnya** untuk menetapkan jadual model.

   Model perlu dilatih secara tetap untuk belajar pola baharu apabila terdapat data baharu yang diinges. Untuk contoh ini, pilih **Bulanan**.

1. Selepas menyemak semula semua butiran, pilih **Simpan dan Jalankan**.

## <a name="task-4---review-model-results-and-explanations"></a>Tugas 4 - Semak semula hasil dan penerangan model

Biarkan model melengkapkan latihan dan pemarkahan data. Anda kini boleh menyemak semula penerangan model pulangan langganan. Untuk mendapatkan maklumat lanjut, lihat [Semak semula status dan keputusan ramalan](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tugas 5 - Cipta segmen pelanggan risiko pulangan tinggi

Menjalankan model pengeluaran mewujudkan entiti baharu yang anda boleh lihat dalam **Data** > **Entiti**.   

Anda boleh mencipta segmen baharu berdasarkan entiti yang dicipta oleh model.

1.  Pergi ke **Segmen**. Pilih **Baharu** dan pilih **Cipta daripada** > **Kecerdasan**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Mencipta segmen dengan output model.":::

1. Pilih titik tamat **OOBSubscriptionChurnPrediction** dan takrifkan segmen: 
   - Medan: ChurnScore
   - Operator: lebih daripada
   - Nilai: 0.6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Sediakan segmen pulangan langganan.":::

Kini anda mempunyai segmen yang dikemas kini secara dinamik yang mengenal pasti pelanggan risiko pulangan tinggi untuk perniagaan langganan ini.

Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
