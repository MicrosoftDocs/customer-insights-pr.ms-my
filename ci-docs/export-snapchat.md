---
title: Eksport segmen ke Snapchat (pratonton)
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke Snapchat.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: abe04cd1464c3f7df969da3c769329382d603d7e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051924"
---
# <a name="export-segments-to-snapchat-preview"></a>Eksport segmen ke Snapchat (pratonton)

Eksport segmen profil pelanggan yang disatukan ke Snapchat dan gunakannya untuk pengiklanan. 

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk sambungan

-   Anda mempunyai [akaun Perniagaan Snapchat](https://business.snapchat.com/), [akaun Iklan Snapchat](https://ads.snapchat.com/), dan kelayakan pentadbir yang sepadan. YOu mesti sekurang-kurangnya menjadi ahli Akaun Organisasi dan Pengurus Data Akaun Iklan tertentu. 
-   Anda mempunyai sekurang-kurangnya satu khalayak dalam pengurus Khalayak Snapchat jenis SAM (Snap Audience Match). 
-   Anda telah [mengkonfigurasi segmen](segments.md) dalam Wawasan Pelanggan.
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Mengeksport ke Snapchat dihadkan kepada segmen.
- Mengeksport hingga 1 juta profil pelanggan kepada Snapchat boleh mengambil masa hingga 15 minit untuk dilengkapkan. 

## <a name="set-up-connection-to-snapchat"></a>Sediakan sambungan ke Snapchat

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Snapchat** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** untuk memulakan sambungan ke Snapchat.

1. Pilih **Sahkan dengan Snapchat** dan berikan kelayakan pentadbir anda untuk Snapchat. 

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Snapchat. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Masukkan [**ID Segmen Snapchat / Penonton**](https://businesshelp.snapchat.com/s/article/custom-audiences). ID penonton boleh didapati di URL selepas memilih penonton dalam Pengurus Khalayak Snapchat. 

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. Ia diperlukan untuk mengeksport segmen ke Snapchat.

1. Pilih segmen yang ingin anda eksport. 

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk memindahkan data ke Snapchat, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data tersebut atas arahan anda, tetapi anda bertanggungjawab untuk memastikan Snapchat memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.
