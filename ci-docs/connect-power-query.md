---
title: Sambung ke Power Query sumber data (mengandungi video)
description: Ingest data melalui Power Query penyambung (mengandungi video).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 7af51ed04fbd28149ea501c58e6fe71b5fa6d4b6
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207056"
---
# <a name="connect-to-a-power-query-data-source"></a>Sambung ke Power Query sumber data

Power Query menawarkan satu set penyambung yang luas untuk menelan data. Kebanyakan penyambung ini disokong oleh Dynamics 365 Customer Insights.

Menambah sumber data berdasarkan Power Query penyambung secara amnya mengikuti langkah-langkah yang digariskan dalam bahagian ini. Walau bagaimanapun, bergantung pada penyambung yang anda gunakan, maklumat berbeza diperlukan. Untuk mengetahui lebih lanjut, lihat dokumentasi tentang penyambung individu dalam [Power Query rujukan penyambung](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Cipta sumber data baharu

1. Pergi **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. Pilih **Microsoft Power Query**.

1. **Berikan Nama** dan Perihalan **pilihan** untuk sumber data dan pilih **Berikut**.

1. Pilih salah satu [penyambung yang tersedia](#available-power-query-data-sources). Dalam contoh ini, kami memilih **penyambung Teks/CSV**.

1. Masukkan butiran yang diperlukan dalam **Tetapan sambungan** untuk penyambung yang dipilih dan pilih **Seterusnya** untuk melihat pratonton data.

1. Pilih **Ubah data**.

1. Dialog **Power Query - Edit pertanyaan** membolehkan anda menyemak dan memperhalusi data. Entiti yang dikenal pasti sistem dalam sumber data terpilih anda muncul dalam anak tetingkap kiri.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Edit dialog pertanyaan":::

1. Anda juga boleh mengubah data anda. Pilih entiti untuk mengedit atau mengubah. Gunakan pilihan dalam Power Query tetingkap untuk menggunakan transformasi. Setiap transformasi disenaraikan di bawah **Langkah-langkah yang digunakan**. Power Query menyediakan banyak [pilihan transformasi](/power-query/power-query-what-is-power-query#transformations) pra-binaan.

   Kami mengesyorkan agar anda menggunakan transformasi berikut:

   - Jika anda sedang mengambil data dari fail CSV, baris pertama selalunya mengandungi tajuk. Pergi ke **Transform** dan pilih **Gunakan baris pertama sebagai pengepala**.
   - Pastikan jenis data ditetapkan dengan sewajarnya. Contohnya, untuk medan tarikh, pilih jenis tarikh.

1. Untuk menambah entiti tambahan pada **sumber data anda dalam dialog Edit pertanyaan**, pergi ke **Rumah** dan pilih **Dapatkan data**. Ulangi langkah 5-10 sehingga anda telah menambah semua entiti untuk sumber data ini. Jika anda mempunyai pangkalan data yang merangkumi set data berbilang, setiap set data adalah entiti sendiri.

1. Pilih **Simpan**. Halaman **Sumber data** dibuka menunjukkan sumber data baru dalam **status Segar Semula**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuatkan data boleh mengambil masa. Selepas segar semula yang berjaya, data yang ditelan boleh disemak dari [**halaman Entiti**](entities.md).

> [!CAUTION]
> Sumber data berdasarkan Power Query mencipta [aliran data masuk Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Jangan ubah nama aliran data dalam Power Platform pusat pentadbiran yang digunakan dalam Wawasan Pelanggan. Menamakan semula aliran data menyebabkan isu dengan rujukan antara Sumber data Wawasan Pelanggan dan Dataverse aliran data.

### <a name="available-power-query-data-sources"></a>Sumber data yang tersedia Power Query

[Power Query Lihat rujukan](/power-query/connectors/) penyambung untuk senarai penyambung yang boleh anda gunakan untuk mengimport data ke Wawasan Pelanggan.

Penyambung dengan tanda semak dalam **lajur Wawasan Pelanggan (Dataflows)** tersedia untuk mencipta sumber data baharu berdasarkan Power Query. Semak dokumentasi penyambung tertentu untuk mengetahui lebih lanjut tentang prasyarat, [had](/power-query/power-query-online-limits) pertanyaan dan butiran lain.

## <a name="add-data-from-on-premises-data-sources"></a>Tambah data daripada sumber data di premis

Pengambilan data daripada sumber data di premis disokong berdasarkan Microsoft Power Platform aliran data (PPDF). Anda boleh mendayakan aliran data dalam Wawasan Pelanggan dengan [menyediakan Microsoft Dataverse URL](create-environment.md) persekitaran semasa menyediakan persekitaran.

Sumber data yang dicipta selepas mengaitkan Dataverse persekitaran dengan Wawasan Pelanggan menggunakan [Power Platform aliran](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) data secara lalai. Aliran data menyokong kesambungan di premis menggunakan get laluan data. Anda boleh mengalih keluar dan mencipta semula sumber data yang Dataverse wujud sebelum persekitaran dikaitkan [menggunakan get laluan](/data-integration/gateway/service-gateway-app) data di premis.

Get laluan data daripada sedia ada Power BI atau Power Apps persekitaran akan kelihatan dan anda boleh menggunakannya semula dalam Wawasan Pelanggan. Halaman sumber data menunjukkan pautan untuk pergi ke persekitaran Microsoft Power Platform yang anda boleh melihat dan mengkonfigurasikan get laluan data di premis.

> [!IMPORTANT]
> Pastikan get laluan anda dikemas kini kepada versi terkini. Anda boleh memasang kemas kini dan mengkonfigurasi semula get laluan daripada gesaan yang ditunjukkan pada skrin get laluan secara langsung atau [memuat turun versi terkini](https://powerapps.microsoft.com/downloads/). Jika anda tidak menggunakan versi get laluan terkini, segar semula aliran data gagal dengan mesej ralat seperti **Kata kunci tidak disokong: sifat konfigurasi. Nama parameter: kata kunci**.
>
> Ralat dengan di premis get laluan data dalam Wawasan Pelanggan sering disebabkan oleh isu konfigurasi. Untuk maklumat lanjut tentang menyelesaikan masalah get laluan data, lihat [Menyelesaikan masalah get laluan data di premis](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Mengedit Power Query sumber data

> [!NOTE]
> Mungkin tidak mungkin untuk membuat perubahan pada sumber data yang sedang digunakan dalam salah satu proses aplikasi (contohnya pembahagian atau penyatuan data).
>
> **Dalam halaman Tetapan**, anda boleh menjejaki kemajuan setiap proses aktif. Apabila proses selesai, anda boleh kembali ke halaman **Sumber Data** dan membuat perubahan anda.

1. Pergi **Data** > **Sumber data**.

1. Di sebelah sumber data yang anda ingin kemas kini, pilih **Edit**.

1. Gunakan perubahan dan transformasi anda dalam **Power Query dialog - Edit pertanyaan** seperti yang diterangkan dalam [seksyen Cipta sumber data](#create-a-new-data-source) baru.

1. Pilih **Simpan** untuk menggunakan perubahan anda dan kembali ke **halaman Sumber** data.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
