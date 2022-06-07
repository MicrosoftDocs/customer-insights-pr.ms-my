---
title: Data Ingest melalui Power Query penyambung (mengandungi video)
description: Penyambung untuk sumber data berdasarkan Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4db97ec02eb96662d30a8536ea42372f81f318d2
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800168"
---
# <a name="connect-to-a-power-query-data-source"></a>Sambung ke Power Query sumber data

Power Query menawarkan satu set penyambung yang luas untuk menelan data. Kebanyakan penyambung ini disokong oleh Dynamics 365 Customer Insights. 

Menambah sumber data berdasarkan Power Query penyambung secara amnya mengikuti langkah-langkah yang digariskan dalam bahagian ini. Walau bagaimanapun, bergantung pada penyambung yang anda gunakan, maklumat berbeza diperlukan. Untuk mengetahui lebih lanjut, lihat dokumentasi tentang penyambung individu dalam [Power Query rujukan penyambung](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Cipta sumber data baharu

1. Pergi **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. Pilih **Microsoft Power Query**.

1. Berikan **Nama** untuk sumber data dan pilih **Seterusnya** untuk mencipta sumber data.

1. Pilih salah satu [penyambung yang tersedia](#available-power-query-data-sources). Dalam contoh ini, kami memilih **penyambung Teks/CSV**.

1. Masukkan butiran yang diperlukan dalam **Tetapan sambungan** untuk penyambung yang dipilih dan pilih **Seterusnya** untuk melihat pratonton data.

1. Pilih **Ubah data**. Dalam langkah ini, anda akan tambahkan entiti pada sumber data anda. Entiti adalah set data. Jika anda mempunyai pangkalan data yang merangkumi set data berbilang, setiap set data adalah entiti sendiri.

1. Dialog **Power Query - Edit pertanyaan** membolehkan anda menyemak dan memperhalusi data. Entiti yang dikenal pasti sistem dalam sumber data terpilih anda muncul dalam anak tetingkap kiri.

   > [!div class="mx-imgBorder"]
   > ![Edit dialog pertanyaan.](media/data-manager-configure-edit-queries.png "Edit dialog pertanyaan")

1. Anda juga boleh mengubah data anda. Pilih entiti untuk mengedit atau mengubah. Gunakan pilihan dalam Power Query tetingkap untuk menggunakan transformasi. Setiap transformasi akan disenaraikan di bawah **Langkah yang digunakan**. Power Query menyediakan banyak pilihan transformasi pra-binaan. Untuk maklumat lanjut, lihat [Power Query Transformasi](/power-query/power-query-what-is-power-query#transformations).

   Kami mengesyorkan agar anda menggunakan transformasi berikut:

   - Jika anda sedang mengambil data dari fail CSV, baris pertama selalunya mengandungi tajuk. Pergi ke **Transform** dan pilih **Gunakan baris pertama sebagai pengepala**.
   - Pastikan jenis data ditetapkan dengan sewajarnya. Contohnya, untuk medan tarikh, pilih jenis tarikh.

1. Untuk menambah entiti tambahan pada **sumber data anda dalam dialog Edit pertanyaan**, pergi ke **Rumah** dan pilih **Dapatkan data**.

1. Pilih **Simpan** di bahagian Power Query bawah tetingkap untuk menyimpan transformasi. Selepas menyimpan, anda akan dapati sumber data anda pada **Data** > **Sumber data**.

1. Pada halaman **Sumber data**, anda akan dapati sumber data baharu berada dalam status **Segar semula**.

## <a name="available-power-query-data-sources"></a>Sumber data yang tersedia Power Query

[Power Query Lihat rujukan](/power-query/connectors/) penyambung untuk senarai penyambung yang boleh anda gunakan untuk mengimport data ke Wawasan Pelanggan. 

Penyambung dengan tanda semak dalam **lajur Wawasan Pelanggan (Dataflows)** tersedia untuk mencipta sumber data baharu berdasarkan Power Query. Semak semula dokumentasi bagi penyambung khusus untuk mengetahui lebih lanjut tentang prasyarat, had dan butiran lain.

## <a name="edit-power-query-data-sources"></a>Mengedit Power Query sumber data

> [!NOTE]
> Ia mungkin tidak mustahil untuk membuat perubahan kepada sumber data yang sedang digunakan dalam salah satu proses aplikasi (contohnya *pembahagian*, *padanan* atau *penggabungan*). 
>
> **Dalam halaman Tetapan**, anda boleh menjejaki kemajuan setiap proses aktif. Apabila proses selesai, anda boleh kembali ke halaman **Sumber Data** dan membuat perubahan anda.

1. Pergi **Data** > **Sumber data**.

2. Pilih elipsis menegak (&vellip;) di sebelah sumber data yang anda mahu ubah dan pilih **Edit** daripada menu juntai bawah.

   > [!div class="mx-imgBorder"]
   > ![Edit pilihan.](media/edit-option-data-sources.png "Edit pilihan")

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]
   
3. Gunakan perubahan dan transformasi anda dalam **Power Query dialog - Edit pertanyaan** seperti yang diterangkan dalam [seksyen Cipta sumber data](#create-a-new-data-source) baru.

4. Pilih **Simpan** selepas Power Query melengkapkan pengeditan anda untuk menyimpan perubahan anda.


[!INCLUDE [footer-include](includes/footer-banner.md)]
