---
title: Eksport segmen ke Marketo (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195255"
---
# <a name="export-segments-to-marketo-preview"></a>Eksport segmen ke Marketo (pratonton)

Eksport segmen profil pelanggan disatukan untuk menjana kempen, menyediakan pemasaran e-mel dan gunakan kumpulan pelanggan tertentu dengan Marketo.

## <a name="prerequisites"></a>Prasyarat

- Akaun [Marketo](https://login.marketo.com/) dan kelayakan pentadbir yang sepadan.
- [ID pelanggan Marketo, rahsia Klien dan REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/).
- [Senarai sedia ada dalam Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) dan ID yang sepadan.
- [Segmen yang dikonfigurasikan](segments.md).
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 1 juta profil pelanggan setiap eksport ke Marketo, yang boleh mengambil masa sehingga 3 jam. Bilangan profil pelanggan yang boleh anda eksport ke Marketo bergantung pada kontrak anda dengan Marketo.
- Segmen sahaja.

## <a name="set-up-connection-to-marketo"></a>Sediakan sambungan ke Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Marketo**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan ID pelanggan Marketo anda **, rahsia Pelanggan dan REST Endpoint Hostname**. Nama hos Titik tamat REST adalah nama hos sahaja tanpa https://. Contoh: xyz-abc-123.mktorest.com.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Marketo. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Masukkan ID **senarai Marketo anda**. ID senarai adalah semata-mata nilai berangka. Contohnya, jika ID senarai Marketo anda ialah ST12345A7, alih keluar aksara sebelum dan selepas angka dan masukkan *12345*.

1. **Dalam bahagian Pemadanan** data, pilih sekurang-kurangnya satu medan yang mewakili alamat e-mel pelanggan atau ID Marketo pelanggan.

1. Secara pilihan, eksport **nama pertama**, **nama akhir**, Bandar **·**, **Negeri**, dan **Negara / Wilayah** untuk membuat e-mel yang lebih diperibadikan. Pilih **Tambah atribut** untuk memetakan medan ini.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Di Marketo, cari segmen anda di bawah [senarai](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) Marketo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
