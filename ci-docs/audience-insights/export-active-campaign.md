---
title: Eksport Data Customer Insights pada ActiveCampaign
description: Ketahui cara mengkonfigurasikan sambungan dan mengeksport pada ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314650"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="e1ce6-103">Eksport segmen pada ActiveCampaign (pratonton)</span><span class="sxs-lookup"><span data-stu-id="e1ce6-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="e1ce6-104">Eksport segmen profil pelanggan disatukan pada ActiveCampaign dan gunakan segmen itu untuk aktiviti pemasaran.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e1ce6-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="e1ce6-105">Prerequisites</span></span>

-   <span data-ttu-id="e1ce6-106">Anda mempunyai [Akaun ActiveCampaign](https://www.activecampaign.com/) dan kelayakan pentadbir yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e1ce6-107">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e1ce6-108">Profil pelanggan yang disatukan dalam segmen yang dieksport mengandungi medan dengan alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e1ce6-109">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="e1ce6-109">Known limitations</span></span>

- <span data-ttu-id="e1ce6-110">Anda boleh mengeksport hingga 1 juta profil setiap eksport pada ActiveCampaign dan ini boleh mengambil masa hingga 90 minit untuk selesai.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="e1ce6-111">Mengeksport pada ActiveCampaign terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="e1ce6-112">Bilangan profil yang boleh anda eksport pada ActiveCampaign bergantung pada kontrak anda dengan ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="e1ce6-113">Sediakan sambungan kepada ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="e1ce6-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="e1ce6-114">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e1ce6-115">Pilih **Tambah sambungan**  dan pilih **ActiveCampaign**  untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="e1ce6-116">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e1ce6-117">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e1ce6-118">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e1ce6-119">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-119">Choose who can use this connection.</span></span> <span data-ttu-id="e1ce6-120">Secara lalai, ia hanya pentadbir.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-120">By default, it's only administrators.</span></span> <span data-ttu-id="e1ce6-121">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e1ce6-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e1ce6-122">Masukkan [Kekunci API ActiveCampaign dan Nama Hos Titik Tamat REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) anda.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="e1ce6-123">Nama hos Titik tamat REST adalah nama hos sahaja tanpa https://.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="e1ce6-124">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e1ce6-125">Pilih **Sambung** kepada memulakan untuk mengesahkan sambungan kepada ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="e1ce6-126">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e1ce6-127">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e1ce6-128">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="e1ce6-128">Configure an export</span></span>

<span data-ttu-id="e1ce6-129">Anda boleh mengkonfigurasikan eksport jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="e1ce6-130">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e1ce6-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e1ce6-131">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e1ce6-132">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e1ce6-133">Dalam medan **Sambungan untuk mengeksport**, pilih sambungan daripada bahagian ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="e1ce6-134">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e1ce6-135">Masukkan [**ID Senarai ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="e1ce6-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="e1ce6-136">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e1ce6-137">Ini diperlukan untuk mengeksport segmen pada ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="e1ce6-138">Sebagai pilihan, anda boleh mengeksport Nama pertama, Nama akhir dan Telefon untuk mencipta e-mel yang lebih diperibadikan.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="e1ce6-139">Pilih Tambah atribut untuk memetakan medan ini.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="e1ce6-140">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-140">Select **Save**.</span></span>

<span data-ttu-id="e1ce6-141">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e1ce6-142">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e1ce6-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e1ce6-143">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e1ce6-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e1ce6-144">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="e1ce6-144">Data privacy and compliance</span></span>

<span data-ttu-id="e1ce6-145">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data kepada ActiveCampaign, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif yang berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e1ce6-146">Microsoft akan memindahkan data tersebut atas arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa ActiveCampaign memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e1ce6-147">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e1ce6-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e1ce6-148">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="e1ce6-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
