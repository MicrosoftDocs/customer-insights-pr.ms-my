---
title: Gabung entiti dalam penyatuan data
description: Gabung entiti untuk mencipta profil pelanggan disatukan.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085587"
---
# <a name="merge-entities"></a><span data-ttu-id="9e337-103">Gabungkan entiti</span><span class="sxs-lookup"><span data-stu-id="9e337-103">Merge entities</span></span>

<span data-ttu-id="9e337-104">Fasa gabung ialah fasa terakhir dalam proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="9e337-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="9e337-105">Tujuannya ialah untuk menyesuaikan data berkonflik.</span><span class="sxs-lookup"><span data-stu-id="9e337-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="9e337-106">Contoh data berkonflik termasuk nama pelanggan yang ditemui dalam dua set data anda tetapi menunjukkan sedikit berbeza dalam setiap ("Grant Marshall" berbanding "Grant Marshal") atau nombor telefon yang berbeza dalam format (617-803-091X berbanding 617803091X).</span><span class="sxs-lookup"><span data-stu-id="9e337-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="9e337-107">Menggabungkan titik data berkonflik itu dilakukan secara atribut dengan atribut.</span><span class="sxs-lookup"><span data-stu-id="9e337-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Halaman gabung dalam proses penyatuan data menunjukkan jadual dengan medan digabungkan yang mentakrifkan profil pelanggan disatukan.":::

<span data-ttu-id="9e337-109">Selepas menyelesaikan [fasa padan](match-entities.md), anda boleh memulakan fasa gabung dengan memilih jubin **Gabung** pada halaman **Satukan**.</span><span class="sxs-lookup"><span data-stu-id="9e337-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="9e337-110">Semak semula pengesyoran sistem</span><span class="sxs-lookup"><span data-stu-id="9e337-110">Review system recommendations</span></span>

<span data-ttu-id="9e337-111">Pada **Data** > **Satukan** > **Gabung**, anda memilih dan mengecualikan atribut untuk bergabung dalam entiti profil pelanggan disatukan anda.</span><span class="sxs-lookup"><span data-stu-id="9e337-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="9e337-112">Profil pelanggan disatukan adalah hasil daripada proses data penyatuan.</span><span class="sxs-lookup"><span data-stu-id="9e337-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="9e337-113">Sesetengah atribut digabungkan oleh sistem secara automatik.</span><span class="sxs-lookup"><span data-stu-id="9e337-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="9e337-114">Untuk melihat atribut yang disertakan dalam salah satu atribut yang digabungkan secara automatik, pilih atribut yang digabungkan dalam tab **Medan pelanggan** jadual.</span><span class="sxs-lookup"><span data-stu-id="9e337-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="9e337-115">Atribut yang digubah bagi atribut yang digabungkan dipaparkan dalam dua baris baharu di bawah atribut yang digabungkan.</span><span class="sxs-lookup"><span data-stu-id="9e337-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="9e337-116">Asingkan, namakan semula, kecualikan, dan edit medan yang digabungkan</span><span class="sxs-lookup"><span data-stu-id="9e337-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="9e337-117">Anda boleh mengubah cara sistem memproses atribut yang digabungkan untuk menjana profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="9e337-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="9e337-118">Pilih **Tunjukkan lagi** dan pilih perkara yang anda mahu ubah.</span><span class="sxs-lookup"><span data-stu-id="9e337-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Pilihan dalam menu juntai bawah Tunjukkan lagi untuk mengurus atribut yang digabungkan.":::

<span data-ttu-id="9e337-120">Untuk maklumat lanjut, lihat bahagian berikut.</span><span class="sxs-lookup"><span data-stu-id="9e337-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="9e337-121">Pisahkan medan yang digabungkan</span><span class="sxs-lookup"><span data-stu-id="9e337-121">Separate merged fields</span></span>

<span data-ttu-id="9e337-122">Untuk memisahkan medan yang digabungkan, cari atribut dalam jadual.</span><span class="sxs-lookup"><span data-stu-id="9e337-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="9e337-123">Medan yang dipisahkan ditunjukkan sebagai titik data individu pada profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="9e337-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="9e337-124">Pilih medan yang digabungkan.</span><span class="sxs-lookup"><span data-stu-id="9e337-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="9e337-125">Pilih **Tunjukkan lagi** dan pilih **Medan berasingan**.</span><span class="sxs-lookup"><span data-stu-id="9e337-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="9e337-126">Sahkan pengasingan.</span><span class="sxs-lookup"><span data-stu-id="9e337-126">Confirm the separation.</span></span>

