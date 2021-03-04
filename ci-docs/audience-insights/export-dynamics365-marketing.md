---
title: Eksport data Customer Insights ke Dynamics 365 Marketing
description: Ketahui bagaimana mengkonfigur sambungan ke Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269065"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="58599-103">Penyambung untuk Dynamics 365 Marketing (pratonton)</span><span class="sxs-lookup"><span data-stu-id="58599-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="58599-104">Gunakan [segmen](segments.md) untuk menjana kumpulan tertentu kempen dan kenalan pelanggan dengan Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="58599-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="58599-105">Untuk maklumat lanjut, lihat [Gunakan segmen daripada Dynamics 365 Customer Insights dengan Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="58599-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="58599-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="58599-106">Prerequisite</span></span>

- <span data-ttu-id="58599-107">Rekod kenalan mesti wujud dalam Dynamics 365 Marketing sebelum anda boleh mengeksport segmen daripada Customer Insights ke Pemasaran.</span><span class="sxs-lookup"><span data-stu-id="58599-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="58599-108">Baca lebih lanjut tentang cara untuk menginges kenalan dalam [Dynamics 365 Marketing menggunakan Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="58599-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="58599-109">Mengeksport segmen daripada wawasan khalayak kepada Pemasaran tidak akan mencipta rekod kenalan baharu dalam tika Pemasaran.</span><span class="sxs-lookup"><span data-stu-id="58599-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="58599-110">Rekod kenalan daripada Pemasaran mesti diinges dalam wawasan khalayak dan digunakan sebagai sumber data.</span><span class="sxs-lookup"><span data-stu-id="58599-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="58599-111">Mereka juga perlu dimasukkan dalam entiti Pelanggan disatukan untuk memetakan ID pelanggan kepada ID kenalan sebelum segmen boleh dieksport.</span><span class="sxs-lookup"><span data-stu-id="58599-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="58599-112">Konfigur penyambung untuk Pemasaran</span><span class="sxs-lookup"><span data-stu-id="58599-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="58599-113">Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.</span><span class="sxs-lookup"><span data-stu-id="58599-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="58599-114">Di bawah **Dynamics 365 Marketing**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="58599-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="58599-115">Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="58599-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="58599-116">Masukkan URL Pemasaran organisasi anda dalam medan **Alamat pelayan**.</span><span class="sxs-lookup"><span data-stu-id="58599-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="58599-117">Dalam bahagian **Akaun pentadbir pelayan**, pilih **Daftar masuk** dan pilih akaun Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="58599-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="58599-118">Petakan medan ID pelanggan ke ID Kenalan Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="58599-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="58599-119">Pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="58599-119">Select **Next**.</span></span>

1. <span data-ttu-id="58599-120">Pilih satu atau lebih segmen.</span><span class="sxs-lookup"><span data-stu-id="58599-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="58599-121">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="58599-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="58599-122">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="58599-122">Export the data</span></span>

<span data-ttu-id="58599-123">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="58599-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="58599-124">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="58599-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]