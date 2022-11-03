---
title: Eksport data Wawasan Pelanggan ke HubSpot
description: Ketahui cara mengkonfigurasi sambungan dan mengeksport ke HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725365"
---
# <a name="export-segments-to-hubspot-preview"></a>Segmen eksport ke HubSpot (pratonton)

Eksport segmen profil pelanggan bersatu ke HubSpot dan gunakannya untuk pemasaran e-mel.

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk sambungan

- A HubSpot [akaun](https://www.hubspot.com/) dan kelayakan pentadbir yang sepadan.
- [Kekunci](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) API daripada HubSpot.
- [Segmen](segments.md) yang dikonfigurasikan dalam Wawasan Pelanggan.

## <a name="known-limitations"></a>Had diketahui

- Pautan peribadi dalam kombinasi dengan Bawa storan anda sendiri (BYOS) tidak disokong.
- Sehingga 100'000 profil pelanggan setiap eksport ke HubSpot, yang boleh mengambil masa sehingga 15 minit untuk diselesaikan. Bilangan profil pelanggan yang boleh anda eksport ke HubSpot bergantung dan terhad pada kontrak anda dengan HubSpot.
- Segmen sahaja.

## <a name="set-up-connection-to-hubspot"></a>Menyediakan sambungan ke HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan dan pilih** HubSpot **untuk mengkonfigurasi sambungan**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan anda HubSpot kelayakan apabila digesa.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan ke HubSpot.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah eksport**.

1. **Dalam medan Sambungan untuk eksport**, pilih sambungan daripada bahagian HubSpot. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. Ulangi langkah yang sama untuk medan pilihan lain.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
