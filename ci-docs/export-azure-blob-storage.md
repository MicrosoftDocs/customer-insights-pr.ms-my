---
title: Export data ke Azure Blob Storage (preview)
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke storan Blob.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 059c8364ca0f3740bc0e4ffeeeba94246c9e5696
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055501"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Export data ke Azure Blob Storage (preview)

Simpan data Customer Insights anda dalam storan Blob atau gunakannya untuk memindahkan data anda ke aplikasi lain.

## <a name="known-limitations"></a>Had diketahui

1. Untuk storan Blob Azure anda boleh memilih antara [Prestasi standard dan tingkat prestasi Premium](/azure/storage/blobs/storage-blob-performance-tiers). Jika anda memilih tingkat prestasi Premium, pilih [blob blok premium sebagai jenis akaun](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Sediakan sambungan kepada Storan Blob

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Storan Blob Azure** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama akaun**, **Kunci akaun** dan **Bekas** untuk akaun Storan Blob anda.
    - Untuk mengetahui lebih lanjut tentang cara mencari nama akaun dan kekunci akaun Storan Blob, lihat [Urus tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).
    - Untuk mengetahui cara untuk mencipta bekas, lihat [Cipta bekas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pilih **Simpan** untuk melengkapkan sambungan. 

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Jika anda menghidupkan tetapan padam lembut untuk akaun Storan Blob Azure, eksport akan gagal. Padamkan padam lembut untuk mengeksport data kepada blob. Untuk maklumat lanjut, lihat [Dayakan padam lembut blob](/azure/storage/blobs/soft-delete-blob-enable)

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Storan Blob Azure. Jika anda tidak melihat nama bahagian ini, maka tiada sambungan jenis ini tersedia untuk anda.

1. Pilih kotak di sebelah setiap entiti yang anda mahu eksport ke destinasi ini.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).

Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).

Data yang dieksport disimpan dalam bekas Storan Blob yang anda konfigurasikan. Laluan folder berikut dicipta secara automatik dalam bekas anda:

- Untuk entiti sumber dan entiti yang dijana oleh sistem:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
  
  > [!TIP]
  > Eksport entiti yang mengandungi sejumlah besar data boleh membawa kepada berbilang fail CSV dalam folder yang sama untuk setiap eksport. Memisahkan eksport berlaku atas sebab prestasi untuk meminimumkan masa yang diperlukan untuk eksport selesai.

- Model.json untuk entiti yang dieksport akan berada pada peringkat %ExportDestinationName%.  
  - Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
