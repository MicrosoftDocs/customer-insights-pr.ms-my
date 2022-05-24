---
title: Panduan sampel ramalan pengesyoran produk
description: Gunakan panduan sampel ini untuk mencuba model ramalan pengesyoran produk di luar kotak.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762697"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Panduan sampel ramalan pengesyoran produk

Kami akan menerangkan kepada anda contoh ramalan pengesyoran produk hujung ke hujung menggunakan data sampel yang diberikan di bawah.

## <a name="scenario"></a>Senario

Contoso ialah sebuah syarikat yang menghasilkan mesin kopi dan kopi berkualiti tinggi, yang mereka jual melalui laman web Contoso Coffee mereka. Matlamat mereka ialah untuk memahami produk yang sepatutnya mereka syorkan kepada pelanggan berulang mereka. Mengetahui perkara yang pelanggan lebih **mungkin akan membeli**, boleh membantu mereka menyimpan usaha pemasaran dengan menumpukan perhatian kepada perkara tertentu.

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.
- Kami mengesyorkan agar anda melaksanakan langkah berikut [dalam persekitaran baharu](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tugas 1 - Inges data

Semak artikel [mengenai pengambilan](data-sources.md) data dan [pengimportan sumber data menggunakan Power Query penyambung](connect-power-query.md) secara khusus. Maklumat berikut menganggap anda membiasakan diri dengan pengingesan data secara umum.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inges data pelanggan daripada platform e-Dagang

1. Cipta sumber data bernama **e-Dagang**, pilih pilihan import dan pilih penyambung **Teks/CSV**.

1. Masukkan URL untuk kenalan eCommerce: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **DateOfBirth**: Tarikh
   - **CreatedOn**: Zon waktu tarikh

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tarikh lahir kepada tarikh ini.":::

1. Dalam medan 'Nama' pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**

1. **Simpan** sumber data.

### <a name="ingest-online-purchase-data"></a>Inges data pembelian dalam talian

1. Tambahkan set data lain pada sumber data **e-Dagang** yang sama. Pilih penyambung **Teks/CSV** semula.

1. Masukkan URL untuk **data Pembelian** Dalam Talian [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **PurchasedOn** : Tarikh/Masa
   - **TotalPrice** : Mata Wang

1. Dalam medan **Nama** pada anak tetingkap sisi, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**.

1. **Simpan** sumber data.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingest data pelanggan daripada skema kesetiaan

1. Cipta sumber data bernama **LoyaltyScheme**, pilih pilihan import dan pilih penyambung **Teks/CSV**.

1. Masukkan URL untuk kenalan eCommerce [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **DateOfBirth**: Tarikh
   - **RewardsPoints**: Nombor Bulat
   - **CreatedOn**: Tarikh/Masa

1. Dalam medan **Nama** pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **loyCustomers**.

1. **Simpan** sumber data.

## <a name="task-2---data-unification"></a>Tugas 2 - Penyatuan data

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Tugas 3 - Mengkonfigurasikan ramalan pengesyoran produk

Dengan adanya profil pelanggan yang bersatu, kami kini boleh menjalankan cadangan produk ramalan.

1. Pergi ke **Kecerdasan** > **Ramalan** pilih **Pengesyoran produk**.

1. Pilih **Mulakan**.

1. Namakan model **Ramalan Model Pengesyoran Produk OOB** dan entiti output **OOBProductRecommendationModelPrediction**.

1. Takrifkan tiga syarat untuk model:

   - **Bilangan produk**: Tetapkan nilai ini kepada **5**. Tetapan ini mentakrifkan bilangan produk yang anda mahu cadangkan kepada pelanggan anda.

   - **Pembelian berulang dijangka**: Pilih **Ya** untuk menunjukkan bahawa anda ingin menyertakan produk dalam pengesyoran yang dibeli oleh pelanggan anda sebelum ini.

   - **Tetingkap lihat kembali:** Pilih sekurang-kurangnya **365 hari**. Tetapan ini menakrifkan sejauh mana model akan melihat kembali pada aktiviti pelanggan untuk menggunakannya sebagai input kepada pengesyoran mereka.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Keutaaman model untuk model pengesyoran produk.":::

1. Dalam langkah Tambah data **yang** diperlukan, pilih **Tambah data**.

1. **Dalam anak tetingkap Tambah data**, pilih **SalesOrderLine** sebagai entiti sejarah pembelian. Pada ketika ini, ia mungkin belum dikonfigurasikan. Buka pautan dalam anak tetingkap untuk mencipta aktiviti dengan langkah berikut:
   1. **Masukkan nama** Aktiviti dan pilih *eCommercePurchases:eCommerce* sebagai **entiti** Aktiviti. Kekunci **Utama** ialah *PurchaseId*.
   1. Tentukan dan namakan hubungan dengan *eCommerceContacts:eCommerce entiti* dan pilih **ContactId** sebagai kunci asing.
   1. Untuk penyatuan Aktiviti, tetapkan **aktiviti** Acara sebagai *TotalPrice* dan Cap Masa kepada *PurchasedOn*. Anda boleh menentukan lebih banyak medan seperti yang digariskan dalam [aktiviti](activities.md) Pelanggan.
   1. Untuk **Jenis** Aktiviti, pilih *SalesOrderLine*. Petakan medan aktiviti berikut:
      - ID baris pesanan: PurchaseId
      - ID Pesanan: PurchaseId
      - Data pesanan: PurchasedOn
      - ID Produk: ProductId
      - Amaun: TotalPrice
   1. Semak dan selesaikan aktiviti sebelum kembali ke konfigurasi model.

1. Kembali dalam **langkah Pilih aktiviti**, pilih aktiviti yang baru dibuat dalam bahagian **Aktiviti**. Pilih **Seterusnya** dan pemetaan atribut telah diisi. Pilih **Simpan**.

1. Dalam panduan sampel ini, kami melangkau **set Tambah maklumat** produk dan **penapis** Produk kerana kami tidak mempunyai data maklumat produk.

1. **Dalam langkah Kemas kini** data, tetapkan jadual model.

   Model perlu dilatih secara tetap untuk belajar pola baharu apabila terdapat data baharu yang diinges. Untuk contoh ini, pilih **Bulanan**.

1. Selepas menyemak semula semua butiran, pilih **Simpan dan Jalankan**. Ia akan mengambil masa beberapa minit untuk menjalankan model pada kali pertama.

## <a name="task-4---review-model-results-and-explanations"></a>Tugas 4 - Semak semula hasil dan penerangan model

Biarkan model melengkapkan latihan dan pemarkahan data. Anda kini boleh menyemak penerangan model pengesyoran pelanggan. Untuk mendapatkan maklumat lanjut, lihat [Semak semula status dan keputusan ramalan](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tugas 5 - Cipta segmen produk yang dibeli tinggi

Menjalankan model pengeluaran mewujudkan entiti baharu yang anda boleh lihat dalam **Data** > **Entiti**.

Anda boleh mencipta segmen baharu berdasarkan entiti yang dicipta oleh model.

1. Pergi ke **Segmen**. Pilih **Baru** dan pilih **Cipta daripada Perisikan**.

   ![Mencipta segmen dengan output model.](media/segment-intelligence.png)

1. Pilih titik tamat **OOBProductRecommendationModelPrediction** dan takrifkan segmen:

   - Medan: ProductID
   - Nilai: Pilih tiga ID produk teratas

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Cipta segmen daripada hasil model.":::

Anda kini mempunyai segmen yang dikemas kini secara dinamik yang mengenal pasti pelanggan yang mungkin berminat untuk membeli tiga produk yang paling disyorkan.

Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
