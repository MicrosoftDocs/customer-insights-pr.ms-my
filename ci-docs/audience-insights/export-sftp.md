---
title: Eksport data Customer Insights ke hos SFTP
description: Ketahui cara mengkonfigurasi sambungan dan mengeksport ke lokasi SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976950"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a>Eksport senarai segmen dan data lain ke SFTP (pratonton)

Gunakan data pelanggan anda dalam aplikasi pihak ketiga dengan mengeksportnya ke lokasi Protokol Pemindahan Fail Selamat (SFTP).

## <a name="prerequisites-for-connection"></a>Prasyarat untuk sambungan

- Ketersediaan hos SFTP dan kelayakan yang sepadan.

## <a name="known-limitations"></a>Had diketahui

- Masa jalanan eksport bergantung pada prestasi sistem anda. Kami mengesyorkan dua CPU teras dan 1 Gb memori sebagai konfigurasi minimum pelayan anda. 
- Mengeksport entiti sehingga 100 juta profil pelanggan boleh mengambil masa 90 minit apabila menggunakan konfigurasi minimum yang disyorkan iaitu dua CPU teras dan 1 Gb memori. 

## <a name="set-up-connection-to-sftp"></a>Sediakan sambungan ke SFTP

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **SFTP** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Menyediakan **Nama pengguna**, **Kata laluan**, **Nama hos**, dan **Eksport folder** untuk akaun SFTP anda.

1. Pilih **Sahkan** untuk menguji sambungan.

1. Pilih sama ada anda mahu mengeksport data **Gzipped** atau **Unzipped** dan **penyahhad medan** untuk fail yang dieksport.

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian SFTP. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Pilih entiti, contohnya segmen, yang anda mahu mengeksport.

   > [!NOTE]
   > Setiap entiti yang dipilih akan dibahagikan kepada lima fail output apabila dieksport. 

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data melalui SFTP, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa destinasi eksport memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
