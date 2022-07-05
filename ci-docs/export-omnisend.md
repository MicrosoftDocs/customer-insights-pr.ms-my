---
title: Eksport segmen ke Omnisend (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Omnisend.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 15918b2e2550869115d30ea4d84b4549c3c7d1ca
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052292"
---
# <a name="export-segments-to-omnisend-preview"></a>Eksport segmen ke Omnisend (pratonton)

Eksport segmen profil pelanggan yang disatukan ke Omnisend dan gunakan segmen tersebut untuk aktiviti pemasaran.

## <a name="prerequisites"></a>Prasyarat

-   Anda mempunyai [akaun Omnisend](https://www.omnisend.com/) dan kelayakan pentadbir yang sepadan.
-   Anda telah [mengkonfigurasi segmen](segments.md) dalam Wawasan Pelanggan.
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Anda boleh mengeksport hingga 1 juta profil pelanggan setiap eksport ke Omnisend dan ia boleh mengambil masa hingga 4 jam untuk melengkapkan.
- Mengeksport ke Omnisend dihadkan kepada segmen.
- Bilangan profil pelanggan yang boleh anda eksport kepada Omnisend bergantung pada kontrak anda dengan Omnisend.

## <a name="set-up-connection-to-omnisend"></a>Sediakan sambungan ke Omnisend

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Omnisend** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan [Kunci API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key) anda.

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** untuk memulakan sambungan ke Omnisend.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada bahagian Omnisend. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. Ia diperlukan untuk mengeksport segmen ke Omnisend. Selain itu, anda boleh mengeksport Nama pertama, Nama akhir, Alamat, Negara/Wilayah, Negeri, Bandar dan Poskod untuk mencipta e-mel yang lebih diperibadikan. Pilih **Tambah atribut** untuk memetakan medan ini.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk memindahkan data ke Ommisend, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan Ommisend memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.
