---
title: Menelan data melalui Power Query penyambung (mengandungi video)
description: Penyambung untuk sumber data berdasarkan Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: aae49be4364676ecc7a307e60eeca13859f1662a
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934989"
---
# <a name="connect-to-a-power-query-data-source"></a>Sambung ke Power Query sumber data

Power Query menawarkan satu set penyambung yang luas untuk menelan data. Kebanyakan penyambung ini disokong oleh Dynamics 365 Customer Insights. 

Menambah sumber data berdasarkan Power Query penyambung secara amnya mengikuti langkah yang digariskan dalam seksyen ini. Walau bagaimanapun, bergantung pada penyambung yang anda gunakan, maklumat berbeza diperlukan. Untuk mengetahui lebih lanjut, lihat dokumentasi tentang penyambung individu dalam [Power Query rujukan penyambung](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Cipta sumber data baharu

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. Pilih **Microsoft, kemudian pilih Seterusnya Power Query** **·**.

1. Berikan **Nama** untuk sumber data dan pilih **Seterusnya** untuk mencipta sumber data.

1. Pilih salah satu [penyambung yang tersedia](#available-power-query-data-sources). Dalam contoh ini, kami memilih **penyambung Teks / CSV.**

1. Masukkan butiran yang diperlukan dalam **Tetapan sambungan** untuk penyambung yang dipilih dan pilih **Seterusnya** untuk melihat pratonton data.

1. Pilih **Ubah data**. Dalam langkah ini, anda akan tambahkan entiti pada sumber data anda. Entiti adalah set data. Jika anda mempunyai pangkalan data yang merangkumi set data berbilang, setiap set data adalah entiti sendiri.

1. Dialog **Power Query - Edit pertanyaan membolehkan anda menyemak dan** memperincikan data. Entiti yang dikenal pasti sistem dalam sumber data terpilih anda muncul dalam anak tetingkap kiri.

   > [!div class="mx-imgBorder"]
   > ![Edit dialog pertanyaan.](media/data-manager-configure-edit-queries.png "Edit dialog pertanyaan")

1. Anda juga boleh mengubah data anda. Pilih entiti untuk mengedit atau mengubah. Gunakan opsyen dalam Power Query tetingkap untuk menggunakan transformasi. Setiap transformasi akan disenaraikan di bawah **Langkah yang digunakan**. Power Query menyediakan pelbagai pilihan transformasi pra-binaan. Untuk maklumat lanjut, lihat [Power Query Transformasi](/power-query/power-query-what-is-power-query#transformations).

1. Anda boleh tambah entiti tambahan ke sumber data anda dengan memilih **Dapatkan data** di dalam dialog **Edit pertanyaan**.

   Kami mengesyorkan agar anda menggunakan transformasi berikut:

   - Jika anda sedang mengambil data dari fail CSV, baris pertama selalunya mengandungi tajuk. Pergi ke **Ubah jadual** dan pilih **Gunakan pengepala sebagai baris pertama**.
   - Pastikan jenis data ditetapkan dengan sewajarnya.

1. Pilih **Simpan di bahagian bawah tetingkap untuk menyimpan** Power Query transformasi. Selepas menyimpan, anda akan dapati sumber data anda pada **Data** > **Sumber data**.

1. Pada halaman **Sumber data**, anda akan dapati sumber data baharu berada dalam status **Segar semula**.

## <a name="available-power-query-data-sources"></a>Power Query Sumber data yang ada

Lihat [Power Query rujukan penyambung](/power-query/connectors/) untuk senarai penyambung yang anda boleh gunakan untuk mengimport data ke Wawasan Pelanggan. 

Penyambung dengan tanda semak dalam **lajur Wawasan Pelanggan (Aliran Data)** tersedia untuk mencipta sumber data baharu berdasarkan Power Query. Semak semula dokumentasi bagi penyambung khusus untuk mengetahui lebih lanjut tentang prasyarat, had dan butiran lain.

## <a name="edit-power-query-data-sources"></a>Mengedit Power Query sumber data

> [!NOTE]
> Ia mungkin tidak mustahil untuk membuat perubahan kepada sumber data yang sedang digunakan dalam salah satu proses aplikasi (contohnya *pembahagian*, *padanan* atau *penggabungan*). 
>
> Dalam **halaman** Seting, anda boleh menjejaki kemajuan setiap proses aktif. Apabila proses selesai, anda boleh kembali ke halaman **Sumber Data** dan membuat perubahan anda.

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

2. Pilih elipsis menegak di sebelah sumber data yang ingin anda ubah dan pilih **Edit** daripada menu juntai bawah.

   > [!div class="mx-imgBorder"]
   > ![Edit pilihan.](media/edit-option-data-sources.png "Edit pilihan")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Gunakan perubahan dan transformasi anda dalam **Power Query dialog - Edit pertanyaan seperti yang diterangkan dalam seksyen Cipta sumber data**[baru](#create-a-new-data-source).

4. Pilih **Simpan masuk selepas melengkapkan** Power Query pengeditan anda untuk menyimpan perubahan anda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
