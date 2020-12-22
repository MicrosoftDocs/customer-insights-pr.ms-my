---
title: Cipta dan urus segmen
description: Cipta bahagian pelanggan untuk mengumpul mereka berasaskan pelbagai atribut.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406486"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="b0aec-103">Cipta dan urus segmen</span><span class="sxs-lookup"><span data-stu-id="b0aec-103">Create and manage segments</span></span>

<span data-ttu-id="b0aec-104">Segmen membolehkan anda mengumpulkan pelanggan berdasarkan atribut demografi, transaksi atau tingkah laku.</span><span class="sxs-lookup"><span data-stu-id="b0aec-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="b0aec-105">Anda boleh menggunakan segmen untuk kempen promosi sasaran, aktiviti jualan dan tindakan sokongan pelanggan untuk mencapai matlamat perniagaan anda.</span><span class="sxs-lookup"><span data-stu-id="b0aec-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="b0aec-106">Anda boleh menakrif penapis kompleks dalam entiti Profil Pelanggan dan entiti yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="b0aec-107">Setiap segmen, selepas pemprosesan, mencipta set rekod pelanggan yang boleh anda eksport dan ambil tindakan padanya.</span><span class="sxs-lookup"><span data-stu-id="b0aec-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="b0aec-108">Sesetengah [had perkhidmatan](service-limits.md) diguna pakai.</span><span class="sxs-lookup"><span data-stu-id="b0aec-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="b0aec-109">Melainkan jika dinyatakan sebaliknya, semua segmen merupakan **Segmen dinamik**, yang disegar semula pada jadual berulang.</span><span class="sxs-lookup"><span data-stu-id="b0aec-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="b0aec-110">Contoh berikut menunjukkan keupayaan pembahagian.</span><span class="sxs-lookup"><span data-stu-id="b0aec-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="b0aec-111">Kami telah menentukan segmen untuk pelanggan yang mengarahkan sekurang-kurangnya $500 barangan dalam 90 hari yang lalu *dan* yang terlibat dalam panggilan khidmat pelanggan yang telah dipertingkatkan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b0aec-112">![Berbilang kumpulan](media/segmentation-group1-2.png "Berbilang kumpulan")</span><span class="sxs-lookup"><span data-stu-id="b0aec-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="b0aec-113">Cipta bahagian baharu</span><span class="sxs-lookup"><span data-stu-id="b0aec-113">Create a new segment</span></span>

<span data-ttu-id="b0aec-114">Segmen diuruskan pada halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="b0aec-115">Dalam cerapan khalayak, pergi ke halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="b0aec-116">Pilih **Baharu** > **Segmen kosong**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="b0aec-117">Dalam anak tetingkap **Bahagian baharu**, pilih jenis bahagian dan berikan **Nama**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="b0aec-118">Secara pilihan, berikan nama paparan, dan description yang membantu mengenal pasti bahagian.</span><span class="sxs-lookup"><span data-stu-id="b0aec-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="b0aec-119">Pilih **Seterusnya** untuk mendapatkan halaman **Pembina bahagian** di mana anda menakrif kumpulan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="b0aec-120">Kumpulan ialah set pelanggan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="b0aec-121">Pilih entiti yang merangkumi atribut yang anda mahu dibahagikan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="b0aec-122">Pilih atribut untuk segmen mengikut.</span><span class="sxs-lookup"><span data-stu-id="b0aec-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="b0aec-123">Atribut ini boleh mempunyai salah satu daripada empat jenis nilai: berangka, rentetan, tarikh atau Boolean.</span><span class="sxs-lookup"><span data-stu-id="b0aec-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="b0aec-124">Pilih operator dan nilai untuk atribut yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="b0aec-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b0aec-125">![Penapis kumpulan tersuai](media/customer-group-numbers.png "Penapis kumpulan pelanggan")</span><span class="sxs-lookup"><span data-stu-id="b0aec-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="b0aec-126">Nombor</span><span class="sxs-lookup"><span data-stu-id="b0aec-126">Number</span></span> |<span data-ttu-id="b0aec-127">Definisi</span><span class="sxs-lookup"><span data-stu-id="b0aec-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="b0aec-128">1</span><span class="sxs-lookup"><span data-stu-id="b0aec-128">1</span></span>     |<span data-ttu-id="b0aec-129">Entity</span><span class="sxs-lookup"><span data-stu-id="b0aec-129">Entity</span></span>          |
   |<span data-ttu-id="b0aec-130">2</span><span class="sxs-lookup"><span data-stu-id="b0aec-130">2</span></span>     |<span data-ttu-id="b0aec-131">Atribut</span><span class="sxs-lookup"><span data-stu-id="b0aec-131">Attribute</span></span>          |
   |<span data-ttu-id="b0aec-132">3</span><span class="sxs-lookup"><span data-stu-id="b0aec-132">3</span></span>    |<span data-ttu-id="b0aec-133">Operator</span><span class="sxs-lookup"><span data-stu-id="b0aec-133">Operator</span></span>         |
   |<span data-ttu-id="b0aec-134">4</span><span class="sxs-lookup"><span data-stu-id="b0aec-134">4</span></span>    |<span data-ttu-id="b0aec-135">Nilai</span><span class="sxs-lookup"><span data-stu-id="b0aec-135">Value</span></span>         |

