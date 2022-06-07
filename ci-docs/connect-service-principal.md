---
title: Sambung ke akaun  Azure Data Lake Storage menggunakan prinsipal perkhidmatan
description: Gunakan prinsipal perkhidmatan Azure untuk menyambung ke data lake anda sendiri.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: b18d1f42b9510ebf23f0666322819865d132173b
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833396"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Sambung ke akaun Azure Data Lake Storage menggunakan prinsipal perkhidmatan Azure

Artikel ini membincangkan cara menyambung Dynamics 365 Customer Insights dengan akaun dengan Azure Data Lake Storage menggunakan prinsipal perkhidmatan Azure dan bukannya kunci akaun storan.

Alat automatik yang menggunakan perkhidmatan Azure harus sentiasa mempunyai keizinan terhad. Daripada mempunyai daftar masuk aplikasi sebagai pengguna yang layak sepenuhnya, Azure menawarkan prinsipal perkhidmatan. Anda boleh menggunakan prinsipal perkhidmatan untuk menambah atau mengedit folder Model Data Biasa dengan selamat [sebagai sumber data](connect-common-data-model.md) atau [mencipta atau mengemas kini persekitaran](create-environment.md).

> [!IMPORTANT]
>
> - Akaun Data Lake Storage yang akan menggunakan prinsipal perkhidmatan mestilah Gen2 dan mempunyai [ruang nama hierarki yang didayakan](/azure/storage/blobs/data-lake-storage-namespace). Akaun storan Azure Data Lake Gen1 tidak disokong.
> - Anda memerlukan keizinan pentadbir untuk Penyewa Azure anda untuk mencipta prinsipal perkhidmatan.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Cipta prinsipal perkhidmatan Azure untuk Customer Insights

Sebelum mencipta prinsipal perkhidmatan baru untuk Wawasan Pelanggan, semak sama ada ia sudah wujud dalam organisasi anda.

### <a name="look-for-an-existing-service-principal"></a>Cari prinsipal perkhidmatan sedia ada

1. Pergi ke [Portal pentadbir Azure](https://portal.azure.com) dan daftar masuk ke organisasi anda.

2. Daripada **perkhidmatan Azure**, pilih **Azure Active Directory**.

3. Di bawah **Urus**, pilih **Aplikasi** Microsoft.

4. Tambah penapis untuk **ID Aplikasi bermula dengan**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` atau cari nama `Dynamics 365 AI for Customer Insights`.

5. Jika anda mendapati rekod yang sepadan, ia bermaksud bahawa prinsipal perkhidmatan sudah wujud.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Syot layar menunjukkan prinsipal perkhidmatan sedia ada.":::

6. Jika tiada keputusan dikembalikan, anda boleh [mencipta prinsipal](#create-a-new-service-principal) perkhidmatan baru. Dalam kebanyakan kes, ia sudah wujud dan anda hanya perlu memberikan kebenaran untuk prinsipal perkhidmatan untuk mengakses akaun storan.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Berikan keizinan kepada prinsipal perkhidmatan untuk mengakses akaun storan

Pergi ke portal Azure untuk memberikan keizinan kepada prinsipal perkhidmatan untuk akaun storan yang anda ingin gunakan dalam Wawasan Pelanggan.

1. Pergi ke [Portal pentadbir Azure](https://portal.azure.com) dan daftar masuk ke organisasi anda.

1. Buka akaun storan yang anda mahu prinsipal perkhidmatan untuk Wawasan Pelanggan mempunyai akses kepada.

1. Pada tetingkap kiri, pilih **Kawalan capaian (IAM)** dan kemudian pilih **Tambah** > **Tambah tugasan peranan**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Syot layar yang menunjukkan portal Azure semasa menambah penugasan peranan.":::

1. Pada anak tetingkap **Tambah penugasan peranan**, tetapkan sifat berikut:
   - Peranan: **Penyumbang Blob Data Storan**
   - Tugaskan akses kepada: **Pengguna, kumpulan atau prinsipal perkhidmatan**
   - Pilih ahli: **Dynamics 365 AI for Customer Insights** ([prinsipal](#create-a-new-service-principal) perkhidmatan yang anda cari lebih awal dalam prosedur ini)

1. Pilih **Semakan + serah hak**.

Prses boleh mengambil masa sehingga 15 minit menyebarkan perubahan.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Masukkan ID sumber Azure atau butiran langganan Azure dalam lampiran akaun storan ke Customer Insights

Anda boleh melampirkan akaun Storan Tasik Data dalam Wawasan Pelanggan untuk [menyimpan data](manage-environments.md) output atau [menggunakannya sebagai sumber data](connect-dataverse-managed-lake.md). Pilihan ini membenarkan anda memilih antara pendekatan berasaskan sumber atau berasaskan langganan. Bergantung pada pendekatan yang anda pilih, ikuti prosedur dalam salah satu bahagian berikut.

### <a name="resource-based-storage-account-connection"></a>Sambungan akaun storan berdasarkan sumber

1. Pergi ke [portal pentadbir Azure](https://portal.azure.com), daftar masuk ke langganan anda dan buka akaun storan anda.

1. Pada anak tetingkap kiri, pergi ke **Titik** > **Akhir Tetapan**.

1. Salin nilai ID sumber akaun storan:

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salin ID sumber akaun storan.":::

1. Dalam Wawasan Pelanggan, masukkan ID sumber dalam medan sumber yang dipaparkan pada skrin sambungan akaun storan.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Masukkan maklumat ID sumber akaun storan.":::   

1. Teruskan dengan langkah yang tinggal dalam Wawasan Pelanggan untuk melampirkan akaun storan.

### <a name="subscription-based-storage-account-connection"></a>Sambungan akaun storan berdasarkan langganan

1. Pergi ke [portal pentadbir Azure](https://portal.azure.com), daftar masuk ke langganan anda dan buka akaun storan anda.

1. Pada tetingkap kiri, pergi ke **Tetapan** > **Sifat**.

1. **Semak semula Langganan**, **kumpulan** Sumber dan **Nama** akaun storan untuk memastikan anda memilih nilai yang betul dalam Wawasan Pelanggan.

1. Dalam Wawasan Pelanggan, pilih nilai untuk medan yang sepadan apabila melampirkan akaun storan.

1. Teruskan dengan langkah yang tinggal dalam Wawasan Pelanggan untuk melampirkan akaun storan.

### <a name="create-a-new-service-principal"></a>Cipta prinsipal perkhidmatan baharu

1. Pasang versi terkini Azure Active Directory PowerShell untuk Graf. Untuk mendapatkan maklumat lanjut, pergi ke [Pasang Azure Active Directory PowerShell untuk Graf](/powershell/azure/active-directory/install-adv2).

   1. Pada PC anda, tekan kekunci Windows pada papan kekunci anda dan cari **Windows PowerShell** dan pilih **Jalankan sebagai pentadbir**.

   1. Dalam tetingkap PowerShell yang terbuka, masukkan `Install-Module AzureAD`.

2. Cipta prinsipal perkhidmatan untuk Customer Insights dengan modul Azure AD PowerShell.

   1. Dalam tetingkap PowerShell, masukkan `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Gantikan *[ID Direktori anda]* dengan ID Direktori sebenar langganan Azure anda di mana anda ingin mencipta prinsipal perkhidmatan. Parameter nama persekitaran `AzureEnvironmentName` adalah pilihan.
  
   1. Masukkan `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Perintah ini mencipta prinsipal perkhidmatan untuk Wawasan Pelanggan pada langganan Azure yang dipilih.

[!INCLUDE [footer-include](includes/footer-banner.md)]