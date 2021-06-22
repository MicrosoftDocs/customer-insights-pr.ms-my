---
title: Hubungan antara entiti dan laluan entiti
description: Cipta dan urus hubungan antara entiti daripada berbilang sumber data.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171175"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="acd8c-103">Perhubungan antara entiti</span><span class="sxs-lookup"><span data-stu-id="acd8c-103">Relationships between entities</span></span>

<span data-ttu-id="acd8c-104">Perhubungan menghubungkan entiti dan mentakrifkan graf data anda apabila entiti berkongsi pengecam biasa, iaitu kunci asing.</span><span class="sxs-lookup"><span data-stu-id="acd8c-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="acd8c-105">Kunci asing ini boleh dirujuk daripada satu entiti ke entiti lain.</span><span class="sxs-lookup"><span data-stu-id="acd8c-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="acd8c-106">Entiti yang berhubung membolehkan definisi segmen dan ukuran berdasarkan berbilang sumber data.</span><span class="sxs-lookup"><span data-stu-id="acd8c-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="acd8c-107">Terdapat tiga jenis perhubungan:</span><span class="sxs-lookup"><span data-stu-id="acd8c-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="acd8c-108">Perhubungan sistem tidak boleh diedit, yang dicipta oleh sistem sebagai sebahagian daripada proses penyatuan data</span><span class="sxs-lookup"><span data-stu-id="acd8c-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="acd8c-109">Perhubungan yang diwarisi dan tidak boleh diedit, yang dicipta secara automatik daripada pengingesan sumber data</span><span class="sxs-lookup"><span data-stu-id="acd8c-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="acd8c-110">Perhubungan tersuai boleh diedit, yang dicipta dan dikonfigurasikan oleh pengguna</span><span class="sxs-lookup"><span data-stu-id="acd8c-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="acd8c-111">Perhubungan sistem tidak boleh diedit</span><span class="sxs-lookup"><span data-stu-id="acd8c-111">Non-editable system relationships</span></span>

<span data-ttu-id="acd8c-112">Semasa penyatuan data, perhubungan sistem dicipta secara automatik berdasarkan padanan pintar.</span><span class="sxs-lookup"><span data-stu-id="acd8c-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="acd8c-113">Perhubungan ini membantu untuk mengaitkan rekod profil pelanggan dengan rekod yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="acd8c-114">Gambar rajah berikut menggambarkan penciptaan tiga perhubungan berdasarkan sistem.</span><span class="sxs-lookup"><span data-stu-id="acd8c-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="acd8c-115">Entiti pelanggan dipadankan dengan entiti lain untuk menghasilkan entiti *Pelanggan* disatukan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Gambar rajah dengan laluan hubungan untuk entiti pelanggan dengan tiga hubungan 1-n.":::

- <span data-ttu-id="acd8c-117">**Perhubungan *CustomerToContact*** dicipta antara entiti *Pelanggan* dengan entiti *Kenalan*.</span><span class="sxs-lookup"><span data-stu-id="acd8c-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="acd8c-118">Entiti *Pelanggan* memperoleh medan kunci **Contact_contactID** untuk mengaitkan dengan entiti *Kenalan* medan kunci **contactID**.</span><span class="sxs-lookup"><span data-stu-id="acd8c-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="acd8c-119">**Perhubungan *CustomerToAccount*** dicipta antara entiti *Pelanggan* dengan entiti *Akaun*.</span><span class="sxs-lookup"><span data-stu-id="acd8c-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="acd8c-120">Entiti *Pelanggan* memperoleh medan kunci **Account_accountID** untuk mengaitkan dengan entiti *Akaun* medan kunci **accountID**.</span><span class="sxs-lookup"><span data-stu-id="acd8c-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="acd8c-121">**Perhubungan *CustomerToWebAccount*** dicipta antara entiti *Pelanggan* dengan entiti *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="acd8c-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="acd8c-122">Entiti *Pelanggan* memperoleh medan kekunci **WebAccount_webaccountID** untuk mengaitkan dengan entiti *WebAccount* medan kekunci **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="acd8c-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="acd8c-123">Perhubungan yang diwarisi dan tidak boleh diedit</span><span class="sxs-lookup"><span data-stu-id="acd8c-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="acd8c-124">Semasa proses pengingesan data, sistem menyemak sumber data untuk perhubungan sedia ada.</span><span class="sxs-lookup"><span data-stu-id="acd8c-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="acd8c-125">Jika tiada perhubungan wujud, sistem mencipta perhubungan secara automatik.</span><span class="sxs-lookup"><span data-stu-id="acd8c-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="acd8c-126">Perhubungan ini juga digunakan dalam proses hiliran.</span><span class="sxs-lookup"><span data-stu-id="acd8c-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="acd8c-127">Cipta perhubungan tersuai</span><span class="sxs-lookup"><span data-stu-id="acd8c-127">Create a custom relationship</span></span>

