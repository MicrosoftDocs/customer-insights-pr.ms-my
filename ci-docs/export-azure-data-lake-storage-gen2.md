---
title: Eksport data Customer Insights ke Azure Data Lake Storage Gen2
description: Ketahui cara mengkonfigurasi sambungan ke Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 8b14992f8312d333d8a12501e8a28496c8434779
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643254"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Senarai segmen eksport dan data lain ke Azure Data Lake Storage Gen2 (pratonton)

Simpan data Customer Insights anda dalam akaun Data Lake Storage Gen2 atau gunakannya untuk memindahkan data anda kepada aplikasi lain.

## <a name="known-limitations"></a>Had diketahui

1. Untuk Azure Data Lake Storage Gen2 anda boleh memilih antara [Prestasi standard dan tingkat prestasi Premium](/azure/storage/blobs/create-data-lake-storage-account) apabila anda mencipta akaun storan untuk data lake anda. Jika anda memilih tingkat prestasi Premium, pilih blob blok premium sebagai jenis akaun. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Sediakan sambungan ke Azure Data Lake Storage Gen2 


1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Azure Data Lake Gen 2** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama akaun**, **Kekunci akaun** dan **Bekas** untuk Azure Data Lake Storage Gen2 anda.
    - Untuk mengetahui cara untuk mencipta akaun storan untuk digunakan dengan Azure Data Lake Storage Gen2, lihat [Cipta akaun storan](/azure/storage/blobs/create-data-lake-storage-account). 
    - Untuk mengetahui lebih lanjut tentang storan nama akaun dan kekunci akaun Azure Data Lake Gen2, lihat [Urus tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).

1. Pilih **Simpan** untuk melengkapkan sambungan. 

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian **Azure Data Lake**. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Pilih kotak di sebelah setiap entiti yang anda mahu eksport ke destinasi ini.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 

Data yang dieksport disimpan dalam bekas storan Azure Data Lake Gen 2 yang anda konfigurasikan. 

[!INCLUDE [footer-include](includes/footer-banner.md)]
