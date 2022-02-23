---
title: Lengkapkan data separa menggunakan ramalan
description: Gunakan ramalan untuk mengisi data pelanggan yang tidak lengkap.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3100acf383d85c00a6ff0a8ebc54e038bd813427
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732417"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Lengkapkan data separa anda dengan ramalan (sudah lapuk)

> [!IMPORTANT]
> Ciri ini akan **lapuk** pada **5 November 2021**. Pelaksanaan semasa akan terus berfungsi sehingga ciri dialih keluar, tetapi anda tidak akan dapat mencipta integrasi baru menggunakan arahan di bawah.

Ramalan membolehkan anda mencipta nilai ramalan dengan mudah yang boleh meningkatkan pemahaman anda tentang pelanggan. Pada halaman **Kecerdasan** > **Ramalan**, anda boleh memilih **Ramalan saya** untuk melihat ramalan yang anda konfigurasikan dalam bahagian wawasan khalayak lain dan membolehkan anda menyesuaikannya lagi.

> [!NOTE]
> Anda tidak boleh menggunakan ciri ini jika persekitaran anda menggunakan storan Azure Data Lake Gen 2.
>
> Ciri ramalan menggunakan alat automatik untuk menilai data dan membuat ramalan berasaskan pada data itu dan dengan itu mempunyai keupayaan yang boleh digunakan sebagai kaedah pemprofilan, kerana ia ditakrifkan oleh Peraturan Perlindungan Data Umum (“GDPR”). Pelanggan menggunakan ciri ini untuk memproses data berkemungkinan tertakluk pada GDPR atau undang-undang atau peraturan yang lain. Anda bertanggungjawab untuk memastikan bahawa penggunaan Dynamics 365 Customer Insights anda, termasuk ramalan, mematuhi semua undang-undang dan peraturan yang berkenaan, termasuk undang-undang yang berkaitan dengan privasi, data peribadi, data biometrik, perlindungan data dan kerahsiaan komunikasi.

## <a name="prerequisites"></a>Prasyarat

Sebelum organisasi anda boleh menggunakan ciri ramalan, prasyarat berikut mesti dipenuhi:

