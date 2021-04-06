---
title: Cipta dan urus segmen
description: Cipta bahagian pelanggan untuk mengumpul mereka berasaskan pelbagai atribut.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597065"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="8d96b-103">Cipta dan urus segmen</span><span class="sxs-lookup"><span data-stu-id="8d96b-103">Create and manage segments</span></span>

<span data-ttu-id="8d96b-104">Segmen membolehkan anda mengumpulkan pelanggan berdasarkan atribut demografi, transaksi atau tingkah laku.</span><span class="sxs-lookup"><span data-stu-id="8d96b-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="8d96b-105">Anda boleh menggunakan segmen untuk kempen promosi sasaran, aktiviti jualan dan tindakan sokongan pelanggan untuk mencapai matlamat perniagaan anda.</span><span class="sxs-lookup"><span data-stu-id="8d96b-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="8d96b-106">Anda boleh menakrif penapis kompleks dalam entiti Profil Pelanggan dan entiti yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="8d96b-107">Setiap segmen, selepas pemprosesan, mencipta set rekod pelanggan yang boleh anda eksport dan ambil tindakan padanya.</span><span class="sxs-lookup"><span data-stu-id="8d96b-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="8d96b-108">Sesetengah [had perkhidmatan](service-limits.md) diguna pakai.</span><span class="sxs-lookup"><span data-stu-id="8d96b-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="8d96b-109">Melainkan jika dinyatakan sebaliknya, semua segmen merupakan **Segmen dinamik**, yang disegar semula pada jadual berulang.</span><span class="sxs-lookup"><span data-stu-id="8d96b-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="8d96b-110">Contoh berikut menunjukkan keupayaan pembahagian.</span><span class="sxs-lookup"><span data-stu-id="8d96b-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="8d96b-111">Kami telah menentukan segmen untuk pelanggan yang mengarahkan sekurang-kurangnya $500 barangan dalam 90 hari yang lalu *dan* yang terlibat dalam panggilan khidmat pelanggan yang telah dipertingkatkan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d96b-112">![Berbilang kumpulan](media/segmentation-group1-2.png "Berbilang kumpulan")</span><span class="sxs-lookup"><span data-stu-id="8d96b-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="8d96b-113">Cipta bahagian baharu</span><span class="sxs-lookup"><span data-stu-id="8d96b-113">Create a new segment</span></span>

<span data-ttu-id="8d96b-114">Segmen diuruskan pada halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="8d96b-115">Dalam cerapan khalayak, pergi ke halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="8d96b-116">Pilih **Baharu** > **Segmen kosong**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="8d96b-117">Dalam anak tetingkap **Bahagian baharu**, pilih jenis bahagian dan berikan **Nama**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="8d96b-118">Secara pilihan, berikan nama paparan, dan description yang membantu mengenal pasti bahagian.</span><span class="sxs-lookup"><span data-stu-id="8d96b-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="8d96b-119">Pilih **Seterusnya** untuk mendapatkan halaman **Pembina bahagian** di mana anda menakrif kumpulan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="8d96b-120">Kumpulan ialah set pelanggan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="8d96b-121">Pilih entiti yang merangkumi atribut yang anda mahu dibahagikan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="8d96b-122">Pilih atribut untuk segmen mengikut.</span><span class="sxs-lookup"><span data-stu-id="8d96b-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="8d96b-123">Atribut ini boleh mempunyai salah satu daripada empat jenis nilai: berangka, rentetan, tarikh atau Boolean.</span><span class="sxs-lookup"><span data-stu-id="8d96b-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="8d96b-124">Pilih operator dan nilai untuk atribut yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="8d96b-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d96b-125">![Penapis kumpulan tersuai](media/customer-group-numbers.png "Penapis kumpulan pelanggan")</span><span class="sxs-lookup"><span data-stu-id="8d96b-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="8d96b-126">Nombor</span><span class="sxs-lookup"><span data-stu-id="8d96b-126">Number</span></span> |<span data-ttu-id="8d96b-127">Definisi</span><span class="sxs-lookup"><span data-stu-id="8d96b-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="8d96b-128">1</span><span class="sxs-lookup"><span data-stu-id="8d96b-128">1</span></span>     |<span data-ttu-id="8d96b-129">Entity</span><span class="sxs-lookup"><span data-stu-id="8d96b-129">Entity</span></span>          |
   |<span data-ttu-id="8d96b-130">2</span><span class="sxs-lookup"><span data-stu-id="8d96b-130">2</span></span>     |<span data-ttu-id="8d96b-131">Atribut</span><span class="sxs-lookup"><span data-stu-id="8d96b-131">Attribute</span></span>          |
   |<span data-ttu-id="8d96b-132">3</span><span class="sxs-lookup"><span data-stu-id="8d96b-132">3</span></span>    |<span data-ttu-id="8d96b-133">Operator</span><span class="sxs-lookup"><span data-stu-id="8d96b-133">Operator</span></span>         |
   |<span data-ttu-id="8d96b-134">4</span><span class="sxs-lookup"><span data-stu-id="8d96b-134">4</span></span>    |<span data-ttu-id="8d96b-135">Nilai</span><span class="sxs-lookup"><span data-stu-id="8d96b-135">Value</span></span>         |

