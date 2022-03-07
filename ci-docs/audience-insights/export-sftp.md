---
title: Eksport data Customer Insights ke hos SFTP
description: Ketahui cara mengkonfigurasi sambungan ke hos SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268009"
---
# <a name="connector-for-sftp-preview"></a>Penyambung untuk SFTP (pratonton)

Gunakan data pelanggan anda dalam aplikasi pihak ketiga dengan mengeksportnya ke hos Protokol Pemindahan Fail Selamat (SFTP).

## <a name="prerequisites"></a>Prasyarat

- Ketersediaan hos SFTP dan kelayakan yang sepadan.

## <a name="connect-to-sftp"></a>Sambung kepada SFTP

1. Pergi ke **Pentadbir** > **Destinasi Eksport**.

1. Di bawah **SFTP**, pilih **Sediakan**.

1. Berikan destinasi anda nama yang dikenali dalam medan **Nama paparan**.

1. Menyediakan **Nama pengguna**, **Kata laluan**, **Nama hos**, dan **Eksport folder** untuk akaun SFTP anda.

1. Pilih **Sahkan** untuk menguji sambungan.

1. Selepas pengesahan berjaya, pilih sama ada anda mahu mengeksport data anda **Digzip** atau **Dinyahzip** dan pilih **pemisah medan** untuk fail yang dieksport.

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Seterusnya** untuk memulakan konfigurasi eksport.

## <a name="configure-the-export"></a>Konfigurasi eksport

1. Pilih entiti, contohnya segmen, yang anda mahu mengeksport.

   > [!NOTE]
   > Setiap entiti yang dipilih akan meningkat kepada lima fail output apabila dieksport. 

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).

## <a name="known-limitations"></a>Had diketahui

- Masa jalanan eksport bergantung pada prestasi sistem anda. Kami mengesyorkan dua CPU teras dan 1 Gb memori sebagai konfigurasi minimum pelayan anda. 
- Mengeksport entiti sehingga 100 juta profil pelanggan boleh mengambil masa 90 minit apabila menggunakan konfigurasi minimum yang disyorkan iaitu dua CPU teras dan 1 Gb memori. 

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data melalui SFTP, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa destinasi eksport memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]