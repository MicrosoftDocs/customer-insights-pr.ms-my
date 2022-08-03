---
title: Sambungkan ke folder Common Data Model menggunakan akaun Azure Data Lake
description: Bekerja dengan data Common Data Model menggunakan Azure Data Lake Storage.
ms.date: 07/27/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: e071bf9364b44a92d81c9ff2269ff4e8654010aa
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207010"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Sambungkan ke data dalam Azure Data Lake Storage

Ingest data ke dalam Dynamics 365 Customer Insights menggunakan akaun Gen2 anda Azure Data Lake Storage. Pengingesan data boleh penuh atau tambahan.

## <a name="prerequisites"></a>Prasyarat

- Pengingesan data menyokong Azure Data Lake Storage *akaun Gen2* secara eksklusif. Anda tidak boleh menggunakan akaun Data Lake Storage Gen1 untuk menelan data.

- Akaun Azure Data Lake Storage mesti mempunyai [ruang nama hierarki yang didayakan](/azure/storage/blobs/data-lake-storage-namespace). Data mesti disimpan dalam format folder hierarki yang mentakrifkan folder akar dan mempunyai subfolder untuk setiap entiti. Subfolder boleh mempunyai data penuh atau folder data tambahan.

- Untuk mengesahkan dengan prinsip perkhidmatan Azure, pastikan ia dikonfigurasikan dalam penyewa anda. Untuk maklumat lanjut, lihat [Menyambung ke Azure Data Lake Storage akaun Gen2 dengan prinsipal](connect-service-principal.md) perkhidmatan Azure.

- Anda Azure Data Lake Storage mahu menyambung dan menelan data daripada perlu berada dalam rantau Azure yang sama dengan Dynamics 365 Customer Insights persekitaran. Sambungan ke folder Common Data Model dari data lake dalam rantau Azure berbeza tidak disokong. Untuk mengetahui rantau Azure persekitaran, pergi ke **Sistem** > **Pentadbir** > **Perihal** dalam Wawasan Pelanggan.

