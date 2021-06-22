---
title: Eksport data Customer Insight ke Snapchat
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124054"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="77796-103">Eksport segmen ke Snapchat (pratonton)</span><span class="sxs-lookup"><span data-stu-id="77796-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="77796-104">Eksport segmen profil pelanggan yang disatukan ke Snapchat dan gunakannya untuk pengiklanan.</span><span class="sxs-lookup"><span data-stu-id="77796-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="77796-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="77796-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="77796-106">Anda mempunyai [akaun Perniagaan Snapchat](https://business.snapchat.com/), [akaun Iklan Snapchat](https://ads.snapchat.com/), dan kelayakan pentadbir yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="77796-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="77796-107">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="77796-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="77796-108">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="77796-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="77796-109">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="77796-109">Known limitations</span></span>

- <span data-ttu-id="77796-110">Mengeksport ke Snapchat dihadkan kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="77796-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="77796-111">Mengeksport hingga 1 juta profil ke Snapchat boleh mengambil masa hingga 15 minit untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="77796-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="77796-112">Sediakan sambungan ke Snapchat</span><span class="sxs-lookup"><span data-stu-id="77796-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="77796-113">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="77796-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="77796-114">Pilih **Tambah sambungan** dan pilih **Snapchat** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="77796-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="77796-115">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="77796-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="77796-116">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="77796-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="77796-117">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="77796-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="77796-118">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="77796-118">Choose who can use this connection.</span></span> <span data-ttu-id="77796-119">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="77796-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="77796-120">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="77796-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="77796-121">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="77796-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="77796-122">Pilih **Sambung** untuk memulakan sambungan ke Snapchat.</span><span class="sxs-lookup"><span data-stu-id="77796-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="77796-123">Pilih **Sahkan dengan Snapchat** dan berikan kelayakan pentadbir anda untuk Snapchat.</span><span class="sxs-lookup"><span data-stu-id="77796-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="77796-124">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="77796-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="77796-125">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="77796-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="77796-126">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="77796-126">Configure an export</span></span>

<span data-ttu-id="77796-127">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="77796-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="77796-128">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="77796-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="77796-129">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="77796-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="77796-130">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="77796-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="77796-131">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Snapchat.</span><span class="sxs-lookup"><span data-stu-id="77796-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="77796-132">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="77796-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="77796-133">Masukkan [**ID Khalayak Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="77796-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="77796-134">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="77796-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="77796-135">Ia diperlukan untuk mengeksport segmen ke Snapchat.</span><span class="sxs-lookup"><span data-stu-id="77796-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="77796-136">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="77796-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="77796-137">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="77796-137">Select **Save**.</span></span>

<span data-ttu-id="77796-138">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="77796-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="77796-139">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="77796-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="77796-140">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="77796-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="77796-141">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="77796-141">Data privacy and compliance</span></span>

<span data-ttu-id="77796-142">Apabila anda mendayakan Dynamics 365 Customer Insights untuk memindahkan data ke Snapchat, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="77796-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="77796-143">Microsoft akan memindahkan data tersebut atas arahan anda, tetapi anda bertanggungjawab untuk memastikan Snapchat memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki.</span><span class="sxs-lookup"><span data-stu-id="77796-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="77796-144">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="77796-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="77796-145">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="77796-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
