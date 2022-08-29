---
title: Sambung ke akaun Azure Data Lake Storage menggunakan prinsipal perkhidmatan Azure
description: Gunakan prinsipal perkhidmatan Azure untuk menyambung ke data lake anda sendiri.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304208"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Sambung ke akaun Azure Data Lake Storage menggunakan prinsipal perkhidmatan Azure

Dynamics 365 Customer Insights menyediakan pilihan untuk menyambung ke akaun dengan Azure Data Lake Storage menggunakan prinsipal perkhidmatan Azure dan bukannya kunci akaun storan.

Alat automatik yang menggunakan perkhidmatan Azure mesti mempunyai keizinan terhad. Daripada mempunyai daftar masuk aplikasi sebagai pengguna yang layak sepenuhnya, Azure menawarkan prinsipal perkhidmatan. Gunakan prinsipal perkhidmatan untuk menambah atau menyunting folder Model Data Biasa dengan [selamat sebagai sumber data](connect-common-data-model.md) atau [mencipta atau mengemas kini persekitaran](create-environment.md).

## <a name="prerequisites"></a>Prasyarat

- Akaun Penyimpanan Tasik Data yang akan menggunakan prinsipal perkhidmatan mestilah Gen2. Akaun storan Azure Data Lake Gen1 tidak disokong.
- Akaun Penyimpanan Tasik Data didayakan [ruang nama hierarki](/azure/storage/blobs/data-lake-storage-namespace).
- Keizinan pentadbir untuk Penyewa Azure anda, jika anda perlu mencipta prinsipal perkhidmatan baharu.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Cipta prinsipal perkhidmatan Azure untuk Customer Insights

Sebelum mencipta prinsipal perkhidmatan baru untuk Wawasan Pelanggan, semak sama ada ia sudah wujud dalam organisasi anda. Dalam kebanyakan kes, ia sudah wujud.

### <a name="look-for-an-existing-service-principal"></a>Cari prinsipal perkhidmatan sedia ada

