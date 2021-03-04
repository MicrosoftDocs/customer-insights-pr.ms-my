---
title: Halaman utama dalam Insights khalayak
description: Mula terokai aplikasi pada Halaman utama.
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477052"
---
# <a name="create-a-new-environment"></a>Cipta persekitaran baru

## <a name="create-a-trial-environment"></a>Cipta persekitaran percubaan

Anda boleh mendaftar untuk percubaan pada [halaman daftar percubaan](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Percubaan tamat tempoh selepas 30 hari.

1. Pilih pilihan **Daftar untuk percubaan percuma** dan pilih **Daftar sekarang**.

1. Berikan alamat e-mel kerja atau sekolah anda, beritahu kami tentang diri anda dan pilih **Seterusnya**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialog untuk mendaftar tika percubaan":::

1. Berikan **Nama** untuk persekitaran baharu anda. 

1. Pilih jenis percubaan.

1. Pilih **Rantau** untuk persekitaran anda.

1. Secara pilihan, untuk pentadbir organisasi Dynamics 365: Pilih **Tetapan lanjutan** dan berikan URL organisasi anda untuk menggunakan ciri ramalan seperti pulangan pelanggan.

1. Pilih **Cipta**. 

Selepas persekitaran dicipta, anda akan melihat persekitaran **Demonstrasi** yang membolehkan anda menerokai aplikasi dengan data rekaan. Anda boleh mengubah data sampel untuk dipadankan dengan industri anda. Pilih ikon **Tetapan** dalam pengepala dan pilih **Tetapan demonstrasi**. Selain itu, anda boleh mengubah tema visual. 

Anda [bertukar kepada persekitaran](#switch-environments) yang anda cipta semasa proses pendaftaran untuk bekerja dengan data anda sendiri.

## <a name="create-a-new-production-or-sandbox-environment"></a>Mencipta persekitaran pengeluaran baharu atau kotak pasir

Dalam persekitaran anda, pilih pemilih **Persekitaran** dalam pengepala aplikasi dan pilih **Baharu**.

Ikuti langkah seolah-olah anda [mencipta persekitaran percubaan](#create-a-trial-environment). Secara lalai, data disimpan dalam Data Lake diuruskan Customer Insights. Anda akan mendapat pilihan tambahan apabila memilih **Tetapan lanjutan** untuk menyimpan data anda dalam Azure Data Lake anda sendiri. Berikan nama akaun anda dan kunci akaun untuk mewujudkan sambungan ke Azure Data Lake anda. 

> [!IMPORTANT]
> Dengan menyimpan data kepada Azure Data Lake Storage, anda bersetuju bahawa data akan dipindahkan kepada dan disimpan di lokasi geografi yang sesuai untuk akaun storan Azure, yang mungkin berbeza daripada tempat data disimpan dalam Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat Amanah Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Terokai halaman utama

Anda boleh [mengakses wawasan khalayak daripada Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) pada URL berikut: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
Halaman **Utama** menunjukkan gambaran keseluruhan segmen, langkah dan data pengayaan (jika dikonfigurasikan) selepas melengkapkan fasa [peta](map-entities.md), [padanan](match-entities.md), dan [gabung](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Wawasan pada Halaman utama](media/home-page-insights.png "Wawasan pada Halaman utama")

Di bawah **Segmen terbaru**, anda melihat kumpulan pelanggan berasaskan demografik, tingkah laku atau atribut transaksi yang telah anda takrifkan. [Mencipta segmen](segments.md) membantu anda untuk mengumpulkan asas pelanggan anda dan lebih menyasarkan aktiviti perniagaan anda.

**Ukuran terkini** menunjukkan jubin dengan [penunjuk prestasi utama (KPI)](measures.md) yang anda takrifkan. Sebagai contoh, purata kemungkinan pelanggan untuk pusing atau purata perbelanjaan dalam talian setiap pelanggan.

Bahagian **Pengayaan terbaru** menyenaraikan hasil jalanan pengayaan yang terbaru selesai. [Pengayaan](enrichment-hub.md) menambah maklumat tentang asas pelanggan anda. Contohnya, dengan memahami minat dan jenama yang menjadi tarikan mereka.

## <a name="switch-environments"></a>Tukar persekitaran

Pilih kawalan **Persekitaran** pada sudut kanan atas halaman untuk mengubah persekitaran.

> [!div class="mx-imgBorder"] 
> ![Tukar persekitaran](media/home-page-environment-switcher.png "Tukar persekitaran")

Pentadbir boleh mencipta dan menguruskan [berbilang persekitaran](manage-environments.md). Mengekalkan lebih daripada satu persekitaran mungkin berguna jika, contohnya, organisasi anda beroperasi di peringkat antarabangsa dan anda perlu mengasingkan data dan cerapan dengan cara berbeza.

## <a name="next-step"></a>Langkah seterusnya

Untuk melihat cerapan anda sendiri pada halaman utama, pertama sekali, anda perlu [menambahkan sumber data](data-sources.md) dan [menyatukan](data-unification.md) data anda untuk membina profil pelanggan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]