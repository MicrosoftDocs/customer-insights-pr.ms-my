---
title: Eksport Data Customer Insights pada Sendinblue
description: Ketahui cara mengkonfigurasikan sambungan dan mengeksport pada Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e6d63e0017caa50379426cd5f9b663571b568de7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643243"
---
# <a name="export-segments-to-sendinblue-preview"></a>Eksport segmen pada Sendinblue (pratonton)

Eksport segmen profil pelanggan disatukan untuk menjana kempen, menyediakan pemasaran e-mel dan menggunakan kumpulan pelanggan khusus dengan Sendinblue.

## <a name="prerequisites-for-connection"></a>Prasyarat untuk sambungan

-   Anda mempunyai [Akaun Sendinblue](https://www.sendinblue.com/) dan kelayakan pentadbir yang sepadan.
-   Terdapat senarai sedia ada dalam Sendinblue dan ID yang sepadan.
-   Anda telah [mengkonfigurasi segmen](segments.md).
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Hingga 1 juta profil pelanggan bagi setiap eksport Sendinblue.
- Mengeksport pada Sendinblue terhad kepada segmen.
- Mengeksport segmen dengan jumlah 1 juta profil pelanggan boleh mengambil masa hingga 90 minit. 
- Bilangan profil pelanggan yang boleh anda eksport kepada Sendinblue bergantung dan terhad pada kontrak anda dengan Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Sediakan sambungan kepada Sendinblue

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Sendinblue** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **[Kunci API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)** anda.

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data** dan pilih **Sambung** untuk memulakan sambungan kepada Sendinblue.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk mengeksport**, pilih sambungan daripada bahagian Sendinblue. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Masukkan **ID senarai Sendinblue** anda 

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. 

1. Sebagai pilihan, anda boleh mengeksport **Nama pertama**, **Nama akhir**, dan **Telefon** untuk mencipta e-mel yang lebih diperibadikan. Pilih **Tambah atribut** untuk memetakan medan ini.

1. Pilih segmen yang ingin anda eksport. 

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data kepada Sendinblue, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif yang berpotensi seperti Data Peribadi. Microsoft akan memindahkan data tersebut atas arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa Sendinblue memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE [footer-include](includes/footer-banner.md)]
