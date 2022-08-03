---
title: Eksport segmen ke LiveRamp (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196727"
---
# <a name="export-segments-to-liverampreg-preview"></a>Eksport segmen ke LiveRamp&reg; (pratonton)

Aktifkan data anda dalam LiveRamp untuk berhubung dengan lebih daripada 500 platform merentasi digital, sosial, dan TV. Bekerja dengan data anda dalam LiveRamp untuk mensasar, menahan, dan memperibadikan kempen iklan.

## <a name="prerequisites"></a>Prasyarat

- Langganan LiveRamp untuk menggunakan penyambung ini. Untuk mendapatkan langganan, [hubungi LiveRamp](https://liveramp.com/contact/) secara terus. [Ketahui lanjut tentang Penyertaan LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Had diketahui

- Eksport LiveRamp menggunakan eksport SFTP. Destinasi SFTP di belakang tembok api pada masa ini tidak disokong.
- Jika anda menggunakan kekunci SSH untuk pengesahan, pastikan anda [mencipta kunci](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) peribadi anda sebagai PEM atau SSH.COM format. Jika anda menggunakan Putty, tukar kunci peribadi anda dengan mengeksport adalah sebagai SSH Terbuka. Format kunci peribadi berikut disokong:
  - RSA dalam format OpenSSL PEM dan ssh.com
  - DSA dalam format OpenSSL PEM dan ssh.com
  - ECDSA 256/384/521 dalam format OpenSSL PEM
  - ED25519 dan RSA dalam format kekunci OpenSSH
- Masa jalanan eksport bergantung pada prestasi sistem anda. Kami mengesyorkan dua CPU teras dan 1 Gb memori sebagai konfigurasi minimum pelayan anda.
- Mengeksport entiti sehingga 100 juta profil pelanggan boleh mengambil masa 90 minit apabila menggunakan konfigurasi minimum yang disyorkan iaitu dua CPU teras dan 1 Gb memori.
- Bilangan sebenar profil (atau data) yang boleh anda eksport ke LiveRamp bergantung pada langganan anda dengan LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Sediakan sambungan ke LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **LiveRamp**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih sama ada anda mahu mengesahkan melalui SSH atau nama pengguna/kata laluan untuk sambungan anda dan berikan butiran yang diperlukan.

1. Pilih **Sahkan** untuk menguji sambungan ke LiveRamp.

1. Selepas pengesahan yang berjaya, semak [privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian LiveRamp. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. **Dalam medan Sambung data**, pilih **E-mel**, **Nama dan alamat**, atau **Telefon** untuk dihantar ke LiveRamp untuk penyelesaian identiti.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Penyambung LiveRamp dengan atribut pemetaan.":::

1. Peta atribut yang sepadan daripada entiti *Pelanggan* anda untuk pengecam kunci yang dipilih.

1. Pilih **Tambah atribut** untuk memetakan lebih banyak atribut untuk dihantar ke LiveRamp.

   > [!TIP]
   > Menghantar lebih banyak atribut pengecam kunci ke LiveRamp mempunyai kemungkinan besar untuk anda mendapatkan kadar pemadanan yang tinggi.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
