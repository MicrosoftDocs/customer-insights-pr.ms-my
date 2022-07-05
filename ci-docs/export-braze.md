---
title: Eksport segmen ke Braze (pratonton)
description: Ketahui cara mengkonfigurasi sambungan dan eksport ke Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082685"
---
# <a name="export-segments-to-braze-preview"></a>Eksport segmen ke Braze (pratonton)

Eksport segmen profil pelanggan bersatu ke Braze dan gunakannya untuk aktiviti pemasaran.

## <a name="prerequisites"></a>Prasyarat

- Akaun [Braze](https://www.braze.com/) dan kelayakan pentadbir yang sepadan.
- Segmen sedia ada [dalam Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Segmen yang](segments.md) dikonfigurasikan dalam Wawasan Pelanggan.
- Profil pelanggan bersatu dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel dan ID pelanggan Braze.

## <a name="known-limitations"></a>Had diketahui

- Mengeksport ke Braze adalah terhad kepada segmen.
- Mengeksport sehingga 1 juta profil pelanggan ke Braze boleh mengambil masa sehingga 40 minit untuk diselesaikan.
- Bilangan profil pelanggan yang boleh anda eksport ke Braze bergantung dan terhad pada kontrak anda dengan Braze.

## <a name="set-up-connection-to-braze"></a>Sediakan sambungan ke Braze

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Braze** untuk mengkonfigurasi sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan kekunci [API Braze anda](https://www.braze.com/docs/api/basics/) untuk terus log masuk.

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** untuk memulakan sambungan ke Braze.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada bahagian Braze. Jika anda tidak melihat seksyen ini, tiada sambungan jenis ini tersedia untuk anda.  

1. **Tambah nama** Paparan untuk eksport anda.

1. Tambah pengecam API segmen Braze yang anda ingin eksport dalam **medan Pengenalpasti** API Segmen Braze. Anda boleh mencari pengecam dalam butiran segmen pada platform Braze.

1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. **Dalam medan ID** Pelanggan, pilih medan yang mewakili ID Braze pelanggan. Ia diperlukan untuk mengeksport segmen ke Braze. Anda boleh memilih lebih banyak medan secara pilihan.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Braze, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan braze memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.
