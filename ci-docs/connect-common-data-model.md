---
title: Sambung data Common Data Model ke akaun Azure Data Lake
description: Bekerja dengan data Common Data Model menggunakan Azure Data Lake Storage.
ms.date: 05/24/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2e8564950a3269180a85f80fb736d2dcbd1b03b6
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833375"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Sambungkan ke folder Common Data Model menggunakan akaun Azure Data Lake

Artikel ini menyediakan maklumat tentang cara menelan data daripada Dynamics 365 Customer Insights folder Model Data Biasa menggunakan akaun Gen2 anda Azure Data Lake Storage.

## <a name="important-considerations"></a>Pertimbangan penting

- Data dalam data Azure Data Lake anda perlu mengikut piawaian Common Data Model. Format lain tidak disokong pada masa ini.

- Pengingesan data menyokong data akaun storan Azure Data Lake *Gen2* secara eksklusif. Anda tidak boleh menggunakan akaun storan Azure Data Lake Gen1 untuk menginges data.

- Akaun storan Azure Data Lake mesti mempunyai [ruang nama hierarki yang didayakan](/azure/storage/blobs/data-lake-storage-namespace).

- Untuk mengesahkan dengan prinsip perkhidmatan Azure, pastikan ia dikonfigurasikan dalam penyewa anda. Untuk maklumat lanjut, lihat [Menyambung ke Azure Data Lake Storage akaun Gen2 dengan prinsipal perkhidmatan Azure](connect-service-principal.md).

- Azure Data Lake yang ingin anda sambungkan dan inges data dari perlu berada di rantau Azure yang sama seperti persekitaran Dynamics 365 Customer Insights. Sambungan ke folder Common Data Model dari data lake dalam rantau Azure berbeza tidak disokong. Untuk mengetahui rantau Azure persekitaran, pergi ke **Sistem** > **Pentadbir** > **Perihal** dalam Wawasan Pelanggan.

