---
title: Aktiviti pelanggan
description: Tentukan aktiviti pelanggan dan lihat aktiviti tersebut dalam garis masa pelanggan.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866418"
---
# <a name="customer-activities"></a><span data-ttu-id="9b061-103">Aktiviti pelanggan</span><span class="sxs-lookup"><span data-stu-id="9b061-103">Customer activities</span></span>

<span data-ttu-id="9b061-104">Gabungkan aktiviti pelanggan daripada [pelbagai sumber data](data-sources.md) dalam Dynamics 365 Customer Insights untuk mencipta garis masa yang menyenaraikan aktiviti secara kronologi.</span><span class="sxs-lookup"><span data-stu-id="9b061-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="9b061-105">Sertakan garis masa dalam aplikasi Dynamics 365 dengan penyelesaian [Kad Pelanggan tambahan](customer-card-add-in.md) atau dalam papan pemuka Power BI.</span><span class="sxs-lookup"><span data-stu-id="9b061-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="9b061-106">Takrifkan aktiviti</span><span class="sxs-lookup"><span data-stu-id="9b061-106">Define an activity</span></span>

<span data-ttu-id="9b061-107">Sumber data anda boleh termasuk entiti dengan data transaksi dan aktiviti daripada berbilang sumber data.</span><span class="sxs-lookup"><span data-stu-id="9b061-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="9b061-108">Kenal pasti entiti ini dan pilih aktiviti yang anda mahu lihat pada garis masa pelanggan.</span><span class="sxs-lookup"><span data-stu-id="9b061-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="9b061-109">Pilih entiti yang mengandungi sasaran aktiviti atau aktiviti anda.</span><span class="sxs-lookup"><span data-stu-id="9b061-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="9b061-110">Entiti mesti mempunyai sekurang-kurangnya satu atribut jenis **Tarikh** yang akan dimasukkan dalam garis masa pelanggan dan anda tidak boleh menambah entiti tanpa medan **Tarikh**.</span><span class="sxs-lookup"><span data-stu-id="9b061-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="9b061-111">Kawalan **Tambah aktiviti** dinyahdayakan jika tiada entiti sedemikian ditemui.</span><span class="sxs-lookup"><span data-stu-id="9b061-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="9b061-112">Dalam wawasan khalayak, pergi ke **Data** > **Aktiviti**.</span><span class="sxs-lookup"><span data-stu-id="9b061-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="9b061-113">Pilih **Tambah aktiviti** untuk memulakan pengalaman berpandu untuk proses persediaan aktiviti.</span><span class="sxs-lookup"><span data-stu-id="9b061-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="9b061-114">Dalam langkah **Data aktiviti**, tetapkan nilai untuk medan berikut:</span><span class="sxs-lookup"><span data-stu-id="9b061-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="9b061-115">**Nama aktiviti**: Pilih nama untuk aktiviti anda.</span><span class="sxs-lookup"><span data-stu-id="9b061-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="9b061-116">**Entiti**: Pilih entiti yang mengandungi data transaksi atau aktiviti.</span><span class="sxs-lookup"><span data-stu-id="9b061-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="9b061-117">**Perkara utama**: Pilih medan yang mengenal pasti rekod secara unik.</span><span class="sxs-lookup"><span data-stu-id="9b061-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="9b061-118">Ia tidak seharusnya mengandungi sebarang nilai duplikasi, nilai kosong atau kehilangan nilai.</span><span class="sxs-lookup"><span data-stu-id="9b061-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Sediakan data aktiviti dengan nama, entiti dan kekunci utama.":::

