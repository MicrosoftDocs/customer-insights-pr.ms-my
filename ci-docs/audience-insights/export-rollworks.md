---
title: Eksport data Customer Insight ke RollWorks
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124100"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="3475b-103">Eksport segmen ke RollWorks (pratonton)</span><span class="sxs-lookup"><span data-stu-id="3475b-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="3475b-104">Eksport segmen profil pelanggan yang disatukan ke RollWorks dan gunakannya untuk pengiklanan.</span><span class="sxs-lookup"><span data-stu-id="3475b-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="3475b-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="3475b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="3475b-106">Anda mempunyai [akaun RollWorks](https://www.rollworks.com/) dan kelayakan pentadbir yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="3475b-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3475b-107">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="3475b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3475b-108">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="3475b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3475b-109">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="3475b-109">Known limitations</span></span>

- <span data-ttu-id="3475b-110">Anda boleh mengeksport hingga 250,000 profil dalam setiap eksport ke RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3475b-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="3475b-111">Anda tidak boleh mengeksport segmen yang kurang daripada 100 profil ke RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3475b-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="3475b-112">Mengeksport ke RollWorks dihadkan kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="3475b-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="3475b-113">Mengeksport hingga 250,000 profil ke RollWorks boleh mengambil masa hingga 10 minit untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="3475b-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="3475b-114">Bilangan profil yang boleh anda eksport ke RollWorks adalah bergantung dan terhad pada kontrak anda dengan RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3475b-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="3475b-115">Sediakan sambungan ke RollWorks</span><span class="sxs-lookup"><span data-stu-id="3475b-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="3475b-116">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="3475b-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3475b-117">Pilih **Tambah sambungan** dan pilih **RollWorks** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="3475b-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="3475b-118">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="3475b-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3475b-119">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="3475b-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3475b-120">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="3475b-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3475b-121">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="3475b-121">Choose who can use this connection.</span></span> <span data-ttu-id="3475b-122">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="3475b-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3475b-123">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3475b-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3475b-124">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="3475b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3475b-125">Pilih **Sambung** untuk memulakan sambungan ke RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3475b-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="3475b-126">Pilih **Sahkan dengan RollWorks** dan berikan kelayakan pentadbir anda untuk RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3475b-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="3475b-127">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="3475b-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3475b-128">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="3475b-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3475b-129">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="3475b-129">Configure an export</span></span>

<span data-ttu-id="3475b-130">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="3475b-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3475b-131">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3475b-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3475b-132">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="3475b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3475b-133">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="3475b-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3475b-134">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3475b-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="3475b-135">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="3475b-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3475b-136">Masukkan **ID Pengiklan RollWorks** [RollWorks Boleh Diiklankan](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="3475b-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="3475b-137">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="3475b-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3475b-138">Ia diperlukan untuk mengeksport segmen ke RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3475b-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="3475b-139">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="3475b-139">Select the segments you want to export.</span></span> <span data-ttu-id="3475b-140">Pilih segmen dengan sekurang-kurangnya 100 ahli.</span><span class="sxs-lookup"><span data-stu-id="3475b-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="3475b-141">Anda tidak boleh mengeksport segmen yang lebih kecil.</span><span class="sxs-lookup"><span data-stu-id="3475b-141">You can't export smaller segments.</span></span> <span data-ttu-id="3475b-142">Selain itu, saiz maksimum segmen untuk mengeksport ialah 250,000 ahli bagi setiap eksport.</span><span class="sxs-lookup"><span data-stu-id="3475b-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="3475b-143">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="3475b-143">Select **Save**.</span></span>

<span data-ttu-id="3475b-144">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="3475b-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3475b-145">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3475b-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3475b-146">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3475b-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3475b-147">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="3475b-147">Data privacy and compliance</span></span>

<span data-ttu-id="3475b-148">Apabila anda mendayakan Dynamics 365 Customer Insights untuk memindahkan data ke RollWorks, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="3475b-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3475b-149">Microsoft akan memindahkan data tersebut atas arahan anda, tetapi anda bertanggungjawab untuk memastikan RollWorks memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki.</span><span class="sxs-lookup"><span data-stu-id="3475b-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3475b-150">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3475b-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="3475b-151">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="3475b-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
