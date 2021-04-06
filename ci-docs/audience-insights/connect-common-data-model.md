---
title: Sambung data Common Data Model ke akaun Azure Data Lake
description: Bekerja dengan data Common Data Model menggunakan Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596556"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="2f7ed-103">Sambungkan ke folder Common Data Model menggunakan akaun Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="2f7ed-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="2f7ed-104">Artikel ini memberikan maklumat tentang cara untuk data daripada folder Common Data Model menggunakan akaun Azure Data Lake Storage Gen2 anda.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="2f7ed-105">Pertimbangan penting</span><span class="sxs-lookup"><span data-stu-id="2f7ed-105">Important considerations</span></span>

- <span data-ttu-id="2f7ed-106">Data dalam data Azure Data Lake anda perlu mengikut piawaian Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="2f7ed-107">Format lain tidak disokong pada masa ini.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="2f7ed-108">Pengingesan data menyokong data akaun storan Azure Data Lake *Gen2* secara eksklusif.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="2f7ed-109">Anda tidak boleh menggunakan akaun storan Azure Data Lake Gen1 untuk menginges data.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="2f7ed-110">Untuk mengesahkan dengan prinsip perkhidmatan Azure, pastikan ia dikonfigurasikan dalam penyewa anda.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="2f7ed-111">Untuk maklumat lanjut, lihat [Sambungkan cerapan khalayak ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="2f7ed-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="2f7ed-112">Azure Data Lake yang ingin anda sambungkan dan inges data dari perlu berada di rantau Azure yang sama seperti persekitaran Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="2f7ed-113">Sambungan ke folder Common Data Model dari data lake dalam rantau Azure berbeza tidak disokong.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="2f7ed-114">Untuk mengetahui rantau Azure persekitaran, pergi ke **Pentadbir** > **Sistem** > **Perihal** dalam cerapan khalayak.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="2f7ed-115">Data disimpan dalam perkhidmatan dalam talian, mungkin disimpan di lokasi lain daripada tempat data diproses atau disimpan dalam Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="2f7ed-116">Dengan mengimport atau menyambung kepada data yang disimpan dalam perkhidmatan dalam talian, anda bersetuju bahawa data boleh dipindahkan ke dan disimpan dengan Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat Amanah Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="2f7ed-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="2f7ed-117">Sambungkan ke folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="2f7ed-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="2f7ed-118">Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="2f7ed-119">Pilih **Tambah sumber data**.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="2f7ed-120">Pilih **Sambung ke folder Common Data Model**, masukkan **Nama** untuk sumber data dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="2f7ed-121">Namakan garis panduan:</span><span class="sxs-lookup"><span data-stu-id="2f7ed-121">Name guidelines:</span></span> 
   - <span data-ttu-id="2f7ed-122">Bermula dengan huruf.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-122">Start with a letter.</span></span>
   - <span data-ttu-id="2f7ed-123">Gunakan huruf dan nombor sahaja.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-123">Use letters and numbers only.</span></span> <span data-ttu-id="2f7ed-124">Aksara khas dan ruang idak dibenarkan.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="2f7ed-125">Gunakan antara 3 dan 64 aksara.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="2f7ed-126">Anda boleh memilih antara pilihan berasaskan sumber dan pilihan berasaskan langganan untuk pengesahan.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="2f7ed-127">Untuk maklumat lanjut, lihat [Sambungkan cerapan khalayak ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="2f7ed-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="2f7ed-128">Masukkan maklumat **Bekas** dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2f7ed-129">![Kotak dialog untuk memasukkan butiran sambungan baharu untuk Data Lake Azure](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="2f7ed-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="2f7ed-130">Anda memerlukan salah satu peranan yang berikut sama ada kepada bekas atau akaun storan yang dirujuk di atas untuk bersambung kepada dan mencipta sumber data:</span><span class="sxs-lookup"><span data-stu-id="2f7ed-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="2f7ed-131">Pembaca Data Blob Storan</span><span class="sxs-lookup"><span data-stu-id="2f7ed-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="2f7ed-132">Pemilik Data Blob Storan</span><span class="sxs-lookup"><span data-stu-id="2f7ed-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="2f7ed-133">Penyumbang Blob Data Storan</span><span class="sxs-lookup"><span data-stu-id="2f7ed-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="2f7ed-134">Dalam dialog **Pilih folder Common Data Model**, pilih fail model.json atau manifest.json untuk mengimport data daripada, dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="2f7ed-135">Sebarang fail model.json atau manifest.json yang berkaitan dengan sumber data lain dalam persekitaran tidak akan ditunjukkan dalam senarai.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="2f7ed-136">Anda akan mendapat senarai entiti yang tersedia dalam fail model.json atau manifest.json yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="2f7ed-137">Anda boleh menyemak semula dan memilih daripada senarai entiti yang tersedia dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="2f7ed-138">Semua entiti yang dipilih akan dinges daripada sumber data baharu.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2f7ed-139">![Kotak dialog yang menunjukkan senarai entiti daripada fail model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="2f7ed-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="2f7ed-140">Menunjukkan entiti data yang mahu anda dayakan pemprofilan data dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="2f7ed-141">Pemprofilan data membolehkan analitis dan keupayaan lain.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="2f7ed-142">Anda boleh memilih keseluruhan entiti yang memilih semua atribut daripada entiti atau memilih sifat tertentu pilihan anda.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="2f7ed-143">Secara lalai, tiada entiti didayakan untuk pemprofilan data.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2f7ed-144">![Kotak dialog menunjukkan pemprofilan data](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="2f7ed-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="2f7ed-145">Selepas menyimpan pilihan anda, halaman **Sumber data** dibuka.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="2f7ed-146">Kini anda patut melihat sambungan folder Common Data Model sebagai sumber data.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="2f7ed-147">Fail model.json atau manifest.json hanya boleh mengaitkan dengan satu sumber data dalam persekitaran yang sama.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="2f7ed-148">Walau bagaimanapun, fail model.json atau manifest.json boleh digunakan untuk sumber data dalam berbilang persekitaran.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="2f7ed-149">Edit sumber data folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="2f7ed-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="2f7ed-150">Anda boleh mengemas kini kekunci akses untuk akaun storan yang mengandungi folder Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="2f7ed-151">Anda juga boleh mengubah fail model.json atau manifest.json.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="2f7ed-152">Untuk menyambung kepada bekas berbeza daripada akaun storan anda, atau mengubah nama akaun, [mencipta sambungan sumber data baharu](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="2f7ed-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="2f7ed-153">Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="2f7ed-154">Bersebelahan dengan sumber data yang anda mahu kemas kini, pilih elipsis.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="2f7ed-155">Pilih pilihan **Edit** daripada senarai.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="2f7ed-156">Secara alternatif, kemas kini **Kunci akses** dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialog untuk mengedit dan mengemas kini kekunci akses untuk sumber data sedia ada](media/edit-access-key.png)

