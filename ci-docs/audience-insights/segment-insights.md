---
title: Cerapan segmen untuk segmen sedia ada
description: Dapatkan cerapan pada segmen sedia ada untuk melihat perbezaan dan persamaan.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: d731d21462b5a31aba0653f87e299d98373bbf49
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270031"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="9a956-103">Wawasan segmen (pratonton)</span><span class="sxs-lookup"><span data-stu-id="9a956-103">Segment insights (preview)</span></span>

<span data-ttu-id="9a956-104">Temui maklumat dan wawasan tambahan sekitar segmen sedia ada anda.</span><span class="sxs-lookup"><span data-stu-id="9a956-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="9a956-105">Ketahui apa yang membezakan dua segmen atau apa persamaan mereka.</span><span class="sxs-lookup"><span data-stu-id="9a956-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="9a956-106">Bertindih bahagian</span><span class="sxs-lookup"><span data-stu-id="9a956-106">Segment overlap</span></span>

<span data-ttu-id="9a956-107">Analisa bertindih segmen menunjukkan bilangan dan pelanggan mana yang biasa dengan dua atau lebih segmen.</span><span class="sxs-lookup"><span data-stu-id="9a956-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="9a956-108">Contohnya, cara segmen pelanggan yang kerap bertindih dengan segmen yang mengandungi pelanggan yang berpuas hati dengan perkhidmatan atau produk anda.</span><span class="sxs-lookup"><span data-stu-id="9a956-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="9a956-109">Anda juga boleh menganalisis cara perubahan bertindih untuk atribut tertentu.</span><span class="sxs-lookup"><span data-stu-id="9a956-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="9a956-110">Jalankan analisis bertindih</span><span class="sxs-lookup"><span data-stu-id="9a956-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="9a956-111">Pergi ke **Segmen** dan pilih tab **wawasan (pratonton)**.</span><span class="sxs-lookup"><span data-stu-id="9a956-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="9a956-112">Pilih **Baharu** dan pilih pilihan **Bertindih** dalam anak tetingkap **Pilih Jenis Wawasan**.</span><span class="sxs-lookup"><span data-stu-id="9a956-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="9a956-113">Pilih segmen kepentingan dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="9a956-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="9a956-114">Secara alternatif, pilih satu atau lebih medan kepentingan untuk menganalisis pertindihan bagi setiap nilai medan yang mungkin dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="9a956-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="9a956-115">Berikan nama untuk anda analisis bertindih, nama paparan pilihan dan perihalan.</span><span class="sxs-lookup"><span data-stu-id="9a956-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="9a956-116">Pilih **Simpan** untuk memulakan analisis.</span><span class="sxs-lookup"><span data-stu-id="9a956-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="9a956-117">Analisis bertindih sudah bersedia apabila status berubah daripada Menyegar semula kepada Berjaya.</span><span class="sxs-lookup"><span data-stu-id="9a956-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="9a956-118">Pandangan dan optimumkan analisis bertindih</span><span class="sxs-lookup"><span data-stu-id="9a956-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="9a956-119">Selepas melengkapkan analisis, cari butiran mengenai wawasan ini dalam **Segmen** > **Wawasan (pratonton)**.</span><span class="sxs-lookup"><span data-stu-id="9a956-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Bahagikan butiran wawasan bertindih":::

<span data-ttu-id="9a956-121">Pilih wawasan untuk melihat hasil analisis:</span><span class="sxs-lookup"><span data-stu-id="9a956-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="9a956-122">Bilangan ahli bertindih segmen yang dipilih untuk analisis.</span><span class="sxs-lookup"><span data-stu-id="9a956-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="9a956-123">Bilangan ahli yang termasuk dalam salah satu segmen tetapi tidak berada dalam segmen yang lain.</span><span class="sxs-lookup"><span data-stu-id="9a956-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="9a956-124">Jika anda memilih medan semasa mengkonfigurasikan analisis bertindih, anda akan dapati mereka dalam tab yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="9a956-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="9a956-125">Anda boleh menggunakan juntai bawah penapis untuk memilih sebarang tahap atribut kepentingan dan jadual di bahagian bawah akan menunjukkan data yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="9a956-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="9a956-126">Pembezaan bahagian</span><span class="sxs-lookup"><span data-stu-id="9a956-126">Segment differentiators</span></span>

