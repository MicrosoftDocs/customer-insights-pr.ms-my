---
title: Panduan sampel ramalan pulangan transaksi
description: Gunakan panduan sampel ini untuk mencuba model ramalan pulangan transaksi luar kotak.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741330"
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

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Tugas 3 - Konfigurasikan ramalan pulangan transaksi

Dengan profil pelanggan yang bersatu, kita kini boleh menjalankan transaksi churn ramalan. Untuk langkah terperinci, lihat [artikel transaksi ramalan](predict-transactional-churn.md). 

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

Biarkan model melengkapkan latihan dan pemarkahan data. Anda kini boleh menyemak penjelasan model churn. Untuk mendapatkan maklumat lanjut, lihat [Semak semula status dan keputusan ramalan](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tugas 5 - Cipta segmen pelanggan risiko pulangan tinggi

Menjalankan model pengeluaran mewujudkan entiti baharu yang anda boleh lihat dalam **Data** > **Entiti**.   

Anda boleh mencipta segmen baharu berdasarkan entiti yang dicipta oleh model.

1.  Pergi ke **Segmen**. Pilih **Baharu** dan pilih **Cipta daripada** > **Kecerdasan**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Mencipta segmen dengan output model.":::

1. **Pilih titik akhir OOBeCommerceChurnPrediction** dan tentukan segmen: 
   - Medan: ChurnScore
   - Operator: lebih daripada
   - Nilai: 0.6

Anda kini mempunyai segmen yang dikemas kini secara dinamik yang mengenal pasti pelanggan berisiko tinggi.

Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
