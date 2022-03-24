---
title: Cipta dan urus persekitaran
description: Ketahui cara untuk mendaftar untuk perkhidmatan dan cara untuk menguruskan persekitaran.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376887"
---
# <a name="manage-environments"></a>Urus persekitaran

## <a name="switch-environments"></a>Tukar persekitaran

Pilih kawalan **Persekitaran** pada sudut kanan atas halaman untuk mengubah persekitaran.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Syot layar kawalan untuk menukar persekitaran.":::

Pentadbir boleh [mencipta](create-environment.md) dan menguruskan persekitaran.

## <a name="edit-an-existing-environment"></a>Edit persekitaran sedia ada

Anda boleh mengedit beberapa butiran persekitaran sedia ada.

1.  Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

2.  Pilih ikon **Edit**.

3. Dalam kotak **Edit persekitaran**, anda boleh mengemas kini tetapan persekitaran.

Untuk mendapatkan maklumat lanjut tentang tetapan persekitaran, lihat [Cipta persekitaran baharu](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Sambung ke Microsoft Dataverse
   
Langkah **Microsoft Dataverse** ini membolehkan anda menyambungkan Customer Insights dengan persekitaran Dataverse anda.

Untuk menggunakan [model ramalan di luar kotak](predictions-overview.md#out-of-box-models), konfigurasikan perkongsian data dengan Dataverse. Atau anda boleh mendayakan penginjesan data daripada sumber data di premis, menyediakan URL persekitaran Microsoft Dataverse yang mentadbir organisasi anda.

> [!IMPORTANT]
> Wawasan Pelanggan dan Dataverse perlu berada di rantau yang sama untuk mendayakan perkongsian data.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Pilihan konfigurasi untuk mendayakan perkongsian data dengan Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights tidak menyokong senario perkongsian data berikut:
> - Jika anda menyimpan semua data kepada Azure Data Lake Storage anda sendiri anda tidak akan dapat mendayakan perkongsian data dengan danau data terurus Dataverse.
> - Jika anda mendayakan perkongsian data dengan Dataverse, anda tidak akan dapat [mencipta nilai yang diramalkan atau hilang dalam entiti](predictions.md).

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

- Sumber data daripada folder Common Data Model dan danau data terurus Dataverse. Anda perlu mencipta sumber data secara manual tersebut dengan nama yang sama seperti dalam persekitaran sumber.

Apabila anda menyalin persekitaran, anda akan melihat mesej pengesahan bahawa persekitaran baharu telah dicipta. Pilih **Pergi ke sumber data** untuk melihat senarai sumber data.

Semua sumber data akan menunjukkan status **Kelayakan Diperlukan**. Edit sumber data dan masukkan kelayakan untuk menyegarkan semula.

:::image type="content" source="media/data-sources-copied.png" alt-text="Senarai sumber data yang telah disalin dan memerlukan pengesahan.":::

Selepas menyegar semula sumber data, pergi ke **Data** > **Satukan**. Di sini anda akan menemui tetapan daripada persekitaran sumber. Mengeditnya seperti yang diperlukan atau pilih **Jalankan** untuk memulakan proses data penyatuan dan mencipta entiti pelanggan disatukan.

Apabila data penyatuan selesai, pergi ke **Langkah-langkah** dan **Segmen** untuk menyegarkan semula juga.

## <a name="change-the-owner-of-an-environment"></a>Tukar pemilik persekitaran

Walaupun beberapa pengguna boleh mempunyai keizinan pentadbir dalam Wawasan Pelanggan, hanya satu pengguna adalah pemilik persekitaran. Secara lalai, pentadbir yang mencipta persekitaran pada mulanya. Sebagai pentadbir persekitaran, anda boleh memperuntukkan pemilikan kepada pengguna lain dengan keizinan pentadbir.

1. Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

1. Pilih ikon **Edit**.

1. **Dalam kotak Edit persekitaran**, pergi ke **langkah Maklumat** asas.

1. **Dalam medan Tukar pemilik persekitaran**, pilih pemilik baru persekitaran.  

1. Pilih **Semak semula dan selesaikan**, kemudian **Kemas kini** untuk menggunakan perubahan. 

## <a name="claim-ownership-of-an-environment"></a>Menuntut pemilikan persekitaran

Jika pemilik persekitaran meninggalkan organisasi atau akaun pengguna mereka dipadamkan, persekitaran tidak akan mempunyai pemilik. Pengguna dengan keizinan pentadbir boleh menuntut pemilikan dan menjadi pemilik baru. Mereka boleh terus memiliki persekitaran atau [menukar pemilikan kepada pentadbir](#change-the-owner-of-an-environment) lain. 

Untuk menuntut pemilikan, pilih **butang Ambil pemilikan** yang ditunjukkan di bahagian atas setiap halaman dalam Wawasan Pelanggan apabila pemilik asal meninggalkan organisasi.

## <a name="reset-an-existing-environment"></a>Tetap semula persekitaran sedia ada

Sebagai pemilik persekitaran, anda boleh menetapkan semula persekitaran kepada keadaan kosong jika anda ingin memadamkan semua konfigurasi dan mengalih keluar data yang ditelan.

1.  Pilih pemilih **Persekitaran** dalam pengepala aplikasi. 

2.  Pilih persekitaran yang mahu anda tetapkan semula dan pilih elipsis (**...**). 

3. Pilih pilihan **Tetap semula**. 

4.  Untuk mengesahkan pemadaman, masukkan nama persekitaran dan pilih **Tetap semula**.

## <a name="delete-an-existing-environment"></a>Padam persekitaran sedia ada

Sebagai pemilik persekitaran, anda boleh memadamkan persekitaran yang anda tadbir.

1.  Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

2.  Pilih persekitaran yang mahu anda tetapkan semula dan pilih elipsis (**...**). 

3. Pilih pilihan **Padam**. 

4.  Untuk mengesahkan pemadaman, masukkan nama persekitaran dan pilih **Padam**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
