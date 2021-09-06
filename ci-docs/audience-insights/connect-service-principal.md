---
title: Sambung ke akaun  Azure Data Lake Storage menggunakan prinsipal perkhidmatan
description: Gunakan prinsipal perkhidmatan Azure untuk menyambung ke data lake anda sendiri.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461159"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Sambung ke akaun Azure Data Lake Storage menggunakan prinsipal perkhidmatan Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Alat automatik yang menggunakan perkhidmatan Azure harus sentiasa mempunyai keizinan terhad. Daripada mempunyai daftar masuk aplikasi sebagai pengguna yang layak sepenuhnya, Azure menawarkan prinsipal perkhidmatan. Teruskan membaca untuk mengetahui cara untuk menyambungkan Dynamics 365 Customer Insights dengan akaun Azure Data Lake Storage dengan menggunakan prinsipal perkhidmatan Azure dan bukannya kekunci akaun storan. 

Anda boleh menggunakan prinsipal perkhidmatan untuk [menambah atau mengedit folder Common Data Service sebagai sumber data](connect-common-data-model.md) secara selamat atau [mencipta atau mengemas kini persekitaran](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Akaun Data Lake Storage yang akan menggunakan<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> prinsipal perkhidmatan mesti mempunyai [ruang nama hierarki didayakan](/azure/storage/blobs/data-lake-storage-namespace).
> - Anda memerlukan keizinan pentadbir untuk langganan Azure anda untuk mencipta prinsipal perkhidmatan.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Cipta prinsipal perkhidmatan Azure untuk Customer Insights

Sebelum mencipta prinsipal perkhidmatan baharu untuk cerapan khalayak atau cerapan penglibatan, semak sama ada ia sudah wujud dalam organisasi anda.

### <a name="look-for-an-existing-service-principal"></a>Cari prinsipal perkhidmatan sedia ada

1. Pergi ke [Portal pentadbir Azure](https://portal.azure.com) dan daftar masuk ke organisasi anda.

2. Daripada **perkhidmatan Azure**, pilih **Azure Active Directory**.

3. Di bawah **Urus**, pilih **Aplikasi Enterprise**.

4. Carian untuk Microsoft<!--note from editor: Via Microsoft Writing Style Guide.--> ID aplikasi:
   - Cerapan khalayak: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` dengan nama `Dynamics 365 AI for Customer Insights`
   - Cerapan penglibatan: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` dengan nama `Dynamics 365 AI for Customer Insights engagement insights`

5. Jika anda mendapati rekod yang sepadan, ia bermaksud bahawa prinsipal perkhidmatan sudah wujud. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Syot layar menunjukkan prinsipal perkhidmatan sedia ada.":::
   
6. Jika tiada hasil dikembalikan, cipta prinsipal perkhidmatan baharu.

>[!NOTE]
>Untuk menggunakan kuasa penuh Dynamics 365 Customer Insights, kami mencadangkan anda menambah kedua-dua aplikasi kepada prinsipal perkhidmatan.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Cipta prinsipal perkhidmatan baharu
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Pasang versi terkini Azure Active Directory PowerShell untuk Graf. Untuk mendapatkan maklumat lanjut, pergi ke [Pasang Azure Active Directory PowerShell untuk Graf](/powershell/azure/active-directory/install-adv2).

   1. Pada PC anda, pilih kekunci Windows pada papan kekunci anda dan cari untuk **Windows PowerShell** dan pilih **Jalankan sebagai pentadbir**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. Dalam tetingkap PowerShell yang terbuka, masukkan `Install-Module AzureAD`.

2. Cipta prinsipal perkhidmatan untuk Customer Insights dengan modul Azure AD PowerShell.

   1. Dalam tetingkap PowerShell, masukkan `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Gantikan *"[ID penyewa anda]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> dengan ID sebenar penyewa anda yang mana ingin anda cipta prinsipal perkhidmatan. Parameter nama persekitaran `AzureEnvironmentName` adalah pilihan.
  
   1. Masukkan `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Perintah ini mencipta prinsipal perkhidmatan untuk cerapan khalayak pada penyewa yang dipilih. 

   1. Masukkan `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Arahan ini mencipta prinsipal perkhidmatan untuk cerapan penglibatan<!--note from editor: Edit okay?--> pada penyewa terpilih.

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

Anda boleh<!--note from editor: Edit suggested only if this section is optional.--> lampirkan akaun Data Lake Storage dalam cerapan khalayak untuk [menyimpan data output](manage-environments.md) atau [gunakannya sebagai sumber data](connect-common-data-service-lake.md). Pilihan ini membenarkan anda memilih antara pendekatan berasaskan sumber atau berasaskan langganan. Bergantung pada pendekatan yang anda pilih, ikuti prosedur dalam salah satu bahagian berikut.<!--note from editor: Suggested.-->

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