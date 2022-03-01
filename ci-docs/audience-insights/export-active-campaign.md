---
title: Eksport Data Customer Insights pada ActiveCampaign
description: Ketahui cara mengkonfigurasikan sambungan dan mengeksport pada ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314650"
---
# <a name="export-segments-to-activecampaign-preview"></a>Eksport segmen pada ActiveCampaign (pratonton)

Eksport segmen profil pelanggan disatukan pada ActiveCampaign dan gunakan segmen itu untuk aktiviti pemasaran.

## <a name="prerequisites"></a>Prasyarat

-   Anda mempunyai [Akaun ActiveCampaign](https://www.activecampaign.com/) dan kelayakan pentadbir yang sepadan.
-   Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.
-   Profil pelanggan yang disatukan dalam segmen yang dieksport mengandungi medan dengan alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Anda boleh mengeksport hingga 1 juta profil setiap eksport pada ActiveCampaign dan ini boleh mengambil masa hingga 90 minit untuk selesai.
- Mengeksport pada ActiveCampaign terhad kepada segmen.
- Bilangan profil yang boleh anda eksport pada ActiveCampaign bergantung pada kontrak anda dengan ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Sediakan sambungan kepada ActiveCampaign

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan**  dan pilih **ActiveCampaign**  untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan [Kekunci API ActiveCampaign dan Nama Hos Titik Tamat REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) anda. Nama hos Titik tamat REST adalah nama hos sahaja tanpa https://. 

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** kepada memulakan untuk mengesahkan sambungan kepada ActiveCampaign.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk mengeksport**, pilih sambungan daripada bahagian ActiveCampaign. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Masukkan [**ID Senarai ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

3. Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan. Ini diperlukan untuk mengeksport segmen pada ActiveCampaign. Sebagai pilihan, anda boleh mengeksport Nama pertama, Nama akhir dan Telefon untuk mencipta e-mel yang lebih diperibadikan. Pilih Tambah atribut untuk memetakan medan ini.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data kepada ActiveCampaign, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif yang berpotensi seperti Data Peribadi. Microsoft akan memindahkan data tersebut atas arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa ActiveCampaign memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.
