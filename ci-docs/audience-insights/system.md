---
title: Konfigurasi sistem dalam cerapan khalayak
description: Ketahui tentang seting sistem dalam Dynamics 365 Customer Insights keupayaan wawasan khalayak.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1b790106f8b9617d0c1f244e1d15a74c7ef9a82b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732381"
---
# <a name="system-configuration"></a>Konfigurasi sistem

Untuk mencapai konfigurasi sistem dalam wawasan khalayak, dari bar navigasi kiri pilih **Sistem Pentadbir untuk melihat senarai tugas dan proses** > **·** sistem.

Halaman **Sistem** termasuk tab berikut:
- [Status](#status-tab)
- [Jadual](#schedule-tab)
- [Penggunaan API](#api-usage-tab)
- [Perihal](#about-tab)
- [Umum](#general-tab)
- [Keselamatan](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Tab tetapan pada halaman sistem.":::

## <a name="status-tab"></a>Tab status

**Tab Status membolehkan anda menjejak kemajuan** tugas, pengambilan data, eksport data dan beberapa proses produk penting yang lain. Kaji semula maklumat pada tab ini untuk memastikan kesempurnaan tugas dan proses aktif anda.

Tab ini termasuk jadual dengan status dan pemprosesan maklumat untuk pelbagai proses. Setiap jadual menjejaki **Nama** tugas dan entitinya yang sepadan, **Status** jalanannya paling terkini dan masa ia **Dikemas kini terakhir**. Anda boleh melihat butiran beberapa yang terakhir berjalan dengan memilih tugas atau nama proses. 

Pilih status di sebelah tugas atau proses dalam **lajur Status untuk membuka anak tetingkap Butiran** **·** Kemajuan.

   :::image type="content" source="media/system-progress-details.png" alt-text="Anak tetingkap butiran kemajuan sistem":::

### <a name="status-definitions"></a>Definisi status

Sistem menggunakan status berikut untuk tugas dan proses:

|Status  |Takrif  |
|---------|---------|
|Dibatalkan |Pemprosesan telah dibatalkan oleh pengguna sebelum ia selesai.   |
|Gagal   |Kemasukan data mempunyai ralat.         |
|Kegagalan  |Pemprosesan telah gagal.  |
|Tidak dimulakan   |Sumber data belum mempunyai data diinges atau masih dalam mod draf.         |
|Pemprosesan  |Tugas atau proses sedang dijalankan.  |
|Menyegar semula    |Kemasukan data sedang berjalan. Anda boleh membatalkan operasi ini dengan memilih **Hentikan menyegar semula** di dalam lajur **Tindakan**. Hentikan segar semula sumber data akan kembali ke keadaan segar semula terakhir.       |
|Dilangkau  |Tugas atau proses dilangkau. Satu atau lebih proses hiliran yang diharapkan oleh tugas ini telah gagal atau dilangkau.|
|Berjaya  |Tugas atau proses berjaya diselesaikan. Untuk sumber data, menunjukkan data telah berjaya diestested jika masa disebutkan dalam **lajur Disegar** semula.|
|Dibaris | Pemprosesan dibaris gilir dan akan bermula sebaik sahaja semua tugas dan proses huluan selesai. Untuk maklumat lanjut, lihat [Menyegar semula proses](#refresh-processes).|

### <a name="refresh-processes"></a>Proses segar semula

Segar semula untuk tugas dan proses dijalankan mengikut jadual yang [dikonfigurasi](#schedule-tab). 

|Proses  |Penerangan  |
|---------|---------|
|Aktiviti  |Berjalan secara manual (segar semula masa tunggal). Bergantung pada proses cantuman. Wawasan bergantung pada pemprosesannya.|
|Pemautan analisis |Berjalan secara manual (segar semula masa tunggal). Bergantung kepada segmen.  |
|Persediaan analisis |Berjalan secara manual (segar semula masa tunggal). Bergantung kepada segmen.  |
|Penyediaan data   |Bergantung kepada cantuman.   |
|Sumber data   |Tidak bergantung kepada mana-mana proses lain. Padanan bergantung pada penyelesaian yang berjaya untuk proses ini.  |
|Pengayaan   |Berjalan secara manual (segar semula masa tunggal). Bergantung pada proses cantuman. |
|Destinasi eksport |Berjalan secara manual (segar semula masa tunggal). Bergantung kepada segmen.  |
|Wawasan |Berjalan secara manual (segar semula masa tunggal). Bergantung kepada segmen.  |
|Kecerdasan   |Bergantung kepada cantuman.   |
|Padankan |Bergantung pada pemprosesan sumber data yang digunakan dalam definisi padanan.      |
|Ukuran  |Berjalan secara manual (segar semula masa tunggal). Bergantung pada proses cantuman.  |
|Gabungkan   |Bergantung pada penyelesaian proses padanan. Segmen, langkah, pengayaan, carian, aktiviti, ramalan dan penyediaan data bergantung pada penyelesaian yang berjaya untuk proses ini.   |
|Profil   |Berjalan secara manual (segar semula masa tunggal). Bergantung pada proses cantuman. |
|Carian   |Berjalan secara manual (segar semula masa tunggal). Bergantung pada proses cantuman. |
|Segmen  |Berjalan secara manual (segar semula masa tunggal). Bergantung pada proses cantuman. Wawasan bergantung pada pemprosesannya.|
|Sistem   |Bergantung pada penyelesaian proses padanan. Segmen, langkah, pengayaan, carian, aktiviti, ramalan dan penyediaan data bergantung pada penyelesaian yang berjaya untuk proses ini.   |
|Pengguna  |Berjalan secara manual (segar semula masa tunggal). Bergantung kepada entiti.  |

Pilih status proses untuk melihat butiran kemajuan keseluruhan kerja yang berada di dalamnya. Proses segar semula di atas boleh membantu memahami perkara yang anda boleh lakukan untuk menangani **tugas atau proses yang dilangkau atau** **Dibariskan.**

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

Anda boleh mengubah format bahasa dan negara/rantau pada tab **Umum**.

Wawasan Pelanggan [menyokong banyak](/dynamics365/get-started/availability) bahasa. Aplikasi ini menggunakan keutamaan bahasa anda untuk memaparkan elemen seperti menu, teks label dan mesej sistem dalam bahasa diutamakan anda.

Data yang diimport dan maklumat yang anda masukkan secara manual tidak diterjemahkan.

### <a name="update-the-settings"></a>Kemas kini tetapan

Untuk mengubah bahasa pilihan anda, pilih **Bahasa** daripada juntai bawah.

Untuk mengubah format pilihan anda untuk tarikh, masa dan nombor, gunakan juntai bawah **Format Negara/Rantau**. Pratonton pemformatan dipaparkan di bawah medan ini. Sistem akan mencadangkan pemilihan secara automatik apabila anda memilih bahasa baharu.

Pilih **Simpan** untuk mengesahkan pilihan anda.

## <a name="api-usage-tab"></a>Tab penggunaan API

Cari butiran tentang penggunaan API masa nyata dan lihat peristiwa yang berlaku dalam tempoh masa yang diberikan. Anda memilih tempoh masa dalam menu juntai bawah **Pilih tempoh masa**. 

**Penggunaan API** mengandungi tiga bahagian: 
- **Panggilan API** - sebuah carta yang membayangkan bilangan panggilan teragregrat kepada API dalam tempoh masa yang dipilih.

- **Pemindahan data** - sebuah carta yang menunjukkan jumlah data yang dipindahkan melalui API dalam tempoh masa yang dipilih.

-  **Operasi** - sebuah jadual dengan baris untuk setiap operasi API tersedia dan butiran mengenai penggunaan operasi. Anda boleh memilih nama operasi untuk pergi ke [rujukan API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operasi yang menggunakan [pengingesan data masa nyata](real-time-data-ingestion.md) mengandungi butang dengan simbol binokular untuk melihat penggunaan API masa nyata. Pilih butang untuk membuka anak tetingkap sisi yang mengandungi butiran penggunaan untuk penggunaan API masa nyata dalam persekitaran semasa.   
   Gunakan kotak **Kumpulan mengikut** dalam anak tetingkap **Penggunaan API masa nyata** untuk memilih cara terbaik untuk menunjukkan interaksi masa nyata anda. Anda boleh mengumpulkan data mengikut kaedah API, nama dilayakkan entiti (entiti yang diinges), dicipta oleh (sumber peristiwa), hasil (berjaya atau gagal) atau kod ralat. Data tersedia sebagai carta sejarah dan sebagai jadual.

## <a name="security-tab"></a>Tab keselamatan

Tab **Keselamatan** membolehkan anda memautkan dan menguruskan [Azure key vault](/azure/key-vault/general/basic-concepts) untuk persekitaran.
Key vault yang ditetapkan boleh digunakan untuk peringkat dan menggunakan rahsia dalam sempadan pematuhan organisasi. Cerapan khalayak boleh menggunakan rahsia dalam Azure Key Vault untuk [menyediakan sambungan](connections.md) kepada sistem pihak ketiga.

Untuk maklumat lanjut, lihat [Bawa Azure key vault anda sendiri](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
