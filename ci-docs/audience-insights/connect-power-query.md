---
title: Menelan data melalui penyambung Power Query (Video)
description: Penyambung untuk sumber data berdasarkan Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 38c447d80a25feca087ca9f110278b8401423018
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903851"
---
# <a name="connect-to-a-power-query-data-source"></a>Sambung kepada sumber data Power Query

Power Query menawarkan set sambungan yang luas kepada data yang paling. Kebanyakan penyambung ini disokong oleh Dynamics 365 Customer Insights. 

Menambah sumber data berdasarkan penyambung Power Query secara amnya mengikuti langkah yang digariskan dalam bahagian ini. Walau bagaimanapun, bergantung pada penyambung yang anda gunakan, maklumat berbeza diperlukan. Untuk mengetahui lebih lanjut, lihat dokumentasi tentang penyambung individu dalam [rujukan penyambung Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Cipta sumber data baharu

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. Pilih **Microsoft Power Query, kemudian pilih** **Berikut**.

1. Berikan **Nama** untuk sumber data dan pilih **Seterusnya** untuk mencipta sumber data.

1. Pilih salah satu [penyambung yang tersedia](#available-power-query-data-sources). Dalam contoh ini, kami memilih **penyambung Teks / CSV.**

1. Masukkan butiran yang diperlukan dalam **Tetapan sambungan** untuk penyambung yang dipilih dan pilih **Seterusnya** untuk melihat pratonton data.

1. Pilih **Ubah data**. Dalam langkah ini, anda akan tambahkan entiti pada sumber data anda. Entiti adalah set data. Jika anda mempunyai pangkalan data yang merangkumi set data berbilang, setiap set data adalah entiti sendiri.

1. Dialog **Power Query - Edit pertanyaan** membolehkan anda menyemak semula dan memperhalusi data. Entiti yang dikenal pasti sistem dalam sumber data terpilih anda muncul dalam anak tetingkap kiri.

   > [!div class="mx-imgBorder"]
   > ![Edit dialog pertanyaan.](media/data-manager-configure-edit-queries.png "Edit dialog pertanyaan")

1. Anda juga boleh mengubah data anda. Pilih entiti untuk mengedit atau mengubah. Gunakan pilihan dalam tetingkap Power Query untuk menggunakan transformasi. Setiap transformasi akan disenaraikan di bawah **Langkah yang digunakan**. Power Query menyediakan pelbagai pilihan transformasi yang dibina terlebih dahulu. Untuk maklumat lebih lanjut, lihat [Transformasi Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Anda boleh tambah entiti tambahan ke sumber data anda dengan memilih **Dapatkan data** di dalam dialog **Edit pertanyaan**.

   Kami mengesyorkan agar anda menggunakan transformasi berikut:

   - Jika anda sedang mengambil data dari fail CSV, baris pertama selalunya mengandungi tajuk. Pergi ke **Ubah jadual** dan pilih **Gunakan pengepala sebagai baris pertama**.
   - Pastikan jenis data ditetapkan dengan sewajarnya.

1. Pilih **Simpan** di bahagian bawah tetingkap Power Query untuk menyimpan transformasi. Selepas menyimpan, anda akan dapati sumber data anda pada **Data** > **Sumber data**.

1. Pada halaman **Sumber data**, anda akan dapati sumber data baharu berada dalam status **Segar semula**.

## <a name="available-power-query-data-sources"></a>Sedia sumber data Power Query

Lihat [rujukan penyambung Power Query](/power-query/connectors/) untuk senarai penyambung yang anda boleh gunakan untuk mengimport data ke Wawasan Pelanggan. 

Penyambung dengan tanda semak dalam lajur **Customer Insights (Alir data)** tersedia untuk mencipta sumber data baharu berdasarkan Power query. Semak semula dokumentasi bagi penyambung khusus untuk mengetahui lebih lanjut tentang prasyarat, had dan butiran lain.

## <a name="edit-power-query-data-sources"></a>Edit sumber data Power Query

> [!NOTE]
> Ia mungkin tidak mustahil untuk membuat perubahan kepada sumber data yang sedang digunakan dalam salah satu proses aplikasi (contohnya *pembahagian*, *padanan* atau *penggabungan*). 
>
> Dalam **halaman** Seting, anda boleh menjejaki kemajuan setiap proses aktif. Apabila proses selesai, anda boleh kembali ke halaman **Sumber Data** dan membuat perubahan anda.

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

2. Pilih elipsis menegak di sebelah sumber data yang ingin anda ubah dan pilih **Edit** daripada menu juntai bawah.

   > [!div class="mx-imgBorder"]
   > ![Edit pilihan.](media/edit-option-data-sources.png "Edit pilihan")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Gunakan perubahan dan transformasi anda dalam dialog **Power Query - Edit pertanyaan** seperti yang diterangkan dalam bahagian [Cipta bahagian sumber data baharu](#create-a-new-data-source).

4. Pilih **Simpan** dalam Power Query selepas melengkapkan pengeditan anda untuk menyimpan perubahan anda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
