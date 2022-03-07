---
title: Laporan corong
description: Cara menggunakan laporan corong untuk memahami cara khalayak membuat keputusan.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7bb961c5ba8d42f704eefe0dcb22e561367f3efb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226271"
---
# <a name="create-and-manage-funnel-reports"></a>Cipta dan urus laporan corong

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Laporan corong mengumpul maklumat tentang langkah-langkah yang berlaku semasa perjalanan pelanggan melalui tapak web atau aplikasi mudah alih anda. Ia membantu anda memahami tahap kemajuan khalayak sepanjang proses dan mengenal pasti titik berhenti. Contohnya, anda boleh menggunakan laporan corong untuk mengenal pasti laluan yang pelanggan anda ambil sebelum mereka membuat pembelian. Laporan corong menyediakan data untuk memaklumkan keputusan dan mengenal pasti kawasan untuk pengoptimuman dan penambahbaikan proses.

## <a name="create-a-funnel-report"></a>Cipta laporan corong

Untuk mencipta laporan corong, tentukan langkah yang anda mahu masukkan dan aktiviti untuk setiap langkah. Aktiviti ialah [peristiwa](glossary.md) yang mewakili tingkah laku pengguna. Laporan corong memaparkan bilangan pengguna yang melengkapkan setiap langkah yang ditakrifkan. 

1. Pergi ke **Corong** dan pilih **+Corong baharu** untuk memulakan laporan corong.

1. Dalam **Editor corong**, di bawah **Langkah** pilih **+Tambah langkah.** 

1. Masukkan nama dalam  **Tajuk langkah**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Laporan corong baharu.":::

1. Pilih **Aktiviti**. Aktiviti merekodkan apabila pengguna melihat halaman (Aktiviti **Pandangan**) atau berinteraksi dengan kandungan (aktiviti **Tindakan**).

1. Gunakan **Kriteria langkah** untuk menentukan dimensi aktiviti. [Dimensi](dimensions.md) ialah atribut yang boleh menerangkan, menapis atau mengumpulkan data.

1. Secara pilihan, anda boleh mengkonfigurasikan langkah corong berbilang syarat. Pilih **Tambah syarat** untuk menentukan lebih banyak dimensi dalam langkah. Kriteria tambahan mesti menggunakan jenis aktiviti yang sama. Anda boleh memilih jika berbilang syarat disambungkan dengan DAN atau ATAU operator.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Editor corong menunjukkan konfigurasi langkah dengan langkah berbilang syarat.":::

1. Pilih **Tambah langkah** sehingga anda melengkapkan semua langkah yang anda mahu dalam laporan.

1. Pilih **Simpan**, namakan laporan dan **Simpan** semula. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Contoh: Laporan corong syarikat Fourth Coffee

Senario berikut menunjukkan satu cara menggunakan laporan corong. Seorang penganalisis dengan syarikat Fourth Coffee mahu memahami pengaruh promosi terkini terhadap kadar langganan. Penganalisis mencipta laporan corong untuk mengenal pasti aktiviti pelanggan. Ia bermula apabila pelanggan tiba pada laman utama syarikat sehingga mereka menggunakan kod promosi langganan. Penganalisis mencipta laporan corong dengan langkah berikut:

Langkah 1: Pelanggan yang tiba pada laman utama   
Langkah 2: Pelanggan yang membuat pembelian   
Langkah 3: Pelanggan yang menggunakan kod promosi untuk mendapatkan diskaun untuk langganan   
Langkah 4: Pendaftaran langganan   

:::image type="content" source="media/funnel-report-example.png" alt-text="contoh laporan corong.":::
  
Corong ini membolehkan anda melihat bilangan pengguna yang menggunakan kod promosi selepas pembelian sekali untuk mendaftar program langganan.

### <a name="configure-advanced-settings"></a>Konfigurasikan tetapan lanjutan 

Laporan corong membolehkan anda menentukan had pada masa yang diperlukan untuk melengkapkan corong. Contohnya, anda boleh menetapkan masa untuk melengkapkan corong kepada empat hari. Tetapan ini hanya akan mengira pendaftaran langganan yang berjaya yang berlaku dalam tempoh empat hari pengguna melawat laman utama.

1. Pergi ke **Corong** untuk membuka **Pustaka corong**.

1. Pilih nama untuk membuka laporan. 

1. Dalam anak tetingkap **Editor Corong** pilih **Tetapan lanjutan**. 

1. Tetapkan had masa pelengkapan corong ke **Hidup**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Editor corong menunjukkan tetapan lanjutan dan pilihan untuk mengehadkan masa untuk melengkapkan corong.":::

1. Pilih masa corong mesti dilengkapkan dalam **Had set pada** senarai juntai bawah.

1. Pilih **Simpan** untuk menggunakan perubahan anda.


## <a name="cross-channel-funnel-reports"></a>Laporan corong silang saluran 

Cerapan penglibatan juga boleh mengumpul data tingkah laku pelanggan pada aplikasi mudah alih anda. Setelah anda telah memulakan aplikasi mudah alih anda dengan cerapan penglibatan [SDK Android](get-started-android.md) atau [SDK iOS](get-started-ios.md), anda boleh membuat laporan corong silang saluran. 

### <a name="create-a-cross-channel-funnel-report"></a>Cipta laporan corong silang saluran 

