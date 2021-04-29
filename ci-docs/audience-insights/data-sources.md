---
title: Pilih sumber data untuk menginges data
description: Ketahui cara mengimport data daripada pelbagai sumber.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887905"
---
# <a name="data-sources-overview"></a><span data-ttu-id="514a0-103">Gambaran keseluruhan sumber data</span><span class="sxs-lookup"><span data-stu-id="514a0-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="514a0-104">Keupayaan wawasan khalayak dalam Dynamics 365 Customer Insights bersambung ke data daripada set sumber yang luas.</span><span class="sxs-lookup"><span data-stu-id="514a0-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="514a0-105">Menyambung kepada sumber data sering dirujukkan sebagai proses *menelan data*.</span><span class="sxs-lookup"><span data-stu-id="514a0-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="514a0-106">Selepas menelan data, anda boleh [menyatukan](data-unification.md) dan mengambil tindakan ke atasnya.</span><span class="sxs-lookup"><span data-stu-id="514a0-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="514a0-107">Tambahkan sumber data</span><span class="sxs-lookup"><span data-stu-id="514a0-107">Add a data source</span></span>

<span data-ttu-id="514a0-108">Rujuk artikel terperinci tentang cara menambah sumber data, bergantung pada pilihan yang anda pilih.</span><span class="sxs-lookup"><span data-stu-id="514a0-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="514a0-109">Anda boleh menambah sumber data dalam tiga cara utama:</span><span class="sxs-lookup"><span data-stu-id="514a0-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="514a0-110">Melalui berpuluh-puluh penyambung Power Query</span><span class="sxs-lookup"><span data-stu-id="514a0-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="514a0-111">Daripada folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="514a0-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="514a0-112">Daripada lake Common Data Service anda sendiri</span><span class="sxs-lookup"><span data-stu-id="514a0-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="514a0-113">Tambah data daripada sumber data di premis</span><span class="sxs-lookup"><span data-stu-id="514a0-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="514a0-114">Pengingesan data daripada sumber data di premis dalam Wawasan Khalayak disokong berdasarkan aliran data Power Platform.</span><span class="sxs-lookup"><span data-stu-id="514a0-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="514a0-115">Aliran data boleh didayakan dalam Customer Insights dengan [menyediakan URL persekitaran Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) semasa menyediakan persekitaran.</span><span class="sxs-lookup"><span data-stu-id="514a0-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="514a0-116">Sumber data yang dicipta selepas mengaitkan persekitaran Dataverse dengan Customer Insights akan menggunakan aliran data [Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) secara lalai.</span><span class="sxs-lookup"><span data-stu-id="514a0-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="514a0-117">Aliran data menyokong kesambungan on-prem menggunakan get laluan data.</span><span class="sxs-lookup"><span data-stu-id="514a0-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="514a0-118">Alih keluar dan cipta semula sumber data yang wujud sebelum persekitaran Dataverse dikaitkan dengan penggunaan get laluan data di premis.</span><span class="sxs-lookup"><span data-stu-id="514a0-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="514a0-119">Get laluan data daripada persekitaran Power BI atau Power Apps sedia ada akan kelihatan dan anda boleh menggunakan semula dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="514a0-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="514a0-120">Halaman sumber data menunjukkan pautan untuk pergi ke persekitaran Power Platform di mana anda boleh melihat dan mengkonfigurasikan get laluan data di premis.</span><span class="sxs-lookup"><span data-stu-id="514a0-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Tangkapan skrin halaman sumber data menunjukkan pautan yang menunjuk kepada persekitaran Power Platform.":::

## <a name="review-ingested-data"></a><span data-ttu-id="514a0-122">Semak data yang ditelan</span><span class="sxs-lookup"><span data-stu-id="514a0-122">Review ingested data</span></span>

