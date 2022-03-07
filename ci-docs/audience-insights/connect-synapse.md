---
title: Data teringja dari Azure Synapse Analytics
description: Gunakan pangkalan data Azure Synapse sebagai sumber data dalam Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356051"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse Sambungkan sumber data (pratonton)

Azure Synapse Analytics adalah perkhidmatan analisis perusahaan yang mempercepatkan masa untuk wawasan di seluruh gudang data dan sistem data besar. Azure Synapse Analytics menyatukan teknologi SQL yang terbaik yang digunakan dalam pergudangan data perusahaan, teknologi Spark yang digunakan untuk data besar, Data Explorer untuk analisis siri log dan masa, Talian paip untuk integrasi data dan ETL / ELT, dan integrasi mendalam dengan perkhidmatan Azure lain seperti Power BI, Cosmos DB, dan AzureML.

Untuk maklumat lanjut, lihat [Azure Synapse gambaran keseluruhan](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

Prasyarat berikut mesti dipenuhi untuk mengkonfigurasi sambungan daripada Customer Insights ke Azure Synapse.

> [!IMPORTANT]
> Pastikan untuk menetapkan semua **tugasan peranan** seperti yang diterangkan.  

## <a name="prerequisites-in-customer-insights"></a>Prasyarat dalam Customer Insights

* Anda mempunyai **peranan Pentadbir** dalam Wawasan Pelanggan. Ketahui lebih lanjut tentang [keizinan pengguna dalam cerapan khalayak](permissions.md#assign-roles-and-permissions).

Dalam Azure: 

- Langganan Azure yang aktif.

- Jika menggunakan akaun Azure Data Lake Storage Gen2, *prinsipal perkhidmatan untuk wawasan khalayak* memerlukan keizinan **Penyumbang Data Blob Storan**. Ketahui lebih lanjut tentang [menyambung ke Azure Data Lake Storage prinsipal perkhidmatan untuk cerapan](connect-service-principal.md) khalayak. Data Lake Storage Gen2 **mesti mempunyai** [ruang nama hierarki](/azure/storage/blobs/data-lake-storage-namespace) didayakan.

- Pada lokasi kumpulan sumber ruang kerja Azure Synapse, *prinsipal perkhidmatan* dan *pengguna untuk wawasan khalayak* perlu ditugaskan sekurang-kurangnya keizinan **Pembaca**. Untuk maklumat lanjut, lihat [Tugaskan peranan Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

- *Pengguna* memerlukan keizinan **Penyumbang Data Blob Storan** pada akaun Azure Data Lake Storage Gen2 tempat data berada dan dipautkan ke ruang kerja Azure Synapse. Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identiti terurus ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan keizinan **Penyumbang Data Blob Storan** pada akaun Azure Data Lake Storage Gen2 tempat data diletak dan dipaut ke ruang kerja Azure Synapse. Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Pada ruang kerja Azure Synapse, *prinsipal perkhidmatan untuk wawasan khalayak* memerlukan peranan **Pentadbir Synapse** ditugaskan. Untuk maklumat lanjut, lihat [Cara menyediakan kawalan akses untuk ruang kerja Synapse anda](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Sambung ke pangkalan data tasik dalam Azure Synapse Analytics

1. Pergi **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. Pilih kaedah **Azure Synapse Analytics (Pratonton**).

1. Berikan **Nama** untuk sumber data dan pilih **Seterusnya** untuk mencipta sumber data. 

1. Pilih sambungan [yang](connections.md) Azure Synapse Analytics tersedia atau cipta sambungan baharu.

1. **Pilih Pangkalan Data** Tasik daripada ruang kerja yang disambungkan dalam sambungan yang dipilih Azure Synapse Analytics dan pilih **Berikut**.

1. Pilih entiti untuk menelan dari pangkalan data yang disambungkan. 

1. Secara pilihan, pilih entiti data untuk membenarkan profil data dihidupkan. 

1. Pilih **Simpan** untuk menggunakan pilihan anda dan mulakan pengingesan data daripada sumber data anda yang baru dicipta yang dipautkan ke jadual pangkalan data Tasik dalam Azure Synapse Analytics.
