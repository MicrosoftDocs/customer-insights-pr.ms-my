---
title: Eksport segmen pada Sendinblue (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan mengeksport pada Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 816a3b242fadaa5a75db878adf0a76baf638e41c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196957"
---
# <a name="export-segments-to-sendinblue-preview"></a>Eksport segmen pada Sendinblue (pratonton)

Eksport segmen profil pelanggan disatukan untuk menjana kempen, menyediakan pemasaran e-mel dan menggunakan kumpulan pelanggan khusus dengan Sendinblue.

## <a name="prerequisites"></a>Prasyarat

- Akaun [Sendinblue](https://www.sendinblue.com/) dan kelayakan pentadbir yang sesuai.
- Kekunci [API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Senarai sedia ada dalam Sendinblue dan ID yang sepadan.
- [Segmen yang dikonfigurasikan](segments.md).
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 1 juta profil pelanggan setiap eksport ke Sendinblue, yang boleh mengambil masa sehingga 90 minit untuk diselesaikan. Bilangan profil pelanggan yang boleh anda eksport ke Sendinblue bergantung pada kontrak anda dengan Sendinblue.
- Segmen sahaja.

## <a name="set-up-connection-to-sendinblue"></a>Sediakan sambungan kepada Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Sendinblue**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan kekunci **API SendinBlue anda**.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk mengeksport**, pilih sambungan daripada bahagian Sendinblue. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Masukkan ID **senarai Sendinblue anda**.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan.

1. Secara pilihan, eksport **nama pertama**, **nama akhir** dan **Telefon** untuk membuat e-mel yang lebih diperibadikan. Pilih **Tambah atribut** untuk memetakan medan ini.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
