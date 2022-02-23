---
title: Permintaan Hak Subjek Data (DSR) di bawah GDPR | Microsoft Docs
description: Memberi respons kepada Permintaan Subjek Data untuk Dynamics 365 Customer Insights keupayaan wawasan khalayak.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732691"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Permintaan Hak Subjek Data (DSR) di bawah GDPR

Peraturan Perlindungan Data Umum (GDPR) Kesatuan Eropah telah berkuat kuasa sejak 25 Mei 2018. Peraturan ini memberikan hak penting kepada individu berkenaan data mereka. GDPR adalah tentang melindungi dan mendayakan hak privasi individu. Anda boleh membaca lebih lanjut tentang komitmen Microsoft terhadap keselamatan dan pematuhan di [Pusat Amanah Microsoft](https://www.microsoft.com/trust-center).

Kami komited untuk membantu para pelanggan kami memenuhi keperluan GDPR mereka. Ini termasuk hak untuk memadamkan dan mengeksport data yang mengandungi maklumat peribadi seperti ID pengguna, nombor telefon dan alamat e-mel. Pentadbir boleh melaksanakan permintaan pengguna untuk memadamkan atau mengeksport data peribadi.

## <a name="audience-insights"></a>Cerapan khalayak

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Memberi respons kepada subjek data GDPR memadamkan permintaan untuk Dynamics 365 Customer Insights keupayaan pandangan khalayak

"Hak untuk pemadaman" dengan memadam data peribadi daripada data pelanggan organisasi adalah perlindungan utama dalam Peraturan Perlindungan Data Umum (GDPR). Mengeluarkan data peribadi termasuk mengeluarkan semua data peribadi dan log janaan sistem kecuali maklumat log audit.

#### <a name="manage-data-subject-delete-requests"></a>Urus permintaan padam subjek data

Insights khalayak menawarkan pengalaman dalam produk untuk memadamkan data peribadi untuk pelanggan atau pengguna khusus:

- **Urus permintaan padam untuk data pelanggan**: Data pelanggan dalam Customer Insights telah ditelan daripada sumber data asal luaran kepada Customer Insights. Semua permintaan penghapusan GDPR mesti dilaksanakan di dalam sumber data asal.
- **Urus permintaan padam untuk data pengguna Customer Insights**: Data untuk pengguna dicipta oleh Customer Insights. Semua permintaan penghapusan GDPR mesti dilakukan di dalam Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Urus permintaan untuk memadamkan data pelanggan

Pentadbir Customer Insights boleh mengikut langkah ini untuk mengalih keluar data pelanggan yang telah dipadamkan dalam sumber data:

1. Log masuk ke Dynamics 365 Customer Insights.
2. Dalam Insights khalayak, pergi ke **Data** > **Sumber data**
3. Untuk setiap sumber data dalam senarai yang mengandungi data pelanggan yang dipadamkan:
   1. Pilih (...) dan kemudian pilih **Muat Semula**.
   2. Semak status sumber data di bawah **Status**. Tanda semak bermaksud segar semula berjaya. Segi tiga amaran bermaksud berlaku suatu kesalahan. Jika segi tiga amaran dipaparkan, hubungi D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Mengendalikan permintaan pemadaman GDPR untuk data pelanggan.](audience-insights/media/gdpr-data-sources.png "Urus permintaan penghapusan GDPR untuk data pelanggan")

##### <a name="manage-delete-requests-for-user-data"></a>Urus permintaan padam untuk data pengguna

Pentadbir Customer Insights boleh mengikut langkah ini untuk menghapuskan data pengguna Customer Insights:

1. Log masuk ke Dynamics 365 Customer Insights.
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