<span data-ttu-id="514a0-123">Anda akan melihat nama setiap sumber data yang ditelan, status dan masa terakhir data disegar semula untuk sumber tersebut.</span><span class="sxs-lookup"><span data-stu-id="514a0-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="514a0-124">Anda boleh mengisih senarai sumber data mengikut setiap lajur.</span><span class="sxs-lookup"><span data-stu-id="514a0-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="514a0-125">![Sumber Data ditambah](media/configure-data-datasource-added.png "Sumber Data ditambah")</span><span class="sxs-lookup"><span data-stu-id="514a0-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="514a0-126">Status</span><span class="sxs-lookup"><span data-stu-id="514a0-126">Status</span></span>  |<span data-ttu-id="514a0-127">Penerangan </span><span class="sxs-lookup"><span data-stu-id="514a0-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="514a0-128">Berjaya</span><span class="sxs-lookup"><span data-stu-id="514a0-128">Successful</span></span>   |<span data-ttu-id="514a0-129">Sumber data berjaya diinges jika masa disebutkan dalam lajur **Disegar semula**.</span><span class="sxs-lookup"><span data-stu-id="514a0-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="514a0-130">Belum dimulakan</span><span class="sxs-lookup"><span data-stu-id="514a0-130">Not started</span></span>   |<span data-ttu-id="514a0-131">Sumber data belum mempunyai data diinges atau masih dalam mod draf.</span><span class="sxs-lookup"><span data-stu-id="514a0-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="514a0-132">Menyegar semula</span><span class="sxs-lookup"><span data-stu-id="514a0-132">Refreshing</span></span>    |<span data-ttu-id="514a0-133">Kemasukan data sedang berjalan.</span><span class="sxs-lookup"><span data-stu-id="514a0-133">Data ingestion is in progress.</span></span> <span data-ttu-id="514a0-134">Anda boleh membatalkan operasi ini dengan memilih **Hentikan menyegar semula** di dalam lajur **Tindakan**.</span><span class="sxs-lookup"><span data-stu-id="514a0-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="514a0-135">Hentikan segar semula sumber data akan kembali ke keadaan segar semula terakhir.</span><span class="sxs-lookup"><span data-stu-id="514a0-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="514a0-136">Gagal</span><span class="sxs-lookup"><span data-stu-id="514a0-136">Failed</span></span>     |<span data-ttu-id="514a0-137">Kemasukan data mempunyai ralat.</span><span class="sxs-lookup"><span data-stu-id="514a0-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="514a0-138">Pilih nilai dalam lajur **Status** bagi sebarang sumber data untuk menyemak butiran lanjut.</span><span class="sxs-lookup"><span data-stu-id="514a0-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="514a0-139">Dalam anak tetingkap **Butiran kemajuan**, kembangkan **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="514a0-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="514a0-140">Pilih **Lihat butiran** untuk maklumat lanjut tentang status segar semula termasuk butiran ralat dan kemas kini proses hiliran.</span><span class="sxs-lookup"><span data-stu-id="514a0-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="514a0-141">Muatan data boleh mengambil masa sedikit.</span><span class="sxs-lookup"><span data-stu-id="514a0-141">Loading data can take some time.</span></span> <span data-ttu-id="514a0-142">Selepas segar semula berjaya, data yang dimasukkan boleh disemak daripada halaman **Entiti**.</span><span class="sxs-lookup"><span data-stu-id="514a0-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="514a0-143">Untuk maklumat lanjut, lihat [Entiti](entities.md).</span><span class="sxs-lookup"><span data-stu-id="514a0-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="514a0-144">Menyegar semula sumber data</span><span class="sxs-lookup"><span data-stu-id="514a0-144">Refresh a data source</span></span>

<span data-ttu-id="514a0-145">Sumber data boleh disegar semula mengikut jadual automatik atau disegar semula secara manual berdasarkan permintaan.</span><span class="sxs-lookup"><span data-stu-id="514a0-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="514a0-146">Pergi ke **Pentadbir** > **Sistem** > [**Jadual**](system.md#schedule-tab) untuk mengkonfigurasi segar semula yang dijadualkan bagi semua sumber data anda yang diinges.</span><span class="sxs-lookup"><span data-stu-id="514a0-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="514a0-147">Untuk menyegar semula sumber data mengikut permintaan, ikuti langkah ini:</span><span class="sxs-lookup"><span data-stu-id="514a0-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="514a0-148">Dalam Insights khalayak, pergi ke **Data** > **Sumber data**</span><span class="sxs-lookup"><span data-stu-id="514a0-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="514a0-149">Pilih elipsis menegak bersebelahan dengan sumber data yang anda mahu segar semula dan pilih **Segar semula** daripada senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="514a0-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="514a0-150">Sumber data kini dicetuskan untuk segar semula secara manual.</span><span class="sxs-lookup"><span data-stu-id="514a0-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="514a0-151">Menyegarkan semula sumber data akan mengemas kini kedua-dua skema entiti dan data untuk semua entiti yang dinyatakan dalam sumber data.</span><span class="sxs-lookup"><span data-stu-id="514a0-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="514a0-152">Pilih **Berhenti menyegar semula** jika anda mahu membatalkan segar semula sedia ada dan sumber data akan bertukar kembali ke status segar semula terakhir.</span><span class="sxs-lookup"><span data-stu-id="514a0-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="514a0-153">Padam sumber data</span><span class="sxs-lookup"><span data-stu-id="514a0-153">Delete a data source</span></span>

1. <span data-ttu-id="514a0-154">Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="514a0-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="514a0-155">Pilih elipsis menegak bersebelahan dengan sumber data yang anda mahu alih keluar dan pilih **Padam** daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="514a0-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="514a0-156">Sahkan pemadaman anda.</span><span class="sxs-lookup"><span data-stu-id="514a0-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
