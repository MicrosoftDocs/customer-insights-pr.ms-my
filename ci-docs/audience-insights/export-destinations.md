---
title: Destinasi eksport
description: Eksport data dan urus destinasi eksport.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596096"
---
# <a name="export-destinations-preview-overview"></a>Gamabaran keseluruhan destinasi eksport (pratonton)

Halaman **Destinasi eksport** menunjukkan anda semua lokasi yang telah anda sediakan untuk mengeksport data. Anda juga boleh menambah destinasi baharu untuk eksport. Selain itu, ia menunjukkan eksport adalah pilihan yang tersedia. Dapatkan gambaran pantas, keterangan dan ketahui perkara yang boleh anda lakukan dengan setiap pilihan kebolehpanjangan. Eksport profil, langkah dan segmen disatukan kepada aplikasi yang disokong untuk perniagaan anda.

Pergi ke **Pentadbir** > **Destinasi eksport** untuk mencari pilihan kebolehpanjangan berikut:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Platform Pengalaman Adobe](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Storan Blob Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Bot untuk Microsoft Teams](export-teams-bot.md)
- [API Customer Insights](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (Tambahan Kad Pelanggan)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Hab Jualan Dynamics 365 (Tambahan Kad Pelanggan)](customer-card-add-in.md)
- [Pengurus Iklan Facebook](export-facebook.md)
- [Google Ads](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

## <a name="add-a-new-export-destination"></a>Tambah destinasi eksport baharu

Untuk menambah destinasi eksport, anda mempunyai [keizinan pentadbir](permissions.md). Jika anda mengeksport perkhidmatan Microsoft, kami mengandaikan kedua-dua perkhidmatan adalah dalam organisasi yang sama.

1. Pergi ke **Pentadbir** > **Destinasi Eksport**.

1. Tukar kepada tab **Destinasi eksport saya**.

1. Pilih **Tambah destinasi** untuk mencipta destinasi eksport baharu.

1. Pada anak tetingkap **Tambah destinasi**, pilih **Jenis** destinasi eksport dalam juntai bawah.

1. Sediakan butiran yang diperlukan dan pilih **Seterusnya** untuk mencipta destinasi eksport.

Anda juga boleh memilih **Sediakan** pada jubin pada tab **Temui**.

## <a name="view-export-destinations"></a>Lihat Eksport destinasi

Selepas mencipta destinasi eksport, anda boleh mencarinya dalam jadual pada tab **Destinasi eksport saya**. Jadual ini mempunyai tiga lajur:

- **Nama paparan**: Nama yang anda masukkan semasa mencipta destinasi.
- **Jenis**: Jenis destinasi eksport yang anda tetapkan semasa mencipta destinasi.
- **Dicipta**: Tarikh anda mencipta destinasi.

## <a name="edit-an-export-destination"></a>Edit destinasi eksport

1. Pilih elipsis menegak untuk destinasi Eksport yang anda mahu edit.

   > [!div class="mx-imgBorder"]
   > ![Elipsis menegak](media/export-destinations-page-ellipsis.png "Elipsis menegak")

1. Pilih **Edit** daripada menu juntai bawah.

1. Tukar nilai yang memerlukan kemas kini dan pilih **Simpan**.

## <a name="export-data-on-demand"></a>Eksport data atas permintaan

Selepas mengkonfigur penyambung untuk destinasi eksport, eksport akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).

Untuk mengeksport data tanpa menunggu segar semula dijadualkan, pergi ke tab **Destinasi eksport saya** pada **Pentadbir** > **Destinasi eksport**.

> [!div class="mx-imgBorder"]
> ![Elipsis menegak](media/export-destinations-page-ellipsis.png "Elipsis menegak")

- Pilih **Eksport** di atas senarai untuk menjalankan eksport ke semua destinasi eksport secara serentak.
- Pilih elipsis (...) selepas item senarai dan kemudian pilih pilihan **Eksport** untuk menjalankan eksport untuk destinasi eksport tunggal.

## <a name="remove-an-export-destination"></a>Alih keluar Eksport destinasi

Untuk mengalih keluar Eksport destinasi, mulakan dari halaman **Eksport destinasi** utama.

1. Pilih elipsis menegak untuk Eksport destinasi yang anda mahu alih keluar.

   > [!div class="mx-imgBorder"]
   > ![Elipsis menegak](media/export-destinations-page-ellipsis.png "Elipsis menegak")

2. Pilih **Alih keluar** daripada menu juntai bawah.

3. Sahkan pengalihan keluar dengan memilih **Alih keluar** pada skrin pengesahan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]