8. <span data-ttu-id="b0aec-136">Jika entiti disambungkan kepada entiti pelanggan disatukan melalui [perhubungan](relationships.md), anda perlu mentakrifkan laluan perhubungan untuk mencipta segmen yang sah.</span><span class="sxs-lookup"><span data-stu-id="b0aec-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="b0aec-137">Tambah entiti daripada laluan perhubungan sehingga anda boleh memilih entiti **Pelanggan : CustomerInsights** daripada juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="b0aec-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="b0aec-138">Kemudian, pilih **Semua rekod** untuk setiap syarat.</span><span class="sxs-lookup"><span data-stu-id="b0aec-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b0aec-139">![Laluan perhubungan semasa penciptaan segmen](media/segments-multiple-relationships.png "Laluan perhubungan semasa penciptaan segmen")</span><span class="sxs-lookup"><span data-stu-id="b0aec-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="b0aec-140">Pilih **Simpan** untuk menyimpan bahagian anda.</span><span class="sxs-lookup"><span data-stu-id="b0aec-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="b0aec-141">Bahagian anda akan disimpan dan diproses jika semua keperluan disahkan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="b0aec-142">Jika tidak, ia akan disimpan sebagai draf.</span><span class="sxs-lookup"><span data-stu-id="b0aec-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="b0aec-143">Pilih **Kembali ke segmen** untuk kembali ke halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="b0aec-144">Mengurus bahagian sedia ada</span><span class="sxs-lookup"><span data-stu-id="b0aec-144">Manage existing segments</span></span>

