---
title: Entiti dan set data
description: Lihat data pada halaman Entiti.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406445"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="317b1-103">Entiti dalam wawasan khalayak</span><span class="sxs-lookup"><span data-stu-id="317b1-103">Entities in audience insights</span></span>

<span data-ttu-id="317b1-104">Selepas [mengkonfigurasi sumber data anda](data-sources.md), pergi ke halaman **Entiti** untuk menilai kualiti data yang dimasukkan.</span><span class="sxs-lookup"><span data-stu-id="317b1-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="317b1-105">Entiti dianggap sebagai set data.</span><span class="sxs-lookup"><span data-stu-id="317b1-105">Entities are considered datasets.</span></span> <span data-ttu-id="317b1-106">Berbilang keupayaan Dynamics 365 Customer Insights dibina sekitar entiti ini.</span><span class="sxs-lookup"><span data-stu-id="317b1-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="317b1-107">Mengkajinya semula dengan teliti boleh membantu anda mengesahkan output keupayaan tersebut.</span><span class="sxs-lookup"><span data-stu-id="317b1-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="317b1-108">Halaman **Entiti** menyenaraikan entiti dan termasuk beberapa lajur:</span><span class="sxs-lookup"><span data-stu-id="317b1-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="317b1-109">**Nama**: Nama entiti data anda.</span><span class="sxs-lookup"><span data-stu-id="317b1-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="317b1-110">Jika anda nampak simbol amaran di sebelah nama entiti, ia bermaksud data untuk entiti tersebut tidak berjaya dimuatkan.</span><span class="sxs-lookup"><span data-stu-id="317b1-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="317b1-111">**Sumber**: Jenis sumber data yang memasukkan entiti</span><span class="sxs-lookup"><span data-stu-id="317b1-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="317b1-112">**Dicipta oleh**: Nama orang yang mencipta entiti</span><span class="sxs-lookup"><span data-stu-id="317b1-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="317b1-113">**Dicipta**: Tarikh dan masa penciptaan entiti</span><span class="sxs-lookup"><span data-stu-id="317b1-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="317b1-114">**Dikemas kini oleh**: Nama orang yang mengemas kini entiti</span><span class="sxs-lookup"><span data-stu-id="317b1-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="317b1-115">**Kemas kini terakhir**: Tarikh dan masa kemas kini yang terakhir bagi entiti</span><span class="sxs-lookup"><span data-stu-id="317b1-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="317b1-116">**Segar semula terakhir**: Tarikh dan masa data terakhir segar semula</span><span class="sxs-lookup"><span data-stu-id="317b1-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="317b1-117">Menerokai data entiti khusus</span><span class="sxs-lookup"><span data-stu-id="317b1-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="317b1-118">Pilih entiti untuk menerokai medan dan rekod yang berbeza termasuk dalam entiti tersebut.</span><span class="sxs-lookup"><span data-stu-id="317b1-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="317b1-119">![Pilih entiti](media/data-manager-entities-data.png "Pilih entiti")</span><span class="sxs-lookup"><span data-stu-id="317b1-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="317b1-120">Tab **Data** dipilih secara lalai dan menunjukkan butiran penyenaraian jadual mengenai rekod individu entiti.</span><span class="sxs-lookup"><span data-stu-id="317b1-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="317b1-121">![Jadual medan](media/data-manager-entities-fields.PNG "Jadual medan")</span><span class="sxs-lookup"><span data-stu-id="317b1-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="317b1-122">Tab **Medan** menunjukkan jadual untuk mengkaji semula butiran entiti yang dipilih, seperti nama medan, jenis data dan jenis.</span><span class="sxs-lookup"><span data-stu-id="317b1-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="317b1-123">Lajur **Jenis** menunjukkan jenis berkaitan Model Data Lazim, yang mana sama ada dikenal pasti secara automatik oleh sistem atau [dipetakan secara manual](map-entities.md) oleh pengguna.</span><span class="sxs-lookup"><span data-stu-id="317b1-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="317b1-124">Ini ialah jenis semantik yang mungkin berbeza daripada jenis data atribut—contohnya, medan *e-mel* di bawah mempunyai jenis data *Teks* tetapi jenis Model Data Lazim (semantik) berkemungkinan *E-mel* atau *AlamatE-mel*.</span><span class="sxs-lookup"><span data-stu-id="317b1-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="317b1-125">Kedua-dua jadual menunjukkan hanya sampel data entiti anda.</span><span class="sxs-lookup"><span data-stu-id="317b1-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="317b1-126">Untuk melihat set data lengkap, pergi ke halaman **Sumber data**, pilih entiti, pilih **Edit** dan lihat data entiti ini dengan editor Power Query seperti yang diterangkan dalam [Sumber data](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="317b1-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="317b1-127">Untuk mengetahui lebih lanjut tentang data yang dimasukkan di dalam entiti, lajur **Ringkasan** menyediakan anda dengan beberapa ciri penting data seperti batal, nilai yang hilang, nilai unik, kiraan dan pengagihan, sebagaimana berkaitan dengan data anda.</span><span class="sxs-lookup"><span data-stu-id="317b1-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="317b1-128">Pilih ikon carta untuk melihat ringkasan data.</span><span class="sxs-lookup"><span data-stu-id="317b1-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="317b1-129">![Simbol ringkasan](media/data-manager-entities-summary.png "Jadual ringkasan data")</span><span class="sxs-lookup"><span data-stu-id="317b1-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="317b1-130">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="317b1-130">Next step</span></span>

<span data-ttu-id="317b1-131">Lihat topik [Menyatukan](data-unification.md) untuk mengetahui cara untuk *memetakan*, *padan* dan *menggabungkan* data yang dimasukkan.</span><span class="sxs-lookup"><span data-stu-id="317b1-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>
