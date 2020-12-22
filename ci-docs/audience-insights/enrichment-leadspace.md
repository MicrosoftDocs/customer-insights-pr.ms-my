---
title: Pengayaan profil syarikat dengan ruang pengayaan pihak ketiga Leadspace
description: Maklumat umum tentang pengayaan pihak ketiga Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668734"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="fa49d-103">Pengayaan profil syarikat dengan Leadspace (pratonton)</span><span class="sxs-lookup"><span data-stu-id="fa49d-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="fa49d-104">Leadspace ialah syarikat sains data yang menyediakan Platform Data Pelanggan B2B.</span><span class="sxs-lookup"><span data-stu-id="fa49d-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="fa49d-105">Ia membolehkan pelanggan dengan profil pelanggan yang disatukan untuk syarikat mengayakan data mereka.</span><span class="sxs-lookup"><span data-stu-id="fa49d-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="fa49d-106">Pengayaan merangkumi atribut tambahan seperti saiz syarikat, lokasi, industri dan banyak lagi.</span><span class="sxs-lookup"><span data-stu-id="fa49d-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fa49d-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="fa49d-107">Prerequisites</span></span>

<span data-ttu-id="fa49d-108">Untuk mengkonfigurasikan Leadspace, prasyarat yang berikut mesti dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="fa49d-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="fa49d-109">Anda mempunyai lesen Leadspace yang aktif dan “kunci kekal” (dirujuk sebagai **Token Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="fa49d-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="fa49d-110">Hubungi terus [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) untuk butiran tentang produk mereka.</span><span class="sxs-lookup"><span data-stu-id="fa49d-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="fa49d-111">Anda mempunyai keizinan [Pentadbir](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="fa49d-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="fa49d-112">Anda mempunyai [profil pelanggan yang disatukan](customer-profiles.md) untuk syarikat.</span><span class="sxs-lookup"><span data-stu-id="fa49d-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="fa49d-113">Konfigurasi</span><span class="sxs-lookup"><span data-stu-id="fa49d-113">Configuration</span></span>

1. <span data-ttu-id="fa49d-114">Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="fa49d-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="fa49d-115">Pilih **Perkayakan data saya** pada jubin Leadspace.</span><span class="sxs-lookup"><span data-stu-id="fa49d-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Petikan skrin jubin Leadspace.":::

1. <span data-ttu-id="fa49d-117">Pilih **Mari Bermula** dan kemudian masukkan **token Leadspace** aktif (kunci kekal).</span><span class="sxs-lookup"><span data-stu-id="fa49d-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="fa49d-118">Semak semula dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="fa49d-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="fa49d-119">Sahkan kedua-dua input dengan memilih **Sambung ke Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="fa49d-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="fa49d-120">Pilih **Peta data** dan takrifkan medan yang hendak digunakan daripada profil disatukan untuk memadankan data syarikat Leadspace.</span><span class="sxs-lookup"><span data-stu-id="fa49d-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="fa49d-121">Medan **Nama syarikat** diperlukan.</span><span class="sxs-lookup"><span data-stu-id="fa49d-121">The **Name of company** field is required.</span></span> <span data-ttu-id="fa49d-122">Untuk ketepatan padanan yang lebih tinggi hingga dua medan yang lain, **Tapak web syarikat** dan **Lokasi syarikat** boleh ditambah.</span><span class="sxs-lookup"><span data-stu-id="fa49d-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Anak tetingkap pemetaan medan Leadspace.":::
   
1. <span data-ttu-id="fa49d-124">Pilih **Gunakan** untuk melengkapkan pemetaan medan.</span><span class="sxs-lookup"><span data-stu-id="fa49d-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="fa49d-125">Pilih **Jalankan** untuk mengayakan profil syarikat.</span><span class="sxs-lookup"><span data-stu-id="fa49d-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="fa49d-126">Tempoh yang diambil oleh pengayaan bergantung kepada bilangan profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="fa49d-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="fa49d-127">Keputusan pengayaan</span><span class="sxs-lookup"><span data-stu-id="fa49d-127">Enrichment results</span></span>

<span data-ttu-id="fa49d-128">Selepas penyegaran semula pengayaan, anda boleh mengulas data syarikat yang baru diperkayakan di bawah [Pengayaan saya](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="fa49d-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="fa49d-129">Anda boleh menemui masa kemas kini terakhir dan bilangan profil yang diperkayakan.</span><span class="sxs-lookup"><span data-stu-id="fa49d-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="fa49d-130">Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.</span><span class="sxs-lookup"><span data-stu-id="fa49d-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="fa49d-131">Untuk maklumat lanjut, lihat [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="fa49d-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fa49d-132">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="fa49d-132">Next steps</span></span>

<span data-ttu-id="fa49d-133">Bina di atas data pelanggan anda yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="fa49d-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fa49d-134">Cipta [segmen](segments.md), [ukur](measures.md) dan juga [eksport data](export-destinations.md) untuk menghantar pengalaman diperibadikan kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="fa49d-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fa49d-135">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="fa49d-135">Data privacy and compliance</span></span>

<span data-ttu-id="fa49d-136">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Leadspace, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="fa49d-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fa49d-137">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Leadspace memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="fa49d-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fa49d-138">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fa49d-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fa49d-139">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="fa49d-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>