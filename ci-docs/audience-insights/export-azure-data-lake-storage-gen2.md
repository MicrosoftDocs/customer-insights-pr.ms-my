---
title: Eksport data Customer Insights ke Azure Data Lake Storage Gen2
description: Ketahui cara mengkonfigurasi sambungan ke Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760062"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="08bfb-103">Sediakan sambungan ke Azure Data Lake Storage Gen2 (pratonton)</span><span class="sxs-lookup"><span data-stu-id="08bfb-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="08bfb-104">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="08bfb-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="08bfb-105">Pilih **Tambah sambungan** dan pilih **Azure Data Lake Gen 2** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="08bfb-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="08bfb-106">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="08bfb-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="08bfb-107">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="08bfb-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="08bfb-108">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="08bfb-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="08bfb-109">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="08bfb-109">Choose who can use this connection.</span></span> <span data-ttu-id="08bfb-110">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="08bfb-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="08bfb-111">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="08bfb-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="08bfb-112">Masukkan **Nama akaun**, **Kekunci akaun** dan **Bekas** untuk Azure Data Lake Storage Gen2 anda.</span><span class="sxs-lookup"><span data-stu-id="08bfb-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="08bfb-113">Untuk mengetahui cara untuk mencipta akaun storan untuk digunakan dengan Azure Data Lake Storage Gen2, lihat [Cipta akaun storan](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="08bfb-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="08bfb-114">Untuk mengetahui lebih lanjut tentang storan nama akaun dan kekunci akaun Azure Data Lake Gen2, lihat [Urus tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="08bfb-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="08bfb-115">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="08bfb-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="08bfb-116">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="08bfb-116">Configure an export</span></span>

<span data-ttu-id="08bfb-117">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="08bfb-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="08bfb-118">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="08bfb-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="08bfb-119">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="08bfb-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="08bfb-120">Untuk mencipta eksport baharu, pilih **Tambah eksport**.</span><span class="sxs-lookup"><span data-stu-id="08bfb-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="08bfb-121">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="08bfb-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="08bfb-122">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="08bfb-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="08bfb-123">Pilih kotak di sebelah setiap entiti yang anda mahu eksport ke destinasi ini.</span><span class="sxs-lookup"><span data-stu-id="08bfb-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="08bfb-124">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="08bfb-124">Select **Save**.</span></span>

<span data-ttu-id="08bfb-125">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="08bfb-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="08bfb-126">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="08bfb-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="08bfb-127">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="08bfb-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="08bfb-128">Data yang dieksport disimpan dalam bekas storan Azure Data Lake Gen 2 yang anda konfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="08bfb-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
