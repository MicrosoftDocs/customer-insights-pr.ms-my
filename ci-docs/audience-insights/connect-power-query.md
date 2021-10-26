---
title: Inges data melalui penyambung Power Query
description: Penyambung untuk sumber data berdasarkan Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: ab6edc3f33ebacb81f55c0882a78c5827b4384ed
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643505"
---
# <a name="connect-to-a-power-query-data-source"></a>Sambung kepada sumber data Power Query

Power Query menawarkan set sambungan yang luas kepada data yang paling. Kebanyakan penyambung ini disokong oleh Dynamics 365 Customer Insights. Menambahkan sumber data berdasarkan penyambung Power Query secara amnya mengikut langkah yang digariskan dalam bahagian seterusnya. Walau bagaimanapun, bergantung pada penyambung yang anda gunakan, maklumat berbeza diperlukan. Untuk mendapatkan maklumat lanjut, lihat dokumentasi mengenai penyambung individu dalam [rujukan penyambung Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Cipta sumber data baharu

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. Pilih kaedah **Import data** dan pilih **Seterusnya**.

1. Berikan **Nama** untuk sumber data dan pilih **Seterusnya** untuk mencipta sumber data. Namakan garis panduan: 
   - Bermula dengan huruf.
   - Gunakan huruf dan nombor sahaja. Aksara khas dan ruang idak dibenarkan.
   - Gunakan antara 3 dan 64 aksara.

1. Pilih salah satu [penyambung yang tersedia](#available-power-query-data-sources). Untuk contoh ini, kami pilih penyambung **Text/CSV**.

1. Masukkan butiran yang diperlukan dalam **Tetapan sambungan** untuk penyambung yang dipilih dan pilih **Seterusnya** untuk melihat pratonton data.

1. Pilih **Ubah data**. Dalam langkah ini, anda akan tambahkan entiti pada sumber data anda. Entiti adalah set data. Jika anda mempunyai pangkalan data yang merangkumi set data berbilang, setiap set data adalah entiti sendiri.

1. Dialog **Power Query - Edit pertanyaan** membolehkan anda menyemak semula dan memperhalusi data. Entiti yang dikenal pasti sistem dalam sumber data terpilih anda muncul dalam anak tetingkap kiri.

   > [!div class="mx-imgBorder"]
   > ![Edit dialog pertanyaan.](media/data-manager-configure-edit-queries.png "Edit dialog pertanyaan")

1. Anda juga boleh mengubah data anda. Pilih entiti untuk mengedit atau mengubah. Gunakan pilihan dalam tetingkap Power Query untuk menggunakan transformasi. Setiap transformasi akan disenaraikan di bawah **Langkah yang digunakan**. Power Query menyediakan pelbagai pilihan transformasi yang dibina terlebih dahulu. Untuk maklumat lebih lanjut, lihat [Transformasi Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Anda boleh tambah entiti tambahan ke sumber data anda dengan memilih **Dapatkan data** di dalam dialog **Edit pertanyaan**.

   Transformasi ini amat disyorkan:

   - Jika anda sedang mengambil data dari fail CSV, baris pertama selalunya mengandungi tajuk. Pergi ke **Ubah jadual** dan pilih **Gunakan pengepala sebagai baris pertama**.
   - Pastikan jenis data ditetapkan dengan sewajarnya.

1. Pilih **Simpan** di bahagian bawah tetingkap Power Query untuk menyimpan transformasi. Selepas menyimpan, anda akan dapati sumber data anda pada **Data** > **Sumber data**.

1. Pada halaman **Sumber data**, anda akan dapati sumber data baharu berada dalam status **Segar semula**.

## <a name="available-power-query-data-sources"></a>Sedia sumber data Power Query

Lihat [Rujukan penyambung Power Query](/power-query/connectors/) untuk senarai penyambung terkini yang boleh anda pilih untuk mengimport data pada Customer Insights. 

Penyambung dengan tanda semak dalam lajur **Customer Insights (Alir data)** tersedia untuk mencipta sumber data baharu berdasarkan Power query. Semak semula dokumentasi bagi penyambung khusus untuk mengetahui lebih lanjut tentang prasyarat, had dan butiran lain.

## <a name="edit-power-query-data-sources"></a>Edit sumber data Power Query

> [!NOTE]
> Ia mungkin tidak mustahil untuk membuat perubahan kepada sumber data yang sedang digunakan dalam salah satu proses aplikasi (contohnya *pembahagian*, *padanan* atau *penggabungan*). 
>
> Menggunakan halaman **Tetapan**, anda boleh menjejaki perkembangan setiap proses aktif. Apabila proses selesai, anda boleh kembali ke halaman **Sumber Data** dan membuat perubahan anda.

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

2. Pilih elipsis menegak di sebelah sumber data yang ingin anda ubah dan pilih **Edit** daripada menu juntai bawah.

   > [!div class="mx-imgBorder"]
   > ![Edit pilihan.](media/edit-option-data-sources.png "Edit pilihan")

3. Gunakan perubahan dan transformasi anda dalam dialog **Power Query - Edit pertanyaan** seperti yang diterangkan dalam bahagian [Cipta bahagian sumber data baharu](#create-a-new-data-source).

4. Pilih **Simpan** dalam Power Query selepas melengkapkan pengeditan anda untuk menyimpan perubahan anda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]