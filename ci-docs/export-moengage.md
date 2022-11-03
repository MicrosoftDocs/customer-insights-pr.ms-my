---
title: Segmen eksport ke MoEngage
description: Ketahui cara mengkonfigurasi sambungan dan mengeksport ke MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725277"
---
# <a name="export-segments-to-moengage-preview"></a>Segmen eksport ke MoEngage (pratonton)

Eksport segmen profil pelanggan bersatu ke MoEngage dan gunakannya untuk pemasaran e-mel di MoEngage.

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk sambungan

- [Akaun](https://www.moengage.com/) MoEngage dan kelayakan pentadbir yang sepadan.
- Kekunci API MoEngage daripada Settings > API dalam MoEngage.
- [Segmen](segments.md) yang dikonfigurasikan dalam Wawasan Pelanggan.

## <a name="known-limitations"></a>Had diketahui

- Pautan peribadi dalam kombinasi dengan Bawa storan anda sendiri (BYOS) tidak disokong.
- Sehingga 100'000 profil pelanggan setiap eksport ke MoEngage, yang boleh mengambil masa sehingga 15 minit. Bilangan profil pelanggan yang boleh anda eksport ke MoEngage bergantung pada kontrak anda dengan MoEngage.
- Segmen sahaja.

## <a name="set-up-connection-to-moengage"></a>Sediakan sambungan kepada MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan dan pilih** MoEngage **untuk mengkonfigurasikan sambungan**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan ID API Data MoEngage dan kunci API [anda](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan ke MoEngage.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah eksport**.

1. **Dalam medan Sambungan untuk eksport**, pilih sambungan daripada seksyen MoEngage. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. Ulangi langkah yang sama untuk medan pilihan lain.

1. Pilih segmen yang ingin anda eksport. Kami akan mencipta satu atau lebih segmen dengan nama yang sama seperti segmen terpilih dalam MoEngage di bawah **Segmen Tersuai Segmen** > **·**.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