1. <span data-ttu-id="9e337-127">Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.</span><span class="sxs-lookup"><span data-stu-id="9e337-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="9e337-128">Namakan semula medan yang digabungkan</span><span class="sxs-lookup"><span data-stu-id="9e337-128">Rename merged fields</span></span>

<span data-ttu-id="9e337-129">Tukar nama paparan bagi atribut yang digabungkan.</span><span class="sxs-lookup"><span data-stu-id="9e337-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="9e337-130">Anda tidak boleh mengubah nama entiti output.</span><span class="sxs-lookup"><span data-stu-id="9e337-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="9e337-131">Pilih medan yang digabungkan.</span><span class="sxs-lookup"><span data-stu-id="9e337-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="9e337-132">Pilih **Tunjukkan lagi** dan pilih **Namakan Semula**.</span><span class="sxs-lookup"><span data-stu-id="9e337-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="9e337-133">Sahkan nama paparan yang ditukar.</span><span class="sxs-lookup"><span data-stu-id="9e337-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="9e337-134">Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.</span><span class="sxs-lookup"><span data-stu-id="9e337-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="9e337-135">Kecualikan medan yang digabungkan</span><span class="sxs-lookup"><span data-stu-id="9e337-135">Exclude merged fields</span></span>

<span data-ttu-id="9e337-136">Kecualikan atribut daripada profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="9e337-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="9e337-137">Jika medan digunakan dalam proses lain, contohnya dalam segmen, alih keluarkannya daripada proses ini sebelum mengecualikannya daripada profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="9e337-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="9e337-138">Pilih medan yang digabungkan.</span><span class="sxs-lookup"><span data-stu-id="9e337-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="9e337-139">Pilih **Tunjukkan lagi** dan pilih **Kecualikan**.</span><span class="sxs-lookup"><span data-stu-id="9e337-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="9e337-140">Sahkan pengecualian.</span><span class="sxs-lookup"><span data-stu-id="9e337-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="9e337-141">Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.</span><span class="sxs-lookup"><span data-stu-id="9e337-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="9e337-142">Pada halaman **Gabung**, pilih **Medan yang dikecualikan** untuk melihat senarai semua medan yang dikecualikan.</span><span class="sxs-lookup"><span data-stu-id="9e337-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="9e337-143">Anak tetingkap ini membenarkan anda menambah semula medan yang dikecualikan.</span><span class="sxs-lookup"><span data-stu-id="9e337-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="9e337-144">Gabungkan medan secara manual</span><span class="sxs-lookup"><span data-stu-id="9e337-144">Manually combine fields</span></span>

<span data-ttu-id="9e337-145">Tentukan atribut yang digabungkan secara manual.</span><span class="sxs-lookup"><span data-stu-id="9e337-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="9e337-146">Pada halaman **Gabung**, pilih **Gabungkan medan**.</span><span class="sxs-lookup"><span data-stu-id="9e337-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="9e337-147">Berikan **Nama** dan **Nama medan output**.</span><span class="sxs-lookup"><span data-stu-id="9e337-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="9e337-148">Pilih medan untuk ditambah.</span><span class="sxs-lookup"><span data-stu-id="9e337-148">Choose a field to add.</span></span> <span data-ttu-id="9e337-149">Pilih **Tambah medan** untuk menggabungkan lebih medan.</span><span class="sxs-lookup"><span data-stu-id="9e337-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="9e337-150">Sahkan pengecualian.</span><span class="sxs-lookup"><span data-stu-id="9e337-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="9e337-151">Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.</span><span class="sxs-lookup"><span data-stu-id="9e337-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="9e337-152">Ubah pesanan pilihan</span><span class="sxs-lookup"><span data-stu-id="9e337-152">Change the order of fields</span></span>