1. <span data-ttu-id="9b061-120">Pilih **Seterusnya** untuk pergi ke langkah seterusnya.</span><span class="sxs-lookup"><span data-stu-id="9b061-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="9b061-121">Dalam langkah **Perhubungan**, konfigurasikan butiran untuk menyambungkan data aktiviti anda kepada pelanggan yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="9b061-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="9b061-122">Langkah ini menggambarkan sambungan antara entiti.</span><span class="sxs-lookup"><span data-stu-id="9b061-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="9b061-123">**Pertama**: Medan asing dalam entiti aktiviti anda yang akan digunakan untuk mewujudkan perhubungan dengan entiti lain.</span><span class="sxs-lookup"><span data-stu-id="9b061-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="9b061-124">**Kedua**: Entiti pelanggan sumber yang sepadan dengan entiti aktiviti anda yang akan berada dalam perhubungan.</span><span class="sxs-lookup"><span data-stu-id="9b061-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="9b061-125">Anda hanya boleh dikaitkan dengan entiti pelanggan sumber yang digunakan dalam proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="9b061-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="9b061-126">**Ketiga**: Jika perhubungan antara entiti aktiviti ini dan entiti pelanggan sumber yang dipilih telah wujud, nama perhubungan akan berada dalam mod baca sahaja.</span><span class="sxs-lookup"><span data-stu-id="9b061-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="9b061-127">Jika tiada perhubungan sedemikian wujud, perhubungan baharu akan dicipta dengan nama yang anda berikan dalam kotak ini.</span><span class="sxs-lookup"><span data-stu-id="9b061-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Takrifkan perhubungan entiti.":::

1. <span data-ttu-id="9b061-129">Pilih **Seterusnya** untuk pergi ke langkah seterusnya.</span><span class="sxs-lookup"><span data-stu-id="9b061-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="9b061-130">Dalam langkah **Penyatuan aktiviti**, pilih peristiwa aktiviti dan masa mula aktiviti anda.</span><span class="sxs-lookup"><span data-stu-id="9b061-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="9b061-131">**Medan diperlukan**</span><span class="sxs-lookup"><span data-stu-id="9b061-131">**Required fields**</span></span>
      1. <span data-ttu-id="9b061-132">**Aktiviti peristiwa**: Medan untuk peristiwa bagi aktiviti ini</span><span class="sxs-lookup"><span data-stu-id="9b061-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="9b061-133">**Cap waktu**: Medan yang mewakili masa mula aktiviti anda.</span><span class="sxs-lookup"><span data-stu-id="9b061-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="9b061-134">**Medan pilihan**</span><span class="sxs-lookup"><span data-stu-id="9b061-134">**Optional fields**</span></span>
      1. <span data-ttu-id="9b061-135">**Butiran tambahan**: Medan dengan maklumat berkaitan untuk aktiviti ini.</span><span class="sxs-lookup"><span data-stu-id="9b061-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="9b061-136">**Ikon**: Ikon yang terbaik mewakili jenis aktiviti ini.</span><span class="sxs-lookup"><span data-stu-id="9b061-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="9b061-137">**Alamat web**: Medan yang mengandungi URL dengan maklumat tentang aktiviti ini.</span><span class="sxs-lookup"><span data-stu-id="9b061-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="9b061-138">Contohnya, sistem transaksi yang memberi sumber untuk aktiviti ini.</span><span class="sxs-lookup"><span data-stu-id="9b061-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="9b061-139">URL ini boleh menjadi mana-mana medan daripada sumber data atau ia boleh dibina sebagai medan baharu menggunakan perubahan Pertanyaan Kuasa.</span><span class="sxs-lookup"><span data-stu-id="9b061-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="9b061-140">Data URL akan disimpan dalam entiti *Aktiviti yang Disatukan* yang boleh digunakan secara hiliran menggunakan [API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="9b061-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Tentukan data aktiviti pelanggan dalam entiti Aktiviti yang Disatukan.":::

