---
title: Gabung entiti dalam penyatuan data
description: Gabung entiti untuk mencipta profil pelanggan disatukan.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597844"
---
# <a name="merge-entities"></a><span data-ttu-id="f6882-103">Gabungkan entiti</span><span class="sxs-lookup"><span data-stu-id="f6882-103">Merge entities</span></span>

<span data-ttu-id="f6882-104">Fasa gabung ialah fasa terakhir dalam proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="f6882-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="f6882-105">Tujuannya ialah untuk menyesuaikan data berkonflik.</span><span class="sxs-lookup"><span data-stu-id="f6882-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="f6882-106">Contoh data berkonflik termasuk nama pelanggan yang ditemui dalam dua set data anda tetapi menunjukkan sedikit berbeza dalam setiap ("Grant Marshall" berbanding "Grant Marshal") atau nombor telefon yang berbeza dalam format (617-803-091X berbanding 617803091X).</span><span class="sxs-lookup"><span data-stu-id="f6882-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="f6882-107">Menggabungkan titik data berkonflik itu dilakukan secara atribut dengan atribut.</span><span class="sxs-lookup"><span data-stu-id="f6882-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="f6882-108">Selepas menyelesaikan [fasa padan](match-entities.md), anda boleh memulakan fasa gabung dengan memilih jubin **Gabung** pada halaman **Satukan**.</span><span class="sxs-lookup"><span data-stu-id="f6882-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="f6882-109">Semak semula pengesyoran sistem</span><span class="sxs-lookup"><span data-stu-id="f6882-109">Review system recommendations</span></span>

<span data-ttu-id="f6882-110">Pada halaman **Gabung**, anda memilih dan mengecualikan atribut untuk menggabungkan dalam entiti profil pelanggan disatukan anda (hasil daripada proses konfigurasi).</span><span class="sxs-lookup"><span data-stu-id="f6882-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="f6882-111">Sesetengah atribut digabungkan oleh sistem secara automatik.</span><span class="sxs-lookup"><span data-stu-id="f6882-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="f6882-112">Lihat atribut yang digabungkan</span><span class="sxs-lookup"><span data-stu-id="f6882-112">View merged attributes</span></span>

<span data-ttu-id="f6882-113">Untuk melihat atribut yang dimasukkan dalam salah satu atribut yang digabungkan secara automatik, pilih atribut yang digabungkan itu.</span><span class="sxs-lookup"><span data-stu-id="f6882-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="f6882-114">Dua atribut yang menggubah atribut yang digabungkan dipaparkan dalam dua baris baharu di bawah atribut yang digabungkan.</span><span class="sxs-lookup"><span data-stu-id="f6882-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f6882-115">![Memilih atribut yang digabungkan](media/configure-data-merge-profile-attributes.png "Pilih atribut yang digabungkan")</span><span class="sxs-lookup"><span data-stu-id="f6882-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="f6882-116">Memisahkan atribut yang digabungkan</span><span class="sxs-lookup"><span data-stu-id="f6882-116">Separate merged attributes</span></span>

<span data-ttu-id="f6882-117">Untuk memisahkan atau membatalkan gabungan mana-mana atribut yang digabungkan secara automatik, cari atribut dalam jadual **Atribut profil**.</span><span class="sxs-lookup"><span data-stu-id="f6882-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="f6882-118">Pilih butang elipsis (...).</span><span class="sxs-lookup"><span data-stu-id="f6882-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="f6882-119">Dalam senarai juntai bawah, pilih **Pisahkan medan**.</span><span class="sxs-lookup"><span data-stu-id="f6882-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="f6882-120">Alih keluar atribut yang digabungkan</span><span class="sxs-lookup"><span data-stu-id="f6882-120">Remove merged attributes</span></span>

<span data-ttu-id="f6882-121">Untuk mengecualikan atribut daripada entiti profil pelanggan terakhir, carinya dalam jadual **Atribut**.</span><span class="sxs-lookup"><span data-stu-id="f6882-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="f6882-122">Pilih butang elipsis (...).</span><span class="sxs-lookup"><span data-stu-id="f6882-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="f6882-123">Dalam senarai juntai bawah, pilih **Jangan gabungkan**.</span><span class="sxs-lookup"><span data-stu-id="f6882-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="f6882-124">Atribut dipindahkan ke bahagian **Alih keluar daripada rekod pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="f6882-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="f6882-125">Menambah atribut yang digabungkan secara manual</span><span class="sxs-lookup"><span data-stu-id="f6882-125">Manually add a merged attribute</span></span>

