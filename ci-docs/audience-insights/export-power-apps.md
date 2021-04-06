---
title: Penyambung Power Apps
description: Sambung dengan Power Apps and Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598166"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="9d2ce-103">Penyambung Microsoft Power Apps (pratonton)</span><span class="sxs-lookup"><span data-stu-id="9d2ce-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="9d2ce-104">Bawa profil pelanggan disatukan ke dalam aplikasi diperibadikan anda Power Apps.</span><span class="sxs-lookup"><span data-stu-id="9d2ce-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="9d2ce-105">Sambung Power Apps dan Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9d2ce-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="9d2ce-106">Customer Insights ialah salah satu daripada banyak [sumber yang tersedia untuk data dalam Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="9d2ce-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="9d2ce-107">Rujuk kepada dokumentasi Power Apps untuk mengetahui cara untuk [menambah sambungan data kepada aplikasi](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="9d2ce-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="9d2ce-108">Kami juga mengesyorkan anda mengulas [cara Power Apps menggunakan perwakilan untuk mengendalikan set data yang besar dalam aplikasi Kanvas](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="9d2ce-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="9d2ce-109">Entiti tersedia</span><span class="sxs-lookup"><span data-stu-id="9d2ce-109">Available entities</span></span>

<span data-ttu-id="9d2ce-110">Selepas menambah Customer Insights sebagai sambungan data, anda boleh memilih entiti berikut dalam Power Apps:</span><span class="sxs-lookup"><span data-stu-id="9d2ce-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="9d2ce-111">Pelanggan: untuk menggunakan data daripada [profil pelanggan disatukan](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9d2ce-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="9d2ce-112">UnifiedActivity: untuk memaparkan [garis masa aktiviti](activities.md) pada aplikasi.</span><span class="sxs-lookup"><span data-stu-id="9d2ce-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="9d2ce-113">Had</span><span class="sxs-lookup"><span data-stu-id="9d2ce-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="9d2ce-114">Entiti boleh diperoleh</span><span class="sxs-lookup"><span data-stu-id="9d2ce-114">Retrievable entities</span></span>

<span data-ttu-id="9d2ce-115">Anda hanya boleh memperoleh entiti **Pelanggan**, **Aktiviti Disatukan** dan **Segmen** melalui penyambung Power Apps.</span><span class="sxs-lookup"><span data-stu-id="9d2ce-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="9d2ce-116">Entiti lain ditunjukkan kerana penyambung asas menyokongnya melalui pencetus dalam Power Automate.</span><span class="sxs-lookup"><span data-stu-id="9d2ce-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="9d2ce-117">Perwakilan</span><span class="sxs-lookup"><span data-stu-id="9d2ce-117">Delegation</span></span>

<span data-ttu-id="9d2ce-118">Kerja penugasan untuk entiti Pelanggan dan entiti Aktiviti Disatukan.</span><span class="sxs-lookup"><span data-stu-id="9d2ce-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="9d2ce-119">Delegasi untuk entiti **Pelanggan**: Untuk menggunakan delegasi untuk entiti ini, medan perlu diindeks dalam [Indeks carian & penapis](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="9d2ce-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="9d2ce-120">Penugasan untuk **Aktiviti Disatukan**: Penugasan untuk entiti ini hanya berfungsi untuk medan **ActivityId** dan **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="9d2ce-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="9d2ce-121">Untuk maklumat lanjut tentang penugasan, lihat [Fungsi dan operasi boleh ditugaskan Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="9d2ce-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="9d2ce-122">Contoh kawalan galeri</span><span class="sxs-lookup"><span data-stu-id="9d2ce-122">Example gallery control</span></span>

<span data-ttu-id="9d2ce-123">Sebagai contoh, anda menambahkan profil pelanggan ke [kawalan galeri](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="9d2ce-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="9d2ce-124">Tambah kawalan **Galeri** kepada aplikasi yang anda sedang bina.</span><span class="sxs-lookup"><span data-stu-id="9d2ce-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9d2ce-125">![Tambah elemen galeri](media/connector-powerapps9.png "Tambah elemen galeri")</span><span class="sxs-lookup"><span data-stu-id="9d2ce-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="9d2ce-126">Pilih **Pelanggan** sebagai sumber data untuk item.</span><span class="sxs-lookup"><span data-stu-id="9d2ce-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9d2ce-127">![Pilih sumber data](media/choose-datasource-powerapps.png "Pilih sumber data")</span><span class="sxs-lookup"><span data-stu-id="9d2ce-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="9d2ce-128">Anda boleh mengubah panel data pada bahagian kanan untuk memilih medan bagi entiti Pelanggan untuk ditunjukkan pada galeri.</span><span class="sxs-lookup"><span data-stu-id="9d2ce-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="9d2ce-129">Jika anda mahu menunjukkan mana-mana medan daripada pelanggan terpilih pada galeri, isikan sifat Teks bagi label:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="9d2ce-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="9d2ce-130">Contoh: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="9d2ce-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="9d2ce-131">Untuk memaparkan garis masa yang disatukan untuk pelanggan, tambahan elemen Galeri dan tambahkan sifat Item: **Penapis('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="9d2ce-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="9d2ce-132">Contoh: Penapis('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="9d2ce-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]