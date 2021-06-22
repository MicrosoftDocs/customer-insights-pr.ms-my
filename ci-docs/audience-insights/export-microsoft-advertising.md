---
title: Eksport data Customer Insights ke Microsoft Advertising
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124525"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="5a72d-103">Eksport segmen ke Microsoft Advertising (pratonton)</span><span class="sxs-lookup"><span data-stu-id="5a72d-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="5a72d-104">Eksport segmen Customer Insights ke Microsoft Advertising untuk mencipta khalayak Padanan Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="5a72d-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="5a72d-105">Gunakan khalayak ini untuk kempen iklan anda.</span><span class="sxs-lookup"><span data-stu-id="5a72d-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a72d-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="5a72d-106">Prerequisites</span></span>

-   <span data-ttu-id="5a72d-107">[Akaun Microsoft Advertising](https://ads.microsoft.com/) dan kelayakan pentadbir yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="5a72d-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5a72d-108">Anda telah menerima terma penggunaan Padanan Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="5a72d-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="5a72d-109">[Segmen dikonfigurasikan](segments.md) dalam cerapan khalayak.</span><span class="sxs-lookup"><span data-stu-id="5a72d-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5a72d-110">Profil pelanggan yang disatukan dalam segmen yang dieksport mengandungi medan dengan alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="5a72d-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5a72d-111">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="5a72d-111">Known limitations</span></span>

- <span data-ttu-id="5a72d-112">Anda boleh mengeksport hingga 500K profil bagi setiap eksport ke Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="5a72d-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="5a72d-113">Mengeksport ke Microsoft Advertising dihadkan kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="5a72d-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="5a72d-114">Mengeksport hingga 500K profil ke Microsoft Advertising boleh mengambil masa hingga 10 minit untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="5a72d-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="5a72d-115">Sediakan sambungan ke Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="5a72d-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="5a72d-116">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="5a72d-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5a72d-117">Pilih **Tambah sambungan** dan pilih **Microsoft Advertising** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="5a72d-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="5a72d-118">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="5a72d-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5a72d-119">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="5a72d-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5a72d-120">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="5a72d-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5a72d-121">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="5a72d-121">Choose who can use this connection.</span></span> <span data-ttu-id="5a72d-122">Nilai lalai ialah pentadbir.</span><span class="sxs-lookup"><span data-stu-id="5a72d-122">The default is administrators.</span></span> <span data-ttu-id="5a72d-123">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5a72d-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5a72d-124">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="5a72d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5a72d-125">Pilih **Sambung** untuk memulakan sambungan ke Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="5a72d-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="5a72d-126">Pilih **Sahkan dengan Microsoft Advertising** dan berikan kelayakan pentadbir anda untuk Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="5a72d-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="5a72d-127">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="5a72d-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5a72d-128">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="5a72d-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5a72d-129">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="5a72d-129">Configure an export</span></span>

<span data-ttu-id="5a72d-130">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="5a72d-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5a72d-131">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5a72d-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5a72d-132">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="5a72d-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5a72d-133">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="5a72d-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5a72d-134">Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada bahagian Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="5a72d-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="5a72d-135">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="5a72d-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5a72d-136">Pilih segmen untuk dieksport.</span><span class="sxs-lookup"><span data-stu-id="5a72d-136">Select the segments to export.</span></span> <span data-ttu-id="5a72d-137">Khalayak Padanan Pelanggan dalam Microsoft Advertising dicipta secara automatik dengan nama segmen yang dipilih untuk eksport.</span><span class="sxs-lookup"><span data-stu-id="5a72d-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="5a72d-138">Setiap segmen akan menghasilkan khalayak Pemadanan Pelanggan yang berasingan.</span><span class="sxs-lookup"><span data-stu-id="5a72d-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="5a72d-139">Masukkan **ID Pelanggan dan ID Akaun Microsoft Advertising** anda.</span><span class="sxs-lookup"><span data-stu-id="5a72d-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="5a72d-140">Anda boleh menemui ID Pelanggan (`cid`) dan ID Akaun (`aid`) dalam parameter URL apabila anda mendaftar masuk Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="5a72d-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="5a72d-141">Di bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan anda yang disatukan dengan alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="5a72d-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="5a72d-142">Ia diperlukan untuk mengeksport segmen ke Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="5a72d-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="5a72d-143">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="5a72d-143">Select **Save**.</span></span>

<span data-ttu-id="5a72d-144">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="5a72d-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5a72d-145">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5a72d-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5a72d-146">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5a72d-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5a72d-147">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="5a72d-147">Data privacy and compliance</span></span>

<span data-ttu-id="5a72d-148">Apabila anda mendayakan Dynamics 365 Customer Insights untuk memindahkan data ke Microsoft Advertising, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="5a72d-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5a72d-149">Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan Microsoft Advertising memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki.</span><span class="sxs-lookup"><span data-stu-id="5a72d-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5a72d-150">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5a72d-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="5a72d-151">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menghentikan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="5a72d-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
