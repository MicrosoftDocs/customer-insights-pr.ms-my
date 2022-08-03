---
title: Eksport segmen ke LinkedIn Ads (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke LinkedIn Ads.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d1a9ae985043398f4bc38163be26ecf0c3c8e2ba
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196819"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Eksport segmen ke LinkedIn Ads (pratonton)

Eksport segmen profil pelanggan yang disatukan kepada LinkedIn Ads untuk mencipta matched audiences. Gunakan matched audiences untuk penyasaran syarikat dan penyasaran kenalan.

## <a name="prerequisites"></a>Prasyarat

- Akaun [LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) dan kelayakan pentadbir yang sepadan.
- [LinkedIn Campaign Manager ID Akaun](https://www.linkedin.com/help/lms/answer/a424270).
- [Segmen yang](segments.md) dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 100,000 profil pelanggan setiap eksport ke Iklan LinkedIn, yang boleh mengambil masa sehingga 10 minit untuk diselesaikan.
- Segmen sahaja. Segmen mesti mengandungi sekurang-kurangnya 300 profil unik.

## <a name="set-up-connection-to-linkedin-ads"></a>Sediakan sambungan ke Iklan LinkedIn

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Iklan LinkedIn**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan ID Akaun anda LinkedIn Campaign Manager.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Sahkan dengan LinkedIn** dan berikan kelayakan pentadbir anda untuk LinkedIn Campaign Manager.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada bahagian LinkedIn Ads. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Pilih sama ada anda mahu mengeksport data untuk [penyasaran kenalan](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) atau [penyasaran syarikat](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) di LinkedIn.

1. Dalam bahagian **Pemadanan Data**, untuk penyasaran kenalan, pilih sekurang-kurangnya satu medan yang mewakili alamat e-mel pelanggan, ID Iklan Apple, ID Iklan Google, ID Pengguna Google atau nama pertama dan akhir. Jika anda memilih penyasaran syarikat, pilih sekurang-kurangnya satu medan yang mewakili nama syarikat, domain e-mel, URL Halaman LinkedIn, simbol Stock atau Tapak Web.

1. Secara pilihan, tambah medan untuk mentakrifkan eksport anda dengan lebih lanjut. Pilih **Tambah atribut** untuk memetakan medan ini.

1. Pilih segmen yang ingin anda eksport. Matched audiences dalam LinkedIn Campaign Manager akan dicipta secara automatik dengan nama segmen yang anda pilih untuk dieksport. Setiap segmen akan menghasilkan matched audiences yang berasingan.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
