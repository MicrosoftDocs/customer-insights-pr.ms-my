---
title: Segmen yang dicadangkan berdasarkan pada aktiviti.
description: Biarkan pembelajaran mesin membantu anda mencari segmen baharu dan segmen yang menarik berdasarkan aktiviti pelanggan.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034097"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="a2536-103">Segmen yang dicadangkan berdasarkan pada aktiviti (pratonton)</span><span class="sxs-lookup"><span data-stu-id="a2536-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="a2536-104">Terokai segmen yang menarik bagi pelanggan anda berdasarkan pada data aktiviti pelanggan yang diinges ke Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a2536-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="a2536-105">Contoh data aktiviti ialah transaksi, tempoh panggilan sokongan, pembelian atau pulangan.</span><span class="sxs-lookup"><span data-stu-id="a2536-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="a2536-106">Untuk mencadangkan segmen, data aktiviti akan dianalisis untuk keterkinian, kekerapan dan nilai kewangan (atau tempoh).</span><span class="sxs-lookup"><span data-stu-id="a2536-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="a2536-107">Sebagai alternatif, anda boleh menjana [segmen yang dicadangkan untuk meningkatkan ukuran atau pemahaman yang lebih baik tentang perkara yang mempengaruhi atribut](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="a2536-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Tab segmen yang dicadangkan menunjukkan cadangan segmen untuk segmen berasaskan aktiviti dan berasaskan atribut.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="a2536-109">Kategorikan pelanggan mengikut aktiviti</span><span class="sxs-lookup"><span data-stu-id="a2536-109">Categorize customers by activity</span></span>

<span data-ttu-id="a2536-110">Dengan [data aktiviti](activities.md) tersedia dalam Customer Insights, kami boleh menjana cadangan yang mewakili kumpulan pelanggan:</span><span class="sxs-lookup"><span data-stu-id="a2536-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="a2536-111">pelanggan yang paling aktif</span><span class="sxs-lookup"><span data-stu-id="a2536-111">most active customers</span></span> 
- <span data-ttu-id="a2536-112">pelanggan yang telah membuat pembelian paling banyak</span><span class="sxs-lookup"><span data-stu-id="a2536-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="a2536-113">pelanggan yang menjana hasil paling banyak</span><span class="sxs-lookup"><span data-stu-id="a2536-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="a2536-114">pelanggan yang belum aktif sejak kebelakangan ini</span><span class="sxs-lookup"><span data-stu-id="a2536-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="a2536-115">pelanggan yang kerap berinteraksi dengan perniagaan anda</span><span class="sxs-lookup"><span data-stu-id="a2536-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="a2536-116">Jika anda mempunyai perniagaan runcit, anda boleh mengetahui pelanggan yang menjana hasil dan ganjaran mereka paling banyak dengan kupon.</span><span class="sxs-lookup"><span data-stu-id="a2536-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="a2536-117">Atau anda boleh mengenal pasti pelanggan sekali-sekala dan menawarkan mereka menyertai program ganjaran supaya mereka melawat perniagaan anda dengan lebih kerap.</span><span class="sxs-lookup"><span data-stu-id="a2536-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="a2536-118">Jika anda dalam perniagaan penjagaan kesihatan yang menyediakan penjagaan kesihatan awam dan matlamat anda ialah untuk meminimumkan perbelanjaan bagi pesakit individu.</span><span class="sxs-lookup"><span data-stu-id="a2536-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="a2536-119">Satu cara untuk berbuat demikian berkemungkinan dengan mengurangkan lawatan berulang yang menyediakan penjagaan terbaik sebaik mungkin dalam kunjungan sekurang mungkin.</span><span class="sxs-lookup"><span data-stu-id="a2536-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="a2536-120">Dalam kes ini, matlamat anda ialah untuk memastikan kekerapan lawatan rendah dan meminimumkan kos berulang untuk pesakit.</span><span class="sxs-lookup"><span data-stu-id="a2536-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="a2536-121">Atau anda boleh mengenal pasti segmen pesakit yang mempunyai janji temu yang kerap dan kos berulang yang tinggi dan menganalisis kes ini untuk meningkatkan rawatan individu.</span><span class="sxs-lookup"><span data-stu-id="a2536-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="a2536-122">Data diperlukan</span><span class="sxs-lookup"><span data-stu-id="a2536-122">Required data</span></span>

<span data-ttu-id="a2536-123">Cadangan dijana berdasarkan pada data input yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="a2536-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="a2536-124">Profil pelanggan: Semua pelanggan atau ahli segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="a2536-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="a2536-125">Tempoh masa: Bulan lepas, tahun lepas atau sebarang tempoh masa tersuai.</span><span class="sxs-lookup"><span data-stu-id="a2536-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="a2536-126">Jenis aktiviti: pembelian, transaksi runcit, transaksi dalam talian, kes sokongan pelanggan, langganan dan sebagainya.</span><span class="sxs-lookup"><span data-stu-id="a2536-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="a2536-127">Entiti dalam Customer Insights yang mengandungi data aktiviti: Entiti UnifiedActivity atau entiti untuk aktiviti tertentu.</span><span class="sxs-lookup"><span data-stu-id="a2536-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="a2536-128">Dimensi untuk dimasukkan: Keterkinian, kekerapan atau dimensi kewangan bergantung pada keperluan perniagaan anda.</span><span class="sxs-lookup"><span data-stu-id="a2536-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="a2536-129">Menjana segmen yang dicadangkan</span><span class="sxs-lookup"><span data-stu-id="a2536-129">Generate suggested segments</span></span>

1. <span data-ttu-id="a2536-130">Pergi ke **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="a2536-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="a2536-131">Pilih tab **Cadangan (pratonton)**.</span><span class="sxs-lookup"><span data-stu-id="a2536-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="a2536-132">Pilih **Cari cadangan baharu** dan pilih **Lihat atau jangkakan tingkah laku pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="a2536-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="a2536-133">Pilih **Mula** untuk menjalankan pengalaman berpandu.</span><span class="sxs-lookup"><span data-stu-id="a2536-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Langkah pertama bagi wizard konfigurasi untuk segmen yang dicadangkan berdasarkan pada aktiviti.":::

1. <span data-ttu-id="a2536-135">Sediakan data input yang diperlukan dan pilih **Seterusnya** teruskan.</span><span class="sxs-lookup"><span data-stu-id="a2536-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="a2536-136">Pilih pelanggan: termasuk semua pelanggan atau segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="a2536-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="a2536-137">Pilih aktiviti: Pilih jenis aktiviti dan entiti yang menerangkan aktiviti.</span><span class="sxs-lookup"><span data-stu-id="a2536-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="a2536-138">Keutamaan: Tetapkan tempoh masa untuk mempertimbangkan faktor bagi cadangan dan petakan atribut.</span><span class="sxs-lookup"><span data-stu-id="a2536-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="a2536-139">Semak input anda dan pilih **Jalankan** untuk menjalankan model dan menjana cadangan.</span><span class="sxs-lookup"><span data-stu-id="a2536-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="a2536-140">Bergantung pada bilangan profil pelanggan dan aktiviti yang dipilih, ini boleh mengambil masa beberapa minit untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="a2536-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="a2536-141">Selepas menjana cadangan, anda boleh menapis dengan mengikut dimensi atau nilai yang paling menarik minat anda.</span><span class="sxs-lookup"><span data-stu-id="a2536-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="a2536-142">Lihat butiran segmen yang dicadangkan</span><span class="sxs-lookup"><span data-stu-id="a2536-142">View details of a suggested segment</span></span>

<span data-ttu-id="a2536-143">Sebaik sahaja cadangan dijana, anda akan dapati cadangan disenaraikan pada **Segmen** > **Cadangan (pratonton)** dalam bahagian **Cadangan berasaskan aktiviti**.</span><span class="sxs-lookup"><span data-stu-id="a2536-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Anak tetingkap sisi yang dikembangkan menunjukkan data terperinci segmen yang dicadangkan.":::

<span data-ttu-id="a2536-145">Pilih **Lihat cadangan** pada segmen yang dicadangkan untuk melihat butiran segmen itu.</span><span class="sxs-lookup"><span data-stu-id="a2536-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="a2536-146">Anak tetingkap sisi memberikan butiran seperti had setiap dimensi dalam perbandingan ke kumpulan sasaran.</span><span class="sxs-lookup"><span data-stu-id="a2536-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="a2536-147">Ia juga menyerlahkan bilangan ahli yang berpotensi dalam segmen dan peratusan yang bersamaan dengan jumlah pelanggan.</span><span class="sxs-lookup"><span data-stu-id="a2536-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="a2536-148">Jika anda mahu menyimpan cadangan sebagai segmen, pilih **Cipta segmen**.</span><span class="sxs-lookup"><span data-stu-id="a2536-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="a2536-149">Simpan cadangan sebagai segmen</span><span class="sxs-lookup"><span data-stu-id="a2536-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="a2536-150">Pergi ke **Segmen** > **Cadangan (pratonton)**.</span><span class="sxs-lookup"><span data-stu-id="a2536-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="a2536-151">Pilih segmen yang anda mahu simpan.</span><span class="sxs-lookup"><span data-stu-id="a2536-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="a2536-152">Dalam anak tetingkap sisi, pilih **Cipta segmen**.</span><span class="sxs-lookup"><span data-stu-id="a2536-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="a2536-153">Selepas menyimpan segmen itu, ia akan ditunjukkan dalam senarai segmen pada tab **Semua segmen**. Ia kini boleh [disegar semula atau dipadam seperti segmen lain](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a2536-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="a2536-154">Anda tidak boleh mengedit butiran segmen.</span><span class="sxs-lookup"><span data-stu-id="a2536-154">You can't edit the segment details.</span></span> <span data-ttu-id="a2536-155">Walau bagaimanapun, anda boleh mengubah kriteria input untuk cadangan dan menjana cadangan yang berbeza.</span><span class="sxs-lookup"><span data-stu-id="a2536-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="a2536-156">Muatkan semula atau edit set cadangan</span><span class="sxs-lookup"><span data-stu-id="a2536-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="a2536-157">Pergi ke **Segmen** > **Cadangan (pratonton)** dan cari segmen dalam bahagian **Cadangan berasaskan aktiviti**.</span><span class="sxs-lookup"><span data-stu-id="a2536-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="a2536-158">Pilih **Segar semula cadangan** untuk segar semula cadangan sambil menyimpan atribut yang dikonfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="a2536-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="a2536-159">Atau pilih **Edit cadangan** untuk mengubah suai atribut yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="a2536-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="a2536-160">Sistem akan menjalankan semula proses, menjana cadangan segmen berdasarkan data terkini dan menggantikan cadangan semasa.</span><span class="sxs-lookup"><span data-stu-id="a2536-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
