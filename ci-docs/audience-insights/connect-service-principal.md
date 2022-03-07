---
title: Sambung ke akaun  Azure Data Lake Storage menggunakan prinsipal perkhidmatan
description: Gunakan prinsipal perkhidmatan Azure untuk menyambung ke data lake anda sendiri.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: d593880b06bd21e96826039a67382b75a4296a87
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354201"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Sambung ke akaun Azure Data Lake Storage menggunakan prinsipal perkhidmatan Azure

Artikel ini membincangkan cara menyambung Dynamics 365 Customer Insights dengan akaun dengan Azure Data Lake Storage menggunakan prinsipal perkhidmatan Azure dan bukannya kunci akaun storan. 

Alat automatik yang menggunakan perkhidmatan Azure harus sentiasa mempunyai keizinan terhad. Daripada mempunyai daftar masuk aplikasi sebagai pengguna yang layak sepenuhnya, Azure menawarkan prinsipal perkhidmatan. Anda boleh menggunakan prinsipal perkhidmatan untuk menambah atau mengedit folder Model Data Biasa dengan [selamat sebagai sumber data](connect-common-data-model.md) atau [mencipta atau mengemas kini persekitaran](create-environment.md).

> [!IMPORTANT]
> - Akaun Storan Tasik Data yang akan menggunakan prinsipal perkhidmatan mestilah Gen2 dan membolehkan [ruang nama hierarki](/azure/storage/blobs/data-lake-storage-namespace). Akaun storan Azure Data Lake Gen1 tidak disokong.
> - Anda memerlukan keizinan pentadbir untuk langganan Azure anda untuk mencipta prinsipal perkhidmatan.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Cipta prinsipal perkhidmatan Azure untuk Customer Insights

Sebelum mencipta prinsipal perkhidmatan baru untuk Wawasan Pelanggan, semak sama ada ia sudah wujud dalam organisasi anda.

### <a name="look-for-an-existing-service-principal"></a>Cari prinsipal perkhidmatan sedia ada

