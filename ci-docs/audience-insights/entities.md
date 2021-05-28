---
title: Entiti dan set data
description: Lihat data pada halaman Entiti.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049405"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="517b9-103">Entiti dalam wawasan khalayak</span><span class="sxs-lookup"><span data-stu-id="517b9-103">Entities in audience insights</span></span>

<span data-ttu-id="517b9-104">Selepas [mengkonfigurasi sumber data anda](data-sources.md), pergi ke halaman **Entiti** untuk menilai kualiti data yang dimasukkan.</span><span class="sxs-lookup"><span data-stu-id="517b9-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="517b9-105">Entiti dianggap sebagai set data.</span><span class="sxs-lookup"><span data-stu-id="517b9-105">Entities are considered datasets.</span></span> <span data-ttu-id="517b9-106">Berbilang keupayaan Dynamics 365 Customer Insights dibina sekitar entiti ini.</span><span class="sxs-lookup"><span data-stu-id="517b9-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="517b9-107">Mengkajinya semula dengan teliti boleh membantu anda mengesahkan output keupayaan tersebut.</span><span class="sxs-lookup"><span data-stu-id="517b9-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="517b9-108">Halaman **Entiti** menyenaraikan entiti dan termasuk beberapa lajur:</span><span class="sxs-lookup"><span data-stu-id="517b9-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="517b9-109">**Nama**: Nama entiti data anda.</span><span class="sxs-lookup"><span data-stu-id="517b9-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="517b9-110">Jika anda nampak simbol amaran di sebelah nama entiti, ia bermaksud data untuk entiti tersebut tidak berjaya dimuatkan.</span><span class="sxs-lookup"><span data-stu-id="517b9-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="517b9-111">**Sumber**: Jenis sumber data yang memasukkan entiti</span><span class="sxs-lookup"><span data-stu-id="517b9-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="517b9-112">**Dicipta oleh**: Nama orang yang mencipta entiti</span><span class="sxs-lookup"><span data-stu-id="517b9-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="517b9-113">**Dicipta**: Tarikh dan masa penciptaan entiti</span><span class="sxs-lookup"><span data-stu-id="517b9-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="517b9-114">**Dikemas kini oleh**: Nama orang yang mengemas kini entiti</span><span class="sxs-lookup"><span data-stu-id="517b9-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="517b9-115">**Kemas kini terakhir**: Tarikh dan masa kemas kini yang terakhir bagi entiti</span><span class="sxs-lookup"><span data-stu-id="517b9-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="517b9-116">**Segar semula terakhir**: Tarikh dan masa data terakhir segar semula</span><span class="sxs-lookup"><span data-stu-id="517b9-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="517b9-117">Menerokai data entiti khusus</span><span class="sxs-lookup"><span data-stu-id="517b9-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="517b9-118">Pilih entiti untuk menerokai medan dan rekod yang berbeza termasuk dalam entiti tersebut.</span><span class="sxs-lookup"><span data-stu-id="517b9-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="517b9-119">![Pilih entiti](media/data-manager-entities-data.png "Pilih entiti")</span><span class="sxs-lookup"><span data-stu-id="517b9-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="517b9-120">Tab **Data** menunjukkan butiran penyenaraian jadual tentang rekod individu entiti.</span><span class="sxs-lookup"><span data-stu-id="517b9-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="517b9-121">![Jadual medan](media/data-manager-entities-fields.PNG "Jadual medan")</span><span class="sxs-lookup"><span data-stu-id="517b9-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="517b9-122">Tab **Atribut** dipilih secara lalai dan menunjukkan jadual untuk menyemak butiran bagi entiti yang dipilih seperti nama medan, jenis data dan jenis.</span><span class="sxs-lookup"><span data-stu-id="517b9-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="517b9-123">Lajur **Jenis** menunjukkan jenis berkaitan Model Data Lazim, yang mana sama ada dikenal pasti secara automatik oleh sistem atau [dipetakan secara manual](map-entities.md) oleh pengguna.</span><span class="sxs-lookup"><span data-stu-id="517b9-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="517b9-124">Ini ialah jenis semantik yang mungkin berbeza daripada jenis data atribut—contohnya, medan *e-mel* di bawah mempunyai jenis data *Teks* tetapi jenis Model Data Lazim (semantik) berkemungkinan *E-mel* atau *AlamatE-mel*.</span><span class="sxs-lookup"><span data-stu-id="517b9-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="517b9-125">Kedua-dua jadual menunjukkan hanya sampel data entiti anda.</span><span class="sxs-lookup"><span data-stu-id="517b9-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="517b9-126">Untuk melihat set data lengkap, pergi ke halaman **Sumber data**, pilih entiti, pilih **Edit** dan lihat data entiti ini dengan editor Power Query seperti yang diterangkan dalam [Sumber data](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="517b9-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="517b9-127">Untuk mengetahui lebih lanjut tentang data yang dimasukkan di dalam entiti, lajur **Ringkasan** menyediakan anda dengan beberapa ciri penting data seperti batal, nilai yang hilang, nilai unik, kiraan dan pengagihan, sebagaimana berkaitan dengan data anda.</span><span class="sxs-lookup"><span data-stu-id="517b9-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="517b9-128">Pilih ikon carta untuk melihat ringkasan data.</span><span class="sxs-lookup"><span data-stu-id="517b9-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="517b9-129">![Simbol ringkasan](media/data-manager-entities-summary.png "Jadual ringkasan data")</span><span class="sxs-lookup"><span data-stu-id="517b9-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="517b9-130">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="517b9-130">Next step</span></span>

<span data-ttu-id="517b9-131">Lihat topik [Menyatukan](data-unification.md) untuk mengetahui cara untuk *memetakan*, *padan* dan *menggabungkan* data yang dimasukkan.</span><span class="sxs-lookup"><span data-stu-id="517b9-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