<span data-ttu-id="acd8c-128">Perhubungan terdiri daripada *entiti sumber* yang mengandungi kunci asing dan *entiti sasaran* yang dihalakan ke kunci asing entiti sumber.</span><span class="sxs-lookup"><span data-stu-id="acd8c-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="acd8c-129">Dalam wawasan khalayak, pergi ke **Data** > **Hubungan**.</span><span class="sxs-lookup"><span data-stu-id="acd8c-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="acd8c-130">Pilih **Perhubungan baharu**.</span><span class="sxs-lookup"><span data-stu-id="acd8c-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="acd8c-131">Dalam anak tetingkap **Perhubungan baharu**, berikan maklumat berikut:</span><span class="sxs-lookup"><span data-stu-id="acd8c-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Anak tetingkap sisi perhubungan baharu dengan medan input kosong.":::

   - <span data-ttu-id="acd8c-133">**Nama perhubungan**: Nama yang mencerminkan tujuan perhubungan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="acd8c-134">Contoh: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="acd8c-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="acd8c-135">**Description**: Description bagi perhubungan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="acd8c-136">**Entiti sumber**: Entiti yang digunakan sebagai sumber dalam perhubungan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="acd8c-137">Contoh: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="acd8c-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="acd8c-138">**Entiti sasaran**: Entiti yang digunakan sebagai sasaran dalam perhubungan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="acd8c-139">Contoh: Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-139">Example: Customer.</span></span>
   - <span data-ttu-id="acd8c-140">**Kekardinalan sumber**: Tentukan kekardinalan entiti sumber.</span><span class="sxs-lookup"><span data-stu-id="acd8c-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="acd8c-141">Kekardinalan menerangkan bilangan elemen yang mungkin dalam satu set.</span><span class="sxs-lookup"><span data-stu-id="acd8c-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="acd8c-142">Ia sentiasa berkaitan dengan kekardinalan sasaran.</span><span class="sxs-lookup"><span data-stu-id="acd8c-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="acd8c-143">Anda boleh memilih antara **Satu** dengan **Banyak**.</span><span class="sxs-lookup"><span data-stu-id="acd8c-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="acd8c-144">Hanya perhubungan banyak-ke-satu dan satu-ke-satu disokong.</span><span class="sxs-lookup"><span data-stu-id="acd8c-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="acd8c-145">Banyak kepada satu: Berbilang rekod sumber boleh berkaitan dengan satu rekod sasaran.</span><span class="sxs-lookup"><span data-stu-id="acd8c-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="acd8c-146">Contoh: Berbilang kes sokongan daripada pelanggan tunggal.</span><span class="sxs-lookup"><span data-stu-id="acd8c-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="acd8c-147">Satu kepada satu: Rekod sumber tunggal berkaitan dengan satu rekod sasaran.</span><span class="sxs-lookup"><span data-stu-id="acd8c-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="acd8c-148">Contoh: Satu ID kesetiaan untuk pelanggan tunggal.</span><span class="sxs-lookup"><span data-stu-id="acd8c-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="acd8c-149">Perhubungan banyak kepada banyak boleh dicipta menggunakan dua perhubungan banyak kepada satu dan entiti pemautan, yang menghubungkan entiti sumber dan entiti sasaran.</span><span class="sxs-lookup"><span data-stu-id="acd8c-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="acd8c-150">**Kekardinalan sasaran**: Pilih kekardinalan rekod entiti sasaran.</span><span class="sxs-lookup"><span data-stu-id="acd8c-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="acd8c-151">**Medan kunci sumber**: Medan kunci asing dalam entiti sumber.</span><span class="sxs-lookup"><span data-stu-id="acd8c-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="acd8c-152">Contoh: SupportCase boleh menggunakan CaseID sebagai medan kunci asing.</span><span class="sxs-lookup"><span data-stu-id="acd8c-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="acd8c-153">**Medan kunci sasaran**: Medan kunci entiti sasaran.</span><span class="sxs-lookup"><span data-stu-id="acd8c-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="acd8c-154">Contoh Pelanggan boleh menggunakan medan kunci **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="acd8c-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="acd8c-155">Pilih **Simpan** untuk mencipta perhubungan tersuai.</span><span class="sxs-lookup"><span data-stu-id="acd8c-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="acd8c-156">Lihat perhubungan</span><span class="sxs-lookup"><span data-stu-id="acd8c-156">View relationships</span></span>

