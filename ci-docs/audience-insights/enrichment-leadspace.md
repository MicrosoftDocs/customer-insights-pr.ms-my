---
title: Pengayaan profil syarikat dengan ruang pengayaan pihak ketiga Leadspace
description: Maklumat umum tentang pengayaan pihak ketiga Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895924"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="0c250-103">Pengayaan profil syarikat dengan Leadspace (pratonton)</span><span class="sxs-lookup"><span data-stu-id="0c250-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="0c250-104">Leadspace ialah syarikat sains data yang menyediakan Platform Data Pelanggan B2B.</span><span class="sxs-lookup"><span data-stu-id="0c250-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="0c250-105">Ia membolehkan pelanggan dengan profil pelanggan yang disatukan untuk syarikat mengayakan data mereka.</span><span class="sxs-lookup"><span data-stu-id="0c250-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="0c250-106">Pengayaan termasuk lebih banyak atribut seperti saiz syarikat, lokasi, industri dan banyak lagi.</span><span class="sxs-lookup"><span data-stu-id="0c250-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0c250-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="0c250-107">Prerequisites</span></span>

<span data-ttu-id="0c250-108">Untuk mengkonfigurasikan Leadspace, prasyarat yang berikut mesti dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="0c250-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0c250-109">Anda mempunyai lesen Leadspace yang aktif.</span><span class="sxs-lookup"><span data-stu-id="0c250-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="0c250-110">Anda mempunyai [profil pelanggan yang disatukan](customer-profiles.md) untuk syarikat.</span><span class="sxs-lookup"><span data-stu-id="0c250-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="0c250-111">Sambungan Leadspace telah dikonfigurasikan oleh pentadbir atau anda mempunyai keizinan [pentadbir](permissions.md#administrator) dan "kunci kekal" (dirujuk sebagai **token Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="0c250-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="0c250-112">Hubungi [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) secara langsung untuk maklumat mengenai produk mereka.</span><span class="sxs-lookup"><span data-stu-id="0c250-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="0c250-113">Konfigurasikan pengayaan</span><span class="sxs-lookup"><span data-stu-id="0c250-113">Configure the enrichment</span></span>

1. <span data-ttu-id="0c250-114">Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="0c250-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="0c250-115">Pilih **Perkayakan data saya** pada jubin Leadspace dan pilih **Mari bermula**.</span><span class="sxs-lookup"><span data-stu-id="0c250-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Petikan skrin jubin Leadspace.":::

1. <span data-ttu-id="0c250-117">Pilih [sambungan](connections.md) daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="0c250-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="0c250-118">Hubungi pentadbir jika tiada sambungan tersedia.</span><span class="sxs-lookup"><span data-stu-id="0c250-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="0c250-119">Jika anda seorang pentadbir, anda boleh mencipta sambungan dengan memilih **Tambah sambungan** dan memilih **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="0c250-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="0c250-120">Pilih **Sambung ke Leadspace** untuk mengesahkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="0c250-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="0c250-121">Pilih **Seterusnya** dan pilih **Set data pelanggan** yang anda mahu perkayakan dengan data syarikat daripada Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0c250-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="0c250-122">Anda boleh memilih entiti **Pelanggan** untuk memperkayakan semua profil pelanggan anda atau pilih entiti segmen untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="0c250-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Tangkapan skrin apabila memilih set data pelanggan.":::

1. <span data-ttu-id="0c250-124">Pilih **Seterusnya** dan tentukan jenis medan daripada profil anda yang disatukan yang digunakan untuk mencari data demografi yang sepadan daripada Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0c250-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="0c250-125">Medan **Nama syarikat** diperlukan.</span><span class="sxs-lookup"><span data-stu-id="0c250-125">The **Name of company** field is required.</span></span> <span data-ttu-id="0c250-126">Untuk ketepatan padanan yang lebih tinggi hingga dua medan yang lain, **Tapak web syarikat** dan **Lokasi syarikat** boleh ditambah.</span><span class="sxs-lookup"><span data-stu-id="0c250-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Anak tetingkap pemetaan medan Leadspace.":::

1. <span data-ttu-id="0c250-128">Pilih **Seterusnya** untuk melengkapkan pemetaan medan.</span><span class="sxs-lookup"><span data-stu-id="0c250-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="0c250-129">Berikan nama untuk pengayaan dan pilih **Simpan pengayaan** selepas menyemak pilihan anda.</span><span class="sxs-lookup"><span data-stu-id="0c250-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="0c250-130">Konfigurasikan sambungan untuk Leadspace</span><span class="sxs-lookup"><span data-stu-id="0c250-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="0c250-131">Anda perlu menjadi pentadbir untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="0c250-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="0c250-132">Pilih **Tambah sambungan** apabila mengkonfigurasikan pengayaan *atau* pergi ke **Pentadbir** > **Sambungan** dan pilih **Sediakan** pada jubin Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0c250-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="0c250-133">Pilih **Mari Bermula**</span><span class="sxs-lookup"><span data-stu-id="0c250-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="0c250-134">Masukkan nama untuk sambungan dalam kotak **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="0c250-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="0c250-135">Berikan token Leadspace yang sah.</span><span class="sxs-lookup"><span data-stu-id="0c250-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="0c250-136">Semak dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="0c250-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="0c250-137">Pilih **Sahkan** untuk mengesahkan konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="0c250-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="0c250-138">Selepas melengkapkan pengesahan, pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="0c250-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Halaman konfigurasi sambungan Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="0c250-140">Keputusan pengayaan</span><span class="sxs-lookup"><span data-stu-id="0c250-140">Enrichment results</span></span>

<span data-ttu-id="0c250-141">Selepas penyegaran semula pengayaan, anda boleh mengulas data syarikat yang baru diperkayakan di bawah [Pengayaan saya](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="0c250-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="0c250-142">Anda boleh menemui masa kemas kini terakhir dan bilangan profil yang diperkayakan.</span><span class="sxs-lookup"><span data-stu-id="0c250-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0c250-143">Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.</span><span class="sxs-lookup"><span data-stu-id="0c250-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="0c250-144">Untuk maklumat lanjut, lihat [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="0c250-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0c250-145">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="0c250-145">Next steps</span></span>

<span data-ttu-id="0c250-146">Bina di atas data pelanggan anda yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="0c250-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0c250-147">Cipta [segmen](segments.md), [ukur](measures.md) dan juga [eksport data](export-destinations.md) untuk menghantar pengalaman diperibadikan kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="0c250-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0c250-148">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="0c250-148">Data privacy and compliance</span></span>

<span data-ttu-id="0c250-149">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Leadspace, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="0c250-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0c250-150">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Leadspace memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="0c250-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0c250-151">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0c250-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0c250-152">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="0c250-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
