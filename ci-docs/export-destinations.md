---
title: Eksport gambaran keseluruhan (pratonton)
description: Urus eksport untuk berkongsi data.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: fd234aff9021ded76d8226bf2f15e035cf75e7db
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245338"
---
# <a name="exports-preview-overview"></a>Eksport gambaran keseluruhan (pratonton)

 Eksport membolehkan anda berkongsi data tertentu dengan pelbagai aplikasi. Ia boleh termasuk profil pelanggan, entiti, skema dan butiran pemetaan. Setiap eksport memerlukan [sambungan, yang disediakan oleh pentadbir, untuk menguruskan pengesahan dan akses](connections.md). Halaman **Eksport** menunjukkan semua eksport yang dikonfigurasikan.

## <a name="export-types"></a>Jenis eksport

Terdapat dua jenis eksport utama:  

- **Eksport data keluar**: eksport sebarang jenis entiti yang tersedia dalam Wawasan Pelanggan. Entiti yang anda pilih untuk eksport akan dieksport dengan semua medan data, metadata, skema dan butiran pemetaan.
- **Eksport segmen**: entiti segmen eksport dari Wawasan Pelanggan. Segmen mewakili senarai profil pelanggan. Apabila mengkonfigurasi eksport, anda memilih medan data yang disertakan, bergantung pada sistem sasaran yang anda eksport data.

### <a name="export-segments"></a>Bahagian eksport

**Mengeksport segmen dalam persekitaran untuk akaun perniagaan (niaga-ke-niaga) atau pelanggan individu (niaga-ke-pengguna)**  
Kebanyakan pilihan eksport menyokong kedua-dua jenis persekitaran. Mengeksport segmen ke pelbagai sistem sasaran mempunyai keperluan khusus. 

**Eksport segmen dalam persekitaran untuk pelanggan individu (Niaga-ke-Pengguna)**  
- Segmen dalam konteks persekitaran untuk pelanggan individu dibina pada entiti *profil pelanggan disatukan*. Setiap segmen yang memenuhi keperluan sistem sasaran (contohnya, alamat e-mel) boleh dieksport.

**Persekitaran eksport segmen untuk akaun perniagaan (niaga-ke-niaga)**  
- Segmen dalam konteks persekitaran untuk akaun perniagaan dibina pada entiti *akaun*. Untuk mengeksport segmen akaun seperti sedia ada, sistem sasaran perlu menyokong segmen akaun tulen. Ini ialah kes untuk [LinkedIn](export-linkedin-ads.md) apabila anda memilih pilihan **syarikat** semasa mentakrifkan eksport.
- Semua sistem sasaran lain memerlukan medan daripada entiti kenalan. Untuk memastikan segmen akaun boleh mendapatkan data daripada kenalan yang berkaitan, takrifan segmen anda perlu untuk atribut projek entiti kenalan. Ketahui lebih lanjut tentang cara [mengkonfigurasikan segmen dan atribut projek](segment-builder.md).

**Had pada eksport segmen**  
- Sistem sasaran pihak ketiga boleh mengehadkan bilangan profil pelanggan yang boleh anda eksport. 
- Untuk pelanggan individu, anda akan melihat bilangan sebenar ahli segmen apabila anda memilih segmen untuk eksport. Anda akan mendapat amaran jika segmen terlalu besar. 
- Untuk akaun perniagaan, anda akan melihat bilangan akaun dalam segmen; walau bagaimanapun, bilangan kenalan yang mungkin diunjurkan tidak ditunjukkan. Dalam sesetengah kes, ini mungkin membawa kepada segmen yang dieksport sebenarnya mengandungi lebih banyak profil pelanggan daripada menerima sistem sasaran. Sekiranya had sistem sasaran melebihi, eksport dilangkau.

## <a name="set-up-a-new-export"></a>Sediakan eksport baharu

