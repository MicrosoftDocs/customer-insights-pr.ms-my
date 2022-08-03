---
title: Eksport segmen ke Google ads (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196589"
---
# <a name="export-segments-to-google-ads-preview"></a>Eksport segmen ke Google ads (pratonton)

Eksport segmen profil pelanggan disatukan pada senarai khalayak Google Ads dan gunakan segmen itu untuk mengiklankan di Carian Google, Gmail YouTube dan Rangkaian Paparan Google.

## <a name="prerequisites"></a>Prasyarat

- Akaun [Google Ads](https://ads.google.com/) dan kelayakan pentadbir yang sepadan.
- [ID pelanggan Google Ads](https://support.google.com/google-ads/answer/1704344).
- Keperluan [Dasar](https://support.google.com/adspolicy/answer/6299717) Padanan Pelanggan dipenuhi.
- Keperluan [saiz](https://support.google.com/google-ads/answer/7558048) senarai pemasaran semula dipenuhi.
- [Segmen yang dikonfigurasikan](segments.md).
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel, telefon, ID pengiklan mudah alih, ID pengguna pihak ketiga atau alamat.

## <a name="known-limitations"></a>Had diketahui

- Eksport sehingga 1 juta profil pelanggan setiap eksport ke Google Ads, yang boleh mengambil masa sehingga 30 minit untuk diselesaikan kerana batasan di pihak penyedia.
- Segmen sahaja.
- Perlawanan dalam Google Ads boleh mengambil masa sehingga 48 jam.

## <a name="set-up-connection-to-google-ads"></a>Sediakan sambungan ke Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Google Ads**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan ID pelanggan Google Ads anda.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sahkan dengan Google Ads** dan berikan kelayakan Google ads anda..

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Google Ads. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Pilih sama ada untuk menggunakan khalayak sedia ada atau mencipta yang baharu:
   - Untuk mengemas kini khalayak Google Ads sedia ada, masukkan ID [khalayak Google Ads anda](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Untuk mencipta khalayak baharu, biarkan medan ID Khalayak Google kosong. Wawasan Pelanggan akan membuat khalayak baharu secara automatik dalam akaun Google Ads anda dan menggunakan nama segmen yang dieksport.

1. **Dalam seksyen Pemadanan** data, pilih satu atau lebih medan data untuk dieksport dan pilih medan yang mewakili medan data yang sepadan dalam Wawasan Pelanggan.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
