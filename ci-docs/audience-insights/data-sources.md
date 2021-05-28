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
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085541"
---
# <a name="data-sources-overview"></a><span data-ttu-id="728b8-103">Gambaran keseluruhan sumber data</span><span class="sxs-lookup"><span data-stu-id="728b8-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="728b8-104">Keupayaan wawasan khalayak dalam Dynamics 365 Customer Insights bersambung ke data daripada set sumber yang luas.</span><span class="sxs-lookup"><span data-stu-id="728b8-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="728b8-105">Menyambung kepada sumber data sering dirujukkan sebagai proses *menelan data*.</span><span class="sxs-lookup"><span data-stu-id="728b8-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="728b8-106">Selepas menelan data, anda boleh [menyatukan](data-unification.md) dan mengambil tindakan ke atasnya.</span><span class="sxs-lookup"><span data-stu-id="728b8-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="728b8-107">Tambahkan sumber data</span><span class="sxs-lookup"><span data-stu-id="728b8-107">Add a data source</span></span>

<span data-ttu-id="728b8-108">Rujuk artikel terperinci tentang cara menambah sumber data, bergantung pada pilihan yang anda pilih.</span><span class="sxs-lookup"><span data-stu-id="728b8-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="728b8-109">Anda boleh menambah sumber data dalam tiga cara utama:</span><span class="sxs-lookup"><span data-stu-id="728b8-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="728b8-110">Melalui berpuluh-puluh penyambung Power Query</span><span class="sxs-lookup"><span data-stu-id="728b8-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="728b8-111">Daripada folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="728b8-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="728b8-112">Daripada lake Common Data Service anda sendiri</span><span class="sxs-lookup"><span data-stu-id="728b8-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="728b8-113">Tambah data daripada sumber data di premis</span><span class="sxs-lookup"><span data-stu-id="728b8-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="728b8-114">Pengingesan data daripada sumber data di premis dalam Wawasan Khalayak disokong berdasarkan aliran data Power Platform.</span><span class="sxs-lookup"><span data-stu-id="728b8-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="728b8-115">Aliran data boleh didayakan dalam Customer Insights dengan [menyediakan URL persekitaran Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) semasa menyediakan persekitaran.</span><span class="sxs-lookup"><span data-stu-id="728b8-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="728b8-116">Sumber data yang dicipta selepas mengaitkan persekitaran Dataverse dengan Customer Insights akan menggunakan aliran data [Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) secara lalai.</span><span class="sxs-lookup"><span data-stu-id="728b8-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="728b8-117">Aliran data menyokong kesambungan di premis menggunakan get laluan data.</span><span class="sxs-lookup"><span data-stu-id="728b8-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="728b8-118">Alih keluar dan cipta semula sumber data yang wujud sebelum persekitaran Dataverse  dikaitkan ke [guna get laluan data di premis](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="728b8-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="728b8-119">Get laluan data daripada persekitaran Power BI atau Power Apps sedia ada akan kelihatan dan anda boleh menggunakan semula dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="728b8-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="728b8-120">Halaman sumber data menunjukkan pautan untuk pergi ke persekitaran Power Platform di mana anda boleh melihat dan mengkonfigurasikan get laluan data di premis.</span><span class="sxs-lookup"><span data-stu-id="728b8-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="728b8-121">Semak data yang ditelan</span><span class="sxs-lookup"><span data-stu-id="728b8-121">Review ingested data</span></span>

<span data-ttu-id="728b8-122">Anda akan melihat nama setiap sumber data yang ditelan, status dan masa terakhir data disegar semula untuk sumber tersebut.</span><span class="sxs-lookup"><span data-stu-id="728b8-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="728b8-123">Anda boleh mengisih senarai sumber data mengikut setiap lajur.</span><span class="sxs-lookup"><span data-stu-id="728b8-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="728b8-124">![Sumber Data ditambah](media/configure-data-datasource-added.png "Sumber Data ditambah")</span><span class="sxs-lookup"><span data-stu-id="728b8-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="728b8-125">Status</span><span class="sxs-lookup"><span data-stu-id="728b8-125">Status</span></span>  |<span data-ttu-id="728b8-126">Penerangan </span><span class="sxs-lookup"><span data-stu-id="728b8-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="728b8-127">Berjaya</span><span class="sxs-lookup"><span data-stu-id="728b8-127">Successful</span></span>   |<span data-ttu-id="728b8-128">Sumber data berjaya diinges jika masa disebutkan dalam lajur **Disegar semula**.</span><span class="sxs-lookup"><span data-stu-id="728b8-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="728b8-129">Belum dimulakan</span><span class="sxs-lookup"><span data-stu-id="728b8-129">Not started</span></span>   |<span data-ttu-id="728b8-130">Sumber data belum mempunyai data diinges atau masih dalam mod draf.</span><span class="sxs-lookup"><span data-stu-id="728b8-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="728b8-131">Menyegar semula</span><span class="sxs-lookup"><span data-stu-id="728b8-131">Refreshing</span></span>    |<span data-ttu-id="728b8-132">Kemasukan data sedang berjalan.</span><span class="sxs-lookup"><span data-stu-id="728b8-132">Data ingestion is in progress.</span></span> <span data-ttu-id="728b8-133">Anda boleh membatalkan operasi ini dengan memilih **Hentikan menyegar semula** di dalam lajur **Tindakan**.</span><span class="sxs-lookup"><span data-stu-id="728b8-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="728b8-134">Hentikan segar semula sumber data akan kembali ke keadaan segar semula terakhir.</span><span class="sxs-lookup"><span data-stu-id="728b8-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="728b8-135">Gagal</span><span class="sxs-lookup"><span data-stu-id="728b8-135">Failed</span></span>     |<span data-ttu-id="728b8-136">Kemasukan data mempunyai ralat.</span><span class="sxs-lookup"><span data-stu-id="728b8-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="728b8-137">Pilih nilai dalam lajur **Status** bagi sebarang sumber data untuk menyemak butiran lanjut.</span><span class="sxs-lookup"><span data-stu-id="728b8-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="728b8-138">Dalam anak tetingkap **Butiran kemajuan**, kembangkan **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="728b8-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="728b8-139">Pilih **Lihat butiran** untuk maklumat lanjut tentang status segar semula termasuk butiran ralat dan kemas kini proses hiliran.</span><span class="sxs-lookup"><span data-stu-id="728b8-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="728b8-140">Muatan data boleh mengambil masa sedikit.</span><span class="sxs-lookup"><span data-stu-id="728b8-140">Loading data can take some time.</span></span> <span data-ttu-id="728b8-141">Selepas segar semula berjaya, data yang dimasukkan boleh disemak daripada halaman **Entiti**.</span><span class="sxs-lookup"><span data-stu-id="728b8-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="728b8-142">Untuk maklumat lanjut, lihat [Entiti](entities.md).</span><span class="sxs-lookup"><span data-stu-id="728b8-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="728b8-143">Menyegar semula sumber data</span><span class="sxs-lookup"><span data-stu-id="728b8-143">Refresh a data source</span></span>

<span data-ttu-id="728b8-144">Sumber data boleh disegar semula mengikut jadual automatik atau disegar semula secara manual berdasarkan permintaan.</span><span class="sxs-lookup"><span data-stu-id="728b8-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="728b8-145">Pergi ke **Pentadbir** > **Sistem** > [**Jadual**](system.md#schedule-tab) untuk mengkonfigurasi segar semula yang dijadualkan bagi semua sumber data anda yang diinges.</span><span class="sxs-lookup"><span data-stu-id="728b8-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="728b8-146">Untuk menyegar semula sumber data mengikut permintaan, ikuti langkah ini:</span><span class="sxs-lookup"><span data-stu-id="728b8-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="728b8-147">Dalam Insights khalayak, pergi ke **Data** > **Sumber data**</span><span class="sxs-lookup"><span data-stu-id="728b8-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="728b8-148">Pilih elipsis menegak bersebelahan dengan sumber data yang anda mahu segar semula dan pilih **Segar semula** daripada senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="728b8-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="728b8-149">Sumber data kini dicetuskan untuk segar semula secara manual.</span><span class="sxs-lookup"><span data-stu-id="728b8-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="728b8-150">Menyegarkan semula sumber data akan mengemas kini kedua-dua skema entiti dan data untuk semua entiti yang dinyatakan dalam sumber data.</span><span class="sxs-lookup"><span data-stu-id="728b8-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="728b8-151">Pilih **Berhenti menyegar semula** jika anda mahu membatalkan segar semula sedia ada dan sumber data akan bertukar kembali ke status segar semula terakhir.</span><span class="sxs-lookup"><span data-stu-id="728b8-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="728b8-152">Padam sumber data</span><span class="sxs-lookup"><span data-stu-id="728b8-152">Delete a data source</span></span>

1. <span data-ttu-id="728b8-153">Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="728b8-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="728b8-154">Pilih elipsis menegak bersebelahan dengan sumber data yang anda mahu alih keluar dan pilih **Padam** daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="728b8-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="728b8-155">Sahkan pemadaman anda.</span><span class="sxs-lookup"><span data-stu-id="728b8-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
