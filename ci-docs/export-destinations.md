---
title: Eksport gambaran keseluruhan (pratonton)
description: Urus eksport untuk berkongsi data.
ms.date: 08/12/2022
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
ms.openlocfilehash: 44f58d694b9bd35a8d8c04d487d40743291e0566
ms.sourcegitcommit: ef3e17134d44d2731605381ea0385dbc5aef6120
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460201"
---
# <a name="exports-preview-overview"></a>Eksport gambaran keseluruhan (pratonton)

 Eksport membolehkan anda berkongsi data tertentu dengan pelbagai aplikasi. Ia boleh termasuk profil pelanggan, entiti, skema dan butiran pemetaan. Setiap eksport memerlukan [sambungan, yang disediakan oleh pentadbir, untuk menguruskan pengesahan dan akses](connections.md). Halaman **Eksport** menunjukkan semua eksport yang dikonfigurasikan.

## <a name="export-types"></a>Jenis eksport

Terdapat dua jenis eksport utama:  

- **Eksport data keluar** membolehkan anda mengeksport sebarang jenis entiti yang tersedia dalam Wawasan Pelanggan. Entiti yang anda pilih untuk eksport akan dieksport dengan semua medan data, metadata, skema dan butiran pemetaan.
- **Eksport segmen** membolehkan anda mengeksport entiti segmen dari Wawasan Pelanggan. Bagi pengguna individu (B-to-C), segmen mewakili senarai profil pelanggan. Untuk perniagaan (B-to-B), [segmen boleh mewakili senarai akaun atau kenalan](segment-builder.md#create-a-new-segment-with-segment-builder). Apabila mengkonfigurasi eksport, anda memilih medan data yang disertakan, bergantung pada sistem sasaran yang anda mengeksport data.

### <a name="export-segments"></a>Bahagian eksport

**Mengeksport segmen dalam persekitaran untuk akaun perniagaan (niaga-ke-niaga) atau pelanggan individu (niaga-ke-pengguna)**  
Kebanyakan pilihan eksport menyokong kedua-dua jenis persekitaran. Mengeksport segmen ke pelbagai sistem sasaran mempunyai keperluan khusus. 

**Eksport segmen dalam persekitaran untuk pelanggan individu (Niaga-ke-Pengguna)**  
- Segmen dalam konteks persekitaran untuk pelanggan individu dibina pada entiti *profil pelanggan disatukan*. Setiap segmen yang memenuhi keperluan sistem sasaran (contohnya, alamat e-mel) boleh dieksport.

**Eksport segmen dalam persekitaran untuk akaun perniagaan (B-to-B)**  
- Segmen dalam konteks persekitaran untuk akaun perniagaan dibina di atas *entiti akaun* atau *entiti hubungan*. Untuk mengeksport segmen akaun seperti sedia ada, sistem sasaran perlu menyokong segmen akaun tulen. Ini ialah kes untuk [LinkedIn](export-linkedin-ads.md) apabila anda memilih pilihan **syarikat** semasa mentakrifkan eksport.
- Semua sistem sasaran lain memerlukan medan daripada entiti kenalan.
- Dengan dua jenis segmen (kenalan dan akaun), Wawasan Pelanggan secara automatik mengenal pasti jenis segmen mana yang layak untuk dieksport berdasarkan sistem sasaran. Sebagai contoh, untuk sistem sasaran berfokuskan hubungan seperti Mailchimp, Wawasan Pelanggan hanya membolehkan anda memilih segmen kenalan untuk dieksport.

**Had pada eksport segmen**  
- Sistem sasaran pihak ketiga boleh mengehadkan bilangan profil pelanggan yang boleh anda eksport. 
- Untuk pelanggan individu, anda akan melihat bilangan sebenar ahli segmen apabila anda memilih segmen untuk eksport. Anda akan mendapat amaran jika segmen terlalu besar. 
- Untuk akaun perniagaan, anda akan melihat bilangan akaun atau kenalan bergantung pada segmen tersebut. Anda akan mendapat amaran jika segmen terlalu besar. Melebihi had hasil sistem sasaran akan melangkau eksport.

## <a name="set-up-a-new-export"></a>Sediakan eksport baharu

Untuk menyediakan atau mengedit eksport, anda memerlukan sambungan yang betul yang tersedia untuk anda. Sambungan bergantung kepada [peranan pengguna](permissions.md) anda:
- **Pentadbir** mempunyai capaian ke semua sambungan. Mereka juga boleh mencipta sambungan baharu apabila menyediakan eksport.
- **Penyumbang** boleh mempunyai capaian ke sambungan khusus. Mereka bergantung kepada pentadbir untuk mengkonfigurasi dan berkongsi sambungan. Senarai eksport menunjukkan penyumbang sama ada mereka boleh mengedit atau hanya melihat eksport dalam lajur **Keizinan anda**. Untuk mendapatkan maklumat lanjut, pergi ke [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Penonton** hanya boleh melihat eksport sedia ada—tidak menciptanya.

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport** untuk mencipta eksport baharu.

1. **Dalam anak tetingkap Sediakan eksport**, pilih sambungan [untuk](connections.md) digunakan.

1. Berikan butiran yang diperlukan dan pilih **Simpan** untuk mencipta eksport. Untuk butiran yang diperlukan, semak dokumentasi Wawasan Pelanggan untuk eksport tertentu.

## <a name="manage-existing-exports"></a>Urus eksport sedia ada

Pergi ke **Eksport** > **Data** untuk melihat eksport, nama sambungan, jenis sambungan dan statusnya. Semua peranan pengguna boleh melihat eksport yang dikonfigurasikan. Anda boleh mengisih senarai eksport mengikut mana-mana lajur atau menggunakan kotak carian untuk mencari eksport yang anda ingin uruskan.

Pilih eksport untuk melihat tindakan yang tersedia.

:::image type="content" source="media/exports_showmore.png" alt-text="Halaman eksport.":::

- **Lihat** atau **Edit** eksport. Pengguna tanpa keizinan mengedit, pilih **Lihat** dan bukannya **Edit** untuk melihat butiran eksport.
- **Jalankan** eksport untuk mengeksport data terkini.
- **Buat pendua** eksport.
- **[Jadualkan](#schedule-and-run-exports)** eksport.
- **Tanggalkan sambungan** untuk mengalih keluar sambungan untuk eksport ini. Terlepas tidak mengalih keluar sambungan, tetapi menyahaktifkan eksport. Lajur Sambungan yang **digunakan** memaparkan Tiada Sambungan.
- **Alih keluar** eksport.

## <a name="schedule-and-run-exports"></a>Jadualkan dan jalankan eksport

Setiap eksport yang dikonfigurasikan mempunyai jadual segar semula. Semasa segar semula, sistem mencari data baharu atau yang dikemas kini untuk disertakan dalam eksport. Secara lalai, eksport dijalankan sebagai sebahagian daripada setiap [segar semula sistem yang dijadualkan](schedule-refresh.md). Anda boleh menyesuaikan jadual segar semula atau mematikan proses itu untuk menjalankan eksport secara manual.

> [!TIP]
> Kurangkan masa pemprosesan eksport segmen dengan amalan terbaik berikut:
> - Mengedarkan entiti segmen merentasi eksport mutiple.
> - Elakkan menjadualkan semua eksport pada masa yang sama. Biarkan 30 minit atau satu jam antara masa yang dijadualkan bagi setiap eksport.

Jadual eksport bergantung pada keadaan persekitaran anda. Jika terdapat kemas kini yang sedang berjalan pada [kebergantungan](system.md#refresh-processes) apabila eksport yang dijadualkan harus bermula, sistem akan melengkapkan kemas kini terlebih dahulu dan kemudian menjalankan eksport. Lajur **Disegar** semula menunjukkan apabila eksport terakhir disegar semula.

### <a name="schedule-exports"></a>Jadualkan eksport

Tentukan jadual segar semula tersuai untuk eksport individu atau beberapa eksport sekaligus. Jadual yang ditentukan pada masa ini disenaraikan dalam lajur **Jadual** senarai eksport. Keizinan untuk mengubah jadual adalah sama seperti [mengedit dan mentakrifkan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Pilih eksport yang ingin anda jadualkan.

1. Pilih **Jadual**.

1. Dalam anak tetingkap **Eksport jadual**, tetapkan **Jalankan jadual** ke **Hidup** untuk menjalankan eksport secara automatik. Tetapkan ke **Mati** untuk menyegarkan semula jadual secara manual.

1. Untuk eksport yang disegarkan semula secara automatik, pilih nilai **Ulangan** dan tentukan butiran untuk eksport tersebut. Masa yang ditentukan terpakai kepada semua tika ulangan. Sudah tiba masanya eksport harus mula menyegarkan semula.

1. Pilih **Simpan**.

Apabila mengedit jadual untuk beberapa eksport, buat pilihan di bawah **Simpan atau penggantian jadual**:

- **Simpan jadual** individu: Simpan jadual yang telah ditetapkan sebelum ini untuk eksport yang dipilih dan hanya nyahdayakan atau dayakannya.
- **Tentukan jadual baharu untuk semua eksport yang dipilih**: Gantikan jadual sedia ada bagi eksport yang dipilih.

### <a name="run-exports-on-demand"></a>Jalankan eksport atas permintaan

Untuk mengeksport data tanpa menunggu segar semula berjadual, pergi ke **Data** > **Eksport**.

- Untuk menjalankan semua eksport, pilih **Jalankan semua** dalam bar perintah. Hanya eksport yang mempunyai jadual aktif dijalankan. Untuk menjalankan eksport yang tidak aktif, jalankan eksport tunggal.
- Untuk menjalankan eksport tunggal, pilih dalam senarai dan pilih **Jalankan** dalam bar perintah.

## <a name="troubleshooting"></a>Pencarisilapan

### <a name="segment-not-eligible-for-export"></a>Segmen tidak layak untuk eksport

**Masalah** Dalam persekitaran akaun perniagaan eksport anda gagal dengan mesej ralat: "Segmen berikut tidak layak untuk destinasi eksport ini: '{nama segmen}'. Sila pilih hanya segmen jenis ContactProfile dan cuba lagi.

**Persekitaran Wawasan Pelanggan Resolusi** untuk akaun perniagaan telah dikemas kini untuk menyokong segmen hubungan sebagai tambahan kepada segmen akaun. Oleh kerana perubahan itu, eksport yang memerlukan butiran hubungan hanya berfungsi dengan segmen berdasarkan kenalan.

1. [Cipta segmen berdasarkan kenalan](segment-builder.md) yang sepadan dengan segmen yang anda gunakan sebelum ini.

1. Sebaik sahaja segmen kenalan itu dijalankan, edit eksport masing-masing dan pilih segmen baharu.

1. Pilih **Simpan** untuk menyimpan konfigurasi atau **Simpan dan jalankan** untuk menguji eksport ini dengan segera.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
