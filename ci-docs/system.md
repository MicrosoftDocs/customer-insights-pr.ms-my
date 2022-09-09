---
title: Lihat konfigurasi sistem
description: Ketahui tentang tetapan sistem dalam Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 6e60bf7c18939a29f660e06989e262deeb59a39b
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396012"
---
# <a name="view-system-configuration"></a>Lihat konfigurasi sistem

Lihat maklumat sistem, status sistem dan penggunaan API.

## <a name="view-api-usage"></a>Lihat penggunaan API

Lihat butiran tentang penggunaan API masa nyata dan lihat peristiwa yang berlaku dalam tempoh masa tertentu.

1. Pergi ke **Sistem** > **Pentadbir** dan pilih tab **penggunaan** API.

1. **Pilih rangka** masa untuk dilihat.

   Halaman **penggunaan** API mengandungi tiga seksyen:

   - **Panggilan API** - sebuah carta yang membayangkan bilangan panggilan teragregrat kepada API dalam tempoh masa yang dipilih.
   - **Pemindahan data** - sebuah carta yang menunjukkan jumlah data yang dipindahkan melalui API dalam tempoh masa yang dipilih.
   - **Operasi** - sebuah jadual dengan baris untuk setiap operasi API tersedia dan butiran mengenai penggunaan operasi. Pilih nama operasi untuk pergi ke [rujukan](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) API.

## <a name="view-system-information"></a>Lihat maklumat sistem

Lihat nama paparan persekitaran, ID, rantau, jenis dan ID sesi.

1. Pergi ke **Sistem** > **Pentadbir** dan pilih tab **Perihal**.

1. Untuk melihat bahasa dan negara/rantau, pilih tab **Umum**.

### <a name="update-preferred-language-or-countryregion"></a>Mengemas kini bahasa atau negara/rantau pilihan

Wawasan [Pelanggan menyokong banyak bahasa](/dynamics365/get-started/availability). Aplikasi ini menggunakan keutamaan bahasa anda untuk memaparkan elemen seperti menu, teks label dan mesej sistem dalam bahasa diutamakan anda.

Data yang diimport dan maklumat yang anda masukkan secara manual tidak diterjemahkan.

1. Pergi ke **Sistem** > **Pentadbir** dan pilih tab **Umum**.

1. Untuk mengubah bahasa pilihan anda, pilih **Bahasa** daripada juntai bawah.

1. Untuk mengubah format pilihan anda untuk tarikh, masa dan nombor, gunakan juntai bawah **Format Negara/Rantau**. Pratonton pemformatan dipaparkan. Sistem ini secara automatik mencadangkan pilihan apabila anda memilih bahasa baru.

1. Pilih **Simpan**.

## <a name="view-system-status"></a>Lihat status sistem

Menjejaki kemajuan tugas, pengingesan data, eksport data dan beberapa proses produk penting lain. Semak semula maklumat untuk memastikan kesempurnaan tugas dan proses aktif anda.

1. Pergi ke **Sistem** > **Pentadbir** dan pilih tab **Status**.

   Status dan memproses maklumat untuk pelbagai proses dipaparkan. **Lihat Nama** tugas, **Status** larian terbarunya dan masa ia **dikemas kini** terakhir.

1. Untuk melihat butiran beberapa larian terakhir, pilih nama tugas atau proses.

1. Untuk melihat butiran kemajuan bagi tugas, pilih status. Anak **tetingkap butiran** Kemajuan dipaparkan.

   :::image type="content" source="media/system-progress-details.png" alt-text="Anak tetingkap butiran kemajuan sistem":::

1. Untuk melihat butiran kemajuan bagi semua tugas, pilih **Seluruh aliran kerja**.

### <a name="status-definitions"></a>Definisi status

Sistem ini menggunakan status berikut untuk tugas dan proses:

