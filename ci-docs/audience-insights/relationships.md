---
title: Hubungan antara entiti dan laluan entiti
description: Cipta dan urus hubungan antara entiti daripada berbilang sumber data.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595223"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="1d68b-103">Perhubungan antara entiti</span><span class="sxs-lookup"><span data-stu-id="1d68b-103">Relationships between entities</span></span>

<span data-ttu-id="1d68b-104">Perhubungan membantu anda connect entiti dan menjana graf data apabila entiti berkongsi pengecam lazim (kekunci asing) yang boleh menjadi rujukan daripada satu entiti ke entiti yang lain.</span><span class="sxs-lookup"><span data-stu-id="1d68b-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="1d68b-105">Entiti yang bersambung membolehkan anda menakrif bahagian dan ukuran berasaskan pada berbilang sumber data.</span><span class="sxs-lookup"><span data-stu-id="1d68b-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="1d68b-106">Terdapat dua jenis perhubungan.</span><span class="sxs-lookup"><span data-stu-id="1d68b-106">There are two types of relationships.</span></span> <span data-ttu-id="1d68b-107">Perhubungan sistem tidak boleh diedit, yang dicipta secara automatik, dan perhubungan tersuai yang dicipta dan dikonfigurasikan oleh pengguna.</span><span class="sxs-lookup"><span data-stu-id="1d68b-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="1d68b-108">Semasa proses padan dan gabung, perhubungan sistem dicipta di belakang tabir berasaskan pada pemadanan pintar.</span><span class="sxs-lookup"><span data-stu-id="1d68b-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="1d68b-109">Perhubungan ini membantu mengaitkan rekod Profil Pelanggan dengan rekod entiti lain yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="1d68b-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="1d68b-110">Diagram berikut menerangkan penciptaan tiga perhubungan sistem apabila entiti pelanggan sepadan dengan entiti tambahan untuk mengeluarkan entiti Profil Pelanggan akhir.</span><span class="sxs-lookup"><span data-stu-id="1d68b-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1d68b-111">![Penciptaan perhubungan](media/relationships-entities-merge.png "Penciptaan perhubungan")</span><span class="sxs-lookup"><span data-stu-id="1d68b-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="1d68b-112">**Perhubungan *CustomerToContact*** dicipta antara entiti Pelanggan dan entiti Kenalan.</span><span class="sxs-lookup"><span data-stu-id="1d68b-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="1d68b-113">Entiti Pelanggan memperoleh medan kekunci **Contact_contactId** untuk mengaitkan dengan medan kekunci entiti Kenalan **contactId**.</span><span class="sxs-lookup"><span data-stu-id="1d68b-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="1d68b-114">**Perhubungan *CustomerToAccount*** dicipta antara entiti Pelanggan dengan entiti Akaun.</span><span class="sxs-lookup"><span data-stu-id="1d68b-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="1d68b-115">Entiti Pelanggan memperoleh medan kekunci **Account_accountId** untuk mengaitkan dengan medan kekunci entiti Akaun **accountId**.</span><span class="sxs-lookup"><span data-stu-id="1d68b-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="1d68b-116">**Perhubungan *CustomerToWebAccount*** dicipta antara entiti Pelanggan dengan entiti WebAccount.</span><span class="sxs-lookup"><span data-stu-id="1d68b-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="1d68b-117">Entiti Pelanggan memperoleh medan kekunci **WebAccount_webaccountId** untuk mengaitkan dengan medan kekunci entiti WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="1d68b-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="1d68b-118">Cipta perhubungan</span><span class="sxs-lookup"><span data-stu-id="1d68b-118">Create a relationship</span></span>

