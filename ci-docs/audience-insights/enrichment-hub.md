---
title: Perkayakan profil pelanggan disatukan
description: Gunakan keupayaan untuk memperkayakan data pelanggan anda.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597706"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="d3699-103">Pengayaan untuk profil pelanggan (pratonton)</span><span class="sxs-lookup"><span data-stu-id="d3699-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="d3699-104">Gunakan data daripada sumber seperti Microsoft dan rakan kongsi lain untuk mengayakan data pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="d3699-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hab pengayaan":::

<span data-ttu-id="d3699-106">Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan** untuk bekerja dengan pilihan pengayaan.</span><span class="sxs-lookup"><span data-stu-id="d3699-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="d3699-107">Anda perlu mempunyai keizinan Penyumbang atau Pentadbir untuk mencipta atau mengedit pengayaan.</span><span class="sxs-lookup"><span data-stu-id="d3699-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="d3699-108">Untuk maklumat lanjut, lihat [Keizinan](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d3699-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="d3699-109">Pada tab **Temui**, anda akan menemui pengayaan yang berikut:</span><span class="sxs-lookup"><span data-stu-id="d3699-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="d3699-110">[Jenama](enrichment-microsoft-graph.md) disediakan oleh Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="d3699-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="d3699-111">[Kepentingan](enrichment-microsoft-graph.md) disediakan oleh Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="d3699-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="d3699-112">[Data syarikat](enrichment-leadspace.md) yang disediakan oleh Leadspace</span><span class="sxs-lookup"><span data-stu-id="d3699-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="d3699-113">[Demografik](enrichment-experian.md) disediakan oleh Experian</span><span class="sxs-lookup"><span data-stu-id="d3699-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="d3699-114">[Data lokasi](enrichment-here.md) yang disediakan oleh HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="d3699-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="d3699-115">[Data tersuai](enrichment-SFTP-custom-import.md) melalui Protokol Pemindahan Fail Selamat (SFTP)</span><span class="sxs-lookup"><span data-stu-id="d3699-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="d3699-116">Pada tab **Pengayaan saya**, anda boleh melihat pengayaan yang telah anda konfigurasikan dan mengedit sifatnya.</span><span class="sxs-lookup"><span data-stu-id="d3699-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="d3699-117">Mengurus pengayaan sedia ada</span><span class="sxs-lookup"><span data-stu-id="d3699-117">Manage existing enrichments</span></span>

<span data-ttu-id="d3699-118">Pergi ke **Pengayaan saya** untuk melihat semua pengayaan dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="d3699-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="d3699-119">Setiap pengayaan diwakili sebagai baris yang termasuk maklumat tambahan tentang pengayaan.</span><span class="sxs-lookup"><span data-stu-id="d3699-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="d3699-120">Pilih pengayaan untuk melihat pilihan tersedia.</span><span class="sxs-lookup"><span data-stu-id="d3699-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="d3699-121">Secara alternatif, anda boleh melihat elipsis (...) pada senarai item untuk melihat pilihan.</span><span class="sxs-lookup"><span data-stu-id="d3699-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Pilihan untuk mengurus pengayaan dalam senarai pengayaan":::

- <span data-ttu-id="d3699-123">**Lihat** butiran pengayaan dengan bilangan profil pelanggan yang dikayakan.</span><span class="sxs-lookup"><span data-stu-id="d3699-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="d3699-124">**Edit** konfigurasi pengayaan.</span><span class="sxs-lookup"><span data-stu-id="d3699-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="d3699-125">**Jalankan** pengayaan untuk mengemas kini profil pelanggan dengan data terkini.</span><span class="sxs-lookup"><span data-stu-id="d3699-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="d3699-126">**Nyahaktifkan** pengayaan sedia ada untuk menghentikannya daripada penyegaran semula secara automatik dengan setiap segar semula dijadualkan.</span><span class="sxs-lookup"><span data-stu-id="d3699-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="d3699-127">Data daripada segar semula terakhir yang berjaya akan terus tersedia.</span><span class="sxs-lookup"><span data-stu-id="d3699-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="d3699-128">**Aktifkan** pengayaan yang tidak aktif untuk memulakan semula penyegaran semula secara automatik dengan setiap segar semula dijadualkan.</span><span class="sxs-lookup"><span data-stu-id="d3699-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="d3699-129">**Padam** pengayaan.</span><span class="sxs-lookup"><span data-stu-id="d3699-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="d3699-130">Anda boleh menjalankan atau menyahaktifkan berbilang pengayaan sekaligus dengan memilihnya dalam senarai.</span><span class="sxs-lookup"><span data-stu-id="d3699-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="d3699-131">Pilihan lihat dan edit tidak tersedia sebagai tindakan pukal dan hanya berfungsi untuk satu pengayaan dalam satu masa.</span><span class="sxs-lookup"><span data-stu-id="d3699-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]