1. Organisasi anda mempunyai contoh yang [disediakan dalam Microsoft Dataverse dan ia berada dalam organisasi yang sama seperti Wawasan](/ai-builder/build-model#prerequisites) Pelanggan.

2. Persekitaran wawasan khalayak anda dilampirkan pada tika Dataverse anda.

Untuk mendapatkan maklumat lanjut, lihat [Cipta persekitaran baharu](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Cipta ramalan dalam entiti Pelanggan

1. Dalam wawasan khalayak, pergi ke **Data** > **Entiti**.

2. Pilih entiti **Pelanggan**.

3. Dalam **Entiti pelanggan: CustomerInsights**, pilih pada tab **Medan**.

4. Cari nama atribut yang anda ingin ramalkan nilai, kemudian pilih ikon **Gambaran Keseluruhan** dalam lajur **Ringkasan**.
   > [!div class="mx-imgBorder"]
   > ![Ikon gambaran keseluruhan.](media/intelligence-overviewicon.png "Ikon gambaran keseluruhan")

5. Jika terdapat kadar nilai tidak diisi yang tinggi bagi atribut anda, pilih **Ramal nilai yang tidak diisi** untuk meneruskan dengan ramalan anda.
   > [!div class="mx-imgBorder"]
   > ![Status gambaran keseluruhan dengan butang ramalkan nilai yang tidak diisi ditunjukkan.](media/intelligence-overviewpredictmissingvalues.png "Status gambaran keseluruhan dengan butang ramalan nilai hilang ditunjukkan")

6. Sediakan **Nama paparan** dan **Nama entiti output** untuk hasil ramalan.

7. Senarai pra-penuhi bagi pilihan akan menunjukkan di mana anda boleh memetakan nilai untuk kategori diramalkan. Dalam kes ini, pilihan kategori anda hanyalah 0 atau 1 kerana ia memetakan ramalan benar/palsu atau bersifat binari. Dalam lajur Kategori, petakan nilai medan yang anda ingin klasifikasikan sebagai “0” dalam ramalan akhir kepada “0” dan item yang anda ingin klasifikasikan sebagai “1” dalam ramalan akhir kepada “1”.
   > [!div class="mx-imgBorder"]
   > ![Contoh menunjukkan nilai medan yang dipetakan kepada kategori.](media/intelligence-categorymapping.png "Contoh menunjukkan nilai medan yang dipetakan ke kategori")

8. Pilih **Selesai** dan ramalan akan diproses. Pemprosesan akan mengambil sedikit masa, bergantung kepada saiz dan kekompleksan data. Hasil akan tersedia dalam entiti baharu berasaskan pada **Nama entiti output** bagi ramalan yang anda telah ciptakan.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Cipta ramalan semasa mencipta bahagian

Meramalkan nilai yang tidak diisi untuk atribut khusus bagi pilihan juga boleh dilakukan semasa mencipta bahagian. Secara khususnya, apabila anda segera mencipta bahagian berasaskan pada sama ada entiti Pelanggan disatukan anda atau entiti Customer_Measure.

Sebagai sebahagian daripada aliran ini, anda akan memiilih atribut khusus untuk asas bahagian anda seperti Kepuasan Pelanggan atau Amaun Pembelian. Selepas penciptaan bahagian, sistem akan mencadangkan kaedah untuk meramalkan sebarang nilai yang hilang untuk atribut ini.

1. Dalam wawasan khalayak, pergi ke **Segmen** dan pilih jubin **Profil**.

2. Pilih **Medan** untuk mencipta bahagian pada dan pilih **Operator**, kemudian pilih **Semak Semula**.

3. Berikan **Nama** dan **Nama paparan** untuk bahagian.

4. Pilih **Simpan**.

5. Jika bahagian yang baharu anda cipta mempunyai data yang tidak lengkap dalam medan sumber, anda boleh memilih untuk meramalkan nilai yang hilang.
   > [!div class="mx-imgBorder"]
   > ![Butang ramalan.](media/segments-predictoption.png "Butang ramalan")

6. Sediakan **Nama paparan** dan **Nama entiti output** untuk hasil ramalan.

7. Pilih **Selesai**. Ramalan anda akan dijana sebentar lagi dalam entiti baharu dengan nama yang anda sediakan untuk **Nama entiti output**.

## <a name="view-a-prediction"></a>Lihat ramalan

1. Dalam wawasan khalayak, pergi ke **Kecerdasan** > **Ramalan** > **Ramalan saya**.

2. Pilih ramalan yang anda mahu semak semula.

3. Pilih elipsis dalam lajur **Tindakan** dan pilih **Lihat**.

4. Anda akan melihat bilangan titik data dalam pandangan ramalan anda.
   > [!div class="mx-imgBorder"]
   > ![Halaman ramalan.](media/intelligence-predictionsviewpage.png "Halaman ramalan")

   - **Nilai ramalan** menunjukkan pemetaan yang anda cipta semasa peringkat pemetaan nilai Medan ke kategori. Ini ialah nilai dalam set data yang telah dipetakan kepada kategori tertentu.
   -**Pempengaruh teratas** merupakan faktor dalam set data anda yang paling cenderung untuk mempengaruhi keyakinan ramalan bagi nilai Medan anda untuk dipetakan ke kategori tertentu.
   - **Prestasi** menunjukkan bagaimana ramalan dilakukan. Pilih pautan untuk mengetahui dengan lanjut.
   - **Pratonton** menunjukkan sampel output set data daripada ramalan anda dan kebarangkalian, atau keyakinan kita, tentang nilai ramalan yang mana 0 ialah tidak pasti, dan 1 ialah pasti.

## <a name="update-a-prediction"></a>Kemas kini ramalan

1. Dalam wawasan khalayak, pergi ke **Kecerdasan** > **Ramalan** > **Ramalan saya**.

2. Pilih ramalan yang anda mahu kemas kini dan pilih ikon **Kemas Kini**.

3. Ramalan akan dijadualkan untuk pemprosesan. Anda boleh melihat masa kemas kini terakhir dalam lajur **Kemas Kini** di halaman **Ramalan**.

## <a name="edit-a-prediction"></a>Edit ramalan

Selepas anda mencipta ramalan, anda boleh sesuaikan model dalam the AI Builder untuk meningkatkan keberkesanan model anda.  

1. Dalam wawasan khalayak, pergi ke **Kecerdasan** > **Ramalan** > **Ramalan saya**.

2. Pilih ramalan yang anda mahu edit.

3. Pilih elipsis dalam lajur **Tindakan** dan pilih **Lihat**.

4. Pilih **Sesuaikan dalam AI Builder**.

5. Kemas kini model anda dalam AI Builder. [Ketahui lebih lanjut tentang mengurus model dalam AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

Jalanan ramalan anda yang seterusnya akan menggunakan model dikemas kini yang anda cipta.

> [!NOTE]
> Model baharu yang dicipta dalam AI Builder tidak akan dipaparkan dalam wawasan khalayak melainkan model itu dicipta daripada pengalaman yang disenaraikan di atas.

## <a name="remove-a-prediction"></a>Alih keluar ramalan

1. Dalam wawasan khalayak, pergi ke **Kecerdasan** > **Ramalan** > **Ramalan saya**.

2. Pilih ramalan yang anda mahu padam.

3. Pilih elipsis dalam lajur **Tindakan** dan pilih **Padam**.

4. Sahkan pemadaman.

## <a name="troubleshooting"></a>Pencarisilapan

Jika anda tidak dapat melengkapkan proses Dataverse lampirkan disebabkan oleh ralat, anda boleh cuba melengkapkan proses secara manual. Terdapat dua isu diketahui yang boleh berlaku dalam proses lampir:

- Penyelesaian Tambahan Kad Pelanggan tidak dipasang.
    1. Lengkapkan arahan untuk [memasang dan mengkonfigurasi penyelesaian](customer-card-add-in.md).

- Keizinan aplikasi tidak diberikan.
    1. Pergi ke [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Pilih **Persekitaran**.
    1. Pilih elipsis yang bersebelahan dengan persekitaran yang anda mahu tambah keizinan dan pilih **Tetapan**.
    1. Kembangkan **Keizinan + pengguna** dan pilih **Pengguna**.
    1. Pilih **+ Baharu** dan pilih **Pengguna**.
    1. Pilih **Pengguna aplikasi** jika ia belum dipilih dan masukkan maklumat berikut:
        - **Nama Pengguna:** cihelp@microsoft.com
        - **ID Permohonan:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Nama Pertama:** Pelanggan
        - **Nama Akhir:** Insights
        - **E-mel Utama:** cihelp@microsoft.com
    1. Pilih **Simpan & Tutup**.
    1. Pilih pengguna yang anda baru cipta.
    1. Pilih **Urus Peranan** dalam bar menu di atas.
    1. Pilih **Pentadbir Sistem** kemudian pilih **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
