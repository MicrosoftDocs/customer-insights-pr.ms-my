---
title: Cipta dan edit ukuran
description: Takrif ukuran berkaitan pelanggan untuk menganalisis dan menunjukkan prestasi bagi beberapa bidang perniagaan.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406477"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="3ffa1-103">Takrifkan dan urus tindakan</span><span class="sxs-lookup"><span data-stu-id="3ffa1-103">Define and manage measures</span></span>

<span data-ttu-id="3ffa1-104">**Ukuran** mewakili penunjuk prestasi utama (KPIs) yang menunjukkan prestasi dan kesihatan bagi bidang perniagaan tertentu.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="3ffa1-105">Wawasan khalayak memberikan pengalaman intuitif untuk membina pelbagai jenis langkah, menggunakan pembina pertanyaan yang tidak memerlukan anda untuk kod atau mengesahkan langkah anda secara manual.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="3ffa1-106">Anda boleh menjejak ukuran perniagaan anda pada halaman **Laman Utama**, lihat ukuran untuk pelanggan tertentu pada **Kad Pelanggan**, dan guna ukuran untuk menakrifkan bahagian pada halaman **Bahagian**.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="3ffa1-107">Cipta ukuran</span><span class="sxs-lookup"><span data-stu-id="3ffa1-107">Create a measure</span></span>

<span data-ttu-id="3ffa1-108">Bahagian ini membimbing anda mencipta ukuran daripada awal.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="3ffa1-109">Anda boleh membina ukuran dengan data daripada berbilang sumber data yang disambungkan melalui entiti Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="3ffa1-110">Sesetengah [had perkhidmatan](service-limits.md) diguna pakai.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="3ffa1-111">Dalam wawasan khalayak, pergi ke **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="3ffa1-112">Pilih **Ukuran baharu**.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-112">Select **New measure**.</span></span>