<span data-ttu-id="1d68b-119">Takrif perhubungan tersuai pada halaman **Perhubungan**.</span><span class="sxs-lookup"><span data-stu-id="1d68b-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="1d68b-120">Setiap perhubungan mengandungi entiti Sumber (entiti yang memegang kekunci asing) dan entiti Sasaran (entiti yang kekunci asing bagi entiti sumber dirujuk).</span><span class="sxs-lookup"><span data-stu-id="1d68b-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="1d68b-121">Dalam wawasan khalayak, pergi ke **Data** > **Hubungan**.</span><span class="sxs-lookup"><span data-stu-id="1d68b-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="1d68b-122">Pilih **Perhubungan baharu**.</span><span class="sxs-lookup"><span data-stu-id="1d68b-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="1d68b-123">Dalam anak tetingkap **Tambah perhubungan**, berikan maklumat berikut:</span><span class="sxs-lookup"><span data-stu-id="1d68b-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1d68b-124">![Masukkan butiran perhubungan](media/relationships-add.png "Masukkan butiran perhubungan")</span><span class="sxs-lookup"><span data-stu-id="1d68b-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="1d68b-125">**Nama perhubungan**: Nama yang menggambarkan tujuan perhubungan (contohnya, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="1d68b-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="1d68b-126">**Description**: Description bagi perhubungan.</span><span class="sxs-lookup"><span data-stu-id="1d68b-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="1d68b-127">**Entiti Sumber**: Pilih entiti yang digunakan sebagai sumber dalam perhubungan (contohnya, WebLog).</span><span class="sxs-lookup"><span data-stu-id="1d68b-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="1d68b-128">**Kekardinalan**: Pilih kekardinalan bagi rekod entiti sumber.</span><span class="sxs-lookup"><span data-stu-id="1d68b-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="1d68b-129">Contohnya, “banyak” bermaksud rekod Weblog berbilang berkait dengan satu WebAccount.</span><span class="sxs-lookup"><span data-stu-id="1d68b-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="1d68b-130">**Medan kekunci sumber**: Ini mewakili medan kekunci asing dalam entiti sumber.</span><span class="sxs-lookup"><span data-stu-id="1d68b-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="1d68b-131">Contohnya, WebLog mempunyai medan kekunci asing **accountId**.</span><span class="sxs-lookup"><span data-stu-id="1d68b-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="1d68b-132">**Entiti sasaran**: Pilih entiti yang digunakan sebagai sasaran dalam perhubungan (contohnya, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="1d68b-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="1d68b-133">**Kekardinalan sasaran**: Pilih kekardinalan rekod entiti sasaran.</span><span class="sxs-lookup"><span data-stu-id="1d68b-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="1d68b-134">Contohnya, “satu” bermaksud rekod Weblog berbilang berkait dengan satu WebAccount.</span><span class="sxs-lookup"><span data-stu-id="1d68b-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="1d68b-135">**Medan kekunci sasaran**: Medan ini mewakili medan kekunci bagi entiti sasaran.</span><span class="sxs-lookup"><span data-stu-id="1d68b-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="1d68b-136">Contohnya, WebAccount mempunyai medan kekunci **accountId**.</span><span class="sxs-lookup"><span data-stu-id="1d68b-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="1d68b-137">Hanya perhubungan banyak-ke-satu dan satu-ke-satu disokong.</span><span class="sxs-lookup"><span data-stu-id="1d68b-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="1d68b-138">Perhubungan banyak-ke-banyak boleh dicipta menggunakan dua perhubungan banyak-ke-satu dan entiti pautan (entiti yang digunakan untuk connect entiti sumber dan entiti sasaran).</span><span class="sxs-lookup"><span data-stu-id="1d68b-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="1d68b-139">Memadam perhubungan</span><span class="sxs-lookup"><span data-stu-id="1d68b-139">Delete a relationship</span></span>

1. <span data-ttu-id="1d68b-140">Dalam wawasan khalayak, pergi ke **Data** > **Hubungan**.</span><span class="sxs-lookup"><span data-stu-id="1d68b-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="1d68b-141">Pilih kotak semak untuk perhubungan yang anda mahu padam.</span><span class="sxs-lookup"><span data-stu-id="1d68b-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="1d68b-142">Pilih **Padam** pada bahagian atas jadual **Perhubungan**.</span><span class="sxs-lookup"><span data-stu-id="1d68b-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="1d68b-143">Sahkan pemadaman anda.</span><span class="sxs-lookup"><span data-stu-id="1d68b-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="1d68b-144">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="1d68b-144">Next step</span></span>

<span data-ttu-id="1d68b-145">Perhubungan sistem dan tersuai digunakan untuk mencipta bahagian berasaskan berbilang sumber data yang tidak lagi silo.</span><span class="sxs-lookup"><span data-stu-id="1d68b-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="1d68b-146">Untuk maklumat lanjut, lihat [Bahagian](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1d68b-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]