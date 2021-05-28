---
title: Perkayakan profil pelanggan disatukan
description: Gunakan keupayaan untuk memperkayakan data pelanggan anda.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954498"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="a23ca-103">Pengayaan untuk profil pelanggan (pratonton)</span><span class="sxs-lookup"><span data-stu-id="a23ca-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="a23ca-104">Gunakan data daripada sumber seperti Microsoft dan rakan kongsi lain untuk mengayakan data pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="a23ca-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hab pengayaan":::

<span data-ttu-id="a23ca-106">Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan** untuk bekerja dengan pilihan pengayaan.</span><span class="sxs-lookup"><span data-stu-id="a23ca-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="a23ca-107">Anda perlu mempunyai keizinan Penyumbang atau Pentadbir untuk mencipta atau mengedit pengayaan.</span><span class="sxs-lookup"><span data-stu-id="a23ca-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="a23ca-108">Untuk maklumat lanjut, lihat [Keizinan](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a23ca-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="a23ca-109">Pada tab **Temui**, anda akan menemui pengayaan yang berikut:</span><span class="sxs-lookup"><span data-stu-id="a23ca-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="a23ca-110">[Jenama](enrichment-microsoft.md) disediakan oleh Microsoft</span><span class="sxs-lookup"><span data-stu-id="a23ca-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="a23ca-111">[Minat](enrichment-microsoft.md) disediakan oleh Microsoft</span><span class="sxs-lookup"><span data-stu-id="a23ca-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="a23ca-112">[Alamat dipertingkatkan](enrichment-enhanced-addresses.md) yang disediakan oleh Microsoft</span><span class="sxs-lookup"><span data-stu-id="a23ca-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="a23ca-113">[Data syarikat](enrichment-leadspace.md) yang disediakan oleh Leadspace</span><span class="sxs-lookup"><span data-stu-id="a23ca-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="a23ca-114">[Demografik](enrichment-experian.md) disediakan oleh Experian</span><span class="sxs-lookup"><span data-stu-id="a23ca-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="a23ca-115">[Data lokasi](enrichment-here.md) yang disediakan oleh HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="a23ca-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="a23ca-116">[Data tersuai](enrichment-SFTP-custom-import.md) melalui Protokol Pemindahan Fail Selamat (SFTP)</span><span class="sxs-lookup"><span data-stu-id="a23ca-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="a23ca-117">Pada tab **Pengayaan saya**, anda boleh melihat pengayaan yang telah anda konfigurasikan dan mengedit sifatnya.</span><span class="sxs-lookup"><span data-stu-id="a23ca-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="a23ca-118">Mengurus pengayaan sedia ada</span><span class="sxs-lookup"><span data-stu-id="a23ca-118">Manage existing enrichments</span></span>

<span data-ttu-id="a23ca-119">Pergi ke **Pengayaan saya** untuk melihat semua pengayaan dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="a23ca-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="a23ca-120">Setiap pengayaan diwakili sebagai baris yang termasuk maklumat tambahan tentang pengayaan.</span><span class="sxs-lookup"><span data-stu-id="a23ca-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="a23ca-121">Pilih pengayaan untuk melihat pilihan tersedia.</span><span class="sxs-lookup"><span data-stu-id="a23ca-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="a23ca-122">Anda juga boleh memilih elipsis (...) pada item senarai untuk melihat pilihan.</span><span class="sxs-lookup"><span data-stu-id="a23ca-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Pilihan untuk mengurus pengayaan dalam senarai pengayaan":::

- <span data-ttu-id="a23ca-124">**Lihat** butiran pengayaan dengan bilangan profil pelanggan yang dikayakan.</span><span class="sxs-lookup"><span data-stu-id="a23ca-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="a23ca-125">**Edit** konfigurasi pengayaan.</span><span class="sxs-lookup"><span data-stu-id="a23ca-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="a23ca-126">**Jalankan** pengayaan untuk mengemas kini profil pelanggan dengan data terkini.</span><span class="sxs-lookup"><span data-stu-id="a23ca-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="a23ca-127">**Nyahaktifkan** pengayaan sedia ada untuk menghentikannya daripada penyegaran semula secara automatik dengan setiap segar semula dijadualkan.</span><span class="sxs-lookup"><span data-stu-id="a23ca-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="a23ca-128">Data daripada segar semula terakhir yang berjaya akan terus tersedia.</span><span class="sxs-lookup"><span data-stu-id="a23ca-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="a23ca-129">**Aktifkan** pengayaan yang tidak aktif untuk memulakan semula penyegaran semula secara automatik dengan setiap segar semula dijadualkan.</span><span class="sxs-lookup"><span data-stu-id="a23ca-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="a23ca-130">**Padam** pengayaan.</span><span class="sxs-lookup"><span data-stu-id="a23ca-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="a23ca-131">Anda boleh menjalankan atau menyahaktifkan berbilang pengayaan sekaligus dengan memilihnya dalam senarai.</span><span class="sxs-lookup"><span data-stu-id="a23ca-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="a23ca-132">Pilihan lihat dan edit tidak tersedia sebagai tindakan pukal dan hanya berfungsi untuk satu pengayaan dalam satu masa.</span><span class="sxs-lookup"><span data-stu-id="a23ca-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="a23ca-133">Sambungan untuk pengayaan</span><span class="sxs-lookup"><span data-stu-id="a23ca-133">Enrichments and connections</span></span>

<span data-ttu-id="a23ca-134">Pengayaan pihak ketiga dikonfigurasikan menggunakan [sambungan](connections.md), yang mana pentadbir menyediakan kelayakan dan persetujuan untuk pindahan data.</span><span class="sxs-lookup"><span data-stu-id="a23ca-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="a23ca-135">Sambungan boleh digunakan oleh pentadbir dan penyumbang untuk mengkonfigurasikan pengayaan.</span><span class="sxs-lookup"><span data-stu-id="a23ca-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="a23ca-136">Pelbagai pengayaan untuk jenis yang sama</span><span class="sxs-lookup"><span data-stu-id="a23ca-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="a23ca-137">Entiti yang akan diperkaya ditentukan semasa konfigurasi pengayaan, yang membolehkan anda memperkayakan hanya subset profil anda.</span><span class="sxs-lookup"><span data-stu-id="a23ca-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="a23ca-138">Contohnya, memperkayakan data hanya untuk segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="a23ca-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="a23ca-139">Anda boleh mengkonfigurasikan beberapa pengayaan jenis yang sama dan menggunakan semula sambungan yang sama.</span><span class="sxs-lookup"><span data-stu-id="a23ca-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="a23ca-140">Sesetengah pengayaan mempunyai had bilangan pengayaan jenis yang sama yang boleh dicipta.</span><span class="sxs-lookup"><span data-stu-id="a23ca-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="a23ca-141">Had dan penggunaan semasa boleh dilihat pada halaman **Pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="a23ca-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
