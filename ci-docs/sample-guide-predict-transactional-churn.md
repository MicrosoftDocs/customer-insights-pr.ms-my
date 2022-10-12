---
title: Panduan sampel ramalan pulangan transaksi
description: Gunakan panduan sampel ini untuk mencuba model ramalan pulangan transaksi luar kotak.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609695"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Panduan sampel ramalan pulangan transaksi

Panduan ini akan menerangkan kepada anda contoh hujung ke hujung ramalan churn transaksi menggunakan data sampel. Kami mengesyorkan agar anda mencuba ramalan [ini dalam persekitaran yang baru](manage-environments.md).

## <a name="scenario"></a>Senario

Contoso adalah sebuah syarikat yang menghasilkan mesin kopi dan kopi berkualiti tinggi. Mereka menjual produk melalui laman web Contoso Coffee mereka. Matlamat mereka adalah untuk mengetahui pelanggan yang biasanya membeli produk mereka secara tetap, akan berhenti menjadi pelanggan aktif dalam masa 60 hari akan datang. Mengetahui pelanggan mereka yang **cenderung untuk memulangkan**, boleh membantu mereka menjimatkan usaha pemasaran dengan memberikan tumpuan dalam mengekalkan mereka.

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md).

## <a name="task-1---ingest-data"></a>Tugas 1 - Inges data

Semak artikel [tentang pengingesan](data-sources.md) data dan [menyambung ke Power Query sumber data](connect-power-query.md). Maklumat berikut menganggap anda sudah biasa dengan pengambilan data secara umum.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inges data pelanggan daripada platform e-Dagang

1. Buat sumber data bernama **eCommerce** dan pilih **penyambung Teks /CSV**.

1. Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscontacts.

1. Semasa mengedit data, pilih **Ubah** kemudian **Gunakan baris pertama sebagai pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:

   - **DateOfBirth**: Tarikh
   - **CreatedOn**: Zon waktu tarikh

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Tukar Tarikh Lahir kepada Tarikh.":::

1. **Dalam medan Nama** pada anak tetingkap kanan, namakan semula sumber data anda kepada **eCommerceHubungi**

1. Simpan sumber data.

### <a name="ingest-online-purchase-data"></a>Inges data pembelian dalam talian

1. Tambahkan set data lain pada sumber data **e-Dagang** yang sama. Pilih penyambung **Teks/CSV** semula.

1. Masukkan URL untuk data pembelian dalam talian https://aka.ms/ciadclassonline.

1. Semasa mengedit data, pilih **Ubah** kemudian **Gunakan baris pertama sebagai pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:

   - **PurchasedOn** : Tarikh/Masa
   - **TotalPrice** : Mata Wang

1. **Dalam medan Nama** pada anak tetingkap kanan, namakan semula sumber data anda kepada **eCommercePurchases**.

1. Simpan sumber data.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingest data pelanggan daripada skema kesetiaan

1. Buat sumber data bernama **LoyaltyScheme** dan pilih **penyambung Teks/CSV**.

1. Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscustomerloyalty.

1. Semasa mengedit data, pilih **Ubah** kemudian **Gunakan baris pertama sebagai pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:

   - **DateOfBirth**: Tarikh
   - **RewardsPoints**: Nombor Bulat
   - **CreatedOn**: Tarikh/Masa

1. **Dalam medan Nama** pada anak tetingkap kanan, namakan semula sumber data anda kepada **loyCustomers**.

1. Simpan sumber data.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Tugas 4 - Konfigurasikan ramalan pulangan transaksi

Dengan profil pelanggan yang bersatu di tempat dan aktiviti, jalankan transaksi churn ramalan.

1. Pergi ke **Ramalan** > **Perisikan**.

1. Pada tab **Cipta**, pilih **Gunakan model** pada **model** Pelanggan churn.

1. Pilih **Transaksi** untuk jenis churn dan kemudian **Bermula**.

1. Namakan model **Ramalan Pulangan Transaksi e-Dagang OOB** dan entiti output **OOBeCommerceChurnPrediction**.

1. Pilih **Seterusnya**.

1. Tentukan keutamaan model:

   - **ramalan tetingkap**: **60** hari untuk menentukan sejauh mana masa depan kita ingin meramalkan churn pelanggan.

   - **Takrif** Churn: **60** hari untuk menunjukkan tempoh tanpa pembelian selepas itu pelanggan dianggap churned.

     :::image type="content" source="media/model-levers.PNG" alt-text="Pilih keutamaan model ramalan Definisi Tetingkap dan Churn.":::

1. Pilih **Seterusnya**.

1. Pilih **Sejarah Pembelian (diperlukan)** dan pilih **Tambah data** untuk sejarah pembelian.

1. Pilih **SalesOrderLine** dan entiti eCommercePurchases dan pilih **Seterusnya**. Data yang diperlukan diisi secara automatik daripada aktiviti tersebut. Pilih **Simpan** dan kemudian **Seterusnya**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Sertai entiti e-Dagang.":::

1. **Langkau langkah Data tambahan (pilihan**).

1. **Dalam langkah Kemas kini data**, pilih **Bulanan** untuk jadual model.

1. Selepas menyemak semula semua butiran, pilih **Simpan dan Jalankan**.

## <a name="task-5---review-model-results-and-explanations"></a>Tugas 5 - Semak semula hasil dan penerangan model

Biarkan model melengkapkan latihan dan pemarkahan data. Semak penjelasan model churn. Untuk maklumat lanjut, lihat [Melihat hasil](predict-transactional-churn.md#view-prediction-results) ramalan.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tugas 6 - Cipta segmen pelanggan risiko pulangan tinggi

Menjalankan model pengeluaran mencipta entiti baru, yang disenaraikan di **Entiti** > **Data**. Anda boleh mencipta segmen baharu berdasarkan entiti yang dicipta oleh model.

1. Pada halaman hasil, pilih **Cipta segmen**.

1. Buat peraturan menggunakan **entiti OOBeCommerceChurnPrediction** dan tentukan segmen:
   - **Padang**: ChurnScore
   - **Pengendali**: lebih besar daripada
   - **Nilai**: 0.6

1. Pilih **Simpan** dan **Jalankan** segmen.

Anda kini mempunyai segmen yang dikemas kini secara dinamik yang mengenal pasti pelanggan berisiko tinggi. Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).

> [!TIP]
> Anda juga boleh mencipta segmen untuk model ramalan daripada **halaman Segmen** dengan **memilih Baharu** dan memilih **Cipta daripada** > **Kecerdasan**. Untuk maklumat lanjut, lihat [Mencipta segmen baharu dengan segmen](segment-quick.md) pantas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