8. <span data-ttu-id="8d96b-136">Jika entiti disambungkan kepada entiti pelanggan disatukan melalui [perhubungan](relationships.md), anda perlu mentakrifkan laluan perhubungan untuk mencipta segmen yang sah.</span><span class="sxs-lookup"><span data-stu-id="8d96b-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="8d96b-137">Tambah entiti daripada laluan perhubungan sehingga anda boleh memilih entiti **Pelanggan : CustomerInsights** daripada juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="8d96b-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="8d96b-138">Kemudian, pilih **Semua rekod** untuk setiap syarat.</span><span class="sxs-lookup"><span data-stu-id="8d96b-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d96b-139">![Laluan perhubungan semasa penciptaan segmen](media/segments-multiple-relationships.png "Laluan perhubungan semasa penciptaan segmen")</span><span class="sxs-lookup"><span data-stu-id="8d96b-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="8d96b-140">Secara lalai, segmen menjana entiti output yang mengandungi semua atribut profil pelanggan yang sepadan dengan penapis yang ditentukan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="8d96b-141">Jika segmen berdasarkan entiti lain daripada entiti *Pelanggan*, anda boleh menambahkan lebih banyak atribut daripada entiti tersebut kepada entiti output.</span><span class="sxs-lookup"><span data-stu-id="8d96b-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="8d96b-142">Pilih **Atribut projek** untuk memilih atribut yang akan ditambah pada entiti output.</span><span class="sxs-lookup"><span data-stu-id="8d96b-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="8d96b-143">Contoh: Segmen berdasarkan entiti yang mengandungi data aktiviti pelanggan yang berkaitan dengan entiti *Pelanggan*.</span><span class="sxs-lookup"><span data-stu-id="8d96b-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="8d96b-144">Segmen mencari semua pelanggan yang memanggil meja bantuan dalam masa 60 hari yang lalu.</span><span class="sxs-lookup"><span data-stu-id="8d96b-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="8d96b-145">Anda boleh memilih untuk menambah tempoh panggilan dan bilangan panggilan kepada semua rekod pelanggan yang sepadan dalam entiti output.</span><span class="sxs-lookup"><span data-stu-id="8d96b-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="8d96b-146">Maklumat ini mungkin berguna untuk menghantar e-mel dengan pautan berguna ke artikel bantuan dalam talian dan soalan lazim kepada pelanggan yang sering membuat panggilan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="8d96b-147">Pilih **Simpan** untuk menyimpan bahagian anda.</span><span class="sxs-lookup"><span data-stu-id="8d96b-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="8d96b-148">Bahagian anda akan disimpan dan diproses jika semua keperluan disahkan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="8d96b-149">Jika tidak, ia akan disimpan sebagai draf.</span><span class="sxs-lookup"><span data-stu-id="8d96b-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="8d96b-150">Pilih **Kembali ke segmen** untuk kembali ke halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="8d96b-151">Mengurus bahagian sedia ada</span><span class="sxs-lookup"><span data-stu-id="8d96b-151">Manage existing segments</span></span>

