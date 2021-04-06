---
title: Eksport data Customer Insights ke SendGrid
description: Ketahui cara mengkonfigurasi sambungan ke SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597292"
---
# <a name="connector-for-sendgrid-preview"></a>Penyambung untuk SendGrid (pratonton)

Eksport segmen bagi profil pelanggan disatukan untuk senarai kenalan SendGrid dan gunakannya untuk kempen dan pemasaran e-mel dalam SendGrid. 

## <a name="prerequisites"></a>Prasyarat

-   Anda mempunyai [Akaun SendGrid](https://sendgrid.com/) dan kelayakan pentadbir yang berkaitan.
-   Terdapat senarai kenalan sedia ada dalam SendGrid dan ID yang berkaitan. Untuk mendapatkan maklumat lanjut, lihat [SendGrid - Urus kenalan](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="connect-to-sendgrid"></a>Sambung kepada SendGrid

1. Pergi ke **Pentadbir** > **Destinasi Eksport**.

1. Di bawah **SendGrid**, pilih **Sediakan**.

1. Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Anak tetingkap konfigurasi eksport SendGrid.":::

1. Masukkan **Kekunci API SendGrid** [Kekunci API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Masukkan **[ID senarai SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** anda.

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** untuk memulakan sambungan ke SendGrid.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Seterusnya** untuk konfigurasi eksport.

## <a name="configure-the-connector"></a>Konfigurasi penyambung

1. Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan. Ulangi langkah yang sama untuk medan pilihan lain seperti **Nama pertama**, **Nama akhir**, **Negara/Rantau**, **Negeri**. **Bandar** dan **Poskod**.

1. Pilih segmen yang ingin anda eksport. Kami amat **mengesyorkan untuk tidak mengeksport lebih daripada 100'000 profil pelanggan dalam jumlah** ke SendGrid. 

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).

## <a name="known-limitations"></a>Had diketahui

- Sehingga 100'000 profil dalam jumlah keseluruhan ke SendGrid.
- Mengeksport ke SendGrid adalah terhad kepada segmen.
- Mengeksport sehingga 100'000 profil ke SendGrid boleh mengambil masa hingga beberapa jam untuk diselesaikan. 
- Bilangan profil yang boleh anda eksport ke SendGrid bergantung dan terhad pada kontrak anda dengan SendGrid.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke SendGrid, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa SendGrid memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]