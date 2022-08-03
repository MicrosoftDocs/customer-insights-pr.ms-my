---
title: Eksport segmen ke RollWorks (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e13aeca4ee5309f85e7de2986cd1a2ba5d2992fb
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195623"
---
# <a name="export-segments-to-rollworks-preview"></a>Eksport segmen ke RollWorks (pratonton)

Eksport segmen profil pelanggan yang disatukan ke RollWorks dan gunakannya untuk pengiklanan.

## <a name="prerequisites"></a>Prasyarat

- Akaun [RollWorks](https://www.rollworks.com/) dan kelayakan pentadbir yang sepadan.
- [ID Pengiklan RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Segmen yang](segments.md) dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 250,000 profil pelanggan setiap eksport ke RollWorks, yang boleh mengambil masa sehingga 10 minit untuk diselesaikan. Bilangan profil pelanggan yang boleh anda eksport ke RollWorks bergantung pada kontrak anda dengan RollWorks.
- Segmen sahaja.

## <a name="set-up-connection-to-rollworks"></a>Sediakan sambungan ke RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **RollWorks**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini.  Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Sahkan dengan RollWorks** dan berikan kelayakan pentadbir anda untuk RollWorks.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian RollWorks. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Masukkan ID **Pengiklan RollWorks anda**.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
