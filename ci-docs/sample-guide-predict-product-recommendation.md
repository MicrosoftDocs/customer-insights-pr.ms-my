---
title: Panduan sampel ramalan pengesyoran produk
description: Gunakan panduan sampel ini untuk mencuba model ramalan pengesyoran produk di luar kotak.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610155"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Panduan sampel ramalan pengesyoran produk

Panduan ini membimbing anda melalui contoh hujung ke hujung pengesyoran produk ramalan menggunakan data sampel. Kami mengesyorkan agar anda mencuba ramalan [ini dalam persekitaran yang baru](manage-environments.md).

## <a name="scenario"></a>Senario

Contoso adalah sebuah syarikat yang menghasilkan mesin kopi dan kopi berkualiti tinggi. Mereka menjual produk melalui laman web Contoso Coffee mereka. Matlamat mereka ialah untuk memahami produk yang sepatutnya mereka syorkan kepada pelanggan berulang mereka. Mengetahui apa yang pelanggan lebih **cenderung untuk membeli** boleh membantu mereka menjimatkan usaha pemasaran dengan memberi tumpuan kepada item tertentu.

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.

## <a name="task-1---ingest-data"></a>Tugas 1 - Inges data

Semak artikel [tentang pengingesan](data-sources.md) data dan [menyambung ke Power Query sumber data](connect-power-query.md). Maklumat berikut menganggap anda sudah biasa dengan pengambilan data secara umum.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inges data pelanggan daripada platform e-Dagang

1. Buat Power Query sumber data bernama **eCommerce** dan pilih **penyambung Teks /CSV**.

1. Masukkan URL untuk kenalan eCommerce:https://aka.ms/ciadclasscontacts.

1. Semasa mengedit data, pilih **Ubah** kemudian **Gunakan baris pertama sebagai pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **DateOfBirth**: Tarikh
   - **CreatedOn**: Zon waktu tarikh

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tarikh lahir kepada tarikh ini.":::

1. **Dalam medan Nama** pada anak tetingkap kanan, namakan semula sumber data anda kepada **eCommerceHubungi**.

1. **Simpan** sumber data.

### <a name="ingest-online-purchase-data"></a>Inges data pembelian dalam talian

1. Tambahkan set data lain pada sumber data **e-Dagang** yang sama. Pilih penyambung **Teks/CSV** semula.

1. Masukkan URL untuk data pembelian dalam talian https://aka.ms/ciadclassonline.

1. Semasa mengedit data, pilih **Ubah** kemudian **Gunakan baris pertama sebagai pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **PurchasedOn** : Tarikh/Masa
   - **TotalPrice** : Mata Wang

1. **Dalam medan Nama** pada anak tetingkap sisi, namakan semula sumber data anda kepada **eCommercePurchases**.

1. **Simpan** sumber data.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingest data pelanggan daripada skema kesetiaan

1. Buat sumber data bernama **LoyaltyScheme** dan pilih **penyambung Teks/CSV**.

1. Masukkan URL untuk pelanggan https://aka.ms/ciadclasscustomerloyalty setia.

1. Semasa mengedit data, pilih **Ubah** kemudian **Gunakan baris pertama sebagai pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **DateOfBirth**: Tarikh
   - **RewardsPoints**: Nombor Bulat
   - **CreatedOn**: Tarikh/Masa

1. **Dalam medan Nama** pada anak tetingkap kanan, namakan semula sumber data anda kepada **loyCustomers**.

1. **Simpan** sumber data.

## <a name="task-2---data-unification"></a>Tugas 2 - Penyatuan data

Semak semula artikel [tentang penyatuan](data-unification.md) data. Maklumat berikut menganggap anda sudah biasa dengan penyatuan data secara umum.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tugas 3 - Buat aktiviti sejarah transaksi

Semak artikel [mengenai aktiviti](activities.md) pelanggan. Maklumat berikut menganggap anda sudah biasa dengan membuat aktiviti secara umum.

