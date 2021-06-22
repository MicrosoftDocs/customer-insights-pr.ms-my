---
title: Eksport data Customer Insight kepada Campaign Monitor
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124192"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="45b06-103">Eksport segmen ke Campaign Monitor (pratonton)</span><span class="sxs-lookup"><span data-stu-id="45b06-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="45b06-104">Eksport segmen profil pelanggan yang disatukan ke Campaign Monitor dan gunakannya untuk aktiviti pemasaran.</span><span class="sxs-lookup"><span data-stu-id="45b06-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="45b06-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="45b06-105">Prerequisites</span></span>

-   <span data-ttu-id="45b06-106">Anda mempunyai [akaun Campaign Monitor](https://www.campaignmonitor.com/) dan kelayakan pentadbir yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="45b06-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="45b06-107">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="45b06-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="45b06-108">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="45b06-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="45b06-109">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="45b06-109">Known limitations</span></span>

- <span data-ttu-id="45b06-110">Anda boleh mengeksport hingga 1 juta profil setiap eksport ke Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="45b06-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="45b06-111">Mengeksport ke Campaign Monitor adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="45b06-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="45b06-112">Mengeksport hingga 1 juta profil ke Campaign Monitor boleh mengambil masa hingga 20 minit untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="45b06-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="45b06-113">Bilangan profil yang boleh anda eksport ke Campaign Monitor adalah bergantung dan terhad pada kontrak anda dengan Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="45b06-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="45b06-114">Sediakan sambungan ke Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="45b06-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="45b06-115">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="45b06-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="45b06-116">Pilih **Tambah sambungan** dan pilih **Campaign Monitor** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="45b06-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="45b06-117">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="45b06-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="45b06-118">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="45b06-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="45b06-119">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="45b06-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="45b06-120">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="45b06-120">Choose who can use this connection.</span></span> <span data-ttu-id="45b06-121">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="45b06-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="45b06-122">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="45b06-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="45b06-123">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="45b06-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="45b06-124">Pilih **Sambung** untuk memulakan sambungan ke Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="45b06-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="45b06-125">Pilih **Sahkan dengan Campaign Monitor** dan berikan kelayakan pentadbir anda untuk Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="45b06-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="45b06-126">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="45b06-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="45b06-127">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="45b06-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="45b06-128">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="45b06-128">Configure an export</span></span>

<span data-ttu-id="45b06-129">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="45b06-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="45b06-130">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="45b06-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="45b06-131">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="45b06-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="45b06-132">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="45b06-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="45b06-133">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="45b06-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="45b06-134">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="45b06-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="45b06-135">Masukkan [**ID Senarai Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) anda.</span><span class="sxs-lookup"><span data-stu-id="45b06-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="45b06-136">[Jana kekunci API](https://www.campaignmonitor.com/api/getting-started/) daripada **Tetapan Akaun** dalam Campaign Monitor dahulu untuk melihat ID senarai API.</span><span class="sxs-lookup"><span data-stu-id="45b06-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="45b06-137">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="45b06-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="45b06-138">Ia diperlukan untuk mengeksport segmen ke Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="45b06-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="45b06-139">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="45b06-139">Select **Save**.</span></span>

<span data-ttu-id="45b06-140">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="45b06-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="45b06-141">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="45b06-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="45b06-142">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="45b06-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="45b06-143">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="45b06-143">Data privacy and compliance</span></span>

<span data-ttu-id="45b06-144">Apabila anda mendayakan Dynamics 365 Customer Insights untuk memindahkan data ke Campaign Monitor, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="45b06-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="45b06-145">Microsoft akan memindahkan data tersebut atas arahan anda, tetapi anda bertanggungjawab untuk memastikan Campaign Monito memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki.</span><span class="sxs-lookup"><span data-stu-id="45b06-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="45b06-146">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="45b06-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="45b06-147">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="45b06-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
