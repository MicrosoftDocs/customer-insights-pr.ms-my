---
title: Cipta dan urus persekitaran
description: Ketahui cara untuk mendaftar untuk perkhidmatan dan cara untuk menguruskan persekitaran.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683484"
---
# <a name="manage-environments"></a>Urus persekitaran

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Tukar persekitaran

Pilih kawalan **Persekitaran** pada sudut kanan atas halaman untuk mengubah persekitaran.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Syot layar kawalan untuk menukar persekitaran.":::

Pentadbir boleh [mencipta](get-started-paid.md) dan menguruskan persekitaran.

## <a name="edit-an-existing-environment"></a>Edit persekitaran sedia ada

Anda boleh mengedit beberapa butiran persekitaran sedia ada.

1.  Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

2.  Pilih ikon **Edit**.

3. Dalam kotak **Edit persekitaran**, anda boleh mengemas kini **Nama paparan**, tetapi anda tidak boleh menukar **Rantau** atau **Jenis**.

4. Jika persekitaran dikonfigurasikan untuk menyimpan data dalam Azure Data Lake Storage, anda boleh mengemas kini **Kunci akaun**. Walau bagaimanapun, anda tidak boleh mengubah **Nama akaun** atau nama **Bekas**.

5. Secara pilihan, anda boleh mengemas kini daripada sambungan berasaskan kunci akaun kepada sambungan berasaskan sumber atau berasaskan langganan. Sebaik sahaja dinaik taraf, anda tidak boleh kembali kepada kunci akaun selepas kemas kini. Untuk maklumat lanjut, lihat [Sambungkan cerapan khalayak ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure](connect-service-principal.md). Anda tidak boleh mengubah maklumat **Bekas** semasa mengemas kini sambungan.

6. Selain itu, anda boleh menyediakan URL persekitaran Microsoft Dataverse di bawah **Konfigurasikan perkongsian data Microsoft Dataverse dan dayakan keupayaan tambahan**. Keupayaan ini termasuk perkongsian data dengan aplikasi dan penyelesaian berdasarkan Microsoft Dataverse, pengingesan data daripada sumber data di premis atau penggunaan [ramalan](predictions.md). Pilih **Dayakan perkongsian data** untuk berkongsi data output Customer Insights dengan Data Lake Terurus Microsoft Dataverse.

   > [!NOTE]
   > - Perkongsian data dengan Microsoft Dataverse Data Lake Terurus pada masa ini tidak disokong apabila anda menyimpan semua data ke Azure Data Lake Storage anda sendiri.
   > - [Ramalan nilai yang hilang dalam entiti](predictions.md) dan laporan Terbenam PowerBI dalam cerapan khalayak (jika didayakan pada persekitaran anda) pada masa ini tidak disokong apabila anda mendayakan perkongsian data dengan danau data yang diuruskan oleh Microsoft Dataverse.

   Selepas mendayakan perkongsian data dengan Microsoft Dataverse, segar semula sepenuhnya sumber data anda dan proses lain akan bermula. Jika proses sedang berjalan, anda tidak melihat pilihan untuk mendayakan perkongsian data dengan Microsoft Dataverse. Tunggu sehingga proses tersebut selesai atau batalkan proses untuk mendayakan perkongsian data. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Pilihan konfigurasi untuk mendayakan perkongsian data dengan Microsoft Dataverse.":::
   
   Apabila anda menjalankan proses, seperti pengingesan data atau penciptaan segmen, folder yang berkaitan akan dicipta dalam akaun storan yang anda tentukan di atas. Fail data dan fail model.json akan dicipta dan ditambah pada subfolder yang berkenaan, bergantung pada proses yang anda jalankan.

## <a name="copy-the-environment-configuration"></a>Salin konfigurasi persekitaran

Apabila anda mencipta persekitaran baharu, anda boleh memilih untuk menyalin konfigurasi daripada persekitaran sedia ada. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Syot layar pilihan tetapan dalam tetapan persekitaran.":::

Anda akan melihat semua persekitaran yang tersedia dalam organisasi anda yang boleh anda salin data daripadanya.

Tetapan konfigurasi berikut disalin:

- Sumber data yang diingeskan/diimport
- Konfigurasi penyatuan data (Peta, Padan, Cantum)
- Bahagian
- Langkah
- Perhubungan
- Aktiviti
- Cari & Indeks penapis
- Destinasi eksport
- Segar semula dijadualkan
- Pengayaan
- Pengurusan model
- Penugasan peranan

Data berikut *tidak* disalin:

- Profil pelanggan.
- Kelayakan sumber data. Anda perlu menyediakan kelayakan untuk setiap sumber data dan menyegarkan semula sumber data secara manual.
- Sumber data daripada folder Common Data Model dan Dataverse diuruskan oleh Data Lake. Anda perlu mencipta sumber data secara manual tersebut dengan nama yang sama seperti dalam persekitaran sumber.

Apabila anda menyalin persekitaran, anda akan melihat mesej pengesahan bahawa persekitaran baharu telah dicipta. Pilih **Pergi ke sumber data** untuk melihat senarai sumber data.

Semua sumber data akan menunjukkan status **Kelayakan Diperlukan**. Edit sumber data dan masukkan kelayakan untuk menyegarkan semula.

:::image type="content" source="media/data-sources-copied.png" alt-text="Senarai sumber data yang telah disalin dan memerlukan pengesahan.":::

Selepas menyegar semula sumber data, pergi ke **Data** > **Satukan**. Di sini anda akan menemui tetapan daripada persekitaran sumber. Mengeditnya seperti yang diperlukan atau pilih **Jalankan** untuk memulakan proses data penyatuan dan mencipta entiti pelanggan disatukan.

Apabila data penyatuan selesai, pergi ke **Langkah-langkah** dan **Segmen** untuk menyegarkan semula juga.

## <a name="reset-an-existing-environment"></a>Tetap semula persekitaran sedia ada

Sebagai pentadbir, anda boleh menetapkan semula persekitaran kepada keadaan kosong jika anda mahu memadam semua konfigurasi dan mengalih keluar data yang diinges.

1.  Pilih pemilih **Persekitaran** dalam pengepala aplikasi. 

2.  Pilih persekitaran yang mahu anda tetapkan semula dan pilih elipsis (**...**). 

3. Pilih pilihan **Tetap semula**. 

4.  Untuk mengesahkan pemadaman, masukkan nama persekitaran dan pilih **Tetap semula**.

## <a name="delete-an-existing-environment"></a>Padam persekitaran sedia ada

Sebagai pentadbir, anda boleh memadamkan persekitaran yang anda tadbir.

1.  Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

2.  Pilih persekitaran yang mahu anda tetapkan semula dan pilih elipsis (**...**). 

3. Pilih pilihan **Padam**. 

4.  Untuk mengesahkan pemadaman, masukkan nama persekitaran dan pilih **Padam**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