<span data-ttu-id="8d96b-152">Pada halaman **Bahagian**, anda boleh melihat semua bahagian yang anda simpan dan mengurusnya.</span><span class="sxs-lookup"><span data-stu-id="8d96b-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="8d96b-153">Setiap segmen diwakili oleh baris yang menyertakan maklumat tambahan tentang segmen.</span><span class="sxs-lookup"><span data-stu-id="8d96b-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="8d96b-154">Anda boleh menyusun segmen dalam lajur dengan memilih tajuk lajur.</span><span class="sxs-lookup"><span data-stu-id="8d96b-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="8d96b-155">Gunakan kotak **Cari** di sudut kanan atas untuk menapis segmen.</span><span class="sxs-lookup"><span data-stu-id="8d96b-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d96b-156">![Pilihan untuk menguruskan segmen sedia ada](media/segments-selected-segment.png "Pilihan untuk menguruskan segmen sedia ada")</span><span class="sxs-lookup"><span data-stu-id="8d96b-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="8d96b-157">Tindakan yang berikut tersedia apabila anda memilih segmen:</span><span class="sxs-lookup"><span data-stu-id="8d96b-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="8d96b-158">**Lihat** butiran segmen, termasuk trend kiraan ahli pratonton ahli segmen.</span><span class="sxs-lookup"><span data-stu-id="8d96b-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="8d96b-159">**Edit** segmen untuk mengubah sifatnya.</span><span class="sxs-lookup"><span data-stu-id="8d96b-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="8d96b-160">**Cipta duplikasi** segmen.</span><span class="sxs-lookup"><span data-stu-id="8d96b-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="8d96b-161">Anda boleh memilih untuk mengedit sifat dengan serta-merta atau hanya menyimpan duplikasi.</span><span class="sxs-lookup"><span data-stu-id="8d96b-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="8d96b-162">**Segar semula** segmen untuk memasukkan data terkini.</span><span class="sxs-lookup"><span data-stu-id="8d96b-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="8d96b-163">**Aktifkan** atau **Nyahaktifkan** segmen.</span><span class="sxs-lookup"><span data-stu-id="8d96b-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="8d96b-164">Segmen mempunyai dua keadaan yang mungkin - aktif atau tidak aktif.</span><span class="sxs-lookup"><span data-stu-id="8d96b-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="8d96b-165">Keadaan ini berguna apabila mengedit segmen.</span><span class="sxs-lookup"><span data-stu-id="8d96b-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="8d96b-166">Untuk segmen tidak aktif, takrifan segmen wujud tetapi ia tidak mengandungi sebarang pelanggan lagi.</span><span class="sxs-lookup"><span data-stu-id="8d96b-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="8d96b-167">Apabila anda mengaktifkan segmen, keadaannya berubah daripada 'tidak aktif' kepada 'aktif" dan ia mula mencari pelanggan yang sepadan dengan takrifan segmen.</span><span class="sxs-lookup"><span data-stu-id="8d96b-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="8d96b-168">Jika [segar semula berjadual](system.md#schedule-tab) dikonfigurasikan, segmen yang tidak aktif mempunyai **Status** yang disenaraikan sebagai **Dilangkau**, menunjukkan bahawa segar semula tidak pernah dicuba.</span><span class="sxs-lookup"><span data-stu-id="8d96b-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="8d96b-169">Apabila segmen yang tidak aktif diaktifkan, ia akan menyegar semula dan akan disertakan dalam segar semula berjadual.</span><span class="sxs-lookup"><span data-stu-id="8d96b-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="8d96b-170">Secara alternatif, anda boleh menggunakan kefungsian **Jadual kemudian** dalam juntai bawah **Aktifkan/Nyahaktifkan** untuk menetapkan tarikh dan masa pada masa depan untuk pengaktifan dan penyahaktifan segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="8d96b-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="8d96b-171">**Nama semula** segmen.</span><span class="sxs-lookup"><span data-stu-id="8d96b-171">**Rename** the segment.</span></span>
- <span data-ttu-id="8d96b-172">**Muat turun** senarai ahli sebagai fail .CSV.</span><span class="sxs-lookup"><span data-stu-id="8d96b-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="8d96b-173">Pilihan **Tambahkan pada** menghantar senarai ID Pelanggan dalam segmen untuk pemprosesan dalam aplikasi lain.</span><span class="sxs-lookup"><span data-stu-id="8d96b-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="8d96b-174">**Padamkan** segmen.</span><span class="sxs-lookup"><span data-stu-id="8d96b-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="8d96b-175">Segar semula segmen</span><span class="sxs-lookup"><span data-stu-id="8d96b-175">Refresh segments</span></span>

