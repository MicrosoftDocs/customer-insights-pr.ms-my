---
title: Eksport Data Customer Insights ke Azure Synapse Analytics
description: Ketahui cara mengkonfigurasi sambungan ke Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e77227e1e353c02cfb13e26a8ecbe0768ba6c0fa
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643164"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Eksport data ke Azure Synapse Analytics (Pratonton)

Azure Synapse adalah perkhidmatan analitis yang mempercepatkan masa untuk wawasan merentasi gudang data dan sistem data besar. Anda boleh menginges dan menggunakan data Customer Insights anda dalam [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

Prasyarat berikut mesti dipenuhi untuk mengkonfigurasi sambungan daripada Customer Insights ke Azure Synapse.

> [!NOTE]
> Pastikan untuk menetapkan semua **tugasan peranan** seperti yang diterangkan.  

## <a name="prerequisites-in-customer-insights"></a>Prasyarat dalam Customer Insights

* Akaun pengguna (AD) anda Azure Active Directory mempunyai **peranan Pentadbir** dalam Wawasan Pelanggan. Ketahui lebih lanjut tentang [mengesetkan keizinan pengguna](permissions.md#assign-roles-and-permissions).

Dalam Azure: 

- Langganan Azure yang aktif.

- Jika menggunakan akaun Gen2 baharu Azure Data Lake Storage, *prinsipal perkhidmatan untuk Wawasan* Pelanggan memerlukan **keizinan Penyumbang** Data Blob Storan. Ketahui lanjut tentang [menyambung ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure untuk wawasan khalayak](connect-service-principal.md). Data Lake Storage Gen2 **mesti mempunyai** [ruang nama hierarki](/azure/storage/blobs/data-lake-storage-namespace) didayakan.

- Pada kumpulan sumber di mana Azure Synapse ruang kerja berada, *prinsipal* perkhidmatan dan *Azure AD pengguna dengan keizinan pentadbir dalam Wawasan* Pelanggan perlu diperuntukkan sekurang-kurangnya **keizinan Pembaca**. Untuk maklumat lanjut, lihat [Tugaskan peranan Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

- Pengguna *Azure AD dengan keizinan pentadbir dalam Wawasan* Pelanggan memerlukan **keizinan Penyumbang** Data Blob Storan pada Azure Data Lake Storage akaun Gen2 di mana data berada dan dipautkan ke Azure Synapse ruang kerja. Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identiti terurus ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan keizinan **Penyumbang Data Blob Storan** pada akaun Azure Data Lake Storage Gen2 tempat data diletak dan dipaut ke ruang kerja Azure Synapse. Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Pada ruang kerja, *prinsipal perkhidmatan untuk Wawasan* Pelanggan memerlukan **peranan Pentadbir** Sinapse yang diberikan. Untuk maklumat lanjut, lihat [Cara menyediakan kawalan akses untuk ruang kerja Synapse anda](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Sediakan sambungan dan eksport ke Azure Synapse

### <a name="configure-a-connection"></a>Konfigurasikan sambungan

Untuk mencipta sambungan, prinsipal perkhidmatan dan akaun pengguna dalam Wawasan Pelanggan memerlukan **keizinan Pembaca** pada *kumpulan* sumber di mana ruang kerja Synapse Analytics terletak. Selain itu, prinsipal perkhidmatan dan pengguna di ruang kerja Synapse Analytics memerlukan **kebenaran Pentadbir** Synapse. 

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Azure Synapse Analytics** atau pilih **Sediakan** pada **Azure Synapse Analytics** jubin untuk mengkonfigurasi sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan Nama paparan. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih atau cari langganan yang anda mahu menggunakan data Customer Insights. Sebaik sahaja langganan dipilih, anda boleh memilih **Ruang kerja**, **Akaun storan** dan **Bekas**.

1. Pilih **Simpan** untuk menyimpan sambungan.

### <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk mengkonfigurasi eksport dengan sambungan kongsi, anda memerlukan sekurang-kurangnya **keizinan Penyumbang** dalam Wawasan Pelanggan. Untuk maklumat lanjut, lihat [keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada seksyen **Azure Synapse Analytics**. Jika anda tidak melihat nama bahagian ini, tiada [sambungan](connections.md) jenis ini tersedia untuk anda.

1. Sediakan **Nama paparan** yang dikenali untuk eksport dan **Nama pangkalan data** anda.

1. Pilih entiti mana yang anda mahu eksport ke Azure Synapse Analytics.
   > [!NOTE]
   > Sumber data berdasarkan [folder Common Data Model](connect-common-data-model.md) tidak disokong.

2. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).

Untuk bertanya data yang dieksport ke Synapse Analytics, anda memerlukan **akses Pembaca** Data Blob Storan ke storan destinasi pada ruang kerja eksport. 

### <a name="update-an-export"></a>Kemas kini eksport

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Edit** pada eksport yang anda mahu kemas kini.

   - **Tambah** atau **Alih Keluar** entiti daripada pemilihan. Jika entiti dialih keluar daripada pilihan, entiti tidak dipadamkan daripada pangkalan data Synapse Analytics. Walau bagaimanapun, penyegaran semula data masa akan datang tidak akan mengemas kini entiti yang dialih keluar dalam pangkalan data itu.

   - **Mengubah Nama Pangkalan Data** mencipta pangkalan data Synapse Analytics baharu. Pangkalan data dengan nama yang dikonfigurasikan sebelum ini tidak akan menerima sebarang kemas kini dalam penyegaran semula masa akan datang.
