---
title: Eksport segmen ke Mailchimp (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d74672768afec94e899ff0aec8c118c2afcde368
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725043"
---
# <a name="export-segments-to-mailchimp-preview"></a>Eksport segmen ke Mailchimp (pratonton)

Segmen eksport profil pelanggan disatukan ke Mailchimp untuk mencipta surat berita dan kempen e-mel.

## <a name="prerequisites"></a>Prasyarat

- [Akaun](https://mailchimp.com/) Mailchimp dan kelayakan pentadbir yang sepadan.
- [Khalayak sedia ada di Mailchimp](https://mailchimp.com/help/create-audience/) dan ID khalayak yang [sepadan](https://mailchimp.com/help/find-audience-id/).
- [Segmen yang dikonfigurasikan](segments.md).
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Pautan peribadi dalam kombinasi dengan Bawa storan anda sendiri (BYOS) tidak disokong.
- Sehingga 1 juta profil pelanggan setiap eksport ke Mailchimp, yang boleh mengambil masa sehingga tiga jam. Bilangan profil pelanggan yang boleh anda eksport ke Mailchimp bergantung pada kontrak anda dengan Mailchimp.
- Segmen sahaja.

## <a name="set-up-connection-to-mailchimp"></a>Sediakan sambungan ke Mailchimp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Mailchimp**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Sahkan dengan Mailchimp** dan berikan kelayakan Mailchimp anda.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Mailchimp. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Masukkan ID **khalayak Mailchimp anda**.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan.

1. Secara pilihan, eksport **nama pertama** dan **nama akhir** untuk membuat e-mel yang lebih diperibadikan. Pilih **Tambah atribut** untuk memetakan medan ini.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
