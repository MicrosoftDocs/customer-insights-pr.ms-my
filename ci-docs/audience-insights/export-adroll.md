---
title: Eksport data Customer Insights ke AdRoll
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124376"
---
# <a name="export-segments-to-adroll-preview"></a>Eksport segmen ke AdRoll (pratonton)

Eksport segmen profil pelanggan yang disatukan ke AdRoll dan gunakan segmen tersebut untuk pengiklanan. 

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk sambungan

-   Anda mempunyai [Akaun AdRoll](https://www.adroll.com/) dan kelayakan pentadbir yang berkaitan.
-   Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Anda boleh mengeksport hingga 250,000 profil bagi setiap eksport ke AdRoll.
- Anda tidak boleh mengeksport segmen yang kurang daripada 100 profil ke AdRoll. 
- Mengeksport ke AdRoll adalah terhad kepada segmen.
- Mengeksport hingga 250,000 profil ke AdRoll mungkin mengambil masa hingga 10 minit untuk selesai. 
- Bilangan profil yang boleh anda eksport ke AdRoll bergantung dan terhad pada kontrak anda dengan AdRoll.

## <a name="set-up-connection-to-adroll"></a>Sediakan sambungan ke AdRoll

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **AdRoll** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** untuk memulakan sambungan ke AdRoll.

1. Pilih **Sahkan dengan AdRoll** dan berikan kelayakan pentadbir anda untuk AdRoll. 

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian AdRoll. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Masukkan **ID Pengiklan AdRoll**. Untuk mendapatkan maklumat lanjut, lihat [Profil Pengiklan AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan. Ia diperlukan untuk mengeksport segmen ke AdRoll.

1. Pilih segmen yang ingin anda eksport. Pilih segmen dengan sekurang-kurangnya 100 ahli. Anda tidak boleh mengeksport segmen yang lebih kecil. Selain itu, saiz maksimum segmen untuk mengeksport ialah 250,000 ahli bagi setiap eksport. 

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke AdRoll, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif yang berpotensi seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa AdRoll memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.
