---
title: Penyambung Power BI (pratonton)
description: Ketahui cara menggunakan penyambung Dynamics 365 Customer Insights dalam Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196681"
---
# <a name="power-bi-connector-preview"></a>Penyambung Power BI (pratonton)

Cipta penggambaran untuk data anda dengan Microsoft Power BI Desktop. Menjana wawasan tambahan dan bina laporan dengan data pelanggan disatukan anda.

## <a name="prerequisites"></a>Prasyarat

- Profil pelanggan bersatu.
- Versi terbaru [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) dipasang pada komputer anda. [Ketahui lebih lanjut tentang Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurasi penyambung untuk Power BI

1. Dalam Power BI Desktop, pilih **Fail** > **Dapatkan Data**.

1. Pilih **Lihat lebih** dan cari **Dynamics 365 Customer Insights**

1. Pilih **Connect**.

1. **Log masuk** dengan akaun organisasi yang sama anda gunakan untuk Customer Insights dan pilih **Sambung**.
   > [!NOTE]
   > Akaun yang anda tunjukkan dalam langkah ini digunakan untuk mengambil data daripada Customer Insights dan tidak perlu sama seperti yang anda daftar masuk dalam Power BI. Untuk tetap semula akaun yang digunakan untuk pengambilan data, buka Power BI dan pergi ke **Fail** > **Pilihan** > **Tetapan** > **Tetapan sumber data**. Dalam senarai sumber data, pilih **Daftar Masuk Dynamics 365 Customer Insights** dan pilih **Keizinan dibenarkan**.  

1. **Dalam kotak dialog Navigator**, lihat senarai semua persekitaran yang anda boleh akses. Kembangkan persekitaran dan buka sebarang folder (entiti, langkah, segmen, pengayaan). Contoh, buka folder **Entiti** untuk melihat semua entiti yang boleh anda import.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Pengemudi Penyambung Power BI.":::

1. Pilih kotak semak bersebelahan dengan entiti untuk disertakan dan **Dimuatkan**. Anda boleh memilih entiti berbilang daripada persekitaran berbilang.

   Kotak dialog pemuatan dipaparkan semasa entiti anda dimuatkan. Setelah semua entiti pilihan anda dimuatkan, gunakan keupayaan Power BI untuk memvisualisasikan data.

## <a name="large-data-sets"></a>Set data yang besar

Penyambung Customer Insights Power BI direka untuk berfungsi bagi data set yang mengandungi hingga 1 juta profil pelanggan. Mengimport set data yang lebih besar mungkin berfungsi, tetapi mengambil masa yang lama dan boleh tamat masa kerana Power BI batasan. Untuk maklumat lanjut, lihat [Power BI: Pengesyoran untuk set data yang lebih besar](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Bekerja dengan subset data

Pertimbangkan untuk bekerja dengan subset data anda. Sebagai contoh, buat [segmen](segments.md) dan bukannya mengeksport semua rekod pelanggan ke Power BI.

## <a name="troubleshooting"></a>Pencarisilapan

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Persekitaran Customer Insights tidak dipaparkan dalam Power BI

Persekitaran yang mempunyai lebih daripada satu [perhubungan](relationships.md) yang ditakrifkan antara dua entiti yang sama dalam Wawasan Pelanggan tidak akan tersedia dalam Power BI penyambung.

Kenal pasti dan alih keluar perhubungan pendua.

1. Pergi ke **Perhubungan** > **Data** pada persekitaran yang anda hilang .Power BI
1. Kenal pasti hubungan pendua:
   - Semak sama ada terdapat lebih daripada satu perhubungan yang ditakrifkan antara dua entiti yang sama.
   - Semak sama ada terdapat hubungan yang dicipta antara dua entiti yang kedua-duanya dimasukkan dalam proses penyatuan. Terdapat perhubungan tersirat yang ditakrifkan antara semua entiti yang disertakan dalam proses penyatuan.
1. Alih keluar sebarang perhubungan pendua yang dikenal pasti.

Selepas penyingkiran perhubungan pendua, cuba konfigurasi penyambung Power BI sekali lagi.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Ralat pada medan tarikh semasa memuatkan entiti dalam Power BI Desktop

Apabila memuatkan entiti yang mengandungi medan dengan format tarikh seperti MM/DD/YYYY, anda mungkin menghadapi ralat kerana format setempat yang tidak sepadan. Ketidakpadanan ini berlaku apabila fail anda Power BI Desktop disetkan ke tempat lain daripada bahasa Inggeris (Amerika Syarikat), kerana medan tarikh dalam Wawasan Pelanggan disimpan dalam format AS.

Fail Power BI Desktop ini mempunyai tetapan bahasa tunggal, yang digunakan apabila mendapatkan data. Untuk membetulkan ralat tarikh, [tetapkan tempat . BPI fail](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) ke Bahasa Inggeris (Amerika Syarikat).

[!INCLUDE [footer-include](includes/footer-banner.md)]
