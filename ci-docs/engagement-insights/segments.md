---
title: Lihat dan cipta segmen
description: Cara mencipta, mengedit dan memadam segmen dan tempat segmen digunakan.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: e99c04e6c92d8ca16c2d69957e0f5b7dba0ac757
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225387"
---
# <a name="view-and-create-segments"></a>Lihat dan cipta segmen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmen membolehkan anda mengenal pasti subset pelawat berdasarkan ciri-ciri atau interaksi laman web. Segmen membolehkan anda menggunakan penapis dan menganalisis subset tersebut. Analisis boleh membantu untuk memeriksa dan memberi respons kepada trend dalam perniagaan anda. 

:::image type="content" source="media/segments-page.png" alt-text="Syot layar aplikasi cerapan penglibatan yang menunjukkan senarai segmen yang sedia ada dalam ruang kerja.":::

## <a name="view-segments"></a>Lihat segmen

1. Pergi ke **Data** dalam anak tetingkap navigasi kiri. 

1. Pilih tab **Segmen** untuk melihat senarai semua segmen dalam ruang kerja. 

## <a name="create-a-segment"></a>Cipta segmen

Segmen terdiri daripada peraturan dan syarat yang berhubung dengan operator logik. Syarat menggunakan penapis pada dimensi yang dipilih. Setiap segmen boleh menggunakan sehingga lima dimensi.

Contoh berikut menunjukkan segmen dengan dua syarat dalam satu peraturan. Ia menapis semua peristiwa laman web yang pelayar ialah Chrome dan sistem operasi ialah iOS atau Android.

:::image type="content" source="media/segment-sample.png" alt-text="Contoh segmen dengan dua syarat dalam peraturan untuk menapis bagi peristiwa laman web.":::

Bahagian ini menerangkan cara mencipta *segmen kosong* daripada mula.

1. Pergi ke **Data** > **Segmen**.

1. Pilih **Bahagian baharu**.

1. Dalam **Pustaka sumber**, pilih (+) bersebelahan dengan atribut yang anda mahu tapis mengikut. Pada masa ini, anda hanya boleh mencipta segmen berdasarkan dimensi.

   :::image type="content" source="media/create-new-segment.png" alt-text="Cipta segmen baharu.":::

1. Dalam bahagian **Peraturan**, pilih operator dan nilai untuk atribut yang dipilih. Operasi berikut disokong.

   :::image type="content" source="media/choose-operator-segment.png" alt-text="Pilih operator untuk segmen baharu anda.":::

   - **adalah**: memerlukan padanan tepat untuk menyertakan nilai. Menggunakan **sama dengan** untuk nilai tunggal atau **mana-mana** untuk menyertakan berbilang nilai.
   - **tidak**: memerlukan padanan tepat untuk mengecualikan nilai. Menggunakan **sama dengan** untuk nilai tunggal atau **mana-mana** untuk menyertakan berbilang nilai.
   - **bermula dengan**: rentetan yang nilai sepadan bermula.
   - **berakhir dengan**: rentetan yang nilai sepadan berakhir.
   - **mengandungi**: rentetan yang terkandung dalam nilai sepadan.

1. Untuk menambah lebih banyak syarat pada kumpulan, anda boleh menggunakan operator logik. Atribut yang diunjurkan diambil kira apabila menggunakan operator set.
   - Operator **DAN**: Kedua-dua syarat mesti dipenuhi sebagai sebahagian proses pembahagian. Pilihan ini adalah paling berguna apabila anda menakrif syarat dalam entiti yang berbeza.
   - Operator **ATAU**: Salah satu syarat perlu dipenuhi sebagai sebahagian daripada proses pembahagian. Pilihan ini paling berguna apabila anda menakrif berbilang syarat untuk entiti yang sama.

1. Pilih **Simpan** dan namakan segmen. 

Segmen akan disenaraikan di halaman **Segmen** dan anda boleh menggunakan segmen pada semua laporan dan corong dalam ruang kerja.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Gunakan segmen dalam laporan atau corong

Anda boleh menggunakan segmen pada laporan atau corong untuk menapis berdasarkan syarat dalam segmen. Walau bagaimanapun, anda tidak boleh menggunakan segmen pada laporan penggunaan masa nyata.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Laporan paparan halaman dengan senarai juntai bawah yang diperluas untuk memilih segmen untuk digunakan.":::

Untuk menggunakan segmen, buka laporan atau corong. Pilih **+ Tambah syarat** dan pilih **Tapis mengikut segmen**. Pilih segmen daripada senarai yang ingin anda gunakan. Segmen akan digunakan untuk laporan. Jika carta tidak menyokong segmen, ia menunjukkan ralat. Untuk mendapatkan maklumat lanjut, lihat [Cipta dan urus laporan corong](funnel-reports.md).
 
Anda boleh menggunakan *sehingga tiga segmen* untuk laporan atau corong.

## <a name="edit-a-segment"></a>Edit segmen

1. Pergi ke **Data** > **Segmen**.
1. Pilih segmen dalam senarai untuk membuka segmen. 
1. Tukar atau tambah nilai seperti yang diperlukan.
1. Pilih **Simpan** untuk menggunakan perubahan anda.

## <a name="change-the-name-of-a-segment"></a>Tukar nama segmen

1. Pergi ke **Data** > **Segmen**.
1. Dalam senarai segmen, pilih **Lagi [...]**. 
1. Daripada senarai juntai bawah, pilih **Edit nama** .
1. Masukkan nama baharu dan pilih **Namakan semula**.

## <a name="delete-a-segment"></a>Padam segmen

1. Pergi ke **Data** > **Segmen**.
1. Dalam senarai segmen, pilih **Lagi [...]**. 
1. Daripada senarai juntai bawah, pilih **Padam**.
1. Pilih **Padam** untuk mengesahkan.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
