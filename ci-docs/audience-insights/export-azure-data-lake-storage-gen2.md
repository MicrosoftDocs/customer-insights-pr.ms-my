---
title: Eksport data Customer Insights ke Azure Data Lake Storage Gen2
description: Ketahui cara mengkonfigurasi sambungan ke Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477190"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Penyambung untuk Azure Data Lake Storage Gen2 (pratonton)

Simpan data Customer Insights anda dalam Azure Data Lake Storage Gen2 atau gunakannya untuk memindahkan data anda kepada aplikasi lain.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Konfigurasikan penyambung untuk Azure Data Lake Storage Gen2

1. Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.

1. Di bawah **Azure Data Lake Storage Gen2**, pilih **Sediakan**.

1. Berikan destinasi anda nama yang dikenali dalam medan **Nama paparan**.

1. Masukkan **Nama akaun**, **Kekunci akaun** dan **Bekas** untuk Azure Data Lake Storage Gen2 anda.
    - Untuk mengetahui cara untuk mencipta akaun storan untuk digunakan dengan Azure Data Lake Storage Gen2, lihat [Cipta akaun storan](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Untuk mengetahui lanjut tentang cara mencari nama akaun dan kunci akaun storan Data Lake Azure Gen2, lihat [Urus tetapan akaun storan dalam portal Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Pilih **Seterusnya**.

1. Pilih kotak di sebelah setiap entiti yang anda mahu eksport ke destinasi ini.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md#export-data-on-demand). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).
