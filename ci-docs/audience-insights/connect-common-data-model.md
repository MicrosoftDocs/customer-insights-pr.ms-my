---
title: Sambung data Common Data Model ke akaun Azure Data Lake
description: Bekerja dengan data Common Data Model menggunakan Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 93871f8029053d4ed4a116d3af3550b7684ee11ea8633e937138245e193a44e6
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033137"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Sambungkan ke folder Common Data Model menggunakan akaun Azure Data Lake

Artikel ini memberikan maklumat tentang cara untuk data daripada folder Common Data Model menggunakan akaun Azure Data Lake Storage Gen2 anda.

## <a name="important-considerations"></a>Pertimbangan penting

- Data dalam data Azure Data Lake anda perlu mengikut piawaian Common Data Model. Format lain tidak disokong pada masa ini.

- Pengingesan data menyokong data akaun storan Azure Data Lake *Gen2* secara eksklusif. Anda tidak boleh menggunakan akaun storan Azure Data Lake Gen1 untuk menginges data.

- Untuk mengesahkan dengan prinsip perkhidmatan Azure, pastikan ia dikonfigurasikan dalam penyewa anda. Untuk maklumat lanjut, lihat [Sambungkan cerapan khalayak ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure](connect-service-principal.md).

- Azure Data Lake yang ingin anda sambungkan dan inges data dari perlu berada di rantau Azure yang sama seperti persekitaran Dynamics 365 Customer Insights. Sambungan ke folder Common Data Model dari data lake dalam rantau Azure berbeza tidak disokong. Untuk mengetahui rantau Azure persekitaran, pergi ke **Pentadbir** > **Sistem** > **Perihal** dalam cerapan khalayak.

- Data disimpan dalam perkhidmatan dalam talian, mungkin disimpan di lokasi lain daripada tempat data diproses atau disimpan dalam Dynamics 365 Customer Insights.Dengan mengimport atau menyambung kepada data yang disimpan dalam perkhidmatan dalam talian, anda bersetuju bahawa data boleh dipindahkan ke dan disimpan dengan Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat Amanah Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Sambungkan ke folder Common Data Model

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. Pilih **Sambung ke folder Common Data Model**, masukkan **Nama** untuk sumber data dan pilih **Seterusnya**. Namakan garis panduan: 
   - Bermula dengan huruf.
   - Gunakan huruf dan nombor sahaja. Aksara khas dan ruang idak dibenarkan.
   - Gunakan antara 3 dan 64 aksara.

