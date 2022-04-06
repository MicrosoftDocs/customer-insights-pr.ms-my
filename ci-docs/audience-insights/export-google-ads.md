---
title: Eksport data Customer Insights ke Google Ads
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7a85237f7aff564d6b540b2c11553a52f875fac4
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523811"
---
# <a name="export-segments-to-google-ads-preview"></a>Eksport segmen ke Google ads (pratonton)

Eksport segmen profil pelanggan disatukan pada senarai khalayak Google Ads dan gunakan segmen itu untuk mengiklankan di Carian Google, Gmail YouTube dan Rangkaian Paparan Google. 


## <a name="prerequisites-for-connection"></a>Prasyarat untuk sambungan

-   Anda mempunyai [Akaun Google Ads](https://ads.google.com/) dan kelayakan pentadbir yang berkaitan.
-   Anda memenuhi keperluan [Dasar Padanan Pelanggan](https://support.google.com/adspolicy/answer/6299717).
-   Anda memenuhi keperluan [saiz senarai pemasaran semula](https://support.google.com/google-ads/answer/7558048).
-   Anda telah [mengkonfigurasi segmen](segments.md).
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel, telefon, ID pengiklan mudah alih, ID pengguna pihak ketiga atau alamat.

## <a name="known-limitations"></a>Had diketahui

- Mengeksport ke Google Ads adalah terhad kepada segmen.
- Segmen eksport dengan jumlah 1 juta profil pelanggan boleh mengambil masa hingga 30 minit kerana had pada bahagian pembekal. 
- Pemadanan dalam Google Ads boleh mengambil masa hingga 48 jam.

## <a name="set-up-connection-to-google-ads"></a>Sediakan sambungan ke Google Ads

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Google Ads** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **[ID pelanggan Google Ads](https://support.google.com/google-ads/answer/1704344)** anda.

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sahkan dengan Google Ads** dan berikan kelayakan Google ads anda..

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan. 

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Google Ads. Jika anda tidak melihat nama bahagian ini, maka tiada sambungan jenis ini tersedia untuk anda.

1. Jika anda ingin mencipta khalayak baharu, biarkan medan ID Khalayak Google kosong. Kami akan membuat khalayak baharu secara automatik dalam akaun Google Ads anda dan menggunakan nama segmen yang dieksport. Jika anda ingin mengemas kini khalayak Google Ads sedia ada, masukkan ID khalayak Google Ads [anda](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. **Dalam seksyen Pemadanan** data, pilih satu atau lebih medan data untuk dieksport dan pilih medan yang mewakili medan data yang sepadan dalam Wawasan Pelanggan.

1. Pilih segmen yang ingin anda eksport. 

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). 

Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Google Ads, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Google Ads memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