<span data-ttu-id="f6882-126">Untuk menambah atribut yang digabung, pergi ke halaman **Gabung**.</span><span class="sxs-lookup"><span data-stu-id="f6882-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="f6882-127">Pilih **Tambah atribut yang digabungkan**.</span><span class="sxs-lookup"><span data-stu-id="f6882-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="f6882-128">Berikan **Nama** untuk mengenal pastinya pada halaman **Gabung** kemudian.</span><span class="sxs-lookup"><span data-stu-id="f6882-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="f6882-129">Secara pilihan, sediakan **Nama paparan** yang akan muncul dalam entiti Profil Pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="f6882-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="f6882-130">Konfigurasi **Pilih atribut pendua** untuk memilih atribut yang anda mahu gabung daripada entiti yang dipadankan.</span><span class="sxs-lookup"><span data-stu-id="f6882-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="f6882-131">Anda juga boleh membuat carian untuk atribut.</span><span class="sxs-lookup"><span data-stu-id="f6882-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="f6882-132">Tetapkan **Kedudukan mengikut kepentingan** untuk mengutamakan satu atribut daripada atribut yang lain.</span><span class="sxs-lookup"><span data-stu-id="f6882-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="f6882-133">Contohnya, jika entiti *WebAccountCSV* mengandungi data paling tepat tentang atribut *Nama penuh*, anda boleh mengutamakan entiti ini daripada *ContactCSV* dengan memilih *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="f6882-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="f6882-134">Hasilnya, *WebAccountCSV* akan dipindahkan ke keutamaan pertama, manakala *ContactCSV* akan dipindahkan ke keutamaan kedua semasa menarik nilai untuk atribut *Nama Penuh*.</span><span class="sxs-lookup"><span data-stu-id="f6882-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="f6882-135">Jalankan gabungan anda</span><span class="sxs-lookup"><span data-stu-id="f6882-135">Run your merge</span></span>

<span data-ttu-id="f6882-136">Sama ada anda menggabungkan atribut secara manual atau membiarkan sistem menggabungkannya, anda sentiasa boleh menjalankan gabungan anda.</span><span class="sxs-lookup"><span data-stu-id="f6882-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="f6882-137">Pilih **Jalankan** pada halaman **Gabung** untuk memulakan proses.</span><span class="sxs-lookup"><span data-stu-id="f6882-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f6882-138">![Simpan dan Jalankan gabungan data](media/configure-data-merge-save-run.png "Simpan dan Jalankan Gabungan Data")</span><span class="sxs-lookup"><span data-stu-id="f6882-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="f6882-139">Untuk membuat perubahan tambahan dan jalankan semula langkah, anda boleh membatalkan gabungan dalam kemajuan.</span><span class="sxs-lookup"><span data-stu-id="f6882-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="f6882-140">Pilih teks **Menyegarkan semula ...** dan pilih **Batal kerja** di bahagian tepi tetingkap yang muncul.</span><span class="sxs-lookup"><span data-stu-id="f6882-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="f6882-141">Selepas **Menyegarkan semula ...** teks berubah kepada **Berjaya**, gabungan telah sempurna dan selesaikan konflik dalam data anda mengikut dasar yang anda takrifkan.</span><span class="sxs-lookup"><span data-stu-id="f6882-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="f6882-142">Atribut gabung dan tidak digabungkan dimasukkan dalam entiti profil disatukan.</span><span class="sxs-lookup"><span data-stu-id="f6882-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="f6882-143">Atribut yang dikecualikan tidak dimasukkan dalam entiti profil disatukan.</span><span class="sxs-lookup"><span data-stu-id="f6882-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="f6882-144">Jika ia bukan kali pertama anda menjalankan dengan berjaya, semua proses hilir, termasuk pengayaan, pensegmenan dan langkah akan dijalankan semula secara automatik.</span><span class="sxs-lookup"><span data-stu-id="f6882-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="f6882-145">Selepas semua proses hilir telah dijalankan semula, profil pelanggan menunjukkan perubahan yang anda lakukan.</span><span class="sxs-lookup"><span data-stu-id="f6882-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="f6882-146">Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="f6882-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f6882-147">Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f6882-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f6882-148">Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja.</span><span class="sxs-lookup"><span data-stu-id="f6882-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f6882-149">Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="f6882-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="f6882-150">Langkah Seterusnya</span><span class="sxs-lookup"><span data-stu-id="f6882-150">Next Step</span></span>

<span data-ttu-id="f6882-151">Konfigurasikan [aktiviti](activities.md), [pengayaan](enrichment-microsoft-graph.md) atau [perhubungan](relationships.md) untuk mendapatkan wawasan lanjut tentang pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="f6882-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="f6882-152">Jika anda sudah mengkonfigurasi aktiviti, pengayaan atau perhubungan, atau jika anda mentakrifkan segmen, ia akan diproses secara automatik untuk menggunakan data pelanggan terkini.</span><span class="sxs-lookup"><span data-stu-id="f6882-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]