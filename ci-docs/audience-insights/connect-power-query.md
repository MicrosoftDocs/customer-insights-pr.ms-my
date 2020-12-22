---
title: Inges data melalui penyambung Power Query
description: Penyambung untuk sumber data berdasarkan Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406458"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="85cc2-103">Sambung kepada sumber data Power Query</span><span class="sxs-lookup"><span data-stu-id="85cc2-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="85cc2-104">Power Query menawarkan set sambungan yang luas kepada data yang paling.</span><span class="sxs-lookup"><span data-stu-id="85cc2-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="85cc2-105">Kebanyakan penyambung ini disokong oleh Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="85cc2-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="85cc2-106">Menambahkan sumber data berdasarkan penyambung Power Query secara amnya mengikut langkah yang digariskan dalam bahagian seterusnya.</span><span class="sxs-lookup"><span data-stu-id="85cc2-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="85cc2-107">Walau bagaimanapun, bergantung pada penyambung yang anda gunakan, maklumat berbeza diperlukan.</span><span class="sxs-lookup"><span data-stu-id="85cc2-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="85cc2-108">Untuk mendapatkan maklumat lanjut, lihat dokumentasi mengenai penyambung individu dalam [rujukan penyambung Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="85cc2-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="85cc2-109">Cipta sumber data baharu</span><span class="sxs-lookup"><span data-stu-id="85cc2-109">Create a new data source</span></span>

1. <span data-ttu-id="85cc2-110">Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="85cc2-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="85cc2-111">Pilih **Tambah sumber data**.</span><span class="sxs-lookup"><span data-stu-id="85cc2-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="85cc2-112">Pilih kaedah **Import data** dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="85cc2-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="85cc2-113">Berikan **Nama** untuk sumber data dan pilih **Seterusnya** untuk mencipta sumber data.</span><span class="sxs-lookup"><span data-stu-id="85cc2-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="85cc2-114">Pilih salah satu [penyambung yang tersedia](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="85cc2-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="85cc2-115">Untuk contoh ini, kami pilih penyambung **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="85cc2-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="85cc2-116">Masukkan butiran yang diperlukan dalam **Tetapan sambungan** untuk penyambung yang dipilih dan pilih **Seterusnya** untuk melihat pratonton data.</span><span class="sxs-lookup"><span data-stu-id="85cc2-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="85cc2-117">Pilih **Ubah data**.</span><span class="sxs-lookup"><span data-stu-id="85cc2-117">Select **Transform data**.</span></span> <span data-ttu-id="85cc2-118">Dalam langkah ini, anda akan tambahkan entiti pada sumber data anda.</span><span class="sxs-lookup"><span data-stu-id="85cc2-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="85cc2-119">Entiti adalah set data.</span><span class="sxs-lookup"><span data-stu-id="85cc2-119">Entities are datasets.</span></span> <span data-ttu-id="85cc2-120">Jika anda mempunyai pangkalan data yang merangkumi set data berbilang, setiap set data adalah entiti sendiri.</span><span class="sxs-lookup"><span data-stu-id="85cc2-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="85cc2-121">Dialog **Power Query - Edit pertanyaan** membolehkan anda menyemak semula dan memperhalusi data.</span><span class="sxs-lookup"><span data-stu-id="85cc2-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="85cc2-122">Entiti yang dikenal pasti sistem dalam sumber data terpilih anda muncul dalam anak tetingkap kiri.</span><span class="sxs-lookup"><span data-stu-id="85cc2-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="85cc2-123">![Edit dialog pertanyaan](media/data-manager-configure-edit-queries.png "Edit dialog pertanyaan")</span><span class="sxs-lookup"><span data-stu-id="85cc2-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="85cc2-124">Anda juga boleh mengubah data anda.</span><span class="sxs-lookup"><span data-stu-id="85cc2-124">You can also transform your data.</span></span> <span data-ttu-id="85cc2-125">Pilih entiti untuk mengedit atau mengubah.</span><span class="sxs-lookup"><span data-stu-id="85cc2-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="85cc2-126">Gunakan pilihan dalam tetingkap Power Query untuk menggunakan transformasi.</span><span class="sxs-lookup"><span data-stu-id="85cc2-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="85cc2-127">Setiap transformasi akan disenaraikan di bawah **Langkah yang digunakan**.</span><span class="sxs-lookup"><span data-stu-id="85cc2-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="85cc2-128">Power Query menyediakan pelbagai pilihan transformasi yang dibina terlebih dahulu.</span><span class="sxs-lookup"><span data-stu-id="85cc2-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="85cc2-129">Untuk maklumat lebih lanjut, lihat [Transformasi Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="85cc2-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="85cc2-130">Anda boleh tambah entiti tambahan ke sumber data anda dengan memilih **Dapatkan data** di dalam dialog **Edit pertanyaan**.</span><span class="sxs-lookup"><span data-stu-id="85cc2-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="85cc2-131">Transformasi ini amat disyorkan:</span><span class="sxs-lookup"><span data-stu-id="85cc2-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="85cc2-132">Jika anda sedang mengambil data dari fail CSV, baris pertama selalunya mengandungi tajuk.</span><span class="sxs-lookup"><span data-stu-id="85cc2-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="85cc2-133">Pergi ke **Ubah jadual** dan pilih **Gunakan pengepala sebagai baris pertama**.</span><span class="sxs-lookup"><span data-stu-id="85cc2-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="85cc2-134">Pastikan jenis data ditetapkan dengan sewajarnya.</span><span class="sxs-lookup"><span data-stu-id="85cc2-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="85cc2-135">Pilih **Simpan** di bahagian bawah tetingkap Power Query untuk menyimpan transformasi.</span><span class="sxs-lookup"><span data-stu-id="85cc2-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="85cc2-136">Selepas menyimpan, anda akan dapati sumber data anda pada **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="85cc2-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="85cc2-137">Pada halaman **Sumber data**, anda akan dapati sumber data baharu berada dalam status **Segar semula**.</span><span class="sxs-lookup"><span data-stu-id="85cc2-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="85cc2-138">Sedia sumber data Power Query</span><span class="sxs-lookup"><span data-stu-id="85cc2-138">Available Power Query data sources</span></span>

<span data-ttu-id="85cc2-139">Lihat [Rujukan penyambung Power Query](https://docs.microsoft.com/power-query/connectors/) untuk senarai penyambung terkini yang boleh anda pilih untuk mengimport data pada Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="85cc2-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="85cc2-140">Penyambung dengan tanda semak dalam lajur **Customer Insights (Alir data)** tersedia untuk mencipta sumber data baharu berdasarkan Power query.</span><span class="sxs-lookup"><span data-stu-id="85cc2-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="85cc2-141">Semak semula dokumentasi bagi penyambung khusus untuk mengetahui lebih lanjut tentang prasyarat, had dan butiran lain.</span><span class="sxs-lookup"><span data-stu-id="85cc2-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="85cc2-142">Edit sumber data Power Query</span><span class="sxs-lookup"><span data-stu-id="85cc2-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="85cc2-143">Ia mungkin tidak mustahil untuk membuat perubahan kepada sumber data yang sedang digunakan dalam salah satu proses aplikasi (contohnya *pembahagian*, *padanan* atau *penggabungan*).</span><span class="sxs-lookup"><span data-stu-id="85cc2-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="85cc2-144">Menggunakan halaman **Tetapan**, anda boleh menjejaki perkembangan setiap proses aktif.</span><span class="sxs-lookup"><span data-stu-id="85cc2-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="85cc2-145">Apabila proses selesai, anda boleh kembali ke halaman **Sumber Data** dan membuat perubahan anda.</span><span class="sxs-lookup"><span data-stu-id="85cc2-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="85cc2-146">Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="85cc2-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="85cc2-147">Pilih elipsis menegak bersebelahan dengan sumber data yang anda mahu tukar dan pilih **Edit** daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="85cc2-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="85cc2-148">![Edit pilihan](media/edit-option-data-sources.png "Edit pilihan")</span><span class="sxs-lookup"><span data-stu-id="85cc2-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="85cc2-149">Gunakan perubahan dan transformasi anda dalam dialog **Power Query - Edit pertanyaan** seperti yang diterangkan dalam bahagian [Cipta bahagian sumber data baharu](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="85cc2-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="85cc2-150">Pilih **Simpan** dalam Power Query selepas melengkapkan pengeditan anda untuk menyimpan perubahan anda.</span><span class="sxs-lookup"><span data-stu-id="85cc2-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