1. Ikut langkah-langkah untuk [mencipta laporan corong](#create-a-funnel-report).    

1. Untuk mengesan cara pelanggan anda berinteraksi dengan jenama anda di kedua-dua tapak web dan aplikasi mudah alih anda atau berbilang tapak web, gunakan penukar ruang kerja untuk mencipta langkah corong dengan data daripada ruang kerja lain. Dalam **Editor Corong**, di bawah **Langkah-langkah**, pilih ruang kerja tempat asal data untuk langkah corong anda.

## <a name="manage-funnel-reports"></a>Urus laporan corong

Anda boleh menyemak laporan corong untuk menganalisis data, menjejaki prestasi dan mengumpulkan cerapan.

> [!NOTE]
> - Laporan corong cerapan penglibatan pada masa ini menyokong senario yang semua penggunanya yang berada dalam corong adalah tanpa nama atau semua pengguna disahkan. 
> - Data sejarah dalam laporan corong tersedia untuk 30 hari yang lalu.

### <a name="view-funnel-reports"></a>Lihat laporan corong

1. Pergi ke **Corong** untuk membuka **Pustaka corong**.
1. Pilih nama untuk membuka laporan.    

### <a name="see-the-data-collected-for-a-report"></a>Lihat data yang dikumpulkan untuk laporan   

Untuk melihat maklumat mengenai fasa

- Tujukan pada langkah dalam laporan.

:::image type="content" source="media/funnel-step-data.png" alt-text="data corong.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Ubah julat tarikh untuk laporan corong

1. Pergi ke **Corong** untuk membuka **Pustaka corong**.

1. Pilih nama untuk membuka laporan.

1. Buka **julat masa** dan pilih tempoh masa baharu daripada senarai atau **Julat tarikh tetap** untuk menentukan julat tarikh.

## <a name="edit-or-delete-funnel-reports"></a>Edit atau padam laporan corong

Anda boleh mengubah nama laporan corong, memadamkannya atau mengubah suai langkah dalam laporan.

### <a name="rename-or-delete-a-funnel-report"></a>Namakan semula atau padamkan laporan corong

1. Pergi ke **Corong** untuk membuka **Pustaka corong**. 

1. Pilih **Lebih banyak** bersebelahan laporan yang mahu ubah dan pilih **Edit nama** atau **Padam**.

### <a name="edit-a-funnel-step"></a>Edit langkah corong  

1. Pergi ke **Corong** untuk membuka **Pustaka corong**. 

1. Pilih nama untuk membuka laporan.

1. Pilih langkah yang anda mahu edit.

1. Pilih **Edit**.

1. Dalam **Editor Corong**, kemas kini maklumat yang anda mahu ubah.  

1. Pilih **Simpan**.

### <a name="reorder-a-funnel-step"></a>Susun semula langkah corong

1. Pergi ke **Corong** untuk membuka **Pustaka corong**. 

1. Pilih nama untuk membuka laporan.

1. Pilih langkah yang anda mahu susun semula.

1. Pilih **Alihkan** dan kemudian **Naik**, **Turun**, **Ke atas** atau **Ke bawah**, untuk mengalihkan langkah.

### <a name="delete-a-funnel-step"></a>Padam langkah corong

1. Pergi ke **Corong** untuk membuka **Pustaka corong**. 

1. Pilih nama untuk membuka laporan.

1. Pilih langkah yang anda mahu alih keluar dan kemudian pilih **Padam**.

## <a name="funnel-insights"></a>Cerapan corong 

Cerapan penglibatan kini menawarkan cerapan corong untuk pelanggan. Gunakan cerapan corong untuk mendapatkan cerapan mendalam berkaitan tingkah laku pelanggan tentang langkah dalam laporan corong anda. Apabila anda mencipta dan menyimpan laporan corong baharu, cerapan corong akan dijana secara automatik untuk laporan anda. 

:::image type="content" source="media/funnel-insights.png" alt-text="Cerapan corong.":::

> [!NOTE]
> Cerapan corong hanya boleh dijana untuk langkah corong yang **tidak** termasuk dimensi tersuai. Untuk menjana cerapan corong untuk semua langkah dalam corong anda, gunakan cerapan penglibatan dimensi di luar kotak untuk mencipta langkah corong anda. 

Anda boleh melihat cerapan corong daripada kategori yang berikut, pada peringkat utama dan peringkat langkah: 

 - Kadar penukaran
 -    Kadar penukaran antara Daftar Keluar and Beli ialah 22%.
 - Masa peralihan 
 -    Masa peralihan purata antara Kart dan Daftar Keluar ialah 23 minit. 
 - Masa pelengkapan 
 -    Purata jumlah masa yang diperlukan oleh pelanggan untuk menyelesaikan corong tersebut ialah 47 minit. 

Gunakan cerapan ini untuk teroka lebih mendalam berkaitan tingkah laku pelanggan dan memahami titik tolak serta penukaran dengan lebih baik untuk laporan corong anda. 

Untuk membandingkan cerapan merentasi langkah yang berbeza, pilih **Lihat pecahan langkah** atau **Bandingkan dengan langkah lain** daripada kad cerapan. Ini akan memaparkan graf bar membandingkan metrik untuk setiap langkah corong. 

Cerapan corong mengira semula setiap 24 jam atau apabila anda **Menyimpan** laporan corong anda. 

> [!NOTE]
> Untuk melihat cerapan untuk corong anda, anda mesti menyimpan laporan anda setiap kali anda membuat perubahan. 

