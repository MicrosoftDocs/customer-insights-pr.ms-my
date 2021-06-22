---
title: Eksport data Customer Insights ke AdRoll
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124376"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="e4900-103">Eksport segmen ke AdRoll (pratonton)</span><span class="sxs-lookup"><span data-stu-id="e4900-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="e4900-104">Eksport segmen profil pelanggan yang disatukan ke AdRoll dan gunakan segmen tersebut untuk pengiklanan.</span><span class="sxs-lookup"><span data-stu-id="e4900-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e4900-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="e4900-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e4900-106">Anda mempunyai [Akaun AdRoll](https://www.adroll.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="e4900-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e4900-107">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="e4900-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e4900-108">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="e4900-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e4900-109">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="e4900-109">Known limitations</span></span>

- <span data-ttu-id="e4900-110">Anda boleh mengeksport hingga 250,000 profil bagi setiap eksport ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e4900-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="e4900-111">Anda tidak boleh mengeksport segmen yang kurang daripada 100 profil ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e4900-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="e4900-112">Mengeksport ke AdRoll adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="e4900-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="e4900-113">Mengeksport hingga 250,000 profil ke AdRoll mungkin mengambil masa hingga 10 minit untuk selesai.</span><span class="sxs-lookup"><span data-stu-id="e4900-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="e4900-114">Bilangan profil yang boleh anda eksport ke AdRoll bergantung dan terhad pada kontrak anda dengan AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e4900-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="e4900-115">Sediakan sambungan ke AdRoll</span><span class="sxs-lookup"><span data-stu-id="e4900-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="e4900-116">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="e4900-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e4900-117">Pilih **Tambah sambungan** dan pilih **AdRoll** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="e4900-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="e4900-118">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="e4900-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e4900-119">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="e4900-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e4900-120">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="e4900-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e4900-121">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="e4900-121">Choose who can use this connection.</span></span> <span data-ttu-id="e4900-122">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="e4900-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e4900-123">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e4900-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e4900-124">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="e4900-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e4900-125">Pilih **Sambung** untuk memulakan sambungan ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e4900-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="e4900-126">Pilih **Sahkan dengan AdRoll** dan berikan kelayakan pentadbir anda untuk AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e4900-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="e4900-127">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="e4900-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e4900-128">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="e4900-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e4900-129">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="e4900-129">Configure an export</span></span>

<span data-ttu-id="e4900-130">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="e4900-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e4900-131">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e4900-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e4900-132">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="e4900-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e4900-133">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="e4900-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e4900-134">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e4900-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="e4900-135">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="e4900-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e4900-136">Masukkan **ID Pengiklan AdRoll**. Untuk mendapatkan maklumat lanjut, lihat [Profil Pengiklan AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="e4900-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="e4900-137">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e4900-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e4900-138">Ia diperlukan untuk mengeksport segmen ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e4900-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="e4900-139">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="e4900-139">Select the segments you want to export.</span></span> <span data-ttu-id="e4900-140">Pilih segmen dengan sekurang-kurangnya 100 ahli.</span><span class="sxs-lookup"><span data-stu-id="e4900-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="e4900-141">Anda tidak boleh mengeksport segmen yang lebih kecil.</span><span class="sxs-lookup"><span data-stu-id="e4900-141">You can't export smaller segments.</span></span> <span data-ttu-id="e4900-142">Selain itu, saiz maksimum segmen untuk mengeksport ialah 250,000 ahli bagi setiap eksport.</span><span class="sxs-lookup"><span data-stu-id="e4900-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="e4900-143">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="e4900-143">Select **Save**.</span></span>

<span data-ttu-id="e4900-144">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="e4900-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e4900-145">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e4900-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e4900-146">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e4900-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e4900-147">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="e4900-147">Data privacy and compliance</span></span>

<span data-ttu-id="e4900-148">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke AdRoll, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif yang berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="e4900-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e4900-149">Microsoft akan memindahkan data sedemikian mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa AdRoll memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki.</span><span class="sxs-lookup"><span data-stu-id="e4900-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e4900-150">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e4900-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e4900-151">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="e4900-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
