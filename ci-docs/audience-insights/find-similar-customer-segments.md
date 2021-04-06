---
title: Cari pelanggan sama dengan AI
description: Cari segmen pelanggan yang serupa dengan kepintaran buatan.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596786"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="8dfdf-103">Pelanggan yang serupa (pratonton)</span><span class="sxs-lookup"><span data-stu-id="8dfdf-103">Similar Customers (preview)</span></span>

<span data-ttu-id="8dfdf-104">Ciri ini membenarkan anda mencari pelanggan yang serupa dalam asas pelanggan menggunakan kepintaran buatan.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="8dfdf-105">Anda perlu mempunyai sekurang-kurangnya satu segmen dicipta untuk menggunakan ciri ini.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="8dfdf-106">Mengembangkan kriteria segmen sedia ada membantu mencari pelanggan yang serupa kepada segmen itu.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="8dfdf-107">*Cari pelanggan yang serupa* menggunakan tujuan automatik untuk menilai data dan membuat ramalan berasaskan pada data itu dan dengan itu mempunyai keupayaan untuk digunakan sebagai kaedah profiling seperti istilah yang ditakrifkan oleh Peraturan Perlindungan Data Umum (“GDPR”).</span><span class="sxs-lookup"><span data-stu-id="8dfdf-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="8dfdf-108">Pelanggan menggunakan ciri ini untuk memproses data berkemungkinan tertakluk pada GDPR atau undang-undang atau peraturan yang lain.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="8dfdf-109">Anda bertanggungjawab untuk memastikan bahawa penggunaan Dynamics 365 Customer Insights anda, termasuk ramalan, mematuhi semua undang-undang dan peraturan yang berkaitan, termasuk undang-undang yang berkaitan dengan privasi, data peribadi, data biometrik, perlindungan data dan kerahsiaan komunikasi.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="8dfdf-110">Mencari pelanggan yang serupa</span><span class="sxs-lookup"><span data-stu-id="8dfdf-110">Finding similar customers</span></span>

1. <span data-ttu-id="8dfdf-111">Dalam Insights khalayak, pergi ke **Segmen** dan pilih segmen yang anda mahu jadikan asas segmen baharu anda.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="8dfdf-112">Itu adalah *segmen sumber* anda.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="8dfdf-113">Dalam bar tindakan, pilih **Cari pelanggan yang serupa**.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="8dfdf-114">Semak nama yang dicadangkan untuk segmen baharu anda dan ubahkannya jika perlu.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="8dfdf-115">Semak medan yang menakrifkan segmen baharu anda.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="8dfdf-116">Medan ini menakrifkan asas pada sistem yang akan cuba mencari pelanggan yang serupa ke segmen sumber anda.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="8dfdf-117">Sistem akan memilih medan yang disyorkan secara lalai.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="8dfdf-118">Medan yang boleh mengurangkan prestasi model dengan ketara dikecualikan secara automatik:</span><span class="sxs-lookup"><span data-stu-id="8dfdf-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="8dfdf-119">Medan dengan jenis data berikut: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="8dfdf-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="8dfdf-120">Medan dengan kekardinalan (bilangan elemen dalam medan) kurang daripada 2 atau lebih daripada 30</span><span class="sxs-lookup"><span data-stu-id="8dfdf-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="8dfdf-121">Pilih jika anda mahu memasukkan **Semua pelanggan** atau hanya pelanggan dalam **Segmen sedia ada tertentu** dalam segmen baharu anda.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="8dfdf-122">Kecualikan pelanggan dalam segmen sumber anda dengan memilih kotak semak **Kecualikan semua dalam segmen sumber**.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="8dfdf-123">Sistem mencadangkan masukkan hanya 20% saiz khalayak sasaran dalam output anda.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="8dfdf-124">Edit ambang bila diperlukan.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-124">Edit this threshold as needed.</span></span> <span data-ttu-id="8dfdf-125">Meningkatkan ambang akan mengurangkan ketepatan.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="8dfdf-126">Pilih **Jalankan** pada bahagian bawah halaman untuk memulakan tugas pengelasan perduaan (kaedah pembelajaran mesin) yang menganalisis set data.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="8dfdf-127">Lihat segmen yang serupa</span><span class="sxs-lookup"><span data-stu-id="8dfdf-127">View the similar segment</span></span>