|Status  |Takrif  |
|---------|---------|
|Dibatalkan |Tugas atau proses telah dibatalkan oleh pengguna sebelum ia selesai.   |
|Gagal   |Tugas atau proses menghadapi ralat.         |
|Kegagalan  |Tugas atau proses telah gagal.  |
|Belum dimulakan   |Sumber data tidak mempunyai data yang ditelan lagi atau tugas masih dalam mod draf.         |
|Pemprosesan  |Tugas atau proses sedang berjalan.  |
|Menyegar semula    |Tugas atau proses sedang berjalan. Untuk membatalkan operasi ini, pilih **Segar** Semula dan **Batalkan kerja**. Menghentikan penyegaran semula tugas atau proses akan mengembalikannya kepada keadaan segar semula terakhirnya.       |
|Dilangkau  |Tugas atau proses dilangkau. Satu atau lebih proses hiliran yang diharapkan oleh tugas ini telah gagal atau dilangkau.|
|Berjaya  |Tugas atau proses berjaya diselesaikan. Untuk sumber data, menunjukkan data telah berjaya ditelan jika masa disebut dalam **lajur Segar Semula**.|
|Berbaris Gilir | Pemprosesan beratur dan akan bermula sebaik sahaja semua tugas dan proses hulu selesai. Untuk maklumat lanjut, lihat [Menyegar semula proses](#refresh-processes).|

### <a name="refresh-processes"></a>Menyegar semula proses

Segar semula untuk tugas dan proses dijalankan mengikut jadual [yang dikonfigurasi](schedule-refresh.md).

|Proses  |Description  |
|---------|---------|
|Aktiviti  |Berjalan secara manual (segar semula masa tunggal). Bergantung pada proses cantuman. Wawasan bergantung pada pemprosesannya.|
|Pemautan analisis |Berjalan secara manual (segar semula masa tunggal). Bergantung kepada segmen.  |
|Persediaan analisis |Berjalan secara manual (segar semula masa tunggal). Bergantung kepada segmen.  |
|Penyediaan data   |Memerlukan entiti untuk dijalankan. Sumber data entiti bergantung kepada pengingesan. Entiti yang diperkaya bergantung kepada pengayaan. Entiti Pelanggan bergantung kepada gabungan.  |
|Sumber data   |Tidak bergantung kepada mana-mana proses lain. Padanan bergantung pada penyelesaian yang berjaya untuk proses ini.  |
|Pengayaan   |Berjalan secara manual (segar semula masa tunggal). Bergantung pada proses cantuman. |
|Eksport destinasi |Berjalan secara manual (segar semula masa tunggal). Bergantung kepada segmen.  |
|Wawasan |Berjalan secara manual (segar semula masa tunggal). Bergantung kepada segmen.  |
|Risikan   |Bergantung pada cantuman.   |
|Padankan |Bergantung pada pemprosesan sumber data yang digunakan dalam definisi padanan.      |
|Langkah  |Berjalan secara manual (segar semula masa tunggal). Bergantung pada proses cantuman.  |
|Gabungkan   |Bergantung pada penyelesaian proses padanan. Segmen, langkah, pengayaan, carian, aktiviti, ramalan dan penyediaan data bergantung pada penyelesaian yang berjaya untuk proses ini.   |
|Profil   |Berjalan secara manual (segar semula masa tunggal). Bergantung pada proses cantuman. |
|Carian   |Berjalan secara manual (segar semula masa tunggal). Bergantung pada proses cantuman. |
|Segmen  |Berjalan secara manual (segar semula masa tunggal). Bergantung pada proses cantuman. Wawasan bergantung pada pemprosesannya.|
|Sistem   |Bergantung pada penyelesaian proses padanan. Segmen, langkah, pengayaan, carian, aktiviti, ramalan dan penyediaan data bergantung pada penyelesaian yang berjaya untuk proses ini.   |
|User  |Berjalan secara manual (segar semula masa tunggal). Bergantung kepada entiti.  |

Pilih status proses untuk melihat butiran kemajuan keseluruhan kerja yang dijalankannya. Proses segar semula di atas boleh membantu memahami perkara yang boleh anda lakukan untuk menangani tugas atau proses Yang **Dilangkau** atau **Beratur**.


[!INCLUDE [footer-include](includes/footer-banner.md)]
