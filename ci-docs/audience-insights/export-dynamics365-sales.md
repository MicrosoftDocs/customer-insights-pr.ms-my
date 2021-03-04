---
title: Eksport data Customer Insights ke Dynamics 365 Sales
description: Ketahui bagaimana mengkonfigur sambungan ke Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269019"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="bb0f3-103">Penyambung untuk Dynamics 365 Sales (pratonton)</span><span class="sxs-lookup"><span data-stu-id="bb0f3-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bb0f3-104">Gunakan data pelanggan anda untuk mencipta senarai pemasaran, menyusuli aliran kerja dan menghantar promosi dengan Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="bb0f3-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="bb0f3-105">Prerequisite</span></span>

1. <span data-ttu-id="bb0f3-106">Rekod kenalan mesti wujud dalam Dynamics 365 Sales sebelum anda boleh mengeksport segmen daripada Customer Insights ke Jualan.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="bb0f3-107">Baca lebih lanjut tentang cara untuk menginges kenalan dalam [Dynamics 365 Sales menggunakan Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="bb0f3-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="bb0f3-108">Mengeksport segmen daripada wawasan khalayak kepada Jualan tidak akan mencipta rekod kenalan baharu dalam tika Jualan.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="bb0f3-109">Rekod kenalan daripada Jualan mesti diinges dalam wawasan khalayak dan digunakan sebagai sumber data.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="bb0f3-110">Mereka juga perlu dimasukkan dalam entiti Pelanggan disatukan untuk memetakan ID pelanggan kepada ID kenalan sebelum segmen boleh dieksport.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="bb0f3-111">Konfigur penyambung untuk Jualan</span><span class="sxs-lookup"><span data-stu-id="bb0f3-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="bb0f3-112">Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bb0f3-113">Di bawah **Dynamics 365 Sales**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="bb0f3-114">Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="bb0f3-115">Masukkan URL Jualan organisasi anda dalam medan **Alamat pelayan**.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="bb0f3-116">Dalam bahagian **Akaun pentadbir pelayan**, pilih **Daftar masuk** dan pilih akaun Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="bb0f3-117">Petakan medan ID pelanggan ke ID Kenalan Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="bb0f3-118">Pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-118">Select **Next**.</span></span>

1. <span data-ttu-id="bb0f3-119">Pilih satu atau lebih segmen.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="bb0f3-120">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="bb0f3-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="bb0f3-121">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="bb0f3-121">Export the data</span></span>

<span data-ttu-id="bb0f3-122">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bb0f3-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="bb0f3-123">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bb0f3-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]