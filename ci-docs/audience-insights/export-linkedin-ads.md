---
title: Eksport data Customer Insights ke LinkedIn Ads
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 867a6541734746f75a35faaa8d3861e0479d6114
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866899"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Eksport segmen ke LinkedIn Ads (pratonton)

Eksport segmen profil pelanggan yang disatukan kepada LinkedIn Ads untuk mencipta matched audiences. Gunakan matched audiences untuk penyasaran syarikat dan penyasaran kenalan.

## <a name="prerequisites"></a>Prasyarat

-   Anda mempunyai [akaun LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) dan kelayakan pentadbir yang sepadan.
-   Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.
-   Profil pelanggan dalam segmen yang dieksport mengandungi medan dengan alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Segmen anda dalam Wawasan Pelanggan perlu mengandungi sekurang-kurangnya 300 profil unik. 
- Anda boleh mengeksport hingga 100,000 profil pelanggan bagi setiap eksport ke Iklan LinkedIn.
- Mengeksport ke LinkedIn Ads dihadkan kepada segmen.
- Mengeksport hingga 100,000 profil pelanggan kepada Iklan LinkedIn boleh mengambil masa hingga 10 minit untuk dilengkapkan. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Sediakan sambungan ke LinkedIn Ads

1. Dalam wawasan khalayak, pergi ke **Pergi ke** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **LinkedIn Ads** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, nilai lalai ialah Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan [ID Akaun LinkedIn Campaign Manager anda](https://www.linkedin.com/help/lms/answer/a424270).

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** untuk memulakan sambungan ke Campaign Monitor.

1. Pilih **Sahkan dengan LinkedIn dan berikan kelayakan pentadbir** anda untuk LinkedIn Campaign Manager.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada bahagian LinkedIn Ads. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Pilih sama ada anda mahu mengeksport data untuk [penyasaran kenalan](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) atau [penyasaran syarikat](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) di LinkedIn. 

1. Dalam bahagian **Pemadanan Data**, untuk penyasaran kenalan, pilih sekurang-kurangnya satu medan yang mewakili alamat e-mel pelanggan, ID Iklan Apple, ID Iklan Google, ID Pengguna Google atau nama pertama dan akhir. Jika anda memilih penyasaran syarikat, pilih sekurang-kurangnya satu medan yang mewakili nama syarikat, domain e-mel, URL Halaman LinkedIn, simbol Stock atau Tapak Web. Medan tambahan boleh dipilih untuk mentakrifkan selanjutnya eksport anda. 

1. Pilih segmen yang ingin anda eksport. Khalayak yang dipadankan dalam LinkedIn Campaign Manager akan dicipta secara automatik dengan nama segmen yang anda pilih untuk dieksport. Setiap segmen akan menghasilkan matched audiences yang berasingan. 

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Iklan LinkedIn, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan LinkedIn Ads memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menghentikan penggunaan kefungsian ini.
