---
title: Eksport segmen ke Kenalan Pemalar (pratonton)
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c0affd3ed45f462696850813bd50331061dde780
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724512"
---
# <a name="export-segments-to-constant-contact-preview"></a>Eksport segmen ke Kenalan Pemalar (pratonton)

Eksport segmen profil pelanggan yang disatukan ke Constant Contact dan gunakannya untuk aktiviti pemasaran.

## <a name="prerequisites"></a>Prasyarat

- [Akaun](https://www.constantcontact.com/account-home) Hubungan Malar dan kelayakan pentadbir yang sepadan.
- [ID Senarai Kenalan Malar](https://app.constantcontact.com/pages/contacts/ui#lists). Buka senarai dalam Constant Contact untuk mencari ID senarai dalam URL.
- [Segmen](segments.md) yang dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Pautan peribadi dalam kombinasi dengan Bawa storan anda sendiri (BYOS) tidak disokong.
- Sehingga 1 juta profil pelanggan setiap eksport ke Constant Contact, yang boleh mengambil masa sehingga satu jam untuk diselesaikan. Bilangan profil pelanggan yang boleh anda eksport ke Constant Contact bergantung pada kontrak anda dengan Constant Contact.
- Segmen sahaja.

## <a name="set-up-connection-to-constant-contact"></a>Sediakan sambungan ke Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Constant Contact**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Sambung** untuk memulakan sambungan.

1. Pilih **Sahkan dengan Kenalan Pemalar** dan berikan kelayakan pentadbir anda untuk Kenalan Pemalar.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Constant Contact. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Masukkan ID **Senarai Kenalan Malar anda**.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan.

1. Secara pilihan, eksport **nama pertama** dan **nama akhir** sebagai medan tambahan untuk membuat e-mel yang lebih diperibadikan. Pilih **Tambah atribut** untuk memetakan medan ini.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