<span data-ttu-id="8d96b-176">Anda boleh memuatkan semula semua segmen serentak dengan memilih **Muat semula semua** pada halaman **Segmen** atau anda boleh memuatkan semula satu atau berbilang segmen apabila anda memilihnya dan memilih **Muat semula** daripada pilihan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="8d96b-177">Sebagai alternatif, anda boleh mengkonfigurasi segar semula pada **Pentadbir** > **Sistem** > **Jadual**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="8d96b-178">Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="8d96b-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="8d96b-179">Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="8d96b-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="8d96b-180">Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja.</span><span class="sxs-lookup"><span data-stu-id="8d96b-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="8d96b-181">Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="8d96b-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="8d96b-182">Muat turun dan mengeksport segmen</span><span class="sxs-lookup"><span data-stu-id="8d96b-182">Download and export segments</span></span>

<span data-ttu-id="8d96b-183">Anda boleh memuat turun segmen anda ke fail CSV atau eksportnya ke Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="8d96b-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="8d96b-184">Muat turun segmen ke fail CSV</span><span class="sxs-lookup"><span data-stu-id="8d96b-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="8d96b-185">Dalam cerapan khalayak, pergi ke halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="8d96b-186">Pilih elipsis dalam jubin segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="8d96b-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="8d96b-187">Pilih **Muat Turun sebagai CSV** daripada tindakan senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="8d96b-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="8d96b-188">Eksport segmen ke Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="8d96b-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="8d96b-189">Sebelum mengeksport segmen ke Dynamics 365 Sales, pentadbir perlu [mencipta destinasi eksport](export-destinations.md) untuk Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="8d96b-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="8d96b-190">Dalam cerapan khalayak, pergi ke halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="8d96b-191">Pilih elipsis dalam jubin segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="8d96b-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="8d96b-192">Pilih **Tambah** daripada tindakan senarai juntai bawah dan pilih destinasi eksport yang anda mahu hantarkan data.</span><span class="sxs-lookup"><span data-stu-id="8d96b-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="8d96b-193">Mod draf untuk bahagian</span><span class="sxs-lookup"><span data-stu-id="8d96b-193">Draft mode for segments</span></span>

<span data-ttu-id="8d96b-194">Jika tidak semua keperluan untuk bahagian diproses dipenuhi, anda boleh menyimpan bahagian sebagai draf dan mengaksesnya daripada halaman **Bahagian**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="8d96b-195">Ia akan disimpan sebagai segmen tidak aktif dan tidak boleh diaktifkan sehingga ia sah.</span><span class="sxs-lookup"><span data-stu-id="8d96b-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="8d96b-196">Menambah lebih banyak syarat ke kumpulan</span><span class="sxs-lookup"><span data-stu-id="8d96b-196">Add more conditions to a group</span></span>

<span data-ttu-id="8d96b-197">Untuk menambahkan lebih banyak syarat ke kumpulan, anda boleh menggunakan dua operator logik:</span><span class="sxs-lookup"><span data-stu-id="8d96b-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="8d96b-198">Operator **DAN**: Kedua-dua syarat mesti dipenuhi sebagai sebahagian proses pembahagian.</span><span class="sxs-lookup"><span data-stu-id="8d96b-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="8d96b-199">Pilihan ini adalah paling berguna apabila anda menakrif syarat dalam entiti yang berbeza.</span><span class="sxs-lookup"><span data-stu-id="8d96b-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="8d96b-200">Operator **ATAU**: Salah satu syarat perlu dipenuhi sebagai sebahagian daripada proses pembahagian.</span><span class="sxs-lookup"><span data-stu-id="8d96b-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="8d96b-201">Pilihan ini paling berguna apabila anda menakrif berbilang syarat untuk entiti yang sama.</span><span class="sxs-lookup"><span data-stu-id="8d96b-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d96b-202">![Operator ATAU di mana salah satu syarat perlu dipenuhi](media/segmentation-either-condition.png "Operator ATAU di mana salah satu syarat perlu dipenuhi")</span><span class="sxs-lookup"><span data-stu-id="8d96b-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="8d96b-203">Pada masa ini berkemungkinan untuk menyarang operator **ATAU** di bawah operator **DAN**, tetapi tidak sebaliknya.</span><span class="sxs-lookup"><span data-stu-id="8d96b-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="8d96b-204">Menggabungkan berbilang kumpulan</span><span class="sxs-lookup"><span data-stu-id="8d96b-204">Combine multiple groups</span></span>

