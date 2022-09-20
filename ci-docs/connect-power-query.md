---
title: Menyambung ke Power Query sumber data (mengandungi video)
description: Menelan data melalui Power Query penyambung (mengandungi video).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6a25e332bafab414c9def4e1e6b461139dd24ea6
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463276"
---
# <a name="connect-to-a-power-query-data-source"></a>Sambung ke Power Query sumber data

Power Query menawarkan satu set penyambung yang luas untuk menelan data. Kebanyakan penyambung ini disokong oleh Dynamics 365 Customer Insights.

Menambah sumber data berdasarkan Power Query penyambung secara amnya mengikut langkah yang digariskan dalam seksyen ini. Walau bagaimanapun, bergantung pada penyambung yang anda gunakan, maklumat berbeza diperlukan. Untuk mengetahui selanjutnya, lihat dokumentasi tentang penyambung individu dalam [Power Query rujukan penyambung](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Cipta sumber data baharu

1. Pergi **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. Pilih **Microsoft Power Query**.

1. **Berikan Nama** dan Perihalan **pilihan** untuk sumber data dan pilih **Berikut**.

1. Pilih salah satu [penyambung yang tersedia](#available-power-query-data-sources). Dalam contoh ini, kami memilih **penyambung Teks / CSV**.

1. Masukkan butiran yang diperlukan dalam **Tetapan sambungan** untuk penyambung yang dipilih dan pilih **Seterusnya** untuk melihat pratonton data.

1. Pilih **Ubah data**.

1. Dialog **Power Query Edit pertanyaan** membolehkan anda menyemak dan memperincikan data. Entiti yang dikenal pasti sistem dalam sumber data terpilih anda muncul dalam anak tetingkap kiri.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Edit dialog pertanyaan":::

1. Anda juga boleh mengubah data anda. Pilih entiti untuk mengedit atau mengubah. Gunakan pilihan dalam Power Query tetingkap untuk menggunakan transformasi. Setiap transformasi disenaraikan di bawah **langkah** Gunaan. Power Query menyediakan banyak [pilihan transformasi](/power-query/power-query-what-is-power-query#transformations) pra-binaan.

   Kami mengesyorkan agar anda menggunakan transformasi berikut:

   - Jika anda sedang mengambil data dari fail CSV, baris pertama selalunya mengandungi tajuk. Pergi ke **Ubah** dan pilih **Gunakan baris pertama sebagai pengepala**.
   - Pastikan jenis data ditetapkan dengan sewajarnya. Contohnya, untuk medan tarikh, pilih jenis tarikh.

1. Untuk menambah entiti tambahan pada sumber data anda dalam **dialog Edit pertanyaan**, pergi ke **Rumah** dan pilih **Dapatkan data**. Ulangi langkah 5-10 sehingga anda telah menambah semua entiti untuk sumber data ini. Jika anda mempunyai pangkalan data yang merangkumi set data berbilang, setiap set data adalah entiti sendiri.

1. Pilih **Simpan**. Halaman **Sumber data** terbuka menunjukkan sumber data baru dalam **menyegar semula** status.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuatkan data boleh mengambil masa. Selepas segar semula berjaya, data yang ditelan boleh disemak dari [**halaman Entiti**](entities.md).

> [!CAUTION]
>
> - Sumber data berdasarkan Power Query mencipta [aliran data dalam Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Jangan ubah nama aliran data dalam Power Platform pusat pentadbiran yang digunakan dalam Wawasan Pelanggan. Menamakan semula aliran data menyebabkan isu dengan rujukan antara Wawasan Pelanggan sumber data dan Dataverse aliran data.
> - Penilaian serentak untuk Power Query sumber data dalam Wawasan Pelanggan mempunyai had segar semula yang sama [seperti Aliran Data dalam PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Jika segar semula data gagal kerana ia mencapai had penilaian, kami mengesyorkan anda melaraskan jadual segar semula bagi setiap aliran data untuk memastikan sumber data tidak diproses pada masa yang sama.

### <a name="available-power-query-data-sources"></a>Sumber data yang tersedia Power Query

[Power Query Lihat rujukan](/power-query/connectors/) penyambung untuk senarai penyambung yang anda boleh gunakan untuk mengimport data ke Wawasan Pelanggan.

Penyambung dengan tanda semak dalam **lajur Wawasan Pelanggan (Aliran Data)** tersedia untuk mencipta sumber data baru berdasarkan Power Query. Semak semula dokumentasi penyambung tertentu untuk mengetahui lebih lanjut tentang prasyarat, [pengehadan](/power-query/power-query-online-limits) pertanyaan dan butiran lain.

## <a name="add-data-from-on-premises-data-sources"></a>Tambah data daripada sumber data di premis

Pengambilan data daripada sumber data di premis disokong berdasarkan Microsoft Power Platform aliran data (PPDF). Anda boleh mendayakan aliran data dalam Wawasan [Pelanggan dengan Microsoft Dataverse menyediakan URL](create-environment.md) persekitaran semasa menyediakan persekitaran.

Sumber data yang dicipta selepas mengaitkan Dataverse persekitaran dengan Wawasan Pelanggan menggunakan [Power Platform aliran](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) data secara lalai. Aliran data menyokong kesambungan di premis menggunakan get laluan data. Anda boleh mengalih keluar dan mencipta semula sumber data yang wujud sebelum Dataverse persekitaran dikaitkan [menggunakan di premis get laluan data](/data-integration/gateway/service-gateway-app).

Get laluan data daripada persekitaran sedia Power BI ada atau Power Apps persekitaran akan kelihatan dan anda boleh menggunakannya semula dalam Wawasan Pelanggan jika get laluan data dan persekitaran Wawasan Pelanggan berada dalam Rantau Azure yang sama. Halaman sumber data menunjukkan pautan untuk pergi ke persekitaran Microsoft Power Platform yang anda boleh melihat dan mengkonfigurasikan get laluan data di premis.

> [!IMPORTANT]
> Pastikan get laluan anda dikemas kini kepada versi terkini. Anda boleh memasang kemas kini dan mengkonfigurasi semula get laluan daripada gesaan yang ditunjukkan pada skrin get laluan secara langsung atau [memuat turun versi](https://powerapps.microsoft.com/downloads/) terkini. Jika anda tidak menggunakan versi get laluan terkini, segar semula aliran data gagal dengan mesej ralat seperti **Kata kunci tidak disokong: sifat konfigurasi. Nama parameter: kata kunci**.
>
> Ralat dengan di premis get laluan data dalam Wawasan Pelanggan sering disebabkan oleh isu konfigurasi. Untuk maklumat lanjut tentang menyelesaikan masalah get laluan data, lihat [Menyelesaikan masalah get laluan](/data-integration/gateway/service-gateway-tshoot) data di premis.

## <a name="edit-power-query-data-sources"></a>Mengedit Power Query sumber data

> [!NOTE]
> Anda mungkin tidak boleh membuat perubahan pada sumber data yang sedang digunakan dalam salah satu proses apl (contohnya segmentasi atau penyatuan data).
>
> Dalam halaman **Seting**, anda boleh menjejaki kemajuan setiap proses aktif. Apabila proses selesai, anda boleh kembali ke halaman **Sumber Data** dan membuat perubahan anda.

1. Pergi **Data** > **Sumber data**.

1. Di sebelah sumber data yang ingin anda kemas kini, pilih **Edit**.

1. Gunakan perubahan dan transformasi anda dalam **Power Query dialog Edit pertanyaan** seperti yang diterangkan dalam [seksyen Cipta sumber data](#create-a-new-data-source) baru.

1. Pilih **Simpan** untuk menggunakan perubahan anda dan kembali ke **halaman Sumber data**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
