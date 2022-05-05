---
title: Ingest data daripada Azure Synapse Analytics
description: Gunakan pangkalan data sebagai Azure Synapse sumber data dalam Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643344"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse Sambungkan sumber data (pratonton)

Azure Synapse Analytics adalah perkhidmatan analisis perusahaan yang mempercepatkan masa untuk cerapan merentasi gudang data dan sistem data besar. Azure Synapse Analytics menyatukan teknologi SQL terbaik yang digunakan dalam pergudangan data perusahaan, teknologi Spark yang digunakan untuk data besar, Data Explorer untuk analisis log dan siri masa, Pipelines untuk integrasi data dan ETL / ELT, dan integrasi mendalam dengan perkhidmatan Azure lain seperti Power BI, Cosmos DB,, dan AzureML.

Untuk maklumat lanjut, lihat [Azure Synapse gambaran keseluruhan](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

Prasyarat berikut mesti dipenuhi untuk mengkonfigurasi sambungan dari Dynamics 365 Customer Insights ke Azure Synapse.

> [!IMPORTANT]
> Pastikan untuk menetapkan semua **tugasan peranan** seperti yang diterangkan.  

## <a name="prerequisites-in-customer-insights"></a>Prasyarat dalam Customer Insights

* Anda mempunyai **peranan Pentadbir** dalam Wawasan Pelanggan. Ketahui lebih lanjut tentang [keizinan pengguna dalam Wawasan](permissions.md#assign-roles-and-permissions) Pelanggan.

Dalam Azure: 

- Langganan Azure yang aktif.

- Jika menggunakan akaun Gen2 baharu Azure Data Lake Storage, *prinsipal perkhidmatan untuk Wawasan* Pelanggan memerlukan **keizinan Penyumbang** Data Blob Storan. Ketahui lebih lanjut tentang [menyambung ke Azure Data Lake Storage dengan prinsipal perkhidmatan untuk Wawasan](connect-service-principal.md) Pelanggan. Data Lake Storage Gen2 **mesti mempunyai** [ruang nama hierarki](/azure/storage/blobs/data-lake-storage-namespace) didayakan.

- Pada kumpulan Azure Synapse sumber ruang kerja terletak, *prinsipal* perkhidmatan dan *pengguna untuk Wawasan* Pelanggan perlu diperuntukkan sekurang-kurangnya **keizinan Pembaca**. Untuk maklumat lanjut, lihat [Tugaskan peranan Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

- *Pengguna* memerlukan keizinan **Penyumbang Data Blob Storan** pada akaun Azure Data Lake Storage Gen2 tempat data berada dan dipautkan ke ruang kerja Azure Synapse. Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identiti terurus ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan keizinan **Penyumbang Data Blob Storan** pada akaun Azure Data Lake Storage Gen2 tempat data diletak dan dipaut ke ruang kerja Azure Synapse. Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Pada ruang kerja, *prinsipal perkhidmatan untuk Wawasan* Pelanggan memerlukan **peranan Pentadbir** Sinapse yang diberikan. Untuk maklumat lanjut, lihat [Cara menyediakan kawalan akses untuk ruang kerja Synapse anda](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Sambung ke pangkalan data tasik data dalam Azure Synapse Analytics

1. Pergi **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. **Azure Synapse Analytics Pilih kaedah (Pratonton**).

1. Berikan **Nama** untuk sumber data dan pilih **Seterusnya** untuk mencipta sumber data. 

1. Pilih sambungan [yang](connections.md) tersedia ke Azure Synapse Analytics atau cipta yang baru.

1. **Pilih Pangkalan Data** Tasik daripada ruang kerja yang disambungkan dalam sambungan yang dipilih Azure Synapse Analytics dan pilih **Berikut**.

1. Pilih entiti untuk menelan dari pangkalan data yang disambungkan. 

1. Secara pilihan, pilih entiti data untuk membenarkan pemprofilan data dihidupkan. 

1. Pilih **Simpan** untuk menggunakan pilihan anda dan mulakan pengambilan data daripada sumber data anda yang baru dicipta yang dipautkan ke jadual pangkalan data Tasik dalam Azure Synapse Analytics.