<span data-ttu-id="b0aec-145">Pada halaman **Bahagian**, anda boleh melihat semua bahagian yang anda simpan dan mengurusnya.</span><span class="sxs-lookup"><span data-stu-id="b0aec-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="b0aec-146">Setiap segmen diwakili oleh baris yang menyertakan maklumat tambahan tentang segmen.</span><span class="sxs-lookup"><span data-stu-id="b0aec-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="b0aec-147">Anda boleh menyusun segmen dalam lajur dengan memilih tajuk lajur.</span><span class="sxs-lookup"><span data-stu-id="b0aec-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="b0aec-148">Gunakan kotak **Cari** di sudut kanan atas untuk menapis segmen.</span><span class="sxs-lookup"><span data-stu-id="b0aec-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b0aec-149">![Pilihan untuk menguruskan segmen sedia ada](media/segments-selected-segment.png "Pilihan untuk menguruskan segmen sedia ada")</span><span class="sxs-lookup"><span data-stu-id="b0aec-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="b0aec-150">Tindakan yang berikut tersedia apabila anda memilih segmen:</span><span class="sxs-lookup"><span data-stu-id="b0aec-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="b0aec-151">**Lihat** butiran segmen, termasuk trend kiraan ahli pratonton ahli segmen.</span><span class="sxs-lookup"><span data-stu-id="b0aec-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="b0aec-152">**Edit** segmen untuk mengubah sifatnya.</span><span class="sxs-lookup"><span data-stu-id="b0aec-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="b0aec-153">**Segar semula** segmen untuk memasukkan data terkini.</span><span class="sxs-lookup"><span data-stu-id="b0aec-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="b0aec-154">**Aktifkan** atau **Nyahaktifkan** segmen.</span><span class="sxs-lookup"><span data-stu-id="b0aec-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="b0aec-155">Segmen mempunyai dua keadaan yang mungkin - aktif atau tidak aktif.</span><span class="sxs-lookup"><span data-stu-id="b0aec-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="b0aec-156">Keadaan ini berguna apabila mengedit segmen.</span><span class="sxs-lookup"><span data-stu-id="b0aec-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="b0aec-157">Untuk segmen tidak aktif, takrifan segmen wujud tetapi ia tidak mengandungi sebarang pelanggan lagi.</span><span class="sxs-lookup"><span data-stu-id="b0aec-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="b0aec-158">Apabila anda mengaktifkan segmen, keadaannya berubah daripada 'tidak aktif' kepada 'aktif" dan ia mula mencari pelanggan yang sepadan dengan takrifan segmen.</span><span class="sxs-lookup"><span data-stu-id="b0aec-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="b0aec-159">Jika [segar semula berjadual](system.md#schedule-tab) dikonfigurasikan, segmen yang tidak aktif mempunyai **Status** yang disenaraikan sebagai **Dilangkau**, menunjukkan bahawa segar semula tidak pernah dicuba.</span><span class="sxs-lookup"><span data-stu-id="b0aec-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="b0aec-160">Apabila segmen yang tidak aktif diaktifkan, ia akan menyegar semula dan akan disertakan dalam segar semula berjadual.</span><span class="sxs-lookup"><span data-stu-id="b0aec-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="b0aec-161">Secara alternatif, anda boleh menggunakan kefungsian **Jadual kemudian** dalam juntai bawah **Aktifkan/Nyahaktifkan** untuk menetapkan tarikh dan masa pada masa depan untuk pengaktifan dan penyahaktifan segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="b0aec-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="b0aec-162">**Nama semula** segmen.</span><span class="sxs-lookup"><span data-stu-id="b0aec-162">**Rename** the segment.</span></span>
- <span data-ttu-id="b0aec-163">**Muat turun** senarai ahli sebagai fail .CSV.</span><span class="sxs-lookup"><span data-stu-id="b0aec-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="b0aec-164">Pilihan **Tambahkan pada** menghantar senarai ID Pelanggan dalam segmen untuk pemprosesan dalam aplikasi lain.</span><span class="sxs-lookup"><span data-stu-id="b0aec-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="b0aec-165">**Padamkan** segmen.</span><span class="sxs-lookup"><span data-stu-id="b0aec-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="b0aec-166">Segar semula segmen</span><span class="sxs-lookup"><span data-stu-id="b0aec-166">Refresh segments</span></span>

<span data-ttu-id="b0aec-167">Anda boleh memuatkan semula semua segmen serentak dengan memilih **Muat semula semua** pada halaman **Segmen** atau anda boleh memuatkan semula satu atau berbilang segmen apabila anda memilihnya dan memilih **Muat semula** daripada pilihan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="b0aec-168">Sebagai alternatif, anda boleh mengkonfigurasi segar semula pada **Pentadbir** > **Sistem** > **Jadual**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="b0aec-169">Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="b0aec-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b0aec-170">Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b0aec-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b0aec-171">Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja.</span><span class="sxs-lookup"><span data-stu-id="b0aec-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b0aec-172">Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="b0aec-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="b0aec-173">Muat turun dan mengeksport segmen</span><span class="sxs-lookup"><span data-stu-id="b0aec-173">Download and export segments</span></span>

