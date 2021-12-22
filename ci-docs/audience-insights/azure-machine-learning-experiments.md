---
title: Percubaan Pembelajaran Mesin Azure
description: Gunakan model berasaskan Pembelajaran Mesin Azure dalam Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e37eec503c9df83ef72497e22afa1266296e642c
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881749"
---
# <a name="use-azure-machine-learning-based-models"></a>Gunakan model berasaskan Pembelajaran Mesin Azure

Data yang disatukan dalam Dynamics 365 Customer Insights adalah ialah untuk membina model pembelajaran mesin yang boleh menjana Insights perniagaan tambahan. Customer Insights disepadukan dengan Pembelajaran Mesin Azure untuk menggunakan model tersuai sendiri.

## <a name="prerequisites"></a>Prasyarat

- Akses kepada Customer Insights
- Langganan Azure Enterprise Aktif
- [Profil pelanggan yang disatukan](data-unification.md)
- [Eksport entiti untuk storan Blob Azure](export-azure-blob-storage.md) dikonfigurasikan

## <a name="set-up-azure-machine-learning-workspace"></a>Sediakan ruang kerja Pembelajaran Mesin Azure

1. Lihat [cipta ruang kerja Pembelajaran Mesin Azure](/azure/machine-learning/concept-workspace#-create-a-workspace) bagi pilihan berbeza untuk mencipta ruang kerja. Untuk prestasi terbaik, cipta ruang kerja dalam rantau Azure yang geografi paling hampir dengan persekitaran Customer Insights anda.

1. Akses ruang kerja anda melalui [Studio Pembelajaran Mesin Azure](https://ml.azure.com/). Terdapat beberapa [cara untuk berinteraksi](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) dengan ruang kerja anda.

## <a name="work-with-azure-machine-learning-designer"></a>Gunakan pereka bentuk Pembelajaran Mesin Azure

Pereka bentuk Azure Pembelajaran Mesin menyediakan kanvas visual di mana anda boleh menyeret dan melepaskan set data dan modul. Talian paip kelompok yang dicipta daripada pereka bentuk boleh disepadukan ke dalam Customer Insights jika ia dikonfigurasikan dengan sewajarnya. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Gunakan SDK Pembelajaran Mesin Azure

Ahli sains data dan pembangun AI menggunakan [SDK Pembelajaran Mesin Azure](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) untuk membina aliran kerja pembelajaran mesin. Buat masa ini, model yang dilatih menggunakan SDK tidak boleh disepadukan secara langsung dengan Customer Insights. Talian paip inferens kelompok yang menggunakan model tersebut diperlukan untuk penyepaduan dengan Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Keperluan talian paip kelompok untuk bersepadu dengan Customer Insights

### <a name="dataset-configuration"></a>Konfigurasi set data

Anda perlu mencipta set data untuk menggunakan data entiti daripada Customer Insights ke talian paip inferens kelompok anda. Set data ini perlu didaftarkan dalam ruang kerja. Buat masa ini, kami hanya menyokong [set data berjadual](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) dalam format .csv. Set data yang sesuai dengan data entiti perlu diparameterkan sebagai parameter talian paip.
   
* Parameter set data dalam Pereka Bentuk
   
     Dalam pereka bentuk, buka **Pilih Lajur dalam Set Data** dan pilih **Tetapkan sebagai parameter talian paip**, tempat anda menyediakan nama untuk parameter.

     > [!div class="mx-imgBorder"]
     > ![Pemparameteran set data dalam pereka bentuk.](media/intelligence-designer-dataset-parameters.png "Pemparameteran set data dalam pereka bentuk")
   
* Parameter set data dalam SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Talian paip inferens kelompok
  
* Dalam pereka bentuk, talian paip latihan boleh digunakan untuk mencipta atau mengemas kini talian paip inferens. Buat masa ini, hanya talian paip inferens kelompok disokong.

* Menggunakan SDK, anda boleh menerbitkan talian paip ke titik tamat. Buat masa ini, Customer Insights menyepadukan dengan talian paip lalai pada titik tamat talian paip kelompok dalam ruang kerja Pembelajaran Mesin.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Import data talian paip ke dalam Customer Insights

* Pereka bentuk menyediakan [modul Data Eksport](/azure/machine-learning/algorithm-module-reference/export-data) yang membenarkan output talian paip dieksport ke storan Azure. Buat masa ini, modul mesti menggunakan jenis storan data **Storan Blob Azure** dan memparameterkan **Storan data** dan **Laluan** relatif. Customer Insights menggantikan kedua-dua parameter ini semasa pelaksanaan talian paip dengan storan data dan laluan yang boleh diakses oleh produk.
   > [!div class="mx-imgBorder"]
   > ![Eksport Konfigurasi Modul Data.](media/intelligence-designer-importdata.png "Eksport Konfigurasi Modul Data")
   
* Apabila menulis output inferens menggunakan kod, anda boleh memuat naik output kepada laluan dalam *storan data berdaftar* dalam ruang kerja. Jika laluan dan storan data adalah diparameterkan dalam talian paip, Customer insights akan dapat membaca dan mengimport output inferens. Buat masa ini, output berjadual tunggal dalam format csv disokong. Laluan mesti disertakan dengan direktori dan nama fail.

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