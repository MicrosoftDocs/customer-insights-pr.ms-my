---
title: Sambung kepada akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan
description: Gunakan prinsipal perkhidmatan Azure untuk cerapan khalayak untuk menyambung ke data lake anda apabila memasukkannya ke cerapan khalayak.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644099"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="36594-103">Sambungkan cerapan khalayak ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure untuk cerapan khalayak</span><span class="sxs-lookup"><span data-stu-id="36594-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="36594-104">Alat automatik yang menggunakan perkhidmatan Azure harus sentiasa mempunyai keizinan terhad.</span><span class="sxs-lookup"><span data-stu-id="36594-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="36594-105">Daripada mempunyai daftar masuk aplikasi sebagai pengguna yang layak sepenuhnya, Azure menawarkan prinsipal perkhidmatan.</span><span class="sxs-lookup"><span data-stu-id="36594-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="36594-106">Teruskan membaca untuk mengetahui cara untuk menyambungkan cerapan khalayak dengan akaun Azure Data Lake Storage Gen2 menggunakan prinsipal perkhidmatan Azure dan bukannya kekunci akaun storan.</span><span class="sxs-lookup"><span data-stu-id="36594-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="36594-107">Anda boleh menggunakan prinsipal perkhidmatan untuk [menambah atau mengedit folder Common Data Model sebagai sumber data](connect-common-data-model.md) atau [mencipta persekitaran sedia ada atau kemas kini](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="36594-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="36594-108">Anda memerlukan keizinan pentadbir untuk langganan Azure anda untuk mencipta prinsipal perkhidmatan.</span><span class="sxs-lookup"><span data-stu-id="36594-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="36594-109">Cipta prinsipal perkhidmatan Azure untuk cerapan khalayak</span><span class="sxs-lookup"><span data-stu-id="36594-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="36594-110">Sebelum mencipta prinsipal perkhidmatan baharu untuk cerapan khalayak, semak sama ada ia sudah wujud dalam organisasi anda.</span><span class="sxs-lookup"><span data-stu-id="36594-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="36594-111">Cari prinsipal perkhidmatan sedia ada</span><span class="sxs-lookup"><span data-stu-id="36594-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="36594-112">Pergi ke [Portal pentadbir Azure](https://portal.azure.com) dan daftar masuk ke organisasi anda.</span><span class="sxs-lookup"><span data-stu-id="36594-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="36594-113">Pilih **Azure Active Directory** daripada perkhidmatan Azure.</span><span class="sxs-lookup"><span data-stu-id="36594-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="36594-114">Di bawah **Urus**, pilih **Aplikasi Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="36594-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="36594-115">Cari ID aplikasi cerapan khalayak pihak pertama `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` atau nama `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="36594-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="36594-116">Jika anda menemui rekod yang sepadan, ia bermaksud bahawa prinsipal perkhidmatan untuk cerapan khalayak wujud.</span><span class="sxs-lookup"><span data-stu-id="36594-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="36594-117">Anda tidak perlu memasang ia lagi.</span><span class="sxs-lookup"><span data-stu-id="36594-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Yangkapan skrin yang menunjukkan prinsipal perkhidmatan sedia ada.":::
   
6. <span data-ttu-id="36594-119">Jika tiada hasil dikembalikan, cipta prinsipal perkhidmatan baharu.</span><span class="sxs-lookup"><span data-stu-id="36594-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="36594-120">Cipta prinsipal perkhidmatan baharu</span><span class="sxs-lookup"><span data-stu-id="36594-120">Create a new service principal</span></span>

1. <span data-ttu-id="36594-121">Pasang versi terkini bagi **Azure Active Directory PowerShell untuk Graf**.</span><span class="sxs-lookup"><span data-stu-id="36594-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="36594-122">Untuk maklumat lanjut, lihat [Pasang Azure Active Directory PowerShell untuk Graf](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="36594-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="36594-123">Pada PC anda, pilih kekunci Windows pada papan kekunci anda dan gelintar untuk **Windows PowerShell** dan **Jalankan sebagai Pentadbir**.</span><span class="sxs-lookup"><span data-stu-id="36594-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="36594-124">Dalam tetingkap PowerShell yang terbuka, masukkan `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="36594-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="36594-125">Cipta prinsipal perkhidmatan untuk cerapan khalayak dengan Modul Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36594-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="36594-126">Dalam tetingkap PowerShell, masukkan `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="36594-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="36594-127">Gantikan "ID penyewa anda" dengan ID penyewa anda yang sebenar yang anda mahu cipta prinsipal perkhidmatan.</span><span class="sxs-lookup"><span data-stu-id="36594-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="36594-128">Parameter nama persekitaran `AzureEnvironmentName` adalah pilihan.</span><span class="sxs-lookup"><span data-stu-id="36594-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="36594-129">Masukkan `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="36594-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="36594-130">Perintah ini mencipta prinsipal perkhidmatan untuk cerapan khalayak pada penyewa yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="36594-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="36594-131">Berikan keizinan kepada prinsipal perkhidmatan untuk mengakses akaun storan</span><span class="sxs-lookup"><span data-stu-id="36594-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="36594-132">Pergi ke portal Azure untuk memberikan keizinan kepada prinsipal perkhidmatan untuk akaun storan yang anda mahu gunakan dalam cerapan khalayak.</span><span class="sxs-lookup"><span data-stu-id="36594-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="36594-133">Pergi ke [Portal pentadbir Azure](https://portal.azure.com) dan daftar masuk ke organisasi anda.</span><span class="sxs-lookup"><span data-stu-id="36594-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="36594-134">Buka akaun storan yang anda mahu asas perkhidmatan untuk cerapan khalayak untuk mempunyai akses kepadanya.</span><span class="sxs-lookup"><span data-stu-id="36594-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="36594-135">Pilih **Kawalan capaian (IAM)** daripada tetingkap navigasi dan pilih **Tambah** > **Tambah tugasan peranan**.</span><span class="sxs-lookup"><span data-stu-id="36594-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Tangkapan skrin menunjukkan portal Azure sambil menambah tugasan peranan.":::
   
1. <span data-ttu-id="36594-137">Dalam anak tetingkap **Tambah tugasan peranan**, tetapkan sifat berikut:</span><span class="sxs-lookup"><span data-stu-id="36594-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="36594-138">Peranan: *Penyumbang Blob Data Storan*</span><span class="sxs-lookup"><span data-stu-id="36594-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="36594-139">Tugaskan akses kepada: *Pengguna, kumpulan atau prinsipal perkhidmatan*</span><span class="sxs-lookup"><span data-stu-id="36594-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="36594-140">Pilih: *Dynamics 365 AI untuk Customer Insights* ([prinsipal perkhidmatan yang anda cipta](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="36594-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="36594-141">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="36594-141">Select **Save**.</span></span>

<span data-ttu-id="36594-142">Prses boleh mengambil masa sehingga 15 minit menyebarkan perubahan.</span><span class="sxs-lookup"><span data-stu-id="36594-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="36594-143">Masukkan ID Sumber Azure atau butiran Langganan Azure dalam lampiran akaun storan kepada Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="36594-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="36594-144">Lampirkan akaun storan Azure Data Lake cerapan khalayak untuk [menyimpan data output](manage-environments.md) atau [menggunakannya sebagai sumber data](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="36594-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="36594-145">Memilih pilihan Azure Data Lake membolehkan anda memilih antara pendekatan berasaskan sumber atau berasaskan langganan.</span><span class="sxs-lookup"><span data-stu-id="36594-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="36594-146">Ikuti langkah di bawah untuk menyediakan maklumat yang diperlukan tentang pendekatan yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="36594-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="36594-147">Sambungan akaun storan berdasarkan sumber</span><span class="sxs-lookup"><span data-stu-id="36594-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="36594-148">Pergi ke [Portal pentadbir Azure](https://portal.azure.com), daftar masuk ke langganan anda dan buka akaun storan anda.</span><span class="sxs-lookup"><span data-stu-id="36594-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="36594-149">Pergi ke **Tetapan** > **Sifat** pada tetingkap navigasi.</span><span class="sxs-lookup"><span data-stu-id="36594-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="36594-150">Salin nilai ID sumber akaun storan:</span><span class="sxs-lookup"><span data-stu-id="36594-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salin ID sumber akaun storan.":::

1. <span data-ttu-id="36594-152">Dalam cerapan khalayak, masukkan ID sumber dalam medan sumber dipaparkan dalam skrin sambungan akaun storan.</span><span class="sxs-lookup"><span data-stu-id="36594-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Masukkan maklumat ID sumber akaun storan.":::   
   
1. <span data-ttu-id="36594-154">Teruskan dengan langkah selebihnya dalam cerapan khalayak untuk melampirkan akaun storan.</span><span class="sxs-lookup"><span data-stu-id="36594-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="36594-155">Sambungan akaun storan berdasarkan langganan</span><span class="sxs-lookup"><span data-stu-id="36594-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="36594-156">Pergi ke [Portal pentadbir Azure](https://portal.azure.com), daftar masuk ke langganan anda dan buka akaun storan anda.</span><span class="sxs-lookup"><span data-stu-id="36594-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="36594-157">Pergi ke **Tetapan** > **Sifat** pada tetingkap navigasi.</span><span class="sxs-lookup"><span data-stu-id="36594-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="36594-158">Semak **Langganan**, **Kumpulan sumber** dan **Nama** akaun storan untuk memastikan anda memilih nilai yang sesuai dalam cerapan khalayak.</span><span class="sxs-lookup"><span data-stu-id="36594-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="36594-159">Dalam cerapan khalayak, pilih nilai atau untuk medan berkaitan apabila melampirkan akaun storan.</span><span class="sxs-lookup"><span data-stu-id="36594-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Masukkan maklumat ID sumber akaun storan.":::
   
1. <span data-ttu-id="36594-161">Teruskan dengan langkah selebihnya dalam cerapan khalayak untuk melampirkan akaun storan.</span><span class="sxs-lookup"><span data-stu-id="36594-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
