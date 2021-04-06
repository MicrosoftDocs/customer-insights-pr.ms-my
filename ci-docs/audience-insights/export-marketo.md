---
title: Eksport data Customer Insights ke Marketo
description: Ketahui cara mengkonfigurasi sambungan ke Marketo.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597982"
---
# <a name="connector-for-marketo-preview"></a>Penyambung untuk Marketo (pratonton)

Eksport segmen profil pelanggan disatukan untuk menjana kempen, menyediakan pemasaran e-mel dan gunakan kumpulan pelanggan tertentu dengan Marketo.

## <a name="prerequisites"></a>Prasyarat

-   Anda mempunyai [Akaun Marketo](https://login.marketo.com/) dan kelayakan pentadbir yang berkaitan.
-   Terdapat senarai sedia ada dalam Marketo dan ID yang berkaitan. Untuk maklumat lanjut, lihat [Senarai Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Anda telah [mengkonfigurasi segmen](segments.md).
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="connect-to-marketo"></a>Sambung ke Marketo

1. Pergi ke **Pentadbir** > **Destinasi Eksport**.

1. Di bawah **Marketo**, pilih **Sediakan**.

1. Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.

1. Masukkan **[ID klien Marketo, Rahsia pelanggan dan Nama hos Titik tamat REST](https://developers.marketo.com/rest-api/authentication/)** anda.

1. Masukkan **[ID senarai Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** anda 

1. Pilih **Saya setuju** untuk mengesahkan **Privasi data dan pematuhan** dan pilih **Sambung** untuk memulakan sambungan ke Marketo.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Eksport tangkap skrin untuk sambungan Marketo":::

1. Pilih **Seterusnya** untuk konfigurasi eksport.

## <a name="configure-the-connector"></a>Konfigurasi penyambung

1. Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan. 

1. Secara alternatif, anda boleh mengeksport **Nama pertama**, **Nama akhir**, **Bandar**, **Negeri**, dan **Negara/Rantau** sebagai medan tambahan untuk mencipta lebih banyak e-mel peribadi. Pilih **Tambah atribut** untuk memetakan medan ini.

1. Pilih segmen yang ingin anda eksport. Anda boleh mengeksport hingga 1 juta jumlah profil pelanggan ke Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Pilih medan dan segmen untuk eksport ke Marketo":::

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab). Dalam Marketo, anda kini boleh mencari segmen anda di bawah [Senarai Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Had diketahui

- Hingga 1 juta profil bagi setiap eksport ke Marketo.
- Mengeksport ke Marketo adalah terhad kepada segmen.
- Mengeksport segmen dengan sejumlah 1 juta profil boleh mengambil masa sehingga 3 jam. 
- Bilangan profil yang boleh anda eksport ke Marketo bergantung dan terhad pada kontrak anda dengan Marketo.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Marketo, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Marketo memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]