---
title: Lengkapkan data separa menggunakan ramalan
description: Gunakan ramalan untuk mengisi data pelanggan yang tidak lengkap.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 66f0b16b5d05741ab98ca5ce2157da8c46b6d9e0
ms.sourcegitcommit: 5379c2b77d613d071a177f509e6417ebf3c47516
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/26/2020
ms.locfileid: "4648722"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="85bc3-103">Lengkapkan data separa anda dengan ramalan</span><span class="sxs-lookup"><span data-stu-id="85bc3-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="85bc3-104">Ramalan membolehkan anda mencipta nilai ramalan dengan mudah yang boleh meningkatkan pemahaman anda tentang pelanggan.</span><span class="sxs-lookup"><span data-stu-id="85bc3-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="85bc3-105">Pada halaman **Kecerdasan** > **Ramalan**, anda boleh memilih **Ramalan saya** untuk melihat ramalan yang anda konfigurasikan dalam bahagian wawasan khalayak lain dan membolehkan anda menyesuaikannya lagi.</span><span class="sxs-lookup"><span data-stu-id="85bc3-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="85bc3-106">Anda tidak boleh menggunakan ciri ini jika persekitaran anda menggunakan storan Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="85bc3-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="85bc3-107">Ciri ramalan menggunakan alat automatik untuk menilai data dan membuat ramalan berasaskan pada data itu dan dengan itu mempunyai keupayaan yang boleh digunakan sebagai kaedah pemprofilan, kerana ia ditakrifkan oleh Peraturan Perlindungan Data Umum (“GDPR”).</span><span class="sxs-lookup"><span data-stu-id="85bc3-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="85bc3-108">Pelanggan menggunakan ciri ini untuk memproses data berkemungkinan tertakluk pada GDPR atau undang-undang atau peraturan yang lain.</span><span class="sxs-lookup"><span data-stu-id="85bc3-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="85bc3-109">Anda bertanggungjawab untuk memastikan bahawa penggunaan Dynamics 365 Customer Insights anda, termasuk ramalan, mematuhi semua undang-undang dan peraturan yang berkaitan, termasuk undang-undang yang berkaitan dengan privasi, data peribadi, data biometrik, perlindungan data dan kerahsiaan komunikasi.</span><span class="sxs-lookup"><span data-stu-id="85bc3-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85bc3-110">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="85bc3-110">Prerequisites</span></span>

