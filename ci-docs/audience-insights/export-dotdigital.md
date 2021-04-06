---
title: Eksport data Customer Insights ke DotDigital
description: Ketahui cara mengkonfigurasi sambungan ke DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598028"
---
# <a name="connector-for-dotdigital-preview"></a>Penyambung untuk DotDigital (pratonton)

Eksport segmen profil pelanggan disatukan ke buku alamat DotDigital dan gunakannya untuk kempen, pemasaran e-mel dan untuk membina segmen pelanggan dengan DotDigital. 

## <a name="prerequisites"></a>Prasyarat

-   Anda mempunyai [Akaun DotDigital](https://dotdigital.com/) dan kelayakan pentadbir yang berkaitan.
-   Terdapat buku alamat sedia ada dalam DotDigital dan ID yang berkaitan. ID boleh ditemui dalam URL apabila anda memilih dan membuka buku alamat. Untuk maklumat lanjut, lihat [Buku alamat DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="connect-to-dotdigital"></a>Sambung ke DotDigital

1. Pergi ke **Pentadbir** > **Destinasi Eksport**.

1. Di bawah **DotDigital**, pilih **Sediakan**.

1. Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Anak tetingkap konfigurasi untuk eksport DotDigital.":::

1. Masukkan **Nama pengguna dan kata laluan DotDigital** anda.

1. Masukkan **[ID buku alamat DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** anda.

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** untuk memulakan sambungan ke DotDigital.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Seterusnya** untuk konfigurasi eksport.

## <a name="configure-the-connector"></a>Konfigurasi penyambung

1. Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan. Ulangi langkah yang sama untuk medan pilihan lain seperti **Nama pertama**, **Nama akhir**, **Nama penuh**, **Jantina** dan **Poskod**.

1. Pilih segmen yang ingin anda eksport. Anda boleh mengeksport hingga 1 juta profil pelanggan dalam jumlah keseluruhan DotDigital.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab). Dalam DotDigital, anda kini boleh mencari segmen anda dalam [Buku alamat DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Had diketahui

- Hingga 1 juta profil bagi setiap eksport ke DotDigital.
- Mengeksport ke DotDigital adalah terhad kepada segmen.
- Mengeksport segmen dengan jumlah 1 juta profil boleh mengambil masa hingga 3 jam kerana had pada bahagian pembekal. 
- Bilangan profil yang boleh anda eksport ke DotDigital bergantung dan terhad pada kontrak anda dengan DotDigital.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke DotDigital, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa DotDigital memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]