1. Anda boleh memilih antara pilihan berasaskan sumber dan pilihan berasaskan langganan untuk pengesahan. Untuk maklumat lanjut, lihat [Sambungkan cerapan khalayak ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure](connect-service-principal.md). Masukkan maklumat **Bekas** dan pilih **Seterusnya**.
   > [!div class="mx-imgBorder"]
   > ![Kotak dialog untuk memasukkan butiran sambungan baharu untuk Data Lake Azure.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Anda memerlukan salah satu peranan yang berikut sama ada kepada bekas atau akaun storan yang dirujuk di atas untuk bersambung kepada dan mencipta sumber data:
   >  - Pembaca Data Blob Storan
   >  - Pemilik Data Blob Storan
   >  - Penyumbang Blob Data Storan

1. Dalam dialog **Pilih folder Common Data Model**, pilih fail model.json atau manifest.json untuk mengimport data daripada, dan pilih **Seterusnya**.
   > [!NOTE]
   > Sebarang fail model.json atau manifest.json yang berkaitan dengan sumber data lain dalam persekitaran tidak akan ditunjukkan dalam senarai.

1. Anda akan mendapat senarai entiti yang tersedia dalam fail model.json atau manifest.json yang dipilih. Anda boleh menyemak semula dan memilih daripada senarai entiti yang tersedia dan pilih **Simpan**. Semua entiti yang dipilih akan dinges daripada sumber data baharu.
   > [!div class="mx-imgBorder"]
   > ![Kotak dialog yang menunjukkan senarai entiti daripada fail model.json.](media/review-entities.png)

8. Menunjukkan entiti data yang mahu anda dayakan pemprofilan data dan pilih **Simpan**. Pemprofilan data membolehkan analitis dan keupayaan lain. Anda boleh memilih keseluruhan entiti yang memilih semua atribut daripada entiti atau memilih sifat tertentu pilihan anda. Secara lalai, tiada entiti didayakan untuk pemprofilan data.
   > [!div class="mx-imgBorder"]
   > ![Kotak dialog menunjukkan pemprofilan data.](media/dataprofiling-entities.png)

9. Selepas menyimpan pilihan anda, halaman **Sumber data** dibuka. Kini anda patut melihat sambungan folder Common Data Model sebagai sumber data.

> [!NOTE]
> Fail model.json atau manifest.json hanya boleh mengaitkan dengan satu sumber data dalam persekitaran yang sama. Walau bagaimanapun, fail model.json atau manifest.json boleh digunakan untuk sumber data dalam berbilang persekitaran.

## <a name="edit-a-common-data-model-folder-data-source"></a>Edit sumber data folder Common Data Model

Anda boleh mengemas kini kekunci akses untuk akaun storan yang mengandungi folder Common Data Model. Anda juga boleh mengubah fail model.json atau manifest.json. Untuk menyambung kepada bekas berbeza daripada akaun storan anda, atau mengubah nama akaun, [mencipta sambungan sumber data baharu](#connect-to-a-common-data-model-folder).

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

2. Bersebelahan dengan sumber data yang anda mahu kemas kini, pilih elipsis.

3. Pilih pilihan **Edit** daripada senarai.

4. Secara alternatif, kemas kini **Kunci akses** dan pilih **Seterusnya**.

   ![Dialog untuk mengedit dan mengemas kini kunci capaian untuk sumber data sedia ada.](media/edit-access-key.png)

5. Secara alternatif, anda boleh mengemas kini dari sambungan utama akaun kepada sambungan berasaskan sumber atau langganan. Untuk maklumat lanjut, lihat [Sambungkan cerapan khalayak ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure](connect-service-principal.md). Anda tidak boleh mengubah maklumat **Bekas** semasa mengemas kini sambungan.
   > [!div class="mx-imgBorder"]

   > ![Kotak dialog untuk memasukkan butiran sambungan untuk Data Lake Azure kepada akaun storan sedia ada.](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Anda memerlukan salah satu peranan yang berikut sama ada kepada bekas atau akaun storan yang dirujuk di atas untuk bersambung kepada dan mencipta sumber data:
   >  - Pembaca Data Blob Storan
   >  - Pemilik Data Blob Storan
   >  - Penyumbang Blob Data Storan


6. Secara alternatif, pilih fail model.json atau manifest.json lainl dengan set entiti yang berbeza daripada bekas.

7. Secara alternatif, anda boleh memilih entiti tambahan untuk diinges. Anda juga boleh mengalih keluar sebarang entiti yang sudah dipilih jika tiada kebergantungan.

   > [!IMPORTANT]
   > Jika terdapat pergantungan pada fail model.json atau manifest.json sedia ada dan set entiti, anda akan melihat mesej ralat dan tidak boleh memilih fail model.json atau manifest.json yang berbeza. Keluarkan kebergantungan sebelum mengubah fail model.json atau manifest.json atau cipta sumber data baharu dengan fail model.json atau manifest.json yang anda mahu gunakan untuk mengelakkan daripada mengeluarkan kebergantungan.

8. Secara alternatif, anda boleh memilih atribut atau entiti tambahan untuk mendayakan pemprofilan data atau menyahdayakan yang sudah dipilih.   


[!INCLUDE[footer-include](../includes/footer-banner.md)]