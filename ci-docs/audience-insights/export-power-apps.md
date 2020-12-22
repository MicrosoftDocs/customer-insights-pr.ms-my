---
title: Penyambung Power Apps
description: Sambung dengan Power Apps and Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406436"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="c99b1-103">Penyambung Microsoft Power Apps (pratonton)</span><span class="sxs-lookup"><span data-stu-id="c99b1-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="c99b1-104">Bawa profil pelanggan disatukan ke dalam aplikasi diperibadikan anda Power Apps.</span><span class="sxs-lookup"><span data-stu-id="c99b1-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="c99b1-105">Sambung Power Apps dan Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c99b1-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="c99b1-106">Customer Insights ialah salah satu daripada banyak [sumber yang tersedia untuk data dalam Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="c99b1-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="c99b1-107">Rujuk kepada dokumentasi Power Apps untuk mengetahui cara untuk [menambah sambungan data kepada aplikasi](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="c99b1-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="c99b1-108">Kami juga mengesyorkan anda mengulas [cara Power Apps menggunakan perwakilan untuk mengendalikan set data yang besar dalam aplikasi Kanvas](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="c99b1-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="c99b1-109">Entiti tersedia</span><span class="sxs-lookup"><span data-stu-id="c99b1-109">Available entities</span></span>

<span data-ttu-id="c99b1-110">Selepas menambah Customer Insights sebagai sambungan data, anda boleh memilih entiti berikut dalam Power Apps:</span><span class="sxs-lookup"><span data-stu-id="c99b1-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="c99b1-111">Pelanggan: untuk menggunakan data daripada [profil pelanggan disatukan](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c99b1-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="c99b1-112">Aktiviti Pelanggan Disatukan: untuk memaparkan [garis masa](activities.md) pada aplikasi.</span><span class="sxs-lookup"><span data-stu-id="c99b1-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="c99b1-113">Had</span><span class="sxs-lookup"><span data-stu-id="c99b1-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="c99b1-114">Entiti boleh diperoleh</span><span class="sxs-lookup"><span data-stu-id="c99b1-114">Retrievable entities</span></span>

<span data-ttu-id="c99b1-115">Anda hanya boleh memperoleh entiti **Pelanggan**, **Aktiviti Disatukan** dan **Segmen** melalui penyambung Power Apps.</span><span class="sxs-lookup"><span data-stu-id="c99b1-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="c99b1-116">Entiti lain ditunjukkan kerana penyambung asas menyokongnya melalui pencetus dalam Power Automate.</span><span class="sxs-lookup"><span data-stu-id="c99b1-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="c99b1-117">Perwakilan</span><span class="sxs-lookup"><span data-stu-id="c99b1-117">Delegation</span></span>

<span data-ttu-id="c99b1-118">Kerja penugasan untuk entiti Pelanggan dan entiti Aktiviti Disatukan.</span><span class="sxs-lookup"><span data-stu-id="c99b1-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="c99b1-119">Delegasi untuk entiti **Pelanggan**: Untuk menggunakan delegasi untuk entiti ini, medan perlu diindeks dalam [Indeks carian & penapis](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="c99b1-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="c99b1-120">Penugasan untuk **Aktiviti Disatukan**: Penugasan untuk entiti ini hanya berfungsi untuk medan **ActivityId** dan **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="c99b1-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="c99b1-121">Untuk maklumat lanjut tentang penugasan, lihat [Fungsi dan operasi boleh ditugaskan Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="c99b1-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="c99b1-122">Contoh kawalan galeri</span><span class="sxs-lookup"><span data-stu-id="c99b1-122">Example gallery control</span></span>

<span data-ttu-id="c99b1-123">Sebagai contoh, anda menambahkan profil pelanggan ke [kawalan galeri](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="c99b1-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="c99b1-124">Tambah kawalan **Galeri** kepada aplikasi yang anda sedang bina.</span><span class="sxs-lookup"><span data-stu-id="c99b1-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c99b1-125">![Tambah elemen galeri](media/connector-powerapps9.png "Tambah elemen galeri")</span><span class="sxs-lookup"><span data-stu-id="c99b1-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="c99b1-126">Pilih **Pelanggan** sebagai sumber data untuk item.</span><span class="sxs-lookup"><span data-stu-id="c99b1-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c99b1-127">![Pilih sumber data](media/choose-datasource-powerapps.png "Pilih sumber data")</span><span class="sxs-lookup"><span data-stu-id="c99b1-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="c99b1-128">Anda boleh mengubah panel data pada bahagian kanan untuk memilih medan bagi entiti Pelanggan untuk ditunjukkan pada galeri.</span><span class="sxs-lookup"><span data-stu-id="c99b1-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="c99b1-129">Jika anda mahu menunjukkan mana-mana medan daripada pelanggan terpilih pada galeri, isikan sifat Teks bagi label:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="c99b1-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="c99b1-130">Contoh: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="c99b1-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="c99b1-131">Untuk memaparkan garis masa yang disatukan untuk pelanggan, tambahan elemen Galeri dan tambahkan sifat Item: **Penapis('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="c99b1-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="c99b1-132">Contoh: Penapis('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="c99b1-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
