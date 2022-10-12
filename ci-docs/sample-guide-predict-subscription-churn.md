---
title: Langganan panduan sampel ramalan pulangan
description: Gunakan panduan sampel ini untuk mencuba model ramalan pulangan langganan luar kotak.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610017"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Langganan panduan sampel ramalan pulangan

Panduan ini akan menerangkan kepada anda contoh ramalan churn langganan hujung ke hujung menggunakan data sampel. Kami mengesyorkan agar anda mencuba ramalan [ini dalam persekitaran yang baru](manage-environments.md).

## <a name="scenario"></a>Senario

Contoso adalah sebuah syarikat yang menghasilkan mesin kopi dan kopi berkualiti tinggi. Mereka menjual produk melalui laman web Contoso Coffee mereka. Mereka baru memulakan perniagaan langganan untuk pelanggan mereka untuk mendapatkan kopi secara tetap. Matlamat mereka adalah untuk memahami pelanggan yang melanggan mungkin membatalkan langganan mereka dalam beberapa bulan akan datang. Mengetahui mana antara pelanggan **mereka yang mungkin churn** boleh membantu mereka menjimatkan usaha pemasaran dengan memberi tumpuan kepada menjaga mereka.

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.

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

1. Simpan sumber data.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingest data pelanggan daripada skema kesetiaan

1. Buat sumber data bernama **LoyaltyScheme** dan pilih **penyambung Teks/CSV**.

1. Masukkan URL untuk pelanggan https://aka.ms/ciadclasscustomerloyalty kesetiaan.

1. Semasa mengedit data, pilih **Ubah** kemudian **Gunakan baris pertama sebagai pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **DateOfBirth**: Tarikh
   - **RewardsPoints**: Nombor Bulat
   - **CreatedOn**: Tarikh/Masa

1. **Dalam medan Nama** pada anak tetingkap kanan, namakan semula sumber data anda kepada **loyCustomers**.

1. Simpan sumber data.

### <a name="ingest-subscription-information"></a>Ingeskan maklumat langganan

1. Cipta sumber data bernama **SubscriptionHistory** dan pilih **penyambung Teks/CSV**.

1. Masukkan URL untuk langganan https://aka.ms/ciadchurnsubscriptionhistory.

1. Semasa mengedit data, pilih **Ubah** kemudian **Gunakan baris pertama sebagai pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **SubscriptioID**: Nombor Bulat
   - **SubscriptionAmount**: Mata Wang
   - **SubscriptionEndDate** : Tarikh/Masa
   - **SubscriptionEndDate**: Tarikh/Masa
   - **TransactionDate**: Tarikh/Masa
   - **IsRecurring**: Benar/Palsu
   - **Is_auto_renew** : Benar/Palsu
   - **RecurringFrequencyInMonths**: Nombor Bulat

1. **Dalam medan Nama** pada anak tetingkap kanan, namakan semula sumber data anda kepada **SubscriptionHistory**.

1. Simpan sumber data.

### <a name="ingest-customer-data-from-website-reviews"></a>Inges data pelanggan daripada ulasan laman web

1. Buat sumber data bernama **Laman Web** dan pilih **penyambung Teks / CSV**.

1. Masukkan URL untuk ulasan https://aka.ms/ciadclasswebsite laman web.

1. Semasa mengedit data, pilih **Ubah** kemudian **Gunakan baris pertama sebagai pengepala**.

1. Kemas kini jenis data untuk lajur yang disenaraikan di bawah:
   - **ReviewRating**: Nombor Bulat
   - **ReviewDate**: Tarikh

1. **Dalam medan Nama** pada anak tetingkap kanan, namakan semula sumber data anda kepada **paparan webReviews**.

## <a name="task-2---data-unification"></a>Tugas 2 - Penyatuan data

Semak semula artikel [tentang penyatuan](data-unification.md) data. Maklumat berikut menganggap anda sudah biasa dengan penyatuan data secara umum.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tugas 3 - Buat aktiviti sejarah transaksi

Semak artikel [mengenai aktiviti](activities.md) pelanggan. Maklumat berikut menganggap anda sudah biasa dengan membuat aktiviti secara umum.

1. Cipta aktiviti yang dipanggil **SubscriptionHistory** dengan *entiti Langganan* dan kunci utamanya, **CustomerId**.

