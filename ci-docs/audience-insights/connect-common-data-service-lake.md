---
title: Sambung kepada entiti dalam lake terurus Common Data Service
description: Import data daripada danau data terurus Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643409"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="8d0da-103">Sambung ke data dalam data lake terurus Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8d0da-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8d0da-104">Artikel ini memberikan maklumat tentang cara pelanggan Dynamics 365 boleh bersambung dengan dengan cepat entiti analitis dalam danau terurus Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8d0da-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="8d0da-105">Anda mesti menjadi pentadbir dalam organisasi Common Data Service untuk meneruskan dan melihat senarai entiti yang tersedia dalam danau terurus.</span><span class="sxs-lookup"><span data-stu-id="8d0da-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="8d0da-106">Pertimbangan penting</span><span class="sxs-lookup"><span data-stu-id="8d0da-106">Important considerations</span></span>

<span data-ttu-id="8d0da-107">Data disimpan dalam perkhidmatan dalam talian seperti Azure Data Lake Storage, mungkin disimpan di lokasi lain daripada tempat data diproses atau disimpan dalam Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8d0da-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="8d0da-108">Dengan mengimport atau menyambung kepada data yang disimpan dalam perkhidmatan dalam talian, anda bersetuju bahawa data boleh dipindahkan ke dan disimpan dengan Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat Amanah Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="8d0da-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="8d0da-109">Sambung ke lake diurus Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8d0da-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="8d0da-110">Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="8d0da-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8d0da-111">Pilih **Tambah sumber data**.</span><span class="sxs-lookup"><span data-stu-id="8d0da-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="8d0da-112">Pilih **Sambung ke Common Data Service** dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="8d0da-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="8d0da-113">Masukkan **Name** untuk sumber data dan kemudian pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="8d0da-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="8d0da-114">Berikan **Alamat pelayan** untuk organisasi Common Data Service anda dan pilih **Daftar masuk**.</span><span class="sxs-lookup"><span data-stu-id="8d0da-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d0da-115">![Kotak dialog untuk memasukkan alamat pelayan Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="8d0da-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="8d0da-116">Pilih entiti yang anda mahu inges daripada senarai yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="8d0da-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="8d0da-117">Jika sesetengah entiti sudah dipilih, ia mungkin akan digunakan oleh aplikasi Dynamics 365 lain (seperti Dynamics 365 Sales Insights atau Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="8d0da-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="8d0da-118">Anda tidak boleh mengubah pemilihan.</span><span class="sxs-lookup"><span data-stu-id="8d0da-118">You can't change the selection.</span></span> <span data-ttu-id="8d0da-119">Entiti ini akan tersedia sebaik sahaja sumber data dicipta.</span><span class="sxs-lookup"><span data-stu-id="8d0da-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d0da-120">![Kotak dialog menunjukkan senarai entiti dalam organisasi Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="8d0da-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="8d0da-121">Simpan pilihan anda untuk mula menyegerakkan entiti yang dipilih ke lake diurus Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8d0da-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="8d0da-122">Anda akan menemui sambungan yang baru ditambah pada halaman **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="8d0da-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="8d0da-123">Ia akan dibariskan untuk segar semula dan menunjukkan entiti dikira sebagai 0 sehingga semua entiti disegerakkan.</span><span class="sxs-lookup"><span data-stu-id="8d0da-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="8d0da-124">Hanya satu sumber data persekitaran boleh secara serentak menggunakan lake terurus Common Data Service yang sama.</span><span class="sxs-lookup"><span data-stu-id="8d0da-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="8d0da-125">Edit sumber data lake diurus Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8d0da-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="8d0da-126">Anda hanya mengedit pemilihan entiti selepas mencipta sumber data.</span><span class="sxs-lookup"><span data-stu-id="8d0da-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="8d0da-127">Sebagai contoh, jika entiti tambahan ditambah Common Data Service dan anda mahu mengimportnya juga.</span><span class="sxs-lookup"><span data-stu-id="8d0da-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="8d0da-128">Untuk mencipta Common Data Service berbeza, [cipta sumber data baharu](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="8d0da-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="8d0da-129">Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="8d0da-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8d0da-130">Bersebelahan dengan sumber data yang anda mahu kemas kini, pilih elipsis.</span><span class="sxs-lookup"><span data-stu-id="8d0da-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="8d0da-131">Pilih pilihan **Edit** daripada senarai.</span><span class="sxs-lookup"><span data-stu-id="8d0da-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="8d0da-132">Pilih entiti tambahan daripada senarai entiti yang tersedia dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="8d0da-132">Select additional entities from the available list of entities and select **Save**.</span></span>
