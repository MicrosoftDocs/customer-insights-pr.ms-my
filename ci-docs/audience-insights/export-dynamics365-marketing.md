---
title: Eksport data Customer Insights ke Dynamics 365 Marketing
description: Ketahui bagaimana mengkonfigur sambungan ke Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597614"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="43ab6-103">Penyambung untuk Dynamics 365 Marketing (pratonton)</span><span class="sxs-lookup"><span data-stu-id="43ab6-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="43ab6-104">Gunakan [segmen](segments.md) untuk menjana kumpulan tertentu kempen dan kenalan pelanggan dengan Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="43ab6-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="43ab6-105">Untuk maklumat lanjut, lihat [Gunakan segmen daripada Dynamics 365 Customer Insights dengan Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="43ab6-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="43ab6-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="43ab6-106">Prerequisite</span></span>

- <span data-ttu-id="43ab6-107">Rekod kenalan mesti wujud dalam Dynamics 365 Marketing sebelum anda boleh mengeksport segmen daripada Customer Insights ke Pemasaran.</span><span class="sxs-lookup"><span data-stu-id="43ab6-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="43ab6-108">Baca lebih lanjut tentang cara untuk menginges kenalan dalam [Dynamics 365 Marketing menggunakan Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="43ab6-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="43ab6-109">Mengeksport segmen daripada wawasan khalayak kepada Pemasaran tidak akan mencipta rekod kenalan baharu dalam tika Pemasaran.</span><span class="sxs-lookup"><span data-stu-id="43ab6-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="43ab6-110">Rekod kenalan daripada Pemasaran mesti diinges dalam wawasan khalayak dan digunakan sebagai sumber data.</span><span class="sxs-lookup"><span data-stu-id="43ab6-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="43ab6-111">Mereka juga perlu dimasukkan dalam entiti Pelanggan disatukan untuk memetakan ID pelanggan kepada ID kenalan sebelum segmen boleh dieksport.</span><span class="sxs-lookup"><span data-stu-id="43ab6-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="43ab6-112">Konfigur penyambung untuk Pemasaran</span><span class="sxs-lookup"><span data-stu-id="43ab6-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="43ab6-113">Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.</span><span class="sxs-lookup"><span data-stu-id="43ab6-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="43ab6-114">Di bawah **Dynamics 365 Marketing**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="43ab6-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="43ab6-115">Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="43ab6-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="43ab6-116">Masukkan URL Pemasaran organisasi anda dalam medan **Alamat pelayan**.</span><span class="sxs-lookup"><span data-stu-id="43ab6-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="43ab6-117">Dalam bahagian **Akaun pentadbir pelayan**, pilih **Daftar masuk** dan pilih akaun Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="43ab6-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="43ab6-118">Petakan medan ID pelanggan ke ID Kenalan Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="43ab6-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="43ab6-119">Pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="43ab6-119">Select **Next**.</span></span>

1. <span data-ttu-id="43ab6-120">Pilih satu atau lebih segmen.</span><span class="sxs-lookup"><span data-stu-id="43ab6-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="43ab6-121">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="43ab6-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="43ab6-122">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="43ab6-122">Export the data</span></span>

<span data-ttu-id="43ab6-123">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="43ab6-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="43ab6-124">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="43ab6-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]