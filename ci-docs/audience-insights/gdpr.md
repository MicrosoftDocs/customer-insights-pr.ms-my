---
title: Permintaan Hak Subjek Data (DSR) di bawah GDPR | Microsoft Docs
description: Respons kepada Permintaan Subjek Data untuk keupayaan Insights khalayak Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268697"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Permintaan Hak Subjek Data (DSR) di bawah GDPR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Respons kepada permintaan padam subjek data GDPR untuk keupayaan Insights khalayak Dynamics 365 Customer Insights

"Hak untuk pemadaman" dengan memadam data peribadi daripada data pelanggan organisasi adalah perlindungan utama dalam Peraturan Perlindungan Data Umum (GDPR). Mengeluarkan data peribadi termasuk mengeluarkan semua data peribadi dan log janaan sistem kecuali maklumat log audit.

### <a name="manage-data-subject-delete-requests"></a>Urus permintaan padam subjek data

Insights khalayak menawarkan pengalaman dalam produk untuk memadamkan data peribadi untuk pelanggan atau pengguna khusus:

- **Urus permintaan padam untuk data pelanggan**: Data pelanggan dalam Customer Insights telah ditelan daripada sumber data asal luaran kepada Customer Insights. Semua permintaan penghapusan GDPR mesti dilaksanakan di dalam sumber data asal.
- **Urus permintaan padam untuk data pengguna Customer Insights**: Data untuk pengguna dicipta oleh Customer Insights. Semua permintaan penghapusan GDPR mesti dilakukan di dalam Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Urus permintaan penghapusan untuk data pelanggan

Pentadbir Customer Insights boleh mengikut langkah ini untuk mengalih keluar data pelanggan yang telah dipadamkan dalam sumber data:

1. Daftar masuk ke Dynamics 365 Customer Insights.
2. Dalam Insights khalayak, pergi ke **Data** > **Sumber data**
3. Untuk setiap sumber data dalam senarai yang mengandungi data pelanggan yang dipadamkan:
   1. Pilih (...) dan kemudian pilih **Muat Semula**.
   2. Semak status sumber data di bawah **Status**. Tanda semak bermaksud segar semula berjaya. Segi tiga amaran bermaksud berlaku suatu kesalahan. Jika segi tiga amaran dipaparkan, hubungi D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Urus permintaan penghapusan GDPR untuk data pelanggan](media/gdpr-data-sources.png "Urus permintaan penghapusan GDPR untuk data pelanggan")

#### <a name="manage-delete-requests-for-user-data"></a>Urus permintaan padam untuk data pengguna

Pentadbir Customer Insights boleh mengikut langkah ini untuk menghapuskan data pengguna Customer Insights:

1. Daftar masuk ke Dynamics 365 Customer Insights.
2. Dalam Insights khalayak, pergi ke **Pentadbir** > **Keizinan**.
3. Tandakan kotak semak untuk pengguna yang anda mahu hapuskan.
4. Pilih **Alih keluar**.

> [!div class="mx-imgBorder"]
> ![Pengendalian permintaan padam GDPR untuk data pengguna](media/gdpr-permissions.png "Pengendalian permintaan padam GDPR untuk data pengguna")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Respons kepada permintaan export subjek data GDPR

Sebagai sebahagian daripada komitmen kami untuk bekerjasama dengan anda dalam perjalanan anda kepada Peraturan Perlindungan Data Umum (GDPR), kami telah membangunkan dokumentasi untuk membantu persediaan anda. Dokumentasi ini memerihalkan langkah yang boleh anda lakukan hari ini untuk menyokong pematuhan GDPR apabila menggunakan Insights khalayak.

### <a name="manage-export-and-view-requests"></a>Urus permintaan eksport dan pandangan

Hak kemudahalihan data membenarkan subjek data untuk meminta salinan data peribadi mereka dalam format elektronik (ditakrifkan sebagai "berstruktur, biasa digunakan, mesin boleh dibaca dan format saling boleh kendali") yang boleh dihantar kepada pengawal data yang lain.

#### <a name="export-customer-data-tenant-admin"></a>Eksport data pelanggan (pentadbir penyewa)

Pentadbir penyewa boleh mengikuti langkah-langkah ini untuk mengeksport data:

1. Hantar e-mel kepada D365CI@microsoft.com untuk menentukan alamat e-mel pelanggan di dalam permintaan. Pasukan Customer Insights akan menghantar e-mel kepada alamat e-mel pentadbir penyewa berdaftar, meminta pengesahan untuk mengeksport data.
2. Memberitahu pengesahan untuk mengeksport data untuk pelanggan yang diminta.
3. Menerima data yang dieksport melalui alamat e-mel pentadbir penyewa.

#### <a name="export-user-data-tenant-admin"></a>Eksport data pengguna (pentadbir penyewa)

1. Hantar e-mel kepada D365CI@microsoft.com untuk menentukan alamat e-mel pengguna di dalam permintaan. Pasukan Customer Insights akan menghantar e-mel kepada alamat e-mel pentadbir penyewa berdaftar, meminta pengesahan untuk mengeksport data.
2. Memberitahu pengesahan untuk mengeksport data untuk pengguna yang diminta.
3. Menerima data yang dieksport melalui alamat e-mel pentadbir penyewa.


[!INCLUDE[footer-include](../includes/footer-banner.md)]