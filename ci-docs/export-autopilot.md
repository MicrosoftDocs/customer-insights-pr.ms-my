---
title: Eksport segmen ke Autopilot (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 449d2c5e32697e4a5d2c9dff4a5a1cbdb26aeb4d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195071"
---
# <a name="export-segments-to-autopilot-preview"></a>Eksport segmen ke Autopilot (pratonton)

Eksport segmen bagi profil pelanggan disatukan untuk Autopilot dan gunakannya untuk pemasaran e-mel dalam Autopilot.

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk sambungan

- Akaun [Autopilot](https://www.autopilothq.com/) dan kelayakan pentadbir yang sepadan.
- Kekunci [API Autopilot](https://autopilot.docs.apiary.io/#)
- [Segmen yang](segments.md) dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 100,000 profil pelanggan setiap eksport ke Autopilot, yang boleh mengambil masa sehingga beberapa jam untuk diselesaikan. Bilangan profil pelanggan yang boleh anda eksport ke Autopilot bergantung pada kontrak anda dengan Autopilot.
- Segmen sahaja.

## <a name="set-up-connection-to-autopilot"></a>Sediakan sambungan ke Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Autopilot**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan Kekunci API autopilot anda.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Autopilot. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan.

1. Secara pilihan, eksport medan lain seperti **nama pertama** dan **nama akhir**.

1. Pilih segmen yang anda ingin eksport yang mematuhi had yang diketahui.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
