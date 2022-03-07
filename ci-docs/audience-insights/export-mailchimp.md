---
title: Eksport data Customer Insights ke Mailchimp
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Mailchimp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f7a33f2eddb6b625ddb8663b97103de75beab44c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226857"
---
# <a name="export-segments-to-mailchimp-preview"></a>Eksport segmen ke Mailchimp (pratonton)

Segmen eksport profil pelanggan disatukan ke Mailchimp untuk mencipta surat berita dan kempen e-mel.

## <a name="prerequisites-for-connection"></a>Prasyarat untuk sambungan

-   Anda mempunyai [Akaun Mailchimp](https://mailchimp.com/) dan kelayakan pentadbir yang berkaitan.
-   Terdapat khalayak sedia ada dalam Mailchimp dan ID yang berkaitan. Untuk maklumat lanjut, lihat [Khalayak Mailchimp](https://mailchimp.com/help/create-audience/).
-   Anda telah [mengkonfigurasi segmen](segments.md)
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Hingga 1 juta profil pelanggan bagi setiap eksport kepada Mailchimp.
- Mengeksport ke Mailchimp adalah terhad kepada segmen.
- Mengeksport segmen dengan 1 juta profil pelanggan boleh mengambil masa sehingga tiga jam. 
- Bilangan profil pelanggan yang boleh anda eksport kepada Mailchimp bergantung dan terhad pada kontrak anda dengan Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Sediakan sambungan ke Mailchimp

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Mailchimp** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** untuk memulakan sambungan ke Mailchimp.

1. Pilih **Sahkan dengan Mailchimp** dan berikan kelayakan Mailchimp anda.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan. 

## <a name="configure-the-connector"></a>Konfigurasi penyambung

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data**> **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Mailchimp. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Masukkan **[ID khalayak Mailchimp](https://mailchimp.com/help/find-audience-id/)**

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. 

1. Selain itu, anda boleh mengeksport **Nama pertama** dan **Nama keluarga** untuk mencipta e-mel yang lebih diperibadikan. Pilih **Tambah atribut** untuk memetakan medan ini.

1. Pilih segmen yang ingin anda eksport. Anda boleh mengeksport hingga 1 juta jumlah profil pelanggan ke Mailchimp.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Mailchimp, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Mailchimp memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
