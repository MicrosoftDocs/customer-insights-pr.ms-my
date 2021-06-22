---
title: Eksport data Customer Insights ke Omnisend
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124526"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="d852c-103">Eksport segmen ke Omnisend (pratonton)</span><span class="sxs-lookup"><span data-stu-id="d852c-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="d852c-104">Eksport segmen profil pelanggan yang disatukan ke Omnisend dan gunakan segmen tersebut untuk aktiviti pemasaran.</span><span class="sxs-lookup"><span data-stu-id="d852c-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d852c-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="d852c-105">Prerequisites</span></span>

-   <span data-ttu-id="d852c-106">Anda mempunyai [akaun Omnisend](https://www.omnisend.com/) dan kelayakan pentadbir yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="d852c-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d852c-107">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="d852c-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d852c-108">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="d852c-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d852c-109">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="d852c-109">Known limitations</span></span>

- <span data-ttu-id="d852c-110">Anda boleh mengeksport sehingga 1 juta profil bagi setiap eksport ke Omnisend dan ia boleh mengambil masa sehingga 4 jam untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="d852c-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="d852c-111">Mengeksport ke Omnisend dihadkan kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="d852c-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="d852c-112">Bilangan profil yang boleh anda eksport ke Omnisend bergantung pada kontrak anda dengan Omnisend.</span><span class="sxs-lookup"><span data-stu-id="d852c-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="d852c-113">Sediakan sambungan ke Omnisend</span><span class="sxs-lookup"><span data-stu-id="d852c-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="d852c-114">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="d852c-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d852c-115">Pilih **Tambah sambungan** dan pilih **Omnisend** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="d852c-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="d852c-116">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="d852c-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d852c-117">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="d852c-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d852c-118">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="d852c-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d852c-119">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="d852c-119">Choose who can use this connection.</span></span> <span data-ttu-id="d852c-120">Secara lalai, ia hanya pentadbir.</span><span class="sxs-lookup"><span data-stu-id="d852c-120">By default it's only administrators.</span></span> <span data-ttu-id="d852c-121">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d852c-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d852c-122">Masukkan [Kunci API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key) anda.</span><span class="sxs-lookup"><span data-stu-id="d852c-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="d852c-123">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="d852c-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d852c-124">Pilih **Sambung** untuk memulakan sambungan ke Omnisend.</span><span class="sxs-lookup"><span data-stu-id="d852c-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="d852c-125">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="d852c-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d852c-126">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="d852c-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d852c-127">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="d852c-127">Configure an export</span></span>

<span data-ttu-id="d852c-128">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="d852c-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d852c-129">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d852c-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d852c-130">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="d852c-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d852c-131">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="d852c-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d852c-132">Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada bahagian Omnisend.</span><span class="sxs-lookup"><span data-stu-id="d852c-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="d852c-133">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="d852c-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d852c-134">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="d852c-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d852c-135">Ia diperlukan untuk mengeksport segmen ke Omnisend.</span><span class="sxs-lookup"><span data-stu-id="d852c-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="d852c-136">Selain itu, anda boleh mengeksport Nama pertama, Nama akhir, Alamat, Negara/Wilayah, Negeri, Bandar dan Poskod untuk mencipta e-mel yang lebih diperibadikan.</span><span class="sxs-lookup"><span data-stu-id="d852c-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="d852c-137">Pilih **Tambah atribut** untuk memetakan medan ini.</span><span class="sxs-lookup"><span data-stu-id="d852c-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d852c-138">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="d852c-138">Select **Save**.</span></span>

<span data-ttu-id="d852c-139">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="d852c-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d852c-140">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d852c-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d852c-141">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d852c-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d852c-142">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="d852c-142">Data privacy and compliance</span></span>

<span data-ttu-id="d852c-143">Apabila anda mendayakan Dynamics 365 Customer Insights untuk memindahkan data ke Ommisend, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="d852c-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d852c-144">Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan Ommisend memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki.</span><span class="sxs-lookup"><span data-stu-id="d852c-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d852c-145">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d852c-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d852c-146">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="d852c-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
