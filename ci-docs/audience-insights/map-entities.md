---
title: Petakan entiti untuk penyatuan data
description: Petakan data untuk mencipta profil pelanggan disatukan.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596004"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="62738-103">Petakan entiti dan atribut</span><span class="sxs-lookup"><span data-stu-id="62738-103">Map entities and attributes</span></span>

<span data-ttu-id="62738-104">**Peta** ialah peringkat pertama dalam proses data penyatuan Insights khalayak.</span><span class="sxs-lookup"><span data-stu-id="62738-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="62738-105">Pemetaan terdiri daripada tiga fasa:</span><span class="sxs-lookup"><span data-stu-id="62738-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="62738-106">*Pemilihan entiti*: Kenal pasti entiti boleh gabung yang membawa kepada set data dengan maklumat yang lebih lengkap tentang pelanggan.</span><span class="sxs-lookup"><span data-stu-id="62738-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="62738-107">*Pemilihan atribut*: Bagi setiap entiti, kenal pasti lajur yang anda mahu gabung dan selaraskan dalam peringkat *padan* dan *gabung*.</span><span class="sxs-lookup"><span data-stu-id="62738-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="62738-108">Lajur ini dipanggil *Atribut*.</span><span class="sxs-lookup"><span data-stu-id="62738-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="62738-109">*Kekunci utama dan pilihan jenis semantik*: Untuk setiap entiti, kenal pasti atribut yang anda mahu takrifkan sebagai kekunci utama untuk entiti tersebut dan untuk setiap atribut, kenal pasti jenis semantik yang terbaik menggambarkan atribut tersebut.</span><span class="sxs-lookup"><span data-stu-id="62738-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="62738-110">Untuk maklumat lanjut tentang aliran penyatuan data umum , lihat [Satukan](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="62738-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="62738-111">Pilih entiti pertama</span><span class="sxs-lookup"><span data-stu-id="62738-111">Select the first entities</span></span>

1. <span data-ttu-id="62738-112">Dalam Insights khalayak, pergi ke **Data** > **Unify** > **Padan**.</span><span class="sxs-lookup"><span data-stu-id="62738-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="62738-113">Mulakan fasa pemetaan dengan memilih **Pilih entiti**.</span><span class="sxs-lookup"><span data-stu-id="62738-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="62738-114">Pilih entiti dan atribut yang anda mahu gunakan dalam fasa *padanan* dan *gabungan*.</span><span class="sxs-lookup"><span data-stu-id="62738-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="62738-115">Anda boleh memilih atribut yang diperlukan secara individu daripada entiti atau memasukkan semua atribut daripada entiti dengan memilih kotak semak **Memasukkan semua medan** pada peringkat entiti.</span><span class="sxs-lookup"><span data-stu-id="62738-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="62738-116">Kami mengesyorkan pemilihan sekurang-kurangnya dua entiti untuk mendapat manfaat daripada proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="62738-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="62738-117">![Tambah contoh entiti](media/data-manager-configure-map-add-entities-example.png "Tambah contoh entiti")</span><span class="sxs-lookup"><span data-stu-id="62738-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="62738-118">Dalam contoh ini, kami menambahkan entiti **eCommerceContacts** dan **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="62738-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="62738-119">Dengan memilih entiti ini, anda boleh memperoleh wawasan yang pelanggan perniagaan online ialah ahli program kesetiaan.</span><span class="sxs-lookup"><span data-stu-id="62738-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="62738-120">Anda boleh mencari pada kata kunci merentasi semua atribut dan entiti untuk memilih atribut yang diperlukan yang anda mahu petakan.</span><span class="sxs-lookup"><span data-stu-id="62738-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="62738-121">![Contoh medan carian](media/data-manager-configure-map-search-fields-example.png "Contoh medan carian")</span><span class="sxs-lookup"><span data-stu-id="62738-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="62738-122">Pilih **Gunakan** untuk mengesahkan pilihan anda.</span><span class="sxs-lookup"><span data-stu-id="62738-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="62738-123">Pilih kekunci utama dan jenis semantik untuk atribut</span><span class="sxs-lookup"><span data-stu-id="62738-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="62738-124">Selepas memilih entiti anda, halaman **Peta** menyenaraikan entiti yang dipilih untuk ulasan anda.</span><span class="sxs-lookup"><span data-stu-id="62738-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="62738-125">Takrifkan kekunci utama untuk entiti dan kenal pasti jenis semantik untuk atribut dalam entiti.</span><span class="sxs-lookup"><span data-stu-id="62738-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="62738-126">**Kekunci utama**: Pilih satu atribut sebagai kekunci utama untuk setiap entiti anda.</span><span class="sxs-lookup"><span data-stu-id="62738-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="62738-127">Untuk atribut menjadi kekunci utama yang sah, ia tidak boleh mengandungi nilai pendua, nilai yang hilang atau nilai tak sah.</span><span class="sxs-lookup"><span data-stu-id="62738-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="62738-128">Atribut jenis data rentetan, integer dan GUID disokong sebagai kekunci utama dan akan dipaparkan dalam medan untuk anda pilih.</span><span class="sxs-lookup"><span data-stu-id="62738-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="62738-129">**Jenis atribut semantik**: Kategori atribut anda, seperti alamat e-mel atau nama.</span><span class="sxs-lookup"><span data-stu-id="62738-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="62738-130">Untuk menggunakan model AI untuk ramalan pintar semantik, jimatkan masa dan tingkatkan ketepatan, tetapkan **Pemetaan pintar** kepada **HIDUPKAN**.</span><span class="sxs-lookup"><span data-stu-id="62738-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="62738-131">Pemetaan pintar menyerlahkan pengesyoran semantik berasaskan AI dalam medan **Jenis**.</span><span class="sxs-lookup"><span data-stu-id="62738-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="62738-132">Jika anda menetapkan ia kepada **MATIKAN**, anda akan melihat pengesyoran pemetaan biasa kami.</span><span class="sxs-lookup"><span data-stu-id="62738-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="62738-133">Anda boleh memilih sebarang jenis semantik daripada senarai pilihan tersedia dan mengatasi pilihan yang disyorkan.</span><span class="sxs-lookup"><span data-stu-id="62738-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="62738-134">![Jenis atribut dan ramalan semantik](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Jenis atribut dan ramalan semantik")</span><span class="sxs-lookup"><span data-stu-id="62738-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="62738-135">Menambah jenis semantik entiti tersuai juga boleh dilakukan.</span><span class="sxs-lookup"><span data-stu-id="62738-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="62738-136">Pilih jenis medan untuk atribut itu dan taip nama jenis semantik tersuai anda.</span><span class="sxs-lookup"><span data-stu-id="62738-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="62738-137">Cara ini, anda juga boleh mengubah jenis atribut yang dikenal pasti oleh sistem.</span><span class="sxs-lookup"><span data-stu-id="62738-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="62738-138">Semua atribut yang jenis semantik dikenal pasti secara automatik dikumpulkan dalam bahagian **Ulasan medan yang dipetakan**.</span><span class="sxs-lookup"><span data-stu-id="62738-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="62738-139">Mengulas atribut ini dan jenis semantik kerana ia akan digunakan untuk menggabungkan entiti anda dalam langkah gabungan data penyatuan.</span><span class="sxs-lookup"><span data-stu-id="62738-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="62738-140">Atribut yang tidak dipetakan secara automatik kepada jenis semantik dikumpulkan dalam bahagian **Takrifkan data dalam bahagian medan tidak dipetakan**.</span><span class="sxs-lookup"><span data-stu-id="62738-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="62738-141">Pilih medan jenis semantik untuk atribut yang tidak dipetakan atau masukkan nama jenis atribut tersuai anda.</span><span class="sxs-lookup"><span data-stu-id="62738-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="62738-142">![Kekunci utama dan jenis atribut](media/data-manager-configure-map-add-attributes.png "Kekunci utama dan jenis atribut")</span><span class="sxs-lookup"><span data-stu-id="62738-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="62738-143">Satu medan perlu dipetakan kepada jenis semantik Person.FullName untuk mengisi nama pelanggan dalam kad pelanggan.</span><span class="sxs-lookup"><span data-stu-id="62738-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="62738-144">Jika tidak, kad pelanggan akan muncul tanpa nama.</span><span class="sxs-lookup"><span data-stu-id="62738-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="62738-145">Tambah dan alih keluar atribut dan entiti</span><span class="sxs-lookup"><span data-stu-id="62738-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="62738-146">Pada **Satukan** > **Peta**, pilih **Edit medan**.</span><span class="sxs-lookup"><span data-stu-id="62738-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="62738-147">Dalam anak tetingkap **Edit medan**, tambah atau alih keluar atribut dan entiti.</span><span class="sxs-lookup"><span data-stu-id="62738-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="62738-148">Gunakan carian atau tatal untuk mencari dan memilih atribut dan entiti yang anda berminat.</span><span class="sxs-lookup"><span data-stu-id="62738-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="62738-149">Anda tidak boleh mengalih keluar atribut atau entiti jika ia telah dipadankan.</span><span class="sxs-lookup"><span data-stu-id="62738-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="62738-150">![Tambah atau alih keluar atribut](media/configure-data-map-edit.png "Tambah atau alih keluar atribut")</span><span class="sxs-lookup"><span data-stu-id="62738-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="62738-151">Pilih **Guna**.</span><span class="sxs-lookup"><span data-stu-id="62738-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="62738-152">Tambah imej pada profil</span><span class="sxs-lookup"><span data-stu-id="62738-152">Add images to profiles</span></span>

<span data-ttu-id="62738-153">Jika entiti mengandungi URL untuk imej atau logo profil yang tersedia secara umum, anda boleh menambahnya ke profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="62738-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="62738-154">Pilih entiti dan cari medan yang mengandungi URL ke imej profil.</span><span class="sxs-lookup"><span data-stu-id="62738-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="62738-155">Dalam medan input **Jenis**, masukkan secara manual nilai berikut:</span><span class="sxs-lookup"><span data-stu-id="62738-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="62738-156">Untuk seseorang: ImejProfil.Seseorang</span><span class="sxs-lookup"><span data-stu-id="62738-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="62738-157">Untuk organisasi: ImejLogo.Organisasi</span><span class="sxs-lookup"><span data-stu-id="62738-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="62738-158">Teruskan dengan langkah penyatuan dan pastikan atribut yang mengandungi URL imej juga ditambah dalam langkah [Gabungan](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="62738-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="62738-159">Tetapkan atribut untuk organisasi</span><span class="sxs-lookup"><span data-stu-id="62738-159">Set attributes for organizations</span></span>

<span data-ttu-id="62738-160">Untuk organisasi (Pratonton), jenis atribut hendaklah dipetakan kepada "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="62738-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="62738-161">![Kekunci utama dan atribut jenis B2B](media/configure-data-map-edit-b2b.png "Kekunci utama dan atribut jenis B2B")</span><span class="sxs-lookup"><span data-stu-id="62738-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="62738-162">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="62738-162">Next step</span></span>

<span data-ttu-id="62738-163">Sebagai sebahagian daripada proses penyatuan data, pergi ke halaman **Padan** .</span><span class="sxs-lookup"><span data-stu-id="62738-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="62738-164">Lawat [**Padan**](match-entities.md) untuk mengetahui tentang peringkat ini.</span><span class="sxs-lookup"><span data-stu-id="62738-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="62738-165">Semak video berikut: [Bermula: Cipta Profile Pelanggan Disatukan](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="62738-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]