---
title: Gunakan model berasaskan Pembelajaran Mesin Azure
description: Gunakan model berasaskan Pembelajaran Mesin Azure dalam Dynamics 365 Customer Insights.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609836"
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

Cipta set data untuk menggunakan data entiti daripada Wawasan Pelanggan untuk saluran paip inferens kelompok anda. Daftarkan set data ini dalam ruang kerja. Buat masa ini, kami hanya menyokong [set data berjadual](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) dalam format .csv. Parameterkan set data yang sepadan dengan data entiti sebagai parameter saluran paip.

- Parameter set data dalam Pereka Bentuk

  Dalam pereka bentuk, buka **Pilih Lajur dalam Set Data** dan pilih **Tetapkan sebagai parameter talian paip**, tempat anda menyediakan nama untuk parameter.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Pemparameteran set data dalam pereka bentuk.":::

- Parameter set data dalam SDK (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Talian paip inferens kelompok
  
- Dalam pereka bentuk, gunakan saluran paip latihan untuk membuat atau mengemas kini saluran paip kesimpulan. Buat masa ini, hanya talian paip inferens kelompok disokong.

- Menggunakan SDK, terbitkan saluran paip ke titik akhir. Buat masa ini, Customer Insights menyepadukan dengan talian paip lalai pada titik tamat talian paip kelompok dalam ruang kerja Pembelajaran Mesin.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Import data talian paip ke dalam Customer Insights

- Pereka bentuk menyediakan [modul Data Eksport](/azure/machine-learning/algorithm-module-reference/export-data) yang membenarkan output talian paip dieksport ke storan Azure. Buat masa ini, modul mesti menggunakan jenis storan data **Storan Blob Azure** dan memparameterkan **Storan data** dan **Laluan** relatif. Customer Insights menggantikan kedua-dua parameter ini semasa pelaksanaan talian paip dengan storan data dan laluan yang boleh diakses oleh produk.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="Eksport Konfigurasi Modul Data.":::

- Semasa menulis output kesimpulan menggunakan kod, muat naik output ke laluan dalam *kedai* data berdaftar di ruang kerja. Jika laluan dan storan data adalah diparameterkan dalam talian paip, Customer insights akan dapat membaca dan mengimport output inferens. Buat masa ini, output berjadual tunggal dalam format csv disokong. Laluan mesti disertakan dengan direktori dan nama fail.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]