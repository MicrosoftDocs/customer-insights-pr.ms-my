---
title: Cipta dan urus segmen
description: Cipta bahagian pelanggan untuk mengumpul mereka berasaskan pelbagai atribut.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064948"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="59490-103">Cipta dan urus segmen</span><span class="sxs-lookup"><span data-stu-id="59490-103">Create and manage segments</span></span>

<span data-ttu-id="59490-104">Takrifkan penapis kompleks sekitar entiti pelanggan disatukan dan entiti yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="59490-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="59490-105">Setiap segmen, selepas pemprosesan, mencipta set rekod pelanggan yang boleh anda eksport dan ambil tindakan padanya.</span><span class="sxs-lookup"><span data-stu-id="59490-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="59490-106">Segmen diuruskan pada halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="59490-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="59490-107">Contoh berikut menunjukkan keupayaan pembahagian.</span><span class="sxs-lookup"><span data-stu-id="59490-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="59490-108">Kami telah menentukan segmen untuk pelanggan yang mengarahkan sekurang-kurangnya $500 barangan dalam 90 hari yang lalu *dan* yang terlibat dalam panggilan khidmat pelanggan yang telah dipertingkatkan.</span><span class="sxs-lookup"><span data-stu-id="59490-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Tangkapan skrin bagi UI pembina segmen dengan dua kumpulan yang menentukan segmen pelanggan.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="59490-110">Cipta bahagian baharu</span><span class="sxs-lookup"><span data-stu-id="59490-110">Create a new segment</span></span>