3. <span data-ttu-id="3ffa1-113">Pilih ukuran **Jenis**:</span><span class="sxs-lookup"><span data-stu-id="3ffa1-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="3ffa1-114">**Atribut Pelanggan**: Medan tunggal bagi setiap pelanggan yang menunjukkan skor, nilai, atau keadaan bagi pelanggan.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="3ffa1-115">Atribut pelanggan dicipta sebagai atribut dalam entiti dijana sistem dipanggil **Ukuran_Pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="3ffa1-116">**Ukuran pelanggan**: Wawasan pada tingkah laku pelanggan dengan pecahan mengikut dimensi terpilih.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="3ffa1-117">Entiti baharu dijana untuk setiap ukuran, berpotensi dengan berbilang rekod bagi setiap pelanggan.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="3ffa1-118">**Ukuran perniagaan**: Jejak prestasi dan kesihatan perniagaan anda.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="3ffa1-119">Ukuran perniagaan boleh mempunyai dua output yang berbeza: output numerik yang ditunjukkan pada halaman **Laman Utama** atau entiti baharu yang anda temui pada halaman **Entiti**.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="3ffa1-120">Berikan **Nama** dan **Nama paparan** optional, kemudian pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="3ffa1-121">Pada bahagian **Entiti**, pilih entiti pertama daripada senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="3ffa1-122">Pada peringkat ini, Anda perlu membuat keputusan sama ada memerlukan entiti tambahan sebagai sebahagian definisi ukuran anda.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3ffa1-123">![Definisi ukuran](media/measure-definition.png "Definisi langkah")</span><span class="sxs-lookup"><span data-stu-id="3ffa1-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="3ffa1-124">Untuk menambah lebih banyak entiti, pilih **Tambah entiti** dan pilih entiti yang anda mahu gunakan untuk ukuran.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3ffa1-125">Anda hanya boleh memilih entiti yang mempunyai hubungan dengan entiti permulaan anda.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="3ffa1-126">Untuk maklumat lanjut tentang menakrif perhubungan, lihat [Perhubungan](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="3ffa1-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="3ffa1-127">Secara pilihan, anda boleh mengkonfigurasikan pemboleh ubah.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="3ffa1-128">Dalam bahagian **Pemboleh ubah**, pilih **Pemboleh ubah baharu**.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="3ffa1-129">Pemboleh ubah adalah pengiraan yang dibuat pada setiap rekod pilihan anda.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="3ffa1-130">Contohnya, menambah mata jualan (POS) dan jualan dalam talian untuk setiap rekod pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="3ffa1-131">Berikan **Nama** untuk pemboleh ubah.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="3ffa1-132">Dalam kawasan **Ungkapan**, pilih medan untuk memulakan pengiraan anda.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="3ffa1-133">Taip ungkapan dalam kawasan **Ungkapan** semasa memilih lebih banyak medan untuk dimasukkan dalam pengiraan.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3ffa1-134">Pada masa ini, hanya ungkapan yang aritmetik disokong.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="3ffa1-135">Selain itu, pengiraan pemboleh ubah tidak menyokong entiti daripada [laluan entiti](relationships.md) yang berbeza.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="3ffa1-136">Pilih **Selesai**.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-136">Select **Done**.</span></span>

11. <span data-ttu-id="3ffa1-137">Dalam bahagian **Definisi ukuran**, anda akan menakrif bagaimana entiti yang dipilih dan pemboleh ubah dikira diagregat dalam entiti ukuran atau atribut baharu.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="3ffa1-138">Pilih **Dimensi baharu**.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-138">Select **New dimension**.</span></span> <span data-ttu-id="3ffa1-139">Anda boleh memikirkan dimensi sebagai fungsi *himpun mengikut*.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="3ffa1-140">Output data untuk entiti atau atribut Ukuran anda akan dihimpun mengikut semua dimensi yang ditakrif oleh anda.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3ffa1-141">![Pilih kitaran agregat](media/measures-businessreport-measure-definition2.png "Pilih kitaran agregat")</span><span class="sxs-lookup"><span data-stu-id="3ffa1-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="3ffa1-142">Pilih atau masukkan maklumat berikut sebagai sebahagian definisi dimensi anda:</span><span class="sxs-lookup"><span data-stu-id="3ffa1-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="3ffa1-143">**Entiti**: Jika anda menakrif entiti Ukuran, ia hendaklah memasukkan sekurang-kurangnya satu atribut.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="3ffa1-144">Jika anda menakrifkan atribut Ukuran, ia hendaklah memasukkan sekurang-kurangnya satu atribut secara lalai.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="3ffa1-145">Pemilihan ini adalah tentang memilih entiti yang memasukkan atribut itu.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="3ffa1-146">**Medan**: Pilih atribut tertentu untuk dimasukkan sama ada dalam entiti atau atribut Ukuran anda.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="3ffa1-147">**Baldi**: Pilih sama ada anda mahu mengumpulkan data secara harian, bulanan, atau tahunan.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="3ffa1-148">Ia adalah pilihan yang diperlukan hanya jika anda telah memilih atribut jenis Tarikh.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="3ffa1-149">**Sebagai**: Takrifkan nama medan baharu anda.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="3ffa1-150">**Nama paparan**: Takrifkan nama paparan medan anda.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ffa1-151">Ukuran perniagaan anda akan disimpan sebagai entiti nombor tunggal dan akan dipaparkan pada halaman **Laman Utama** melainkan anda menambah lebih banyak dimensi pada ukuran anda.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="3ffa1-152">Selepas menambah lebih banyak dimensi, ukuran *tidak* akan ditunjukkan pada halaman **Laman Utama**.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="3ffa1-153">Secara pilihan, tambah fungsi pengagregatan.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="3ffa1-154">Sebarang pengagregatan yang anda cipta hasilnya dalam nilai baharu antara entiti atau atribut Ukuran anda.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="3ffa1-155">Fungsi pengagregatan yang disokong ialah: **Minimum**, **Maksimum**, **Purata**, **Median**, **Jumlah**, **Unik Kiraan**, **Pertama** (mengambil rekod pertama bagi nilai dimensi), dan **Akhir** (mengambil kira rekod terakhir ditambah pada nilai dimensi).</span><span class="sxs-lookup"><span data-stu-id="3ffa1-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="3ffa1-156">Pilih **Simpan** untuk menggunakan perubahan anda pada ukuran.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="3ffa1-157">Urus tindakan anda</span><span class="sxs-lookup"><span data-stu-id="3ffa1-157">Manage your measures</span></span>

<span data-ttu-id="3ffa1-158">Selepas mencipta sekurang-kurangnya satu ukuran, anda akan melihat senarai ukuran pada halaman **Langkah**.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="3ffa1-159">Anda akan menemui maklumat tentang jenis ukuran, pencipta, tarikh dan masa penciptaan, tarikh dan masa edit terakhir, status (sama ada ukuran aktif, tidak aktif, atau gagal), dan tarikh dan masa penyegaran semula terakhir.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="3ffa1-160">Apabila anda memilih tindakan daripada senarai, anda boleh melihat pratonton output.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="3ffa1-161">Untuk menyegarkan semula semua tindakan pada masa yang sama, pilih **Segar semula semua** tanpa memilih tindakan khusus.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3ffa1-162">![Tindakan untuk mengurus langkah tunggal](media/measure-actions.png "Tindakan untuk mengurus langkah tunggal")</span><span class="sxs-lookup"><span data-stu-id="3ffa1-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="3ffa1-163">Secara alternatif, pilih tindakan daripada senarai dan lakukan salah satu daripada tindakan berikut:</span><span class="sxs-lookup"><span data-stu-id="3ffa1-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="3ffa1-164">Pilih nama langkah untuk melihat butiran.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="3ffa1-165">**Edit** konfigurasi langkah.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="3ffa1-166">**Nama semula** langkah.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-166">**Rename** the measure.</span></span>
- <span data-ttu-id="3ffa1-167">**Padam** langkah.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-167">**Delete** the measure.</span></span>
- <span data-ttu-id="3ffa1-168">Pilih elipsis (...) dan kemudian **Segar semula** untuk memulakan proses segar semula untuk tindakan.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="3ffa1-169">Pilih elipsis (...) dan kemudian **Muat turun** untuk mendapatkan Fail .CSV tindakan.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="3ffa1-170">Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3ffa1-171">Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="3ffa1-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3ffa1-172">Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3ffa1-173">Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="3ffa1-174">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="3ffa1-174">Next step</span></span>

<span data-ttu-id="3ffa1-175">Anda boleh menggunakan ukuran sedia ada untuk mencipta bahagian pelanggan pertama pada halaman **Bahagian**.</span><span class="sxs-lookup"><span data-stu-id="3ffa1-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="3ffa1-176">Untuk maklumat lanjut, lihat [Bahagian](segments.md).</span><span class="sxs-lookup"><span data-stu-id="3ffa1-176">For more information, see [Segments](segments.md).</span></span>
