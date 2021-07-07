---
title: Eksport data Customer Insights ke Microsoft Advertising
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124525"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Eksport segmen ke Microsoft Advertising (pratonton)

Eksport segmen Customer Insights ke Microsoft Advertising untuk mencipta khalayak Padanan Pelanggan. Gunakan khalayak ini untuk kempen iklan anda.

## <a name="prerequisites"></a>Prasyarat

-   [Akaun Microsoft Advertising](https://ads.microsoft.com/) dan kelayakan pentadbir yang sepadan.
-   Anda telah menerima terma penggunaan Padanan Pelanggan. 
-   [Segmen dikonfigurasikan](segments.md) dalam cerapan khalayak.
-   Profil pelanggan yang disatukan dalam segmen yang dieksport mengandungi medan dengan alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Anda boleh mengeksport hingga 500K profil bagi setiap eksport ke Microsoft Advertising.
- Mengeksport ke Microsoft Advertising dihadkan kepada segmen.
- Mengeksport hingga 500K profil ke Microsoft Advertising boleh mengambil masa hingga 10 minit untuk diselesaikan. 


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

1. Di bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan anda yang disatukan dengan alamat e-mel pelanggan. Ia diperlukan untuk mengeksport segmen ke Microsoft Advertising.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk memindahkan data ke Microsoft Advertising, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan Microsoft Advertising memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menghentikan penggunaan kefungsian ini.