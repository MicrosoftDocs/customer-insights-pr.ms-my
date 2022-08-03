---
title: Eksport data ke Azure Data Lake Storage Gen2 (pratonton)
description: Ketahui cara mengkonfigurasi sambungan ke Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196451"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Eksport data ke Azure Data Lake Storage Gen2 (pratonton)

Simpan data Customer Insights anda dalam akaun Data Lake Storage Gen2 atau gunakannya untuk memindahkan data anda kepada aplikasi lain.

## <a name="prerequisites"></a>Prasyarat

- Akaun [storan untuk digunakan dengan Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Untuk mencari nama dan kunci akaun storan, lihat [Menguruskan seting akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Had diketahui

- Untuk Azure Data Lake Storage Gen2, pilih antara [prestasi Standard dan peringkat prestasi Premium](/azure/storage/blobs/create-data-lake-storage-account). Jika anda memilih tingkat prestasi Premium, pilih [blob blok premium sebagai jenis akaun](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Sediakan sambungan ke Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Azure Data Lake Gen 2**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama akaun**, **Kekunci akaun** dan **Bekas** untuk Azure Data Lake Storage Gen2 anda.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada seksyen Azure Data Lake. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Masukkan nama folder untuk Azure Data Lake Storage storan Gen2.

1. Pilih kotak di sebelah setiap entiti yang anda mahu eksport ke destinasi ini.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Data yang dieksport disimpan dalam bekas storan Azure Data Lake Gen 2 yang anda konfigurasikan.

> [!TIP]
> Eksport entiti yang mengandungi sejumlah besar data boleh membawa kepada berbilang fail CSV dalam folder yang sama untuk setiap eksport. Memisahkan eksport berlaku atas sebab prestasi untuk meminimumkan masa yang diperlukan untuk eksport selesai.

[!INCLUDE [footer-include](includes/footer-banner.md)]