<span data-ttu-id="85bc3-111">Sebelum organisasi anda boleh menggunakan ciri ramalan, prasyarat berikut mesti dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="85bc3-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="85bc3-112">Organisasi anda mempunyai tika yang [disediakan dalam Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) dan ia berada dalam organisasi yang sama dengan Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="85bc3-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="85bc3-113">Persekitaran anda dilampirkan pada tika Common Data Service anda.</span><span class="sxs-lookup"><span data-stu-id="85bc3-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="85bc3-114">Jika anda sedang [mencipta persekitaran baharu](manage-environments.md), konfigurasikannya dalam dialog **Cipta persekitaran** dan pilih **Lanjutan**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="85bc3-115">Jika anda telah mencipta persekitaran, pergi ke tetapannya dan pilih **Lanjutan**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="85bc3-116">Walau apa pun, dalam bahagian **Gunakan ramalan**, masukkan URL tika Common Data Service yang anda mahu lampirkan pada persekitaran anda.</span><span class="sxs-lookup"><span data-stu-id="85bc3-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="85bc3-117">Cipta ramalan dalam entiti Pelanggan</span><span class="sxs-lookup"><span data-stu-id="85bc3-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="85bc3-118">Dalam wawasan khalayak, pergi ke **Data** > **Entiti**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="85bc3-119">Pilih entiti **Pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="85bc3-120">Dalam **Entiti pelanggan: CustomerInsights**, pilih pada tab **Medan**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="85bc3-121">Cari nama atribut yang anda ingin ramalkan nilai, kemudian pilih ikon **Gambaran Keseluruhan** dalam lajur **Ringkasan**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="85bc3-122">![Ikon gambaran keseluruhan](media/intelligence-overviewicon.png "Ikon gambaran keseluruhan")</span><span class="sxs-lookup"><span data-stu-id="85bc3-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="85bc3-123">Jika terdapat kadar nilai tidak diisi yang tinggi bagi atribut anda, pilih **Ramal nilai yang tidak diisi** untuk meneruskan dengan ramalan anda.</span><span class="sxs-lookup"><span data-stu-id="85bc3-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="85bc3-124">![Status gambaran keseluruhan dengan butang nilai yang tidak diisi ditunjukkan](media/intelligence-overviewpredictmissingvalues.png "Status gambaran keseluruhan dengan butang ramalan nilai hilang ditunjukkan")</span><span class="sxs-lookup"><span data-stu-id="85bc3-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="85bc3-125">Sediakan **Nama paparan** dan **Nama entiti output** untuk hasil ramalan.</span><span class="sxs-lookup"><span data-stu-id="85bc3-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="85bc3-126">Senarai pra-penuhi bagi pilihan akan menunjukkan di mana anda boleh memetakan nilai untuk kategori diramalkan.</span><span class="sxs-lookup"><span data-stu-id="85bc3-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="85bc3-127">Dalam kes ini, pilihan kategori anda hanyalah 0 atau 1 kerana ia memetakan ramalan benar/palsu atau bersifat binari.</span><span class="sxs-lookup"><span data-stu-id="85bc3-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="85bc3-128">Dalam lajur Kategori, petakan nilai medan yang anda ingin klasifikasikan sebagai “0” dalam ramalan akhir kepada “0” dan item yang anda ingin klasifikasikan sebagai “1” dalam ramalan akhir kepada “1”.</span><span class="sxs-lookup"><span data-stu-id="85bc3-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="85bc3-129">![Contoh menunjukkan nilai medan yang dipetakan ke kategori](media/intelligence-categorymapping.png "Contoh menunjukkan nilai medan yang dipetakan ke kategori")</span><span class="sxs-lookup"><span data-stu-id="85bc3-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="85bc3-130">Pilih **Selesai** dan ramalan akan diproses.</span><span class="sxs-lookup"><span data-stu-id="85bc3-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="85bc3-131">Pemprosesan akan mengambil sedikit masa, bergantung kepada saiz dan kekompleksan data.</span><span class="sxs-lookup"><span data-stu-id="85bc3-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="85bc3-132">Hasil akan tersedia dalam entiti baharu berasaskan pada **Nama entiti output** bagi ramalan yang anda telah ciptakan.</span><span class="sxs-lookup"><span data-stu-id="85bc3-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="85bc3-133">Cipta ramalan semasa mencipta bahagian</span><span class="sxs-lookup"><span data-stu-id="85bc3-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="85bc3-134">Meramalkan nilai yang tidak diisi untuk atribut khusus bagi pilihan juga boleh dilakukan semasa mencipta bahagian.</span><span class="sxs-lookup"><span data-stu-id="85bc3-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="85bc3-135">Secara khususnya, apabila anda segera mencipta bahagian berasaskan pada sama ada entiti Pelanggan disatukan anda atau entiti Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="85bc3-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="85bc3-136">Sebagai sebahagian daripada aliran ini, anda akan memiilih atribut khusus untuk asas bahagian anda seperti Kepuasan Pelanggan atau Amaun Pembelian.</span><span class="sxs-lookup"><span data-stu-id="85bc3-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="85bc3-137">Selepas penciptaan bahagian, sistem akan mencadangkan kaedah untuk meramalkan sebarang nilai yang hilang untuk atribut ini.</span><span class="sxs-lookup"><span data-stu-id="85bc3-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="85bc3-138">Dalam wawasan khalayak, pergi ke **Segmen** dan pilih jubin **Profil**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="85bc3-139">Pilih **Medan** untuk mencipta bahagian pada dan pilih **Operator**, kemudian pilih **Semak Semula**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="85bc3-140">Berikan **Nama** dan **Nama paparan** untuk bahagian.</span><span class="sxs-lookup"><span data-stu-id="85bc3-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="85bc3-141">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-141">Select **Save**.</span></span>

