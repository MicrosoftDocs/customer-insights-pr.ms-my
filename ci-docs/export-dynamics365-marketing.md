---
title: Eksport data Customer Insights ke Dynamics 365 Marketing
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642960"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Gunakan segmen dalam Dynamics 365 Marketing (pratonton)



Gunakan [segmen](segments.md) untuk menjana kumpulan tertentu kempen dan kenalan pelanggan dengan Dynamics 365 Marketing. Untuk maklumat lanjut, lihat [Gunakan segmen daripada Dynamics 365 Customer Insights dengan Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Jika anda menggunakan keupayaan baharu Dynamics 365 Marketing untuk orkestrasi perjalanan pelanggan masa nyata dalam organisasi Dataverse, anda tidak perlu mencipta eksport standard untuk Dynamics 365 Marketing. Kenalan dan segmen daripada Wawasan Pelanggan boleh didapati terus dalam Dynamics 365 Marketing selepas menyambungkan Pemasaran dan Wawasan Pelanggan. Sebelum anda memadamkan eksport sedia ada, semak dokumentasi tentang [cara menyambungkan Wawasan Pelanggan dan Orkestrasi perjalanan pelanggan Pemasaran Dynamics 365](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Prasyarat untuk sambungan

- Rekod kenalan mesti wujud dalam Dynamics 365 Marketing sebelum anda boleh mengeksport segmen daripada Customer Insights ke Pemasaran. Baca lebih lanjut tentang cara untuk menginges kenalan dalam [Dynamics 365 Marketing menggunakan Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Mengeksport segmen daripada Wawasan Pelanggan ke Pemasaran tidak akan mencipta rekod kenalan baharu dalam keadaan Pemasaran. Rekod hubungan dari Pemasaran mesti ditelan dalam Wawasan Pelanggan dan digunakan sebagai sumber data. Mereka juga perlu dimasukkan dalam entiti Pelanggan disatukan untuk memetakan ID pelanggan kepada ID kenalan sebelum segmen boleh dieksport.

## <a name="set-up-connection-to-marketing"></a>Sediakan sambungan ke Marketing

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Dynamics 365 Marketing** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan URL Pemasaran organisasi anda dalam medan **Alamat pelayan**.

1. Dalam bahagian **Akaun pentadbir pelayan**, pilih **Daftar masuk** dan pilih akaun Dynamics 365 Marketing.

1. Petakan medan ID Kenalan dalam entiti Pelanggan kepada ID Kenalan Dynamics 365.

1. Pilih **Simpan** untuk melengkapkan sambungan. 

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Dynamics 365 Marketing. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Pilih satu atau lebih segmen.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
