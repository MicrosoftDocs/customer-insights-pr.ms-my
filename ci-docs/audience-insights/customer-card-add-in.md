---
title: Pasang dan konfigurasi Tambahan Kad Pelanggan
description: Pasang dan konfigurasi tambahan Kad Pelanggan untuk Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597338"
---
# <a name="customer-card-add-in-preview"></a>Tambahan Kad Pelanggan (pratonton)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dapatkan pandangan 360 darjah pelanggan anda secara langsung dalam aplikasi Dynamics 365. Lihat demografi, wawasan dan tempoh masa aktiviti dengan Tambahan Kad Pelanggan.

## <a name="prerequisites"></a>Prasyarat

- Aplikasi Dynamics 365 (seperti Hab Jualan atau Hab Customer Service), versi 9.0 dan kemudian dengan Antara Muka Disatukan didayakan.
- Profil pelanggan yang [diinges daripada aplikasi Dynamics 365 yang menggunakan Common Data Service](connect-power-query.md).
- Pengguna Tambahan Kad Pelanggan perlu [ditambah sebagai pengguna](permissions.md) dalam cerapan khalayak.
- [Mengkonfigurasi keupayaan carian dan penapis](search-filter-index.md).
- Kawalan demografi: Medan demografi (seperti umur atau jantina) boleh didapati dalam profil pelanggan disatukan.
- Kawalan pengayaan: Memerlukan [pengayaan](enrichment-hub.md) aktif digunakan pada profil pelanggan.
- Kawalan kepintaran: Memerlukan data yang dihasilkan menggunakan Pembelajaran Mesin Azure ([Ramalan](predictions.md) atau [Model Tersuai](custom-models.md))
- Langkah kawalan: Memerlukan [langkah yang dikonfigurasikan](measures.md).
- Kawalan garis masa: Memerlukan [aktiviti yang dikonfigurasikan](activities.md).

## <a name="install-the-customer-card-add-in"></a>Pasangkan Tambahan Kad Pelanggan

Tambahan Kad Pelanggan ialah penyelesaian untuk aplikasi penglibatan pelanggan dalam Dynamics 365. Untuk memasang penyelesaian, pergi ke AppSource dan Cari **Kad Pelanggan Dinamik**. Pilih [Tambahan Kad Pelanggan pada AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) dan pilih **Dapatkannya Sekarang**.

Anda mungkin perlu mendaftar masuk dengan kelayakan pentadbir anda bagi aplikasi Dynamics 365 untuk memasang penyelesaian.

Ia boleh mengambil sedikit masa untuk penyelesaian dipasangkan ke persekitaran anda.

## <a name="configure-the-customer-card-add-in"></a>Konfigurasi Tambahan Kad Pelanggan

1. Sebagai pentadbir, pergi ke bahagian **Tetapan** dalam Dynamics 365 dan pilih **Penyelesaian**.

1. Pilih pautan **Nama Paparan** untuk penyelesaian **(Pratonton) Tambahan Kad Pelanggan Dynamics 365 Customer Insights**.

   > [!div class="mx-imgBorder"]
   > ![Pilih nama paparan](media/select-display-name.png "Pilih nama paparan")

1. Pilih **Log masuk** dan masukkan kelayakan akaun pentadbir yang anda gunakan untuk mengkonfigurasi Customer Insights.

   > [!NOTE]
   > Periksa sama ada penghalang timbul pelayar tidak menyekat tetingkap pengesahan apabila anda memilih butang **Log masuk**.

1. Pilih persekitaran yang ingin anda ambil data daripadanya.

1. Takrifkan pemetaan medan kepada rekod dalam aplikasi Dynamics 365.
   - Untuk memetakan dengan kenalan, pilih medan dalam entiti Pelanggan yang sepadan dengan ID entiti kenalan anda.
   - Untuk memetakan dengan akaun, pilih medan dalam entiti Pelanggan yang sepadan dengan ID entiti kenalan anda.

   > [!div class="mx-imgBorder"]
   > ![Medan ID Kenalan](media/contact-id-field.png "Medan ID kenalan")

1. Pilih **Simpan konfigurasi** untuk menyimpan tetapan.

1. Seterusnya, anda perlu menugaskan peranan keselamatan dalam Dynamics 365 supaya pengguna boleh menyesuaikan dan melihat kad pelanggan. Dalam Dynamics 365, pergi ke **Tetapan** > **Keselamatan** > **Pengguna**. Pilih pengguna untuk mengedit peranan pengguna dan pilih **Urus peranan**.

1. Peruntukkan peranan **Penyesuai Kad Customer Insights** kepada pengguna yang akan menyesuaikan kandungan yang ditunjukkan pada kad untuk seluruh organisasi.

## <a name="add-customer-card-controls-to-forms"></a>Tambah kawalan Kad Pelanggan pada borang
  
1. Untuk menambah kawalan Kad Pelanggan kepada borang Kenalan anda, pergi ke **Tetapan** > **Penyesuaian** dalam Dynamics 365.

1. Pilih **Sesuaikan Sistem**.

1. Semak lalu kepada entiti **Kenalan**, kembangkannya dan pilih **Borang**.

1. Pilih borang kenalan yang anda mahu tambah kawalan Kad Pelanggan.

    > [!div class="mx-imgBorder"]
    > ![Pilih borang Kenalan](media/contact-active-forms.png "Pilih borang Kenalan")

1. Untuk menambah kawalan, di dalam editor borang, seret sebarang medan daripada **Peneroka Medan** ke tempat anda mahu kawalan tersebut timbul.

1. Pilih medan pada borang yang anda baru tambah dan kemudian pilih **Tukar Ciri-Ciri**.

1. Pergi ke tab **Kawalan** dan pilih **Tambah Kawalan**. Pilih salah satu kawalan tersuai yang tersedia dan pilih **Tambah**.

1. Di dalam dialog **Ciri-Ciri Medan**, kosongkan kotak semak **Label paparan pada borang**.

1. Pilih pilihan **Web** untuk kawalan. Untuk kawalan Pengayaan, pilih jenis pengayaan yang anda mahu paparkan dengan mengkonfigurasikan medan **enrichmentType**. Tambah kawalan pengayaan berasingan untuk setiap jenis pengayaan.

1. Pilih **Simpan** dan **Terbitkan** untuk menerbitkan borang kenalan yang dikemas kini.

1. Pergi ke borang kenalan yang diterbitkan. Anda akan nampak kawalan yang baru ditambah. Anda mungkin perlu log masuk pertama kali anda menggunakannya.

1. Untuk sesuaikan apa yang anda mahu tunjukkan pada kawalan tersuai, pilih butang edit di sudut kanan atas.

## <a name="upgrade-customer-card-add-in"></a>Naik Taraf Tambahan Kad Pelanggan
Tambahan Kad Pelanggan tidak naik taraf secara automatik. Untuk naik taraf kepada versi terkini, ikuti prosedur ini dalam aplikasi Dynamics 365 yang mempunyai Tambahan yang dipasang.

1. Dalam aplikasi Dynamics 365, pergi ke **Tetapan** > **Penyesuaian** dan pilih **Penyelesaian**.

1. Dalam jadual tambahan, cari **CustomerInsightsCustomerCard** dan pilih baris.

1. Pilih **Gunakan Naik Taraf Penyelesaian** dalam bar tindakan.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Naik taraf penyelesaian dalam kawasan Penyesuaian aplikasi Dynamics 365":::

1. Selepas memulakan proses naik taraf, anda akan melihat penunjuk memuat sehingga naik taraf selesai. Jika tiada versi lebih baharu, naik taraf itu akan menunjukkan mesej ralat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]