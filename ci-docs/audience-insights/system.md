---
title: Konfigurasi sistem dalam cerapan khalayak
description: Ketahui tentang tetapan sistem dalam keupayaan cerapan khalayak Dynamics 365 Customer Insights.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 32bb89b02947350c056c8ce8adbe37500d2099a1
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/13/2021
ms.locfileid: "6556089"
---
# <a name="system-configuration"></a>Konfigurasi sistem

Halaman **Sistem** termasuk tab berikut:
- [Status](#status-tab)
- [Jadual](#schedule-tab)
- [Penggunaan API](#api-usage-tab)
- [Perihal](#about-tab)
- [Umum](#general-tab)

> [!div class="mx-imgBorder"]
> ![Halaman sistem.](media/system-tabs.png "Halaman Sistem")

## <a name="status-tab"></a>Tab status

**Tab status** membolehkan anda menjejaki pengingesan data, eksport data dan beberapa proses produk penting lain. Semak semula maklumat pada tab ini untuk memastikan kesempurnaan proses aktif.

Tab ini termasuk jadual dengan status dan pemprosesan maklumat untuk pelbagai proses. Setiap jadual menjejaki **Nama** tugas dan entitinya yang sepadan, **Status** jalanannya paling terkini dan masa ia **Dikemas kini terakhir**.

Lihat butiran jalanan beberapa tugas terakhir dengan memilih namanya.

### <a name="status-types"></a>Jenis status

Terdapat enam jenis status untuk tugas. Jenis status yang berikut juga ditunjukkan pada halaman *Padan*, *Cantum*, *Sumber data*, *Segmen*, *Ukuran*, *Pengayaan*, *Aktiviti* dan *Ramalan*:

- **Pemprosesan:** Tugas sedang berjalan. Status boleh berubah kepada Berjaya atau Gagal.
- **Berjaya:** Tugas berjaya dilengkapkan.
- **Dilangkau:** Tugas telah dilangkau. Satu atau lebih proses hiliran yang diharapkan oleh tugas ini telah gagal atau dilangkau.
- **Kegagalan:** Pemprosesan tugas telah gagal.
- **Dibatalkan:** Pemprosesan telah dibatalkan oleh pengguna sebelum ia selesai.
- **Beratur dalam baris:** Pemprosesan sedang dibariskan dan akan bermula sebaik sahaja semua tugas huluan diselesaikan. Untuk maklumat lanjut, lihat [Segar semula dasar](#refresh-policies).

### <a name="refresh-policies"></a>Segar semula dasar

Senarai ini menunjukkan dasar segar semula untuk setiap proses utama:

- **Sumber data:** Berjalan berdasarkan [jadual yang dikonfigurasi](#schedule-tab). Tidak bergantung kepada mana-mana proses lain. Padanan bergantung pada penyelesaian yang berjaya untuk proses ini.
- **Padanan:** Berjalan berdasarkan [jadual yang dikonfigurasi](#schedule-tab). Bergantung pada pemprosesan sumber data yang digunakan dalam definisi padanan. Gabungan bergantung pada penyelesaian yang berjaya untuk proses ini.
- **Gabung**: Berjalan berdasarkan [jadual yang dikonfigurasi](#schedule-tab). Bergantung pada penyelesaian proses padanan. Segmen, langkah, pengayaan, carian, aktiviti, ramalan dan penyediaan data bergantung pada penyelesaian yang berjaya untuk proses ini.
- **Segmen**: Berjalan secara manual (segar semula sekali) dan mengikut [jadual dikonfigurasi](#schedule-tab). Bergantung pada gabungan. Wawasan bergantung pada pemprosesannya.
- **Langkah**: Berjalan secara manual (segar semula sekali) dan mengikut [jadual dikonfigurasi](#schedule-tab). Bergantung pada gabungan.
- **Aktiviti**: Berjalan secara manual (segar semula sekali) dan mengikut [jadual dikonfigurasi](#schedule-tab). Bergantung pada gabungan.
- **Pengayaan**: Berjalan secara manual (segar semula sekali) dan mengikut [jadual dikonfigurasi](#schedule-tab). Bergantung pada gabungan.
- **Carian**: Berjalan secara manual (segar semula sekali) dan mengikut [jadual dikonfigurasi](#schedule-tab). Bergantung pada gabungan.
- **Persediaan data**: Berjalan berdasarkan [jadual yang dikonfigurasi](#schedule-tab). Bergantung pada gabungan.
- **Wawasan**: Berjalan secara manual (segar semula sekali) dan mengikut [jadual dikonfigurasi](#schedule-tab). Bergantung pada Segmen.

Pilih status tugas untuk melihat butiran mengenai kemajuan keseluruhan kerja. Dasar segar semula di atas boleh membantu memahami perkara yang boleh anda lakukan untuk menangani tugas **Dilangkau** atau **Dibaris gilir**.

## <a name="schedule-tab"></a>Tab jadual

Gunakan tab **Jadual** untuk menjadualkan segar semula automatik semua [sumber data yang diinges](data-sources.md) anda. Muat semula automatik membantu memastikan bahawa kemas kini daripada sumber data anda ditunjukkan dalam profil pelanggan anda yang disatukan.

1. Dalam cerapan khalayak, pergi ke tab **Pentadbir** > **Sistem** dan pilih **Jadual**.

2. Keadaan lalai untuk segar semula dijadualkan adalah **Tutup**. Untuk mendayakan segar semula berjadual, ubah togel pada bahagian atas skrin ke **Hidup**.

3. Pilih antara segar semula **Mingguan** (lalai) dan **Harian**. Jika anda berhasrat untuk menjadualkan segar semula secara mingguan, pilih satu atau lebih hari untuk menjalankan segar semula.

4. Tetapkan **Zon waktu** anda, kemudian gunakan juntai bawah **Masa** untuk menetapkan masa muat semula anda. Apabila anda telah selesai, pilih **Tetapkan**. Jika anda ingin menjadualkan berbilang segar semula dalam satu hari, pilih **Tambah masa lagi**.

5. Pilih **Simpan** untuk menggunakan perubahan anda.

## <a name="about-tab"></a>Tab Perihal

Tab **Tentang** mengandungi **Nama paparan** organisasi anda, **ID Persekitaran** aktif, **Rantau** dan **ID Sesi** anda. Jika anda mempunyai lebih daripada satu persekitaran kerja, anda perlu memberikan setiap satunya nama paparan yang boleh dikenal pasti dengan mudah.

## <a name="general-tab"></a>Tab umum

Terdapat dua pilihan pada tab **Umum**, **Bahasa** dan **Format Negara/Rantau**.

Aplikasi ini [menyokong beberapa bahasa](supported-languages.md). Untuk mengubah bahasa pilihan anda, pilih **Bahasa** daripada juntai bawah.

Untuk mengubah format pilihan anda untuk tarikh, masa dan nombor, gunakan juntai bawah **Format Negara/Rantau**. Pratonton pemformatan dipaparkan di bawah medan ini. Sistem akan mencadangkan pemilihan secara automatik apabila anda memilih bahasa baharu.

Pilih **Simpan** untuk mengesahkan pilihan anda.

## <a name="api-usage-tab"></a>Tab penggunaan API

Cari butiran tentang penggunaan API masa nyata dan lihat peristiwa yang berlaku dalam tempoh masa yang diberikan. Anda memilih tempoh masa dalam menu juntai bawah **Pilih tempoh masa**. 

**Penggunaan API** mengandungi tiga bahagian: 
- **Panggilan API** - sebuah carta yang membayangkan bilangan panggilan teragregrat kepada API dalam tempoh masa yang dipilih.

- **Pemindahan data** - sebuah carta yang menunjukkan jumlah data yang dipindahkan melalui API dalam tempoh masa yang dipilih.

-  **Operasi** - sebuah jadual dengan baris untuk setiap operasi API tersedia dan butiran mengenai penggunaan operasi. Anda boleh memilih nama operasi untuk pergi ke [rujukan API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operasi yang menggunakan [pengingesan data masa nyata](real-time-data-ingestion.md) akan mengandungi butang dengan simbol binokular untuk melihat penggunaan API masa nyata. Pilih butang untuk membuka anak tetingkap sisi yang mengandungi butiran penggunaan untuk penggunaan API masa nyata dalam persekitaran semasa.   
   Gunakan kotak **Kumpulan mengikut** dalam anak tetingkap **Penggunaan API masa nyata** untuk memilih cara terbaik untuk menunjukkan interaksi masa nyata anda. Anda boleh mengumpulkan data mengikut kaedah API, nama dilayakkan entiti (entiti yang diinges), dicipta oleh (sumber peristiwa), hasil (berjaya atau gagal) atau kod ralat. Data tersedia sebagai carta sejarah dan sebagai jadual.


[!INCLUDE[footer-include](../includes/footer-banner.md)]