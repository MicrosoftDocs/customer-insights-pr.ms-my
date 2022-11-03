---
title: Eksport segmen ke SendGrid (pratonton)
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724859"
---
# <a name="export-segments-to-sendgrid-preview"></a>Eksport segmen ke SendGrid (pratonton)

Eksport segmen bagi profil pelanggan disatukan untuk senarai kenalan SendGrid dan gunakannya untuk kempen dan pemasaran e-mel dalam SendGrid.

## <a name="prerequisites"></a>Prasyarat

- [Akaun](https://sendgrid.com/) SendGrid dan kelayakan pentadbir yang sepadan.
- [Senarai kenalan sedia ada dalam SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) dan ID yang sepadan.
- Kekunci [API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Segmen](segments.md) yang dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Pautan peribadi dalam kombinasi dengan Bawa storan anda sendiri (BYOS) tidak disokong.
- Sehingga 100,000 profil pelanggan secara keseluruhan SendGrid, yang boleh mengambil masa sehingga beberapa jam untuk diselesaikan. Bilangan profil pelanggan yang boleh anda eksport ke SendGrid bergantung pada kontrak anda dengan SendGrid.
- Segmen sahaja.

## <a name="set-up-connection-to-sendgrid"></a>Sediakan sambungan ke SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **SendGrid**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan kekunci **API SendGrid anda**.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian SendGrid. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Masukkan ID **senarai SendGrid anda**.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan.

1. Secara pilihan, pilih medan seperti **nama pertama, nama akhir**, Negara/Rantau **, Negeri**, **·** **Bandar** **dan** Poskod.**·**

1. Pilih segmen yang ingin anda eksport berikutan had yang diketahui.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