<span data-ttu-id="b0aec-174">Anda boleh memuat turun segmen anda ke fail CSV atau eksportnya ke Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b0aec-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="b0aec-175">Muat turun segmen ke fail CSV</span><span class="sxs-lookup"><span data-stu-id="b0aec-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="b0aec-176">Dalam cerapan khalayak, pergi ke halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="b0aec-177">Pilih elipsis dalam jubin segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="b0aec-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="b0aec-178">Pilih **Muat Turun sebagai CSV** daripada tindakan senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="b0aec-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="b0aec-179">Eksport segmen ke Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="b0aec-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="b0aec-180">Sebelum mengeksport segmen ke Dynamics 365 Sales, pentadbir perlu [mencipta destinasi eksport](export-destinations.md) untuk Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b0aec-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="b0aec-181">Dalam cerapan khalayak, pergi ke halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="b0aec-182">Pilih elipsis dalam jubin segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="b0aec-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="b0aec-183">Pilih **Tambah** daripada tindakan senarai juntai bawah dan pilih destinasi eksport yang anda mahu hantarkan data.</span><span class="sxs-lookup"><span data-stu-id="b0aec-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="b0aec-184">Mod draf untuk bahagian</span><span class="sxs-lookup"><span data-stu-id="b0aec-184">Draft mode for segments</span></span>

<span data-ttu-id="b0aec-185">Jika tidak semua keperluan untuk bahagian diproses dipenuhi, anda boleh menyimpan bahagian sebagai draf dan mengaksesnya daripada halaman **Bahagian**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="b0aec-186">Ia akan disimpan sebagai segmen tidak aktif dan tidak boleh diaktifkan sehingga ia sah.</span><span class="sxs-lookup"><span data-stu-id="b0aec-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="b0aec-187">Menambah lebih banyak syarat ke kumpulan</span><span class="sxs-lookup"><span data-stu-id="b0aec-187">Add more conditions to a group</span></span>

<span data-ttu-id="b0aec-188">Untuk menambahkan lebih banyak syarat ke kumpulan, anda boleh menggunakan dua operator logik:</span><span class="sxs-lookup"><span data-stu-id="b0aec-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="b0aec-189">Operator **DAN**: Kedua-dua syarat mesti dipenuhi sebagai sebahagian proses pembahagian.</span><span class="sxs-lookup"><span data-stu-id="b0aec-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="b0aec-190">Pilihan ini adalah paling berguna apabila anda menakrif syarat dalam entiti yang berbeza.</span><span class="sxs-lookup"><span data-stu-id="b0aec-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="b0aec-191">Operator **ATAU**: Salah satu syarat perlu dipenuhi sebagai sebahagian daripada proses pembahagian.</span><span class="sxs-lookup"><span data-stu-id="b0aec-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="b0aec-192">Pilihan ini paling berguna apabila anda menakrif berbilang syarat untuk entiti yang sama.</span><span class="sxs-lookup"><span data-stu-id="b0aec-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b0aec-193">![Operator ATAU di mana salah satu syarat perlu dipenuhi](media/segmentation-either-condition.png "Operator ATAU di mana salah satu syarat perlu dipenuhi")</span><span class="sxs-lookup"><span data-stu-id="b0aec-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="b0aec-194">Pada masa ini berkemungkinan untuk menyarang operator **ATAU** di bawah operator **DAN**, tetapi tidak sebaliknya.</span><span class="sxs-lookup"><span data-stu-id="b0aec-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="b0aec-195">Menggabungkan berbilang kumpulan</span><span class="sxs-lookup"><span data-stu-id="b0aec-195">Combine multiple groups</span></span>

