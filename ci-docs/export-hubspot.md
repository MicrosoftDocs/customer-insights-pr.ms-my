---
title: Eksport data Wawasan Pelanggan ke HubSpot
description: Ketahui cara mengkonfigurasi sambungan dan eksport ke HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588934"
---
# <a name="export-segments-to-hubspot-preview"></a>Eksport segmen ke HubSpot (pratonton)

Eksport segmen profil pelanggan bersatu ke HubSpot dan gunakannya untuk pemasaran e-mel.

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk sambungan

- Akaun [HubSpot](https://www.hubspot.com/) dan kelayakan pentadbir yang sepadan.
- [Kunci](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) API daripada HubSpot.
- [Segmen yang](segments.md) dikonfigurasikan dalam Wawasan Pelanggan.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 100'000 profil pelanggan setiap eksport ke HubSpot, yang boleh mengambil masa sehingga 15 minit untuk diselesaikan. Bilangan profil pelanggan yang boleh anda eksport ke HubSpot bergantung dan terhad pada kontrak anda dengan HubSpot.
- Segmen sahaja.

## <a name="set-up-connection-to-hubspot"></a>Sediakan sambungan ke HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **HubSpot** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan kelayakan HubSpot anda apabila digesa.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan ke HubSpot.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada bahagian HubSpot. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. Ulangi langkah yang sama untuk medan pilihan lain.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