5. <span data-ttu-id="85bc3-142">Jika bahagian yang baharu anda cipta mempunyai data yang tidak lengkap dalam medan sumber, anda boleh memilih untuk meramalkan nilai yang hilang.</span><span class="sxs-lookup"><span data-stu-id="85bc3-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="85bc3-143">![Butang ramalan](media/segments-predictoption.png "Butang ramalan")</span><span class="sxs-lookup"><span data-stu-id="85bc3-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="85bc3-144">Sediakan **Nama paparan** dan **Nama entiti output** untuk hasil ramalan.</span><span class="sxs-lookup"><span data-stu-id="85bc3-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="85bc3-145">Pilih **Selesai**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-145">Select **Done**.</span></span> <span data-ttu-id="85bc3-146">Ramalan anda akan dijana sebentar lagi dalam entiti baharu dengan nama yang anda sediakan untuk **Nama entiti output**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="85bc3-147">Lihat ramalan</span><span class="sxs-lookup"><span data-stu-id="85bc3-147">View a prediction</span></span>

1. <span data-ttu-id="85bc3-148">Dalam wawasan khalayak, pergi ke **Kecerdasan** > **Ramalan** > **Ramalan saya**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="85bc3-149">Pilih ramalan yang anda mahu semak semula.</span><span class="sxs-lookup"><span data-stu-id="85bc3-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="85bc3-150">Pilih elipsis dalam lajur **Tindakan** dan pilih **Lihat**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="85bc3-151">Anda akan melihat bilangan titik data dalam pandangan ramalan anda.</span><span class="sxs-lookup"><span data-stu-id="85bc3-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="85bc3-152">![Halaman ramalan](media/intelligence-predictionsviewpage.png "Halaman ramalan")</span><span class="sxs-lookup"><span data-stu-id="85bc3-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="85bc3-153">**Nilai ramalan** menunjukkan pemetaan yang anda cipta semasa peringkat pemetaan nilai Medan ke kategori.</span><span class="sxs-lookup"><span data-stu-id="85bc3-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="85bc3-154">Ini ialah nilai dalam set data yang telah dipetakan kepada kategori tertentu.</span><span class="sxs-lookup"><span data-stu-id="85bc3-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="85bc3-155">-**Pempengaruh teratas** merupakan faktor dalam set data anda yang paling cenderung untuk mempengaruhi keyakinan ramalan bagi nilai Medan anda untuk dipetakan ke kategori tertentu.</span><span class="sxs-lookup"><span data-stu-id="85bc3-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="85bc3-156">**Prestasi** menunjukkan bagaimana ramalan dilakukan.</span><span class="sxs-lookup"><span data-stu-id="85bc3-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="85bc3-157">Pilih pautan untuk mengetahui dengan lanjut.</span><span class="sxs-lookup"><span data-stu-id="85bc3-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="85bc3-158">**Pratonton** menunjukkan sampel output set data daripada ramalan anda dan kebarangkalian, atau keyakinan kita, tentang nilai ramalan yang mana 0 ialah tidak pasti, dan 1 ialah pasti.</span><span class="sxs-lookup"><span data-stu-id="85bc3-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="85bc3-159">Kemas kini ramalan</span><span class="sxs-lookup"><span data-stu-id="85bc3-159">Update a prediction</span></span>

1. <span data-ttu-id="85bc3-160">Dalam wawasan khalayak, pergi ke **Kecerdasan** > **Ramalan** > **Ramalan saya**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="85bc3-161">Pilih ramalan yang anda mahu kemas kini dan pilih ikon **Kemas Kini**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="85bc3-162">Ramalan akan dijadualkan untuk pemprosesan.</span><span class="sxs-lookup"><span data-stu-id="85bc3-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="85bc3-163">Anda boleh melihat masa kemas kini terakhir dalam lajur **Kemas Kini** di halaman **Ramalan**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="85bc3-164">Edit ramalan</span><span class="sxs-lookup"><span data-stu-id="85bc3-164">Edit a prediction</span></span>

