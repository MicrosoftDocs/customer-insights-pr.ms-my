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
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977388"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="a1ae0-103">Eksport data ke Azure Synapse Analytics (Pratonton)</span><span class="sxs-lookup"><span data-stu-id="a1ae0-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="a1ae0-104">Azure Synapse adalah perkhidmatan analitis yang mempercepatkan masa untuk wawasan merentasi gudang data dan sistem data besar.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="a1ae0-105">Anda boleh menginges dan menggunakan data Customer Insights anda dalam [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="a1ae0-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a1ae0-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="a1ae0-106">Prerequisites</span></span>

<span data-ttu-id="a1ae0-107">Prasyarat berikut mesti dipenuhi untuk mengkonfigurasi sambungan daripada Customer Insights ke Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="a1ae0-108">Pastikan untuk menetapkan semua **tugasan peranan** seperti yang diterangkan.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="a1ae0-109">Prasyarat dalam Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a1ae0-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="a1ae0-110">Anda mempunyai peranan **Pentadbir** dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="a1ae0-111">Ketahui lanjut tentang [Menetapkan keizinan pengguna dalam wawasan khalayak](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="a1ae0-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="a1ae0-112">Dalam Azure:</span><span class="sxs-lookup"><span data-stu-id="a1ae0-112">In Azure:</span></span> 

- <span data-ttu-id="a1ae0-113">Langganan Azure yang aktif.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-113">An active Azure subscription.</span></span>

- <span data-ttu-id="a1ae0-114">Jika menggunakan akaun Azure Data Lake Storage Gen2, *prinsipal perkhidmatan untuk wawasan khalayak* memerlukan keizinan **Penyumbang Data Blob Storan**.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="a1ae0-115">Ketahui lanjut tentang [menyambung ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure untuk wawasan khalayak](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a1ae0-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="a1ae0-116">Data Lake Storage Gen2 **mesti mempunyai** [ruang nama hierarki](/azure/storage/blobs/data-lake-storage-namespace) didayakan.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="a1ae0-117">Pada lokasi kumpulan sumber ruang kerja Azure Synapse, *prinsipal perkhidmatan* dan *pengguna untuk wawasan khalayak* perlu ditugaskan sekurang-kurangnya keizinan **Pembaca**.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="a1ae0-118">Untuk maklumat lanjut, lihat [Tugaskan peranan Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="a1ae0-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="a1ae0-119">*Pengguna* memerlukan keizinan **Penyumbang Data Blob Storan** pada akaun Azure Data Lake Storage Gen2 tempat data berada dan dipautkan ke ruang kerja Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="a1ae0-120">Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="a1ae0-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="a1ae0-121">*[Identiti terurus ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan keizinan **Penyumbang Data Blob Storan** pada akaun Azure Data Lake Storage Gen2 tempat data diletak dan dipaut ke ruang kerja Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="a1ae0-122">Ketahui lanjut tentang [menggunakan portal Azure untuk menugaskan peranan Azure mengakses ke blob dan data baris](/azure/storage/common/storage-auth-aad-rbac-portal) dan [Keizinan Penyumbang Data Blob Storan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="a1ae0-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="a1ae0-123">Pada ruang kerja Azure Synapse, *prinsipal perkhidmatan untuk wawasan khalayak* memerlukan peranan **Pentadbir Synapse** ditugaskan.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="a1ae0-124">Untuk maklumat lanjut, lihat [Cara menyediakan kawalan akses untuk ruang kerja Synapse anda](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="a1ae0-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="a1ae0-125">Sediakan sambungan dan eksport ke Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="a1ae0-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="a1ae0-126">Konfigurasikan sambungan</span><span class="sxs-lookup"><span data-stu-id="a1ae0-126">Configure a connection</span></span>

1. <span data-ttu-id="a1ae0-127">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a1ae0-128">Pilih **Tambah sambungan** dan pilih **Azure Synapse Analytics** atau pilih **Sediakan** pada jubin **Azure Synapse Analytics** untuk mengkonfigurasi sambungan.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="a1ae0-129">Berikan sambungan anda nama yang dikenali dalam medan Nama paparan.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="a1ae0-130">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="a1ae0-131">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a1ae0-132">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-132">Choose who can use this connection.</span></span> <span data-ttu-id="a1ae0-133">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a1ae0-134">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a1ae0-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a1ae0-135">Pilih atau cari langganan yang anda mahu menggunakan data Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="a1ae0-136">Sebaik sahaja langganan dipilih, anda boleh memilih **Ruang kerja**, **Akaun storan** dan **Bekas**.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="a1ae0-137">Pilih **Simpan** untuk menyimpan sambungan.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="a1ae0-138">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="a1ae0-138">Configure an export</span></span>

<span data-ttu-id="a1ae0-139">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a1ae0-140">Untuk maklumat lanjut, lihat [keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a1ae0-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a1ae0-141">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a1ae0-142">Untuk mencipta eksport baharu, pilih **Tambah eksport**.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="a1ae0-143">Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada bahagian **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="a1ae0-144">Jika anda tidak melihat nama bahagian ini, tiada [sambungan](connections.md) jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="a1ae0-145">Sediakan **Nama paparan** yang dikenali untuk eksport dan **Nama pangkalan data** anda.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="a1ae0-146">Pilih entiti yang anda mahu eksport ke Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="a1ae0-147">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-147">Select **Save**.</span></span>

<span data-ttu-id="a1ae0-148">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a1ae0-149">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a1ae0-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a1ae0-150">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a1ae0-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="a1ae0-151">Kemas kini eksport</span><span class="sxs-lookup"><span data-stu-id="a1ae0-151">Update an export</span></span>

1. <span data-ttu-id="a1ae0-152">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a1ae0-153">Pilih **Edit** pada eksport yang anda mahu kemas kini.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="a1ae0-154">**Tambah** atau **Alih Keluar** entiti daripada pemilihan.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="a1ae0-155">Jika entiti dialih keluar daripada pilihan, entiti tidak dipadamkan daripada pangkalan data Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="a1ae0-156">Walau bagaimanapun, penyegaran semula data masa akan datang tidak akan mengemas kini entiti yang dialih keluar dalam pangkalan data itu.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="a1ae0-157">**Mengubah Nama Pangkalan Data** mencipta pangkalan data Synapse Analytics baharu.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="a1ae0-158">Pangkalan data dengan nama yang dikonfigurasikan sebelum ini tidak akan menerima sebarang kemas kini dalam penyegaran semula masa akan datang.</span><span class="sxs-lookup"><span data-stu-id="a1ae0-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
