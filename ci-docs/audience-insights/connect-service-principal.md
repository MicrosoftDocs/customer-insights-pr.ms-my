---
title: Sambung kepada akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan
description: Gunakan prinsipal perkhidmatan Azure untuk cerapan khalayak untuk menyambung ke data lake anda apabila memasukkannya ke cerapan khalayak.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267733"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Sambungkan cerapan khalayak ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure untuk cerapan khalayak

Alat automatik yang menggunakan perkhidmatan Azure harus sentiasa mempunyai keizinan terhad. Daripada mempunyai daftar masuk aplikasi sebagai pengguna yang layak sepenuhnya, Azure menawarkan prinsipal perkhidmatan. Teruskan membaca untuk mengetahui cara untuk menyambungkan cerapan khalayak dengan akaun Azure Data Lake Storage Gen2 menggunakan prinsipal perkhidmatan Azure dan bukannya kekunci akaun storan. 

Anda boleh menggunakan prinsipal perkhidmatan untuk [menambah atau mengedit folder Common Data Model sebagai sumber data](connect-common-data-model.md) atau [mencipta persekitaran sedia ada atau kemas kini](manage-environments.md#create-an-environment-in-an-existing-organization).

> [!IMPORTANT]
> - Akaun Storan Gen2 Data Lake Azure yang bertujuan untuk menggunakan prinsipal perkhidmatan mesti mempunyai [Ruang Nama Hierarki (HNS) didayakan](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).
> - Anda memerlukan keizinan pentadbir untuk langganan Azure anda untuk mencipta prinsipal perkhidmatan.

## <a name="create-azure-service-principal-for-audience-insights"></a>Cipta prinsipal perkhidmatan Azure untuk cerapan khalayak

Sebelum mencipta prinsipal perkhidmatan baharu untuk cerapan khalayak, semak sama ada ia sudah wujud dalam organisasi anda.

### <a name="look-for-an-existing-service-principal"></a>Cari prinsipal perkhidmatan sedia ada

1. Pergi ke [Portal pentadbir Azure](https://portal.azure.com) dan daftar masuk ke organisasi anda.

2. Pilih **Azure Active Directory** daripada perkhidmatan Azure.

3. Di bawah **Urus**, pilih **Aplikasi Enterprise**.

4. Cari ID aplikasi cerapan khalayak pihak pertama `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` atau nama `Dynamics 365 AI for Customer Insights`.

5. Jika anda menemui rekod yang sepadan, ia bermaksud bahawa prinsipal perkhidmatan untuk cerapan khalayak wujud. Anda tidak perlu memasang ia lagi.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Yangkapan skrin yang menunjukkan prinsipal perkhidmatan sedia ada.":::
   
6. Jika tiada hasil dikembalikan, cipta prinsipal perkhidmatan baharu.

### <a name="create-a-new-service-principal"></a>Cipta prinsipal perkhidmatan baharu

1. Pasang versi terkini bagi **Azure Active Directory PowerShell untuk Graf**. Untuk maklumat lanjut, lihat [Pasang Azure Active Directory PowerShell untuk Graf](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - Pada PC anda, pilih kekunci Windows pada papan kekunci anda dan gelintar untuk **Windows PowerShell** dan **Jalankan sebagai Pentadbir**.
   
   - Dalam tetingkap PowerShell yang terbuka, masukkan `Install-Module AzureAD`.

2. Cipta prinsipal perkhidmatan untuk cerapan khalayak dengan Modul Azure AD PowerShell.
   - Dalam tetingkap PowerShell, masukkan `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Gantikan "ID penyewa anda" dengan ID penyewa anda yang sebenar yang anda mahu cipta prinsipal perkhidmatan. Parameter nama persekitaran `AzureEnvironmentName` adalah pilihan.
  
   - Masukkan `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Perintah ini mencipta prinsipal perkhidmatan untuk cerapan khalayak pada penyewa yang dipilih.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Berikan keizinan kepada prinsipal perkhidmatan untuk mengakses akaun storan

Pergi ke portal Azure untuk memberikan keizinan kepada prinsipal perkhidmatan untuk akaun storan yang anda mahu gunakan dalam cerapan khalayak.

1. Pergi ke [Portal pentadbir Azure](https://portal.azure.com) dan daftar masuk ke organisasi anda.

1. Buka akaun storan yang anda mahu asas perkhidmatan untuk cerapan khalayak untuk mempunyai akses kepadanya.

1. Pilih **Kawalan capaian (IAM)** daripada tetingkap navigasi dan pilih **Tambah** > **Tambah tugasan peranan**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Tangkapan skrin menunjukkan portal Azure sambil menambah tugasan peranan.":::
   
1. Dalam anak tetingkap **Tambah tugasan peranan**, tetapkan sifat berikut:
   - Peranan: *Penyumbang Blob Data Storan*
   - Tugaskan akses kepada: *Pengguna, kumpulan atau prinsipal perkhidmatan*
   - Pilih: *Dynamics 365 AI untuk Customer Insights* ([prinsipal perkhidmatan yang anda cipta](#create-a-new-service-principal))

1.  Pilih **Simpan**.

Prses boleh mengambil masa sehingga 15 minit menyebarkan perubahan.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Masukkan ID Sumber Azure atau butiran Langganan Azure dalam lampiran akaun storan kepada Audience Insights.

Lampirkan akaun storan Azure Data Lake cerapan khalayak untuk [menyimpan data output](manage-environments.md) atau [menggunakannya sebagai sumber data](connect-common-data-service-lake.md). Memilih pilihan Azure Data Lake membolehkan anda memilih antara pendekatan berasaskan sumber atau berasaskan langganan.

Ikuti langkah di bawah untuk menyediakan maklumat yang diperlukan tentang pendekatan yang dipilih.

### <a name="resource-based-storage-account-connection"></a>Sambungan akaun storan berdasarkan sumber

1. Pergi ke [Portal pentadbir Azure](https://portal.azure.com), daftar masuk ke langganan anda dan buka akaun storan anda.

1. Pergi ke **Tetapan** > **Sifat** pada tetingkap navigasi.

1. Salin nilai ID sumber akaun storan:

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salin ID sumber akaun storan.":::

1. Dalam cerapan khalayak, masukkan ID sumber dalam medan sumber dipaparkan dalam skrin sambungan akaun storan.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Masukkan maklumat ID sumber akaun storan.":::   
   
1. Teruskan dengan langkah selebihnya dalam cerapan khalayak untuk melampirkan akaun storan.

### <a name="subscription-based-storage-account-connection"></a>Sambungan akaun storan berdasarkan langganan

1. Pergi ke [Portal pentadbir Azure](https://portal.azure.com), daftar masuk ke langganan anda dan buka akaun storan anda.

1. Pergi ke **Tetapan** > **Sifat** pada tetingkap navigasi.

1. Semak **Langganan**, **Kumpulan sumber** dan **Nama** akaun storan untuk memastikan anda memilih nilai yang sesuai dalam cerapan khalayak.

1. Dalam cerapan khalayak, pilih nilai atau untuk medan berkaitan apabila melampirkan akaun storan.
   
1. Teruskan dengan langkah selebihnya dalam cerapan khalayak untuk melampirkan akaun storan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]