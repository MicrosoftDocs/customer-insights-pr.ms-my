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
ms.openlocfilehash: d79b2d34e425e123224209814fef6e367c77c813
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396102"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Sambungkan ke data dalam Azure Data Lake Storage

Menelan data menggunakan Dynamics 365 Customer Insights akaun Gen2 anda Azure Data Lake Storage. Pengingesan data boleh penuh atau bertambah.

## <a name="prerequisites"></a>Prasyarat

- Pengingesan data menyokong Azure Data Lake Storage *akaun Gen2* secara eksklusif. Anda tidak boleh menggunakan akaun Data Lake Storage Gen1 untuk menelan data.

- Akaun Azure Data Lake Storage mesti mendayakan [ruang nama hierarki](/azure/storage/blobs/data-lake-storage-namespace). Data mesti disimpan dalam format folder hierarki yang mentakrifkan folder akar dan mempunyai subfolder untuk setiap entiti. Subfolder boleh mempunyai data penuh atau folder data tambahan.

- Untuk mengesahkan dengan prinsip perkhidmatan Azure, pastikan ia dikonfigurasikan dalam penyewa anda. Untuk maklumat lanjut, lihat [Menyambung kepada Azure Data Lake Storage akaun Gen2 dengan prinsipal](connect-service-principal.md) perkhidmatan Azure.

- Anda Azure Data Lake Storage ingin menyambung dan menelan data daripada perlu berada dalam rantau Azure yang sama dengan Dynamics 365 Customer Insights persekitaran. Sambungan ke folder Common Data Model dari data lake dalam rantau Azure berbeza tidak disokong. Untuk mengetahui rantau Azure persekitaran, pergi ke **Perihal Sistem** > **·** > **Pentadbir** dalam Wawasan Pelanggan.

