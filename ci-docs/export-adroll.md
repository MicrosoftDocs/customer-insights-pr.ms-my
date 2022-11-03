---
title: Eksport segmen ke AdRoll (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 81adad4caf2d4c6f792bf920b29fc7c67eef42b0
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724723"
---
# <a name="export-segments-to-adroll-preview"></a>Eksport segmen ke AdRoll (pratonton)

Eksport segmen profil pelanggan yang disatukan ke AdRoll dan gunakan segmen tersebut untuk pengiklanan.

## <a name="prerequisites"></a>Prasyarat

- Akaun [AdRoll](https://www.adroll.com/) dan kelayakan pentadbir yang sepadan.
- [ID Pengiklan AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Segmen](segments.md) yang dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Pautan peribadi dalam kombinasi dengan Bawa storan anda sendiri (BYOS) tidak disokong.
- Sehingga 250,000 profil pelanggan setiap eksport ke AdRoll, yang boleh mengambil masa sehingga 10 minit untuk diselesaikan. Bilangan profil pelanggan yang boleh anda eksport ke AdRoll bergantung pada kontrak anda dengan AdRoll.
- Segmen sahaja. Segmen mesti mengandungi sekurang-kurangnya 100 profil pelanggan.

## <a name="set-up-connection-to-adroll"></a>Sediakan sambungan ke AdRoll

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **AdRoll**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Sahkan dengan AdRoll** dan berikan kelayakan pentadbir anda untuk AdRoll.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian AdRoll. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Masukkan **ID Pengiklan AdRoll anda**.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
