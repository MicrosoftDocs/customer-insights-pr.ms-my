---
title: Eksport segmen ke DotDigital (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724997"
---
# <a name="export-segments-to-dotdigital-preview"></a>Eksport segmen ke DotDigital (pratonton)

Eksport segmen profil pelanggan disatukan ke buku alamat DotDigital dan gunakannya untuk kempen, pemasaran e-mel dan untuk membina segmen pelanggan dengan DotDigital.

## <a name="prerequisites"></a>Prasyarat

- Akaun [DotDigital](https://dotdigital.com/) dan [pengguna API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- ID DotDigital daripada [buku alamat baharu](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) atau sedia ada dalam DotDigital. ID boleh ditemui dalam URL apabila anda memilih dan membuka buku alamat.
- [Segmen](segments.md) yang dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Pautan peribadi dalam kombinasi dengan Bawa storan anda sendiri (BYOS) tidak disokong.
- Sehingga 1 juta profil pelanggan setiap eksport ke DotDigital, yang boleh mengambil masa sehingga tiga jam untuk diselesaikan kerana batasan di pihak penyedia. Bilangan profil pelanggan yang boleh anda eksport ke DotDigital bergantung pada kontrak anda dengan DotDigital.
- Segmen sahaja.

## <a name="set-up-connection-to-dotdigital"></a>Sediakan sambungan ke DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **DotDigital**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama pengguna dan kata laluan API DotDigital** anda.

1. Masukkan ID **buku alamat DotDigital anda**.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian DotDigital. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan.

1. Secara pilihan, eksport **nama pertama**, nama akhir **,** Nama **penuh, Jantina**, **dan** **kod** pos.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Dalam DotDigital, cari segmen anda dalam [buku](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) alamat DotDigital.

[!INCLUDE [footer-include](includes/footer-banner.md)]