- Data yang disimpan dalam perkhidmatan dalam talian boleh disimpan di lokasi yang berbeza daripada tempat data diproses atau disimpan.Dynamics 365 Customer InsightsDengan mengimport atau menyambung ke data yang disimpan dalam perkhidmatan dalam talian, anda bersetuju bahawa data boleh dipindahkan dan disimpan dengan Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat](https://www.microsoft.com/trust-center) Amanah Microsoft.

- Prinsipal perkhidmatan Wawasan Pelanggan mestilah berada dalam salah satu peranan berikut untuk mengakses akaun storan. Untuk maklumat lanjut, lihat [Berikan keizinan kepada prinsipal perkhidmatan untuk mengakses akaun](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account) storan.
  - Pembaca Data Blob Storan
  - Pemilik Data Blob Storan
  - Penyumbang Blob Data Storan

- Pengguna yang menyediakan sambungan sumber data memerlukan keizinan Penyumbang Data Blob Storan paling sedikit pada akaun storan.

- Data dalam Storan Tasik Data anda harus mengikut standard Model Data Umum untuk penyimpanan data anda dan mempunyai model data umum yang manifes untuk mewakili skema fail data (*.csv atau *.parket). Manifes mesti memberikan butiran entiti seperti lajur entiti dan jenis data, dan lokasi fail data dan jenis fail. Untuk maklumat lanjut, lihat [Manifes](/common-data-model/sdk/manifest) Model Data Biasa. Jika manifes tidak hadir, pengguna Pentadbir dengan Pemilik Data Storan Blob atau capaian Penyumbang Data Blob Storan boleh menentukan skema apabila menelan data.

## <a name="connect-to-azure-data-lake-storage"></a>Sambungkan ke Azure Data Lake Storage

1. Pergi **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. Pilih **Azure data lake storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Kotak dialog untuk memasukkan butiran sambungan untuk Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. **Masukkan Nama** untuk sumber data dan Perihalan **pilihan**. Nama unik mengenal pasti sumber data dan dirujuk dalam proses hiliran dan tidak boleh diubah.

1. Pilih salah satu opsyen berikut untuk **Sambung storan anda menggunakan**. Untuk maklumat lanjut, lihat [Menyambung Wawasan Pelanggan kepada Azure Data Lake Storage akaun Gen2 dengan prinsipal](connect-service-principal.md) perkhidmatan Azure.

   - **Azure resource**: Enter the **Resource Id**. Secara pilihan, jika anda ingin menelan data daripada akaun storan melalui Pautan Peribadi Azure, pilih **Dayakan Pautan** Peribadi. Untuk maklumat lanjut, lihat [Pautan](security-overview.md#set-up-an-azure-private-link) Peribadi.
   - **Langganan** Azure: Pilih **Langganan** dan kemudian **kumpulan** Sumber dan **akaun** Storan. Secara pilihan, jika anda ingin menelan data daripada akaun storan melalui Pautan Peribadi Azure, pilih **Dayakan Pautan** Peribadi. Untuk maklumat lanjut, lihat [Pautan](security-overview.md#set-up-an-azure-private-link) Peribadi.
  
   > [!NOTE]
   > Anda memerlukan salah satu peranan berikut sama ada ke bekas atau akaun storan untuk membuat sumber data:
   >
   >  - Storage Blob Data Reader mencukupi untuk dibaca daripada akaun storan dan menelan data ke Wawasan Pelanggan.
   >  - Penyumbang atau Pemilik Data Blob Storan diperlukan jika anda ingin mengedit fail manifes terus dalam Wawasan Pelanggan.  
  
1. Pilih nama **Bekas** yang mengandungi data dan skema (model.json atau fail manifest.json) untuk mengimport data dan pilih **Berikut**.
   > [!NOTE]
   > Sebarang fail model.json atau manifest.json yang berkaitan dengan sumber data lain dalam persekitaran tidak akan ditunjukkan dalam senarai. Walau bagaimanapun, fail model.json atau manifest.json boleh digunakan untuk sumber data dalam berbilang persekitaran.

1. Untuk mencipta skema baharu, pergi ke [Cipta fail](#create-a-new-schema-file) skema baharu.

1. Untuk menggunakan skema sedia ada, navigasi ke folder yang mengandungi fail model.json atau manifest.cdm.json. Anda boleh mencari dalam direktori untuk mencari fail.

1. Pilih fail json dan pilih **Seterusnya**. Senarai entiti yang tersedia dipaparkan.

   :::image type="content" source="media/review-entities.png" alt-text="Kotak dialog senarai entiti untuk dipilih":::

1. Pilih entiti yang ingin anda sertakan.

   :::image type="content" source="media/ADLS_required.png" alt-text="Kotak dialog menunjukkan kekunci Diperlukan untuk Primer":::

   > [!TIP]
   > Untuk mengedit entiti dalam antara muka penyuntingan JSON, pilih entiti dan kemudian **Edit fail skema**. Buat perubahan dan pilih **Simpan**.

1. Untuk entiti terpilih yang memerlukan pengingesan tambahan, **Paparan yang diperlukan** di bawah **Segar Semula tambahan**. Untuk setiap entiti ini, lihat [Mengkonfigurasikan segar semula tambahan untuk sumber](incremental-refresh-data-sources.md) data Azure Data Lake.

1. Bagi entiti terpilih yang mempunyai kunci primer belum ditakrifkan, **Paparan yang diperlukan** di bawah **Kekunci primer**. Bagi setiap entiti ini:
   1. Pilih **Diperlukan**. Panel **entiti** Edit dipaparkan.
   1. Pilih **kekunci** Utama. Kunci utama ialah atribut yang unik kepada entiti. Untuk atribut menjadi kekunci utama yang sah, ia tidak boleh mengandungi nilai pendua, nilai yang hilang atau nilai tak sah. Atribut rentetan, integer dan jenis data GUID disokong sebagai kekunci primer.
   1. Secara pilihan, tukar corak partition.
   1. Pilih **Tutup** untuk menyimpan dan menutup panel.

1. Pilih bilangan **Atribut untuk setiap entiti yang** disertakan. Halaman **Uruskan atribut** dipaparkan.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Kotak dialog untuk memilih pemprofilan data.":::

   1. Cipta atribut baharu, edit atau padamkan atribut sedia ada. Anda boleh menukar nama, format data atau menambah jenis semantik.
   1. Untuk mendayakan analisis dan keupayaan lain, pilih **Profil data** untuk keseluruhan entiti atau untuk atribut tertentu. Secara lalai, tiada entiti didayakan untuk pemprofilan data.
   1. Pilih **Selesai**.

1. Pilih **Simpan**. Halaman **Sumber data** terbuka menunjukkan sumber data baru dalam **menyegar semula** status.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuatkan data boleh mengambil masa. Selepas segar semula berjaya, data yang ditelan boleh disemak dari [**halaman Entiti**](entities.md).

### <a name="create-a-new-schema-file"></a>Buat fail skema baru

1. Pilih **Fail skema baharu**.

1. Masukkan nama untuk fail dan pilih **Simpan**.

1. Pilih **Entiti baharu**. Panel **Entiti** Baru dipaparkan.

1. Masukkan nama entiti dan pilih **Lokasi fail data**.
   - **Berbilang fail** .csv atau .parket: Semak lalu ke folder akar, pilih jenis corak dan masukkan ungkapan.
   - **Fail .csv tunggal atau .parquet**: Semak lalu ke fail .csv atau .parquet dan pilihnya.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Kotak dialog untuk mencipta entiti baru dengan Lokasi fail data diserlahkan.":::

1. Pilih **Simpan**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Kotak dialog untuk mentakrifkan atau menjana atribut secara automatik.":::

1. Pilih **takrifkan atribut** untuk menambah atribut secara manual atau pilih **jananya** secara automatik. Untuk menentukan atribut, masukkan nama, pilih format data dan jenis semantik pilihan. Untuk atribut yang dijanakan secara automatik:

   1. Selepas atribut dijanakan secara automatik, pilih **Semak atribut**. Halaman **Uruskan atribut** dipaparkan.

   1. Pastikan format data adalah betul untuk setiap atribut.

   1. Untuk mendayakan analisis dan keupayaan lain, pilih **Profil data** untuk keseluruhan entiti atau untuk atribut tertentu. Secara lalai, tiada entiti didayakan untuk pemprofilan data.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Kotak dialog untuk memilih pemprofilan data.":::

   1. Pilih **Selesai**. Halaman **Pilih entiti** dipaparkan.

1. Teruskan menambah entiti dan atribut, jika berkenaan.

1. Selepas semua entiti telah ditambah, pilih **Sertakan** untuk memasukkan entiti dalam pengingesan sumber data.

   :::image type="content" source="media/ADLS_required.png" alt-text="Kotak dialog menunjukkan kekunci Diperlukan untuk Primer":::

1. Untuk entiti terpilih yang memerlukan pengingesan tambahan, **Paparan yang diperlukan** di bawah **Segar Semula tambahan**. Untuk setiap entiti ini, lihat [Mengkonfigurasikan segar semula tambahan untuk sumber](incremental-refresh-data-sources.md) data Azure Data Lake.

1. Bagi entiti terpilih yang mempunyai kunci primer belum ditakrifkan, **Paparan yang diperlukan** di bawah **Kekunci primer**. Bagi setiap entiti ini:
   1. Pilih **Diperlukan**. Panel **entiti** Edit dipaparkan.
   1. Pilih **kekunci** Utama. Kunci utama ialah atribut yang unik kepada entiti. Untuk atribut menjadi kekunci utama yang sah, ia tidak boleh mengandungi nilai pendua, nilai yang hilang atau nilai tak sah. Atribut rentetan, integer dan jenis data GUID disokong sebagai kekunci primer.
   1. Secara pilihan, tukar corak partition.
   1. Pilih **Tutup** untuk menyimpan dan menutup panel.

1. Pilih **Simpan**. Halaman **Sumber data** terbuka menunjukkan sumber data baru dalam **menyegar semula** status.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuatkan data boleh mengambil masa. Selepas segar semula berjaya, data yang ditelan boleh disemak dari [**halaman Entiti**](entities.md).

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Azure Data Lake Storage Mengedit sumber data

Anda boleh mengemas kini *Connect ke akaun storan menggunakan* pilihan. Untuk maklumat lanjut, lihat [Menyambung Wawasan Pelanggan kepada Azure Data Lake Storage akaun Gen2 dengan prinsipal](connect-service-principal.md) perkhidmatan Azure. Untuk menyambung kepada bekas berbeza daripada akaun storan anda, atau mengubah nama akaun, [mencipta sambungan sumber data baharu](#connect-to-azure-data-lake-storage).

1. Pergi **Data** > **Sumber data**.

1. Di sebelah sumber data yang ingin anda kemas kini, pilih **Edit**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Kotak dialog untuk mengedit Azure Data Lake sumber data.":::

1. Ubah sebarang maklumat berikut:

   - **Penerangan**
   - **Sambungkan storan anda menggunakan** dan maklumat sambungan. Anda tidak boleh mengubah maklumat **Bekas** semasa mengemas kini sambungan.
      > [!NOTE]
      > Salah satu peranan berikut mesti diberikan kepada akaun storan atau bekas:
        > - Pembaca Data Blob Storan
        > - Pemilik Data Blob Storan
        > - Penyumbang Blob Data Storan

   - **Dayakan Pautan** Peribadi jika anda ingin menelan data daripada akaun storan melalui Pautan Peribadi Azure. Untuk maklumat lanjut, lihat [Pautan](security-overview.md#set-up-an-azure-private-link) Peribadi.

1. Pilih **Seterusnya**.
1. Ubah mana-mana daripada berikut:
   - Navigasi ke fail model.json atau manifest.json yang berbeza dengan set entiti yang berbeza dari bekas.
   - Untuk menambah entiti tambahan untuk menelan, pilih **Entiti baru**.
   - Untuk mengalih keluar mana-mana entiti yang telah dipilih jika tiada kebergantungan, pilih entiti dan **Padam**.
      > [!IMPORTANT]
      > Jika terdapat pergantungan pada fail model.json atau manifest.json sedia ada dan set entiti, anda akan melihat mesej ralat dan tidak boleh memilih fail model.json atau manifest.json yang berbeza. Keluarkan kebergantungan sebelum mengubah fail model.json atau manifest.json atau cipta sumber data baharu dengan fail model.json atau manifest.json yang anda mahu gunakan untuk mengelakkan daripada mengeluarkan kebergantungan.
   - Untuk mengubah lokasi fail data atau kunci utama, pilih **Edit**.
   - Untuk mengubah data pengingesan tambahan, lihat [Mengkonfigurasikan segar semula tambahan untuk sumber data Azure Data Lake](incremental-refresh-data-sources.md).
   - Hanya tukar nama entiti agar sepadan dengan nama entiti dalam fail .json.

     > [!NOTE]
     > Sentiasa simpan nama entiti dalam Wawasan Pelanggan sama seperti nama entiti di dalam fail model.json atau manifest.json selepas pengingesan. Wawasan Pelanggan mengesahkan semua nama entiti dengan model.json atau manifest.json semasa setiap penyegaran semula sistem. Jika nama entiti ditukar sama ada di dalam Wawasan Pelanggan atau di luar, ralat berlaku kerana Wawasan Pelanggan tidak dapat mencari nama entiti baharu dalam fail .json. Jika nama entiti tertelan diubah secara tidak sengaja, edit nama entiti dalam Wawasan Pelanggan agar sepadan dengan nama dalam fail .json.

1. Pilih **Atribut** untuk menambah atau mengubah atribut atau untuk mendayakan pemprofilan data. Kemudian pilih **Selesai**.

1. Klik **Simpan** untuk menggunakan perubahan anda dan kembali ke **halaman Sumber data**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
