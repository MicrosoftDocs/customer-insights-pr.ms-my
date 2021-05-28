---
title: Penyambung Power Automate | Microsoft Docs
description: Cipta aliran dalam Microsoft Power Automate daripada Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976099"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="ed88a-103">Penyambung Power Automate (pratonton)</span><span class="sxs-lookup"><span data-stu-id="ed88a-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="ed88a-104">Pencetus peristiwa khusus untuk berlaku secara automatik apabila data anda berubah dan uruskan aliran yang lebih kompleks dalam [Power Automate](https://flow.microsoft.com/) secara langsung.</span><span class="sxs-lookup"><span data-stu-id="ed88a-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="ed88a-105">Power Automate pencetus</span><span class="sxs-lookup"><span data-stu-id="ed88a-105">Power Automate triggers</span></span>

<span data-ttu-id="ed88a-106">Gunakan pencetus untuk mencipta aliran awan dan mengautomasikan tugas berulang, seperti pemberitahuan atau tindakan yang lebih lanjut.</span><span class="sxs-lookup"><span data-stu-id="ed88a-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="ed88a-107">Pencetus apabila muat semula sumber data gagal.</span><span class="sxs-lookup"><span data-stu-id="ed88a-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="ed88a-108">Pencetus apabila muat semula sumber data berjaya.</span><span class="sxs-lookup"><span data-stu-id="ed88a-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="ed88a-109">Pencetus apabila ambang bersilang pada segmen.</span><span class="sxs-lookup"><span data-stu-id="ed88a-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="ed88a-110">Pencetus dihadkan untuk melintas di atas ambang.</span><span class="sxs-lookup"><span data-stu-id="ed88a-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="ed88a-111">Pencetus apabila ambang bersilang pada ukuran perniagaan.</span><span class="sxs-lookup"><span data-stu-id="ed88a-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="ed88a-112">Hanya ukuran perniagaan tanpa dimensi disokong.</span><span class="sxs-lookup"><span data-stu-id="ed88a-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="ed88a-113">Pencetus dihadkan melintas di atas ambang.</span><span class="sxs-lookup"><span data-stu-id="ed88a-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="ed88a-114">Tercetus apabila segar semula penuh (sumber data, segmen, langkah,...) telah dilengkapkan.</span><span class="sxs-lookup"><span data-stu-id="ed88a-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="ed88a-115">Tercetus apabila segar semula proses penyatuan (peta, padan, cantum) selesai.</span><span class="sxs-lookup"><span data-stu-id="ed88a-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="ed88a-116">[Konfigurasikan pencetus anda dalam Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="ed88a-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="ed88a-117">Power Automate tindakan</span><span class="sxs-lookup"><span data-stu-id="ed88a-117">Power Automate actions</span></span>
<span data-ttu-id="ed88a-118">Penyambung Power Automate menyediakan tindakan lain selain pencetus yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="ed88a-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="ed88a-119">Untuk maklumat lanjut, lihat [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="ed88a-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="ed88a-120">Cipta aliran Power Automate</span><span class="sxs-lookup"><span data-stu-id="ed88a-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="ed88a-121">Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.</span><span class="sxs-lookup"><span data-stu-id="ed88a-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ed88a-122">Pada jubin **Power Automate**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="ed88a-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="ed88a-123">Penyambung Customer Insights (pratonton) dalam Power Automate terbuka.</span><span class="sxs-lookup"><span data-stu-id="ed88a-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="ed88a-124">**Log masuk** ke Power Automate.</span><span class="sxs-lookup"><span data-stu-id="ed88a-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="ed88a-125">Pilih salah satu pencetus yang ada dan tambahkan lebih banyak langkah ke aliran baharu anda.</span><span class="sxs-lookup"><span data-stu-id="ed88a-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="ed88a-126">Untuk maklumat lanjut, lihat [Cipta aliran awan dalam Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="ed88a-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="ed88a-127">Contoh cara menggunakan aliran:</span><span class="sxs-lookup"><span data-stu-id="ed88a-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="ed88a-128">Siarkan mesej ke saluran Microsoft Teams jika segar semula sumber data gagal.</span><span class="sxs-lookup"><span data-stu-id="ed88a-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="ed88a-129">Hantar e-mel kepada pemilik data apabila ambang pada segmen dilanggar.</span><span class="sxs-lookup"><span data-stu-id="ed88a-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
