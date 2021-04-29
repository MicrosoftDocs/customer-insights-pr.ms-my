---
title: Eksport data Customer Insights ke Storan Blob Azure
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke storan Blob.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760246"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="f71fa-103">Eksport senarai segmen dan data lain ke Storan Blob Azure (pratonton)</span><span class="sxs-lookup"><span data-stu-id="f71fa-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="f71fa-104">Simpan data Customer Insights anda dalam storan Blob atau gunakannya untuk memindahkan data anda ke aplikasi lain.</span><span class="sxs-lookup"><span data-stu-id="f71fa-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="f71fa-105">Sediakan sambungan ke storan Blob</span><span class="sxs-lookup"><span data-stu-id="f71fa-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="f71fa-106">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="f71fa-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f71fa-107">Pilih **Tambah sambungan** dan pilih **Storan Blob Azure** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="f71fa-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="f71fa-108">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="f71fa-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f71fa-109">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="f71fa-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f71fa-110">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="f71fa-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f71fa-111">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="f71fa-111">Choose who can use this connection.</span></span> <span data-ttu-id="f71fa-112">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="f71fa-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f71fa-113">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f71fa-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f71fa-114">Masukkan **Nama akaun**, **Kunci akaun** dan **Bekas** untuk akaun storan Blob anda.</span><span class="sxs-lookup"><span data-stu-id="f71fa-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="f71fa-115">Untuk mengetahui lebih lanjut tentang cara untuk mencari nama akaun dan kekunci akaun storan Blob, lihat [Urus tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="f71fa-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="f71fa-116">Untuk mengetahui cara untuk mencipta bekas, lihat [Cipta bekas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="f71fa-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="f71fa-117">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="f71fa-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="f71fa-118">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="f71fa-118">Configure an export</span></span>

<span data-ttu-id="f71fa-119">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="f71fa-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f71fa-120">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f71fa-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f71fa-121">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="f71fa-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f71fa-122">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="f71fa-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f71fa-123">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Storan Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="f71fa-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="f71fa-124">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="f71fa-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f71fa-125">Pilih kotak di sebelah setiap entiti yang anda mahu eksport ke destinasi ini.</span><span class="sxs-lookup"><span data-stu-id="f71fa-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="f71fa-126">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="f71fa-126">Select **Save**.</span></span>

<span data-ttu-id="f71fa-127">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="f71fa-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f71fa-128">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f71fa-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="f71fa-129">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f71fa-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="f71fa-130">Data yang dieksport disimpan dalam bekas storan Blob yang anda konfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="f71fa-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="f71fa-131">Laluan folder berikut dicipta secara automatik dalam bekas anda:</span><span class="sxs-lookup"><span data-stu-id="f71fa-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="f71fa-132">Untuk entiti sumber dan entiti yang dijana oleh sistem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="f71fa-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="f71fa-133">Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="f71fa-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="f71fa-134">Model. json untuk entiti yang dieksport akan berada pada peringkat %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="f71fa-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="f71fa-135">Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="f71fa-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
