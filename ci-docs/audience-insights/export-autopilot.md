---
title: Eksport data Customer Insights ke Autopilot
description: Ketahui cara mengkonfigurasi sambungan ke Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269249"
---
# <a name="connector-for-autopilot-preview"></a>Penyambung untuk Autopilot (pratonton)

Eksport segmen bagi profil pelanggan disatukan untuk Autopilot dan gunakannya untuk pemasaran e-mel dalam Autopilot. 

## <a name="prerequisites"></a>Prasyarat

-   Anda mempunyai sebuah [Akaun Autopilot](https://www.autopilothq.com/) dan kelayakan pentadbir yang berkaitan.
-   Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="connect-to-autopilot"></a>Sambung kepada AutoPilot

1. Pergi ke **Pentadbir** > **Destinasi Eksport**.

1. Di bawah **Autopilot**, pilih **Sediakan**.

1. Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Anak tetingkap konfigurasi untuk sambungan Autopilot.":::

1. Masukkan **Kekunci API Autopilot** [Kekunci API Autopilot](https://autopilot.docs.apiary.io/#).

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** untuk memulakan sambungan ke Autopilot.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Seterusnya** untuk konfigurasi eksport.

## <a name="configure-the-connector"></a>Konfigurasi penyambung

1. Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan. Ulangi langkah yang sama untuk medan pilihan lain seperti **Nama pertama**, **Nama keluarga**.

1. Pilih segmen yang ingin anda eksport. Kami amat **mengesyorkan untuk tidak mengeksport lebih daripada 100'000 profil pelanggan dalam jumlah** untuk Autopilot. 

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).

## <a name="known-limitations"></a>Had diketahui

- Anda boleh mengeksport hingga 100'000 juta jumlah profil pelanggan ke Autopilot.
- Mengeksport ke Autopilot adalah terhad kepada segmen.
- Mengeksport sehingga 100'000 profil ke Autopilot boleh mengambil masa hingga beberapa jam untuk diselesaikan. 
- Bilangan profil yang boleh anda eksport ke Autopilot bergantung dan terhad pada kontrak anda dengan Autopilot.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Autopilot, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Autopilot memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]