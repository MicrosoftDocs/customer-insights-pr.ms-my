---
title: Pengayaan dengan pengayaan pihak ketiga HERE Technologies
description: Maklumat umum tentang pengayaan pihak ketiga HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896062"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="2725e-103">Pengayaan profil pelanggan dengan HERE Technologies (pratonton)</span><span class="sxs-lookup"><span data-stu-id="2725e-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="2725e-104">HERE Technologies adalah syarikat platform lokasi yang menyediakan data dan perkhidmatan yang mengutamakan lokasi.</span><span class="sxs-lookup"><span data-stu-id="2725e-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="2725e-105">Dengan perkhidmatan pengayaan data HERE Technologies, anda boleh membina pemahaman lokasi yang lebih tepat tentang pelanggan anda dengan normalisasi alamat, latitud serta pengekstrakan longitud dan banyak lagi.</span><span class="sxs-lookup"><span data-stu-id="2725e-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2725e-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="2725e-106">Prerequisites</span></span>

<span data-ttu-id="2725e-107">Untuk mengkonfigurasi pengayaan HERE Technologies, prasyarat berikut mesti dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="2725e-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="2725e-108">Anda mempunyai langganan HERE Technologies yang aktif.</span><span class="sxs-lookup"><span data-stu-id="2725e-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="2725e-109">Untuk mendapatkan langganan, anda boleh [daftar di sini](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) atau [hubungi HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) secara terus.</span><span class="sxs-lookup"><span data-stu-id="2725e-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="2725e-110">Ketahui lebih lanjut tentang Pengayaan Lokasi HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="2725e-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="2725e-111">[Sambungan](connections.md) HERE tersedia *atau* anda mempunyai keizinan [pentadbir](permissions.md#administrator) dan kekunci API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="2725e-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="2725e-112">Konfigurasikan pengayaan</span><span class="sxs-lookup"><span data-stu-id="2725e-112">Configure the enrichment</span></span>

1. <span data-ttu-id="2725e-113">Pergi ke **Data** > **Pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="2725e-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="2725e-114">Pilih **Perkayakan data saya** pada jubin HERE Technologies dan pilih **Mari bermula**.</span><span class="sxs-lookup"><span data-stu-id="2725e-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2725e-115">![Jubin HERE Technologies](media/HERE-tile.png "Jubin HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="2725e-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="2725e-116">Pilih [sambungan](connections.md) daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="2725e-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="2725e-117">Hubungi pentadbir jika tiada sambungan tersedia.</span><span class="sxs-lookup"><span data-stu-id="2725e-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="2725e-118">Jika anda seorang pentadbir, anda boleh mencipta sambungan dengan memilih **Tambah sambungan**.</span><span class="sxs-lookup"><span data-stu-id="2725e-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="2725e-119">Pilih **HERE Technologies** dari menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="2725e-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="2725e-120">Pilih **Sambung ke HERE Technologies** untuk mengesahkan pilihan.</span><span class="sxs-lookup"><span data-stu-id="2725e-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="2725e-121">Pilih **Seterusnya** dan pilih **Set data pelanggan** yang anda mahu perkayakan dengan data lokasi daripada HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="2725e-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="2725e-122">Anda boleh memilih entiti **Pelanggan** untuk memperkayakan semua profil pelanggan anda atau pilih entiti segmen untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="2725e-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Tangkapan skrin apabila memilih set data pelanggan.":::

1. <span data-ttu-id="2725e-124">Pilih jika anda mahu memetakan medan kepada alamat utama dan/atau kedua.</span><span class="sxs-lookup"><span data-stu-id="2725e-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="2725e-125">Anda boleh menentukan pemetaan medan untuk kedua-dua alamat dan memperkayakan profil untuk kedua-dua alamat secara berasingan.</span><span class="sxs-lookup"><span data-stu-id="2725e-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="2725e-126">Contohnya, jika terdapat alamat rumah dan perniagaan.</span><span class="sxs-lookup"><span data-stu-id="2725e-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="2725e-127">Pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="2725e-127">Select **Next**.</span></span>

1. <span data-ttu-id="2725e-128">Takrifkan medan daripada profil disatukan yang perlu anda gunakan untuk mencari pemadanan data lokasi yang sepadan daripada HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="2725e-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="2725e-129">Medan **Jalan 1** dan **Poskod** diperlukan untuk alamat utama dan/atau sekunder yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="2725e-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="2725e-130">Untuk ketepatan padanan yang lebih tinggi, lebih banyak medan boleh ditambah.</span><span class="sxs-lookup"><span data-stu-id="2725e-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2725e-131">![Halaman konfigurasi pengayaan HERE Technologies](media/enrichment-HERE-configuration.png "Halaman konfigurasi pengayaan HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="2725e-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="2725e-132">Pilih **Seterusnya** untuk melengkapkan pemetaan medan.</span><span class="sxs-lookup"><span data-stu-id="2725e-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="2725e-133">Berikan nama untuk pengayaan.</span><span class="sxs-lookup"><span data-stu-id="2725e-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="2725e-134">1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.</span><span class="sxs-lookup"><span data-stu-id="2725e-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="2725e-135">Konfigurasikan sambungan untuk HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="2725e-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="2725e-136">Anda perlu menjadi pentadbir untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="2725e-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="2725e-137">Pilih **Tambah sambungan** apabila mengkonfigurasikan pengayaan *atau* pergi ke **Pentadbir** > **Sambungan** dan pilih **Sediakan** pada jubin HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="2725e-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="2725e-138">Masukkan nama untuk sambungan dalam kotak **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="2725e-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="2725e-139">Sediakan kekunci API HERE Technologies yang sah.</span><span class="sxs-lookup"><span data-stu-id="2725e-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="2725e-140">Semak dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="2725e-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="2725e-141">Pilih **Sahkan** untuk mengesahkan konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="2725e-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="2725e-142">Selepas melengkapkan pengesahan, pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="2725e-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="2725e-143">![Halaman konfigurasi sambungan HERE Technologies](media/enrichment-HERE-connection.png "Halaman konfigurasi sambungan HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="2725e-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2725e-144">Keputusan pengayaan</span><span class="sxs-lookup"><span data-stu-id="2725e-144">Enrichment results</span></span>

<span data-ttu-id="2725e-145">Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah.</span><span class="sxs-lookup"><span data-stu-id="2725e-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="2725e-146">Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2725e-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2725e-147">Masa pemprosesan akan bergantung pada saiz data pelanggan anda dan masa respons API daripada HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="2725e-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="2725e-148">Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="2725e-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="2725e-149">Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="2725e-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2725e-150">Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.</span><span class="sxs-lookup"><span data-stu-id="2725e-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2725e-151">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="2725e-151">Next steps</span></span>

<span data-ttu-id="2725e-152">Bina di atas data pelanggan anda yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="2725e-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2725e-153">Cipta [segmen](segments.md), [ukur](measures.md) dan juga [eksport data](export-destinations.md) untuk menghantar pengalaman diperibadikan kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="2725e-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2725e-154">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="2725e-154">Data privacy and compliance</span></span>

<span data-ttu-id="2725e-155">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke HERE Technologies, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="2725e-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2725e-156">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa HERE Technologies memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="2725e-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2725e-157">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2725e-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2725e-158">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="2725e-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