<span data-ttu-id="59490-111">Terdapat berbilang cara untuk mencipta segmen baharu.</span><span class="sxs-lookup"><span data-stu-id="59490-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="59490-112">Bahagian ini menerangkan cara mencipta *segmen kosong* daripada mula.</span><span class="sxs-lookup"><span data-stu-id="59490-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="59490-113">Anda juga boleh mencipta *segmen pantas* berdasarkan pada entiti sedia ada atau menggunakan model pembelajaran mesin untuk mendapatkan *segmen yang dicadangkan*.</span><span class="sxs-lookup"><span data-stu-id="59490-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="59490-114">Maklumat lanjut: [Gambaran keseluruhan segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="59490-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="59490-115">Semasa mencipta segmen, anda boleh menyimpan draf.</span><span class="sxs-lookup"><span data-stu-id="59490-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="59490-116">Ia akan disimpan sebagai segmen tidak aktif dan tidak boleh diaktifkan setelah selesai dengan konfigurasi yang sah.</span><span class="sxs-lookup"><span data-stu-id="59490-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="59490-117">Pergi ke halaman **Bahagian**.</span><span class="sxs-lookup"><span data-stu-id="59490-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="59490-118">Pilih **Baharu** > **Segmen kosong**.</span><span class="sxs-lookup"><span data-stu-id="59490-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="59490-119">Dalam anak tetingkap **Segmen baharu**, pilih jenis segmen:</span><span class="sxs-lookup"><span data-stu-id="59490-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="59490-120">**Segmen dinamik** [segar semula](segments.md#refresh-segments) pada jadual berulang.</span><span class="sxs-lookup"><span data-stu-id="59490-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="59490-121">**Segmen statik** berjalan sebaik sahaja anda menciptanya.</span><span class="sxs-lookup"><span data-stu-id="59490-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="59490-122">Berikan **Nama entiti output** untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="59490-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="59490-123">Secara pilihan, berikan nama paparan, dan description yang membantu mengenal pasti bahagian.</span><span class="sxs-lookup"><span data-stu-id="59490-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="59490-124">Pilih **Seterusnya** untuk mendapatkan halaman **Pembina bahagian** di mana anda menakrif kumpulan.</span><span class="sxs-lookup"><span data-stu-id="59490-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="59490-125">Kumpulan ialah set pelanggan.</span><span class="sxs-lookup"><span data-stu-id="59490-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="59490-126">Pilih entiti yang merangkumi atribut yang anda mahu dibahagikan.</span><span class="sxs-lookup"><span data-stu-id="59490-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="59490-127">Pilih atribut untuk segmen mengikut.</span><span class="sxs-lookup"><span data-stu-id="59490-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="59490-128">Atribut ini boleh mempunyai salah satu daripada empat jenis nilai: berangka, rentetan, tarikh atau Boolean.</span><span class="sxs-lookup"><span data-stu-id="59490-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="59490-129">Pilih operator dan nilai untuk atribut yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="59490-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="59490-130">![Penapis kumpulan tersuai](media/customer-group-numbers.png "Penapis kumpulan pelanggan")</span><span class="sxs-lookup"><span data-stu-id="59490-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="59490-131">Nombor</span><span class="sxs-lookup"><span data-stu-id="59490-131">Number</span></span> |<span data-ttu-id="59490-132">Definisi</span><span class="sxs-lookup"><span data-stu-id="59490-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="59490-133">1</span><span class="sxs-lookup"><span data-stu-id="59490-133">1</span></span>     |<span data-ttu-id="59490-134">EntitI</span><span class="sxs-lookup"><span data-stu-id="59490-134">Entity</span></span>          |
   |<span data-ttu-id="59490-135">2</span><span class="sxs-lookup"><span data-stu-id="59490-135">2</span></span>     |<span data-ttu-id="59490-136">Atribut</span><span class="sxs-lookup"><span data-stu-id="59490-136">Attribute</span></span>          |
   |<span data-ttu-id="59490-137">3</span><span class="sxs-lookup"><span data-stu-id="59490-137">3</span></span>    |<span data-ttu-id="59490-138">Operator</span><span class="sxs-lookup"><span data-stu-id="59490-138">Operator</span></span>         |
   |<span data-ttu-id="59490-139">4</span><span class="sxs-lookup"><span data-stu-id="59490-139">4</span></span>    |<span data-ttu-id="59490-140">Nilai</span><span class="sxs-lookup"><span data-stu-id="59490-140">Value</span></span>         |

   1. <span data-ttu-id="59490-141">Untuk menambahkan lebih banyak syarat ke kumpulan, anda boleh menggunakan dua operator logik:</span><span class="sxs-lookup"><span data-stu-id="59490-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="59490-142">Operator **DAN**: Kedua-dua syarat mesti dipenuhi sebagai sebahagian proses pembahagian.</span><span class="sxs-lookup"><span data-stu-id="59490-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="59490-143">Pilihan ini adalah paling berguna apabila anda menakrif syarat dalam entiti yang berbeza.</span><span class="sxs-lookup"><span data-stu-id="59490-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="59490-144">Operator **ATAU**: Salah satu syarat perlu dipenuhi sebagai sebahagian daripada proses pembahagian.</span><span class="sxs-lookup"><span data-stu-id="59490-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="59490-145">Pilihan ini paling berguna apabila anda menakrif berbilang syarat untuk entiti yang sama.</span><span class="sxs-lookup"><span data-stu-id="59490-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="59490-146">![Operator ATAU di mana salah satu syarat perlu dipenuhi](media/segmentation-either-condition.png "Operator ATAU di mana salah satu syarat perlu dipenuhi")</span><span class="sxs-lookup"><span data-stu-id="59490-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="59490-147">Pada masa ini berkemungkinan untuk menyarang operator **ATAU** di bawah operator **DAN**, tetapi tidak sebaliknya.</span><span class="sxs-lookup"><span data-stu-id="59490-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="59490-148">Setiap kumpulan berpadanan dengan set pelanggan.</span><span class="sxs-lookup"><span data-stu-id="59490-148">Each group matches set of customers.</span></span> <span data-ttu-id="59490-149">Anda boleh menggabungkan kumpulan untuk memasukkan pelanggan yang diperlukan bagi kes perniagaan anda.</span><span class="sxs-lookup"><span data-stu-id="59490-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="59490-150">Pilih **Tambah Kumpulan**.</span><span class="sxs-lookup"><span data-stu-id="59490-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="59490-151">![Kumpulan pelanggan tambah kumpulan](media/customer-group-add-group.png "Kumpulan pelanggan tambah kumpulan")</span><span class="sxs-lookup"><span data-stu-id="59490-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="59490-152">Pilih salah satu operator set: **Kesatuan**, **Bersilang** atau **Kecuali**.</span><span class="sxs-lookup"><span data-stu-id="59490-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="59490-153">![Kumpulan pelanggan tambah kesatuan](media/customer-group-union.png "Kumpulan pelanggan tambah kesatuan")</span><span class="sxs-lookup"><span data-stu-id="59490-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="59490-154">**Kesatuan** menyatukan dua kumpulan.</span><span class="sxs-lookup"><span data-stu-id="59490-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="59490-155">**Bersilang** dua kumpulan bertindih.</span><span class="sxs-lookup"><span data-stu-id="59490-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="59490-156">Hanya data yang *umum* pada kedua-dua kumpulan dikekalkan dalam kumpulan disatukan.</span><span class="sxs-lookup"><span data-stu-id="59490-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="59490-157">**Kecuali** menggabungkan dua kumpulan.</span><span class="sxs-lookup"><span data-stu-id="59490-157">**Except** combines the two groups.</span></span> <span data-ttu-id="59490-158">Hanya data dalam kumpulan A yang *tidak umum* pada data dalam kumpulan B dikekalkan.</span><span class="sxs-lookup"><span data-stu-id="59490-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="59490-159">Jika entiti disambungkan kepada entiti pelanggan disatukan melalui [perhubungan](relationships.md), anda perlu mentakrifkan laluan perhubungan untuk mencipta segmen yang sah.</span><span class="sxs-lookup"><span data-stu-id="59490-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="59490-160">Tambah entiti daripada laluan perhubungan sehingga anda boleh memilih entiti **Pelanggan : CustomerInsights** daripada juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="59490-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="59490-161">Kemudian pilih **Semua rekod** untuk setiap langkah.</span><span class="sxs-lookup"><span data-stu-id="59490-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="59490-162">![Laluan perhubungan semasa penciptaan segmen](media/segments-multiple-relationships.png "Laluan perhubungan semasa penciptaan segmen")</span><span class="sxs-lookup"><span data-stu-id="59490-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="59490-163">Secara lalai, segmen menjana entiti output yang mengandungi semua atribut profil pelanggan yang sepadan dengan penapis yang ditentukan.</span><span class="sxs-lookup"><span data-stu-id="59490-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="59490-164">Jika segmen berdasarkan entiti lain daripada entiti *Pelanggan*, anda boleh menambahkan lebih banyak atribut daripada entiti tersebut kepada entiti output.</span><span class="sxs-lookup"><span data-stu-id="59490-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="59490-165">Pilih **Atribut projek** untuk memilih atribut yang akan ditambah pada entiti output.</span><span class="sxs-lookup"><span data-stu-id="59490-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="59490-166">Contoh: Segmen berdasarkan entiti yang mengandungi data aktiviti pelanggan yang berkaitan dengan entiti *Pelanggan*.</span><span class="sxs-lookup"><span data-stu-id="59490-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="59490-167">Segmen mencari semua pelanggan yang memanggil meja bantuan dalam masa 60 hari yang lalu.</span><span class="sxs-lookup"><span data-stu-id="59490-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="59490-168">Anda boleh memilih untuk menambah tempoh panggilan dan bilangan panggilan kepada semua rekod pelanggan yang sepadan dalam entiti output.</span><span class="sxs-lookup"><span data-stu-id="59490-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="59490-169">Maklumat ini mungkin berguna untuk menghantar e-mel dengan pautan berguna ke artikel bantuan dalam talian dan soalan lazim kepada pelanggan yang sering membuat panggilan.</span><span class="sxs-lookup"><span data-stu-id="59490-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="59490-170">Atribut yang diunjurkan hanya berfungsi untuk entiti yang mempunyai perhubungan satu dengan banyak dengan entiti pelanggan.</span><span class="sxs-lookup"><span data-stu-id="59490-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="59490-171">Contohnya, seorang pelanggan boleh mempunyai berbilang langganan.</span><span class="sxs-lookup"><span data-stu-id="59490-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="59490-172">Anda hanya boleh mengunjurkan atribut daripada entiti yang digunakan dalam setiap kumpulan pertanyaan segmen yang anda bangunkan.</span><span class="sxs-lookup"><span data-stu-id="59490-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="59490-173">Atribut yang diunjurkan diambil kira apabila menggunakan operator set.</span><span class="sxs-lookup"><span data-stu-id="59490-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="59490-174">Pilih **Simpan** untuk menyimpan bahagian anda.</span><span class="sxs-lookup"><span data-stu-id="59490-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="59490-175">Bahagian anda akan disimpan dan diproses jika semua keperluan disahkan.</span><span class="sxs-lookup"><span data-stu-id="59490-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="59490-176">Jika tidak, ia akan disimpan sebagai draf.</span><span class="sxs-lookup"><span data-stu-id="59490-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="59490-177">Pilih **Kembali ke segmen** untuk kembali ke halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="59490-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="59490-178">Segmen pantas</span><span class="sxs-lookup"><span data-stu-id="59490-178">Quick segments</span></span>

