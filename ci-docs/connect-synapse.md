---
title: Sambungkan Azure Synapse sumber data (pratonton)
description: Gunakan pangkalan data sebagai Azure Synapse sumber data dalam Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738167"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Sambungkan Azure Synapse Analytics sumber data (pratonton)

Azure Synapse Analytics adalah perkhidmatan analisis perusahaan yang mempercepatkan masa untuk mendapatkan pandangan di seluruh gudang data dan sistem data besar. Azure Synapse Analytics menyatukan teknologi SQL terbaik yang digunakan dalam pergudangan data perusahaan, teknologi Spark yang digunakan untuk data besar, Data Explorer untuk analisis siri log dan masa, Pipelines untuk integrasi data dan ETL/ELT, dan integrasi mendalam dengan perkhidmatan Azure lain seperti Power BI, Cosmos DB dan AzureML.

Untuk maklumat lanjut, lihat [Azure Synapse gambaran keseluruhan](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

> [!NOTE]
> Synapse Workspaces yang didayakan [tembok](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) api tidak disokong pada masa ini.
> [!IMPORTANT]
> Pastikan untuk menetapkan semua **tugasan peranan** seperti yang diterangkan.  

**Dalam Pandangan** Pelanggan:

* Anda mempunyai **peranan Pentadbir** dalam Wawasan Pelanggan. Ketahui lebih lanjut tentang [keizinan pengguna dalam Wawasan](permissions.md#add-users) Pelanggan.

**In Azure**:

- Langganan Azure yang aktif.

- Jika menggunakan akaun Gen2 baharu Azure Data Lake Storage , *prinsipal perkhidmatan untuk Wawasan* Pelanggan iaitu "Dynamics 365 AI for Customer Insights" memerlukan **keizinan Penyumbang** Data Blob Storan. Ketahui lebih lanjut tentang [menyambung dengan Azure Data Lake Storage prinsipal perkhidmatan untuk Wawasan](connect-service-principal.md) Pelanggan. Data Lake Storage Gen2 **mesti mempunyai** [ruang nama hierarki](/azure/storage/blobs/data-lake-storage-namespace) didayakan.

- Pada kumpulan sumber, ruang kerja terletak, prinsipal perkhidmatan iaitu "Dynamics 365 AI for Customer Insights" dan Azure Synapse pengguna untuk Wawasan *Pelanggan perlu diberikan sekurang-kurangnya* keizinan Pembaca *.* **·** Untuk maklumat lanjut, lihat [Tugaskan peranan Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

- *Pengguna* memerlukan keizinan **Penyumbang Data Blob Storan** pada akaun Azure Data Lake Storage Gen2 tempat data berada dan dipautkan ke ruang kerja Azure Synapse. Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identiti terurus ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan keizinan **Penyumbang Data Blob Storan** pada akaun Azure Data Lake Storage Gen2 tempat data diletak dan dipaut ke ruang kerja Azure Synapse. Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Pada ruang kerja, *prinsipal perkhidmatan untuk Wawasan* Pelanggan iaitu "Dynamics 365 AI for Customer Insights" memerlukan **peranan Pentadbir** Sinapse yang diberikan. Pengguna **memerlukan** sekurang-kurangnya **peranan Penyumbang** Sinapse yang diperuntukkan untuk ruang kerja. Untuk maklumat lanjut, lihat [Cara menyediakan kawalan akses untuk ruang kerja Synapse anda](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Jika persekitaran Wawasan Pelanggan anda menyimpan [data sendiri Azure Data Lake Storage](own-data-lake-storage.md), pengguna yang menyediakan sambungan untuk Azure Synapse Analytics memerlukan sekurang-kurangnya peranan Pembaca **terbina dalam** pada akaun Storan Tasik Data. Untuk maklumat lanjut, lihat [Tugaskan peranan Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Menyambung ke pangkalan data tasik data dalam Azure Synapse Analytics

1. Pergi **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. **Azure Synapse Analytics Pilih kaedah (Pratonton).**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Kotak dialog untuk menyambung ke data Synapse Analytics":::
  
1. **Masukkan Nama** untuk sumber data dan Perihalan **pilihan**.

1. Pilih sambungan [yang](connections.md) tersedia atau Azure Synapse Analytics [cipta yang](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse) baharu.

1. Pilih Pangkalan Data **daripada** ruang kerja yang disambungkan dalam sambungan terpilih Azure Synapse Analytics dan pilih **Berikut**. Pada masa ini, kami hanya menyokong pangkalan data jenis *pangkalan data* Lake.

1. Pilih entiti untuk menelan daripada pangkalan data yang disambungkan dan pilih **Seterusnya**.

1. Secara pilihan, pilih entiti data untuk membenarkan pemprofilan data.

1. Pilih **Simpan** untuk menggunakan pilihan anda dan mulakan pengingesan data daripada sumber data anda yang baru dicipta dipautkan ke jadual pangkalan data Tasik dalam Azure Synapse Analytics. Halaman **Sumber** data terbuka menunjukkan sumber data baru dalam **status Segar** Semula.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuatkan data boleh mengambil masa. Selepas segar semula berjaya, data yang ditelan boleh disemak semula daripada [**halaman Entiti**](entities.md) .

[!INCLUDE [footer-include](includes/footer-banner.md)]
