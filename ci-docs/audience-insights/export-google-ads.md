---
title: Eksport data Customer Insights ke Google Ads
description: Ketahui cara mengkonfigurasi sambungan ke Google ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568475"
---
# <a name="connector-for-google-ads-preview"></a>Penyambung untuk Google Ads (pratonton)

Eksport segmen profil pelanggan disatukan ke senarai khalayak Google Ads dan gunakannya untuk mengiklan pada Google Search, Gmail, YouTube dan Google Display Network. 

## <a name="prerequisites"></a>Prasyarat

-   Anda mempunyai [Akaun Google Ads](https://ads.google.com/) dan kelayakan pentadbir yang berkaitan.
-   Terdapat khalayak sedia ada dalam Google Ads dan ID yang berkaitan. Untuk maklumat lanjut, lihat [Khalayak Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Anda telah [mengkonfigurasi segmen](segments.md)
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel, nama pertama dan nama akhir

## <a name="connect-to-google-ads"></a>Sambungkan dengan Google Ads

1. Pergi ke **Pentadbir** > **Destinasi Eksport**.

1. Di bawah **Google Ads**, pilih **Sediakan**.

1. Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.

1. Masukkan **[ID pelanggan Google Ads](https://support.google.com/google-ads/answer/1704344)** anda.

1. Masukkan **[Token pembangun diluluskan Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** anda.

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Masukkan **[ID khalayak Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** anda dan pilih **Sambung** untuk memulakan sambungan ke Google Ads.

1. Pilih **Sahkan dengan Google Ads** dan berikan kelayakan Google ads anda..

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Eksport petikan skrin untuk sambungan Google Ads":::

1. Pilih **Seterusnya** untuk konfigurasi eksport.

## <a name="configure-the-connector"></a>Konfigurasi penyambung

1. Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan. Ulangi langkah yang sama untuk medan **Nama pertama** dan **Nama akhir**.

1. Pilih segmen yang ingin anda eksport. Anda boleh mengeksport hingga 1 juta profil pelanggan dalam jumlah keseluruhan Google ads.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab). Dalam Google ads, anda kini boleh mencari segmen anda di bawah [Khalayak Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Had diketahui

- Hingga 1 juta profil bagi setiap eksport ke Google ads.
- Mengeksport ke Google Ads adalah terhad kepada segmen.
- Mengeksport segmen dengan jumlah 1 juta profil boleh mengambil masa hingga 5 minit kerana had pada bahagian pembekal. 
- Pemadanan dalam Google Ads boleh mengambil masa hingga 48 jam.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Google Ads, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Google Ads memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.
