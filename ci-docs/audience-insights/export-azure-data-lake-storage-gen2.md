---
title: Eksport data Customer Insights ke Azure Data Lake Storage Gen2
description: Ketahui cara mengkonfigurasi sambungan ke Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477190"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="9a072-103">Penyambung untuk Azure Data Lake Storage Gen2 (pratonton)</span><span class="sxs-lookup"><span data-stu-id="9a072-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="9a072-104">Simpan data Customer Insights anda dalam Azure Data Lake Storage Gen2 atau gunakannya untuk memindahkan data anda kepada aplikasi lain.</span><span class="sxs-lookup"><span data-stu-id="9a072-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="9a072-105">Konfigurasikan penyambung untuk Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="9a072-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="9a072-106">Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.</span><span class="sxs-lookup"><span data-stu-id="9a072-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9a072-107">Di bawah **Azure Data Lake Storage Gen2**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="9a072-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="9a072-108">Berikan destinasi anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="9a072-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9a072-109">Masukkan **Nama akaun**, **Kekunci akaun** dan **Bekas** untuk Azure Data Lake Storage Gen2 anda.</span><span class="sxs-lookup"><span data-stu-id="9a072-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="9a072-110">Untuk mengetahui cara untuk mencipta akaun storan untuk digunakan dengan Azure Data Lake Storage Gen2, lihat [Cipta akaun storan](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="9a072-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="9a072-111">Untuk mengetahui lanjut tentang cara mencari nama akaun dan kunci akaun storan Data Lake Azure Gen2, lihat [Urus tetapan akaun storan dalam portal Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="9a072-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="9a072-112">Pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="9a072-112">Select **Next**.</span></span>

1. <span data-ttu-id="9a072-113">Pilih kotak di sebelah setiap entiti yang anda mahu eksport ke destinasi ini.</span><span class="sxs-lookup"><span data-stu-id="9a072-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="9a072-114">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="9a072-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9a072-115">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="9a072-115">Export the data</span></span>

<span data-ttu-id="9a072-116">Anda boleh [eksport data atas permintaan](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9a072-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="9a072-117">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9a072-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
