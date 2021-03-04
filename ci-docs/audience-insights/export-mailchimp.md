---
title: Eksport data Customer Insights ke Mailchimp
description: Ketahui cara mengkonfigurasi sambungan ke Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267184"
---
# <a name="connector-for-mailchimp-preview"></a>Penyambung untuk Mailchimp (pratonton)

Segmen eksport profil pelanggan disatukan ke Mailchimp untuk mencipta surat berita dan kempen e-mel.

## <a name="prerequisites"></a>Prasyarat

-   Anda mempunyai [Akaun Mailchimp](https://mailchimp.com/) dan kelayakan pentadbir yang berkaitan.
-   Terdapat khalayak sedia ada dalam Mailchimp dan ID yang berkaitan. Untuk maklumat lanjut, lihat [Khalayak Mailchimp](https://mailchimp.com/help/create-audience/).
-   Anda telah [mengkonfigurasi segmen](segments.md)
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="connect-to-mailchimp"></a>Sambung kepada Mailchimp

1. Pergi ke **Pentadbir** > **Destinasi Eksport**.

1. Di bawah **Mailchimp**, pilih **Sediakan**.

1. Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Masukkan **[ID khalayak Mailchimp](https://mailchimp.com/help/find-audience-id/)** anda dan pilih **Sambung** untuk memulakan sambungan ke Mailchimp.

1. Pilih **Sahkan dengan Mailchimp** dan berikan kelayakan Mailchimp anda.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Eksport tangkap skrin untuk sambungan Customer Insights":::

1. Pilih **Seterusnya** untuk konfigurasi eksport.

## <a name="configure-the-connector"></a>Konfigurasi penyambung

1. Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan. 

1. Secara alternatif, anda boleh mengeksport **Nama pertama** dan **Nama akhir** sebagai medan tambahan untuk mencipta lebih banyak e-mel peribadi. Pilih **Tambah atribut** untuk memetakan medan ini.

1. Pilih segmen yang ingin anda eksport. Anda boleh mengeksport hingga 1 juta jumlah profil pelanggan ke Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Pilih medan dan segmen untuk eksport ke Mailchimp":::

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab). Dalam Mailchimp, anda kini boleh mencari segmen anda di bawah [Khalayak Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Had diketahui

- Hingga 1 juta profil bagi setiap eksport ke Mailchimp.
- Mengeksport ke Mailchimp adalah terhad kepada segmen.
- Mengeksport segmen dengan 1 juta jumlah profil boleh mengambil masa hingga tiga jam kerana had pada bahagian pembekal. 
- Bilangan profil yang boleh anda eksport ke Mailchimp bergantung dan terhad pada kontrak anda dengan Mailchimp.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Mailchimp, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Mailchimp memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]