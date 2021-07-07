---
title: Cipta dan urus persekitaran
description: Ketahui cara untuk mendaftar untuk perkhidmatan dan cara untuk menguruskan persekitaran.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304891"
---
# <a name="manage-environments"></a>Urus persekitaran

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Artikel ini menerangkan cara untuk mencipta organisasi baharu dan cara untuk memperuntukkan persekitaran.

## <a name="sign-up-and-create-an-organization"></a>Daftar dan cipta organisasi

1. Pergi ke laman web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Pilih **Mulakan**.

3. Pilih senario pendaftaran pilihan anda dan pilih pautan berkaitan.

4. Terima terma dan syarat dan pilih **Teruskan** untuk mula mencipta organisasi.

5. Selepas persekitaran dicipta, anda akan dihalakan semula ke [Customer Insights](https://home.ci.ai.dynamics.com).

6. Gunakan persekitaran demo untuk meneroka aplikasi atau mencipta persekitaran baharu dengan mengikuti langkah dalam bahagian seterusnya.

7. Selepas menentukan tetapan persekitaran, pilih **Cipta**.

8. Anda akan dilog masuk selepas persekitaran dicipta dengan jayanya.

## <a name="create-an-environment-in-an-existing-organization"></a>Cipta persekitaran dalam organisasi sedia ada

Terdapat dua cara untuk mencipta persekitaran baharu. Anda boleh sama ada menentukan konfigurasi baharu secara keseluruhan atau anda boleh menyalin beberapa tetapan konfigurasi daripada persekitaran sedia ada.

> [!NOTE]
> Organisasi boleh mencipta *dua* persekitaran untuk setiap lesen Customer Insights. Jika organisasi anda membeli lebih daripada satu lesen, sila [hubungi pasukan sokongan kami](https://go.microsoft.com/fwlink/?linkid=2079641) untuk meningkatkan bilangan persekitaran yang tersedia. Untuk maklumat lanjut mengenai kapasiti dan kapasiti tambahan, muat turun [panduan pelesenan Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Untuk mencipta persekitaran:

1. Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

1. Pilih **Baharu**.

   > [!div class="mx-imgBorder"]
   > ![Tetapan persekitaran.](media/environment-settings-dialog.png)

1. Dalam dialog **Cipta persekitaran**, pilih **Persekitaran Baharu**.

   Jika anda mahu [menyalin data daripada persekitaran semasa](#considerations-for-copy-configuration-preview), pilih **Salin daripada persekitaran sedia ada**. Anda akan melihat semua persekitaran yang tersedia dalam organisasi anda yang boleh anda salin data daripadanya.

1. Sediakan butiran berikut:
   - **Nama**: Nama untuk persekitaran ini. Medan ini sudah diisikan jika anda telah menyalin persekitaran sedia ada tetapi anda boleh mengubahnya.
   - **Jenis**: Pilih sama ada anda mahu mencipta persekitaran Pengeluaran atau Kotak Pasir.
   - **Rantau**: Rantau yang perkhidmatan diatur letak dan dihoskan di dalamnya.
   
1. Secara pilihan, anda boleh memilih **Tetapan lanjutan**:

   - **Simpan semua data pada**: Menentukan tempat anda mahu menyimpan data keluaran yang dijanakan daripada Customer Insights. Anda akan mempunyai dua pilihan: **Storan persekitaran** (Azure Data Lake  yang diuruskan oleh pasukan Customer Insights) dan **Azure Data Lake Storage** (Azure Data Lake Storage anda sendiri). Secara lalai, pilihan storan Customer Insights dipilih.

     > [!NOTE]
     > Dengan menyimpan data di Azure Data Lake Storage, anda bersetuju bahawa data akan dipindahkan dan disimpan di lokasi geografi yang sesuai untuk akaun storan Azure tersebut, yang mungkin berbeza daripada lokasi data yang disimpan dalam Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat Amanah Microsoft.](https://www.microsoft.com/trust-center)
     >
     > Pada masa ini, entiti yang diinges sentiasa disimpan dalam Customer Insights yang Diuruskan oleh Data Lake. 
     > 
     > Kami menyokong akaun Azure Data Lake Storage sahaja dari rantau Azure yang sama yang anda pilih semasa mencipta persekitaran. 
     > 
     > Kami menyokong akaun Azure Data Lake Storage sahaja yang mempunyai ruang nama berhierarki didayakan.


   - Untuk pilihan Azure Data Lake Storage, anda boleh memilih antara pilihan berasaskan sumber dan pilihan berasaskan langganan untuk pengesahan. Untuk maklumat lanjut, lihat [Sambungkan cerapan khalayak ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure](connect-service-principal.md). Nama **Bekas** tidak boleh ditukar dan akan menjadi `customerinsights`.
   
   - Jika anda ingin menggunakan [ramalan](predictions.md), konfigurasikan perkongsian data dengan Microsoft Dataverse atau dayakan pengingesan data daripada sumber data di premis, sediakan URL persekitaran Microsoft Dataverse di bawah **Konfigurasi perkongsian data dengan Microsoft Dataverse dan dayakan keupayaan tambahan**. Pilih **Dayakan perkongsian data** untuk berkongsi data output Customer Insights dengan Microsoft Dataverse Data Lake Terurus.

     > [!NOTE]
     > - Perkongsian data dengan Microsoft Dataverse Data Lake Terurus pada masa ini tidak disokong apabila anda menyimpan semua data ke Azure Data Lake Storage anda sendiri.
     > - [Ramalan nilai hilang dalam entiti](predictions.md) tidak disokong buat masa ini apabila anda mendayakan perkongsian data dengan Microsoft Dataverse Data Lake Terurus.

     > [!div class="mx-imgBorder"]
     > ![Pilihan konfigurasi untuk mendayakan perkongsian data dengan Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)

   Apabila anda menjalankan proses, seperti pengingesan data atau penciptaan segmen, folder yang berkaitan akan dicipta dalam akaun storan yang anda tentukan di atas. Fail data dan fail model.json akan dicipta dan ditambah pada folder berdasarkan nama proses.

   Jika anda mencipta berbilang persekitaran Customer Insights dan memilih untuk menyimpan entiti output daripada persekitaran tersebut dalam akaun storan anda, folder berasingan akan dicipta untuk setiap persekitaran dengan ci_<environmentid> dalam container.

### <a name="considerations-for-copy-configuration-preview"></a>Pertimbangan untuk konfigurasi salinan (pratonton)

Tetapan konfigurasi berikut disalin:

- Konfigurasi ciri
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

Tetapan konfigurasi berikut *tidak* disalin:

- Profil pelanggan.
- Kelayakan sumber data. Anda perlu menyediakan kelayakan untuk setiap sumber data dan menyegarkan semula sumber data secara manual.
- Sumber data daripada folder Common Data Model dan Dataverse diuruskan oleh Data Lake. Anda perlu mencipta sumber data secara manual tersebut dengan nama yang sama seperti dalam persekitaran sumber.

Apabila anda menyalin persekitaran, anda akan melihat mesej pengesahan bahawa persekitaran baharu telah dicipta. Pilih **Pergi ke sumber data** untuk melihat senarai sumber data.

Semua sumber data akan menunjukkan status **Kelayakan Diperlukan**. Edit sumber data dan masukkan kelayakan untuk menyegarkan semula.

> [!div class="mx-imgBorder"]
> ![Sumber data disalin.](media/data-sources-copied.png)

Selepas menyegar semula sumber data, pergi ke **Data** > **Satukan**. Di sini anda akan menemui tetapan daripada persekitaran sumber. Mengeditnya seperti yang diperlukan atau pilih **Jalankan** untuk memulakan proses data penyatuan dan mencipta entiti pelanggan disatukan.

Apabila data penyatuan selesai, pergi ke **Langkah-langkah** dan **Segmen** untuk menyegarkan semula juga.

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
   > - [Ramalan nilai yang hilang dalam entiti](predictions.md) pada masa ini tidak disokong apabila anda mendayakan perkongsian data dengan Data Lake Terurus Microsoft Dataverse.

   Selepas mendayakan perkongsian data dengan Microsoft Dataverse, segar semula sepenuhnya sumber data anda dan proses lain akan bermula. Jika proses sedang berjalan, anda tidak melihat pilihan untuk mendayakan perkongsian data dengan Microsoft Dataverse. Tunggu sehingga proses tersebut selesai atau batalkan proses untuk mendayakan perkongsian data. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Pilihan konfigurasi untuk mendayakan perkongsian data dengan Microsoft Dataverse.":::
   
   Apabila anda menjalankan proses, seperti pengingesan data atau penciptaan segmen, folder yang berkaitan akan dicipta dalam akaun storan yang anda tentukan di atas. Fail data dan fail model.json akan dicipta dan ditambah pada subfolder yang berkenaan, bergantung pada proses yang anda jalankan.

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