<span data-ttu-id="85bc3-165">Selepas anda mencipta ramalan, anda boleh sesuaikan model dalam the AI Builder untuk meningkatkan keberkesanan model anda.</span><span class="sxs-lookup"><span data-stu-id="85bc3-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="85bc3-166">Dalam wawasan khalayak, pergi ke **Kecerdasan** > **Ramalan** > **Ramalan saya**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="85bc3-167">Pilih ramalan yang anda mahu edit.</span><span class="sxs-lookup"><span data-stu-id="85bc3-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="85bc3-168">Pilih elipsis dalam lajur **Tindakan** dan pilih **Lihat**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="85bc3-169">Pilih **Sesuaikan dalam AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="85bc3-170">Kemas kini model anda dalam AI Builder.</span><span class="sxs-lookup"><span data-stu-id="85bc3-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="85bc3-171">[Ketahui lebih lanjut tentang mengurus model dalam AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="85bc3-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="85bc3-172">Jalanan ramalan anda yang seterusnya akan menggunakan model dikemas kini yang anda cipta.</span><span class="sxs-lookup"><span data-stu-id="85bc3-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="85bc3-173">Model baharu yang dicipta dalam AI Builder tidak akan dipaparkan dalam wawasan khalayak melainkan model itu dicipta daripada pengalaman yang disenaraikan di atas.</span><span class="sxs-lookup"><span data-stu-id="85bc3-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="85bc3-174">Alih keluar ramalan</span><span class="sxs-lookup"><span data-stu-id="85bc3-174">Remove a prediction</span></span>

1. <span data-ttu-id="85bc3-175">Dalam wawasan khalayak, pergi ke **Kecerdasan** > **Ramalan** > **Ramalan saya**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="85bc3-176">Pilih ramalan yang anda mahu padam.</span><span class="sxs-lookup"><span data-stu-id="85bc3-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="85bc3-177">Pilih elipsis dalam lajur **Tindakan** dan pilih **Padam**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="85bc3-178">Sahkan pemadaman.</span><span class="sxs-lookup"><span data-stu-id="85bc3-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="85bc3-179">Penyelesaian masalah</span><span class="sxs-lookup"><span data-stu-id="85bc3-179">Troubleshooting</span></span>

<span data-ttu-id="85bc3-180">Jika anda tidak dapat melengkapkan proses lampir Common Data Service kerana ralat, anda boleh cuba melengkapkan proses itu secara manual.</span><span class="sxs-lookup"><span data-stu-id="85bc3-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="85bc3-181">Terdapat dua isu diketahui yang boleh berlaku dalam proses lampir:</span><span class="sxs-lookup"><span data-stu-id="85bc3-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="85bc3-182">Penyelesaian Tambahan Kad Pelanggan tidak dipasang.</span><span class="sxs-lookup"><span data-stu-id="85bc3-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="85bc3-183">Lengkapkan arahan untuk [memasang dan mengkonfigurasi penyelesaian](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="85bc3-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="85bc3-184">Keizinan aplikasi tidak diberikan.</span><span class="sxs-lookup"><span data-stu-id="85bc3-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="85bc3-185">Pergi ke [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="85bc3-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="85bc3-186">Pilih **Persekitaran**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="85bc3-187">Pilih elipsis yang bersebelahan dengan persekitaran yang anda mahu tambah keizinan dan pilih **Tetapan**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="85bc3-188">Kembangkan **Keizinan + pengguna** dan pilih **Pengguna**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="85bc3-189">Pilih **+ Baharu** dan pilih **Pengguna**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="85bc3-190">Pilih **Pengguna aplikasi** jika ia belum dipilih dan masukkan maklumat berikut:</span><span class="sxs-lookup"><span data-stu-id="85bc3-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="85bc3-191">**Nama Pengguna:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="85bc3-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="85bc3-192">**ID Aplikasi:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="85bc3-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="85bc3-193">**Nama Pertama:** Pelanggan</span><span class="sxs-lookup"><span data-stu-id="85bc3-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="85bc3-194">**Nama Akhir:** Insights</span><span class="sxs-lookup"><span data-stu-id="85bc3-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="85bc3-195">**E-mel Utama:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="85bc3-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="85bc3-196">Pilih **Simpan & Tutup**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="85bc3-197">Pilih pengguna yang anda baru cipta.</span><span class="sxs-lookup"><span data-stu-id="85bc3-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="85bc3-198">Pilih **Urus Peranan** dalam bar menu di atas.</span><span class="sxs-lookup"><span data-stu-id="85bc3-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="85bc3-199">Pilih **Pentadbir Sistem** kemudian pilih **OK**.</span><span class="sxs-lookup"><span data-stu-id="85bc3-199">Select **System Administrator**, then select **OK**.</span></span>
