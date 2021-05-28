---
title: Eksport data Customer Insights ke Dynamics 365 Marketing
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976811"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="39f6f-103">Gunakan segmen dalam Dynamics 365 Marketing (pratonton)</span><span class="sxs-lookup"><span data-stu-id="39f6f-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="39f6f-104">Gunakan [segmen](segments.md) untuk menjana kumpulan tertentu kempen dan kenalan pelanggan dengan Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="39f6f-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="39f6f-105">Untuk maklumat lanjut, lihat [Gunakan segmen daripada Dynamics 365 Customer Insights dengan Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="39f6f-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="39f6f-106">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="39f6f-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="39f6f-107">Rekod kenalan mesti wujud dalam Dynamics 365 Marketing sebelum anda boleh mengeksport segmen daripada Customer Insights ke Pemasaran.</span><span class="sxs-lookup"><span data-stu-id="39f6f-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="39f6f-108">Baca lebih lanjut tentang cara untuk menginges kenalan dalam [Dynamics 365 Marketing menggunakan Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="39f6f-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="39f6f-109">Mengeksport segmen daripada wawasan khalayak kepada Pemasaran tidak akan mencipta rekod kenalan baharu dalam tika Pemasaran.</span><span class="sxs-lookup"><span data-stu-id="39f6f-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="39f6f-110">Rekod kenalan daripada Pemasaran mesti diinges dalam wawasan khalayak dan digunakan sebagai sumber data.</span><span class="sxs-lookup"><span data-stu-id="39f6f-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="39f6f-111">Mereka juga perlu dimasukkan dalam entiti Pelanggan disatukan untuk memetakan ID pelanggan kepada ID kenalan sebelum segmen boleh dieksport.</span><span class="sxs-lookup"><span data-stu-id="39f6f-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="39f6f-112">Sediakan sambungan ke Marketing</span><span class="sxs-lookup"><span data-stu-id="39f6f-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="39f6f-113">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="39f6f-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="39f6f-114">Pilih **Tambah sambungan** dan pilih **Dynamics 365 Marketing** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="39f6f-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="39f6f-115">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="39f6f-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="39f6f-116">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="39f6f-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="39f6f-117">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="39f6f-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="39f6f-118">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="39f6f-118">Choose who can use this connection.</span></span> <span data-ttu-id="39f6f-119">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="39f6f-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="39f6f-120">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="39f6f-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="39f6f-121">Masukkan URL Pemasaran organisasi anda dalam medan **Alamat pelayan**.</span><span class="sxs-lookup"><span data-stu-id="39f6f-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="39f6f-122">Dalam bahagian **Akaun pentadbir pelayan**, pilih **Daftar masuk** dan pilih akaun Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="39f6f-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="39f6f-123">Petakan medan ID pelanggan ke ID Kenalan Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="39f6f-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="39f6f-124">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="39f6f-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="39f6f-125">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="39f6f-125">Configure an export</span></span>

<span data-ttu-id="39f6f-126">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="39f6f-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="39f6f-127">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="39f6f-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="39f6f-128">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="39f6f-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="39f6f-129">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="39f6f-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="39f6f-130">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="39f6f-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="39f6f-131">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="39f6f-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="39f6f-132">Pilih satu atau lebih segmen.</span><span class="sxs-lookup"><span data-stu-id="39f6f-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="39f6f-133">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="39f6f-133">Select **Save**.</span></span>

<span data-ttu-id="39f6f-134">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="39f6f-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="39f6f-135">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="39f6f-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="39f6f-136">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="39f6f-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
