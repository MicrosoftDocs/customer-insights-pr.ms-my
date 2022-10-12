---
title: Panduan sampel ramalan nilai sepanjang hayat pelanggan (CLV)
description: Gunakan panduan sampel ini untuk mencuba model ramalan nilai sepanjang hayat pelanggan.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609649"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Panduan sampel ramalan nilai sepanjang hayat pelanggan (CLV)

Panduan ini membimbing anda melalui contoh hujung ke hujung nilai seumur hidup Pelanggan (CLV) ramalan dalam Wawasan Pelanggan menggunakan data sampel. Kami mengesyorkan agar anda mencuba ramalan [ini dalam persekitaran yang baru](manage-environments.md).

## <a name="scenario"></a>Senario

Contoso adalah sebuah syarikat yang menghasilkan mesin kopi dan kopi berkualiti tinggi. Mereka menjual produk melalui laman web Contoso Coffee mereka. Syarikat ingin memahami nilai (hasil) yang boleh dijana oleh pelanggan mereka dalam tempoh 12 bulan akan datang. Mengetahui nilai yang diharapkan pelanggan mereka dalam tempoh 12 bulan akan datang akan membantu mereka mengemudi usaha pemasaran mereka ke atas pelanggan bernilai tinggi.

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md).

## <a name="task-1---ingest-data"></a>Tugas 1 - Inges data

Semak artikel [tentang pengingesan](data-sources.md) data dan [menyambung ke Power Query sumber data](connect-power-query.md). Maklumat berikut menganggap anda sudah biasa dengan pengambilan data secara umum.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inges data pelanggan daripada platform e-Dagang

1. Buat Power Query sumber data bernama **eCommerce** dan pilih **penyambung Teks /CSV**.

1. Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscontacts.

1. Semasa mengedit data, pilih **Ubah** kemudian **Gunakan baris pertama sebagai pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **DateOfBirth**: Tarikh
   - **CreatedOn**: Zon waktu tarikh

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tarikh lahir kepada tarikh ini.":::

1. **Dalam medan Nama** pada anak tetingkap kanan, namakan semula sumber data anda kepada **eCommerceHubungi**

1. **Simpan** sumber data.

### <a name="ingest-online-purchase-data"></a>Inges data pembelian dalam talian

1. Tambahkan set data lain pada sumber data **e-Dagang** yang sama. Pilih penyambung **Teks/CSV** semula.

1. Masukkan URL untuk data **Pembelian Dalam Talian** https://aka.ms/ciadclassonline.

1. Semasa mengedit data, pilih **Ubah** kemudian **Gunakan baris pertama sebagai pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **PurchasedOn** : Tarikh/Masa
   - **TotalPrice** : Mata Wang

1. **Dalam medan Nama** pada anak tetingkap sisi, namakan semula sumber data anda kepada **eCommercePurchases**.

1. **Simpan** sumber data.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingest data pelanggan daripada skema kesetiaan

1. Buat sumber data bernama **LoyaltyScheme** dan pilih **penyambung Teks/CSV**.

1. Masukkan URL untuk pelanggan https://aka.ms/ciadclasscustomerloyalty kesetiaan.

1. Semasa mengedit data, pilih **Ubah** kemudian **Gunakan baris pertama sebagai pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **DateOfBirth**: Tarikh
   - **RewardsPoints**: Nombor Bulat
   - **CreatedOn**: Tarikh/Masa

1. **Dalam medan Nama** pada anak tetingkap kanan, namakan semula sumber data anda kepada **loyCustomers**.

1. **Simpan** sumber data.

### <a name="ingest-customer-data-from-website-reviews"></a>Inges data pelanggan daripada ulasan laman web

1. Buat sumber data bernama **Laman Web** dan pilih **penyambung Teks / CSV**.

1. Masukkan URL untuk ulasan laman web https://aka.ms/CI-ILT/WebReviews.

1. Semasa mengedit data, pilih **Ubah** kemudian **Gunakan baris pertama sebagai pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **ReviewRating**: Nombor perpuluhan
   - **ReviewDate**: Tarikh

1. Dalam medan **Nama** pada anak tetingkap kanan, namakan semula sumber data anda kepada **Ulasan**.

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