- Data yang disimpan dalam perkhidmatan dalam talian mungkin disimpan di lokasi yang berbeza daripada di mana data diproses atau disimpan dalam Dynamics 365 Customer Insights.Dengan mengimport atau menyambung ke data yang disimpan dalam perkhidmatan dalam talian, anda bersetuju bahawa data boleh dipindahkan dan disimpan dengan Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat Amanah Microsoft](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Sambungkan ke folder Common Data Model

1. Pergi **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. Pilih **storan** tasik data Azure, masukkan **Nama** untuk sumber data, kemudian pilih **Seterusnya**.

   - Jika digesa, pilih salah satu set data sampel yang berkaitan dengan industri anda, kemudian pilih **Seterusnya**.

1. Anda boleh memilih antara pilihan berasaskan sumber dan pilihan berasaskan langganan untuk pengesahan. Untuk maklumat lanjut, lihat [Menyambung ke Azure Data Lake Storage akaun Gen2 dengan prinsipal perkhidmatan Azure](connect-service-principal.md). Masukkan **alamat** Pelayan, pilih **log masuk**, kemudian pilih **Seterusnya**.
   > [!div class="mx-imgBorder"]
   > ![Kotak dialog untuk memasukkan butiran sambungan baharu untuk Data Lake Azure.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Anda memerlukan salah satu peranan berikut sama ada ke bekas pada akaun storan dan membuat sumber data:
   >
   >  - Storage Blob Data Reader adalah mencukupi untuk membaca daripada akaun storan dan menelan data kepada Wawasan Pelanggan. 
   >  - Penyumbang Data Blob Storan atau Pemilik diperlukan jika anda ingin mengedit fail manifes secara langsung dalam Wawasan Pelanggan.

1. Dalam dialog **Pilih folder Common Data Model**, pilih fail model.json atau manifest.json untuk mengimport data daripada, dan pilih **Seterusnya**.
   > [!NOTE]
   > Sebarang fail model.json atau manifest.json yang berkaitan dengan sumber data lain dalam persekitaran tidak akan ditunjukkan dalam senarai.

1. Anda akan melihat senarai entiti yang tersedia dalam fail model.json atau manifest.json yang dipilih. Semak semula dan pilih daripada senarai entiti yang tersedia, kemudian pilih **Simpan**. Semua entiti yang dipilih akan dinges daripada sumber data baharu.
   > [!div class="mx-imgBorder"]
   > ![Kotak dialog yang menunjukkan senarai entiti daripada fail model.json.](media/review-entities.png)

1. Tunjukkan entiti data yang anda mahu dayakan pemprofilan data, kemudian pilih **Simpan**. Pemprofilan data membolehkan analitis dan keupayaan lain. Anda boleh memilih keseluruhan entiti yang memilih semua atribut daripada entiti atau memilih sifat tertentu pilihan anda. Secara lalai, tiada entiti didayakan untuk pemprofilan data.
   > [!div class="mx-imgBorder"]
   > ![Kotak dialog menunjukkan pemprofilan data.](media/dataprofiling-entities.png)

1. Selepas menyimpan pilihan anda, halaman **Sumber data** dibuka. Kini anda patut melihat sambungan folder Common Data Model sebagai sumber data.

> [!NOTE]
> Fail model.json atau manifest.json hanya boleh mengaitkan dengan satu sumber data dalam persekitaran yang sama. Walau bagaimanapun, fail model.json atau manifest.json boleh digunakan untuk sumber data dalam berbilang persekitaran.

## <a name="edit-a-common-data-model-folder-data-source"></a>Edit sumber data folder Common Data Model

Anda boleh mengemas kini kekunci akses untuk akaun storan yang mengandungi folder Common Data Model. Anda juga boleh mengubah fail model.json atau manifest.json. Untuk menyambung kepada bekas berbeza daripada akaun storan anda, atau mengubah nama akaun, [mencipta sambungan sumber data baharu](#connect-to-a-common-data-model-folder).

1. Pergi **Data** > **Sumber data**.

2. Di sebelah sumber data yang anda ingin kemas kini, pilih elipsis menegak (&vellip;).

3. Pilih pilihan **Edit** daripada senarai.

4. Secara alternatif, kemas kini **Kunci akses** dan pilih **Seterusnya**.

   ![Dialog untuk mengedit dan mengemas kini kunci capaian untuk sumber data sedia ada.](media/edit-access-key.png)

5. Secara alternatif, anda boleh mengemas kini dari sambungan utama akaun kepada sambungan berasaskan sumber atau langganan. Untuk maklumat lanjut, lihat [Menyambung ke Azure Data Lake Storage akaun Gen2 dengan prinsipal perkhidmatan Azure](connect-service-principal.md). Anda tidak boleh mengubah maklumat **Bekas** semasa mengemas kini sambungan.
   > [!div class="mx-imgBorder"]

   > ![Kotak dialog untuk memasukkan butiran sambungan untuk Data Lake Azure kepada akaun storan sedia ada.](media/enter-existing-storage-details.png)

6. Secara alternatif, pilih fail model.json atau manifest.json lainl dengan set entiti yang berbeza daripada bekas.

7. Secara alternatif, anda boleh memilih entiti tambahan untuk diinges. Anda juga boleh mengalih keluar sebarang entiti yang sudah dipilih jika tiada kebergantungan.

   > [!IMPORTANT]
   > Jika terdapat pergantungan pada fail model.json atau manifest.json sedia ada dan set entiti, anda akan melihat mesej ralat dan tidak boleh memilih fail model.json atau manifest.json yang berbeza. Keluarkan kebergantungan sebelum mengubah fail model.json atau manifest.json atau cipta sumber data baharu dengan fail model.json atau manifest.json yang anda mahu gunakan untuk mengelakkan daripada mengeluarkan kebergantungan.

8. Secara alternatif, anda boleh memilih atribut atau entiti tambahan untuk mendayakan pemprofilan data atau menyahdayakan yang sudah dipilih.

[!INCLUDE [footer-include](includes/footer-banner.md)]
