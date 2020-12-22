---
title: Model pembelajaran mesin tersuai | Dokumen Microsoft
description: Kerja dengan model tersuai daripada Azure Machine Learning dalam Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668914"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="b9fef-103">Model pembelajaran mesin tersuai</span><span class="sxs-lookup"><span data-stu-id="b9fef-103">Custom machine learning models</span></span>

<span data-ttu-id="b9fef-104">**Kecerdasan** > **Model tersuai** membolehkan anda mengurus aliran kerja berasaskan model Pembelajaran Mesin Azure.</span><span class="sxs-lookup"><span data-stu-id="b9fef-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="b9fef-105">Aliran kerja membantu anda memilih data yang anda mahukan untuk menjana wawasan dan memetakan keputusan kepada data pelanggan disatukan anda.</span><span class="sxs-lookup"><span data-stu-id="b9fef-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="b9fef-106">Untuk maklumat lanjut tentang membina model ML tersuai, lihat [Gunakan model berasaskan Pembelajaran Mesin Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="b9fef-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="b9fef-107">AI Yang Bertanggungjawab</span><span class="sxs-lookup"><span data-stu-id="b9fef-107">Responsible AI</span></span>

<span data-ttu-id="b9fef-108">Ramalan menawarkan keupayaan untuk mencipta pengalaman pelanggan yang lebih baik, meningkatkan keupayaan perniagaan dan strim hasil.</span><span class="sxs-lookup"><span data-stu-id="b9fef-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="b9fef-109">Kami amat mengesyorkan agar anda mengimbangkan nilai ramalan anda terhadap kesan yang telah diberikan dan bias yang mungkin diperkenalkan dengan cara yang beretika.</span><span class="sxs-lookup"><span data-stu-id="b9fef-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="b9fef-110">Ketahui lebih lanjut tentang cara Microsoft [menangani AI Yang Bertanggungjawab](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="b9fef-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="b9fef-111">Anda juga boleh mengetahui tentang [teknik dan proses untuk pembelajaran mesin yang bertanggungjawab](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) khusus kepada Pembelajaran Mesin Azure.</span><span class="sxs-lookup"><span data-stu-id="b9fef-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b9fef-112">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="b9fef-112">Prerequisites</span></span>

- <span data-ttu-id="b9fef-113">Pada masa ini, ciri ini menyokong perkhidmatan web yang diterbitkan melalui [Studio Pembelajaran Mesin (klasik)](https://studio.azureml.net) dan [talian paip kelompok Pembelajaran Mesin Azure](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="b9fef-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="b9fef-114">Anda memerlukan akaun storan Azure Data Lake Gen2 yang berkaitan dengan tika Azure Studio anda untuk menggunakan ciri ini.</span><span class="sxs-lookup"><span data-stu-id="b9fef-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="b9fef-115">Untuk mendapatkan maklumat lanjut, [Cipta akaun storan Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="b9fef-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="b9fef-116">Tambah aliran kerja baharu</span><span class="sxs-lookup"><span data-stu-id="b9fef-116">Add a new workflow</span></span>

1. <span data-ttu-id="b9fef-117">Pergi ke **Kecerdasan** > **Model tersuai** dan pilih **Aliran kerja baharu**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="b9fef-118">Berikan model tersuai anda nama yang mudah dikenali dalam medan **Nama**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b9fef-119">![Petikan skrin anak tetingkap aliran kerja Baharu](media/new-workflowv2.png "Petikan skrin anak tetingkap aliran kerja Baharu")</span><span class="sxs-lookup"><span data-stu-id="b9fef-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="b9fef-120">Pilih organisasi yang mengandungi perkhidmatan web dalam **Penyewa yang mengandungi perkhidmatan web anda**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="b9fef-121">Jika langganan Pembelajaran Mesin Azure berada dalam penyewa yang berbeza daripada Customer Insights, pilih **Daftar masuk** dengan kelayakan anda untuk organisasi yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="b9fef-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="b9fef-122">Pilih **Ruang kerja** yang berkaitan dengan perkhidmatan web anda.</span><span class="sxs-lookup"><span data-stu-id="b9fef-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="b9fef-123">Terdapat dua bahagian yang disenaraikan, satu untuk Pembelajaran Mesin Azure v1 (Studio Pembelajaran Mesin (klasik)) dan Pembelajaran Mesin Azure v2 (Pembelajaran Mesin Azure).</span><span class="sxs-lookup"><span data-stu-id="b9fef-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="b9fef-124">Jika anda tidak pasti ruang kerja yang sesuai untuk perkhidmatan web Studio Pembelajaran Mesin (klasik) anda, pilih **Mana-mana**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="b9fef-125">Pilih perkhidmatan web Studio Pembelajaran Mesin (klasik) atau talian paip Pembelajaran Mesin Azure dalam juntai bawah **Perkhidmatan web yang mengandungi model anda**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="b9fef-126">Kemudian pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="b9fef-127">Ketahui lebih lanjut tentang [menerbitkan perkhidmatan web Studio Pembelajaran Mesin (klasik)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="b9fef-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="b9fef-128">Ketahui lebih lanjut tentang [menerbitkan talian paip dalam Pembelajaran Mesin Azure menggunakan pereka bentuk](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) atau [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="b9fef-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="b9fef-129">Talian paip anda mesti diterbitkan di bawah [titik tamat talian paip](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="b9fef-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="b9fef-130">Untuk setiap **Input perkhidmatan web**, pilih **Entiti** yang berpadanan daripada wawasan khalayak dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b9fef-131">![Konfigurasikan aliran kerja](media/intelligence-screen2-updated.png "Konfigurasikan aliran kerja")</span><span class="sxs-lookup"><span data-stu-id="b9fef-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="b9fef-132">Dalam langkah **Parameter Output Model**, tetapkan ciri berikut:</span><span class="sxs-lookup"><span data-stu-id="b9fef-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="b9fef-133">Studio Pembelajaran Mesin (klasik)</span><span class="sxs-lookup"><span data-stu-id="b9fef-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="b9fef-134">Masukkan output **Nama entiti** yang anda mahu hasil output perkhidmatan web mengalir masuk.</span><span class="sxs-lookup"><span data-stu-id="b9fef-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="b9fef-135">Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="b9fef-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="b9fef-136">Masukkan output **Nama entiti** yang anda mahu hasil output talian paip mengalir masuk.</span><span class="sxs-lookup"><span data-stu-id="b9fef-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="b9fef-137">Pilih **Nama parameter storan data output** bagi talian paip kelompok daripada juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="b9fef-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="b9fef-138">Pilih **Nama parameter Laluan Output** bagi talian paip kelompok daripada juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="b9fef-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="b9fef-139">![Anak tetingkap Parameter Output Model](media/intelligence-screen3-outputparameters.png "Anak tetingkap Parameter Output Model")</span><span class="sxs-lookup"><span data-stu-id="b9fef-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="b9fef-140">Pilih atribut berpadanan daripada senarai juntai bawah **ID Pelanggan dalam hasil** yang mengenal pasti pelanggan dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b9fef-141">![Kaitkan hasil dengan anak tetingkap data Pelanggan](media/intelligence-screen4-relatetocustomer.png "Kaitkan hasil dengan anak tetingkap data Pelanggan")</span><span class="sxs-lookup"><span data-stu-id="b9fef-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="b9fef-142">Anda akan melihat skrin **Aliran Kerja Disimpan** dengan butiran tentang aliran kerja tersebut.</span><span class="sxs-lookup"><span data-stu-id="b9fef-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="b9fef-143">Jika anda mengkonfigurasi aliran kerja untuk talian paip Pembelajaran Mesin Azure, wawasan khalayak akan dilampirkan ke ruang kerja yang mengandungi talian paip.</span><span class="sxs-lookup"><span data-stu-id="b9fef-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="b9fef-144">Wawasan khalayak akan mendapat peranan **Penyumbang** pada ruang kerja Azure.</span><span class="sxs-lookup"><span data-stu-id="b9fef-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="b9fef-145">Pilih **Selesai**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-145">Select **Done**.</span></span>

1. <span data-ttu-id="b9fef-146">Anda kini boleh menjalankan aliran kerja daripada halaman **Model Tersuai**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="b9fef-147">Edit satu aliran kerja</span><span class="sxs-lookup"><span data-stu-id="b9fef-147">Edit a workflow</span></span>

1. <span data-ttu-id="b9fef-148">Pada halaman **Model Tersuai**, pilih elipsis menegak dalam lajur **Tindakan** di sebelah aliran kerja yang anda cipta sebelum ini dan pilih **Edit**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="b9fef-149">Anda boleh mengemas kini nama aliran kerja anda yang dikenali dalam medan **Nama paparan** tetapi anda tidak boleh mengubah perkhidmatan web atau talian paip yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="b9fef-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="b9fef-150">Pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-150">Select **Next**.</span></span>

1. <span data-ttu-id="b9fef-151">Untuk setiap **Input perkhidmatan web**, anda boleh mengemas kini **Entiti** yang berpadanan daripada wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="b9fef-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="b9fef-152">Kemudian pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="b9fef-153">Dalam langkah **Parameter Output Model**, tetapkan ciri berikut:</span><span class="sxs-lookup"><span data-stu-id="b9fef-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="b9fef-154">Studio Pembelajaran Mesin (klasik)</span><span class="sxs-lookup"><span data-stu-id="b9fef-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="b9fef-155">Masukkan output **Nama entiti** yang anda mahu hasil output perkhidmatan web mengalir masuk.</span><span class="sxs-lookup"><span data-stu-id="b9fef-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="b9fef-156">Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="b9fef-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="b9fef-157">Masukkan output **Nama entiti** yang anda mahu hasil output talian paip mengalir masuk.</span><span class="sxs-lookup"><span data-stu-id="b9fef-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="b9fef-158">Pilih **Nama parameter storan data output** untuk talian paip ujian anda.</span><span class="sxs-lookup"><span data-stu-id="b9fef-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="b9fef-159">Pilih **Nama parameter Laluan Output** untuk talian paip ujian anda.</span><span class="sxs-lookup"><span data-stu-id="b9fef-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="b9fef-160">Pilih atribut berpadanan daripada senarai juntai bawah **ID Pelanggan dalam hasil** yang mengenal pasti pelanggan dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="b9fef-161">Anda perlu memilih atribut daripada output inferens dengan nilai yang serupa dengan lajur ID Pelanggan bagi entiti Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="b9fef-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="b9fef-162">Jika tidak mempunyai lajur sedemikian dalam set data anda, pilih atribut yang mengenal pasti baris secara unik.</span><span class="sxs-lookup"><span data-stu-id="b9fef-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="b9fef-163">Jalankan aliran kerja</span><span class="sxs-lookup"><span data-stu-id="b9fef-163">Run a workflow</span></span>

1. <span data-ttu-id="b9fef-164">Pada halaman **Model Tersuai**, pilih elipsis menegak dalam lajur **Tindakan** di sebelah aliran kerja yang anda cipta sebelum ini.</span><span class="sxs-lookup"><span data-stu-id="b9fef-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="b9fef-165">Pilih **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-165">Select **Run**.</span></span>

<span data-ttu-id="b9fef-166">Aliran kerja anda juga berjalan secara automatik dengan setiap muat semula berjadual.</span><span class="sxs-lookup"><span data-stu-id="b9fef-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="b9fef-167">Ketahui lebih lanjut tentang [menyediakan menyegarkan semula berjadual](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b9fef-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="b9fef-168">Padam satu aliran kerja</span><span class="sxs-lookup"><span data-stu-id="b9fef-168">Delete a workflow</span></span>

1. <span data-ttu-id="b9fef-169">Pada halaman **Model Tersuai**, pilih elipsis menegak dalam lajur **Tindakan** di sebelah aliran kerja yang anda cipta sebelum ini.</span><span class="sxs-lookup"><span data-stu-id="b9fef-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="b9fef-170">Pilih **Padam** dan sahkan pemadaman anda.</span><span class="sxs-lookup"><span data-stu-id="b9fef-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="b9fef-171">Aliran kerja anda akan dipadamkan.</span><span class="sxs-lookup"><span data-stu-id="b9fef-171">Your workflow will be deleted.</span></span> <span data-ttu-id="b9fef-172">[Entiti](entities.md) yang telah dicipta apabila anda mencipta aliran kerja berlanjutan dan boleh dilihat daripada halaman **Entiti**.</span><span class="sxs-lookup"><span data-stu-id="b9fef-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
