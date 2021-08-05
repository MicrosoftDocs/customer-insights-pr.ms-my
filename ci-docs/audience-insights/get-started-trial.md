---
title: Cipta dan konfigurasikan percubaan Customer Insights
description: Langkah-langkah untuk mendapatkan langganan percubaan untuk Dynamics 365 Customer Insights dan mengkonfigurasikannya.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f80654f03252142ce08241ff3ca3606be4595740
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650493"
---
# <a name="set-up-a-trial-environment"></a>Sediakan persekitaran percubaan 

Percubaan Dynamics 365 Customer Insights membolehkan anda menyemak keupayaan utama dan mengetahui lebih lanjut tentang pelbagai ciri. Langganan percubaan dipadam selepas tamat tempoh. Persekitaran percubaan dicipta oleh pengguna individu yang menjadi pentadbir persekitaran percubaan mereka. Mereka boleh menjemput lebih ramai pengguna kepada percubaan mereka dan mengkonfigurasikan pelbagai ciri.

## <a name="create-a-trial-environment"></a>Cipta persekitaran percubaan

Anda boleh mendaftar untuk percubaan pada [halaman daftar percubaan](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Pilih pilihan **Daftar untuk percubaan percuma** dan pilih **Daftar sekarang**.

1. Berikan alamat e-mel kerja atau sekolah anda, beritahu kami lebih lanjut tentang diri anda dan pilih **Mulakan**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialog untuk mendaftar tika percubaan":::

1. Semak terma dan syarat dan pilih **Teruskan** untuk mengesahkan.

1. Berikan **Nama** untuk persekitaran baharu anda. 

1. Tetapkan **Jenis** persekitaran sebagai **Percubaan**.

1. Dalam medan **Pilih demo industri**, anda boleh memilih set data khusus industri secara pilihan. Anda juga boleh [menukar kepada demo industri](#use-industry-specific-demo-data-sets-in-audience-insights) kemudian dan mulakan dengan set data lalai.

1. Pilih **Rantau** untuk persekitaran anda.

1. Secara pilihan, jika anda ialah pentadbir organisasi Dynamics 365: Pilih **Tetapan lanjutan** dan sediakan URL organisasi anda untuk menggunakan ciri ramalan seperti ramalan pulangan pelanggan. 

1. Pilih **Cipta**. 

Ia mengambil masa seketika untuk melengkapkan persediaan persekitaran. Selepas selesai, anda dihalakan ke persekitaran demo atau demo industri yang anda pilih dalam langkah di atas. Anda kini boleh meneroka aplikasi dengan data demo baca sahaja. Untuk menambah data anda sendiri kepada persekitaran, lihat [Cipta data demo khusus senario dalam persekitaran anda sendiri](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Syot layar persekitaran percubaan yang baru dicipta.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Gunakan set data demo khusus industri dalam cerapan khalayak

Menyambungkan sumber data sebenar adalah salah satu langkah penting dalam menggunakan kuasa Customer Insights. Untuk mencuba ciri tanpa mengganggu data anda sendiri, anda boleh menggunakan data demo khusus industri secara pilihan. Terdapat beberapa set data demo yang tersedia untuk industri berikut: 

-   Automotif
-   Perbankan
-   Barangan pengguna
-   Kerajaan
-   Penjagaan Kesihatan
-   Hospitaliti
-   Insurans
-   Perkilangan
-   Perkhidmatan profesional
-   Peruncitan

### <a name="see-industry-specific-demo-data-in-trials"></a>Lihat data demo khusus industri dalam percubaan

Untuk versi baca sahaja Customer Insights, disesuaikan dengan industri atau senario tertentu, mulakan dalam persekitaran Demo. 
 
1.  Dalam cerapan khalayak, pilih persekitaran **Demo** dalam pemilih persekitaran.

2.  Pada **Utama**, pilih pilihan daripada Pilih menu juntai bawah demo industri.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Pilih industri untuk persekitaran percubaan.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Cipta data demo khusus senario dalam persekitaran anda sendiri

Sebagai pentadbir, pilih pemilih persekitaran dalam pengepala aplikasi untuk mencipta persekitaran baharu. Dalam persekitaran baharu, anda boleh mengkonfigurasi sumber data anda sendiri dan menyediakan aplikasi mengikut keperluan anda. 

1.  Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

2.  Untuk mengimport sumber data anda sendiri, pergi ke [panduan tentang pengingesan data](data-sources.md).     
   Jika anda lebih suka bekerja dengan data sampel yang membolehkan anda mencuba pengingesan data, anda boleh injes data demo industri dalam persekitaran anda. Pilih pilihan **Import daripada Datahub** dan ikuti langkah-langkah di bawah.

3.  Pilih kad industri yang sesuai dengan senario anda. 

4.  Semak dan kemas kini nama sumber data yang dicadangkan secara pilihan. 

5.  Pilih **Seterusnya** untuk menginges data sampel. 

Anda kini boleh menggunakan data yang diinges untuk menyesuaikan Customer Insights dengan senario anda. Untuk melihat persekitaran khusus untuk data demo yang diinges, pilih pilihan **Demo <Industry>** dalam pemilih persekitaran.

## <a name="limitations-in-trials"></a>Batasan dalam percubaan

- Percubaan aktif selama 30 hari secara lalai. Walau bagaimanapun, anda boleh melanjutkannya selepas hari ke-23 apabila anda mendaftar masuk kepada percubaan anda.
- Anda tidak boleh menggunakan akaun Azure Data Lake Storage anda sendiri untuk menyimpan data output semasa percubaan. Walau bagaimanapun, anda boleh menginges data daripada akaun storan Data Lake.
- Anda boleh menyimpan sehingga 3 GB data dalam persekitaran Dataverse yang diperuntukkan secara automatik apabila anda memulakan percubaan Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Salin data daripada percubaan kepada langganan berbayar

Secara amnya, kami mengesyorkan anda memulakan dengan segar dengan data anda sendiri apabila menaik taraf kepada versi berbayar Customer Insights. 

Secara pilihan, anda boleh menyalin data anda daripada persekitaran percubaan jika anda membeli Customer Insights. Anda mestilah seorang pentadbir percubaan Customer Insights dan pentadbir global penyewa Microsoft 365 anda atau pentadbir Dynamics 365 dalam organisasi anda untuk memindahkan tetapan daripada persekitaran percubaan kepada persekitaran berbayar. 

Selepas mendaftar masuk kepada tika berbayar Customer Insights anda buat kali pertama, anda diminta untuk mencipta persekitaran baru. Dalam proses ini, anda boleh memilih untuk menyalin konfigurasi daripada persekitaran sedia ada dan memindahkan kebanyakan tetapan. Jika anda mempunyai keizinan yang disebut di atas, persekitaran percubaan akan ditunjukkan dalam senarai ini. Untuk maklumat lanjut, lihat [Salin konfigurasi persekitaran](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Langkah seterusnya

Semak artikel berikut untuk membantu anda bermula dengan mengkonfigurasikan Customer Insights. 

- [Tambah lebih ramai pengguna dan peruntukkan keizinan](permissions.md).
- [Injes sumber data anda](data-sources.md) dan jalankannya melalui [proses penyatuan data](data-unification.md) untuk mendapatkan [profil pelanggan disatukan](customer-profiles.md).
- [Perkayakan profil pelanggan disatukan](enrichment-hub.md) atau [jalankan model ramalan](predictions-overview.md).
- Cipta [segmen](segments.md) kepada pelanggan kumpulan dan [ukur](measures.md) semakan KPI.
- Sediakan [sambungan](connections.md) dan [eksport](export-destinations.md) untuk memproses subset data anda dalam aplikasi lain.