1. Tambah aktiviti lain dan petakan nama medannya pada medan yang sepadan:
   - **Entiti aktiviti**: Ulasan:Laman web
   - **Kunci primer**: ReviewId
   - **Timestamp**: ReviewDate
   - **Aktiviti** acara: ActivityTypeDisplay
   - **Butiran** tambahan: UlasanRating
   - **Jenis aktiviti**: Semakan

1. Jalankan aktiviti tersebut.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Tugas 4 - Konfigurasi ramalan nilai sepanjang hayat pelanggan

Dengan profil pelanggan bersatu di tempat dan aktiviti yang dibuat, jalankan nilai seumur hidup pelanggan (CLV) ramalan. Untuk langkah terperinci, lihat [Nilai Sepanjang Hayat Pelanggan ramalan](predict-customer-lifetime-value.md).

1. Pergi ke **Ramalan** > **Perisikan**.

1. Pada tab **Cipta**, pilih **Gunakan model** pada **jubin Nilai** Sepanjang Hayat Pelanggan.

1. Pilih **Mulakan**.

1. Namakan model **Ramalan OOB eCommerce CLV** dan entiti output **OOBeCommerceCLVPrediction**.

1. Tentukan keutamaan model:
   - **ramalan tempoh** masa: **12 bulan atau 1 tahun** untuk menentukan sejauh mana masa depan untuk meramalkan CLV.
   - **Pelanggan** aktif: **Biarkan model mengira selang** pembelian yang merupakan tempoh masa di mana pelanggan mesti mempunyai sekurang-kurangnya satu transaksi untuk dianggap aktif.
   - **Pelanggan** bernilai tinggi: secara manual menentukan pelanggan bernilai tinggi sebagai **30% pelanggan** aktif teratas.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Keutamaan melangkah dalam pengalaman berpandu untuk model CLV.":::

1. Pilih **Seterusnya**.

1. Dalam langkah **Data yang Diperlukan**, pilih **Tambah data** untuk menyediakan data sejarah transaksi.

    :::image type="content" source="media/clv-model-required.png" alt-text="Tambah langkah data yang diperlukan dalam pengalaman berpandu untuk model CLV.":::

1. Pilih **SalesOrderLine** dan entiti eCommercePurchases dan pilih **Seterusnya**. Data yang diperlukan diisi secara automatik daripada aktiviti tersebut. Pilih **Simpan** dan kemudian **Seterusnya**.

1. Langkah **tambahan data (pilihan)** membolehkan anda menambah lebih banyak data aktiviti pelanggan untuk mendapatkan lebih banyak cerapan untuk interaksi pelanggan. Untuk contoh ini, pilih **Tambah data** dan tambah aktiviti semakan web.

1. Pilih **Seterusnya**.

1. **Dalam langkah Kemas kini data**, pilih **Bulanan** untuk jadual model.

1. Pilih **Seterusnya**.

1. Selepas menyemak semula semua butiran, pilih **Simpan dan Jalankan**.

## <a name="task-5---review-model-results-and-explanations"></a>Tugas 5 - Semak semula hasil dan penerangan model

Biarkan model melengkapkan latihan dan pemarkahan data. [Semak keputusan dan penjelasan](predict-customer-lifetime-value.md#view-prediction-results) model CLV.

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Tugas 6 - Cipta segmen pelanggan bernilai tinggi

Menjalankan model mencipta entiti baharu, yang disenaraikan pada **Data** > **Entiti**. Anda boleh mencipta segmen pelanggan baharu berdasarkan entiti yang dicipta oleh model.

1. Pada halaman hasil, pilih **Cipta segmen**.

1. Buat peraturan menggunakan **entiti OOBeCommerceCLVPrediction** dan tentukan segmen:
   - **Padang**: CLVScore
   - **Pengendali**: lebih besar daripada
   - **Nilai**: 1500

1. Pilih **Simpan** dan **Jalankan** segmen.

Anda kini mempunyai segmen yang mengenal pasti pelanggan yang diramalkan untuk menjana lebih daripada $1500 pendapatan dalam tempoh 12 bulan akan datang. Segmen ini akan dikemas kini secara dinamik jika lebih banyak data diinges. Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).

> [!TIP]
> Anda juga boleh mencipta segmen untuk model ramalan daripada **halaman Segmen** dengan **memilih Baharu** dan memilih **Cipta daripada** > **Kecerdasan**. Untuk maklumat lanjut, lihat [Mencipta segmen baharu dengan segmen](segment-quick.md) pantas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
