---
title: Pengingesan data masa nyata dan pengehadan
description: Maklumat umum mengenai keupayaan masa nyata dalam wawasan khalayak.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598580"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="249e1-103">Pengingesan data masa nyata (pratonton)</span><span class="sxs-lookup"><span data-stu-id="249e1-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="249e1-104">Kefungsian hampir dengan masa nyata membolehkan anda melihat, dalam sekelip mata, interaksi terkini yang pelanggan anda telah lakukan dengan produk atau perkhidmatan anda.</span><span class="sxs-lookup"><span data-stu-id="249e1-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="249e1-105">[Menyegarkan semula yang dijadualkan](system.md#schedule-tab) termasuk bilangan rekod yang besar dan beberapa operasi kompleks.</span><span class="sxs-lookup"><span data-stu-id="249e1-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="249e1-106">Pertama, data ditarik daripada sumber data.</span><span class="sxs-lookup"><span data-stu-id="249e1-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="249e1-107">Seterusnya, data disatukan dan kemudian diperkaya dengan maklumat tambahan.</span><span class="sxs-lookup"><span data-stu-id="249e1-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="249e1-108">Setiap jalanan proses ini boleh mengambil masa berminit-minit hingga berjam-jam.</span><span class="sxs-lookup"><span data-stu-id="249e1-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="249e1-109">Kefungsian masa nyata menyediakan data dengan serta-merta untuk penggunaan, sehingga segar semula dijadualkan seterusnya menarik data ini daripada sumber data.</span><span class="sxs-lookup"><span data-stu-id="249e1-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="249e1-110">Kemas kini masa nyata mempunyai masa tamat tempoh dan selepas masa ini, ia tidak lagi menulis ganti nilai daripada sumber data:</span><span class="sxs-lookup"><span data-stu-id="249e1-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="249e1-111">Kemas kini profil akan disimpan selama 4 jam</span><span class="sxs-lookup"><span data-stu-id="249e1-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="249e1-112">Aktiviti akan disimpan selama 30 hari</span><span class="sxs-lookup"><span data-stu-id="249e1-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="249e1-113">Nilai ini ialah parameter panggilan API yang boleh anda ubah.</span><span class="sxs-lookup"><span data-stu-id="249e1-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="249e1-114">Ia bertujuan untuk memastikan data sumber anda mengekalkan sumber kepercayaan anda.</span><span class="sxs-lookup"><span data-stu-id="249e1-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="249e1-115">Jika anda mahu kemas kini masa nyata dimasukkan lebih lama, anda perlu menambahnya ke sumber data supaya ia akan ditarik semasa segar semula yang dijadualkan seterusnya.</span><span class="sxs-lookup"><span data-stu-id="249e1-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="249e1-116">Kemas kini masa nyata medan profil pelanggan yang disatukan</span><span class="sxs-lookup"><span data-stu-id="249e1-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="249e1-117">Profil yang dikemas kini akan ditunjukkan dalam pandangan kad pelanggan atau sebarang visualisasi lain dalam tempoh masa beberapa saat.</span><span class="sxs-lookup"><span data-stu-id="249e1-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="249e1-118">Oleh kerana operasi masa nyata berlaku selepas penyatuan data telah berlaku, ia hanya digunakan pada profil pelanggan yang disatukan.</span><span class="sxs-lookup"><span data-stu-id="249e1-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="249e1-119">Oleh sebab itu, perubahan profil masa nyata tidak akan mengemas kini langkah, keahlian bahagian atau pengayaan.</span><span class="sxs-lookup"><span data-stu-id="249e1-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="249e1-120">Had-had</span><span class="sxs-lookup"><span data-stu-id="249e1-120">Limitations</span></span>

- <span data-ttu-id="249e1-121">Profil pelanggan boleh dikemas kini tetapi tidak dicipta atau dipadamkan.</span><span class="sxs-lookup"><span data-stu-id="249e1-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="249e1-122">Mengeksport kemas kini masa nyata kepada sistem luaran, seperti Power BI, tidak boleh dilakukan pada masa ini.</span><span class="sxs-lookup"><span data-stu-id="249e1-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="249e1-123">Penciptaan aktiviti masa nyata</span><span class="sxs-lookup"><span data-stu-id="249e1-123">Real-time creation of activities</span></span>

