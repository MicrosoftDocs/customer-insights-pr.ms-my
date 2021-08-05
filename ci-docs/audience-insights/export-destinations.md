---
title: Eksport data daripada Customer Insights
description: Urus eksport untuk berkongsi data.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 47bdcc5bb38587063e4414377568943f868107a3
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539354"
---
# <a name="exports-preview-overview"></a>Eksport gambaran keseluruhan (pratonton)

Halaman **Eksport** menunjukkan semua eksport yang dikonfigurasikan. Eksport berkongsi data tertentu dengan pelbagai aplikasi. Ia termasuk profil pelanggan atau entiti, skema, dan butiran pemetaan. Setiap eksport memerlukan [sambungan, yang disediakan oleh pentadbir, untuk menguruskan pengesahan dan akses](connections.md).

Pergi ke **Data** > **Eksport** untuk melihat halaman eksport. Semua peranan pengguna boleh melihat eksport yang dikonfigurasikan. Gunakan medan carian dalam bar perintah untuk mencari eksport mengikut nama, nama sambungan atau jenis sambungan.

## <a name="set-up-a-new-export"></a>Sediakan eksport baharu

Untuk menyediakan atau mengedit eksport, anda perlu mempunyai sambungan yang tersedia untuk anda. Sambungan bergantung kepada [peranan pengguna](permissions.md) anda:
- Pentadbir mempunyai akses ke semua sambungan. Mereka juga boleh mencipta sambungan baharu apabila menyediakan eksport.
- Penyumbang boleh mempunyai akses ke sambungan tertentu. Mereka bergantung kepada pentadbir untuk mengkonfigurasi dan berkongsi sambungan. Senarai eksport menunjukkan penyumbang sama ada mereka boleh mengedit atau hanya melihat eksport dalam lajur **Keizinan anda**. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Penonton hanya boleh melihat eksport sedia ada tetapi tidak menciptanya.

### <a name="define-a-new-export"></a>Tentukan eksport baharu

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport** untuk mencipta eksport baharu.

1. Dalam anak tetingkap **Sediakan eksport**, pilih sambungan yang hendak digunakan. [Sambungan](connections.md) diurus oleh pentadbir. 

1. Berikan butiran yang diperlukan dan pilih **Simpan** untuk mencipta eksport.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Tentukan eksport baharu berdasarkan eksport yang sedia ada

1. Pergi ke **Data** > **Eksport**.

1. Dalam senarai eksport, pilih eksport yang ingin anda duplikasi.

1. Pilih **Cipta duplikasi** dalam bar perintah untuk membuka anak tetingkap **Sediakan eksport** dengan butiran eksport yang dipilih.

1. Semak dan sesuaikan eksport dan pilih **Simpan** untuk mencipta eksport baharu.

### <a name="edit-an-export"></a>Edit eksport

1. Pergi ke **Data** > **Eksport**.

1. Dalam senarai eksport, pilih eksport yang ingin anda edit.

1. Pilih **Edit** dalam bar perintah.

1. Ubah nilai yang anda mahu kemas kini dan pilih **Simpan**.

## <a name="view-exports-and-export-details"></a>Lihat eksport dan butiran eksport

Selepas mencipta destinasi eksport, ia disenaraikan dalam **Data** > **Eksport**. Semua pengguna boleh melihat data mana yang dikongsi dan status terkininya.

1. Pergi ke **Data** > **Eksport**.

1. Pengguna tanpa keizinan mengedit, pilih **Lihat** dan bukannya **Edit** untuk melihat butiran eksport.

1. Anak tetingkap sisi menunjukkan konfigurasi eksport. Tanpa keizinan edit, anda tidak boleh mengubah nilai. Pilih **Tutup** untuk kembali ke halaman eksport.

## <a name="schedule-and-run-exports"></a>Jadualkan dan jalankan eksport

Setiap eksport yang dikonfigurasikan mempunyai jadual segar semula. Semasa segar semula, sistem mencari data baharu atau yang dikemas kini untuk disertakan dalam eksport. Secara lalai, eksport dijalankan sebagai sebahagian daripada setiap [segar semula sistem yang dijadualkan](system.md#schedule-tab). Anda boleh menyesuaikan jadual segar semula atau mematikan proses itu untuk menjalankan eksport secara manual.

Jadual eksport bergantung pada keadaan persekitaran anda. Jika terdapat kemas kini yang sedang berjalan pada [kebergantungan](system.md#refresh-policies) apabila eksport yang dijadualkan harus bermula, sistem akan melengkapkan kemas kini terlebih dahulu dan kemudian menjalankan eksport. Anda boleh melihat masa eksport disegarkan semula buat kali terakhir dalam lajur **Disegar semula**.

### <a name="schedule-exports"></a>Jadualkan eksport

Anda boleh menentukan jadual segar semula tersuai untuk eksport individu atau beberapa eksport secara serentak. Jadual yang ditentukan pada masa ini disenaraikan dalam lajur **Jadual** senarai eksport. Keizinan untuk menukar jadual adalah sama seperti untuk [mengedit dan menentukan eksport](export-destinations.md#set-up-a-new-export). 

1. Pergi ke **Data** > **Eksport**.

1. Pilih eksport yang ingin anda jadualkan.

1. Pilih **Jadual** dalam bar perintah.

1. Dalam anak tetingkap **Eksport jadual**, tetapkan **Jalankan jadual** ke **Hidup** untuk menjalankan eksport secara automatik. Tetapkan ke **Mati** untuk menyegarkan semula jadual secara manual.

1. Untuk eksport yang disegarkan semula secara automatik, pilih nilai **Ulangan** dan tentukan butiran untuk eksport tersebut. Masa yang ditentukan terpakai kepada semua tika ulangan. Sudah tiba masanya eksport harus mula menyegarkan semula.

1. Gunakan dan aktifkan perubahan anda dengan memilih **Simpan**.

Apabila mengedit jadual untuk beberapa eksport, anda perlu membuat pilihan di bawah **Simpan atau ganti jadual**:
- **Simpan jadual individu**: Teruskan dengan jadual yang ditentukan sebelumnya untuk eksport yang dipilih dan hanya nyahdayakan atau dayakan jadual tersebut.
- **Tentukan jadual baharu untuk semua eksport yang dipilih**: Gantikan jadual sedia ada bagi eksport yang dipilih.

### <a name="run-exports-on-demand"></a>Jalankan eksport atas permintaan

Untuk mengeksport data tanpa menunggu segar semula berjadual, pergi ke **Data** > **Eksport**.

- Untuk menjalankan semua eksport, pilih **Jalankan semua** dalam bar perintah. Tindakan ini hanya akan menjalankan eksport yang mempunyai jadual aktif.
- Untuk menjalankan eksport tunggal, pilih dalam senarai dan pilih **Jalankan** dalam bar perintah. Itulah cara anda menjalankan eksport tanpa jadual aktif. 

## <a name="remove-an-export"></a>Alih keluar Eksport

1. Pergi ke **Data** > **Eksport**.

1. Pilih eksport yang ingin anda alih keluar.

1. Pilih **Alih Keluar** dalam bar perintah.

1. Sahkan pengalihan keluar dengan memilih **Alih keluar** pada skrin pengesahan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
