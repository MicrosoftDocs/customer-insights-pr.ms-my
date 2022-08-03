---
title: Export data ke Azure Blob Storage (preview)
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke storan Blob.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195715"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Export data ke Azure Blob Storage (preview)

Simpan data Customer Insights anda dalam storan Blob atau gunakannya untuk memindahkan data anda ke aplikasi lain.

## <a name="prerequisites"></a>Prasyarat

- [Nama akaun](/azure/storage/blobs/create-data-lake-storage-account) Azure Blob Storage dan kunci akaun. Untuk mencari nama dan kunci, lihat [Menguruskan tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Had diketahui

- Untuk Azure Blob Storage, pilih antara [prestasi Standard dan peringkat prestasi Premium](/azure/storage/blobs/storage-blob-performance-tiers). Jika anda memilih tingkat prestasi Premium, pilih [blob blok premium sebagai jenis akaun](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Sediakan sambungan ke Storan Blob

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Azure Blob Storage**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama akaun**, **Kunci akaun** dan **Bekas** untuk akaun Storan Blob anda.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Untuk mengkonfigurasi eksport ini, anda mesti mempunyai [keizinan](export-destinations.md#set-up-a-new-export) untuk jenis sambungan ini.

> [!IMPORTANT]
> Jika anda menghidupkan [tetapan](/azure/storage/blobs/soft-delete-blob-enable) padam lembut untuk akaun Storan Azure Blob, eksport akan gagal. Padamkan padam lembut untuk mengeksport data kepada blob.

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Storan Blob Azure. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Masukkan nama folder untuk storan Blob.

1. Pilih kotak di sebelah setiap entiti yang anda mahu eksport ke destinasi ini.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Data yang dieksport disimpan dalam bekas Storan Blob yang anda konfigurasikan. Laluan folder berikut dicipta secara automatik dalam bekas anda:

- Untuk entiti sumber dan entiti yang dijana oleh sistem:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Contoh: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Eksport entiti yang mengandungi sejumlah besar data boleh membawa kepada berbilang fail CSV dalam folder yang sama untuk setiap eksport. Memisahkan eksport berlaku atas sebab prestasi untuk meminimumkan masa yang diperlukan untuk eksport selesai.

- Model.json untuk entiti yang dieksport berada di *%ExportDestinationName%* peringkat.  
  
  Contoh: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