Untuk menyediakan atau mengedit eksport, anda memerlukan sambungan yang betul yang tersedia untuk anda. Sambungan bergantung kepada [peranan pengguna](permissions.md) anda:
- **Pentadbir** mempunyai capaian ke semua sambungan. Mereka juga boleh mencipta sambungan baharu apabila menyediakan eksport.
- **Penyumbang** boleh mempunyai capaian ke sambungan khusus. Mereka bergantung kepada pentadbir untuk mengkonfigurasi dan berkongsi sambungan. Senarai eksport menunjukkan penyumbang sama ada mereka boleh mengedit atau hanya melihat eksport dalam lajur **Keizinan anda**. Untuk mendapatkan maklumat lanjut, pergi ke [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Penonton** hanya boleh melihat eksport sedia ada—tidak menciptanya.

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport** untuk mencipta eksport baharu.

1. Dalam anak tetingkap **Sediakan eksport**, pilih sambungan [yang](connections.md) hendak digunakan.

1. Berikan butiran yang diperlukan dan pilih **Simpan** untuk mencipta eksport. Untuk butiran yang diperlukan, semak dokumentasi Wawasan Pelanggan untuk eksport tertentu.

## <a name="manage-existing-exports"></a>Urus eksport sedia ada

Pergi ke **Eksport** > **Data** untuk melihat eksport, nama sambungan mereka, jenis sambungan dan status. Semua peranan pengguna boleh melihat eksport yang dikonfigurasikan. Anda boleh mengisih senarai eksport mengikut mana-mana lajur atau menggunakan kotak carian untuk mencari eksport yang anda ingin uruskan.

Pilih eksport untuk melihat tindakan yang tersedia.

:::image type="content" source="media/exports_showmore.png" alt-text="Halaman eksport.":::

- **Lihat** atau **Edit** eksport. Pengguna tanpa keizinan mengedit, pilih **Lihat** dan bukannya **Edit** untuk melihat butiran eksport.
- **Jalankan** eksport untuk mengeksport data terkini.
- **Buat pendua** eksport.
- **[Jadualkan](#schedule-and-run-exports)** eksport.
- **Buang sambungan** untuk mengalih keluar sambungan untuk eksport ini. Detach tidak mengalih keluar sambungan, tetapi menyahaktifkan eksport. Lajur Sambungan yang **digunakan** memaparkan Tiada Sambungan.
- **Keluarkan** eksport.

## <a name="schedule-and-run-exports"></a>Jadualkan dan jalankan eksport

Setiap eksport yang dikonfigurasikan mempunyai jadual segar semula. Semasa segar semula, sistem mencari data baharu atau yang dikemas kini untuk disertakan dalam eksport. Secara lalai, eksport dijalankan sebagai sebahagian daripada setiap [segar semula sistem yang dijadualkan](schedule-refresh.md). Anda boleh menyesuaikan jadual segar semula atau mematikan proses itu untuk menjalankan eksport secara manual.

Jadual eksport bergantung pada keadaan persekitaran anda. Jika terdapat kemas kini yang sedang berjalan pada [kebergantungan](system.md#refresh-processes) apabila eksport yang dijadualkan harus bermula, sistem akan melengkapkan kemas kini terlebih dahulu dan kemudian menjalankan eksport. Lajur **Segar Semula** ditunjukkan apabila eksport kali terakhir disegarkan semula.

### <a name="schedule-exports"></a>Jadualkan eksport

Tentukan jadual segar semula tersuai untuk eksport individu atau beberapa eksport sekaligus. Jadual yang ditentukan pada masa ini disenaraikan dalam lajur **Jadual** senarai eksport. Kebenaran untuk mengubah jadual adalah sama seperti [mengedit dan menentukan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Pilih eksport yang ingin anda jadualkan.

1. Pilih **Jadual**.

1. Dalam anak tetingkap **Eksport jadual**, tetapkan **Jalankan jadual** ke **Hidup** untuk menjalankan eksport secara automatik. Tetapkan ke **Mati** untuk menyegarkan semula jadual secara manual.

1. Untuk eksport yang disegarkan semula secara automatik, pilih nilai **Ulangan** dan tentukan butiran untuk eksport tersebut. Masa yang ditentukan terpakai kepada semua tika ulangan. Sudah tiba masanya eksport harus mula menyegarkan semula.

1. Pilih **Simpan**.

Apabila mengedit jadual untuk beberapa eksport, buat pilihan di bawah **Simpan atau batalkan jadual**:

- **Kekalkan jadual** individu: Kekalkan jadual yang ditetapkan sebelum ini untuk eksport yang dipilih dan hanya lumpuhkan atau dayakannya.
- **Tentukan jadual baharu untuk semua eksport yang dipilih**: Gantikan jadual sedia ada bagi eksport yang dipilih.

### <a name="run-exports-on-demand"></a>Jalankan eksport atas permintaan

Untuk mengeksport data tanpa menunggu segar semula berjadual, pergi ke **Data** > **Eksport**.

- Untuk menjalankan semua eksport, pilih **Jalankan semua** dalam bar perintah. Hanya eksport yang mempunyai jadual aktif dijalankan. Untuk menjalankan eksport yang tidak aktif, jalankan eksport tunggal.
- Untuk menjalankan eksport tunggal, pilih dalam senarai dan pilih **Jalankan** dalam bar perintah.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
