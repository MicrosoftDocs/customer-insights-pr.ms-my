---
title: Eksport data ke hos SFTP (pratonton) (mengandungi video)
description: Ketahui cara mengkonfigurasi sambungan dan mengeksport ke lokasi SFTP.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67789a87cf0ff1b0d9933f2c0adde37762c83476
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082769"
---
# <a name="export-data-to-sftp-preview"></a>Eksport data ke SFTP (pratonton)

Gunakan data pelanggan anda dalam aplikasi pihak ketiga dengan mengeksportnya ke lokasi Protokol Pemindahan Fail Selamat (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Prasyarat untuk sambungan

- Ketersediaan hos SFTP dan kelayakan yang sepadan.

## <a name="known-limitations"></a>Had diketahui

- Destinasi SFTP di belakang tembok api pada masa ini tidak disokong. 
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

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).
Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).

> [!TIP]
> Eksport entiti yang mengandungi sejumlah besar data boleh membawa kepada berbilang fail CSV dalam folder yang sama untuk setiap eksport. Memisahkan eksport berlaku atas sebab prestasi untuk meminimumkan masa yang diperlukan untuk eksport selesai.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data melalui SFTP, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa destinasi eksport memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.

[!INCLUDE [footer-include](includes/footer-banner.md)]
