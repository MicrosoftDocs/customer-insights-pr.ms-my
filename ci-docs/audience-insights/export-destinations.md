---
title: Destinasi eksport
description: Eksport data dan urus destinasi eksport.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477144"
---
# <a name="export-destinations-preview-overview"></a>Gamabaran keseluruhan destinasi eksport (pratonton)

Halaman **Destinasi eksport** menunjukkan anda semua lokasi yang telah anda sediakan untuk mengeksport data. Anda juga boleh menambah destinasi baharu untuk eksport. Selain itu, ia menunjukkan eksport adalah pilihan yang tersedia. Dapatkan gambaran pantas, keterangan dan ketahui perkara yang boleh anda lakukan dengan setiap pilihan kebolehpanjangan. Eksport profil, langkah dan segmen disatukan kepada aplikasi yang disokong untuk perniagaan anda.

Pergi ke **Pentadbir** > **Destinasi eksport** untuk mencari pilihan kebolehpanjangan berikut:

- [Tambahan Kad Pelanggan Dynamics 365](customer-card-add-in.md)
- [Penyambung Pengurus Iklan Facebook](export-facebook.md)
- [Penyambung Power Automate](export-power-automate.md)
- [Penyambung Power Apps](export-power-apps.md)
- [Penyambung Power BI](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Storan Blob Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [LiveRamp&reg; penyambung](export-liveramp.md)
- [Bot untuk Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [API Customer Insights](apis.md)

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