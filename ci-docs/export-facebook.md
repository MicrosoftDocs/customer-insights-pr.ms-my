---
title: Segmen eksport ke Facebook Pengurus Iklan (pratonton) (mengandungi video)
description: Ketahui cara untuk mengkonfigurasikan sambungan dan Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724615"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Segmen eksport ke Facebook Pengurus Iklan (pratonton)

Eksport segmen profil pelanggan disatukan ke Pengurus Iklan Facebook untuk mencipta kempen pada Facebook dan Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Prasyarat

- [Facebook Akaun Iklan yang merangkumi](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) Akaun [Facebook Perniagaan](https://business.facebook.com/).
- Keistimewaan pentadbir pada [Facebook Akaun Iklan](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Terma Khalayak Tersuai perlu diterima oleh pengguna yang menyediakan sambungan dalam Wawasan Pelanggan.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 10 juta profil pelanggan setiap eksport ke Facebook Pengurus Iklan, yang boleh mengambil masa sehingga 90 minit.
- Segmen sahaja.
- Facebook Penyepaduan iklan tidak menyokong pengguna dengan lebih daripada 25 akaun iklan.
- Facebook *Senarai* pelanggan taipkan [khalayak](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) tersuai sahaja.
  > [!NOTE]
  > Dalam sesetengah kes, anda mungkin melihat khalayak tersuai pelbagai jenis dalam senarai juntai bawah. Jika anda memilih jenis lain selain *daripada senarai* pelanggan, eksport gagal.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Sediakan sambungan ke Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Facebook Pengurus** Iklan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. [Benarkan penyumbang menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sahkan dengan Facebook Ads:

   1. Pilih **Teruskan dengan Facebook** untuk log masuk ke akaun Iklan Facebook anda.

   1. Benarkan keizinan **ads_management** selepas pengesahan dengan Facebook.

   1. Pilih **Akaun Iklan Facebook** yang anda ingin kendalikan.

   1. Pilih **khalayak tersuai sedia ada** daripada senarai juntai bawah atau cipta **Khalayak tersuai baharu**.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. **Dalam medan Sambungan untuk eksport**, pilih sambungan daripada Facebook bahagian Pengurus Iklan. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Dalam medan Sambungkan **data**, pilih **E-mel**, **Nama dan alamat** atau **Telefon** untuk dihantar kepada Facebook Pengurus Iklan.

1. Petakan atribut yang sepadan daripada entiti pelanggan disatukan anda untuk pengecam kunci yang dipilih.
   > [!TIP]
   > Peluang terbaik untuk padanan berlaku jika anda memilih **E-mel** sebagai pengecam kunci. Menambah pengecam tambahan mungkin meningkatkan pemadanan.

1. Pilih **Tambah atribut** untuk memetakan lebih banyak atribut untuk dihantar kepada Facebook Ads Manager. Atribut daripada Pengurus Iklan Facebook dipetakan pada nama mesra pengguna berikut: **FN** = **Nama Pertama**, **LN** = **Nama Keluarga**, **FI** = **Parap Pertama**, **PHONE** = **Telefon**, **GEN** = **Jantina**, **DOB** = **Tarikh Lahir**, **ST** = **Negeri**, **CT** = **Bandar**, **ZIP** = **Poskod/Kod Zip**, **COUNTRY** = **Negara/Rantau**

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
