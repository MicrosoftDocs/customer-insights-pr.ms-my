---
title: Aktiviti pelanggan
description: Tentukan aktiviti pelanggan dan lihat aktiviti tersebut dalam garis masa pelanggan.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667240"
---
# <a name="customer-activities"></a><span data-ttu-id="3c4f1-103">Aktiviti pelanggan</span><span class="sxs-lookup"><span data-stu-id="3c4f1-103">Customer activities</span></span>

<span data-ttu-id="3c4f1-104">Gabungkan aktiviti pelanggan daripada [pelbagai sumber data](data-sources.md) dalam Dynamics 365 Customer Insights untuk mencipta garis masa pelanggan yang menyenaraikan aktiviti dalam susunan kronologi.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="3c4f1-105">Anda boleh memasukkan garis masa dalam aplikasi penglibatan pelanggan dalam Dynamics 365 menerusi [tambahan Kad Pelanggan](customer-card-add-in.md), atau dalam papan pemuka Power BI.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="3c4f1-106">Takrifkan aktiviti</span><span class="sxs-lookup"><span data-stu-id="3c4f1-106">Define an activity</span></span>

<span data-ttu-id="3c4f1-107">Sumber data anda termasuk entiti dengan data transaksi dan aktiviti daripada sumber data berbilang.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="3c4f1-108">Kenal pasti entiti ini dan pilih aktiviti yang anda mahu lihat pada garis masa pelanggan.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="3c4f1-109">Pilih entiti yang mengandungi sasaran aktiviti atau aktiviti anda.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="3c4f1-110">Dalam wawasan khalayak, pergi ke **Data** > **Aktiviti**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="3c4f1-111">Pilih **Tambah aktiviti**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3c4f1-112">Entiti mesti mempunyai sekurang-kurangnya satu atribut jenis **Tarikh** yang akan dimasukkan dalam garis masa pelanggan dan anda tidak boleh menambah entiti tanpa medan **Tarikh**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="3c4f1-113">Kawalan **Tambah aktiviti** dinyahdayakan jika tiada entiti sedemikian ditemui.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="3c4f1-114">Dalam anak tetingkap **Tambah aktiviti**, tetapkan nilai untuk medan berikut:</span><span class="sxs-lookup"><span data-stu-id="3c4f1-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="3c4f1-115">**Entiti**: Pilih entiti yang mengandungi data transaksi atau aktiviti.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="3c4f1-116">**Perkara utama**: Pilih medan yang mengenal pasti rekod secara unik.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="3c4f1-117">Ia tidak seharusnya mengandungi sebarang nilai duplikasi, nilai kosong atau kehilangan nilai.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="3c4f1-118">**Cap masa**: Pilih medan yang mewakili masa mula aktiviti anda.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="3c4f1-119">**Peristiwa**: Pilih medan yang merupakan peristiwa untuk aktiviti tersebut.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="3c4f1-120">**Alamat web**: Pilih medan yang mewakili URL yang menyediakan maklumat tambahan tentang aktiviti ini.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="3c4f1-121">Contohnya, sistem transaksi yang memberi sumber untuk aktiviti ini.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="3c4f1-122">URL ini boleh menjadi mana-mana medan daripada sumber data atau ia boleh dibina sebagai medan baharu menggunakan perubahan Pertanyaan Kuasa.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="3c4f1-123">Data URL akan disimpan dalam entiti Aktiviti Disatukan, yang menjadi hiliran yang digunakan menggunakan API.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="3c4f1-124">**Butiran**: Secara pilihan, pilih medan yang ditambah untuk butiran tambahan.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="3c4f1-125">**Ikon**: Secara pilihan, pilih ikon yang mewakili aktiviti ini.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="3c4f1-126">**Jenis Aktiviti**: Takrifkan rujukan jenis aktiviti untuk Model Data Biasa yang menghuraikan sebaiknya takrifan semantik aktiviti.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="3c4f1-127">Dalam bahagian **Persediaan perhubungan**, butiran dikonfigurasi untuk menyambungkan data aktiviti anda kepada pelanggan yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c4f1-128">![Takrifkan perhubungan entiti](media/activities-entities-define.png "Takrifkan perhubungan entiti")</span><span class="sxs-lookup"><span data-stu-id="3c4f1-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="3c4f1-129">**Medan entiti aktiviti**: Pilih medan dalam entiti aktiviti anda yang akan digunakan untuk mewujudkan perhubungan dengan entiti lain.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="3c4f1-130">**Entiti pelanggan** : Pilih entiti pelanggan sumber berkaitan dengan entiti aktiviti anda akan berada dalam perhubungan.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="3c4f1-131">Anda hanya boleh mengaitkan dengan entiti pelanggan sumber yang digunakan dalam proses data penyatuan.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="3c4f1-132">**Medan entiti pelanggan**: Medan ini menunjukkan kunci utama bagi entiti pelanggan sumber seperti yang dipilih dalam proses peta.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="3c4f1-133">Medan kunci utama dalam entiti pelanggan sumber ini digunakan untuk mewujudkan perhubungan dengan entiti aktiviti.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="3c4f1-134">**Nama**: Jika perhubungan antara entiti aktiviti ini dan entiti pelanggan sumber yang terpilih telah wujud, nama perhubungan akan berada dalam mod baca sahaja.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="3c4f1-135">Jika tiada hubungan sedemikian wujud, perhubungan baharu akan dicipta dengan nama yang disediakan di sini.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="3c4f1-136">Pilih **Simpan** untuk menggunakan perubahan anda.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="3c4f1-137">Pada halaman **Aktiviti**, pilih **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="3c4f1-138">Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3c4f1-139">Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="3c4f1-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3c4f1-140">Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3c4f1-141">Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="3c4f1-142">Edit aktiviti</span><span class="sxs-lookup"><span data-stu-id="3c4f1-142">Edit an activity</span></span>

1. <span data-ttu-id="3c4f1-143">Dalam wawasan khalayak, pergi ke **Data** > **Aktiviti**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="3c4f1-144">Pilih entiti aktiviti yang anda mahu edit dan pilih **Edit**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="3c4f1-145">Atau, anda boleh hover pada baris entiti dan pilih ikon **Edit**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="3c4f1-146">Klik pada ikon **Edit**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="3c4f1-147">Dalam anak tetingkap **Edit aktiviti**, kemas kini nilai dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="3c4f1-148">Pada halaman **Aktiviti**, pilih **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="3c4f1-149">Padam aktiviti</span><span class="sxs-lookup"><span data-stu-id="3c4f1-149">Delete an activity</span></span>

1. <span data-ttu-id="3c4f1-150">Dalam wawasan khalayak, pergi ke **Data** > **Aktiviti**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="3c4f1-151">Pilih entiti aktiviti yang anda mahu alih keluar dan pilih **Padam**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="3c4f1-152">Atau, anda boleh hover pada baris entiti dan pilih ikon **Padam**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="3c4f1-153">Selain itu, anda boleh memilih entiti aktiviti berbilang untuk dipadam serentak.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c4f1-154">![Edit atau padam perhubungan entiti](media/activities-entities-edit-delete.png "Edit atau padam perhubungan entiti.").</span><span class="sxs-lookup"><span data-stu-id="3c4f1-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="3c4f1-155">Pilih pada ikon **Padam**.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="3c4f1-156">Sahkan pemadaman anda.</span><span class="sxs-lookup"><span data-stu-id="3c4f1-156">Confirm your deletion.</span></span>