<span data-ttu-id="acd8c-157">Halaman Perhubungan menyenaraikan semua perhubungan yang telah dicipta.</span><span class="sxs-lookup"><span data-stu-id="acd8c-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="acd8c-158">Setiap baris mewakili perhubungan, yang juga termasuk butiran tentang entiti sumber, entiti sasaran dan kekardinalan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Senarai perhubungan dan pilihan dalam bar tindakan halaman Perhubungan.":::

<span data-ttu-id="acd8c-160">Halaman ini menawarkan satu set pilihan untuk perhubungan sedia ada dan baharu:</span><span class="sxs-lookup"><span data-stu-id="acd8c-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="acd8c-161">**Perhubungan Baharu**: [Cipta perhubungan tersuai](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="acd8c-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="acd8c-162">**Penampak**: [Terokai penampak perhubungan](#explore-the-relationship-visualizer) untuk melihat gambar rajah rangkaian perhubungan yang sedia ada dan kekardinalan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="acd8c-163">**Tapis mengikut**: Pilih jenis perhubungan untuk ditunjukkan dalam senarai.</span><span class="sxs-lookup"><span data-stu-id="acd8c-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="acd8c-164">**Cari perhubungan**: Gunakan carian berdasarkan teks pada sifat perhubungan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="acd8c-165">Terokai penampak perhubungan</span><span class="sxs-lookup"><span data-stu-id="acd8c-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="acd8c-166">Penampak perhubungan menunjukkan gambar rajah rangkaian perhubungan yang sedia ada antara entiti yang berhubung dengan kekardinalan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="acd8c-167">Untuk menyesuaikan pandangan, anda boleh mengubah kedudukan kotak dengan menyeret kotak pada kanvas.</span><span class="sxs-lookup"><span data-stu-id="acd8c-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Syot layar gambar rajah rangkaian penampak perhubungan dengan sambungan antara entiti yang berkaitan.":::

<span data-ttu-id="acd8c-169">Pilihan yang tersedia:</span><span class="sxs-lookup"><span data-stu-id="acd8c-169">Available options:</span></span> 
- <span data-ttu-id="acd8c-170">**Eksport sebagai imej**: Simpan pandangan semasa sebagai fail imej.</span><span class="sxs-lookup"><span data-stu-id="acd8c-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="acd8c-171">**Tukar kepada tataletak mendatar/menegak**: Tukar penjajaran entiti dan perhubungan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="acd8c-172">**Edit**: Kemas kini sifat perhubungan tersuai dalam anak tetingkap edit dan simpan perubahan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="acd8c-173">Urus perhubungan yang sedia ada</span><span class="sxs-lookup"><span data-stu-id="acd8c-173">Manage existing relationships</span></span> 

<span data-ttu-id="acd8c-174">Pada halaman Perhubungan, setiap perhubungan diwakili oleh baris.</span><span class="sxs-lookup"><span data-stu-id="acd8c-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="acd8c-175">Pilih perhubungan dan pilih salah satu daripada pilihan berikut:</span><span class="sxs-lookup"><span data-stu-id="acd8c-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="acd8c-176">**Edit**: Kemas kini sifat perhubungan tersuai dalam anak tetingkap edit dan simpan perubahan.</span><span class="sxs-lookup"><span data-stu-id="acd8c-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="acd8c-177">**Padam**: Padam perhubungan tersuai.</span><span class="sxs-lookup"><span data-stu-id="acd8c-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="acd8c-178">**Lihat**: Lihat perhubungan yang dicipta sistem dan diwarisi.</span><span class="sxs-lookup"><span data-stu-id="acd8c-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="acd8c-179">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="acd8c-179">Next step</span></span>

<span data-ttu-id="acd8c-180">Perhubungan sistem dan tersuai digunakan untuk [mencipta segmen](segments.md) berdasarkan berbilang sumber data yang tidak lagi silo.</span><span class="sxs-lookup"><span data-stu-id="acd8c-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
