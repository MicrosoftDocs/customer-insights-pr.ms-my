---
title: Eksport data ke Azure Synapse Analytics (pratonton)
description: Ketahui cara mengkonfigurasi sambungan ke Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259855"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Eksport data ke Azure Synapse Analytics (pratonton)

Azure Synapse adalah perkhidmatan analitis yang mempercepatkan masa untuk wawasan merentasi gudang data dan sistem data besar. Anda boleh menginges dan menggunakan data Customer Insights anda dalam [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

> [!NOTE]
> Pastikan untuk menetapkan semua **tugasan peranan** seperti yang diterangkan.

- Dalam Wawasan Pelanggan, akaun pengguna (AD) anda Azure Active Directory mesti mempunyai [peranan Pentadbir](permissions.md#add-users).

Dalam Azure:

- Langganan Azure yang aktif.

- Jika menggunakan akaun Gen2 baharu Azure Data Lake Storage, [prinsipal perkhidmatan untuk Wawasan](connect-service-principal.md) Pelanggan mempunyai **keizinan Penyumbang** Data Blob Storan. Data Lake Storage Gen2 **mesti mempunyai** [ruang nama hierarki](/azure/storage/blobs/data-lake-storage-namespace) didayakan.

- Pada kumpulan sumber tempat Azure Synapse ruang kerja berada, *prinsipal* perkhidmatan dan *Azure AD pengguna dengan keizinan pentadbir dalam Wawasan* Pelanggan mesti diperuntukkan sekurang-kurangnya **keizinan** Pembaca [...](/azure/role-based-access-control/role-assignments-portal).

- Pengguna *Azure AD dengan keizinan pentadbir dalam Wawasan* Pelanggan mempunyai **keizinan Penyumbang** Data Blob Storan pada Azure Data Lake Storage akaun Gen2 tempat data berada dan dipautkan ke Azure Synapse ruang kerja. Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Identiti *[Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* terurus ruang kerja mempunyai **keizinan Penyumbang** Data Blob Storan pada Azure Data Lake Storage akaun Gen2 di mana data berada dan dipautkan ke Azure Synapse ruang kerja. Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Pada ruang kerja, *prinsipal perkhidmatan untuk Wawasan* Pelanggan mempunyai **peranan Pentadbir**[Synapse yang](/azure/synapse-analytics/security/how-to-set-up-access-control) ditugaskan.

- Jika persekitaran Wawasan Pelanggan anda menyimpan data sendiri [Azure Data Lake Storage](own-data-lake-storage.md), pengguna yang menyediakan sambungan untuk Azure Synapse Analytics memerlukan sekurang-kurangnya peranan Pembaca **terbina dalam** pada akaun Storan Tasik Data. Untuk maklumat lanjut, lihat [Tugaskan peranan Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="set-up-connection-to-azure-synapse"></a>Sediakan sambungan ke Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Azure Synapse Analytics**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih atau cari langganan yang anda mahu menggunakan data Customer Insights. Sebaik sahaja langganan dipilih, anda boleh memilih **Ruang kerja**, **Akaun storan** dan **Bekas**.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)] Untuk mengkonfigurasikan eksport dengan sambungan dikongsi, anda memerlukan sekurang-kurangnya **keizinan Penyumbang** dalam Wawasan Pelanggan.

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. **Dalam medan Sambungan untuk eksport**, pilih sambungan daripada Azure Synapse Analytics seksyen. Hubungi pentadbir jika tiada sambungan tersedia.

1. Sediakan **Nama paparan** yang dikenali untuk eksport dan **Nama pangkalan data** anda. Eksport akan mewujudkan pangkalan data [Azure Synapse tasik baru](/azure/synapse-analytics/database-designer/concepts-lake-database) dalam ruang kerja yang ditakrifkan dalam sambungan.

1. Pilih entiti yang anda mahu eksport Azure Synapse Analytics.
   > [!NOTE]
   > Sumber data berdasarkan [folder Common Data Model](connect-common-data-model.md) tidak disokong.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Untuk bertanya data yang dieksport ke Synapse Analytics, anda memerlukan **akses Pembaca** Data Blob Storan ke storan destinasi pada ruang kerja eksport.

## <a name="update-an-export"></a>Kemas kini eksport

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Edit** pada eksport yang anda mahu kemas kini.

   - **Tambah** atau **Alih Keluar** entiti daripada pemilihan. Jika entiti dialih keluar daripada pilihan, entiti tidak dipadamkan daripada pangkalan data Synapse Analytics. Walau bagaimanapun, penyegaran semula data masa akan datang tidak akan mengemas kini entiti yang dialih keluar dalam pangkalan data itu.

   - **Mengubah Nama Pangkalan Data** mencipta pangkalan data Synapse Analytics baharu. Pangkalan data dengan nama yang dikonfigurasikan sebelum ini tidak akan menerima sebarang kemas kini dalam penyegaran semula masa akan datang.

[!INCLUDE [footer-include](includes/footer-banner.md)]
