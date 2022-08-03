---
title: Eksport segmen ke Dynamics 365 Sales (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195992"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Eksport segmen ke Dynamics 365 Sales (pratonton)

Gunakan data pelanggan anda untuk mencipta senarai pemasaran, menyusuli aliran kerja dan menghantar promosi dengan Dynamics 365 Sales.

## <a name="prerequisites"></a>Prasyarat

Rekod kenalan mesti wujud dalam Dynamics 365 Sales sebelum anda boleh mengeksport segmen daripada Customer Insights ke Jualan. Baca lebih lanjut tentang cara menelan kenalan dari [Dynamics 365 Sales menggunakan Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Mengeksport segmen daripada Wawasan Pelanggan ke Jualan tidak akan mencipta rekod kenalan baharu dalam keadaan Jualan. Rekod hubungan daripada Jualan mesti ditelan dalam Wawasan Pelanggan dan digunakan sebagai sumber data. Mereka juga perlu dimasukkan dalam entiti Pelanggan disatukan untuk memetakan ID pelanggan kepada ID kenalan sebelum segmen boleh dieksport.

## <a name="known-limitations"></a>Had diketahui

Eksport ke Dynamics 365 Sales terhad kepada 100,000 setiap segmen, yang boleh mengambil masa sehingga 3 jam untuk diselesaikan.

## <a name="set-up-connection-to-sales"></a>Sediakan sambungan ke Jualan

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Dynamics 365 Sales**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan URL Jualan organisasi anda dalam medan **Alamat pelayan**.

1. Dalam bahagian **Akaun pentadbir pelayan**, pilih **Daftar masuk** dan pilih akaun Dynamics 365 Sales.

1. Petakan medan ID pelanggan ke ID Kenalan Dynamics 365.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Dynamics 365 Sales. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Pilih medan ID Kenalan dalam entiti Pelanggan yang sepadan dengan ID Kenalan Dynamics 365.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
