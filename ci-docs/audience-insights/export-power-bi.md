---
title: Penyambung Power BI
description: Ketahui cara menggunakan penyambung Dynamics 365 Customer Insights dalam Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406439"
---
# <a name="connector-for-power-bi-preview"></a>Penyambung untuk Power BI (pratonton)

Cipta visualisasi untuk data anda dengan Power BI Desktop. Menjana wawasan tambahan dan bina laporan dengan data pelanggan disatukan anda.

## <a name="prerequisites"></a>Prasyarat

- Anda mempunyai profil pelanggan disatukan.
- Versi terkini [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) dipasang pada komputer anda. [Ketahui lebih lanjut tentang Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurasi penyambung untuk Power BI

1. Dalam Power BI Desktop, pilih **Fail** > **Dapatkan Data**.

1. Pilih **Lihat lebih** dan cari **Dynamics 365 Customer Insights**

1. Pilih hasilnya dan pilih **Sambung**.

1. **Log masuk** dengan akaun organisasi yang sama anda gunakan untuk Customer Insights dan pilih **Sambung**.
   > [!NOTE]
   > Akaun yang anda tunjukkan dalam langkah ini digunakan untuk mengambil data daripada Customer Insights dan tidak perlu sama seperti yang anda daftar masuk dalam Power BI. Untuk tetap semula akaun yang digunakan untuk pengambilan data, buka Power BI dan pergi ke **Fail** > **Pilihan** > **Tetapan** > **Tetapan sumber data**. Dalam senarai sumber data, pilih **Daftar Masuk Dynamics 365 Customer Insights** dan pilih **Keizinan dibenarkan**.  

1. Dalam kotak dialog **Pengemudi**. anda lihat senarai semua persekitaran yang anda mempunyai akses. Kembangkan persekitaran dan buka sebarang folder (entiti, langkah, segmen, pengayaan). Contoh, buka folder **Entiti** untuk melihat semua entiti yang boleh anda import.

   ![Navigasi Penyambung Power BI](media/power-bi-navigator.png "Navigasi Penyambung Power BI")

1. Pilih kotak semak bersebelahan dengan entiti untuk disertakan dan **Dimuatkan**. Anda boleh memilih entiti berbilang daripada persekitaran berbilang.

1. Anda akan melihat pemuatan kotak dialog semasa entiti anda dimuatkan. Sebaik sahaja semua entiti yang dipilih anda telah dimuatkan, anda boleh menggunakan keupayaan Power BI untuk menggambarkan data tersebut.

## <a name="large-data-sets"></a>Set data yang besar

Penyambung Customer Insights Power BI direka untuk berfungsi bagi data set yang mengandungi hingga 1 juta profil pelanggan. Mengimport set data yang lebih besar mungkin boleh tetapi ianya mengambil masa yang lama. Selain itu, proses mungkin berjalan ke masa keluar kerana had Power BI. Untuk maklumat lanjut, lihat [Power BI: Pengesyoran untuk set data yang lebih besar](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Bekerja dengan subset data

Pertimbangkan untuk bekerja dengan subset data anda. Sebagai contoh, anda boleh mencipta [segmen](segments.md) daripada mengeksport semua rekod pelanggan ke Power BI.