<span data-ttu-id="9a956-127">Pembezaan segmen membantu anda ketahui apa yang membezakan segmen daripada seluruh pelanggan anda atau daripada segmen lain.</span><span class="sxs-lookup"><span data-stu-id="9a956-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="9a956-128">Anda hanya perlu memilih segmen dan sistem akan mengenal pasti atribut dan langkah profil yang membezakan segmen yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="9a956-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="9a956-129">Jalankan analisis pembezaan</span><span class="sxs-lookup"><span data-stu-id="9a956-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="9a956-130">Pergi ke **Segmen** dan pilih tab **wawasan (pratonton)**.</span><span class="sxs-lookup"><span data-stu-id="9a956-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="9a956-131">Pilih **Baharu** dan pilih pilihan **Bertindih** dalam anak tetingkap **Pilih Jenis Wawasan**.</span><span class="sxs-lookup"><span data-stu-id="9a956-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="9a956-132">Pilih segmen yang anda mahu analisis sebagai **Segmen utama** dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="9a956-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="9a956-133">Pilih **Semua pelanggan** atau **Segmen kedua** untuk membandingkan dengan segmen utama anda dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="9a956-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="9a956-134">Secara alternatif, pilih satu atau lebih medan kepentingan untuk fokus analisis pada atribut tertentu dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="9a956-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="9a956-135">Berikan nama untuk anda analisis bertindih, nama paparan pilihan dan perihalan.</span><span class="sxs-lookup"><span data-stu-id="9a956-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="9a956-136">Pilih **Simpan** untuk memulakan analisis.</span><span class="sxs-lookup"><span data-stu-id="9a956-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="9a956-137">Analisis bertindih sudah bersedia apabila status berubah daripada Menyegar semula kepada Berjaya.</span><span class="sxs-lookup"><span data-stu-id="9a956-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="9a956-138">Pandangan dan optimumkan analisis pembezaan</span><span class="sxs-lookup"><span data-stu-id="9a956-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="9a956-139">Selepas melengkapkan analisis, cari butiran mengenai wawasan ini dalam **Segmen** > **Wawasan (pratonton)**.</span><span class="sxs-lookup"><span data-stu-id="9a956-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Butiran wawasan pembezaan segmen":::

<span data-ttu-id="9a956-141">Pilih wawasan untuk melihat hasil analisis.</span><span class="sxs-lookup"><span data-stu-id="9a956-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="9a956-142">Analisis pembezaan termasuk dua tab.</span><span class="sxs-lookup"><span data-stu-id="9a956-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="9a956-143">Tab **Atribut** menyenaraikan atribut profil dianggap sebagai pembezaan.</span><span class="sxs-lookup"><span data-stu-id="9a956-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="9a956-144">Tab **Langkah** menyenaraikan pembezaan.</span><span class="sxs-lookup"><span data-stu-id="9a956-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="9a956-145">Setiap tab merangkumi butiran berikut:</span><span class="sxs-lookup"><span data-stu-id="9a956-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="9a956-146">Kedudukan senarai pembezaan, diisih oleh skor perbezaan.</span><span class="sxs-lookup"><span data-stu-id="9a956-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="9a956-147">**Skor perbezaan** untuk setiap pembezaan.</span><span class="sxs-lookup"><span data-stu-id="9a956-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="9a956-148">Skor perbezaan mewakili darjah perbezaan atribut antara dua segmen.</span><span class="sxs-lookup"><span data-stu-id="9a956-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="9a956-149">Semakin tinggi skor perbezaan, lebih banyak atribut berbeza antara kedua-dua segmen.</span><span class="sxs-lookup"><span data-stu-id="9a956-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="9a956-150">Pilih skor untuk membuka anak tetingkap **Skor perbezaan** dengan pengagihan nilai untuk atribut tersebut.</span><span class="sxs-lookup"><span data-stu-id="9a956-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="9a956-151">Uruskan wawasan segmen</span><span class="sxs-lookup"><span data-stu-id="9a956-151">Manage segment insights</span></span>

<span data-ttu-id="9a956-152">Anda boleh menggunakan pilihan berikut pada wawasan anda daripada bar perintah:</span><span class="sxs-lookup"><span data-stu-id="9a956-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="9a956-153">**Kembali** untuk mengembalikan senarai wawasan</span><span class="sxs-lookup"><span data-stu-id="9a956-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="9a956-154">**Segar semula** untuk menjalankan analisis sekali lagi</span><span class="sxs-lookup"><span data-stu-id="9a956-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="9a956-155">**Padam** untuk alih keluar wawasan ini</span><span class="sxs-lookup"><span data-stu-id="9a956-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]