1. Buat aktiviti yang dipanggil **eCommercePurchases** dengan *entiti eCommercePurchases:eCommerce* dan kunci utamanya, **PurchaseId**.

1. Buat hubungan antara *eCommercePurchases:eCommerce* dan *eCommerceContacts:eCommerce* dengan **ContactID** sebagai kunci asing untuk menghubungkan kedua-dua entiti.

1. Pilih **TotalPrice** untuk **EventActivity** dan **PurchasedOn** untuk **TimeStamp**.

1. Pilih **SalesOrderLine** untuk **Jenis** Aktiviti dan memetakan data aktiviti secara semantik.

1. Jalankan aktiviti tersebut.

## <a name="task-4---configure-product-recommendation-prediction"></a>Tugas 4 - Mengkonfigurasikan ramalan pengesyoran produk

Dengan profil pelanggan bersatu di tempat dan aktiviti yang dibuat, jalankan cadangan produk ramalan.

1. Pergi ke **Ramalan** > **Perisikan**.

1. Pada tab **Cipta**, pilih **Gunakan model** pada **jubin Cadangan produk (pratonton**).

1. Pilih **Mulakan**.

1. Namakan model **Ramalan Model Pengesyoran Produk OOB** dan entiti output **OOBProductRecommendationModelPrediction**.

1. Pilih **Seterusnya**.

1. Tentukan keutamaan model:
   - **Bilangan produk**: **5** untuk menentukan berapa banyak produk yang ingin anda cadangkan kepada pelanggan anda.
   - **Pembelian berulang dijangka**: **Ya** untuk memasukkan produk yang dibeli sebelum ini dalam cadangan.
   - **Lihat kembali tetingkap:** **365 hari** untuk menentukan sejauh mana model akan melihat ke belakang sebelum mengesyorkan produk lagi.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Keutaaman model untuk model pengesyoran produk.":::

1. Pilih **Seterusnya**.

1. **Dalam langkah Tambah sejarah** pembelian, pilih **Tambah data**.

1. Pilih **SalesOrderLine** dan entiti eCommercePurchases dan pilih **Seterusnya**. Data yang diperlukan diisi secara automatik daripada aktiviti tersebut. Pilih **Simpan** dan kemudian **Seterusnya**.

1. **Langkau langkah Tambah maklumat** produk dan **penapis** produk kerana kami tidak mempunyai data maklumat produk.

1. **Dalam langkah Kemas kini data**, pilih **Bulanan** untuk jadual model.

1. Pilih **Seterusnya**.

1. Selepas menyemak semula semua butiran, pilih **Simpan dan Jalankan**.

## <a name="task-5---review-model-results-and-explanations"></a>Tugas 5 - Semak semula hasil dan penerangan model

Biarkan model melengkapkan latihan dan pemarkahan data. [Semak penjelasan](predict-transactional-churn.md#view-prediction-results) model cadangan produk.

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Tugas 6 - Cipta segmen produk yang dibeli tinggi

Menjalankan model mencipta entiti baharu, yang disenaraikan pada **Data** > **Entiti**. Anda boleh mencipta segmen baharu berdasarkan entiti yang dicipta oleh model.

1. Pada halaman hasil, pilih **Cipta segmen**.

1. Buat peraturan menggunakan **entiti OOBProductRecommendationModelPrediction** dan tentukan segmen:
   - **Bidang**: ProductID
   - **Nilai**: Pilih tiga ID produk teratas

1. Pilih **Simpan** dan **Jalankan** segmen.

Anda kini mempunyai segmen yang dikemas kini secara dinamik yang mengenal pasti pelanggan yang mungkin berminat untuk membeli lima produk yang paling disyorkan. Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).

> [!TIP]
> Anda juga boleh mencipta segmen untuk model ramalan daripada **halaman Segmen** dengan **memilih Baharu** dan memilih **Cipta daripada** > **Kecerdasan**. Untuk maklumat lanjut, lihat [Mencipta segmen baharu dengan segmen](segment-quick.md) pantas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