<span data-ttu-id="249e1-124">API masa nyata membolehkan anda menerbitkan aktiviti baharu daripada sistem sumber anda (rekod sumber individu) kepada profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="249e1-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="249e1-125">Aktiviti baharu akan tersedia sebagai aktiviti yang disatukan dalam garis masa profil pelanggan yang disatukan dalam sekelip mata.</span><span class="sxs-lookup"><span data-stu-id="249e1-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="249e1-126">Anda boleh melihat garis masa dalam pandangan kad pelanggan atau sebarang integrasi garis masa lain yang anda konfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="249e1-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="249e1-127">Aktiviti adalah tidak berubah.</span><span class="sxs-lookup"><span data-stu-id="249e1-127">Activities are immutable.</span></span> <span data-ttu-id="249e1-128">Ia tidak berubah setelah dicipta.</span><span class="sxs-lookup"><span data-stu-id="249e1-128">They don't change once created.</span></span>
> - <span data-ttu-id="249e1-129">Pada masa ini, bahagian dan langkah tidak akan dikemas kini berdasarkan aktiviti baharu.</span><span class="sxs-lookup"><span data-stu-id="249e1-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="249e1-130">Aktiviti yang ditambahkan hanya melalui API masa nyata bukan sebahagian daripada eksport dan tidak akan ditunjukkan dalam Power BI.</span><span class="sxs-lookup"><span data-stu-id="249e1-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="249e1-131">Terdapat dua cara untuk sambung ke API masa nyata:</span><span class="sxs-lookup"><span data-stu-id="249e1-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="249e1-132">[secara tidak langsung](#connect-via-the-dynamics-365-customer-insights-connector), menggunakan [penyambung Dynamics 365 Customer Insights](/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="249e1-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="249e1-133">[secara langsung](#connect-directly-to-the-real-time-api), dengan kod</span><span class="sxs-lookup"><span data-stu-id="249e1-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="249e1-134">Kedua-dua cara berkongsi prasyarat yang berikut:</span><span class="sxs-lookup"><span data-stu-id="249e1-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="249e1-135">Persekitaran Customer Insights</span><span class="sxs-lookup"><span data-stu-id="249e1-135">A Customer Insights environment</span></span>
- <span data-ttu-id="249e1-136">Profil pelanggan yang disatukan</span><span class="sxs-lookup"><span data-stu-id="249e1-136">Unified customer profiles</span></span>
- <span data-ttu-id="249e1-137">Aktiviti dikonfigurasikan dan berjalan</span><span class="sxs-lookup"><span data-stu-id="249e1-137">Activities configured and run</span></span>
- <span data-ttu-id="249e1-138">Keizinan Penyumbang atau Pentadbir untuk mengesahkan akaun anda</span><span class="sxs-lookup"><span data-stu-id="249e1-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="249e1-139">Sambungkan melalui penyambung Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="249e1-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="249e1-140">API masa nyata boleh menginges data daripada sambungan Power Platform yang khusus, [penyambung Dynamics 365 Customer Insights](/connectors/customerinsights/), tanpa perlu menulis dan mengatur letak sebarang kod.</span><span class="sxs-lookup"><span data-stu-id="249e1-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="249e1-141">Penyambung boleh melakukan tindakan masa nyata yang sama seperti API.</span><span class="sxs-lookup"><span data-stu-id="249e1-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="249e1-142">Anda memerlukan lesen yang sah untuk penyambung premium.</span><span class="sxs-lookup"><span data-stu-id="249e1-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="249e1-143">Untuk maklumat lanjut, lihat [Soalan Lazim pelesenan Power Apps dan Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="249e1-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="249e1-144">Power Platform [Power Apps dan/atau Power Automate](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="249e1-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="249e1-145">Azure [Aplikasi Logik](/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="249e1-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="249e1-146">Untuk butiran tentang mencipta aliran, lihat [dokumentasi Power Automate](/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="249e1-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="249e1-147">Sambungkan secara langsung kepada API masa nyata</span><span class="sxs-lookup"><span data-stu-id="249e1-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="249e1-148">Anda boleh menggunakan keupayaan masa nyata dengan membina talian paip anda sendiri dan menyambung secara langsung ke API masa nyata.</span><span class="sxs-lookup"><span data-stu-id="249e1-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="249e1-149">Anda boleh menyiarkan aktiviti dalam format sistem sumber anda atau dalam format UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="249e1-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="249e1-150">Dapatkan format dengan membuat panggilan API kepada /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="249e1-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="249e1-151">Butiran API ini, termasuk parameter dan respons, boleh didapati dalam seksyen **EntityData** pada [Rujukan Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="249e1-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="249e1-152">Untuk mendapatkan maklumat lanjut, lihat [Kerja dengan Customer Insights API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="249e1-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="249e1-153">Memahami pengguna masa nyata anda dengan telemetri</span><span class="sxs-lookup"><span data-stu-id="249e1-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="249e1-154">Dapatkan gambaran keseluruhan jumlah permintaan kepada API masa nyata dan maklumat mengenai isu yang mungkin dihadapi oleh sistem.</span><span class="sxs-lookup"><span data-stu-id="249e1-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="249e1-155">Anda boleh [mengakses telemetri masa nyata](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="249e1-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]