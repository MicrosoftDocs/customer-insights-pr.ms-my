---
title: Penyambung Power BI
description: Ketahui cara menggunakan penyambung Dynamics 365 Customer Insights dalam Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406439"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="0a974-103">Penyambung untuk Power BI (pratonton)</span><span class="sxs-lookup"><span data-stu-id="0a974-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="0a974-104">Cipta visualisasi untuk data anda dengan Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="0a974-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="0a974-105">Menjana wawasan tambahan dan bina laporan dengan data pelanggan disatukan anda.</span><span class="sxs-lookup"><span data-stu-id="0a974-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0a974-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="0a974-106">Prerequisites</span></span>

- <span data-ttu-id="0a974-107">Anda mempunyai profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="0a974-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="0a974-108">Versi terkini [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) dipasang pada komputer anda.</span><span class="sxs-lookup"><span data-stu-id="0a974-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="0a974-109">[Ketahui lebih lanjut tentang Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="0a974-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="0a974-110">Konfigurasi penyambung untuk Power BI</span><span class="sxs-lookup"><span data-stu-id="0a974-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="0a974-111">Dalam Power BI Desktop, pilih **Fail** > **Dapatkan Data**.</span><span class="sxs-lookup"><span data-stu-id="0a974-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="0a974-112">Pilih **Lihat lebih** dan cari **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="0a974-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="0a974-113">Pilih hasilnya dan pilih **Sambung**.</span><span class="sxs-lookup"><span data-stu-id="0a974-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="0a974-114">**Log masuk** dengan akaun organisasi yang sama anda gunakan untuk Customer Insights dan pilih **Sambung**.</span><span class="sxs-lookup"><span data-stu-id="0a974-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="0a974-115">Akaun yang anda tunjukkan dalam langkah ini digunakan untuk mengambil data daripada Customer Insights dan tidak perlu sama seperti yang anda daftar masuk dalam Power BI.</span><span class="sxs-lookup"><span data-stu-id="0a974-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="0a974-116">Untuk tetap semula akaun yang digunakan untuk pengambilan data, buka Power BI dan pergi ke **Fail** > **Pilihan** > **Tetapan** > **Tetapan sumber data**.</span><span class="sxs-lookup"><span data-stu-id="0a974-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="0a974-117">Dalam senarai sumber data, pilih **Daftar Masuk Dynamics 365 Customer Insights** dan pilih **Keizinan dibenarkan**.</span><span class="sxs-lookup"><span data-stu-id="0a974-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="0a974-118">Dalam kotak dialog **Pengemudi**.</span><span class="sxs-lookup"><span data-stu-id="0a974-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="0a974-119">anda lihat senarai semua persekitaran yang anda mempunyai akses.</span><span class="sxs-lookup"><span data-stu-id="0a974-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="0a974-120">Kembangkan persekitaran dan buka sebarang folder (entiti, langkah, segmen, pengayaan).</span><span class="sxs-lookup"><span data-stu-id="0a974-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="0a974-121">Contoh, buka folder **Entiti** untuk melihat semua entiti yang boleh anda import.</span><span class="sxs-lookup"><span data-stu-id="0a974-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="0a974-122">![Navigasi Penyambung Power BI](media/power-bi-navigator.png "Navigasi Penyambung Power BI")</span><span class="sxs-lookup"><span data-stu-id="0a974-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="0a974-123">Pilih kotak semak bersebelahan dengan entiti untuk disertakan dan **Dimuatkan**.</span><span class="sxs-lookup"><span data-stu-id="0a974-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="0a974-124">Anda boleh memilih entiti berbilang daripada persekitaran berbilang.</span><span class="sxs-lookup"><span data-stu-id="0a974-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="0a974-125">Anda akan melihat pemuatan kotak dialog semasa entiti anda dimuatkan.</span><span class="sxs-lookup"><span data-stu-id="0a974-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="0a974-126">Sebaik sahaja semua entiti yang dipilih anda telah dimuatkan, anda boleh menggunakan keupayaan Power BI untuk menggambarkan data tersebut.</span><span class="sxs-lookup"><span data-stu-id="0a974-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="0a974-127">Set data yang besar</span><span class="sxs-lookup"><span data-stu-id="0a974-127">Large data sets</span></span>

<span data-ttu-id="0a974-128">Penyambung Customer Insights Power BI direka untuk berfungsi bagi data set yang mengandungi hingga 1 juta profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="0a974-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="0a974-129">Mengimport set data yang lebih besar mungkin boleh tetapi ianya mengambil masa yang lama.</span><span class="sxs-lookup"><span data-stu-id="0a974-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="0a974-130">Selain itu, proses mungkin berjalan ke masa keluar kerana had Power BI.</span><span class="sxs-lookup"><span data-stu-id="0a974-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="0a974-131">Untuk maklumat lanjut, lihat [Power BI: Pengesyoran untuk set data yang lebih besar](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="0a974-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="0a974-132">Bekerja dengan subset data</span><span class="sxs-lookup"><span data-stu-id="0a974-132">Work with a subset of data</span></span>

<span data-ttu-id="0a974-133">Pertimbangkan untuk bekerja dengan subset data anda.</span><span class="sxs-lookup"><span data-stu-id="0a974-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="0a974-134">Sebagai contoh, anda boleh mencipta [segmen](segments.md) daripada mengeksport semua rekod pelanggan ke Power BI.</span><span class="sxs-lookup"><span data-stu-id="0a974-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
