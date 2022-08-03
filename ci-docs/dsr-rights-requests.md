---
title: Permintaan Hak Subjek Data (DSR) di bawah GDPR | Microsoft Docs
description: Respons kepada Permintaan Subjek Data untuk Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146706"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Permintaan Hak Subjek Data (DSR) di bawah GDPR

Peraturan Perlindungan Data Umum (GDPR) Kesatuan Eropah telah berkuat kuasa sejak 25 Mei 2018. Peraturan ini memberikan hak penting kepada individu berkenaan data mereka. GDPR adalah tentang melindungi dan mendayakan hak privasi individu. Anda boleh membaca lebih lanjut tentang komitmen Microsoft terhadap keselamatan dan pematuhan di [Pusat Amanah Microsoft](https://www.microsoft.com/trust-center).

Kami komited untuk membantu para pelanggan kami memenuhi keperluan GDPR mereka. Ini termasuk hak untuk memadamkan dan mengeksport data yang mengandungi maklumat peribadi seperti ID pengguna, nombor telefon dan alamat e-mel. Pentadbir boleh melaksanakan permintaan pengguna untuk memadamkan atau mengeksport data peribadi.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Respons kepada permintaan pemadaman subjek data GDPR untuk Dynamics 365 Customer Insights

"Hak untuk pemadaman" dengan memadam data peribadi daripada data pelanggan organisasi adalah perlindungan utama dalam Peraturan Perlindungan Data Umum (GDPR). Mengeluarkan data peribadi termasuk mengeluarkan semua data peribadi dan log janaan sistem kecuali maklumat log audit.

#### <a name="manage-data-subject-delete-requests"></a>Urus permintaan padam subjek data

Wawasan Pelanggan menawarkan pengalaman dalam produk berikut untuk memadamkan data peribadi untuk pelanggan atau pengguna tertentu:

- **Urus permintaan padam untuk data pelanggan**: Data pelanggan dalam Customer Insights telah ditelan daripada sumber data asal luaran kepada Customer Insights. Lakukan permintaan padam GDPR dalam sumber data asal terlebih dahulu.
- **Urus permintaan padam untuk data pengguna Customer Insights**: Data untuk pengguna dicipta oleh Customer Insights. Semua permintaan penghapusan GDPR mesti dilakukan di dalam Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Urus permintaan untuk memadamkan data pelanggan

Pentadbir Wawasan Pelanggan boleh mengikuti langkah ini untuk mengalih keluar data pelanggan yang telah dipadamkan dalam sumber data. Pastikan permintaan padam telah dilakukan dalam sumber data anda sebelum meneruskan langkah-langkah yang disenaraikan di bawah. 

1. Daftar masuk ke Dynamics 365 Customer Insights.
1. Pergi ke **sumber Data Data** > **·**
1. Untuk setiap sumber data dalam senarai yang mengandungi data pelanggan yang dipadamkan:
   1. Pilih elipsis menegak (&vellip;) dan kemudian pilih **Segar Semula**.
   1. Semak status sumber data di bawah **Status**. Tanda semak bermaksud segar semula berjaya. Segi tiga amaran bermaksud berlaku suatu kesalahan. Jika segi tiga amaran dipaparkan, hubungi D365CI@microsoft.com.
1. Selepas segar semula sumber data yang berjaya, jalankan segar semula hiliran juga. Terutama, jika anda tidak mempunyai segar semula penuh berulang Wawasan Pelanggan yang dijadualkan. 

> [!IMPORTANT]
> Segmen statik tidak termasuk dalam segar semula penuh atau menjalankan segar semula hiliran selepas permintaan padam. Untuk memastikan data pelanggan dialih keluar daripada segmen statik juga, cipta semula segmen statik dengan data sumber yang disegarkan semula.

> [!div class="mx-imgBorder"]
> ![Mengendalikan permintaan pemadaman GDPR untuk data pelanggan.](media/gdpr-data-sources.png "Urus permintaan penghapusan GDPR untuk data pelanggan")

##### <a name="manage-delete-requests-for-user-data"></a>Urus permintaan padam untuk data pengguna

Pentadbir Customer Insights boleh mengikut langkah ini untuk menghapuskan data pengguna Customer Insights:

1. Daftar masuk ke Dynamics 365 Customer Insights.
2. Pergi ke **Keizinan** > **Keselamatan** > **Pentadbir**.
3. Tandakan kotak semak untuk pengguna yang anda mahu hapuskan.
4. Pilih **Alih keluar**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Respons kepada permintaan export subjek data GDPR

Sebagai sebahagian daripada komitmen kami untuk bekerjasama dengan anda dalam perjalanan anda ke Peraturan Perlindungan Data Umum (GDPR), kami telah membangunkan dokumentasi untuk membantu anda bertindak balas terhadap permintaan daripada subjek data.

#### <a name="manage-export-and-view-requests"></a>Urus permintaan eksport dan pandangan

Hak kemudahalihan data membenarkan subjek data untuk meminta salinan data peribadi mereka dalam format elektronik (ditakrifkan sebagai "berstruktur, biasa digunakan, mesin boleh dibaca dan format saling boleh kendali") yang boleh dihantar kepada pengawal data yang lain.

##### <a name="export-customer-data-tenant-admin"></a>Eksport data pelanggan (pentadbir penyewa)

Pentadbir penyewa boleh mengikuti langkah-langkah ini untuk mengeksport data:

1. Hantar e-mel kepada D365CI@microsoft.com untuk menentukan alamat e-mel pelanggan di dalam permintaan. Pasukan Customer Insights akan menghantar e-mel kepada alamat e-mel pentadbir penyewa berdaftar, meminta pengesahan untuk mengeksport data.
2. Memberitahu pengesahan untuk mengeksport data untuk pelanggan yang diminta.
3. Menerima data yang dieksport melalui alamat e-mel pentadbir penyewa.

##### <a name="export-user-data-tenant-admin"></a>Eksport data pengguna (pentadbir penyewa)

1. Hantar e-mel kepada D365CI@microsoft.com untuk menentukan alamat e-mel pengguna di dalam permintaan. Pasukan Customer Insights akan menghantar e-mel kepada alamat e-mel pentadbir penyewa berdaftar, meminta pengesahan untuk mengeksport data.
2. Memberitahu pengesahan untuk mengeksport data untuk pengguna yang diminta.
3. Menerima data yang dieksport melalui alamat e-mel pentadbir penyewa.

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Pengendalian penghapusan data dalam Dynamics 365 Customer Insights

1. Data akan dipadamkan (sekatan data dan gambar data) jika partition data dan gambar data tidak aktif selama lebih dari 30 hari, yang bermaksud mereka telah digantikan dengan partition data baru dan gambar melalui segar semula sumber data.
2. Tidak semua data dan gambar dipadamkan. Pembahagian data dan petikan data terkini adalah mengikut definisi aktif kerana ia digunakan dalam Wawasan Pelanggan. Untuk data terkini, tidak kira sama ada sumber data tidak disegar semula dalam tempoh 30 hari yang lalu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
