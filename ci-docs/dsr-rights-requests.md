---
title: Permintaan Hak Subjek Data (DSR) di bawah GDPR | Microsoft Docs
description: Respons kepada Permintaan Subjek Data untuk keupayaan Insights khalayak Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350280"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Permintaan Hak Subjek Data (DSR) di bawah GDPR

Peraturan Perlindungan Data Umum (GDPR) Kesatuan Eropah telah berkuat kuasa sejak 25 Mei 2018. Peraturan ini memberikan hak penting kepada individu berkenaan data mereka. GDPR adalah tentang melindungi dan mendayakan hak privasi individu. Anda boleh membaca lebih lanjut tentang komitmen Microsoft terhadap keselamatan dan pematuhan di [Pusat Amanah Microsoft](https://www.microsoft.com/trust-center).

Kami komited untuk membantu para pelanggan kami memenuhi keperluan GDPR mereka. Ini termasuk hak untuk memadamkan dan mengeksport data yang mengandungi maklumat peribadi seperti ID pengguna, nombor telefon dan alamat e-mel. Pentadbir boleh melaksanakan permintaan pengguna untuk memadamkan atau mengeksport data peribadi.

## <a name="audience-insights"></a>Cerapan khalayak

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Respons kepada permintaan padam subjek data GDPR untuk keupayaan Insights khalayak Dynamics 365 Customer Insights

"Hak untuk pemadaman" dengan memadam data peribadi daripada data pelanggan organisasi adalah perlindungan utama dalam Peraturan Perlindungan Data Umum (GDPR). Mengeluarkan data peribadi termasuk mengeluarkan semua data peribadi dan log janaan sistem kecuali maklumat log audit.

#### <a name="manage-data-subject-delete-requests"></a>Urus permintaan padam subjek data

Insights khalayak menawarkan pengalaman dalam produk untuk memadamkan data peribadi untuk pelanggan atau pengguna khusus:

- **Urus permintaan padam untuk data pelanggan**: Data pelanggan dalam Customer Insights telah ditelan daripada sumber data asal luaran kepada Customer Insights. Semua permintaan penghapusan GDPR mesti dilaksanakan di dalam sumber data asal.
- **Urus permintaan padam untuk data pengguna Customer Insights**: Data untuk pengguna dicipta oleh Customer Insights. Semua permintaan penghapusan GDPR mesti dilakukan di dalam Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Urus permintaan untuk memadamkan data pelanggan

Pentadbir Customer Insights boleh mengikut langkah ini untuk mengalih keluar data pelanggan yang telah dipadamkan dalam sumber data:

1. Daftar masuk ke Dynamics 365 Customer Insights.
2. Dalam Insights khalayak, pergi ke **Data** > **Sumber data**
3. Untuk setiap sumber data dalam senarai yang mengandungi data pelanggan yang dipadamkan:
   1. Pilih (...) dan kemudian pilih **Muat Semula**.
   2. Semak status sumber data di bawah **Status**. Tanda semak bermaksud segar semula berjaya. Segi tiga amaran bermaksud berlaku suatu kesalahan. Jika segi tiga amaran dipaparkan, hubungi D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Mengendalikan permintaan pemadaman GDPR untuk data pelanggan.](audience-insights/media/gdpr-data-sources.png "Urus permintaan penghapusan GDPR untuk data pelanggan")

##### <a name="manage-delete-requests-for-user-data"></a>Urus permintaan padam untuk data pengguna

Pentadbir Customer Insights boleh mengikut langkah ini untuk menghapuskan data pengguna Customer Insights:

1. Daftar masuk ke Dynamics 365 Customer Insights.
2. Dalam Insights khalayak, pergi ke **Pentadbir** > **Keizinan**.
3. Tandakan kotak semak untuk pengguna yang anda mahu hapuskan.
4. Pilih **Alih keluar**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Respons kepada permintaan export subjek data GDPR

Sebagai sebahagian daripada komitmen kami untuk bekerjasama dengan anda dalam perjalanan anda kepada Peraturan Perlindungan Data Umum (GDPR), kami telah membangunkan dokumentasi untuk membantu persediaan anda. Dokumentasi ini memerihalkan langkah yang boleh anda lakukan hari ini untuk menyokong pematuhan GDPR apabila menggunakan Insights khalayak.

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

Untuk mengalih keluar data persetujuan tentang pengguna tertentu, alih keluarnya dalam sumber data yang ditelan kepada keupayaan pengurusan persetujuan. Selepas menyegarkan semula sumber data, data yang dikeluarkan akan dipadamkan dalam Pusat Persetujuan juga. Aplikasi yang menggunakan entiti persetujuan juga akan memadamkan data yang telah dialih keluar pada sumber selepas [segar semula](audience-insights/system.md#refresh-processes). Kami mengesyorkan anda menyegar semula sumber data dengan cepat selepas bertindak balas kepada permintaan subjek data untuk mengalih keluar data pengguna daripada semua proses dan aplikasi lain.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]