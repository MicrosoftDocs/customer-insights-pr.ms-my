---
title: Langganan panduan sampel ramalan pulangan
description: Gunakan panduan sampel ini untuk mencuba model ramalan pulangan langganan luar kotak.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 324e5c19778230dd978b2f4e9156a2dd82b3d2bd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595529"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Panduan sampel ramalan pulangan langganan (pratonton)

Kami akan menerangkan kepada anda contoh ramalan pulangan langganan hujung ke hujung menggunakan data sampel yang diberikan di bawah. 

## <a name="scenario"></a>Senario

Contoso ialah sebuah syarikat yang menghasilkan mesin kopi dan kopi berkualiti tinggi, yang mereka jual melalui laman web Contoso Coffee mereka. Mereka baru memulakan perniagaan langganan untuk pelanggan mereka untuk mendapatkan kopi secara tetap. Matlamat mereka ialah untuk memahami, pelanggan yang melanggan yang mana mungkin membatalkan langganan mereka dalam beberapa bulan akan datang. Mengetahui pelanggan mereka yang **cenderung untuk memulangkan**, boleh membantu mereka menjimatkan usaha pemasaran dengan memberikan tumpuan dalam mengekalkan mereka.

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

1. Dalam medan **Nama** pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**

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

### <a name="ingest-subscription-information"></a>Ingeskan maklumat langganan

1. Cipta sumber data bernama **SubscriptionHistory**, pilih pilihan import dan pilih penyambung **Text/CSV**.

1. Masukkan URL untuk kenalan e-dagang https://aka.ms/ciadchurnsubscriptionhistory.

1. Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:

   - **SubscriptioID**: Nombor Bulat
   - **SubscriptionAmount**: Mata Wang
   - **SubscriptionEndDate** : Tarikh/Masa
   - **SubscriptionEndDate**: Tarikh/Masa
   - **TransactionDate**: Tarikh/Masa
   - **IsRecurring**: Benar/Palsu
   - **Is_auto_renew** : Benar/Palsu
   - **RecurringFrequencyInMonths**: Nombor Bulat

1. Dalam medan **Nama** pada anak tetingkap sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **SubscriptionHistory**.

1. Simpan sumber data.

### <a name="ingest-customer-data-from-website-reviews"></a>Inges data pelanggan daripada ulasan laman web

1. Cipta sumber data bernama **Laman Web**, pilih pilihan import dan pilih penyambung **Text/CSV**.

1. Masukkan URL untuk kenalan e-dagang https://aka.ms/ciadclasswebsite.

1. Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:

   - **ReviewRating**: Nombor Bulat
   - **ReviewDate**: Tarikh

1. Dalam medan 'Nama' pada anak tetingkap sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **webReviews**.

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

1. Dalam senarai juntai bawah **Utama**, pilih **eCommerceContacts : e-Dagang** sebagai sumber utama dan menyertakan semua rekod.

1. Dalam senarai juntai bawah **Entiti 2**, pilih **loyCustomers : LoyaltyScheme** dan menyertakan semua rekod.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Menyatukan padanan e-Dagang dan Kesetiaan.":::

1. Pilih **Cipta peraturan baharu**

1. Tambah syarat pertama anda menggunakan FullName.

   * Untuk eCommerceContacts pilih **FullName** dalam senarai juntai bawah.
   * Untuk loyCustomers, pilih **FullName** dalam senarai juntai bawah.
   * Pilih senarai juntai bawah **Menormalkan** dan pilih **Jenis (Telefon, Nama, Alamat, ...)**.
   * Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.

1. Masukkan nama **FullName, Email** untuk peraturan baharu.

   * Tambah syarat kedua untuk alamat e-mel dengan memilih **Tambah Syarat**
   * Untuk entiti eCommerceContacts, pilih **EMail** dalam senarai juntai bawah.
   * Untuk entiti loyCustomers, pilih **EMail** dalam senarai juntai bawah. 
   * Biarkan Menormalkan kosong. 
   * Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Menyatukan peraturan padanan untuk nama dan e-mel.":::

7. Pilih **Simpan** dan **Jalankan**.

### <a name="merge"></a>Gabungkan

1. Pergi ke tab **Gabungan**.

1. Pada **ContactId** untuk entiti **loyCustomers**, tukar nama paparan kepada **ContactIdLOYALTY** untuk membezakannya daripada ID lain yang diinges.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="namakan semula contactid daripada ID kesetiaan.":::

1. Pilih **Simpan** dan **Jalankan** untuk memulakan Proses Gabungan.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Tugas 3 - Konfigurasikan ramalan pulangan langganan

Dengan adanya profil pelanggan disatukan, kini kami dapat menjalankan ramalan pulangan langganan. Untuk langkah terperinci, lihat artikel [Ramalan pulangan langganan (pratonton)](predict-subscription-churn.md). 

1. Pergi ke **Kecerdasan** > **Teroka** dan pilih untuk menggunakan **Model pulangan pelanggan**.

1. Pilih pilihan **Langganan** dan pilih **Mari Bermula**.

1. Namakan model **Ramalan Pulangan Langganan OOB** dan **OOBSubscriptionChurnPrediction** entiti output.

1. Takrifkan dua syarat untuk model pulangan:

   * **Hari sejak langganan tamat**: **sekurang-kurangnya 60** hari. Jika pelanggan tidak memperbaharui langganan dalam tempoh ini selepas langganan mereka tamat, mereka dianggap telah memberikan pulangan. 

   * **Definisi pulangan**: **sekurang-kurangnya 93** hari. Tempoh model meramalkan pelanggan mana yang mungkin akan memberikan pulangan. Semakin jauh masa hadapan anda melihat, semakin kurang tepat keputusan.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Pilih Tetingkap Ramalan tuil model dan Definisi Ramalan.":::

1. Pilih **Tambah data yang diperlukan** dan pilih **Tambah data** untuk sejarah langganan.

1. Tambah **Langganan: Entiti SubscriptionHistory** dan petakan medan daripada e-Dagang kepada medan berkaitan yang diperlukan oleh model.

1. Sertai **Langganan: Entiti SubscriptionHistory** dengan **eCommerceContacts : e-Dagang**, namakan hubungan **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Sertai entiti e-Dagang.":::

1. Di bawah Aktiviti Pelanggan, tambah **webReviews : Entiti Laman Web** dan petakan medan daripada webReviews kepada medan berkaitan yang diperlukan oleh model. 
   - Kunci utama: ReviewId
   - Cap waktu: ReviewDate
   - Peristiwa: ReviewRating

1. Konfigurasikan aktiviti untuk ulasan laman web. Pilih aktiviti **Ulasan** dan sertai **webReviews: Entiti laman web** dengan **eCommerceContacts: e-Dagang**.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]