<span data-ttu-id="b0aec-196">Setiap kumpulan menghasilkan set pelanggan khusus.</span><span class="sxs-lookup"><span data-stu-id="b0aec-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="b0aec-197">Anda boleh menggabungkan kumpulan ini untuk memasukkan pelanggan yang diperlukan untuk kes perniagaan anda.</span><span class="sxs-lookup"><span data-stu-id="b0aec-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="b0aec-198">Dalam cerapan khalayak, pergi ke halaman **Segmen** dan pilih satu segmen.</span><span class="sxs-lookup"><span data-stu-id="b0aec-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="b0aec-199">Pilih **Tambah Kumpulan**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b0aec-200">![Kumpulan pelanggan tambah kumpulan](media/customer-group-add-group.png "Kumpulan pelanggan tambah kumpulan")</span><span class="sxs-lookup"><span data-stu-id="b0aec-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="b0aec-201">Pilih salah satu pengendali set berikut: **Kesatuan**, **Silang** atau **Kecuali**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b0aec-202">![Kumpulan pelanggan tambah kesatuan](media/customer-group-union.png "Kumpulan pelanggan tambah kesatuan")</span><span class="sxs-lookup"><span data-stu-id="b0aec-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="b0aec-203">Pilih operasi set untuk mentakrifkan kumpulan baharu.</span><span class="sxs-lookup"><span data-stu-id="b0aec-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="b0aec-204">Simpan kumpulan yang berbeza untuk menentukan data yang dapat dikekalkan:</span><span class="sxs-lookup"><span data-stu-id="b0aec-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="b0aec-205">**Kesatuan** menyatukan dua kumpulan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="b0aec-206">**Bersilang** dua kumpulan bertindih.</span><span class="sxs-lookup"><span data-stu-id="b0aec-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="b0aec-207">Hanya data yang *umum* pada kedua-dua kumpulan dikekalkan dalam kumpulan disatukan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="b0aec-208">**Kecuali** menggabungkan dua kumpulan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-208">**Except** combines the two groups.</span></span> <span data-ttu-id="b0aec-209">Hanya data dalam kumpulan A yang *tidak umum* pada data dalam kumpulan B dikekalkan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="b0aec-210">Lihat sejarah pemprosesan dan ahli bahagian</span><span class="sxs-lookup"><span data-stu-id="b0aec-210">View processing history and segment members</span></span>