<span data-ttu-id="8d96b-205">Setiap kumpulan menghasilkan set pelanggan khusus.</span><span class="sxs-lookup"><span data-stu-id="8d96b-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="8d96b-206">Anda boleh menggabungkan kumpulan ini untuk memasukkan pelanggan yang diperlukan untuk kes perniagaan anda.</span><span class="sxs-lookup"><span data-stu-id="8d96b-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="8d96b-207">Dalam cerapan khalayak, pergi ke halaman **Segmen** dan pilih satu segmen.</span><span class="sxs-lookup"><span data-stu-id="8d96b-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="8d96b-208">Pilih **Tambah Kumpulan**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d96b-209">![Kumpulan pelanggan tambah kumpulan](media/customer-group-add-group.png "Kumpulan pelanggan tambah kumpulan")</span><span class="sxs-lookup"><span data-stu-id="8d96b-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="8d96b-210">Pilih salah satu pengendali set berikut: **Kesatuan**, **Silang** atau **Kecuali**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d96b-211">![Kumpulan pelanggan tambah kesatuan](media/customer-group-union.png "Kumpulan pelanggan tambah kesatuan")</span><span class="sxs-lookup"><span data-stu-id="8d96b-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="8d96b-212">Pilih operasi set untuk mentakrifkan kumpulan baharu.</span><span class="sxs-lookup"><span data-stu-id="8d96b-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="8d96b-213">Simpan kumpulan yang berbeza untuk menentukan data yang dapat dikekalkan:</span><span class="sxs-lookup"><span data-stu-id="8d96b-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="8d96b-214">**Kesatuan** menyatukan dua kumpulan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="8d96b-215">**Bersilang** dua kumpulan bertindih.</span><span class="sxs-lookup"><span data-stu-id="8d96b-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="8d96b-216">Hanya data yang *umum* pada kedua-dua kumpulan dikekalkan dalam kumpulan disatukan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="8d96b-217">**Kecuali** menggabungkan dua kumpulan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-217">**Except** combines the two groups.</span></span> <span data-ttu-id="8d96b-218">Hanya data dalam kumpulan A yang *tidak umum* pada data dalam kumpulan B dikekalkan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="8d96b-219">Lihat sejarah pemprosesan dan ahli bahagian</span><span class="sxs-lookup"><span data-stu-id="8d96b-219">View processing history and segment members</span></span>

