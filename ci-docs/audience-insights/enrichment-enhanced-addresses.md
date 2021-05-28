---
title: Pengayaan peningkatan alamat
description: Perkayakan dan normalkan maklumat alamat profil pelanggan dengan model Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965589"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="19124-103">Pengayaan profil pelanggan dengan alamat yang dipertingkatkan</span><span class="sxs-lookup"><span data-stu-id="19124-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="19124-104">Alamat dalam data anda boleh tidak berstruktur, tidak lengkap atau tidak betul.</span><span class="sxs-lookup"><span data-stu-id="19124-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="19124-105">Gunakan model Microsoft untuk menormalkan dan memperkayakan alamat anda ke dalam [Format Model Data Tersuai](/common-data-model/schema/core/applicationcommon/address) untuk ketepatan dan wawasan yang lebih baik.</span><span class="sxs-lookup"><span data-stu-id="19124-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="19124-106">Cara kami mempertingkatkan alamat</span><span class="sxs-lookup"><span data-stu-id="19124-106">How we enhance addresses</span></span>

<span data-ttu-id="19124-107">Model kami akan melalui proses dua langkah untuk meningkatkan alamat.</span><span class="sxs-lookup"><span data-stu-id="19124-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="19124-108">Pertama, ia menghuraikan alamat untuk mengenal pasti komponennya dan menempatkannya ke dalam format berstruktur.</span><span class="sxs-lookup"><span data-stu-id="19124-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="19124-109">Kemudian kami menggunakan kecerdasan buatan untuk membetulkan, melengkapkan dan menyeragamkan nilai dalam alamat.</span><span class="sxs-lookup"><span data-stu-id="19124-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="19124-110">Contoh</span><span class="sxs-lookup"><span data-stu-id="19124-110">Example</span></span>

<span data-ttu-id="19124-111">Maklumat alamat mungkin dalam format yang tidak standard dan mengandungi ralat ejaan.</span><span class="sxs-lookup"><span data-stu-id="19124-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="19124-112">Model boleh membetulkan isu ini dan mencipta alamat yang konsisten dalam profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="19124-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="19124-113">Had</span><span class="sxs-lookup"><span data-stu-id="19124-113">Limitations</span></span>

<span data-ttu-id="19124-114">Alamat yang dipertingkatkan hanya berfungsi dengan nilai yang sudah wujud dalam data alamat diinges anda.</span><span class="sxs-lookup"><span data-stu-id="19124-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="19124-115">Model tidak:</span><span class="sxs-lookup"><span data-stu-id="19124-115">The model doesn't:</span></span> 

1. <span data-ttu-id="19124-116">Tentu sah jika alamat adalah alamat yang sah.</span><span class="sxs-lookup"><span data-stu-id="19124-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="19124-117">Sahkan Jika sebarang nilai seperti poskod atau nama jalan adalah sah.</span><span class="sxs-lookup"><span data-stu-id="19124-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="19124-118">Tukar nilai yang tidak dikenali.</span><span class="sxs-lookup"><span data-stu-id="19124-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="19124-119">Model menggunakan teknik berasaskan pembelajaran mesin untuk meningkatkan alamat.</span><span class="sxs-lookup"><span data-stu-id="19124-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="19124-120">Walaupun kami menggunakan ambang keyakinan tinggi apabila model mengubah nilai input seperti dengan mana-mana model yang berasaskan ML, ketepatan 100% tidak dijamin.</span><span class="sxs-lookup"><span data-stu-id="19124-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="19124-121">Negara atau rantau yang disokong</span><span class="sxs-lookup"><span data-stu-id="19124-121">Supported countries or regions</span></span>

<span data-ttu-id="19124-122">Kami kini menyokong memperkaya alamat dalam negara atau rantau ini:</span><span class="sxs-lookup"><span data-stu-id="19124-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="19124-123">Australia</span><span class="sxs-lookup"><span data-stu-id="19124-123">Australia</span></span>
- <span data-ttu-id="19124-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="19124-124">Canada</span></span>
- <span data-ttu-id="19124-125">United Kingdom</span><span class="sxs-lookup"><span data-stu-id="19124-125">United Kingdom</span></span>
- <span data-ttu-id="19124-126">Amerika Syarikat</span><span class="sxs-lookup"><span data-stu-id="19124-126">United States</span></span>

