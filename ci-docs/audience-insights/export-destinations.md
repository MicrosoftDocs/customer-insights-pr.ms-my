---
title: Eksport data daripada Customer Insights
description: Urus eksport untuk berkongsi data.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016625"
---
# <a name="exports-preview-overview"></a>Eksport gambaran keseluruhan (pratonton)

Halaman **Eksport** menunjukkan semua eksport yang dikonfigurasikan. Eksport berkongsi data tertentu dengan pelbagai aplikasi. Ia termasuk profil pelanggan atau entiti, skema, dan butiran pemetaan. Setiap eksport memerlukan [sambungan, yang disediakan oleh pentadbir, untuk menguruskan pengesahan dan akses](connections.md).

Pergi ke **Data** > **Eksport** untuk melihat halaman eksport. Semua peranan pengguna mempunyai akses untuk melihat eksport yang dikonfigurasikan. Penggunaan medan carian dalam bar perintah untuk mencari eksport dengan nama, nama sambungan atau jenis sambungan mereka.

## <a name="set-up-a-new-export"></a>Sediakan eksport baharu

Untuk menyediakan atau mengedit eksport, anda perlu mempunyai sambungan yang tersedia untuk anda. Sambungan bergantung kepada [peranan pengguna](permissions.md) anda:
- Pentadbir mempunyai akses ke semua sambungan. Mereka juga boleh mencipta sambungan baharu apabila menyediakan eksport.
- Penyumbang boleh mempunyai akses ke sambungan tertentu. Mereka bergantung kepada pentadbir untuk mengkonfigurasi dan berkongsi sambungan. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Penonton hanya boleh melihat eksport sedia ada tetapi tidak menciptanya.

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport** untuk mencipta destinasi eksport baharu.

1. Dalam anak tetingkap **Sediakan eksport**, pilih sambungan yang hendak digunakan. [Sambungan](connections.md) diurus oleh pentadbir. 

1. Berikan butiran yang diperlukan dan pilih **Simpan** untuk mencipta eksport.

### <a name="edit-an-export"></a>Edit eksport

1. Pilih elipsis menegak untuk destinasi eksport yang anda mahu edit.

1. Pilih **Edit** dari menu juntai bawah.

1. Ubah nilai yang anda mahu kemas kini dan pilih **Simpan**.

## <a name="view-exports-and-export-details"></a>Lihat Eksport dan butiran eksport

Selepas membuat destinasi eksport, ia disenaraikan dalam **Data** > **Eksport**. Semua pengguna boleh melihat data mana yang dikongsi dan status terkininya.

1. Pergi ke **Data** > **Eksport**.

1. Pengguna tanpa keizinan edit, pilih **Lihat** dan bukannya **Edit**. Lihat butiran eksport.

1. Anak tetingkap sisi ini menunjukkan persediaan eksport ini. Tanpa keizinan edit, anda tidak boleh mengubah nilai. Pilih **Tutup** untuk kembali ke halaman eksport.

## <a name="run-exports-on-demand"></a>Jalankan eksport atas permintaan

Selepas mengkonfigurasikan eksport, ia akan berjalan dengan setiap [segar semula berjadual](system.md#schedule-tab) selagi ia mempunyai sambungan kerja.

Untuk mengeksport data tanpa menunggu segar semula berjadual, pergi ke **Data** > **Eksport**. Anda mempunyai dua pilihan:

- Untuk menjalankan semua eksport, pilih **Jalankan semua** dalam bar perintah. 
- Untuk menjalankan eksport tunggal, pilih elipsis (...) pada item senarai dan kemudian pilih **Jalankan**.

## <a name="remove-an-export"></a>Alih keluar Eksport

1. Pergi ke **Data** > **Eksport**.

1. Pilih elipsis menegak untuk Eksport yang anda mahu alih keluar.

1. Pilih **Alih keluar** daripada menu juntai bawah.

1. Sahkan pengalihan keluar dengan memilih **Alih keluar** pada skrin pengesahan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