<span data-ttu-id="8dfdf-128">Selepas memproses segmen yang serupa, anda akan menemui segmen baharu disenaraikan pada halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8dfdf-129">![Segmen pelanggan yang serupa](media/expanded-segment.png "Segmen pelanggan yang serupa")</span><span class="sxs-lookup"><span data-stu-id="8dfdf-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="8dfdf-130">Pilih **Pandangan** dalam bar tindakan untuk membuka butiran segmen.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="8dfdf-131">Pandangan ini mengandungi maklumat tentang pengedaran merentas [skor persamaan](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="8dfdf-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="8dfdf-132">Anda juga menemui nilai skor persamaan dalam **Pratonton ahli segment**.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="8dfdf-133">Gunakan output segmen yang serupa</span><span class="sxs-lookup"><span data-stu-id="8dfdf-133">Use the output of a similar segment</span></span>

<span data-ttu-id="8dfdf-134">Anda boleh [bekerja dengan output segmen yang serupa](segments.md) seperti yang anda lakukan dengan segmen lain.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="8dfdf-135">Contohnya, eksport segmen atau bina ukuran.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="8dfdf-136">Segar semula dan edit segmen yang serupa</span><span class="sxs-lookup"><span data-stu-id="8dfdf-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="8dfdf-137">Untuk menyegar semula segmen yang serupa, pilihnya pada halaman **Segmen** dan pilih **Segar semula** dalam bar tindakan.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="8dfdf-138">Mengedit segmen yang serupa akan memproses semula data anda.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="8dfdf-139">Segmen yang dicipta terdahulu dikemas kini dengan data yang disegar semula.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="8dfdf-140">Untuk mengedit segmen yang serupa, pilihnya pada halaman **Segmen** dan pilih **Edit** dalam bar tindakan.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="8dfdf-141">Gunakan perubahan anda dan pilih **Jalankan** untuk memulakan pemprosesan.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="8dfdf-142">Padam segmen yang serupa</span><span class="sxs-lookup"><span data-stu-id="8dfdf-142">Delete a similar segment</span></span>

<span data-ttu-id="8dfdf-143">Pilih segmen pada halaman **Segmen** dan pilih **Padam** dalam bar tindakan.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="8dfdf-144">Kemudian sahkan pemadaman anda.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="8dfdf-145">Tentang skor persamaan</span><span class="sxs-lookup"><span data-stu-id="8dfdf-145">About similarity scores</span></span>

<span data-ttu-id="8dfdf-146">Model pembelajaran mesin pengelasan perduaan memperuntukkan skor kepada pelanggan dalam segmen yang serupa.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="8dfdf-147">Skor berasaskan pada persamaan kepada pelanggan dalam segmen sumber.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="8dfdf-148">Skor persamaan di bawah 0.55 adalah pelanggan yang diklasifikasikan oleh sistem sebagai *tidak serupa* kepada pelanggan dalam segmen sumber</span><span class="sxs-lookup"><span data-stu-id="8dfdf-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="8dfdf-149">Skor persamaan antara 0.55 – 0.7 diklasifikasikan sebagai *agak serupa*</span><span class="sxs-lookup"><span data-stu-id="8dfdf-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="8dfdf-150">Skor persamaan antara 0.7 – 0.85 diklasifikasikan sebagai *serupa*</span><span class="sxs-lookup"><span data-stu-id="8dfdf-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="8dfdf-151">Skor persamaan antara 0.85 – 1 adalah pelanggan yang diklasifikasikan oleh sistem sebagai *sangat serupa*</span><span class="sxs-lookup"><span data-stu-id="8dfdf-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="8dfdf-152">Pelanggan dengan skor persamaan di bawah 0.4 tidak termasuk dalam output model.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="8dfdf-153">Sistem tidak mempertimbangkannya sebagai tidak cukup serupa kepada segmen sumber.</span><span class="sxs-lookup"><span data-stu-id="8dfdf-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]