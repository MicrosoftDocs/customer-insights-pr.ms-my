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
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304707"
---
# <a name="data-sources-overview"></a><span data-ttu-id="bca23-103">Gambaran keseluruhan sumber data</span><span class="sxs-lookup"><span data-stu-id="bca23-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bca23-104">Keupayaan wawasan khalayak dalam Dynamics 365 Customer Insights bersambung ke data daripada set sumber yang luas.</span><span class="sxs-lookup"><span data-stu-id="bca23-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="bca23-105">Menyambung kepada sumber data sering dirujukkan sebagai proses *menelan data*.</span><span class="sxs-lookup"><span data-stu-id="bca23-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="bca23-106">Selepas menelan data, anda boleh [menyatukan](data-unification.md) dan mengambil tindakan ke atasnya.</span><span class="sxs-lookup"><span data-stu-id="bca23-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="bca23-107">Tambahkan sumber data</span><span class="sxs-lookup"><span data-stu-id="bca23-107">Add a data source</span></span>

<span data-ttu-id="bca23-108">Rujuk artikel terperinci tentang cara menambah sumber data, bergantung pada pilihan yang anda pilih.</span><span class="sxs-lookup"><span data-stu-id="bca23-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="bca23-109">Anda boleh menambah sumber data dalam tiga cara utama:</span><span class="sxs-lookup"><span data-stu-id="bca23-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="bca23-110">Melalui berpuluh-puluh penyambung Power Query</span><span class="sxs-lookup"><span data-stu-id="bca23-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="bca23-111">Daripada folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="bca23-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="bca23-112">Daripada lake Microsoft Dataverse anda sendiri</span><span class="sxs-lookup"><span data-stu-id="bca23-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="bca23-113">Tambah data daripada sumber data di premis</span><span class="sxs-lookup"><span data-stu-id="bca23-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="bca23-114">Pengingesan data daripada sumber data di premis dalam cerapan Khalayak disokong berdasarkan pada aliran data Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="bca23-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="bca23-115">Aliran data boleh didayakan dalam Customer Insights dengan [menyediakan URL persekitaran Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) semasa menyediakan persekitaran.</span><span class="sxs-lookup"><span data-stu-id="bca23-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="bca23-116">Sumber data yang dicipta selepas mengaitkan persekitaran Dataverse dengan Customer Insights akan menggunakan aliran data [Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) secara lalai.</span><span class="sxs-lookup"><span data-stu-id="bca23-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="bca23-117">Aliran data menyokong kesambungan di premis menggunakan get laluan data.</span><span class="sxs-lookup"><span data-stu-id="bca23-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="bca23-118">Alih keluar dan cipta semula sumber data yang wujud sebelum persekitaran Dataverse  dikaitkan ke [guna get laluan data di premis](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="bca23-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="bca23-119">Get laluan data daripada persekitaran Power BI atau Power Apps sedia ada akan kelihatan dan anda boleh menggunakan semula dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bca23-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="bca23-120">Halaman sumber data menunjukkan pautan untuk pergi ke persekitaran Microsoft Power Platform yang anda boleh melihat dan mengkonfigurasikan get laluan data di premis.</span><span class="sxs-lookup"><span data-stu-id="bca23-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="bca23-121">Semak data yang ditelan</span><span class="sxs-lookup"><span data-stu-id="bca23-121">Review ingested data</span></span>

<span data-ttu-id="bca23-122">Anda akan melihat nama setiap sumber data yang ditelan, status dan masa terakhir data disegar semula untuk sumber tersebut.</span><span class="sxs-lookup"><span data-stu-id="bca23-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="bca23-123">Anda boleh mengisih senarai sumber data mengikut setiap lajur.</span><span class="sxs-lookup"><span data-stu-id="bca23-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bca23-124">![Sumber Data ditambah](media/configure-data-datasource-added.png "Sumber Data ditambah")</span><span class="sxs-lookup"><span data-stu-id="bca23-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="bca23-125">Status</span><span class="sxs-lookup"><span data-stu-id="bca23-125">Status</span></span>  |<span data-ttu-id="bca23-126">Penerangan </span><span class="sxs-lookup"><span data-stu-id="bca23-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="bca23-127">Berjaya</span><span class="sxs-lookup"><span data-stu-id="bca23-127">Successful</span></span>   |<span data-ttu-id="bca23-128">Sumber data berjaya diinges jika masa disebutkan dalam lajur **Disegar semula**.</span><span class="sxs-lookup"><span data-stu-id="bca23-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="bca23-129">Belum dimulakan</span><span class="sxs-lookup"><span data-stu-id="bca23-129">Not started</span></span>   |<span data-ttu-id="bca23-130">Sumber data belum mempunyai data diinges atau masih dalam mod draf.</span><span class="sxs-lookup"><span data-stu-id="bca23-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="bca23-131">Menyegar semula</span><span class="sxs-lookup"><span data-stu-id="bca23-131">Refreshing</span></span>    |<span data-ttu-id="bca23-132">Kemasukan data sedang berjalan.</span><span class="sxs-lookup"><span data-stu-id="bca23-132">Data ingestion is in progress.</span></span> <span data-ttu-id="bca23-133">Anda boleh membatalkan operasi ini dengan memilih **Hentikan menyegar semula** di dalam lajur **Tindakan**.</span><span class="sxs-lookup"><span data-stu-id="bca23-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="bca23-134">Hentikan segar semula sumber data akan kembali ke keadaan segar semula terakhir.</span><span class="sxs-lookup"><span data-stu-id="bca23-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="bca23-135">Gagal</span><span class="sxs-lookup"><span data-stu-id="bca23-135">Failed</span></span>     |<span data-ttu-id="bca23-136">Kemasukan data mempunyai ralat.</span><span class="sxs-lookup"><span data-stu-id="bca23-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="bca23-137">Pilih nilai dalam lajur **Status** bagi sebarang sumber data untuk menyemak butiran lanjut.</span><span class="sxs-lookup"><span data-stu-id="bca23-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="bca23-138">Dalam anak tetingkap **Butiran kemajuan**, kembangkan **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="bca23-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="bca23-139">Pilih **Lihat butiran** untuk maklumat lanjut tentang status segar semula termasuk butiran ralat dan kemas kini proses hiliran.</span><span class="sxs-lookup"><span data-stu-id="bca23-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="bca23-140">Memuatkan data boleh mengambil masa.</span><span class="sxs-lookup"><span data-stu-id="bca23-140">Loading data can take time.</span></span> <span data-ttu-id="bca23-141">Selepas segar semula berjaya, data yang dimasukkan boleh disemak daripada halaman **Entiti**.</span><span class="sxs-lookup"><span data-stu-id="bca23-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="bca23-142">Untuk maklumat lanjut, lihat [Entiti](entities.md).</span><span class="sxs-lookup"><span data-stu-id="bca23-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="bca23-143">Menyegar semula sumber data</span><span class="sxs-lookup"><span data-stu-id="bca23-143">Refresh a data source</span></span>

<span data-ttu-id="bca23-144">Sumber data boleh disegar semula mengikut jadual automatik atau disegar semula secara manual berdasarkan permintaan.</span><span class="sxs-lookup"><span data-stu-id="bca23-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="bca23-145">Pergi ke **Pentadbir** > **Sistem** > [**Jadual**](system.md#schedule-tab) untuk mengkonfigurasi segar semula yang dijadualkan bagi semua sumber data anda yang diinges.</span><span class="sxs-lookup"><span data-stu-id="bca23-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="bca23-146">Untuk menyegar semula sumber data mengikut permintaan, ikuti langkah ini:</span><span class="sxs-lookup"><span data-stu-id="bca23-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="bca23-147">Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="bca23-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="bca23-148">Pilih elipsis menegak di sebelah sumber data yang ingin anda segar semula dan pilih **Segar semula** daripada senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="bca23-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="bca23-149">Sumber data kini dicetuskan untuk segar semula secara manual.</span><span class="sxs-lookup"><span data-stu-id="bca23-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="bca23-150">Menyegarkan semula sumber data akan mengemas kini kedua-dua skema entiti dan data untuk semua entiti yang dinyatakan dalam sumber data.</span><span class="sxs-lookup"><span data-stu-id="bca23-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="bca23-151">Pilih **Berhenti menyegar semula** jika anda mahu membatalkan segar semula sedia ada dan sumber data akan bertukar kembali ke status segar semula terakhir.</span><span class="sxs-lookup"><span data-stu-id="bca23-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="bca23-152">Padam sumber data</span><span class="sxs-lookup"><span data-stu-id="bca23-152">Delete a data source</span></span>

1. <span data-ttu-id="bca23-153">Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="bca23-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="bca23-154">Pilih elipsis menegak di sebelah sumber data yang ingin anda alih keluar dan pilih **Padam** daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="bca23-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="bca23-155">Sahkan pemadaman anda.</span><span class="sxs-lookup"><span data-stu-id="bca23-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
