---
title: Eksport segmen ke Microsoft Advertising (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196543"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Eksport segmen ke Microsoft Advertising (pratonton)

Eksport segmen Customer Insights ke Microsoft Advertising untuk mencipta khalayak Padanan Pelanggan. Gunakan khalayak ini untuk kempen iklan anda.

## <a name="prerequisites"></a>Prasyarat

- Akaun [Pengiklanan](https://ads.microsoft.com/) Microsoft dan kelayakan pentadbir yang sepadan.
- ID Pelanggan Pengiklanan Microsoft dan ID Akaun. Cari ID Pelanggan (`cid`) dan ID Akaun (`aid`) dalam parameter URL apabila anda log masuk ke Pengiklanan Microsoft.
- Terma penggunaan Padanan Pelanggan diterima.
- [Segmen yang](segments.md) dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 500,000 profil pelanggan setiap eksport ke Pengiklanan Microsoft, yang boleh mengambil masa sehingga 10 minit.
- Segmen sahaja.

## <a name="set-up-connection-to-microsoft-advertising"></a>Sediakan sambungan ke Pengiklanan Microsoft

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Pengiklanan Microsoft**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Nilai lalai ialah pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **ID** Pelanggan Pengiklanan Microsoft.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Sahkan dengan Microsoft Advertising** dan berikan kelayakan pentadbir anda untuk Microsoft Advertising.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada bahagian Microsoft Advertising. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Pilih segmen untuk dieksport. Khalayak Padanan Pelanggan dalam Microsoft Advertising dicipta secara automatik dengan nama segmen yang dipilih untuk eksport. Setiap segmen akan menghasilkan khalayak Pemadanan Pelanggan yang berasingan.

1. Masukkan **ID Pelanggan dan ID Akaun Microsoft Advertising** anda.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan dengan alamat e-mel pelanggan.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