1. Pergi ke [Portal pentadbir Azure](https://portal.azure.com) dan daftar masuk ke organisasi anda.

2. Daripada **perkhidmatan Azure**, pilih **Azure Active Directory**.

3. Di bawah **Urus**, pilih **Aplikasi Enterprise**.

4. Cari ID aplikasi Microsoft:
   - Cerapan khalayak: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` dengan nama `Dynamics 365 AI for Customer Insights`
   - Cerapan penglibatan: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` dengan nama `Dynamics 365 AI for Customer Insights engagement insights`

5. Jika anda mendapati rekod yang sepadan, ia bermaksud bahawa prinsipal perkhidmatan sudah wujud. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Syot layar menunjukkan prinsipal perkhidmatan sedia ada.":::
   
6. Jika tiada hasil dikembalikan, cipta prinsipal perkhidmatan baharu.

>[!NOTE]
>Untuk menggunakan kuasa penuh Dynamics 365 Customer Insights, kami mencadangkan anda menambah kedua-dua aplikasi kepada prinsipal perkhidmatan.

### <a name="create-a-new-service-principal"></a>Cipta prinsipal perkhidmatan baharu

1. Pasang versi terkini Azure Active Directory PowerShell untuk Graf. Untuk mendapatkan maklumat lanjut, pergi ke [Pasang Azure Active Directory PowerShell untuk Graf](/powershell/azure/active-directory/install-adv2).

   1. Pada PC anda, pilih kekunci Windows pada papan kekunci anda dan cari untuk **Windows PowerShell** dan pilih **Jalankan sebagai pentadbir**.
   
   1. Dalam tetingkap PowerShell yang terbuka, masukkan `Install-Module AzureAD`.

2. Cipta prinsipal perkhidmatan untuk Customer Insights dengan modul Azure AD PowerShell.

   1. Dalam tetingkap PowerShell, masukkan `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Gantikan *[ID penyewa anda]* dengan ID penyewa anda yang sebenar yang anda mahu mencipta prinsipal perkhidmatan. Parameter nama persekitaran `AzureEnvironmentName` adalah pilihan.
  
   1. Masukkan `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Perintah ini mencipta prinsipal perkhidmatan untuk cerapan khalayak pada penyewa yang dipilih. 

   1. Masukkan `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Perintah ini mencipta prinsipal perkhidmatan untuk cerapan penglibatan pada penyewa terpilih.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Berikan keizinan kepada prinsipal perkhidmatan untuk mengakses akaun storan

Pergi ke portal Azure untuk memberikan keizinan kepada prinsipal perkhidmatan untuk akaun storan yang anda mahu gunakan dalam cerapan khalayak.

1. Pergi ke [Portal pentadbir Azure](https://portal.azure.com) dan daftar masuk ke organisasi anda.

1. Buka akaun storan yang anda mahu asas perkhidmatan untuk cerapan khalayak untuk mempunyai akses kepadanya.

1. Pada tetingkap kiri, pilih **Kawalan capaian (IAM)** dan kemudian pilih **Tambah** > **Tambah tugasan peranan**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Syot layar yang menunjukkan portal Azure semasa menambah penugasan peranan.":::

1. Pada anak tetingkap **Tambah penugasan peranan**, tetapkan sifat berikut:
   - Peranan: **Penyumbang Blob Data Storan**
   - Tugaskan akses kepada: **Pengguna, kumpulan atau prinsipal perkhidmatan**
   - Pilih: **Dynamics 365 for Customer Insights** dan **cerapan penglibatan Dynamics 365 for Customer Insights** (dua [prinsipal perkhidmatan](#create-a-new-service-principal) yang anda cipta lebih awal dalam prosedur ini)

1.  Pilih **Simpan**.

Prses boleh mengambil masa sehingga 15 minit menyebarkan perubahan.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Masukkan ID sumber Azure atau butiran langganan Azure dalam lampiran akaun storan kepada cerapan khalayak

Anda boleh melampirkan akaun Data Lake Storage dalam cerapan khalayak untuk [menyimpan data output](manage-environments.md) atau [gunakannya sebagai sumber data](/dynamics365/customer-insights/audience-insights/connect-dataverse-managed-lake). Pilihan ini membenarkan anda memilih antara pendekatan berasaskan sumber atau berasaskan langganan. Bergantung pada pendekatan yang anda pilih, ikuti prosedur dalam salah satu bahagian berikut.

### <a name="resource-based-storage-account-connection"></a>Sambungan akaun storan berdasarkan sumber

1. Pergi ke [portal pentadbir Azure](https://portal.azure.com), daftar masuk ke langganan anda dan buka akaun storan anda.

1. Pada tetingkap kiri, pergi ke **Tetapan** > **Sifat**.

1. Salin nilai ID sumber akaun storan:

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salin ID sumber akaun storan.":::

1. Dalam cerapan khalayak, sisipkan ID sumber dalam medan sumber yang dipaparkan pada skrin sambungan akaun storan.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Masukkan maklumat ID sumber akaun storan.":::   

1. Teruskan dengan langkah selebihnya dalam cerapan khalayak untuk melampirkan akaun storan.

### <a name="subscription-based-storage-account-connection"></a>Sambungan akaun storan berdasarkan langganan

1. Pergi ke [portal pentadbir Azure](https://portal.azure.com), daftar masuk ke langganan anda dan buka akaun storan anda.

1. Pada tetingkap kiri, pergi ke **Tetapan** > **Sifat**.

1. Semak **Langganan**, **Kumpulan sumber** dan **Nama** akaun storan untuk memastikan anda memilih nilai yang sesuai dalam cerapan khalayak.

1. Dalam cerapan khalayak, pilih nilai untuk medan yang berkaitan apabila melampirkan akaun storan.

1. Teruskan dengan langkah selebihnya dalam cerapan khalayak untuk melampirkan akaun storan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]