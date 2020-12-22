---
title: Segar semula tokokan untuk sumber data berasaskan Power Query
description: Segar semula data baharu dan yang dikemas kini untuk sumber data besar berdasarkan Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406469"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="24e46-103">Segar semula peningkatan untuk sumber data berasaskan Power Query</span><span class="sxs-lookup"><span data-stu-id="24e46-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="24e46-104">Segar semula peningkatan untuk sumber data memberikan kelebihan berikut:</span><span class="sxs-lookup"><span data-stu-id="24e46-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="24e46-105">**Lebih cepat menyegar semula** - Hanya data yang telah diubah akan disegar semula.</span><span class="sxs-lookup"><span data-stu-id="24e46-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="24e46-106">Sebagai contoh, anda mungkin menyegar semula hanya lima hari yang lalu daripada set data yang bersejarah.</span><span class="sxs-lookup"><span data-stu-id="24e46-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="24e46-107">**Kebolehpercayaan dipertingkat** - Dengan menyegarkan semula yang lebih kecil, anda tidak perlu mengekalkan sambungan ke sistem sumber yang tidak menentu untuk jangka masa panjang, mengurangkan risiko isu sambungan.</span><span class="sxs-lookup"><span data-stu-id="24e46-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="24e46-108">**Penggunaan sumber dikurangkan** - Menyegar semula hanya sebahagian daripada jumlah data anda yang membawa kepada penggunaan sumber pengkomputeran yang lebih cekap dan mengurangkan jejak alam.</span><span class="sxs-lookup"><span data-stu-id="24e46-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="24e46-109">Konfigurasikan segar semula tokokan</span><span class="sxs-lookup"><span data-stu-id="24e46-109">Configure incremental refresh</span></span>

<span data-ttu-id="24e46-110">Insights khalayak membenarkan segar semula tokokan untuk sumber data yang diimport melalui Power Query yang menyokong pengingesan tokokan.</span><span class="sxs-lookup"><span data-stu-id="24e46-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="24e46-111">Sebagai contoh, pangkalan data SQL Azure dengan medan tarikh dan masa, yang menunjukkan apabila rekod data terakhir dikemas kini.</span><span class="sxs-lookup"><span data-stu-id="24e46-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="24e46-112">[Cipta sumber data baharu berdasarkan Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="24e46-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="24e46-113">Berikan nama untuk sumber data.</span><span class="sxs-lookup"><span data-stu-id="24e46-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="24e46-114">Pilih sumber data yang menyokong segar semula tokokan, seperti pangkalan data SQL Azure.</span><span class="sxs-lookup"><span data-stu-id="24e46-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="24e46-115">Pilih entiti atau jadual untuk dimasukkan.</span><span class="sxs-lookup"><span data-stu-id="24e46-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="24e46-116">Lengkapkan langkah-langkah transformasi dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="24e46-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="24e46-117">Dalam kotak dialog **Tetapkan segar semula tokokan**, pilih **Sediakan** untuk membuka **Tetapan segar semula tokokan**.</span><span class="sxs-lookup"><span data-stu-id="24e46-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="24e46-118">Jika anda memilih **Langkau**, sumber data akan menyegar semula keseluruhan set data.</span><span class="sxs-lookup"><span data-stu-id="24e46-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="24e46-119">Anda juga boleh menggunakan segar semula tokokan kemudian dengan mengedit sumber data sedia ada.</span><span class="sxs-lookup"><span data-stu-id="24e46-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="24e46-120">Pada **Tetapan segar semula tokokan**, anda akan mengkonfigurasi segar semula tokokan untuk semua entiti yang anda pilih semasa mencipta sumber data.</span><span class="sxs-lookup"><span data-stu-id="24e46-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="24e46-121">![Konfigurasikan entiti dalam sumber data untuk segar semula tokokan](media/incremental-refresh-settings.png "Konfigurasikan entiti dalam sumber data untuk segar semula tokokan")</span><span class="sxs-lookup"><span data-stu-id="24e46-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="24e46-122">Pilih entiti dan berikan butiran berikut:</span><span class="sxs-lookup"><span data-stu-id="24e46-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="24e46-123">**Takrifkan kunci utama**: Pilih kunci utama untuk entiti atau jadual.</span><span class="sxs-lookup"><span data-stu-id="24e46-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="24e46-124">**Takrifkan medan "terakhir dikemas kini"**": Medan ini hanya akan memaparkan atribut jenis tarikh atau masa.</span><span class="sxs-lookup"><span data-stu-id="24e46-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="24e46-125">Pilih atribut yang menunjukkan apabila rekod terakhir dikemas kini.</span><span class="sxs-lookup"><span data-stu-id="24e46-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="24e46-126">Ia akan digunakan untuk mengenal pasti rekod yang berada dalam lingkungan peningkatan segar semula jangka masa.</span><span class="sxs-lookup"><span data-stu-id="24e46-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="24e46-127">**Semak untuk setiap kemas kini**: Tentukan tempoh masa yang anda mahu untuk tempoh masa segar semula tokokan.</span><span class="sxs-lookup"><span data-stu-id="24e46-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="24e46-128">Pilih **Simpan** untuk melengkapkan penciptaan sumber data.</span><span class="sxs-lookup"><span data-stu-id="24e46-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="24e46-129">Segar semula data awal akan menjadi segar semula sepenuhnya.</span><span class="sxs-lookup"><span data-stu-id="24e46-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="24e46-130">Selepas itu, segar semula data tokokan berlaku seperti yang dikonfigurasikan dalam langkah sebelumnya.</span><span class="sxs-lookup"><span data-stu-id="24e46-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
