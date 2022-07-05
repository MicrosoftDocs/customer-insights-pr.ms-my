---
title: Eksport segmen ke Criteo (pratonton)
description: Ketahui cara mengkonfigurasi sambungan dan eksport ke Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082790"
---
# <a name="export-segments-to-criteo-preview"></a>Eksport segmen ke Criteo (pratonton)

Eksport segmen profil pelanggan bersatu untuk menjana kempen, menyediakan pemasaran e-mel dan menggunakan kumpulan pelanggan tertentu dengan Criteo.

## <a name="prerequisites-for-connection"></a>Prasyarat untuk sambungan

-   Anda mempunyai [akaun](https://www.criteo.com/login/) penargetan Semula Criteo Dynamics dan kelayakan pentadbir yang sepadan.
-   Anda telah [mengkonfigurasi segmen](segments.md).
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Sehingga 1 juta profil pelanggan setiap eksport ke Criteo.
- Mengeksport ke Criteo adalah terhad kepada segmen.
- Mengeksport segmen dengan jumlah 1 juta profil pelanggan boleh mengambil masa hingga 30 minit. 
- Bilangan profil pelanggan yang boleh anda eksport ke Criteo bergantung dan terhad pada kontrak anda dengan Criteo.

## <a name="set-up-connection-to-criteo"></a>Sediakan sambungan ke Criteo

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Criteo** untuk mengkonfigurasi sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih **Saya bersetuju** untuk mengesahkan **privasi dan pematuhan** Data dan pilih **Sambung** untuk memulakan sambungan ke Criteo.

1. Pilih **Sahkan dengan Criteo** dan berikan nama pengguna dan kelayakan Pentadbir anda untuk Criteo. 

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada seksyen Criteo. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda. 

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. 

1. Secara pilihan, anda boleh mengeksport **ID** pengiklan dan **Nama**

1. Pilih segmen yang ingin anda eksport. 

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Criteo, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa Criteo memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](includes/footer-banner.md)]
