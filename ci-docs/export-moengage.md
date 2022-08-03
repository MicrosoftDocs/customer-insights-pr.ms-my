---
title: Eksport segmen ke MoEngage
description: Ketahui cara mengkonfigurasi sambungan dan eksport ke MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199215"
---
# <a name="export-segments-to-moengage-preview"></a>Eksport segmen ke MoEngage (pratonton)

Eksport segmen profil pelanggan bersatu ke MoEngage dan gunakannya untuk pemasaran e-mel di MoEngage.

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk sambungan

- [Akaun MoEngage](https://www.moengage.com/) dan kelayakan pentadbir yang sepadan.
- Kekunci API MoEngage dari Tetapan > API dalam MoEngage.
- [Segmen yang](segments.md) dikonfigurasikan dalam Wawasan Pelanggan.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 100'000 profil pelanggan setiap eksport ke MoEngage, yang boleh mengambil masa sehingga 15 minit. Bilangan profil pelanggan yang boleh anda eksport ke MoEngage bergantung pada kontrak anda dengan MoEngage.
- Segmen sahaja.

## <a name="set-up-connection-to-moengage"></a>Sediakan sambungan ke MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **MoEngage** untuk mengkonfigurasi sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Masukkan ID API Data MoEngage dan kekunci API anda](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan ke MoEngage.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian MoEngage. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. Ulangi langkah yang sama untuk medan pilihan lain.

1. Pilih segmen yang ingin anda eksport. Kami akan mencipta satu atau lebih segmen dengan nama yang sama dengan segmen yang dipilih dalam MoEngage di bawah **Segmen Tersuai Segmen** > **·**.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
