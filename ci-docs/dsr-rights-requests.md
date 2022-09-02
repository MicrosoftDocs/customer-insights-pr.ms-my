---
title: Permintaan Hak Subjek Data (DSR) di bawah GDPR | Microsoft Docs
description: Respons kepada Permintaan Subjek Data untuk Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387122"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Permintaan Hak Subjek Data (DSR) di bawah GDPR

Peraturan Perlindungan Data Umum (GDPR) Kesatuan Eropah telah berkuat kuasa sejak 25 Mei 2018. Peraturan ini memberikan hak penting kepada individu berkenaan data mereka. GDPR adalah tentang melindungi dan mendayakan hak privasi individu. Baca lebih lanjut tentang komitmen Microsoft terhadap keselamatan dan pematuhan di [Pusat Amanah Microsoft](https://www.microsoft.com/trust-center).

Kami komited untuk membantu para pelanggan kami memenuhi keperluan GDPR mereka. Ia termasuk hak untuk memadam atau mengeksport data yang merangkumi maklumat peribadi seperti ID pengguna, nombor telefon dan alamat e-mel. Pentadbir boleh melaksanakan permintaan pengguna untuk memadamkan atau mengeksport data peribadi.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Memberi respons kepada permintaan pemadaman subjek data GDPR untuk Wawasan Pelanggan

"Hak untuk pemadaman" dengan memadam data peribadi daripada data pelanggan organisasi adalah perlindungan utama dalam Peraturan Perlindungan Data Umum (GDPR). Mengeluarkan data peribadi termasuk mengeluarkan semua data peribadi dan log janaan sistem kecuali maklumat log audit.

### <a name="manage-data-subject-delete-requests"></a>Urus permintaan padam subjek data

Wawasan Pelanggan menawarkan pengalaman dalam produk berikut untuk memadam data peribadi untuk pelanggan atau pengguna tertentu:

- **Urus permintaan padam untuk data pelanggan**: Data pelanggan dalam Customer Insights telah ditelan daripada sumber data asal luaran kepada Customer Insights. Melaksanakan permintaan pemadaman GDPR dalam sumber data asal terlebih dahulu.
- **Urus permintaan padam untuk data pengguna Customer Insights**: Data untuk pengguna dicipta oleh Customer Insights. Melaksanakan semua permintaan pemadaman GDPR dalam Wawasan Pelanggan.

#### <a name="manage-requests-to-delete-customer-data"></a>Urus permintaan untuk memadamkan data pelanggan

Sebagai pentadbir Wawasan Pelanggan, alih keluar data pelanggan Wawasan Pelanggan yang telah dipadamkan dalam sumber data. Sahkan permintaan pemadaman GDPR telah dilakukan dalam sumber data asal.

1. Daftar masuk ke Dynamics 365 Customer Insights.

1. Pergi **Data** > **Sumber data**.

1. Untuk setiap sumber data dalam senarai yang mengandungi data pelanggan yang dipadamkan:
   1. Pilih sumber data kemudian pilih **Segar Semula**.
   1. Semak status sumber data di bawah **Status**. Tanda semak bermaksud segar semula berjaya. Segi tiga amaran bermaksud berlaku suatu kesalahan. Jika segi tiga amaran dipaparkan, hubungi D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Mengendalikan permintaan pemadaman GDPR untuk data pelanggan.":::

1. Selepas sumber data yang berjaya disegar semula, jalankan hiliran juga menyegar semula. Terutama, jika anda tidak mempunyai segar semula penuh Wawasan Pelanggan yang dijadualkan.

   > [!IMPORTANT]
   > Segmen statik tidak termasuk dalam segar semula penuh atau menjalankan segar semula hiliran selepas permintaan padam. Untuk memastikan data pelanggan dikeluarkan daripada segmen statik juga, cipta semula segmen statik dengan data sumber yang disegar semula.

#### <a name="manage-delete-requests-for-user-data"></a>Urus permintaan padam untuk data pengguna

Sebagai pentadbir Wawasan Pelanggan, padamkan data pengguna Wawasan Pelanggan.

1. Daftar masuk ke Dynamics 365 Customer Insights.

1. Pergi ke **> Keselamatan** > **Pentadbir** dan pilih tab **Pengguna**.

1. Pilih kotak semak untuk pengguna yang anda ingin padamkan.

1. Pilih **Alih keluar**.

1. Sahkan pemadaman.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Respons kepada permintaan export subjek data GDPR

Hak kemudahalihan data membenarkan subjek data untuk meminta salinan data peribadi mereka dalam format elektronik (ditakrifkan sebagai "berstruktur, biasa digunakan, mesin boleh dibaca dan format saling boleh kendali") yang boleh dihantar kepada pengawal data yang lain.

### <a name="manage-export-and-view-requests"></a>Urus permintaan eksport dan pandangan

Urus permintaan untuk mengeksport data pelanggan atau pengguna.

#### <a name="export-customer-data-tenant-admin"></a>Eksport data pelanggan (pentadbir penyewa)

Sebagai pentadbir penyewa, eksport data pelanggan.

1. Hantar e-mel kepada D365CI@microsoft.com untuk menentukan alamat e-mel pelanggan di dalam permintaan. Pasukan Customer Insights akan menghantar e-mel kepada alamat e-mel pentadbir penyewa berdaftar, meminta pengesahan untuk mengeksport data.
2. Memberitahu pengesahan untuk mengeksport data untuk pelanggan yang diminta.
3. Menerima data yang dieksport melalui alamat e-mel pentadbir penyewa.

#### <a name="export-user-data-tenant-admin"></a>Eksport data pengguna (pentadbir penyewa)

Sebagai pentadbir penyewa, eksport data pengguna.

1. Hantar e-mel kepada D365CI@microsoft.com untuk menentukan alamat e-mel pengguna di dalam permintaan. Pasukan Wawasan Pelanggan menghantar e-mel ke alamat e-mel pentadbir penyewa berdaftar, meminta pengesahan untuk mengeksport data.
1. Memberitahu pengesahan untuk mengeksport data untuk pengguna yang diminta.
1. Menerima data yang dieksport melalui alamat e-mel pentadbir penyewa.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Pengendalian pemadaman data dalam Dynamics 365 Customer Insights

Data dipadamkan (sekatan data dan petikan data) jika partition data dan syot kilat data tidak aktif selama lebih daripada 30 hari, bermakna ia telah digantikan dengan partition data baru dan petikan melalui segar semula sumber data.

Tidak semua data dan gambar dipadamkan. Pembahagian data terkini dan petikan data aktif kerana ia digunakan dalam Wawasan Pelanggan. Untuk data terkini, tidak kira sama ada sumber data tidak disegar semula dalam tempoh 30 hari yang lalu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
