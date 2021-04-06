---
title: Lihat profil pelanggan
description: Dapatkan pandangan gabungan data pelanggan disatukan anda.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596878"
---
# <a name="customer-profiles"></a><span data-ttu-id="44ade-103">Profil pelanggan</span><span class="sxs-lookup"><span data-stu-id="44ade-103">Customer profiles</span></span>

<span data-ttu-id="44ade-104">Halaman **Pelanggan** menunjukkan pandangan gabungan pelanggan anda, berdasarkan data profil yang dikumpulkan daripada [semua sumber data](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="44ade-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="44ade-105">Profil pelanggan tersedia sebaik sahaja anda [mencipta entiti Pelanggan disatukan](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="44ade-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="44ade-106">Pastikan anda melengkapkan proses penyatuan data untuk mendapatkan lebih banyak pandangan tentang pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="44ade-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="44ade-107">Halaman itu juga membenarkan anda membuat carian untuk pelanggan.</span><span class="sxs-lookup"><span data-stu-id="44ade-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="44ade-108">Pelanggan boleh individu atau organisasi (pratonton).</span><span class="sxs-lookup"><span data-stu-id="44ade-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="44ade-109">Setiap profil pelanggan atau organisasi diwakili oleh jubin.</span><span class="sxs-lookup"><span data-stu-id="44ade-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="44ade-110">Pilih jubin untuk melihat maklumat tambahan tentang pelanggan atau organisasi tertentu.</span><span class="sxs-lookup"><span data-stu-id="44ade-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="44ade-111">Gunakan kawalan penomboran halaman pada bahagian bawah halaman untuk melihat rekod tambahan.</span><span class="sxs-lookup"><span data-stu-id="44ade-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="44ade-112">![Profil pelanggan B2C](media/profiles-customers.png "Profil pelanggan B2C")</span><span class="sxs-lookup"><span data-stu-id="44ade-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="44ade-113">Organisasi (Pratonton)</span><span class="sxs-lookup"><span data-stu-id="44ade-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="44ade-114">![Profil pelanggan B2B](media/profile-customers-b2b.png "Profil pelanggan B2B")</span><span class="sxs-lookup"><span data-stu-id="44ade-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="44ade-115">Jika anda tidak dapat melihat jubin apabila anda memilih **Pelanggan** dalam navigasi, pentadbir anda perlu untuk [mentakrifkan sekurang-kurangnya satu atribut yang boleh dicari](search-filter-index.md) pada **Indeks carian & penapis**.</span><span class="sxs-lookup"><span data-stu-id="44ade-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="44ade-116">Carian untuk pelanggan</span><span class="sxs-lookup"><span data-stu-id="44ade-116">Search for customers</span></span>

<span data-ttu-id="44ade-117">Carian untuk pelanggan dengan memasukkan nama atau beberapa atribut yang lain dalam kotak carian.</span><span class="sxs-lookup"><span data-stu-id="44ade-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="44ade-118">Carian hanya berfungsi dalam entiti Profil Pelanggan yang dicipta semasa proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="44ade-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="44ade-119">Sebagai pentadbir, anda boleh konfigurasikan atribut boleh dicari menggunakan halaman **Indeks Carian & Tapis**.</span><span class="sxs-lookup"><span data-stu-id="44ade-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="44ade-120">Untuk maklumat lanjut, lihat [Mengurus indeks carian & tapis](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="44ade-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="44ade-121">Tapis pelanggan</span><span class="sxs-lookup"><span data-stu-id="44ade-121">Filter customers</span></span>

<span data-ttu-id="44ade-122">Anda boleh menapis pelanggan dengan medan entiti Profil Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="44ade-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="44ade-123">Sama seperti carian, pada mulanya pentadbir anda perlu menakrif medan sebagai boleh ditapis menggunakan halaman **Indeks Carian & Tapis**.</span><span class="sxs-lookup"><span data-stu-id="44ade-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="44ade-124">Pilih **Tapis** pada halaman **Pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="44ade-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="44ade-125">Tandakan kotak di sebelah atribut bagi menapis pelanggan mengikut kemahuan anda.</span><span class="sxs-lookup"><span data-stu-id="44ade-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="44ade-126">![Profil pelanggan](media/profiles-customers3.png "Profil pelanggan")</span><span class="sxs-lookup"><span data-stu-id="44ade-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="44ade-127">Alih keluar penapis anda dengan memilih **Kosongkan penapis** pada halaman **Pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="44ade-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="44ade-128">Halaman butiran pelanggan</span><span class="sxs-lookup"><span data-stu-id="44ade-128">Customer details page</span></span>

<span data-ttu-id="44ade-129">Pilih sebarang jubin pelanggan untuk membuka **halaman butiran pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="44ade-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="44ade-130">Pandangan ini mengandungi maklumat disatukan untuk pelanggan terpilih.</span><span class="sxs-lookup"><span data-stu-id="44ade-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="44ade-131">Butiran pelanggan termasuk:</span><span class="sxs-lookup"><span data-stu-id="44ade-131">Customer details include:</span></span>

-   <span data-ttu-id="44ade-132">**Jubin profil pelanggan:** Jubin ini menunjukkan nilai berbeza daripada entiti profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="44ade-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="44ade-133">Butiran ini boleh termasuk alamat e-mel, nama, bandar dan sebagainya.</span><span class="sxs-lookup"><span data-stu-id="44ade-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="44ade-134">**Kemungkinan minat, bakal jenama:** Menunjukkan jika anda mengkonfigurasi pengayaan pihak pertama.</span><span class="sxs-lookup"><span data-stu-id="44ade-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="44ade-135">Ia mewakili kepentingan yang berkemungkinan dan afiniti untuk jenama pelanggan dengan profil yang serupa dengan pelanggan ini mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="44ade-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="44ade-136">Untuk maklumat lanjut, lihat [Perkayakan profil pelanggan. dengan afiniti jenama dan kepentingan](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="44ade-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="44ade-137">**Langkah:** Menunjukkan jika anda mengkonfigurasi satu atau lebih langkah daripada jenis khusus: langkah atribut pelanggan.</span><span class="sxs-lookup"><span data-stu-id="44ade-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="44ade-138">Ia termasuk KPI yang dikira pada pelanggan anda pada peringkat pelanggan individu.</span><span class="sxs-lookup"><span data-stu-id="44ade-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="44ade-139">Untuk maklumat lanjut, lihat [Langkah mentakrif dan mengurus](measures.md).</span><span class="sxs-lookup"><span data-stu-id="44ade-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="44ade-140">**Garis masa aktiviti:** Menunjukkan jika anda telah mengkonfigurasi aktiviti.</span><span class="sxs-lookup"><span data-stu-id="44ade-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="44ade-141">Pandangan garis masa mengandungi aktiviti yang disusun secara kronologi pada pelanggan ini, bermula dengan aktiviti paling terkini.</span><span class="sxs-lookup"><span data-stu-id="44ade-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="44ade-142">Untuk maklumat lanjut, lihat [Aktiviti pelanggan](activities.md).</span><span class="sxs-lookup"><span data-stu-id="44ade-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="44ade-143">Pilih **kembali ke Pelanggan** untuk kembali ke halaman carian pelanggan.</span><span class="sxs-lookup"><span data-stu-id="44ade-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="44ade-144">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="44ade-144">Next steps</span></span>

<span data-ttu-id="44ade-145">[Tambah lebih banyak sumber data](data-sources.md) atau [cipta segmen pelanggan](segments.md).</span><span class="sxs-lookup"><span data-stu-id="44ade-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]