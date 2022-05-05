---
title: Eksport data Customer Insights ke Microsoft Advertising
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Microsoft Advertising.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 14479e915dd6ae76e018b59bee5980a600bb222d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643914"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Eksport segmen ke Microsoft Advertising (pratonton)

Eksport segmen Customer Insights ke Microsoft Advertising untuk mencipta khalayak Padanan Pelanggan. Gunakan khalayak ini untuk kempen iklan anda.

## <a name="prerequisites"></a>Prasyarat

-   [Akaun Microsoft Advertising](https://ads.microsoft.com/) dan kelayakan pentadbir yang sepadan.
-   Anda telah menerima terma penggunaan Padanan Pelanggan. 
-   [Segmen yang](segments.md) dikonfigurasikan dalam Wawasan Pelanggan.
-   Profil pelanggan yang disatukan dalam segmen yang dieksport mengandungi medan dengan alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Anda boleh mengeksport hingga 500,000 profil pelanggan bagi setiap eksport ke Microsoft Advertising.
- Mengeksport ke Microsoft Advertising dihadkan kepada segmen.
- Mengeksport hingga 500,000 profil pelanggan kepada Microsoft Advertising boleh mengambil masa hingga 10 minit untuk dilengkapkan. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Sediakan sambungan ke Microsoft Advertising

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Microsoft Advertising** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Nilai lalai ialah pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** untuk memulakan sambungan ke Microsoft Advertising.

1. Pilih **Sahkan dengan Microsoft Advertising** dan berikan kelayakan pentadbir anda untuk Microsoft Advertising.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada bahagian Microsoft Advertising. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Pilih segmen untuk dieksport. Khalayak Padanan Pelanggan dalam Microsoft Advertising dicipta secara automatik dengan nama segmen yang dipilih untuk eksport. Setiap segmen akan menghasilkan khalayak Pemadanan Pelanggan yang berasingan. 

1. Masukkan **ID Pelanggan dan ID Akaun Microsoft Advertising** anda. Anda boleh menemui ID Pelanggan (`cid`) dan ID Akaun (`aid`) dalam parameter URL apabila anda mendaftar masuk Microsoft Advertising.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan dengan alamat e-mel pelanggan. Ia diperlukan untuk mengeksport segmen ke Microsoft Advertising.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk memindahkan data ke Microsoft Advertising, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan Microsoft Advertising memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menghentikan penggunaan kefungsian ini.
