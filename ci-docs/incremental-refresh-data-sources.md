---
title: Segar semula tambahan untuk Power Query dan sumber data Azure Data Lake
description: Segar semula data baru dan dikemas kini untuk sumber data besar berdasarkan Power Query atau sumber data tasik data Azure.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207148"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Segar semula tambahan untuk Power Query dan sumber data Azure Data Lake

Segar semula tambahan untuk sumber data berdasarkan Power Query atau Azure Data Lake menyediakan kelebihan berikut:

- **Lebih cepat menyegar semula** - Hanya data yang telah diubah akan disegar semula. Sebagai contoh, anda mungkin menyegar semula hanya lima hari yang lalu daripada set data yang bersejarah.
- **Kebolehpercayaan dipertingkat** - Dengan menyegarkan semula yang lebih kecil, anda tidak perlu mengekalkan sambungan ke sistem sumber yang tidak menentu untuk jangka masa panjang, mengurangkan risiko isu sambungan.
- **Penggunaan sumber dikurangkan** - Menyegar semula hanya sebahagian daripada jumlah data anda yang membawa kepada penggunaan sumber pengkomputeran yang lebih cekap dan mengurangkan jejak alam.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Mengkonfigurasikan segar semula tambahan untuk sumber data berdasarkan Power Query

Wawasan Pelanggan membenarkan segar semula tambahan untuk sumber data yang diimport melalui Power Query pengingesan tambahan tersebut. Sebagai contoh, pangkalan data SQL Azure dengan medan tarikh dan masa, yang menunjukkan apabila rekod data terakhir dikemas kini.

1. [Buat sumber data baru berdasarkan Power Query](connect-power-query.md).

1. Pilih sumber data yang menyokong segar semula tambahan, seperti [pangkalan data Azure SQL](/power-query/connectors/azuresqldatabase).

1. Pilih entiti atau jadual untuk dimasukkan.

1. Lengkapkan langkah-langkah transformasi dan pilih **Seterusnya**.

1. Dalam kotak dialog **Tetapkan segar semula tokokan**, pilih **Sediakan** untuk membuka **Tetapan segar semula tokokan**. Jika anda memilih **Langkau**, sumber data akan menyegar semula keseluruhan set data.
   > [!TIP]
   > Anda juga boleh menggunakan segar semula tokokan kemudian dengan mengedit sumber data sedia ada.

1. Pada **Tetapan segar semula tokokan**, anda akan mengkonfigurasi segar semula tokokan untuk semua entiti yang anda pilih semasa mencipta sumber data.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurasikan seting segar semula tambahan.":::

1. Pilih entiti dan berikan butiran berikut:

   - **Takrifkan kunci utama**: Pilih kunci utama untuk entiti atau jadual.
   - **Takrifkan medan "terakhir dikemas kini"**": Medan ini hanya akan memaparkan atribut jenis tarikh atau masa. Pilih atribut yang menunjukkan apabila rekod terakhir dikemas kini. Ia akan digunakan untuk mengenal pasti rekod yang berada dalam lingkungan peningkatan segar semula jangka masa.
   - **Semak untuk setiap kemas kini**: Tentukan tempoh masa yang anda mahu untuk tempoh masa segar semula tokokan.

1. Pilih **Simpan** untuk melengkapkan penciptaan sumber data. Segar semula data awal akan menjadi segar semula sepenuhnya. Selepas itu, segar semula data tokokan berlaku seperti yang dikonfigurasikan dalam langkah sebelumnya.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Konfigurasikan segar semula tambahan untuk sumber data Azure Data Lake

Wawasan Pelanggan membenarkan segar semula tambahan untuk sumber data yang disambungkan ke Azure Data Lake Storage. Untuk menggunakan pengingesan tambahan dan segar semula untuk entiti, konfigurasikan entiti tersebut apabila menambah sumber data Azure Data Lake atau lebih baharu apabila mengedit sumber data. Folder data entiti mesti mengandungi folder berikut:

- **FullData**: Folder dengan fail data yang mengandungi rekod awal
- **Data** Tambahan: Folder dengan folder hierarki tarikh/masa dalam **format yyyy/mm/dd/hh** yang mengandungi kemas kini tambahan. **hh** mewakili jam UTC kemas kini dan mengandungi **folder Upserts** dan **Deletes**. **Upserts** mengandungi fail data dengan kemas kini kepada rekod sedia ada atau rekod baru. **Hapus** mengandungi fail data dengan rekod yang akan dialih keluar.

1. Apabila menambah atau mengedit sumber data, navigasi ke **anak tetingkap Atribut** untuk entiti.

1. Semak semula atribut. Pastikan atribut tarikh yang dicipta atau terakhir dikemas kini disediakan dengan *format Data DateTime* **dan** jenis *Semantik Calendar.Date* **.** Edit atribut jika perlu dan pilih **Selesai**.

1. **Daripada anak tetingkap Pilih Entiti**, edit entiti. Kotak **semak pengambilan** tambahan dipilih.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Konfigurasikan entiti dalam sumber data untuk segar semula tokokan.":::

   1. Semak lalu ke folder root yang mengandungi fail .csv atau .parquet untuk data penuh, upserts data tambahan dan pemadaman data tambahan.
   1. Masukkan sambungan untuk data penuh dan kedua-dua fail tambahan (\. csv atau \. parket).
   1. Untuk fail .csv, pilih pembatas lajur dan jika anda mahu baris pertama fail sebagai pengepala lajur.
   1. Pilih **Simpan**.

1. Untuk **Terakhir dikemas kini**, pilih atribut cap masa tarikh.

1. Jika kekunci **Utama** tidak dipilih, pilih kekunci utama. Kunci utama ialah atribut yang unik kepada entiti. Untuk atribut menjadi kekunci utama yang sah, ia tidak boleh mengandungi nilai pendua, nilai yang hilang atau nilai tak sah. Atribut jenis data rentetan, integer dan GUID disokong sebagai kekunci utama.

1. Pilih **Tutup** untuk menyimpan dan menutup anak tetingkap.

1. Teruskan dengan menambah atau mengedit sumber data.

[!INCLUDE [footer-include](includes/footer-banner.md)]