<span data-ttu-id="8d96b-220">anda boleh melihat penyatuan data tentang bahagian dengan menyemak semula butirannya.</span><span class="sxs-lookup"><span data-stu-id="8d96b-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="8d96b-221">Pada halaman **Bahagian**, pilih bahagian yang anda mahu semak semula.</span><span class="sxs-lookup"><span data-stu-id="8d96b-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="8d96b-222">Bahagian atas halaman termasuk graf trend yang menggambarkan perubahan dalam kiraan ahli.</span><span class="sxs-lookup"><span data-stu-id="8d96b-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="8d96b-223">Tuding pada titik data untuk melihat kiraan ahli pada tarikh tertentu.</span><span class="sxs-lookup"><span data-stu-id="8d96b-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="8d96b-224">Anda boleh mengemas kini tempoh masa bagi visualisasi.</span><span class="sxs-lookup"><span data-stu-id="8d96b-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d96b-225">![Julat masa bahagian](media/segment-time-range.png "Julat masa bahagian")</span><span class="sxs-lookup"><span data-stu-id="8d96b-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="8d96b-226">Bahagian bawah mengandungi senarai ahli bahagian.</span><span class="sxs-lookup"><span data-stu-id="8d96b-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="8d96b-227">Medan yang muncul dalam senarai adalah berasaskan pada atribut bagi entiti segmen anda.</span><span class="sxs-lookup"><span data-stu-id="8d96b-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="8d96b-228">Senarai ialah pratonton bagi pemadanan ahli bahagian dan menunjukkan 100 rekod pertama bahagian anda supaya anda boleh segera menilainya dan menyemak semula definisinya jika perlu.</span><span class="sxs-lookup"><span data-stu-id="8d96b-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="8d96b-229">Untuk melihat semua rekod yang sepadan, anda perlu [mengeksport bahagian](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8d96b-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="8d96b-230">Segmen pantas</span><span class="sxs-lookup"><span data-stu-id="8d96b-230">Quick segments</span></span>

<span data-ttu-id="8d96b-231">Sebagai tambahan kepada pembina segmen, terdapat satu lagi laluan untuk mencipta segmen.</span><span class="sxs-lookup"><span data-stu-id="8d96b-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="8d96b-232">Segmen pantas membolehkan anda membina segmen ringkas dengan operator tunggal dengan cepat dan dengan cerapan segera.</span><span class="sxs-lookup"><span data-stu-id="8d96b-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="8d96b-233">Pada halaman **Segmen**, pilih **Baharu** > **Cipta dengan cepat daripada**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="8d96b-234">Pilih pilihan **Profil** untuk membina bahagian yang berasaskan pada entiti Pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="8d96b-235">Pilih pilihan **Ukuran** untuk membina segment dalam setiap jenis ukuran atribut pelanggan yang telah anda cipta sebelum ini pada halaman **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="8d96b-236">Pilih pilihan **Kecerdasan** untuk membina segmen di sekitar salah satu entiti output yang dijana anda menggunakan sama ada keupayaan **Ramalan** atau **Model Tersuai**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="8d96b-237">Dalam kotak dialog **Segmen pantas baharu**, pilih atribut daripada **Medan** juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="8d96b-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="8d96b-238">Sistem akan memberikan wawasan tambahan yang membantu anda mencipta bahagian yang lebih baik untuk pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="8d96b-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="8d96b-239">Untuk medan kategori, kami akan menunjukkan 10 kiraan pelanggan teratas.</span><span class="sxs-lookup"><span data-stu-id="8d96b-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="8d96b-240">Pilih **Nilai** dan pilih **Semak Semula**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="8d96b-241">Untuk atribut numerik, sistem akan menunjukkan apakah nilai atribut yang jatuh dalam setiap persentil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="8d96b-242">Pilih **Operator** dan **Nilai**, kemudian pilih **Semak Semula**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="8d96b-243">Sistem akan memberikan anda **saiz bahagian yang dianggarkan**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="8d96b-244">Anda boleh memilih sama ada untuk menjana bahagian yang anda takrif, atau kunjungi semula terlebih dahulu untuk mendapatkan saiz bahagian yang berbeza.</span><span class="sxs-lookup"><span data-stu-id="8d96b-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8d96b-245">![Nama dan anggaran bagi bahagian pantas](media/quick-segment-name.png "Nama dan anggaran bagi bahagian pantas")</span><span class="sxs-lookup"><span data-stu-id="8d96b-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="8d96b-246">Berikan **Nama** untuk bahagian anda.</span><span class="sxs-lookup"><span data-stu-id="8d96b-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="8d96b-247">Secara pilihan, berikan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="8d96b-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="8d96b-248">Pilih **Simpan** untuk mencipta bahagian.</span><span class="sxs-lookup"><span data-stu-id="8d96b-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="8d96b-249">Selepas bahagian selesai diproses, anda boleh melihatnya seperti bahagian lain yang anda cipta.</span><span class="sxs-lookup"><span data-stu-id="8d96b-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="8d96b-250">Untuk senario berikut, kami menyarankan penggunaan pembina bahagian berbanding keupayaan bahagian yang disyorkan:</span><span class="sxs-lookup"><span data-stu-id="8d96b-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="8d96b-251">Mencipta bahagian dengan penapis pada medan kategori di mana operator berbeza daripada operator **Is**</span><span class="sxs-lookup"><span data-stu-id="8d96b-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="8d96b-252">Mencipta bahagian dengan penapis pada medan numerik di mana operator berbeza daripada operator **Antara**, **Lebih daripada**, dan **Kurang daripada**</span><span class="sxs-lookup"><span data-stu-id="8d96b-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="8d96b-253">Cipta segmen dengan penapis pada medan jenis tarikh</span><span class="sxs-lookup"><span data-stu-id="8d96b-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="8d96b-254">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="8d96b-254">Next steps</span></span>

<span data-ttu-id="8d96b-255">[Eksport bahagian](export-destinations.md) dan teroka [Kad Pelanggan](customer-card-add-in.md) dan [Penyambung](export-power-bi.md) untuk mendapatkan wawasan pada peringkat pelanggan.</span><span class="sxs-lookup"><span data-stu-id="8d96b-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]