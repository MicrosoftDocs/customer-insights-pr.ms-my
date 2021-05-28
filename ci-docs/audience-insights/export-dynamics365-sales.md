---
title: Eksport data Customer Insights ke Dynamics 365 Sales
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976237"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="17a37-103">Gunakan segmen dalam Dynamics 365 Sales (pratonton)</span><span class="sxs-lookup"><span data-stu-id="17a37-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="17a37-104">Gunakan data pelanggan anda untuk mencipta senarai pemasaran, menyusuli aliran kerja dan menghantar promosi dengan Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="17a37-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="17a37-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="17a37-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="17a37-106">Rekod kenalan mesti wujud dalam Dynamics 365 Sales sebelum anda boleh mengeksport segmen daripada Customer Insights ke Jualan.</span><span class="sxs-lookup"><span data-stu-id="17a37-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="17a37-107">Baca lebih lanjut tentang cara untuk menginges kenalan dalam [Dynamics 365 Sales menggunakan Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="17a37-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="17a37-108">Mengeksport segmen daripada wawasan khalayak kepada Jualan tidak akan mencipta rekod kenalan baharu dalam tika Jualan.</span><span class="sxs-lookup"><span data-stu-id="17a37-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="17a37-109">Rekod kenalan daripada Jualan mesti diinges dalam wawasan khalayak dan digunakan sebagai sumber data.</span><span class="sxs-lookup"><span data-stu-id="17a37-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="17a37-110">Mereka juga perlu dimasukkan dalam entiti Pelanggan disatukan untuk memetakan ID pelanggan kepada ID kenalan sebelum segmen boleh dieksport.</span><span class="sxs-lookup"><span data-stu-id="17a37-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="17a37-111">Sediakan sambungan ke Sales</span><span class="sxs-lookup"><span data-stu-id="17a37-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="17a37-112">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="17a37-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="17a37-113">Pilih **Tambah sambungan** dan pilih **Dynamics 365 Sales** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="17a37-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="17a37-114">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="17a37-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="17a37-115">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="17a37-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="17a37-116">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="17a37-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="17a37-117">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="17a37-117">Choose who can use this connection.</span></span> <span data-ttu-id="17a37-118">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="17a37-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="17a37-119">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="17a37-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="17a37-120">Masukkan URL Jualan organisasi anda dalam medan **Alamat pelayan**.</span><span class="sxs-lookup"><span data-stu-id="17a37-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="17a37-121">Dalam bahagian **Akaun pentadbir pelayan**, pilih **Daftar masuk** dan pilih akaun Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="17a37-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="17a37-122">Petakan medan ID pelanggan ke ID Kenalan Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="17a37-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="17a37-123">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="17a37-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="17a37-124">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="17a37-124">Configure an export</span></span>

<span data-ttu-id="17a37-125">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="17a37-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="17a37-126">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="17a37-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="17a37-127">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="17a37-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="17a37-128">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="17a37-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="17a37-129">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="17a37-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="17a37-130">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="17a37-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="17a37-131">Pilih satu atau lebih segmen.</span><span class="sxs-lookup"><span data-stu-id="17a37-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="17a37-132">Pilih **Simpan**</span><span class="sxs-lookup"><span data-stu-id="17a37-132">Select **Save**</span></span>

<span data-ttu-id="17a37-133">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="17a37-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="17a37-134">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="17a37-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="17a37-135">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="17a37-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