<span data-ttu-id="59490-179">Segmen pantas membolehkan anda membina segmen ringkas dengan operator tunggal dengan pantas untuk wawasan yang lebih pantas.</span><span class="sxs-lookup"><span data-stu-id="59490-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="59490-180">Pada halaman **Segmen**, pilih **Baharu** > **Cipta daripada**.</span><span class="sxs-lookup"><span data-stu-id="59490-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="59490-181">Pilih pilihan **Profil** untuk membina segmen yang berasaskan pada entiti *pelanggan disatukan*.</span><span class="sxs-lookup"><span data-stu-id="59490-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="59490-182">Pilih pilihan **Ukuran** untuk membina segmen sekitar ukuran yang anda buat sebelum ini.</span><span class="sxs-lookup"><span data-stu-id="59490-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="59490-183">Pilih pilihan **Kecerdasan** untuk membina segmen di sekitar salah satu entiti output yang dijana anda menggunakan sama ada keupayaan **Ramalan** atau **Model Tersuai**.</span><span class="sxs-lookup"><span data-stu-id="59490-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="59490-184">Dalam kotak dialog **Segmen pantas baharu**, pilih atribut daripada **Medan** juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="59490-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="59490-185">Sistem akan memberikan wawasan tambahan yang membantu anda mencipta bahagian yang lebih baik untuk pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="59490-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="59490-186">Untuk medan kategori, kami akan menunjukkan 10 kiraan pelanggan teratas.</span><span class="sxs-lookup"><span data-stu-id="59490-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="59490-187">Pilih **Nilai** dan pilih **Semak Semula**.</span><span class="sxs-lookup"><span data-stu-id="59490-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="59490-188">Untuk atribut numerik, sistem akan menunjukkan apakah nilai atribut yang jatuh dalam setiap persentil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="59490-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="59490-189">Pilih **Operator** dan **Nilai**, kemudian pilih **Semak Semula**.</span><span class="sxs-lookup"><span data-stu-id="59490-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="59490-190">Sistem akan memberikan anda **saiz bahagian yang dianggarkan**.</span><span class="sxs-lookup"><span data-stu-id="59490-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="59490-191">Anda boleh memilih sama ada untuk menjana bahagian yang anda takrif, atau kunjungi semula terlebih dahulu untuk mendapatkan saiz bahagian yang berbeza.</span><span class="sxs-lookup"><span data-stu-id="59490-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="59490-192">![Nama dan anggaran bagi bahagian pantas](media/quick-segment-name.png "Nama dan anggaran bagi bahagian pantas")</span><span class="sxs-lookup"><span data-stu-id="59490-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="59490-193">Berikan **Nama** untuk bahagian anda.</span><span class="sxs-lookup"><span data-stu-id="59490-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="59490-194">Secara pilihan, berikan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="59490-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="59490-195">Pilih **Simpan** untuk mencipta bahagian.</span><span class="sxs-lookup"><span data-stu-id="59490-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="59490-196">Selepas bahagian selesai diproses, anda boleh melihatnya seperti bahagian lain yang anda cipta.</span><span class="sxs-lookup"><span data-stu-id="59490-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="59490-197">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="59490-197">Next steps</span></span>

<span data-ttu-id="59490-198">[Eksport bahagian](export-destinations.md) dan teroka [Kad Pelanggan](customer-card-add-in.md) dan [Penyambung](export-power-bi.md) untuk mendapatkan wawasan pada peringkat pelanggan.</span><span class="sxs-lookup"><span data-stu-id="59490-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
