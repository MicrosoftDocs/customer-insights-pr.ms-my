---
title: Eksport segmen ke Campaign Monitor (pratonton)
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196313"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Eksport segmen ke Campaign Monitor (pratonton)

Eksport segmen profil pelanggan yang disatukan ke Campaign Monitor dan gunakannya untuk aktiviti pemasaran.

## <a name="prerequisites"></a>Prasyarat

- Akaun [Monitor](https://www.campaignmonitor.com/) Kempen dan kelayakan pentadbir yang sepadan.
- [ID Senarai Monitor Kempen](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Kunci [API](https://www.campaignmonitor.com/api/getting-started/) Dijana daripada **Tetapan** Akaun dalam Monitor Kempen untuk mendapatkan ID senarai API.
- [Segmen yang](segments.md) dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 1 juta profil pelanggan setiap eksport ke Monitor Kempen, yang boleh mengambil masa sehingga 20 minit untuk diselesaikan. Bilangan profil pelanggan yang boleh anda eksport ke Monitor Kempen bergantung pada kontrak anda dengan Monitor Kempen.
- Segmen sahaja.

## <a name="set-up-connection-to-campaign-monitor"></a>Sediakan sambungan ke Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Monitor** Kempen.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan ke Campaign Monitor.

1. Pilih **Sahkan dengan Campaign Monitor** dan berikan kelayakan pentadbir anda untuk Campaign Monitor.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Campaign Monitor. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Masukkan ID **Senarai Monitor Kempen anda**.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. Ia diperlukan untuk mengeksport segmen ke Campaign Monitor.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
