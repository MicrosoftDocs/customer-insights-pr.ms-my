---
title: Penyambung Power Automate | Microsoft Docs
description: Mencipta aliran dalam Microsoft Power Automate daripada Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406434"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="241ba-103">Penyambung Power Automate (pratonton)</span><span class="sxs-lookup"><span data-stu-id="241ba-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="241ba-104">Pencetus peristiwa khusus untuk berlaku secara automatik apabila data anda berubah dan uruskan aliran yang lebih kompleks dalam [Power Automate](https://flow.microsoft.com/) secara langsung.</span><span class="sxs-lookup"><span data-stu-id="241ba-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="241ba-105">Power Automate pencetus</span><span class="sxs-lookup"><span data-stu-id="241ba-105">Power Automate triggers</span></span>

<span data-ttu-id="241ba-106">Anda boleh menggunakan pelbagai pencetus yang membolehkan anda mencipta aliran untuk mengautomatikkan tugas berulang, seperti pemberitahuan atau tindakan yang lebih lanjut.</span><span class="sxs-lookup"><span data-stu-id="241ba-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="241ba-107">Pencetus apabila muat semula sumber data gagal.</span><span class="sxs-lookup"><span data-stu-id="241ba-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="241ba-108">Pencetus apabila muat semula sumber data berjaya.</span><span class="sxs-lookup"><span data-stu-id="241ba-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="241ba-109">Pencetus apabila ambang bersilang pada segmen.</span><span class="sxs-lookup"><span data-stu-id="241ba-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="241ba-110">Pencetus dihadkan untuk melintas di atas ambang.</span><span class="sxs-lookup"><span data-stu-id="241ba-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="241ba-111">Pencetus apabila ambang bersilang pada ukuran perniagaan.</span><span class="sxs-lookup"><span data-stu-id="241ba-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="241ba-112">Pencetus dihadkan melintas di atas ambang.</span><span class="sxs-lookup"><span data-stu-id="241ba-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="241ba-113">Tercetus apabila segar semula penuh (sumber data, segmen, langkah,...) telah dilengkapkan.</span><span class="sxs-lookup"><span data-stu-id="241ba-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="241ba-114">Tercetus apabila segar semula proses penyatuan (peta, padan, cantum) selesai.</span><span class="sxs-lookup"><span data-stu-id="241ba-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="241ba-115">[Konfigurasikan pencetus anda dalam Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="241ba-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="241ba-116">Power Automate tindakan</span><span class="sxs-lookup"><span data-stu-id="241ba-116">Power Automate actions</span></span>
<span data-ttu-id="241ba-117">Penyambung Power Automate menyediakan tindakan lain selain pencetus yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="241ba-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="241ba-118">Untuk maklumat lanjut, lihat [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="241ba-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="241ba-119">Cipta aliran Power Automate dalam Insights khalayak</span><span class="sxs-lookup"><span data-stu-id="241ba-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="241ba-120">Dalam Insights khalayak, pergi ke **Pentadbir** > **Sistem**.</span><span class="sxs-lookup"><span data-stu-id="241ba-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="241ba-121">Pada halaman **Sistem**, pilih tab **Status**.</span><span class="sxs-lookup"><span data-stu-id="241ba-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="241ba-122">Dalam bahagian **Sumber Data**, pilih **Aliran** dan pilih **Cipta aliran** daripada senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="241ba-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="241ba-123">Penyambung ![Power Automate menunjukan tindakan Mencipta Aliran](media/power-automate-connector-create-flow.png "Penyambung Power Automate menunjukkan tindakan Cipta Aliran")</span><span class="sxs-lookup"><span data-stu-id="241ba-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="241ba-124">Dalam Power Automate, pilih salah satu daripada pencetus yang tersedia untuk mencipta aliran keutamaan anda.</span><span class="sxs-lookup"><span data-stu-id="241ba-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="241ba-125">Jika anda sedang mencipta aliran pertama anda, anda akan perlu membuat pengesahan dengan penyambung Power Automate terlebih dahulu.</span><span class="sxs-lookup"><span data-stu-id="241ba-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