1. <span data-ttu-id="9b061-142">Pilih **Seterusnya** untuk beralih ke langkah yang seterusnya.</span><span class="sxs-lookup"><span data-stu-id="9b061-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="9b061-143">Anda boleh memilih **Selesai dan semak** untuk menyimpan aktiviti sekarang dengan jenis aktiviti yang ditetapkan kepada **Lain-lain**.</span><span class="sxs-lookup"><span data-stu-id="9b061-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="9b061-144">Dalam langkah **Jenis Aktiviti**, pilih jenis aktiviti dan secara pilihan, pilih jika anda mahu memetakan secara semantik sebahagian daripada jenis aktiviti untuk digunakan dalam bahagian lain dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9b061-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="9b061-145">Pada masa ini, jenis aktiviti *Langganan* & *SalesOrderLine* boleh dipetakan secara semantik selepas bersetuju untuk memetakan petak.</span><span class="sxs-lookup"><span data-stu-id="9b061-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="9b061-146">Jika jenis aktiviti tidak berkaitan dengan aktiviti baharu, anda boleh memilih *Lain-lain* atau *Cipta baharu* untuk jenis aktiviti yang tersuai.</span><span class="sxs-lookup"><span data-stu-id="9b061-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="9b061-147">Pilih **Seterusnya** untuk beralih ke langkah yang seterusnya.</span><span class="sxs-lookup"><span data-stu-id="9b061-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="9b061-148">Dalam langkah **Semak**, sahkan pilihan anda.</span><span class="sxs-lookup"><span data-stu-id="9b061-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="9b061-149">Anda kembali ke mana-mana langkah sebelumnya dan mengemas kini maklumat jika perlu.</span><span class="sxs-lookup"><span data-stu-id="9b061-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Semak medan khusus untuk aktiviti.":::
   
1. <span data-ttu-id="9b061-151">Pilih **Simpan aktiviti** untuk menggunakan perubahan anda dan pilih **Selesai** untuk kembali ke **Data** > **Aktiviti**.</span><span class="sxs-lookup"><span data-stu-id="9b061-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="9b061-152">Di sini, anda melihat aktiviti yang ditetapkan untuk ditunjukkan dalam garis masa.</span><span class="sxs-lookup"><span data-stu-id="9b061-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="9b061-153">Pada halaman **Aktiviti**, pilih **Jalankan** untuk memproses aktiviti.</span><span class="sxs-lookup"><span data-stu-id="9b061-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="9b061-154">Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="9b061-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="9b061-155">Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="9b061-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="9b061-156">Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja.</span><span class="sxs-lookup"><span data-stu-id="9b061-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="9b061-157">Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="9b061-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="9b061-158">Urus aktiviti sedia ada</span><span class="sxs-lookup"><span data-stu-id="9b061-158">Manage existing activities</span></span>

<span data-ttu-id="9b061-159">Pada **Data** > **Aktiviti**, anda boleh melihat semua aktiviti yang disimpan dan menguruskannya.</span><span class="sxs-lookup"><span data-stu-id="9b061-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="9b061-160">Setiap aktiviti diwakili oleh baris yang juga termasuk butiran mengenai sumber, entiti dan jenis aktiviti.</span><span class="sxs-lookup"><span data-stu-id="9b061-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="9b061-161">Tindakan berikut tersedia apabila anda memilih aktiviti.</span><span class="sxs-lookup"><span data-stu-id="9b061-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="9b061-162">**Edit**: Buka persediaan aktiviti pada langkah tinjauan.</span><span class="sxs-lookup"><span data-stu-id="9b061-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="9b061-163">Anda boleh mengubah sebarang atau semua konfigurasi semasa daripada langkah ini.</span><span class="sxs-lookup"><span data-stu-id="9b061-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="9b061-164">Selepas mengubah konfigurasi, pilih **Simpan aktiviti** dan kemudian pilih **Jalankan** untuk memproses perubahan.</span><span class="sxs-lookup"><span data-stu-id="9b061-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="9b061-165">**Namakan semula**: Buka dialog di tempat untuk memasukkan nama lain untuk aktiviti yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="9b061-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="9b061-166">Pilih **Simpan** untuk menggunakan perubahan anda.</span><span class="sxs-lookup"><span data-stu-id="9b061-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="9b061-167">**Padam**: Buka dialog untuk mengesahkan pemadaman aktiviti yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="9b061-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="9b061-168">Anda juga boleh memadamkan lebih daripada satu aktiviti sekaligus dengan memilih aktiviti dan kemudian memilih ikon padam.</span><span class="sxs-lookup"><span data-stu-id="9b061-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="9b061-169">Pilih **Padam** untuk mengesahkan pemadaman.</span><span class="sxs-lookup"><span data-stu-id="9b061-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
