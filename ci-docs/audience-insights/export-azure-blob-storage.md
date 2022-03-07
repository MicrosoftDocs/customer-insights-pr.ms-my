---
title: Eksport data Customer Insights ke Storan Blob Azure
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke storan Blob.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976192"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Eksport senarai segmen dan data lain ke Storan Blob Azure (pratonton)

Simpan data Customer Insights anda dalam storan Blob atau gunakannya untuk memindahkan data anda ke aplikasi lain.

## <a name="set-up-the-connection-to-blob-storage"></a>Sediakan sambungan ke storan Blob

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Storan Blob Azure** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama akaun**, **Kunci akaun** dan **Bekas** untuk akaun storan Blob anda.
    - Untuk mengetahui lebih lanjut tentang cara untuk mencari nama akaun dan kekunci akaun storan Blob, lihat [Urus tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).
    - Untuk mengetahui cara untuk mencipta bekas, lihat [Cipta bekas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pilih **Simpan** untuk melengkapkan sambungan. 

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Storan Blob Azure. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Pilih kotak di sebelah setiap entiti yang anda mahu eksport ke destinasi ini.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).     
Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 

Data yang dieksport disimpan dalam bekas storan Blob yang anda konfigurasikan. Laluan folder berikut dicipta secara automatik dalam bekas anda:

- Untuk entiti sumber dan entiti yang dijana oleh sistem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model. json untuk entiti yang dieksport akan berada pada peringkat %ExportDestinationName%
  - Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