1. Buat hubungan antara *SubscriptionHistory:Langganan* dan *eCommerceHubungka:eCommerce* dengan **CustomerID** sebagai kunci asing untuk menghubungkan kedua-dua entiti.

1. Pilih **Jenis Langganan untuk** EventActivity **dan** SubscriptionEndDate **untuk** TimeStamp **·**.

1. Pilih **Langganan** untuk **Jenis** Aktiviti dan memetakan data aktiviti secara semantik.

1. Jalankan aktiviti tersebut.

1. Tambah aktiviti lain dan petakan nama medannya pada medan yang sepadan:
   - Entiti aktiviti pelanggan: Reviews:Website
   - Kunci utama: Website.Reviews.ReviewId
   - Cap masa: Website.Reviews.ReviewDate
   - Peristiwa (nama aktiviti): Website.Reviews.ActivityTypeDisplay
   - Butiran (amaun atau nilai): Website.Reviews.ReviewRating

1. Jalankan aktiviti tersebut.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Tugas 4 - Konfigurasikan ramalan pulangan langganan

Dengan profil pelanggan bersatu di tempat dan aktiviti yang dibuat, jalankan ramalan churn langganan. Untuk langkah terperinci, lihat [ramalan churn langganan](predict-subscription-churn.md).

1. Pergi ke **Ramalan** > **Perisikan**.

1. Pada tab **Cipta**, pilih **Gunakan model** pada **jubin model** churn Pelanggan.

1. Pilih **Langganan** untuk jenis churn kemudian **Bermula**.

1. Namakan model **Ramalan Pulangan Langganan OOB** dan **OOBSubscriptionChurnPrediction** entiti output.

1. Tentukan keutamaan model:
   - **Hari sejak langganan tamat**: **60** hari untuk menunjukkan bahawa pelanggan dianggap tergelak jika mereka tidak memperbaharui langganan dalam tempoh ini selepas langganan mereka tamat.
   - **Hari untuk menyiasat masa depan untuk meramalkan churn**: **93** hari yang merupakan tempoh model meramalkan pelanggan mana yang mungkin churn. Semakin jauh masa hadapan anda melihat, semakin kurang tepat keputusan.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Pilih keutamaan model dan definisi churn.":::

1. Pilih **Seterusnya**.

1. Dalam langkah Data **yang** Diperlukan, pilih **Tambah data** untuk menyediakan sejarah langganan.

1. Pilih **Langganan** dan entiti SubscriptionHistory dan pilih **Berikut**. Data yang diperlukan diisi secara automatik daripada aktiviti tersebut. Pilih **Simpan**.

1. Di bawah Aktiviti Pelanggan, pilih **Tambah data**.

1. Untuk contoh ini, tambahkan aktiviti semakan web.

1. Pilih **Seterusnya**.

1. **Dalam langkah Kemas kini data**, pilih **Bulanan** untuk jadual model.

1. Selepas menyemak semula semua butiran, pilih **Simpan dan Jalankan**.

## <a name="task-5---review-model-results-and-explanations"></a>Tugas 5 - Semak semula hasil dan penerangan model

Biarkan model melengkapkan latihan dan pemarkahan data. Semak penjelasan model churn langganan. Untuk maklumat lanjut, lihat [Melihat hasil](predict-subscription-churn.md#view-prediction-results) ramalan.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tugas 6 - Cipta segmen pelanggan risiko pulangan tinggi

Menjalankan model mencipta entiti baharu, yang disenaraikan pada **Data** > **Entiti**. Anda boleh mencipta segmen baharu berdasarkan entiti yang dicipta oleh model.

1. Pada halaman hasil, pilih **Cipta segmen**.

1. Buat peraturan menggunakan **entiti OOBSubscriptionChurnPrediction** dan tentukan segmen:
   - **Padang**: ChurnScore
   - **Pengendali**: lebih besar daripada
   - **Nilai**: 0.6

1. Pilih **Simpan** dan **Jalankan** segmen.

Kini anda mempunyai segmen yang dikemas kini secara dinamik yang mengenal pasti pelanggan risiko pulangan tinggi untuk perniagaan langganan ini. Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).

> [!TIP]
> Anda juga boleh mencipta segmen untuk model ramalan daripada **halaman Segmen** dengan **memilih Baharu** dan memilih **Cipta daripada** > **Kecerdasan**. Untuk maklumat lanjut, lihat [Mencipta segmen baharu dengan segmen](segment-quick.md) pantas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
