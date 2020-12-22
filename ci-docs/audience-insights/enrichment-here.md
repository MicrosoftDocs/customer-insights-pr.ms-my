---
title: Pengayaan dengan pengayaan pihak ketiga HERE Technologies
description: Maklumat umum tentang pengayaan pihak ketiga HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668689"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="c76c9-103">Pengayaan profil pelanggan dengan HERE Technologies (pratonton)</span><span class="sxs-lookup"><span data-stu-id="c76c9-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="c76c9-104">HERE Technologies adalah syarikat platform lokasi yang menyediakan data dan perkhidmatan yang mengutamakan lokasi.</span><span class="sxs-lookup"><span data-stu-id="c76c9-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="c76c9-105">Dengan perkhidmatan pengayaan data HERE Technologies, anda boleh membina pemahaman lokasi yang lebih tepat tentang pelanggan anda dengan normalisasi alamat, latitud serta pengekstrakan longitud dan banyak lagi.</span><span class="sxs-lookup"><span data-stu-id="c76c9-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c76c9-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="c76c9-106">Prerequisites</span></span>

<span data-ttu-id="c76c9-107">Untuk mengkonfigurasi pengayaan HERE Technologies, prasyarat berikut mesti dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="c76c9-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c76c9-108">Anda mempunyai langganan HERE Technologies yang aktif.</span><span class="sxs-lookup"><span data-stu-id="c76c9-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="c76c9-109">Untuk mendapatkan langganan, anda boleh [daftar di sini](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) atau [hubungi HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) secara terus.</span><span class="sxs-lookup"><span data-stu-id="c76c9-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="c76c9-110">Ketahui lebih lanjut tentang Pengayaan Lokasi HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c76c9-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="c76c9-111">Anda mempunyai kunci API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c76c9-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="c76c9-112">Anda mempunyai keizinan [Pentadbir](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="c76c9-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="c76c9-113">Konfigurasi</span><span class="sxs-lookup"><span data-stu-id="c76c9-113">Configuration</span></span>

1. <span data-ttu-id="c76c9-114">Pergi ke **Data** > **Pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="c76c9-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="c76c9-115">Pilih **Perkayakan data saya** pada jubin HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c76c9-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c76c9-116">![Jubin HERE Technologies](media/HERE-tile.png "Jubin HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="c76c9-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="c76c9-117">Masukkan **Kunci API HERE Technologies** yang aktif.</span><span class="sxs-lookup"><span data-stu-id="c76c9-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="c76c9-118">Semak semula dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="c76c9-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="c76c9-119">Sahkan kedua-dua input dengan memilih **Sambung ke HERE**.</span><span class="sxs-lookup"><span data-stu-id="c76c9-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="c76c9-120">Pilih **Tambah data** dan pilih jika anda mahu memetakan medan kepada alamat utama dan/atau sekunder.</span><span class="sxs-lookup"><span data-stu-id="c76c9-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="c76c9-121">Anda boleh menentukan pemetaan medan bagi kedua-dua alamat (contohnya, alamat rumah dan perniagaan) dan memperkayakan profil untuk kedua-dua alamat secara berasingan.</span><span class="sxs-lookup"><span data-stu-id="c76c9-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="c76c9-122">Pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="c76c9-122">Select **Next**.</span></span>

1. <span data-ttu-id="c76c9-123">Takrifkan medan daripada profil disatukan yang perlu anda gunakan untuk mencari pemadanan data lokasi yang sepadan daripada HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c76c9-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="c76c9-124">Medan **Jalan 1** dan **Poskod** diperlukan untuk alamat utama dan/atau sekunder yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="c76c9-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="c76c9-125">Untuk ketepatan padanan yang lebih tinggi, lebih banyak medan boleh ditambah.</span><span class="sxs-lookup"><span data-stu-id="c76c9-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c76c9-126">![Halaman konfigurasi pengayaan HERE Technologies](media/enrichment-HERE-configuration.png "Halaman konfigurasi pengayaan HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="c76c9-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="c76c9-127">Pilih **Gunakan** untuk melengkapkan pemetaan medan.</span><span class="sxs-lookup"><span data-stu-id="c76c9-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="c76c9-128">Keputusan pengayaan</span><span class="sxs-lookup"><span data-stu-id="c76c9-128">Enrichment results</span></span>

<span data-ttu-id="c76c9-129">Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah.</span><span class="sxs-lookup"><span data-stu-id="c76c9-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="c76c9-130">Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c76c9-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c76c9-131">Masa pemprosesan akan bergantung pada saiz data pelanggan anda dan masa respons API daripada HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c76c9-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="c76c9-132">Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="c76c9-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="c76c9-133">Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="c76c9-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c76c9-134">Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.</span><span class="sxs-lookup"><span data-stu-id="c76c9-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c76c9-135">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="c76c9-135">Next steps</span></span>

<span data-ttu-id="c76c9-136">Bina di atas data pelanggan anda yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="c76c9-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c76c9-137">Cipta [segmen](segments.md), [ukur](measures.md) dan juga [eksport data](export-destinations.md) untuk menghantar pengalaman diperibadikan kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="c76c9-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c76c9-138">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="c76c9-138">Data privacy and compliance</span></span>

<span data-ttu-id="c76c9-139">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke HERE Technologies, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="c76c9-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c76c9-140">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa HERE Technologies memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="c76c9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c76c9-141">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c76c9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c76c9-142">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="c76c9-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
