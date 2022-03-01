---
title: Eksport data Customer Insights ke AdRoll
description: Ketahui cara mengkonfigurasikan sambungan ke AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697085"
---
# <a name="connector-for-adroll-preview"></a>Penyambung untuk AdRoll (pratonton)

Eksport segmen profil pelanggan yang disatukan ke AdRoll dan gunakan segmen tersebut untuk pengiklanan. 

## <a name="prerequisites"></a>Prasyarat

-   Anda mempunyai [Akaun AdRoll](https://www.adroll.com/) dan kelayakan pentadbir yang berkaitan.
-   Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="connect-to-adroll"></a>Sambung kepada AdRoll

1. Pergi ke **Pentadbir** > **Destinasi Eksport**.

1. Di bawah **AdRoll**, pilih **Sediakan**.

1. Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Anak tetingkap konfigurasi untuk sambungan AdRoll.":::

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** untuk memulakan sambungan ke AdRoll.

1. Pilih **Sahkan dengan AdRoll** dan berikan kelayakan pentadbir anda untuk AdRoll. 

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Masukkan **ID Pengiklan AdRoll** anda [AdRoll yang Boleh Diiklankan](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Pilih **Seterusnya** untuk konfigurasi eksport.

## <a name="configure-the-connector"></a>Konfigurasi penyambung

1. Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan. Ia diperlukan untuk mengeksport segmen ke AdRoll.

1. Pilih segmen yang ingin anda eksport. Pilih segmen dengan sekurang-kurangnya 100 ahli. Anda tidak boleh mengeksport segmen yang lebih kecil. Selain itu, saiz maksimum segmen untuk mengeksport ialah 250,000 ahli bagi setiap eksport. 

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).

## <a name="known-limitations"></a>Had diketahui

- Anda boleh mengeksport hingga 250,000 profil bagi setiap eksport ke AdRoll.
- Anda tidak boleh mengeksport segmen yang kurang daripada 100 profil ke AdRoll. 
- Mengeksport ke AdRoll adalah terhad kepada segmen.
- Mengeksport hingga 250,000 profil ke AdRoll mungkin mengambil masa hingga 10 minit untuk selesai. 
- Bilangan profil yang boleh anda eksport ke AdRoll bergantung dan terhad pada kontrak anda dengan AdRoll.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke AdRoll, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif yang berpotensi seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa AdRoll memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.
