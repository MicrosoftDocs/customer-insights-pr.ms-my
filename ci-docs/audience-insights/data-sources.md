---
title: Pilih sumber data untuk menginges data
description: Ketahui cara mengimport data daripada pelbagai sumber.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643964"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="923a6-103">Gambaran keseluruhan tentang sumber data</span><span class="sxs-lookup"><span data-stu-id="923a6-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="923a6-104">Keupayaan wawasan khalayak dalam Dynamics 365 Customer Insights bersambung ke data daripada set sumber yang luas.</span><span class="sxs-lookup"><span data-stu-id="923a6-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="923a6-105">Menyambung kepada sumber data sering dirujukkan sebagai proses *menelan data*.</span><span class="sxs-lookup"><span data-stu-id="923a6-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="923a6-106">Selepas menelan data, anda boleh [menyatukan](data-unification.md) dan mengambil tindakan ke atasnya.</span><span class="sxs-lookup"><span data-stu-id="923a6-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="923a6-107">Tambahkan sumber data</span><span class="sxs-lookup"><span data-stu-id="923a6-107">Add a data source</span></span>

<span data-ttu-id="923a6-108">Rujuk artikel terperinci tentang cara menambah sumber data, bergantung pada pilihan yang anda pilih.</span><span class="sxs-lookup"><span data-stu-id="923a6-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="923a6-109">Anda boleh menambah sumber data dalam tiga cara utama:</span><span class="sxs-lookup"><span data-stu-id="923a6-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="923a6-110">Melalui berpuluh-puluh penyambung Power Query</span><span class="sxs-lookup"><span data-stu-id="923a6-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="923a6-111">Daripada folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="923a6-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="923a6-112">Daripada lake Common Data Service anda sendiri</span><span class="sxs-lookup"><span data-stu-id="923a6-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="923a6-113">Anda tidak boleh menambah data daripada sumber data di premis lagi.</span><span class="sxs-lookup"><span data-stu-id="923a6-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="923a6-114">Semak data yang ditelan</span><span class="sxs-lookup"><span data-stu-id="923a6-114">Review ingested data</span></span>

<span data-ttu-id="923a6-115">Anda akan melihat nama setiap sumber data yang ditelan, status dan masa terakhir data disegar semula untuk sumber tersebut.</span><span class="sxs-lookup"><span data-stu-id="923a6-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="923a6-116">Anda boleh mengisih senarai sumber data mengikut setiap lajur.</span><span class="sxs-lookup"><span data-stu-id="923a6-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="923a6-117">![Sumber Data ditambah](media/configure-data-datasource-added.png "Sumber Data ditambah")</span><span class="sxs-lookup"><span data-stu-id="923a6-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="923a6-118">Status</span><span class="sxs-lookup"><span data-stu-id="923a6-118">Status</span></span>  |<span data-ttu-id="923a6-119">Penerangan </span><span class="sxs-lookup"><span data-stu-id="923a6-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="923a6-120">Berjaya</span><span class="sxs-lookup"><span data-stu-id="923a6-120">Successful</span></span>   |<span data-ttu-id="923a6-121">Sumber data berjaya diinges jika masa disebutkan dalam lajur **Disegar semula**.</span><span class="sxs-lookup"><span data-stu-id="923a6-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="923a6-122">Belum dimulakan</span><span class="sxs-lookup"><span data-stu-id="923a6-122">Not started</span></span>   |<span data-ttu-id="923a6-123">Sumber data belum mempunyai data diinges atau masih dalam mod draf.</span><span class="sxs-lookup"><span data-stu-id="923a6-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="923a6-124">Menyegar semula</span><span class="sxs-lookup"><span data-stu-id="923a6-124">Refreshing</span></span>    |<span data-ttu-id="923a6-125">Kemasukan data sedang berjalan.</span><span class="sxs-lookup"><span data-stu-id="923a6-125">Data ingestion is in progress.</span></span> <span data-ttu-id="923a6-126">Anda boleh membatalkan operasi ini dengan memilih **Hentikan menyegar semula** di dalam lajur **Tindakan**.</span><span class="sxs-lookup"><span data-stu-id="923a6-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="923a6-127">Hentikan segar semula sumber data akan kembali ke keadaan segar semula terakhir.</span><span class="sxs-lookup"><span data-stu-id="923a6-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="923a6-128">Gagal</span><span class="sxs-lookup"><span data-stu-id="923a6-128">Failed</span></span>     |<span data-ttu-id="923a6-129">Kemasukan data mempunyai ralat.</span><span class="sxs-lookup"><span data-stu-id="923a6-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="923a6-130">Pilih **Status segar semula** untuk menyemak lebih banyak butiran tentang status segar semula termasuk butiran ralat dan kemas kini proses hiliran.</span><span class="sxs-lookup"><span data-stu-id="923a6-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="923a6-131">Muatan data boleh mengambil masa sedikit.</span><span class="sxs-lookup"><span data-stu-id="923a6-131">Loading data can take some time.</span></span> <span data-ttu-id="923a6-132">Selepas segar semula berjaya, data yang dimasukkan boleh disemak daripada halaman **Entiti**.</span><span class="sxs-lookup"><span data-stu-id="923a6-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="923a6-133">Untuk maklumat lanjut, lihat [Entiti](entities.md).</span><span class="sxs-lookup"><span data-stu-id="923a6-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="923a6-134">Menyegar semula sumber data</span><span class="sxs-lookup"><span data-stu-id="923a6-134">Refresh a data source</span></span>

<span data-ttu-id="923a6-135">Sumber data boleh disegar semula mengikut jadual automatik atau disegar semula secara manual berdasarkan permintaan.</span><span class="sxs-lookup"><span data-stu-id="923a6-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="923a6-136">Pergi ke **Pentadbir** > **Sistem** > [**Jadual**](system.md#schedule-tab) untuk mengkonfigurasi segar semula yang dijadualkan bagi semua sumber data anda yang diinges.</span><span class="sxs-lookup"><span data-stu-id="923a6-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="923a6-137">Untuk menyegar semula sumber data mengikut permintaan, ikuti langkah ini:</span><span class="sxs-lookup"><span data-stu-id="923a6-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="923a6-138">Dalam Insights khalayak, pergi ke **Data** > **Sumber data**</span><span class="sxs-lookup"><span data-stu-id="923a6-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="923a6-139">Pilih elipsis menegak bersebelahan dengan sumber data yang anda mahu segar semula dan pilih **Segar semula** daripada senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="923a6-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="923a6-140">Sumber data kini dicetuskan untuk segar semula secara manual.</span><span class="sxs-lookup"><span data-stu-id="923a6-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="923a6-141">Menyegar semula sumber data akan mengemas kini skema entiti serta data untuk semua entiti yang ditentukan dalam sumber data.</span><span class="sxs-lookup"><span data-stu-id="923a6-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="923a6-142">Pilih **Berhenti menyegar semula** jika anda mahu membatalkan segar semula sedia ada dan sumber data akan bertukar kembali ke status segar semula terakhir.</span><span class="sxs-lookup"><span data-stu-id="923a6-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="923a6-143">Padam sumber data</span><span class="sxs-lookup"><span data-stu-id="923a6-143">Delete a data source</span></span>

1. <span data-ttu-id="923a6-144">Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="923a6-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="923a6-145">Pilih elipsis menegak bersebelahan dengan sumber data yang anda mahu alih keluar dan pilih **Padam** daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="923a6-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="923a6-146">Sahkan pemadaman anda.</span><span class="sxs-lookup"><span data-stu-id="923a6-146">Confirm your deletion.</span></span>
