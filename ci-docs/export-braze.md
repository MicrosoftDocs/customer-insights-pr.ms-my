---
title: Eksport segmen ke Braze (pratonton)
description: Ketahui cara mengkonfigurasi sambungan dan eksport ke Braze.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 84dc7f13f30e0334d431fe5b5866c7f87e82ab27
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195118"
---
# <a name="export-segments-to-braze-preview"></a>Eksport segmen ke Braze (pratonton)

Eksport segmen profil pelanggan bersatu ke Braze dan gunakannya untuk aktiviti pemasaran.

## <a name="prerequisites"></a>Prasyarat

- Akaun [Braze](https://www.braze.com/) dan kelayakan pentadbir yang sepadan.
- Kekunci [API Braze](https://www.braze.com/docs/api/basics/)
- [Segmen yang](segments.md) dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan bersatu dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel dan ID pelanggan Braze.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 1 juta profil pelanggan ke Braze, yang boleh mengambil masa sehingga 40 minit untuk diselesaikan. Bilangan profil pelanggan yang boleh anda eksport ke Braze bergantung pada kontrak anda dengan Braze.
- Segmen sahaja.

## <a name="set-up-connection-to-braze"></a>Sediakan sambungan ke Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Braze**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan kekunci API Braze anda untuk terus log masuk.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada bahagian Braze. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. **Dalam medan ID** Pelanggan, pilih medan yang mewakili ID Braze pelanggan. Segmen dalam Braze akan dicipta dengan nama segmen yang sama seperti dalam Dynamics 365 Customer Insights. Anda boleh memilih lebih banyak, medan pilihan untuk memadankan data.

1. Pilih entiti atau segmen yang anda mahu eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
