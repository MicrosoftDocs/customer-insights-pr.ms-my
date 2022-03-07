---
title: Eksport data Customer Insights ke Azure Data Lake Storage Gen2
description: Ketahui cara mengkonfigurasi sambungan ke Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: c4408e52550b6648e2a001041dc0acdb5063d6a6ef1b8e4bba3321bf25fefcfc
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031990"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Sediakan sambungan ke Azure Data Lake Storage Gen2 (pratonton)

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

[!INCLUDE[footer-include](../includes/footer-banner.md)]
