---
title: Segmen eksport ke Iterable (pratonton)
description: Ketahui cara mengkonfigurasi sambungan dan mengeksport ke Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 69e2bd207c98fc2530620018bf95dd869d1798f6
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724557"
---
# <a name="export-segments-to-iterable-preview"></a>Segmen eksport ke Iterable (pratonton)

Eksport segmen profil pelanggan bersatu ke Iterable dan menggunakannya untuk aktiviti pemasaran.

## <a name="prerequisites"></a>Prasyarat

- Akaun [Iterable](https://iterable.com/) dan kelayakan pentadbir yang sepadan.
- Kekunci [API yang Boleh Diterima](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Segmen](segments.md) yang dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Pautan peribadi dalam kombinasi dengan Bawa storan anda sendiri (BYOS) tidak disokong.
- Sehingga 1 juta profil pelanggan ke Iterable, yang boleh mengambil masa sehingga 30 minit untuk diselesaikan. Bilangan profil pelanggan yang boleh anda eksport ke Iterable bergantung pada kontrak anda dengan Iterable.
- Segmen sahaja.

## <a name="set-up-connection-to-iterable"></a>Menyediakan sambungan kepada Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Boleh Diterima**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan kunci API Iterable anda untuk terus log masuk.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada seksyen Boleh Lelar. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. Senarai yang dibuat dalam Iterable akan menerima nama yang sama seperti nama segmen anda dalam Dynamics 365 Customer Insights.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
