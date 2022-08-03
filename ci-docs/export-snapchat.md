---
title: Eksport segmen ke Snapchat (pratonton)
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195393"
---
# <a name="export-segments-to-snapchat-preview"></a>Eksport segmen ke Snapchat (pratonton)

Eksport segmen profil pelanggan yang disatukan ke Snapchat dan gunakannya untuk pengiklanan.

## <a name="prerequisites"></a>Prasyarat

- Akaun [Perniagaan Snapchat,](https://business.snapchat.com/) akaun [Iklan](https://ads.snapchat.com/) Snapchat, dan kelayakan pentadbir yang sesuai. Anda mesti sekurang-kurangnya menjadi ahli Akaun Organisasi dan Pengurus Data Akaun Iklan tertentu.
- Sekurang-kurangnya satu penonton dalam pengurus Penonton Snapchat jenis SAM (Snap Audience Match).
- ID [Segmen Snapchat / Penonton](https://businesshelp.snapchat.com/s/article/custom-audiences). ID penonton boleh didapati di URL selepas memilih penonton dalam Pengurus Khalayak Snapchat.
- [Segmen yang](segments.md) dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 1 juta profil pelanggan, yang boleh mengambil masa sehingga 15 minit untuk diselesaikan.
- Segmen sahaja.

## <a name="set-up-connection-to-snapchat"></a>Sediakan sambungan ke Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Snapchat**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Sahkan dengan Snapchat** dan berikan kelayakan pentadbir anda untuk Snapchat.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Snapchat. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Masukkan **ID** Segmen Snapchat / Penonton.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
