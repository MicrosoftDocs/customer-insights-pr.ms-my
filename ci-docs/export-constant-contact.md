---
title: Eksport segmen ke Kenalan Pemalar (pratonton)
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke Constant Contact.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fe9706a7cd0755412ee18c4b974684bb9aa3f8d3
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082307"
---
# <a name="export-segments-to-constant-contact-preview"></a>Eksport segmen ke Kenalan Pemalar (pratonton)

Eksport segmen profil pelanggan yang disatukan ke Constant Contact dan gunakannya untuk aktiviti pemasaran. 

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk sambungan

-   Anda mempunyai [akaun Constant Contact](https://www.constantcontact.com/account-home) dan kelayakan pentadbir yang sepadan.
-   Anda telah [mengkonfigurasi segmen](segments.md) dalam Wawasan Pelanggan.
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Anda boleh mengeksport hingga 1 juta profil pelanggan setiap eksport untuk Kenalan Pemalar.
- Mengeksport ke Constant Contact dihadkan kepada segmen.
- Mengeksport hingga 1 juta profil pelanggan kepada Kenalan Pemalar boleh mengambil masa hingga 1 jam untuk dilengkapkan. 
- Bilangan profil pelanggan yang boleh anda eksport kepada Kenalan Pemalar bergantung dan terhad pada kontrak anda dengan Kenalan Pemalar.

## <a name="set-up-connection-to-constant-contact"></a>Sediakan sambungan ke Constant Contact

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Constant Contact** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** untuk memulakan sambungan ke Constant Contact.

1. Pilih **Sahkan dengan Kenalan Pemalar** dan berikan kelayakan pentadbir anda untuk Kenalan Pemalar. 

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Constant Contact. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Masukkan [**ID Senarai Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists) anda. Buka senarai dalam Constant Contact untuk mencari ID senarai dalam URL.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. Ia diperlukan untuk mengeksport segmen ke Constant Contact.

1. Secara alternatif, anda boleh mengeksport Nama pertama dan Nama akhir sebagai medan tambahan untuk mencipta lebih banyak e-mel peribadi. Pilih **Tambah atribut** untuk memetakan medan ini.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk memindahkan data ke Constant Contact, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data tersebut atas arahan anda, tetapi anda bertanggungjawab untuk memastikan Constant Contact memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.
