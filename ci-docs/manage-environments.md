---
title: Cipta dan urus persekitaran
description: Ketahui cara untuk mendaftar untuk perkhidmatan dan cara untuk menguruskan persekitaran.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fcdb7f073ff73322ff69d0a8684391819a809d00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643614"
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

Sediakan persekitaran anda sendiri Microsoft Dataverse untuk berkongsi data (profil dan cerapan) dengan aplikasi perniagaan berdasarkan Dataverse, seperti Dynamics 365 Marketing atau aplikasi berpandukan model dalam Power Apps.

Untuk menggunakan [model ramalan di luar kotak](predictions-overview.md#out-of-box-models), konfigurasikan perkongsian data dengan Dataverse. Atau anda boleh mendayakan penginjesan data daripada sumber data di premis, menyediakan URL persekitaran Microsoft Dataverse yang mentadbir organisasi anda.

Mendayakan perkongsian data dengan Microsoft Dataverse memilih kotak semak perkongsian data akan mencetuskan segar semula penuh sekali sumber data anda dan semua proses lain.

> [!IMPORTANT]
> 1. Wawasan Pelanggan dan Dataverse perlu berada di rantau yang sama untuk mendayakan perkongsian data.
> 1. Anda mesti mempunyai peranan pentadbir global dalam Dataverse persekitaran. Sahkan sama ada persekitaran ini [Dataverse dikaitkan dengan](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) kumpulan keselamatan tertentu dan pastikan anda ditambahkan pada kumpulan keselamatan tersebut.
> 1. Tiada persekitaran Wawasan Pelanggan sedia ada yang telah dikaitkan dengan Dataverse persekitaran tersebut. Ketahui cara mengalih [keluar sambungan sedia ada ke Dataverse persekitaran](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Pilihan konfigurasi untuk mendayakan perkongsian data dengan Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Mendayakan perkongsian data dengan Dataverse daripada anda sendiri Azure Data Lake Storage (Pratonton)

Jika persekitaran anda dikonfigurasikan untuk menggunakan anda sendiri Azure Data Lake Storage untuk menyimpan data Wawasan Pelanggan, mendayakan perkongsian data dengan Microsoft Dataverse memerlukan beberapa konfigurasi tambahan.

1. Cipta dua kumpulan keselamatan pada langganan Azure anda - satu **kumpulan keselamatan Pembaca** dan satu **kumpulan keselamatan Penyumbang** dan tetapkan Microsoft Dataverse perkhidmatan sebagai pemilik untuk kedua-dua kumpulan keselamatan.
2. Urus Senarai Kawalan Akses (ACL) pada bekas CustomerInsights dalam akaun storan anda melalui kumpulan keselamatan ini. Microsoft Dataverse Tambahkan perkhidmatan dan sebarang Dataverse aplikasi perniagaan berasaskan seperti Dynamics 365 Marketing kepada **kumpulan keselamatan Pembaca** dengan **keizinan baca sahaja**. Tambah *hanya* aplikasi Wawasan Pelanggan kepada **kumpulan keselamatan Penyumbang** untuk memberikan kedua-dua **keizinan baca dan tulis** untuk menulis profil dan cerapan.
   
#### <a name="prerequisites"></a>Prasyarat

Untuk melaksanakan skrip PowerShell, anda perlu mengimport tiga modul berikut. 

1. Pasang versi [Azure Active Directory terkini PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. Pada PC anda, pilih kekunci Windows pada papan kekunci anda dan cari untuk **Windows PowerShell** dan pilih **Jalankan sebagai pentadbir**.
   1. Dalam tetingkap PowerShell yang terbuka, masukkan `Install-Module AzureAD`.
2. Import tiga modul.
    1. Dalam tetingkap PowerShell, masukkan `Install-Module -Name Az.Accounts` dan ikuti langkah-langkah. 
    1. Ulangi untuk `Install-Module -Name Az.Resources` dan `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Langkah konfigurasi

1. Muat turun dua skrip PowerShell yang perlu anda jalankan dari repo [GitHub jurutera](https://github.com/trin-msft/byol) kami.
    1. `CreateSecurityGroups.ps1`
       - Anda memerlukan *keizinan pentadbir* penyewa untuk menjalankan skrip PowerShell ini. 
       - Skrip PowerShell ini mencipta dua kumpulan keselamatan pada langganan Azure anda. Satu untuk kumpulan Pembaca dan satu lagi untuk kumpulan Penyumbang dan akan menjadikan Microsoft Dataverse perkhidmatan sebagai pemilik untuk kedua-dua kumpulan keselamatan ini.
       - Laksanakan skrip PowerShell ini dalam Windows PowerShell dengan menyediakan ID langganan Azure yang mengandungi .Azure Data Lake Storage Buka skrip PowerShell dalam editor untuk menyemak maklumat tambahan dan logik yang dilaksanakan.
       - Simpan kedua-dua nilai ID kumpulan keselamatan yang dijana oleh skrip ini kerana kami akan menggunakannya dalam `ByolSetup.ps1` skrip.
       
        > [!NOTE]
        > Penciptaan kumpulan keselamatan boleh dilumpuhkan pada penyewa anda. Dalam kes itu, persediaan manual diperlukan dan pentadbir anda Azure AD perlu [mendayakan penciptaan](/azure/active-directory/enterprise-users/groups-self-service-management) kumpulan keselamatan.

    2. `ByolSetup.ps1`
        - Anda memerlukan *keizinan Pemilik* Data Blob Storan pada tahap akaun storan/bekas untuk menjalankan skrip ini atau skrip ini akan mencipta satu untuk anda. Tugasan peranan anda boleh dialih keluar secara manual selepas berjaya menjalankan skrip.
        - Skrip PowerShell ini menambah kawalan akses berasaskan tole (RBAC) yang diperlukan untuk Microsoft Dataverse perkhidmatan dan sebarang Dataverse aplikasi perniagaan berasaskan. Ia juga mengemas kini Senarai Kawalan Akses (ACL) pada bekas CustomerInsights untuk kumpulan keselamatan yang `CreateSecurityGroups.ps1` dicipta dengan skrip. Kumpulan Penyumbang akan mempunyai *keizinan rwx* dan kumpulan Pembaca akan mempunyai *keizinan r-x* sahaja.
        - Laksanakan skrip PowerShell ini dalam Windows PowerShell dengan menyediakan ID langganan Azure yang mengandungi nama akaun storan anda Azure Data Lake Storage, nama kumpulan sumber, dan nilai id kumpulan keselamatan Pembaca dan Penyumbang. Buka skrip PowerShell dalam editor untuk menyemak maklumat tambahan dan logik yang dilaksanakan.
        - Salin rentetan output selepas berjaya menjalankan skrip. Rentetan output kelihatan seperti ini: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Masukkan rentetan output yang disalin dari atas ke dalam **medan Pengecam** keizinan langkah konfigurasi persekitaran untuk Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Pilihan konfigurasi untuk membolehkan perkongsian data daripada anda sendiri Azure Data Lake Storage dengan Microsoft Dataverse.":::

Customer Insights tidak menyokong senario perkongsian data berikut:
- Jika anda mendayakan perkongsian data dengan Dataverse, anda tidak akan dapat [mencipta nilai yang diramalkan atau hilang dalam entiti](predictions.md).
- Jika anda mendayakan perkongsian data dengan Dataverse, anda tidak akan dapat melihat sebarang laporan Terbenam PowerBI pilihan dalam persekitaran Wawasan Pelanggan anda.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Mengalih keluar sambungan sedia ada ke Dataverse persekitaran

Apabila menyambung ke Dataverse persekitaran, mesej **ralat Organisasi CDS ini telah dilampirkan pada contoh** Wawasan Pelanggan yang Dataverse lain bermakna persekitaran telah digunakan dalam persekitaran Wawasan Pelanggan. Anda boleh mengalih keluar sambungan sedia ada sebagai pentadbir global pada Dataverse persekitaran. Ia boleh mengambil masa beberapa jam untuk mengisi perubahan.

1. Pergi ke [Power Apps](https://make.powerapps.com).
1. Pilih persekitaran daripada pemilih persekitaran.
1. Pergi ke **Penyelesaian**
1. Nyahpasang atau padamkan penyelesaian bernama **Dynamics 365 Customer Insights Tambahan Kad Pelanggan (Pratonton)**.

ATAU 

1. Buka persekitaran anda Dataverse.
1. Pergi ke **Tetapan** > **LanjutanSolutions**.
1. **Nyahpasang penyelesaian CustomerInsightsCustomerCard**.

## <a name="copy-the-environment-configuration"></a>Salin konfigurasi persekitaran

Sebagai pentadbir, anda boleh memilih untuk menyalin konfigurasi daripada persekitaran sedia ada apabila anda mencipta konfigurasi baharu. 

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

## <a name="set-up-a-copied-environment"></a>Sediakan persekitaran yang disalin

Apabila anda menyalin konfigurasi persekitaran, data *berikut tidak* disalin:

- Profil pelanggan.
- Kelayakan sumber data. Anda perlu menyediakan kelayakan untuk setiap sumber data dan menyegarkan semula sumber data secara manual.
- Sumber data daripada folder Common Data Model dan danau data terurus Dataverse. Anda perlu mencipta sumber data secara manual tersebut dengan nama yang sama seperti dalam persekitaran sumber.
- Rahsia sambungan yang digunakan untuk eksport dan pengayaan. Anda perlu membenarkan semula sambungan dan kemudian mengaktifkan semula pengayaan dan eksport. 

Apabila anda menyalin persekitaran, anda akan melihat mesej pengesahan bahawa persekitaran baharu telah dicipta. Pilih **Pergi ke sumber data** untuk melihat senarai sumber data.

Semua sumber data akan menunjukkan status **Kelayakan Diperlukan**. Edit sumber data dan masukkan kelayakan untuk menyegarkan semula.

:::image type="content" source="media/data-sources-copied.png" alt-text="Senarai sumber data yang telah disalin dan memerlukan pengesahan.":::

Selepas menyegar semula sumber data, pergi ke **Data** > **Satukan**. Di sini anda akan menemui tetapan daripada persekitaran sumber. Mengeditnya seperti yang diperlukan atau pilih **Jalankan** untuk memulakan proses data penyatuan dan mencipta entiti pelanggan disatukan.

Apabila data penyatuan selesai, pergi ke **Langkah-langkah** dan **Segmen** untuk menyegarkan semula juga.

Sebelum anda mengaktifkan semula eksport dan pengayaan, pergi ke **AdminConnections** > **untuk** membenarkan semula sambungan dalam persekitaran baharu anda.

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

> [!NOTE]
> Memadam persekitaran tidak mengalih keluar perkaitan kepada Dataverse persekitaran. Ketahui cara mengalih [keluar sambungan sedia ada ke Dataverse persekitaran](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE [footer-include](includes/footer-banner.md)]