<span data-ttu-id="9e337-153">Sesetengah entiti mengandungi lebih banyak butiran daripada yang lain.</span><span class="sxs-lookup"><span data-stu-id="9e337-153">Some entities contain more details than others.</span></span> <span data-ttu-id="9e337-154">Jika entiti termasuk data terkini tentang medan, anda boleh mengutamakannya daripada entiti lain apabila menggabungkan nilai.</span><span class="sxs-lookup"><span data-stu-id="9e337-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="9e337-155">Pilih medan yang digabungkan.</span><span class="sxs-lookup"><span data-stu-id="9e337-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="9e337-156">Pilih **Tunjukkan lagi** dan pilih **Edit**.</span><span class="sxs-lookup"><span data-stu-id="9e337-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="9e337-157">Dalam anak tetingkap **Gabungkan medan**, pilih **Alih ke atas/ke bawah** untuk menetapkan pesanan atau seret dan lepaskannya dalam kedudukan yang dikehendaki.</span><span class="sxs-lookup"><span data-stu-id="9e337-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="9e337-158">Sahkan perubahan.</span><span class="sxs-lookup"><span data-stu-id="9e337-158">Confirm the change.</span></span>

1. <span data-ttu-id="9e337-159">Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.</span><span class="sxs-lookup"><span data-stu-id="9e337-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="9e337-160">Jalankan gabungan anda</span><span class="sxs-lookup"><span data-stu-id="9e337-160">Run your merge</span></span>

<span data-ttu-id="9e337-161">Sama ada anda menggabungkan atribut secara manual atau membiarkan sistem menggabungkannya, anda sentiasa boleh menjalankan gabungan anda.</span><span class="sxs-lookup"><span data-stu-id="9e337-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="9e337-162">Pilih **Jalankan** pada halaman **Gabung** untuk memulakan proses.</span><span class="sxs-lookup"><span data-stu-id="9e337-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9e337-163">![Simpan dan Jalankan gabungan data](media/configure-data-merge-save-run.png "Simpan dan Jalankan Gabungan Data")</span><span class="sxs-lookup"><span data-stu-id="9e337-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="9e337-164">Pilih **Jalankan Gabungan sahaja** jika anda hanya mahu melihat output yang ditunjukkan dalam entiti pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="9e337-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="9e337-165">Proses hiliran akan disegar semula seperti yang [ditakrifkan dalam jadual segar semula](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9e337-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="9e337-166">Pilih **Jalankan proses Gabungan dan hiliran** untuk menyegar semula sistem dengan perubahan anda.</span><span class="sxs-lookup"><span data-stu-id="9e337-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="9e337-167">Semua proses termasuk pengayaan, segmen dan ukuran akan berjalan semula secara automatik.</span><span class="sxs-lookup"><span data-stu-id="9e337-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="9e337-168">Selepas semua proses hiliran dilengkapkan, profil pelanggan menunjukkan sebarang perubahan yang anda lakukan.</span><span class="sxs-lookup"><span data-stu-id="9e337-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="9e337-169">Untuk membuat lebih banyak perubahan dan menjalankan semula langkah, anda boleh membatalkan penggabungan yang sedang dilaksanakan.</span><span class="sxs-lookup"><span data-stu-id="9e337-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="9e337-170">Pilih teks **Menyegarkan semula ...** dan pilih **Batal kerja** di bahagian tepi tetingkap yang muncul.</span><span class="sxs-lookup"><span data-stu-id="9e337-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="9e337-171">Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="9e337-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="9e337-172">Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="9e337-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="9e337-173">Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja.</span><span class="sxs-lookup"><span data-stu-id="9e337-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="9e337-174">Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="9e337-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="9e337-175">Langkah Seterusnya</span><span class="sxs-lookup"><span data-stu-id="9e337-175">Next Step</span></span>

<span data-ttu-id="9e337-176">Konfigurasikan [aktiviti](activities.md), [pengayaan](enrichment-hub.md) atau [perhubungan](relationships.md) untuk mendapatkan wawasan lanjut tentang pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="9e337-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="9e337-177">Jika anda telah mengkonfigurasikan aktiviti, pengayaan atau segmen, ia akan diproses secara automatik untuk menggunakan data pelanggan terkini.</span><span class="sxs-lookup"><span data-stu-id="9e337-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
