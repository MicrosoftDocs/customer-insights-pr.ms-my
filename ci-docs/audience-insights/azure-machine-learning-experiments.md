---
title: Percubaan Pembelajaran Mesin Azure
description: Gunakan model berasaskan Pembelajaran Mesin Azure dalam Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267917"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="a1aa3-103">Gunakan model berasaskan Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="a1aa3-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="a1aa3-104">Data yang disatukan dalam Dynamics 365 Customer Insights adalah ialah untuk membina model pembelajaran mesin yang boleh menjana Insights perniagaan tambahan.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="a1aa3-105">Customer Insights bersepadu dengan Studio Pembelajaran Mesin (klasik) dan Pembelajaran Mesin Azure untuk menggunakan model tersuai anda sendiri.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="a1aa3-106">Rujuk [percubaan Studio Pembelajaran Mesin (klasik)](machine-learning-studio-experiments.md) bagi contoh percubaan yang dibina pada Studio Pembelajaran Mesin (klasik).</span><span class="sxs-lookup"><span data-stu-id="a1aa3-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a1aa3-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="a1aa3-107">Prerequisites</span></span>

- <span data-ttu-id="a1aa3-108">Akses kepada Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a1aa3-108">Access to Customer Insights</span></span>
- <span data-ttu-id="a1aa3-109">Langganan Azure Enterprise Aktif</span><span class="sxs-lookup"><span data-stu-id="a1aa3-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="a1aa3-110">Profil pelanggan yang disatukan</span><span class="sxs-lookup"><span data-stu-id="a1aa3-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="a1aa3-111">[Eksport entiti untuk storan Blob Azure](export-azure-blob-storage.md) dikonfigurasikan</span><span class="sxs-lookup"><span data-stu-id="a1aa3-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="a1aa3-112">Sediakan ruang kerja Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="a1aa3-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="a1aa3-113">Lihat [cipta ruang kerja Pembelajaran Mesin Azure](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) bagi pilihan berbeza untuk mencipta ruang kerja.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="a1aa3-114">Untuk prestasi terbaik, cipta ruang kerja dalam rantau Azure yang geografi paling hampir dengan persekitaran Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="a1aa3-115">Akses ruang kerja anda melalui [Studio Pembelajaran Mesin Azure](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="a1aa3-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="a1aa3-116">Terdapat beberapa [cara untuk berinteraksi](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) dengan ruang kerja anda.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="a1aa3-117">Gunakan pereka bentuk Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="a1aa3-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="a1aa3-118">Pereka bentuk Pembelajaran Mesin Azure menyediakan kanvas visual, tempat anda boleh menyeret dan melepaskan set data dan modul, serupa dengan Studio Pembelajaran Mesin (klasik).</span><span class="sxs-lookup"><span data-stu-id="a1aa3-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="a1aa3-119">Talian paip kelompok yang dicipta daripada pereka bentuk boleh disepadukan ke dalam Customer Insights jika ia dikonfigurasikan dengan sewajarnya.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="a1aa3-120">Gunakan SDK Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="a1aa3-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="a1aa3-121">Ahli sains data dan pembangun AI menggunakan [SDK Pembelajaran Mesin Azure](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) untuk membina aliran kerja pembelajaran mesin.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="a1aa3-122">Buat masa ini, model yang dilatih menggunakan SDK tidak boleh disepadukan secara langsung dengan Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="a1aa3-123">Talian paip inferens kelompok yang menggunakan model tersebut diperlukan untuk penyepaduan dengan Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="a1aa3-124">Keperluan talian paip kelompok untuk bersepadu dengan Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a1aa3-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="a1aa3-125">Konfigurasi set data</span><span class="sxs-lookup"><span data-stu-id="a1aa3-125">Dataset Configuration</span></span>

<span data-ttu-id="a1aa3-126">Anda perlu mencipta set data untuk menggunakan data entiti daripada Customer Insights ke talian paip inferens kelompok anda.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="a1aa3-127">Set data ini perlu didaftarkan dalam ruang kerja.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="a1aa3-128">Buat masa ini, kami hanya menyokong [set data berjadual](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) dalam format .csv.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="a1aa3-129">Set data yang sesuai dengan data entiti perlu diparameterkan sebagai parameter talian paip.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="a1aa3-130">Parameter set data dalam Pereka Bentuk</span><span class="sxs-lookup"><span data-stu-id="a1aa3-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="a1aa3-131">Dalam pereka bentuk, buka **Pilih Lajur dalam Set Data** dan pilih **Tetapkan sebagai parameter talian paip**, tempat anda menyediakan nama untuk parameter.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="a1aa3-132">![Pemparameteran set data dalam pereka bentuk](media/intelligence-designer-dataset-parameters.png "Pemparameteran set data dalam pereka bentuk")</span><span class="sxs-lookup"><span data-stu-id="a1aa3-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="a1aa3-133">Parameter set data dalam SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="a1aa3-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="a1aa3-134">Talian paip inferens kelompok</span><span class="sxs-lookup"><span data-stu-id="a1aa3-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="a1aa3-135">Dalam pereka bentuk, talian paip latihan boleh digunakan untuk mencipta atau mengemas kini talian paip inferens.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="a1aa3-136">Buat masa ini, hanya talian paip inferens kelompok disokong.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="a1aa3-137">Menggunakan SDK, anda boleh menerbitkan talian paip ke titik tamat.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="a1aa3-138">Buat masa ini, Customer Insights menyepadukan dengan talian paip lalai pada titik tamat talian paip kelompok dalam ruang kerja Pembelajaran Mesin.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="a1aa3-139">Import data talian paip ke dalam Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a1aa3-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="a1aa3-140">Pereka bentuk menyediakan [modul Data Eksport](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) yang membenarkan output talian paip dieksport ke storan Azure.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="a1aa3-141">Buat masa ini, modul mesti menggunakan jenis storan data **Storan Blob Azure** dan memparameterkan **Storan data** dan **Laluan** relatif.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="a1aa3-142">Customer Insights menggantikan kedua-dua parameter ini semasa pelaksanaan talian paip dengan storan data dan laluan yang boleh diakses oleh produk.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a1aa3-143">![Eksport Konfigurasi Modul Data](media/intelligence-designer-importdata.png "Eksport Konfigurasi Modul Data")</span><span class="sxs-lookup"><span data-stu-id="a1aa3-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="a1aa3-144">Apabila menulis output inferens menggunakan kod, anda boleh memuat naik output kepada laluan dalam *storan data berdaftar* dalam ruang kerja.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="a1aa3-145">Jika laluan dan storan data adalah diparameterkan dalam talian paip, Customer insights akan dapat membaca dan mengimport output inferens.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="a1aa3-146">Buat masa ini, output berjadual tunggal dalam format csv disokong.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="a1aa3-147">Laluan mesti disertakan dengan direktori dan nama fail.</span><span class="sxs-lookup"><span data-stu-id="a1aa3-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]