<span data-ttu-id="b0aec-211">anda boleh melihat penyatuan data tentang bahagian dengan menyemak semula butirannya.</span><span class="sxs-lookup"><span data-stu-id="b0aec-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="b0aec-212">Pada halaman **Bahagian**, pilih bahagian yang anda mahu semak semula.</span><span class="sxs-lookup"><span data-stu-id="b0aec-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="b0aec-213">Bahagian atas halaman termasuk graf trend yang menggambarkan perubahan dalam kiraan ahli.</span><span class="sxs-lookup"><span data-stu-id="b0aec-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="b0aec-214">Tuding pada titik data untuk melihat kiraan ahli pada tarikh tertentu.</span><span class="sxs-lookup"><span data-stu-id="b0aec-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="b0aec-215">Anda boleh mengemas kini tempoh masa bagi visualisasi.</span><span class="sxs-lookup"><span data-stu-id="b0aec-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b0aec-216">![Julat masa bahagian](media/segment-time-range.png "Julat masa bahagian")</span><span class="sxs-lookup"><span data-stu-id="b0aec-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="b0aec-217">Bahagian bawah mengandungi senarai ahli bahagian.</span><span class="sxs-lookup"><span data-stu-id="b0aec-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="b0aec-218">Medan yang muncul dalam senarai adalah berasaskan pada atribut bagi entiti segmen anda.</span><span class="sxs-lookup"><span data-stu-id="b0aec-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="b0aec-219">Senarai ialah pratonton bagi pemadanan ahli bahagian dan menunjukkan 100 rekod pertama bahagian anda supaya anda boleh segera menilainya dan menyemak semula definisinya jika perlu.</span><span class="sxs-lookup"><span data-stu-id="b0aec-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="b0aec-220">Untuk melihat semua rekod yang sepadan, anda perlu [mengeksport bahagian](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b0aec-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="b0aec-221">Segmen pantas</span><span class="sxs-lookup"><span data-stu-id="b0aec-221">Quick segments</span></span>

<span data-ttu-id="b0aec-222">Sebagai tambahan kepada pembina segmen, terdapat satu lagi laluan untuk mencipta segmen.</span><span class="sxs-lookup"><span data-stu-id="b0aec-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="b0aec-223">Segmen pantas membolehkan anda membina segmen ringkas dengan operator tunggal dengan cepat dan dengan cerapan segera.</span><span class="sxs-lookup"><span data-stu-id="b0aec-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="b0aec-224">Pada halaman **Segmen**, pilih **Baharu** > **Cipta dengan cepat daripada**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="b0aec-225">Pilih pilihan **Profil** untuk membina bahagian yang berasaskan pada entiti Pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="b0aec-226">Pilih pilihan **Ukuran** untuk membina segment dalam setiap jenis ukuran atribut pelanggan yang telah anda cipta sebelum ini pada halaman **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="b0aec-227">Pilih pilihan **Kecerdasan** untuk membina segmen di sekitar salah satu entiti output yang dijana anda menggunakan sama ada keupayaan **Ramalan** atau **Model Tersuai**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="b0aec-228">Dalam kotak dialog **Segmen pantas baharu**, pilih atribut daripada **Medan** juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="b0aec-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="b0aec-229">Sistem akan memberikan wawasan tambahan yang membantu anda mencipta bahagian yang lebih baik untuk pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="b0aec-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="b0aec-230">Untuk medan kategori, kami akan menunjukkan 10 kiraan pelanggan teratas.</span><span class="sxs-lookup"><span data-stu-id="b0aec-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="b0aec-231">Pilih **Nilai** dan pilih **Semak Semula**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="b0aec-232">Untuk atribut numerik, sistem akan menunjukkan apakah nilai atribut yang jatuh dalam setiap persentil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="b0aec-233">Pilih **Operator** dan **Nilai**, kemudian pilih **Semak Semula**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="b0aec-234">Sistem akan memberikan anda **saiz bahagian yang dianggarkan**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="b0aec-235">Anda boleh memilih sama ada untuk menjana bahagian yang anda takrif, atau kunjungi semula terlebih dahulu untuk mendapatkan saiz bahagian yang berbeza.</span><span class="sxs-lookup"><span data-stu-id="b0aec-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b0aec-236">![Nama dan anggaran bagi bahagian pantas](media/quick-segment-name.png "Nama dan anggaran bagi bahagian pantas")</span><span class="sxs-lookup"><span data-stu-id="b0aec-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="b0aec-237">Berikan **Nama** untuk bahagian anda.</span><span class="sxs-lookup"><span data-stu-id="b0aec-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="b0aec-238">Secara pilihan, berikan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="b0aec-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="b0aec-239">Pilih **Simpan** untuk mencipta bahagian.</span><span class="sxs-lookup"><span data-stu-id="b0aec-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="b0aec-240">Selepas bahagian selesai diproses, anda boleh melihatnya seperti bahagian lain yang anda cipta.</span><span class="sxs-lookup"><span data-stu-id="b0aec-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="b0aec-241">Untuk senario berikut, kami menyarankan penggunaan pembina bahagian berbanding keupayaan bahagian yang disyorkan:</span><span class="sxs-lookup"><span data-stu-id="b0aec-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="b0aec-242">Mencipta bahagian dengan penapis pada medan kategori di mana operator berbeza daripada operator **Is**</span><span class="sxs-lookup"><span data-stu-id="b0aec-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="b0aec-243">Mencipta bahagian dengan penapis pada medan numerik di mana operator berbeza daripada operator **Antara**, **Lebih daripada**, dan **Kurang daripada**</span><span class="sxs-lookup"><span data-stu-id="b0aec-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="b0aec-244">Cipta segmen dengan penapis pada medan jenis tarikh</span><span class="sxs-lookup"><span data-stu-id="b0aec-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="b0aec-245">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="b0aec-245">Next steps</span></span>

<span data-ttu-id="b0aec-246">[Eksport bahagian](export-destinations.md) dan teroka [Kad Pelanggan](customer-card-add-in.md) dan [Penyambung](export-power-bi.md) untuk mendapatkan wawasan pada peringkat pelanggan.</span><span class="sxs-lookup"><span data-stu-id="b0aec-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
