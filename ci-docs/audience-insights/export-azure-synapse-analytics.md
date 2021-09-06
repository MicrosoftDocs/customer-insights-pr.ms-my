---
title: Eksport data Customer Insights ke Azure Synapse Analytics
description: Ketahui cara mengkonfigurasikan sambungan ke Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f206043298bdbf8a84b0ef37b47a43290653beba7d3d0e8b807ec74513614aa8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031944"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Eksport data ke Azure Synapse Analytics (Pratonton)

Azure Synapse adalah perkhidmatan analitis yang mempercepatkan masa untuk wawasan merentasi gudang data dan sistem data besar. Anda boleh menginges dan menggunakan data Customer Insights anda dalam [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

Prasyarat berikut mesti dipenuhi untuk mengkonfigurasi sambungan daripada Customer Insights ke Azure Synapse.

> [!NOTE]
> Pastikan untuk menetapkan semua **tugasan peranan** seperti yang diterangkan.  

## <a name="prerequisites-in-customer-insights"></a>Prasyarat dalam Customer Insights

* Anda mempunyai peranan **Pentadbir** dalam wawasan khalayak. Ketahui lanjut tentang [Menetapkan keizinan pengguna dalam wawasan khalayak](permissions.md#assign-roles-and-permissions)

Dalam Azure: 

- Langganan Azure yang aktif.

- Jika menggunakan akaun Azure Data Lake Storage Gen2, *prinsipal perkhidmatan untuk wawasan khalayak* memerlukan keizinan **Penyumbang Data Blob Storan**. Ketahui lanjut tentang [menyambung ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure untuk wawasan khalayak](connect-service-principal.md). Data Lake Storage Gen2 **mesti mempunyai** [ruang nama hierarki](/azure/storage/blobs/data-lake-storage-namespace) didayakan.

- Pada lokasi kumpulan sumber ruang kerja Azure Synapse, *prinsipal perkhidmatan* dan *pengguna untuk wawasan khalayak* perlu ditugaskan sekurang-kurangnya keizinan **Pembaca**. Untuk maklumat lanjut, lihat [Tugaskan peranan Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

- *Pengguna* memerlukan keizinan **Penyumbang Data Blob Storan** pada akaun Azure Data Lake Storage Gen2 tempat data berada dan dipautkan ke ruang kerja Azure Synapse. Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identiti terurus ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan keizinan **Penyumbang Data Blob Storan** pada akaun Azure Data Lake Storage Gen2 tempat data diletak dan dipaut ke ruang kerja Azure Synapse. Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Pada ruang kerja Azure Synapse, *prinsipal perkhidmatan untuk wawasan khalayak* memerlukan peranan **Pentadbir Synapse** ditugaskan. Untuk maklumat lanjut, lihat [Cara menyediakan kawalan akses untuk ruang kerja Synapse anda](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Sediakan sambungan dan eksport ke Azure Synapse

### <a name="configure-a-connection"></a>Konfigurasikan sambungan

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Azure Synapse Analytics** atau pilih **Sediakan** pada jubin **Azure Synapse Analytics** untuk mengkonfigurasi sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan Nama paparan. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih atau cari langganan yang anda mahu menggunakan data Customer Insights. Sebaik sahaja langganan dipilih, anda boleh memilih **Ruang kerja**, **Akaun storan** dan **Bekas**.

1. Pilih **Simpan** untuk menyimpan sambungan.

### <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada bahagian **Azure Synapse Analytics**. Jika anda tidak melihat nama bahagian ini, tiada [sambungan](connections.md) jenis ini tersedia untuk anda.

1. Sediakan **Nama paparan** yang dikenali untuk eksport dan **Nama pangkalan data** anda.

1. Pilih entiti yang anda mahu eksport ke Azure Synapse Analytics.
   > [!NOTE]
   > Sumber data berdasarkan [folder Common Data Model](connect-common-data-model.md) tidak disokong.

2. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Kemas kini eksport

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Edit** pada eksport yang anda mahu kemas kini.

   - **Tambah** atau **Alih Keluar** entiti daripada pemilihan. Jika entiti dialih keluar daripada pilihan, entiti tidak dipadamkan daripada pangkalan data Synapse Analytics. Walau bagaimanapun, penyegaran semula data masa akan datang tidak akan mengemas kini entiti yang dialih keluar dalam pangkalan data itu.

   - **Mengubah Nama Pangkalan Data** mencipta pangkalan data Synapse Analytics baharu. Pangkalan data dengan nama yang dikonfigurasikan sebelum ini tidak akan menerima sebarang kemas kini dalam penyegaran semula masa akan datang.
