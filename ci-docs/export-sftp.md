---
title: Eksport data ke hos SFTP (pratonton) (mengandungi video)
description: Ketahui cara mengkonfigurasi sambungan dan mengeksport ke lokasi SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207240"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Eksport data ke hos SFTP (pratonton)

Gunakan data pelanggan anda dalam aplikasi pihak ketiga dengan mengeksportnya ke lokasi Protokol Pemindahan Fail Selamat (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Prasyarat

- Ketersediaan hos SFTP dan kelayakan yang sepadan.

## <a name="known-limitations"></a>Had diketahui

- Destinasi SFTP di belakang tembok api pada masa ini tidak disokong.
- Masa jalanan eksport bergantung pada prestasi sistem anda. Kami mengesyorkan dua CPU teras dan 1 Gb memori sebagai konfigurasi minimum pelayan anda.
- Sehingga 100 juta profil pelanggan, yang boleh mengambil masa 90 minit apabila menggunakan konfigurasi minimum yang disyorkan dua teras CPU dan memori 1 Gb.
- Jika anda menggunakan kekunci SSH untuk pengesahan, pastikan anda [mencipta kunci](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) peribadi anda sebagai PEM atau SSH.COM format. Jika anda menggunakan Putty, tukar kunci peribadi anda dengan mengeksport adalah sebagai SSH Terbuka. Format kunci peribadi berikut disokong:
  - RSA dalam format OpenSSL PEM dan ssh.com
  - DSA dalam format OpenSSL PEM dan ssh.com
  - ECDSA 256/384/521 dalam format OpenSSL PEM
  - ED25519 dan RSA dalam format kekunci OpenSSH

## <a name="set-up-connection-to-sftp"></a>Sediakan sambungan ke SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **SFTP**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih sama ada anda mahu mengesahkan melalui SSH atau nama pengguna/kata laluan untuk sambungan anda dan berikan butiran yang diperlukan. Jika anda menggunakan kekunci SSH untuk pengesahan, pastikan anda [mencipta kunci](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) peribadi anda sebagai PEM atau SSH.COM format. Jika anda menggunakan Putty, tukar kunci peribadi anda dengan mengeksport adalah sebagai SSH Terbuka. Format kunci peribadi berikut disokong:
   - RSA dalam format OpenSSL PEM dan ssh.com
   - DSA dalam format OpenSSL PEM dan ssh.com
   - ECDSA 256/384/521 dalam format OpenSSL PEM
   - ED25519 dan RSA dalam format kekunci OpenSSH

1. Pilih **Sahkan** untuk menguji sambungan.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian SFTP. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Pilih sama ada anda mahu mengeksport data **Gzipped** atau **Unzipped** dan **penyahhad medan** untuk fail yang dieksport.

1. Pilih entiti, contohnya segmen, yang anda ingin eksport.

   > [!NOTE]
   > Setiap entiti yang dipilih akan dibahagikan kepada maksimum lima fail output apabila dieksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Eksport entiti yang mengandungi sejumlah besar data boleh membawa kepada berbilang fail CSV dalam folder yang sama untuk setiap eksport. Memisahkan eksport berlaku atas sebab prestasi untuk meminimumkan masa yang diperlukan untuk eksport selesai.

[!INCLUDE [footer-include](includes/footer-banner.md)]
