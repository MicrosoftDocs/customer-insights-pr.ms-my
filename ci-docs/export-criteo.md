---
title: Eksport segmen ke Criteo (pratonton)
description: Ketahui cara mengkonfigurasi sambungan dan eksport ke Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d7c8d6f0121fe18a6c886ba3776109a1a592ef33
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195347"
---
# <a name="export-segments-to-criteo-preview"></a>Eksport segmen ke Criteo (pratonton)

Eksport segmen profil pelanggan bersatu untuk menjana kempen, menyediakan pemasaran e-mel dan menggunakan kumpulan pelanggan tertentu dengan Criteo.

## <a name="prerequisites"></a>Prasyarat

- Akaun [penargetan](https://www.criteo.com/login/) Semula Criteo Dynamics dan kelayakan pentadbir yang sepadan.
- [Segmen yang dikonfigurasikan](segments.md).
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 1 juta profil pelanggan setiap eksport ke Criteo, yang boleh mengambil masa sehingga 30 minit untuk diselesaikan. Bilangan profil pelanggan yang boleh anda eksport ke Criteo bergantung pada kontrak anda dengan Criteo.
- Segmen sahaja.

## <a name="set-up-connection-to-criteo"></a>Sediakan sambungan ke Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Criteo**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Sahkan dengan Criteo** dan berikan nama pengguna dan kelayakan Pentadbir anda untuk Criteo.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada seksyen Criteo. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan.

1. Secara pilihan, eksport **ID** pengiklan dan **Nama**.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
