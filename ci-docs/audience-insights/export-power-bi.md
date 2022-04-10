---
title: Penyambung Power BI
description: Ketahui cara menggunakan penyambung Dynamics 365 Customer Insights dalam Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: dccc069a355725bae09c1fece9292b9aee374e6d
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225527"
---
# <a name="connector-for-power-bi-preview"></a>Penyambung untuk Power BI (pratonton)

Cipta visualisasi untuk data anda dengan Power BI Desktop. Menjana wawasan tambahan dan bina laporan dengan data pelanggan disatukan anda.

## <a name="prerequisites"></a>Prasyarat

- Anda mempunyai profil pelanggan disatukan.
- Versi terbaru [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) dipasang pada komputer anda. [Ketahui lebih lanjut tentang Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurasi penyambung untuk Power BI

1. Dalam Power BI Desktop, pilih **Fail** > **Dapatkan Data**.

1. Pilih **Lihat lebih** dan cari **Dynamics 365 Customer Insights**

1. Pilih **Connect**.

1. **Log masuk** dengan akaun organisasi yang sama anda gunakan untuk Customer Insights dan pilih **Sambung**.
   > [!NOTE]
   > Akaun yang anda tunjukkan dalam langkah ini digunakan untuk mengambil data daripada Customer Insights dan tidak perlu sama seperti yang anda daftar masuk dalam Power BI. Untuk tetap semula akaun yang digunakan untuk pengambilan data, buka Power BI dan pergi ke **Fail** > **Pilihan** > **Tetapan** > **Tetapan sumber data**. Dalam senarai sumber data, pilih **Daftar Masuk Dynamics 365 Customer Insights** dan pilih **Keizinan dibenarkan**.  

1. Dalam kotak dialog **Pengemudi**. anda lihat senarai semua persekitaran yang anda mempunyai akses. Kembangkan persekitaran dan buka sebarang folder (entiti, langkah, segmen, pengayaan). Contoh, buka folder **Entiti** untuk melihat semua entiti yang boleh anda import.

   ![Pengemudi Penyambung Power BI.](media/power-bi-navigator.png "Navigasi Penyambung Power BI")

1. Pilih kotak semak bersebelahan dengan entiti untuk disertakan dan **Dimuatkan**. Anda boleh memilih entiti berbilang daripada persekitaran berbilang.

1. Anda akan melihat pemuatan kotak dialog semasa entiti anda dimuatkan. Sebaik sahaja semua entiti yang dipilih anda telah dimuatkan, anda boleh menggunakan keupayaan Power BI untuk menggambarkan data tersebut.

## <a name="large-data-sets"></a>Set data yang besar

Penyambung Customer Insights Power BI direka untuk berfungsi bagi data set yang mengandungi hingga 1 juta profil pelanggan. Mengimport set data yang lebih besar mungkin boleh tetapi ianya mengambil masa yang lama. Selain itu, proses mungkin berjalan ke masa keluar kerana had Power BI. Untuk maklumat lanjut, lihat [Power BI: Pengesyoran untuk set data yang lebih besar](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Bekerja dengan subset data

Pertimbangkan untuk bekerja dengan subset data anda. Sebagai contoh, anda boleh mencipta [segmen](segments.md) daripada mengeksport semua rekod pelanggan ke Power BI.

## <a name="troubleshooting"></a>Pencarisilapan

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Persekitaran Customer Insights tidak dipaparkan dalam Power BI

Persekitaran yang mempunyai lebih daripada satu [perhubungan](relationships.md) yang ditakrifkan antara dua entiti yang sama dalam wawasan khalayak tidak akan tersedia dalam penyambung Power BI.

Anda boleh mengenal pasti dan mengalih keluar perhubungan pendua.

1. Dalam wawasan khalayak, pergi ke **Data** > **Perhubungan** pada persekitaran yang anda tiada dalam Power BI.
2. Kenal pasti hubungan pendua:
   - Semak sama ada terdapat lebih daripada satu perhubungan yang ditakrifkan antara dua entiti yang sama.
   - Semak sama ada terdapat hubungan yang dicipta antara dua entiti yang kedua-duanya dimasukkan dalam proses penyatuan. Terdapat perhubungan tersirat yang ditakrifkan antara semua entiti yang disertakan dalam proses penyatuan.
3. Alih keluar sebarang perhubungan pendua yang dikenal pasti.

Selepas penyingkiran perhubungan pendua, cuba konfigurasi penyambung Power BI sekali lagi. Persekitarannya sepatutnya boleh tersedia sekarang.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Ralat pada medan tarikh semasa memuatkan entiti dalam Power BI Desktop

Apabila memuatkan entiti yang mengandungi medan dengan format tarikh seperti MM/DD/YYYY, anda boleh menghadapi ralat kerana disebabkan format bahasa yang tidak sepadan. Ketidaksepadanan ini berlaku apabila fail Power BI Desktop anda ditetapkan kepada bahasa lain selain daripada Bahasa Inggeris (Amerika Syarikat), kerana medan tarikh dalam cerapan khalayak disimpan dalam format AS.

Fail Power BI Desktop ini mempunyai tetapan bahasa tunggal, yang digunakan apabila mendapatkan data. Dapatkan medan tarikh ini ditafsirkan dengan betul, tetapkan bahasa fail .BPI kepada Bahasa Inggeris (Amerika Syarikat). [Ketahui cara menukar bahasa fail Power BI desktop](/power-bi/fundamentals/supported-languages-countries-regions.md#choose-the-locale-for-importing-data-into-power-bi-desktop).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