1. Pergi ke [Portal pentadbir Azure](https://portal.azure.com) dan daftar masuk ke organisasi anda.

2. Daripada **perkhidmatan Azure**, pilih **Azure Active Directory**.

3. Di bawah **Urus**, pilih **Aplikasi** Microsoft.

4. Tambah penapis untuk **ID Aplikasi bermula dengan**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` atau cari nama `Dynamics 365 AI for Customer Insights`.

5. Jika anda mendapati rekod yang sepadan, ia bermaksud bahawa prinsipal perkhidmatan sudah wujud. [Berikan kebenaran](#grant-permissions-to-the-service-principal-to-access-the-storage-account) untuk prinsipal perkhidmatan mengakses akaun storan.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Syot layar menunjukkan prinsipal perkhidmatan sedia ada.":::

6. Jika tiada keputusan dikembalikan, [cipta prinsipal](#create-a-new-service-principal) perkhidmatan baharu.

### <a name="create-a-new-service-principal"></a>Cipta prinsipal perkhidmatan baharu

1. Pasang versi terkini Azure Active Directory PowerShell untuk Graf. Untuk mendapatkan maklumat lanjut, pergi ke [Pasang Azure Active Directory PowerShell untuk Graf](/powershell/azure/active-directory/install-adv2).

   1. Pada PC anda, tekan kekunci Windows pada papan kekunci anda dan cari **Windows PowerShell** dan pilih **Jalankan sebagai pentadbir**.

   1. Dalam tetingkap PowerShell yang terbuka, masukkan `Install-Module AzureAD`.

2. Cipta prinsipal perkhidmatan untuk Customer Insights dengan modul Azure AD PowerShell.

   1. Dalam tetingkap PowerShell, masukkan `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Gantikan *[ID Direktori anda]* dengan ID Direktori sebenar langganan Azure anda di mana anda ingin mencipta prinsipal perkhidmatan. Parameter nama persekitaran `AzureEnvironmentName` adalah pilihan.
  
   1. Masukkan `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Perintah ini mencipta prinsipal perkhidmatan untuk Wawasan Pelanggan pada langganan Azure yang dipilih.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Berikan keizinan kepada prinsipal perkhidmatan untuk mengakses akaun storan

Untuk memberikan kebenaran kepada prinsipal perkhidmatan untuk akaun storan yang ingin anda gunakan dalam Wawasan Pelanggan, salah satu peranan berikut mesti ditugaskan ke akaun storan atau bekas:

|Kelayakan|Keperluan|
|----------|------------|
|Pengguna yang log masuk pada masa ini|**Peranan**: Storan Pembaca Data Blob, Penyumbang Blob Storan atau Pemilik Blob Storan.<br>**Tahap**: Keizinan yang diberikan pada akaun storan atau bekas.</br>|
|Prinsipal Perkhidmatan Wawasan Pelanggan -<br>Menggunakan Azure Data Lake Storage sebagai sumber data</br>|Pilihan 1<ul><li>**Peranan**: Storan Pembaca Data Blob, Penyumbang Data Blob Storan atau Pemilik Data Blob Storan.</li><li>**Tahap**: Keizinan yang diberikan pada akaun storan.</li></ul>Pilihan 2 *(tanpa berkongsi akses Prinsipal Perkhidmatan ke akaun storan)*<ul><li>**Peranan 1**: Pembaca Data Blob Storan, Penyumbang Data Blob Storan atau Pemilik Data Blob Storan.</li><li>**Tahap**: Kebenaran yang diberikan pada bekas.</li><li>**Peranan 2**: Penghadang Data Blob Storan.</li><li>**Tahap**: Keizinan yang diberikan pada akaun storan.</li></ul>|
|Prinsipal Perkhidmatan Wawasan Pelanggan - <br>Menggunakan Azure Data Lake Storage sebagai output atau destinasi</br>|Pilihan 1<ul><li>**Peranan**: Penyumbang Data Blob Storan atau Pemilik Blob Storan.</li><li>**Tahap**: Keizinan yang diberikan pada akaun storan.</li></ul>Pilihan 2 *(tanpa berkongsi akses Prinsipal Perkhidmatan ke akaun storan)*<ul><li>**Peranan**: Penyumbang Data Blob Storan atau Pemilik Blob Storan.</li><li>**Tahap**: Kebenaran yang diberikan pada bekas.</li><li>**Peranan 2**: Storage Blob Delegator.</li><li>**Tahap**: Keizinan yang diberikan pada akaun storan.</li></ul>|

1. Pergi ke [Portal pentadbir Azure](https://portal.azure.com) dan daftar masuk ke organisasi anda.

1. Buka akaun storan yang anda mahu prinsipal perkhidmatan untuk Wawasan Pelanggan mempunyai akses.

1. Pada tetingkap kiri, pilih **Kawalan capaian (IAM)** dan kemudian pilih **Tambah** > **Tambah tugasan peranan**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Syot layar yang menunjukkan portal Azure semasa menambah penugasan peranan.":::

1. Pada anak tetingkap **Tambah penugasan peranan**, tetapkan sifat berikut:
   - **Peranan**: Storage Blob Data Reader, Storage Blob Contributor atau Storage Blob Owner berdasarkan kelayakan yang disenaraikan di atas.
   - **Peruntukkan capaian kepada**: **Pengguna, kumpulan atau prinsipal perkhidmatan**
   - **Pilih** ahli: **Dynamics 365 AI for Customer Insights** ([prinsipal](#create-a-new-service-principal) perkhidmatan yang anda cari sebelum ini dalam prosedur ini)

1. Pilih **Semak + tugaskan**.

Prses boleh mengambil masa sehingga 15 minit menyebarkan perubahan.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Masukkan ID sumber Azure atau butiran langganan Azure dalam lampiran akaun storan ke Wawasan Pelanggan

Lampirkan akaun Penyimpanan Tasik Data dalam Wawasan Pelanggan untuk [menyimpan data](manage-environments.md) output atau [menggunakannya sebagai sumber data](connect-dataverse-managed-lake.md). Pilih antara [pendekatan berasaskan](#resource-based-storage-account-connection) sumber atau [berasaskan](#subscription-based-storage-account-connection) langganan dan ikuti langkah tersebut.

### <a name="resource-based-storage-account-connection"></a>Sambungan akaun storan berdasarkan sumber

1. Pergi ke [portal pentadbir Azure](https://portal.azure.com), daftar masuk ke langganan anda dan buka akaun storan anda.

1. Pada anak tetingkap kiri, pergi ke **Seting** > **Titik Akhir**.

1. Salin nilai ID sumber akaun storan:

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salin ID sumber akaun storan.":::

1. Dalam Wawasan Pelanggan, masukkan ID sumber dalam medan sumber yang dipaparkan pada skrin sambungan akaun storan.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Masukkan maklumat ID sumber akaun storan.":::

1. Teruskan dengan langkah selebihnya dalam Wawasan Pelanggan untuk melampirkan akaun storan.

### <a name="subscription-based-storage-account-connection"></a>Sambungan akaun storan berdasarkan langganan

1. Pergi ke [portal pentadbir Azure](https://portal.azure.com), daftar masuk ke langganan anda dan buka akaun storan anda.

1. Pada tetingkap kiri, pergi ke **Tetapan** > **Sifat**.

1. **Semak Semula Langganan**, **Kumpulan** Sumber dan **Nama** akaun storan untuk memastikan anda memilih nilai yang betul dalam Wawasan Pelanggan.

1. Dalam Wawasan Pelanggan, pilih nilai untuk medan yang sepadan semasa melampirkan akaun storan.

1. Teruskan dengan langkah selebihnya dalam Wawasan Pelanggan untuk melampirkan akaun storan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
