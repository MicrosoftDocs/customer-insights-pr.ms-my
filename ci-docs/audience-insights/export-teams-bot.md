---
title: Bot untuk Microsoft Teams
description: Carian profil pelanggan disatukan dalam Microsoft Teams dengan bantuan bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267963"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="260df-103">Pasukan bot untuk Dynamics 365 Customer Insights (pratonton)</span><span class="sxs-lookup"><span data-stu-id="260df-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="260df-104">Sambung dengan Microsoft Teams untuk membolehkan bot mencari profil pelanggan disatukan dalam saluran Teams.</span><span class="sxs-lookup"><span data-stu-id="260df-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="260df-105">![Bot Teams menunjukkan rekod pelanggan](media/teams-bot.png "Bot Teams menunjukkan rekod pelanggan")</span><span class="sxs-lookup"><span data-stu-id="260df-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="260df-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="260df-106">Prerequisites</span></span>

<span data-ttu-id="260df-107">Untuk menyedia dan mengkonfigurasi bot, prasyarat berikut mesti dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="260df-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="260df-108">Sekurang-kurangnya satu [sumber data ditambah](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="260df-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="260df-109">[Proses penyatuan](data-unification.md) adalah lengkap.</span><span class="sxs-lookup"><span data-stu-id="260df-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="260df-110">Medan ditambah ke [indeks carian dan tapisan](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="260df-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="260df-111">Customer Insights dan Teams adalah dalam organisasi yang sama.</span><span class="sxs-lookup"><span data-stu-id="260df-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="260df-112">Konfigurasi bot</span><span class="sxs-lookup"><span data-stu-id="260df-112">Configure the bot</span></span>

1. <span data-ttu-id="260df-113">Dalam Insights khalayak, pergi ke **Pentadbir** > **Export Destinasi**.</span><span class="sxs-lookup"><span data-stu-id="260df-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="260df-114">Pada jubin Microsoft Teams, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="260df-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="260df-115">Anda dihalakan semula ke kawasan **Aplikasi** dalam Teams.</span><span class="sxs-lookup"><span data-stu-id="260df-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="260df-116">Anda juga boleh membuka Teams dan memilih **Aplikasi** di bahagian bawah sudut kiri atau [dapatkannya daripada AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) secara terus.</span><span class="sxs-lookup"><span data-stu-id="260df-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="260df-117">Cari **Customer Insights** dan pilih aplikasi.</span><span class="sxs-lookup"><span data-stu-id="260df-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="260df-118">Pilih **Tambah**.</span><span class="sxs-lookup"><span data-stu-id="260df-118">Select **Add**.</span></span>
1. <span data-ttu-id="260df-119">Selepas mendaftar masuk ke Customer Insights dalam Teams, anda akan melihat message selamat datang dan boleh bermula.</span><span class="sxs-lookup"><span data-stu-id="260df-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="260df-120">Perkara yang anda boleh lakukan dengan bot</span><span class="sxs-lookup"><span data-stu-id="260df-120">Things you can do with the bot</span></span>

<span data-ttu-id="260df-121">Bot menyediakan keupayaan carian untuk profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="260df-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="260df-122">Masukkan **Cari** diikuti dengan nama, alamat e-mel, atau mana-mana medan pada profil pelanggan disatukan yang ditambah ke indeks carian dan tapisan.</span><span class="sxs-lookup"><span data-stu-id="260df-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="260df-123">Anda akan mendapat kad dengan sehingga 15 medan daripada profil pelanggan yang terhasil.</span><span class="sxs-lookup"><span data-stu-id="260df-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="260df-124">Berbilang padanan mengembalikan senarai hasil di mana anda boleh memilih profil.</span><span class="sxs-lookup"><span data-stu-id="260df-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="260df-125">Anda boleh menambah istilah carian dalam petikan berganda untuk mencari padanan yang tepat.</span><span class="sxs-lookup"><span data-stu-id="260df-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="260df-126">Jika organisasi anda mengekalkan berbilang persekitaran Customer Insights dalam organisasi yang sama, anda boleh memasukkan **switchinstance** untuk memilih persekitaran yang anda mahu sambungkan bot tersebut.</span><span class="sxs-lookup"><span data-stu-id="260df-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="260df-127">Masukkan **bantuan** untuk melihat senarai perintah yang tersedia untuk bot.</span><span class="sxs-lookup"><span data-stu-id="260df-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]