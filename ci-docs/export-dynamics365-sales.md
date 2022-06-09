---
title: Eksport data Customer Insights ke Dynamics 365 Sales
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 987690283090ec83ca75f50bf8f3cd8da9295887
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643315"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Gunakan segmen dalam Dynamics 365 Sales (pratonton)



Gunakan data pelanggan anda untuk mencipta senarai pemasaran, menyusuli aliran kerja dan menghantar promosi dengan Dynamics 365 Sales.

## <a name="known-limitations"></a>Had diketahui

- Eksport ke Dynamics 365 Sales terhad kepada 100'000 ahli setiap segmen.
- Eksport segmen ke Dynamics 365 Sales boleh mengambil masa sehingga 3 jam untuk diselesaikan. 

## <a name="prerequisite-for-connection"></a>Prasyarat untuk sambungan

1. Rekod kenalan mesti wujud dalam Dynamics 365 Sales sebelum anda boleh mengeksport segmen daripada Customer Insights ke Jualan. Baca lebih lanjut tentang cara menelan kenalan dari [Dynamics 365 Sales menggunakan Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Mengeksport segmen daripada Wawasan Pelanggan ke Jualan tidak akan mencipta rekod kenalan baharu dalam keadaan Jualan. Rekod hubungan daripada Jualan mesti ditelan dalam Wawasan Pelanggan dan digunakan sebagai sumber data. Mereka juga perlu dimasukkan dalam entiti Pelanggan disatukan untuk memetakan ID pelanggan kepada ID kenalan sebelum segmen boleh dieksport.

## <a name="set-up-the-connection-to-sales"></a>Sediakan sambungan ke Sales

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Dynamics 365 Sales** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan URL Jualan organisasi anda dalam medan **Alamat pelayan**.

1. Dalam bahagian **Akaun pentadbir pelayan**, pilih **Daftar masuk** dan pilih akaun Dynamics 365 Sales.

1. Petakan medan ID pelanggan ke ID Kenalan Dynamics 365.

1. Pilih **Simpan** untuk melengkapkan sambungan. 

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Dynamics 365 Sales. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Pilih satu atau lebih segmen.

1. Pilih **Simpan**

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]