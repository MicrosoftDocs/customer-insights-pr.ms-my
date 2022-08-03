---
title: Eksport segmen ke ActiveCampaign
description: Ketahui cara mengkonfigurasikan sambungan dan mengeksport pada ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 178d2df8edf1abcec72664e19d73a88f2b97f12d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195577"
---
# <a name="export-segments-to-activecampaign-preview"></a>Eksport segmen pada ActiveCampaign (pratonton)

Eksport segmen profil pelanggan disatukan pada ActiveCampaign dan gunakan segmen itu untuk aktiviti pemasaran.

## <a name="prerequisites"></a>Prasyarat

- Akaun [ActiveCampaign](https://www.activecampaign.com/) dan kelayakan pentadbir yang sepadan.
- [ID Senarai ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- [Kekunci](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) API ActiveCampaign dan Rest Endpoint Hostname.
- [Segmen yang](segments.md) dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 1 juta profil pelanggan setiap eksport ke ActiveCampaign, yang boleh mengambil masa sehingga 90 minit untuk diselesaikan. Bilangan profil pelanggan yang boleh anda eksport kepada ActiveCampaign bergantung pada kontrak anda dengan ActiveCampaign anda.
- Segmen sahaja.

## <a name="set-up-connection-to-activecampaign"></a>Sediakan sambungan kepada ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **ActiveCampaign**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan Kekunci API ActiveCampaign dan Nama Hos Titik Tamat REST anda. Nama hos Titik tamat REST adalah nama hos sahaja tanpa https://.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk mengeksport**, pilih sambungan daripada bahagian ActiveCampaign. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Masukkan ID **Senarai ActiveCampaign anda**.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan.

1. Secara pilihan, eksport **nama pertama**, **nama akhir** dan **Telefon** untuk membuat e-mel yang lebih diperibadikan. Pilih **Tambah atribut** untuk memetakan medan ini.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
