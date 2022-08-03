---
title: Eksport segmen ke Dynamics 365 Marketing (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Dynamics 365 Marketing.
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
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196635"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Eksport segmen ke Dynamics 365 Marketing (pratonton)

Gunakan [segmen](segments.md) untuk menjana kempen dan menghubungi kumpulan pelanggan tertentu dengan [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Jika anda menggunakan keupayaan baharu Dynamics 365 Marketing untuk orkestrasi perjalanan pelanggan masa nyata dalam organisasi Dataverse, anda tidak perlu mencipta eksport standard untuk Dynamics 365 Marketing. Kenalan dan segmen daripada Wawasan Pelanggan boleh didapati terus dalam Dynamics 365 Marketing selepas menyambungkan Pemasaran dan Wawasan Pelanggan. Sebelum anda memadamkan eksport sedia ada, semak dokumentasi tentang [cara menyambungkan Wawasan Pelanggan dan Orkestrasi perjalanan pelanggan Pemasaran Dynamics 365](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Prasyarat

Rekod kenalan mesti wujud dalam Dynamics 365 Marketing sebelum anda boleh mengeksport segmen daripada Customer Insights ke Pemasaran. Baca lebih lanjut tentang cara untuk menginges kenalan dalam [Dynamics 365 Marketing menggunakan Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Mengeksport segmen daripada Wawasan Pelanggan ke Pemasaran tidak akan mencipta rekod kenalan baharu dalam keadaan Pemasaran. Rekod hubungan dari Pemasaran mesti ditelan dalam Wawasan Pelanggan dan digunakan sebagai sumber data. Mereka juga perlu dimasukkan dalam entiti Pelanggan disatukan untuk memetakan ID pelanggan kepada ID kenalan sebelum segmen boleh dieksport.

## <a name="set-up-connection-to-marketing"></a>Sediakan sambungan ke Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Dynamics 365 Marketing**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan URL Pemasaran organisasi anda dalam medan **Alamat pelayan**.

1. Dalam bahagian **Akaun pentadbir pelayan**, pilih **Daftar masuk** dan pilih akaun Dynamics 365 Marketing.

1. Petakan medan ID Kenalan dalam entiti Pelanggan kepada ID Kenalan Dynamics 365.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Dynamics 365 Marketing. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Pilih medan ID Kenalan dalam entiti Pelanggan yang sepadan dengan ID Kenalan Dynamics 365.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
