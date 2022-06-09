---
title: Tambahan Kad Pelanggan untuk aplikasi Dynamics 365 (mengandungi video)
description: Tunjukkan data profil pelanggan daripada Wawasan Pelanggan dalam aplikasi Dynamics 365 dengan tambahan ini.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8508880bb3274bb491a314a043a5222d4d381073
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755647"
---
# <a name="customer-card-add-in-preview"></a>Tambahan Kad Pelanggan (pratonton)

Dapatkan pandangan 360 darjah pelanggan anda secara langsung dalam aplikasi Dynamics 365. Dengan Tambahan Kad Pelanggan yang dipasang dalam aplikasi Dynamics 365 yang disokong, anda boleh memilih untuk memaparkan medan profil, cerapan dan garis masa aktiviti pelanggan. Tambahan akan mendapatkan data daripada Customer Insights tanpa mempengaruhi data dalam aplikasi Dynamics 365 yang disambung.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Prasyarat

- Tambahan hanya berfungsi dengan aplikasi berpandukan model Dynamics 365 seperti Jualan atau Khidmat Pelanggan versi 9.0 dan kemudian.
- Untuk data Dynamics 365 anda memetakan ke profil pelanggan Wawasan Pelanggan, kami mengesyorkan ia [ditelan daripada aplikasi Dynamics 365 menggunakan Microsoft Dataverse penyambung](connect-power-query.md). Jika anda menggunakan kaedah yang berbeza untuk menelan kenalan Dynamics 365 (atau akaun), anda perlu memastikan `contactid` medan (atau `accountid`) ditetapkan sebagai [kunci utama untuk sumber data tersebut dalam langkah peta proses penyatuan data](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Semua pengguna Dynamics 365 Tambahan Kad Pelanggan mesti ditambah [sebagai pengguna](permissions.md) dalam Wawasan Pelanggan untuk melihat data.
- [Keupayaan](search-filter-index.md) carian dan penapis yang dikonfigurasikan dalam Wawasan Pelanggan diperlukan untuk mencari data berfungsi.
- Setiap kawalan tambahan bergantung pada data tertentu dalam Wawasan Pelanggan. Sesetengah data dan kawalan hanya tersedia dalam persekitaran jenis tertentu. Konfigurasi tambahan akan memberitahu anda jika kawalan tidak tersedia kerana jenis persekitaran yang dipilih. Ketahui lebih lanjut tentang [kes penggunaan persekitaran](work-with-business-accounts.md).
  - **Kawalan ukuran** : memerlukan [ukuran dikonfigurasikan](measures.md) bagi jenis atribut pelanggan.
  - **Kawalan perisikan**: Memerlukan data yang dijana menggunakan [ramalan atau model](predictions-overview.md) tersuai.
  - **Kawalan butiran pelanggan** : Semua medan daripada profil tersedia dalam profil pelanggan disatukan.
  - **Kawalan pengayaan**: Memerlukan aktif [penggayaan](enrichment-hub.md) digunakan ke profil pelanggan. Tambahan kad menyokong pengayaan ini: [Jenama](enrichment-microsoft.md) yang disediakan oleh Microsoft, [Kepentingan](enrichment-microsoft.md) yang disediakan oleh Microsoft dan [data](enrichment-office.md) penglibatan Office yang disediakan oleh Microsoft.
  - **Kawalan kenalan** : Memerlukan definisi entiti semantik bagi jenis kenalan.
  - **Kawalan garis masa**: Memerlukan [aktiviti yang dikonfigurasikan](activities.md).

## <a name="install-the-customer-card-add-in"></a>Pasangkan Tambahan Kad Pelanggan

Tambahan Kad Pelanggan ialah penyelesaian untuk aplikasi penglibatan pelanggan dalam Dynamics 365. Untuk memasang penyelesaian, pergi ke AppSource dan Cari **Kad Pelanggan Dinamik**. Pilih [Tambahan Kad Pelanggan pada AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) dan pilih **Dapatkannya Sekarang**.

Anda mungkin perlu mendaftar masuk dengan kelayakan pentadbir anda bagi aplikasi Dynamics 365 untuk memasang penyelesaian. Ia boleh mengambil sedikit masa untuk penyelesaian dipasangkan ke persekitaran anda.

## <a name="configure-the-customer-card-add-in"></a>Konfigurasi Tambahan Kad Pelanggan

1. Sebagai pentadbir, pergi ke bahagian **Tetapan** dalam Dynamics 365 dan pilih **Penyelesaian**.

1. Pilih pautan **Nama Paparan** untuk penyelesaian **(Pratonton) Tambahan Kad Pelanggan Dynamics 365 Customer Insights**.

   > [!div class="mx-imgBorder"]
   > ![Pilih nama paparan.](media/select-display-name.png "Pilih nama paparan.")

1. Pilih **Log masuk** dan masukkan kelayakan akaun pentadbir yang anda gunakan untuk mengkonfigurasi Customer Insights.

   > [!NOTE]
   > Periksa sama ada penghalang timbul pelayar tidak menyekat tetingkap pengesahan apabila anda memilih butang **Log masuk**.

1. Pilih persekitaran Customer Insights yang anda mahu ambil data daripadanya.

1. Takrifkan pemetaan medan ke rekod dalam aplikasi Dynamics 365. Bergantung pada data anda dalam Customer Insights yang anda boleh pilih untuk memetakan pilihan berikut:
   - Untuk memetakan dengan kenalan, pilih medan dalam entiti Pelanggan yang sepadan dengan ID entiti kenalan anda.
   - Untuk memetakan dengan akaun, pilih medan dalam entiti Pelanggan yang sepadan dengan ID entiti kenalan anda.

   > [!div class="mx-imgBorder"]
   > ![Medan ID kenalan.](media/contact-id-field.png "Medan ID kenalan.")

1. Pilih **Simpan konfigurasi** untuk menyimpan tetapan.

1. Seterusnya, anda perlu menugaskan peranan keselamatan dalam Dynamics 365 supaya pengguna boleh menyesuaikan dan melihat kad pelanggan. Dalam Dynamics 365, pergi ke **Tetapan** > **Keselamatan** > **Pengguna**. Pilih pengguna untuk mengedit peranan pengguna dan pilih **Urus peranan**.

1. Peruntukkan peranan **Penyesuai Kad Customer Insights** kepada pengguna yang akan menyesuaikan kandungan yang ditunjukkan pada kad untuk seluruh organisasi.

## <a name="add-customer-card-controls-to-forms"></a>Tambah kawalan Kad Pelanggan pada borang

Bergantung pada senario anda, anda boleh memilih untuk menambahkan kawalan kepada sama ada borang **Kenalan** atau borang **Akaun**. Jika persekitaran Wawasan Pelanggan anda adalah untuk akaun perniagaan, kami mengesyorkan anda menambah kawalan pada borang Akaun. Dalam kes tersebut, gantikan "kenalan" dalam langkah di bawah dengan "akaun."

1. Untuk menambah kawalan Kad Pelanggan kepada borang Kenalan anda, pergi ke **Tetapan** > **Penyesuaian** dalam Dynamics 365.

1. Pilih **Sesuaikan Sistem**.

1. Layari ke entiti **Kenalan**, kembangkannya dan pilih **Borang**.

1. Pilih borang kenalan yang anda mahu untuk tambah kawalan Kad Pelanggan ke.

    > [!div class="mx-imgBorder"]
    > ![Pilih borang Kenalan.](media/contact-active-forms.png "Pilih borang Kenalan.")

1. Untuk menambah kawalan, di dalam editor borang, seret sebarang medan daripada **Peneroka Medan** ke tempat anda mahu kawalan tersebut timbul.

1. Pilih medan pada borang yang anda baru tambah dan kemudian pilih **Ubah Sifat**.

1. Pergi ke tab **Kawalan** dan pilih **Tambah Kawalan**. Pilih salah satu kawalan tersuai yang tersedia dan pilih **Tambah**.

1. Di dalam dialog **Ciri-Ciri Medan**, kosongkan kotak semak **Label paparan pada borang**.

1. Pilih pilihan **Web** untuk kawalan. Untuk kawalan Pengayaan, pilih jenis pengayaan yang anda mahu paparkan dengan mengkonfigurasikan medan **enrichmentType**. Tambah kawalan pengayaan berasingan untuk setiap jenis pengayaan.

1. Pilih **Simpan** dan **Terbitkan** untuk menerbitkan borang kenalan yang dikemas kini.

1. Pergi ke borang kenalan yang diterbitkan. Anda akan nampak kawalan yang baru ditambah. Anda mungkin perlu log masuk pertama kali anda menggunakannya.

1. Untuk sesuaikan apa yang anda mahu tunjukkan pada kawalan tersuai, pilih butang edit di sudut kanan atas.

## <a name="upgrade-customer-card-add-in"></a>Naik Taraf Tambahan Kad Pelanggan

Tambahan Kad Pelanggan tidak naik taraf secara automatik. Untuk menaik taraf kepada versi terkini, ikuti langkah ini dalam aplikasi Dynamics 365 yang mempunyai tambahan yang dipasang.

1. Dalam aplikasi Dynamics 365, pergi ke **Tetapan** > **Penyesuaian** dan pilih **Penyelesaian**.

1. Dalam jadual tambahan, cari **CustomerInsightsCustomerCard** dan pilih baris.

1. Pilih **Gunakan Naik Taraf Penyelesaian** dalam bar tindakan.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Naik taraf penyelesaian dalam kawasan Penyesuaian aplikasi Dynamics 365.":::

1. Selepas memulakan proses naik taraf, anda akan melihat penunjuk memuat sehingga naik taraf selesai. Jika tiada versi lebih baharu, naik taraf itu akan menunjukkan mesej ralat.

## <a name="troubleshooting"></a>Pencarisilapan

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Kawalan daripada Tambahan Kad Pelanggan tidak menemui data

**Masalah:**

Walaupun dengan medan ID yang dikonfigurasikan dengan betul, kawalan tidak dapat mencari data untuk mana-mana pelanggan.  

**Penyelesaian:**

1. Pastikan anda mengkonfigurasi Tambahan Kad mengikut arahan: [Konfigurasikan Tambahan Kad Pelanggan](#configure-the-customer-card-add-in)

1. Semak konfigurasi pengingesan data. Edit sumber data untuk sistem Dynamics 365 yang mengandungi ID kenalan GUID. Jika ID kenalan GUID ditunjukkan dengan aksara huruf besar dalam Power Query editor, cuba langkah berikut:
    1. Edit sumber data untuk membuka sumber data dalam Power Query Editor.
    1. Pilih lajur ID kenalan.
    1. Pilih **Transform** dalam bar pengepala untuk melihat tindakan yang tersedia.
    1. Pilih **huruf kecil**. Sahkan jika GUID dalam jadual kini huruf kecil.
    1. Simpan sumber data.
    1. Jalankan proses pengambilan data, penyatuan, dan hiliran untuk menyebarkan perubahan kepada GUID.

Selepas sistem selesai segar semula penuh, kawalan Tambahan Kad Pelanggan harus menunjukkan data yang dijangkakan.

[!INCLUDE [footer-include](includes/footer-banner.md)]