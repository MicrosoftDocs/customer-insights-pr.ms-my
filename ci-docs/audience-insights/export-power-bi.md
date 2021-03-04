---
title: Penyambung Power BI
description: Ketahui cara menggunakan penyambung Dynamics 365 Customer Insights dalam Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477099"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="182fe-103">Penyambung untuk Power BI (pratonton)</span><span class="sxs-lookup"><span data-stu-id="182fe-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="182fe-104">Cipta visualisasi untuk data anda dengan Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="182fe-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="182fe-105">Menjana wawasan tambahan dan bina laporan dengan data pelanggan disatukan anda.</span><span class="sxs-lookup"><span data-stu-id="182fe-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="182fe-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="182fe-106">Prerequisites</span></span>

- <span data-ttu-id="182fe-107">Anda mempunyai profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="182fe-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="182fe-108">Versi terkini [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) dipasang pada komputer anda.</span><span class="sxs-lookup"><span data-stu-id="182fe-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="182fe-109">[Ketahui lebih lanjut tentang Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="182fe-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="182fe-110">Konfigurasi penyambung untuk Power BI</span><span class="sxs-lookup"><span data-stu-id="182fe-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="182fe-111">Dalam Power BI Desktop, pilih **Fail** > **Dapatkan Data**.</span><span class="sxs-lookup"><span data-stu-id="182fe-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="182fe-112">Pilih **Lihat lebih** dan cari **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="182fe-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="182fe-113">Pilih **Connect**.</span><span class="sxs-lookup"><span data-stu-id="182fe-113">Select **Connect**.</span></span>

1. <span data-ttu-id="182fe-114">**Log masuk** dengan akaun organisasi yang sama anda gunakan untuk Customer Insights dan pilih **Sambung**.</span><span class="sxs-lookup"><span data-stu-id="182fe-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="182fe-115">Akaun yang anda tunjukkan dalam langkah ini digunakan untuk mengambil data daripada Customer Insights dan tidak perlu sama seperti yang anda daftar masuk dalam Power BI.</span><span class="sxs-lookup"><span data-stu-id="182fe-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="182fe-116">Untuk tetap semula akaun yang digunakan untuk pengambilan data, buka Power BI dan pergi ke **Fail** > **Pilihan** > **Tetapan** > **Tetapan sumber data**.</span><span class="sxs-lookup"><span data-stu-id="182fe-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="182fe-117">Dalam senarai sumber data, pilih **Daftar Masuk Dynamics 365 Customer Insights** dan pilih **Keizinan dibenarkan**.</span><span class="sxs-lookup"><span data-stu-id="182fe-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="182fe-118">Dalam kotak dialog **Pengemudi**.</span><span class="sxs-lookup"><span data-stu-id="182fe-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="182fe-119">anda lihat senarai semua persekitaran yang anda mempunyai akses.</span><span class="sxs-lookup"><span data-stu-id="182fe-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="182fe-120">Kembangkan persekitaran dan buka sebarang folder (entiti, langkah, segmen, pengayaan).</span><span class="sxs-lookup"><span data-stu-id="182fe-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="182fe-121">Contoh, buka folder **Entiti** untuk melihat semua entiti yang boleh anda import.</span><span class="sxs-lookup"><span data-stu-id="182fe-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="182fe-122">![Navigasi Penyambung Power BI](media/power-bi-navigator.png "Navigasi Penyambung Power BI")</span><span class="sxs-lookup"><span data-stu-id="182fe-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="182fe-123">Pilih kotak semak bersebelahan dengan entiti untuk disertakan dan **Dimuatkan**.</span><span class="sxs-lookup"><span data-stu-id="182fe-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="182fe-124">Anda boleh memilih entiti berbilang daripada persekitaran berbilang.</span><span class="sxs-lookup"><span data-stu-id="182fe-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="182fe-125">Anda akan melihat pemuatan kotak dialog semasa entiti anda dimuatkan.</span><span class="sxs-lookup"><span data-stu-id="182fe-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="182fe-126">Sebaik sahaja semua entiti yang dipilih anda telah dimuatkan, anda boleh menggunakan keupayaan Power BI untuk menggambarkan data tersebut.</span><span class="sxs-lookup"><span data-stu-id="182fe-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="182fe-127">Set data yang besar</span><span class="sxs-lookup"><span data-stu-id="182fe-127">Large data sets</span></span>

<span data-ttu-id="182fe-128">Penyambung Customer Insights Power BI direka untuk berfungsi bagi data set yang mengandungi hingga 1 juta profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="182fe-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="182fe-129">Mengimport set data yang lebih besar mungkin boleh tetapi ianya mengambil masa yang lama.</span><span class="sxs-lookup"><span data-stu-id="182fe-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="182fe-130">Selain itu, proses mungkin berjalan ke masa keluar kerana had Power BI.</span><span class="sxs-lookup"><span data-stu-id="182fe-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="182fe-131">Untuk maklumat lanjut, lihat [Power BI: Pengesyoran untuk set data yang lebih besar](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="182fe-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="182fe-132">Bekerja dengan subset data</span><span class="sxs-lookup"><span data-stu-id="182fe-132">Work with a subset of data</span></span>

<span data-ttu-id="182fe-133">Pertimbangkan untuk bekerja dengan subset data anda.</span><span class="sxs-lookup"><span data-stu-id="182fe-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="182fe-134">Sebagai contoh, anda boleh mencipta [segmen](segments.md) daripada mengeksport semua rekod pelanggan ke Power BI.</span><span class="sxs-lookup"><span data-stu-id="182fe-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="182fe-135">Pencarisilapan</span><span class="sxs-lookup"><span data-stu-id="182fe-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="182fe-136">Persekitaran Customer Insights tidak dipaparkan dalam Power BI</span><span class="sxs-lookup"><span data-stu-id="182fe-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="182fe-137">Persekitaran yang mempunyai lebih daripada satu [perhubungan](relationships.md) yang ditakrifkan antara dua entiti yang sama dalam wawasan khalayak tidak akan tersedia dalam penyambung Power BI.</span><span class="sxs-lookup"><span data-stu-id="182fe-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="182fe-138">Anda boleh mengenal pasti dan mengalih keluar perhubungan pendua.</span><span class="sxs-lookup"><span data-stu-id="182fe-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="182fe-139">Dalam wawasan khalayak, pergi ke **Data** > **Perhubungan** pada persekitaran yang anda tiada dalam Power BI.</span><span class="sxs-lookup"><span data-stu-id="182fe-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="182fe-140">Kenal pasti hubungan pendua:</span><span class="sxs-lookup"><span data-stu-id="182fe-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="182fe-141">Semak sama ada terdapat lebih daripada satu perhubungan yang ditakrifkan antara dua entiti yang sama.</span><span class="sxs-lookup"><span data-stu-id="182fe-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="182fe-142">Semak sama ada terdapat hubungan yang dicipta antara dua entiti yang kedua-duanya dimasukkan dalam proses penyatuan.</span><span class="sxs-lookup"><span data-stu-id="182fe-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="182fe-143">Terdapat perhubungan tersirat yang ditakrifkan antara semua entiti yang disertakan dalam proses penyatuan.</span><span class="sxs-lookup"><span data-stu-id="182fe-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="182fe-144">Alih keluar sebarang perhubungan pendua yang dikenal pasti.</span><span class="sxs-lookup"><span data-stu-id="182fe-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="182fe-145">Selepas penyingkiran perhubungan pendua, cuba konfigurasi penyambung Power BI sekali lagi.</span><span class="sxs-lookup"><span data-stu-id="182fe-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="182fe-146">Persekitarannya sepatutnya boleh tersedia sekarang.</span><span class="sxs-lookup"><span data-stu-id="182fe-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