5. <span data-ttu-id="2f7ed-158">Secara alternatif, anda boleh mengemas kini dari sambungan utama akaun kepada sambungan berasaskan sumber atau langganan.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="2f7ed-159">Untuk maklumat lanjut, lihat [Sambungkan cerapan khalayak ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="2f7ed-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="2f7ed-160">Anda tidak boleh mengubah maklumat **Bekas** semasa mengemas kini sambungan.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Kotak dialog untuk memasukkan butiran sambungan untuk Data Lake Azure ke akaun storan sedia ada](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="2f7ed-162">Anda memerlukan salah satu peranan yang berikut sama ada kepada bekas atau akaun storan yang dirujuk di atas untuk bersambung kepada dan mencipta sumber data:</span><span class="sxs-lookup"><span data-stu-id="2f7ed-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="2f7ed-163">Pembaca Data Blob Storan</span><span class="sxs-lookup"><span data-stu-id="2f7ed-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="2f7ed-164">Pemilik Data Blob Storan</span><span class="sxs-lookup"><span data-stu-id="2f7ed-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="2f7ed-165">Penyumbang Blob Data Storan</span><span class="sxs-lookup"><span data-stu-id="2f7ed-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="2f7ed-166">Secara alternatif, pilih fail model.json atau manifest.json lainl dengan set entiti yang berbeza daripada bekas.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="2f7ed-167">Secara alternatif, anda boleh memilih entiti tambahan untuk diinges.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="2f7ed-168">Anda juga boleh mengalih keluar sebarang entiti yang sudah dipilih jika tiada kebergantungan.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="2f7ed-169">Jika terdapat pergantungan pada fail model.json atau manifest.json sedia ada dan set entiti, anda akan melihat mesej ralat dan tidak boleh memilih fail model.json atau manifest.json yang berbeza.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="2f7ed-170">Keluarkan kebergantungan sebelum mengubah fail model.json atau manifest.json atau cipta sumber data baharu dengan fail model.json atau manifest.json yang anda mahu gunakan untuk mengelakkan daripada mengeluarkan kebergantungan.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="2f7ed-171">Secara alternatif, anda boleh memilih atribut atau entiti tambahan untuk mendayakan pemprofilan data atau menyahdayakan yang sudah dipilih.</span><span class="sxs-lookup"><span data-stu-id="2f7ed-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]