Untuk mengalih keluar data persetujuan tentang pengguna tertentu, alihnya keluar dalam sumber data yang diingest kepada keupayaan pengurusan persetujuan. Selepas menyegar semula sumber data, data yang dialih keluar akan dipadamkan dalam Pusat Persetujuan juga. Aplikasi yang menggunakan entiti persetujuan juga akan memadamkan data yang telah dialih keluar pada sumber selepas [segar semula](audience-insights/system.md#refresh-processes). Kami mengesyorkan untuk menyegar semula sumber data dengan cepat selepas memberi respons kepada permintaan subjek data untuk mengalih keluar data pengguna daripada semua proses dan aplikasi lain.


## <a name="engagement-insights-preview"></a>Cerapan penglibatan (pratonton)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Memadamkan dan mengeksport data peristiwa yang mengandungi maklumat boleh dikenal pasti pengguna akhir

Bahagian berikut menghuraikan cara memadamkan dan mengeksport data peristiwa yang mungkin mengandungi data peribadi.

Untuk memadamkan atau mengeksport data:

1. Tag sifat peristiwa yang mengandungi data dengan maklumat peribadi.
2. Padamkan atau eksport data yang berkaitan dengan nilai tertentu (contohnya: ID pengguna yang ditentukan).

#### <a name="tag-and-update-event-properties"></a>Tag dan kemas kini sifat peristiwa

Data peribadi ditag pada tahap sifat peristiwa. Pertama, tag sifat yang dipertimbangkan untuk pemadaman atau eksport.

Untuk mengetag sifat peristiwa sebagai mengandungi maklumat peribadi, ikuti langkah berikut:

1. Buka ruang kerja yang mengandungi peristiwa.

1. Pergi ke **Data** > **Peristiwa** untuk melihat senarai peristiwa dalam ruang kerja yang dipilih.
  
1. Pilih peristiwa yang anda mahu tag.

1. Pilih **Edit sifat** untuk membuka anak tetingkap yang menyenaraikan semua sifat peristiwa yang dipilih.
     
1. Pilih **...** dan kemudian pilih **Edit** untuk mencapai dialog **Kemas kini sifat**.

   ![Edit peristiwa.](engagement-insights/media/edit-event.png "Edit peristiwa")

1. Dalam tetingkap **Kemas Kini Sifat**, pilih **...** di sudut kanan atas dan kemudian pilih kotak **Mengandungi EUII**. Pilih **Kemas Kini** untuk menyimpan perubahan anda.

   ![Simpan perubahan anda.](engagement-insights/media/update-property.png "Simpan perubahan anda")

   > [!NOTE]
   > Setiap kali skema peristiwa berubah atau anda mencipta peristiwa baharu, anda disyorkan untuk menilai sifat peristiwa berkaitan dan tag atau menyahtag peristiwa tersebut sebagai mengandungi data peribadi, jika perlu.

#### <a name="delete-or-export-tagged-event-data"></a>Padam atau eksport data peristiwa yang ditag

Jika semua sifat peristiwa telah ditag sewajarnya seperti yang dihuraikan dalam langkah sebelumnya, pentadbir persekitaran boleh mengeluarkan permintaan pemadaman terhadap data peristiwa yang ditag.

Untuk menguruskan permintaan pemadaman atau eksport EUII

1. Pergi ke **Pentadbir** > **Persekitaran** > **Tetapan**.

1. Dalam bahagian **Urus maklumat boleh dikenal pasti pengguna akhir (EUII)**, pilih **Urus EUII**.

##### <a name="deletion"></a>Pemadaman

Untuk pemadaman, anda boleh memasukkan senarai ID pengguna yang dipisahkan koma dalam bahagian **Padamkan maklumat boleh dikenal pasti pengguna akhir (EUII)**. ID ini kemudian akan dibandingkan dengan semua sifat peristiwa yang ditag bagi semua projek dalam persekitaran semasa melalui pemadanan rentetan yang tepat. 

Jika nilai sifat sepadan dengan salah satu ID yang diberikan, peristiwa berkaitan akan dipadamkan secara kekal. Disebabkan oleh ketakterbalikan tindakan ini, anda mesti mengesahkan pemadaman selepas memilih **Padam**.

##### <a name="export"></a>Export

Proses eksport serupa dengan proses pemadaman apabila berkaitan dengan penentuan nilai sifat peristiwa dalam bahagian **Eksport maklumat boleh dikenal pasti pengguna akhir (EUII)**. Selain itu, anda perlu menyediakan **URL Storan Blob Azure** untuk menentukan destinasi eksport. URL Blob Azure mesti termasuk [Tandatangan Akses Dikongsi (SAS)](/azure/storage/common/storage-sas-overview).

Selepas memilih **Eksport**, semua peristiwa pasukan semasa yang mengandungi sifat ditag sepadan akan dieksport dalam format CSV ke destinasi eksport.

### <a name="good-practices"></a>Amalan yang baik

* Cuba elakkan daripada menghantar sebarang peristiwa yang mengandungi data peribadi.
* Jika anda perlu menghantar peristiwa yang mengandungi data EUII, hadkan bilangan peristiwa dan sifat peristiwa yang mengandungi data EUII. Sebaik-baiknya, hadkan diri anda kepada satu peristiwa tersebut.
* Pastikan bahawa sedikit orang yang mungkin mempunyai akses kepada data peribadi yang dihantar.
* Untuk peristiwa yang mengandungi data peribadi, pastikan bahawa anda menetapkan satu sifat untuk mengeluarkan pengecam unik yang boleh dipautkan dengan mudah kepada pengguna tertentu (contohnya, ID pengguna). Ini menjadikannya lebih mudah untuk mengasingkan data dan untuk mengeksport atau memadamkan data yang betul.
* Hanya tag satu sifat setiap peristiwa sebagai mengandungi data peribadi. Sebaik-baiknya, satu yang hanya mengandungi pengecam unik.
* Jangan tag sifat yang mengandungi nilai berjela-jela (contohnya, keseluruhan isi permintaan). Keupayaan cerapan penglibatan menggunakan pemadanan rentetan yang tepat apabila memutuskan peristiwa yang hendak dipadamkan atau dieksport.

[!INCLUDE[footer-include](includes/footer-banner.md)]