- Data yang disimpan dalam perkhidmatan dalam talian mungkin disimpan di lokasi yang berbeza daripada di mana data diproses atau disimpan dalam Dynamics 365 Customer Insights.Dengan mengimport atau menyambung ke data yang disimpan dalam perkhidmatan dalam talian, anda bersetuju bahawa data boleh dipindahkan dan disimpan dengan Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat Amanah Microsoft](https://www.microsoft.com/trust-center).

- Prinsipal perkhidmatan Wawasan Pelanggan mesti berada dalam salah satu peranan berikut untuk mengakses akaun storan. Untuk maklumat lanjut, lihat [Berikan keizinan kepada prinsipal perkhidmatan untuk mengakses akaun](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account) storan.
  - Pembaca Data Blob Storan
  - Pemilik Data Blob Storan
  - Penyumbang Blob Data Storan

- Data dalam Storan Tasik Data anda hendaklah mengikut standard Model Data Biasa untuk penyimpanan data anda dan mempunyai model data biasa yang nyata untuk mewakili skema fail data (*.csv atau *.parquet). Manifesto mesti memberikan butiran entiti seperti lajur entiti dan jenis data, dan lokasi fail data dan jenis fail. Untuk maklumat lanjut, lihat [Model Data Biasa nyata](/common-data-model/sdk/manifest). Jika manifes tidak hadir, pengguna Pentadbir dengan Pemilik Data Blob Storan atau akses Penyumbang Data Blob Storan boleh menentukan skema apabila menelan data.

## <a name="connect-to-azure-data-lake-storage"></a>Sambungkan ke Azure Data Lake Storage

1. Pergi **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. Select **Azure data lake storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Kotak dialog untuk memasukkan butiran sambungan untuk Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. **Masukkan Nama** untuk sumber data dan Perihalan **pilihan**. Nama itu mengenal pasti sumber data secara unik dan dirujuk dalam proses hiliran dan tidak boleh diubah.

1. Pilih salah satu daripada pilihan berikut untuk **Sambungkan storan anda menggunakan**. Untuk maklumat lanjut, lihat [Menyambungkan Wawasan Pelanggan ke Azure Data Lake Storage akaun Gen2 dengan prinsipal](connect-service-principal.md) perkhidmatan Azure.

   - **Azure resource**: Enter the **Resource Id**. Secara pilihan, jika anda ingin menelan data daripada akaun storan melalui Azure Private Link, pilih **Dayakan Pautan** Peribadi. Untuk maklumat lanjut, lihat [Pautan](security-overview.md#private-links-tab) Peribadi.
   - **Langganan** Azure: Pilih **Langganan** dan kemudian **kumpulan** Sumber dan **akaun** Storan. Secara pilihan, jika anda ingin menelan data daripada akaun storan melalui Azure Private Link, pilih **Dayakan Pautan** Peribadi. Untuk maklumat lanjut, lihat [Pautan](security-overview.md#private-links-tab) Peribadi.
  
   > [!NOTE]
   > Anda memerlukan salah satu peranan berikut sama ada ke bekas atau akaun storan untuk membuat sumber data:
   >
   >  - Storage Blob Data Reader adalah mencukupi untuk membaca daripada akaun storan dan menelan data kepada Wawasan Pelanggan. 
   >  - Penyumbang Data Blob Storan atau Pemilik diperlukan jika anda ingin mengedit fail manifes secara langsung dalam Wawasan Pelanggan.  
  
1. Pilih nama **Kontena** yang mengandungi data dan skema (fail model.json atau manifest.json) untuk mengimport data dan pilih **Seterusnya**.
   > [!NOTE]
   > Sebarang fail model.json atau manifest.json yang berkaitan dengan sumber data lain dalam persekitaran tidak akan ditunjukkan dalam senarai. Walau bagaimanapun, fail model.json atau manifest.json boleh digunakan untuk sumber data dalam berbilang persekitaran.

1. Untuk mencipta skema baru, pergi ke [Cipta fail](#create-a-new-schema-file) skema baru.

1. Untuk menggunakan skema sedia ada, navigasi ke folder yang mengandungi fail model.json atau manifest.cdm.json. Anda boleh mencari dalam direktori untuk mencari fail.

1. Pilih fail json dan pilih **Seterusnya**. Senarai entiti yang ada dipaparkan.

   :::image type="content" source="media/review-entities.png" alt-text="Kotak dialog senarai entiti untuk dipilih":::

1. Pilih entiti yang anda mahu sertakan.

   :::image type="content" source="media/ADLS_required.png" alt-text="Kotak dialog menunjukkan kekunci Diperlukan untuk Utama":::

   > [!TIP]
   > Untuk mengedit entiti dalam antara muka pengeditan JSON, pilih entiti dan kemudian **Edit fail** skema. Buat perubahan dan pilih **Simpan**.

1. Untuk entiti terpilih yang memerlukan pengambilan tambahan, **Diperlukan** dipaparkan di bawah **Segar semula tambahan**. Bagi setiap entiti ini, lihat [Konfigurasikan segar semula tambahan untuk sumber data Azure Data Lake](incremental-refresh-data-sources.md).

1. Untuk entiti terpilih di mana kekunci utama belum ditakrif, **Diperlukan** dipaparkan di bawah **kekunci** Utama. Bagi setiap entiti ini:
   1. Pilih **Diperlukan**. Panel **entiti** Edit dipaparkan.
   1. Pilih kekunci **Utama**. Kunci utama ialah atribut yang unik kepada entiti. Untuk atribut menjadi kekunci utama yang sah, ia tidak boleh mengandungi nilai pendua, nilai yang hilang atau nilai tak sah. Atribut jenis data rentetan, integer dan GUID disokong sebagai kekunci utama.
   1. Secara pilihan, ubah corak partition.
   1. Pilih **Tutup** untuk menyimpan dan menutup panel.

1. Pilih bilangan **Atribut untuk setiap entiti yang** disertakan. Halaman **Urus atribut** dipaparkan.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Kotak dialog untuk memilih pemprofilan data.":::

   1. Cipta atribut baru, edit atau padamkan atribut sedia ada. Anda boleh menukar nama, format data, atau menambah jenis semantik.
   1. Untuk mendayakan analisis dan keupayaan lain, pilih **Profil data** untuk keseluruhan entiti atau untuk atribut tertentu. Secara lalai, tiada entiti didayakan untuk pemprofilan data.
   1. Pilih **Selesai**.

1. Pilih **Simpan**. Halaman **Sumber data** dibuka menunjukkan sumber data baru dalam **status Segar Semula**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuatkan data boleh mengambil masa. Selepas segar semula yang berjaya, data yang ditelan boleh disemak dari [**halaman Entiti**](entities.md).

### <a name="create-a-new-schema-file"></a>Cipta fail skema baru

1. Pilih **Fail skema baru**.

1. Masukkan nama untuk fail dan pilih **Simpan**.

1. Pilih **Entiti baru**. Panel **Entiti** Baru dipaparkan.

1. Masukkan nama entiti dan pilih **lokasi Fail data**.
   - **Berbilang fail** .csv atau .parquet: Semak lalu ke folder root, pilih jenis corak dan masukkan ungkapan.
   - **Fail .csv tunggal atau .parquet**: Semak lalu ke fail .csv atau .parquet dan pilihnya.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Kotak dialog untuk mencipta entiti baru dengan lokasi fail Data diserlahkan.":::

1. Pilih **Simpan**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Kotak dialog untuk mentakrifkan atau menjana atribut secara automatik.":::

1. Pilih **tentukan atribut** untuk menambah atribut secara manual atau pilih menjananya **secara** automatik. Untuk menentukan atribut, masukkan nama, pilih format data dan jenis semantik pilihan. Untuk atribut yang dijana secara automatik:

   1. Selepas atribut dijana secara automatik, pilih **Semak semula atribut**. Halaman **Urus atribut** dipaparkan.

   1. Pastikan format data adalah betul untuk setiap atribut.

   1. Untuk mendayakan analisis dan keupayaan lain, pilih **Profil data** untuk keseluruhan entiti atau untuk atribut tertentu. Secara lalai, tiada entiti didayakan untuk pemprofilan data.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Kotak dialog untuk memilih pemprofilan data.":::

   1. Pilih **Selesai**. Halaman **Pilih entiti dipaparkan**.

1. Teruskan menambah entiti dan atribut, jika berkenaan.

1. Selepas semua entiti telah ditambah, pilih **Sertakan** untuk memasukkan entiti dalam sumber data pengambilan.

   :::image type="content" source="media/ADLS_required.png" alt-text="Kotak dialog menunjukkan kekunci Diperlukan untuk Utama":::

1. Untuk entiti terpilih yang memerlukan pengambilan tambahan, **Diperlukan** dipaparkan di bawah **Segar semula tambahan**. Bagi setiap entiti ini, lihat [Konfigurasikan segar semula tambahan untuk sumber data Azure Data Lake](incremental-refresh-data-sources.md).

1. Untuk entiti terpilih di mana kekunci utama belum ditakrif, **Diperlukan** dipaparkan di bawah **kekunci** Utama. Bagi setiap entiti ini:
   1. Pilih **Diperlukan**. Panel **entiti** Edit dipaparkan.
   1. Pilih kekunci **Utama**. Kunci utama ialah atribut yang unik kepada entiti. Untuk atribut menjadi kekunci utama yang sah, ia tidak boleh mengandungi nilai pendua, nilai yang hilang atau nilai tak sah. Atribut jenis data rentetan, integer dan GUID disokong sebagai kekunci utama.
   1. Secara pilihan, ubah corak partition.
   1. Pilih **Tutup** untuk menyimpan dan menutup panel.

1. Pilih **Simpan**. Halaman **Sumber data** dibuka menunjukkan sumber data baru dalam **status Segar Semula**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuatkan data boleh mengambil masa. Selepas segar semula yang berjaya, data yang ditelan boleh disemak dari [**halaman Entiti**](entities.md).

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Azure Data Lake Storage Mengedit sumber data

Anda boleh mengemas kini *Sambung ke akaun storan menggunakan* pilihan. Untuk maklumat lanjut, lihat [Menyambungkan Wawasan Pelanggan ke Azure Data Lake Storage akaun Gen2 dengan prinsipal](connect-service-principal.md) perkhidmatan Azure. Untuk menyambung kepada bekas berbeza daripada akaun storan anda, atau mengubah nama akaun, [mencipta sambungan sumber data baharu](#connect-to-azure-data-lake-storage).

1. Pergi **Data** > **Sumber data**.

1. Di sebelah sumber data yang anda ingin kemas kini, pilih **Edit**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Kotak dialog untuk mengedit Azure Data Lake sumber data.":::

1. Tukar mana-mana maklumat berikut:

   - **Penerangan**
   - **Sambungkan storan anda menggunakan** dan maklumat sambungan. Anda tidak boleh mengubah maklumat **Bekas** semasa mengemas kini sambungan.
      > [!NOTE]
      > Salah satu peranan berikut mesti diberikan kepada akaun storan atau bekas:
        > - Pembaca Data Blob Storan
        > - Pemilik Data Blob Storan
        > - Penyumbang Blob Data Storan

   - **Dayakan Pautan** Peribadi jika anda ingin mengasingkan data daripada akaun storan melalui Azure Private Link. Untuk maklumat lanjut, lihat [Pautan](security-overview.md#private-links-tab) Peribadi.

1. Pilih **Seterusnya**.
1. Tukar mana-mana yang berikut:
   - Navigasi ke fail model.json atau manifest.json yang berbeza dengan set entiti yang berbeza dari bekas.
   - Untuk menambah entiti tambahan pada menelan, pilih **Entiti baru**.
   - Untuk mengalih keluar mana-mana entiti yang telah dipilih jika tiada kebergantungan, pilih entiti dan **Padam**.
      > [!IMPORTANT]
      > Jika terdapat pergantungan pada fail model.json atau manifest.json sedia ada dan set entiti, anda akan melihat mesej ralat dan tidak boleh memilih fail model.json atau manifest.json yang berbeza. Keluarkan kebergantungan sebelum mengubah fail model.json atau manifest.json atau cipta sumber data baharu dengan fail model.json atau manifest.json yang anda mahu gunakan untuk mengelakkan daripada mengeluarkan kebergantungan.
   - Untuk menukar lokasi fail data atau kekunci utama, pilih **Edit**.
   - Untuk mengubah data pengingesan tambahan, lihat [Mengkonfigurasikan segar semula tambahan untuk sumber](incremental-refresh-data-sources.md) data Azure Data Lake.
   - Hanya tukar nama entiti untuk dipadankan dengan nama entiti dalam fail .json.

     > [!NOTE]
     > Sentiasa simpan nama entiti dalam Wawasan Pelanggan sama seperti nama entiti di dalam fail model.json atau manifest.json selepas pengingesan. Wawasan Pelanggan mengesahkan semua nama entiti dengan model.json atau manifest.json semasa setiap segar semula sistem. Jika nama entiti ditukar sama ada di dalam Wawasan Pelanggan atau di luar, ralat berlaku kerana Wawasan Pelanggan tidak dapat mencari nama entiti baharu dalam fail .json. Jika nama entiti yang ditelan ditukar secara tidak sengaja, edit nama entiti dalam Wawasan Pelanggan untuk dipadankan dengan nama dalam fail .json.

1. Pilih **Atribut** untuk menambah atau mengubah atribut, atau untuk mendayakan pemprofilan data. Kemudian pilih **Selesai**.

1. Klik **Simpan** untuk menggunakan perubahan anda dan kembali ke **halaman Sumber** data.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
