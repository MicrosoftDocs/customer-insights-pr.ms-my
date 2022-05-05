---
title: Permintaan Hak Subjek Data (DSR) di bawah GDPR | Microsoft Docs
description: Respons kepada Permintaan Subjek Data untuk Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 5b39452d7a4612242739e8000e57217954c71289
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641527"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Permintaan Hak Subjek Data (DSR) di bawah GDPR

Peraturan Perlindungan Data Umum (GDPR) Kesatuan Eropah telah berkuat kuasa sejak 25 Mei 2018. Peraturan ini memberikan hak penting kepada individu berkenaan data mereka. GDPR adalah tentang melindungi dan mendayakan hak privasi individu. Anda boleh membaca lebih lanjut tentang komitmen Microsoft terhadap keselamatan dan pematuhan di [Pusat Amanah Microsoft](https://www.microsoft.com/trust-center).

Kami komited untuk membantu para pelanggan kami memenuhi keperluan GDPR mereka. Ini termasuk hak untuk memadamkan dan mengeksport data yang mengandungi maklumat peribadi seperti ID pengguna, nombor telefon dan alamat e-mel. Pentadbir boleh melaksanakan permintaan pengguna untuk memadamkan atau mengeksport data peribadi.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Respons kepada permintaan pemadaman subjek data GDPR untuk Dynamics 365 Customer Insights

"Hak untuk pemadaman" dengan memadam data peribadi daripada data pelanggan organisasi adalah perlindungan utama dalam Peraturan Perlindungan Data Umum (GDPR). Mengeluarkan data peribadi termasuk mengeluarkan semua data peribadi dan log janaan sistem kecuali maklumat log audit.

#### <a name="manage-data-subject-delete-requests"></a>Urus permintaan padam subjek data

Wawasan Pelanggan menawarkan pengalaman dalam produk berikut untuk memadamkan data peribadi untuk pelanggan atau pengguna tertentu:

- **Urus permintaan padam untuk data pelanggan**: Data pelanggan dalam Customer Insights telah ditelan daripada sumber data asal luaran kepada Customer Insights. Semua permintaan penghapusan GDPR mesti dilaksanakan di dalam sumber data asal.
- **Urus permintaan padam untuk data pengguna Customer Insights**: Data untuk pengguna dicipta oleh Customer Insights. Semua permintaan penghapusan GDPR mesti dilakukan di dalam Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Urus permintaan untuk memadamkan data pelanggan

Pentadbir Customer Insights boleh mengikut langkah ini untuk mengalih keluar data pelanggan yang telah dipadamkan dalam sumber data:

1. Daftar masuk ke Dynamics 365 Customer Insights.
2. Pergi ke **sumber DataData** > **·**
3. Untuk setiap sumber data dalam senarai yang mengandungi data pelanggan yang dipadamkan:
   1. Pilih (...) dan kemudian pilih **Muat Semula**.
   2. Semak status sumber data di bawah **Status**. Tanda semak bermaksud segar semula berjaya. Segi tiga amaran bermaksud berlaku suatu kesalahan. Jika segi tiga amaran dipaparkan, hubungi D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Mengendalikan permintaan pemadaman GDPR untuk data pelanggan.](media/gdpr-data-sources.png "Urus permintaan penghapusan GDPR untuk data pelanggan")

##### <a name="manage-delete-requests-for-user-data"></a>Urus permintaan padam untuk data pengguna

Pentadbir Customer Insights boleh mengikut langkah ini untuk menghapuskan data pengguna Customer Insights:

1. Daftar masuk ke Dynamics 365 Customer Insights.
2. Pergi ke **AdminPermissions** > **·**.
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

## <a name="consent-management-preview"></a>Pengurusan persetujuan (pratonton)

Keupayaan pengurusan persetujuan tidak mengumpul data pengguna secara langsung. Ia hanya mengimport dan memproses data persetujuan yang disediakan oleh pengguna dalam aplikasi lain.

Untuk mengalih keluar data persetujuan tentang pengguna tertentu, alih keluarnya dalam sumber data yang ditelan kepada keupayaan pengurusan persetujuan. Selepas menyegar semula sumber data, data yang dikeluarkan akan dipadamkan dalam Pusat Persetujuan juga. Aplikasi yang menggunakan entiti persetujuan juga akan memadamkan data yang telah dialih keluar pada sumber selepas [segar semula](system.md#refresh-processes). Kami mengesyorkan menyegar semula sumber data dengan cepat selepas bertindak balas terhadap permintaan subjek data untuk mengalih keluar data pengguna daripada semua proses dan aplikasi lain.

[!INCLUDE [footer-include](includes/footer-banner.md)]