<span data-ttu-id="19124-127">Alamat mesti mengandungi nilai negara/rantau.</span><span class="sxs-lookup"><span data-stu-id="19124-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="19124-128">Kami tidak memproses alamat untuk negara atau rantau yang tidak disokong dan alamat yang tidak mempunyai negara atau rantau yang disediakan.</span><span class="sxs-lookup"><span data-stu-id="19124-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="19124-129">Konfigurasikan pengayaan</span><span class="sxs-lookup"><span data-stu-id="19124-129">Configure the enrichment</span></span>

1. <span data-ttu-id="19124-130">Pergi ke **Data** > **Pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="19124-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="19124-131">Pilih **Kayakan data saya** pada jubin **Alamat dipertingkatkan**.</span><span class="sxs-lookup"><span data-stu-id="19124-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Tangkapan skrin jubin alamat yang Dipertingkatkan.":::

1. <span data-ttu-id="19124-133">Pilih **Set data pelanggan** dan pilih entiti yang mengandungi alamat yang anda mahu perkayakan.</span><span class="sxs-lookup"><span data-stu-id="19124-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="19124-134">Anda boleh memilih entiti *Pelanggan* untuk memperkayakan alamat dalam semua profil pelanggan anda atau memilih entiti segmen untuk memperkayakan alamat hanya dalam profil pelanggan yang terkandung dalam segmen itu.</span><span class="sxs-lookup"><span data-stu-id="19124-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="19124-135">Pilih cara alamat diformatkan dalam set data anda.</span><span class="sxs-lookup"><span data-stu-id="19124-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="19124-136">Pilih **Alamat atribut tunggal** jika alamat dalam data anda menggunakan medan tunggal.</span><span class="sxs-lookup"><span data-stu-id="19124-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="19124-137">Pilih **Alamat berbilang atribut** jika alamat dalam data anda menggunakan lebih daripada satu medan data.</span><span class="sxs-lookup"><span data-stu-id="19124-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="19124-138">Negara/Rantau adalah mandatori dalam kedua-dua alamat atribut tunggal dan berbilang atribut.</span><span class="sxs-lookup"><span data-stu-id="19124-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="19124-139">Alamat yang tidak mengandungi nilai negara/rantau yang sah atau disokong tidak akan diperkaya</span><span class="sxs-lookup"><span data-stu-id="19124-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="19124-140">Petakan medan alamat daripada entiti pelanggan disatukan anda.</span><span class="sxs-lookup"><span data-stu-id="19124-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Halaman pemetaan medan alamat yang dipertingkatkan.":::

1. <span data-ttu-id="19124-142">Pilih **Seterusnya** untuk melengkapkan pemetaan medan.</span><span class="sxs-lookup"><span data-stu-id="19124-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="19124-143">Berikan nama untuk pengayaan dan entiti output.</span><span class="sxs-lookup"><span data-stu-id="19124-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="19124-144">Pilih **Simpan pengayaan** selepas menyemak pilihan anda.</span><span class="sxs-lookup"><span data-stu-id="19124-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="19124-145">Keputusan pengayaan</span><span class="sxs-lookup"><span data-stu-id="19124-145">Enrichment results</span></span>

<span data-ttu-id="19124-146">Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah.</span><span class="sxs-lookup"><span data-stu-id="19124-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="19124-147">Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="19124-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="19124-148">Masa pemprosesan bergantung pada saiz data pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="19124-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="19124-149">Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="19124-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="19124-150">Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="19124-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="19124-151">Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.</span><span class="sxs-lookup"><span data-stu-id="19124-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="19124-152">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="19124-152">Next steps</span></span>

<span data-ttu-id="19124-153">Bina di atas data pelanggan anda yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="19124-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="19124-154">Cipta [segmen](segments.md), [ukur](measures.md) dan juga [eksport data](export-destinations.md) untuk menghantar pengalaman diperibadikan kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="19124-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
