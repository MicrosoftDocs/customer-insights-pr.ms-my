---
title: Eksport data Customer Insight ke Constant Contact
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124284"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="825df-103">Eksport segmen ke Kenalan Pemalar (pratonton)</span><span class="sxs-lookup"><span data-stu-id="825df-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="825df-104">Eksport segmen profil pelanggan yang disatukan ke Constant Contact dan gunakannya untuk aktiviti pemasaran.</span><span class="sxs-lookup"><span data-stu-id="825df-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="825df-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="825df-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="825df-106">Anda mempunyai [akaun Constant Contact](https://www.constantcontact.com/account-home) dan kelayakan pentadbir yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="825df-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="825df-107">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="825df-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="825df-108">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="825df-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="825df-109">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="825df-109">Known limitations</span></span>

- <span data-ttu-id="825df-110">Anda boleh mengeksport hingga 1 juta profil setiap eksport ke Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="825df-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="825df-111">Mengeksport ke Constant Contact dihadkan kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="825df-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="825df-112">Mengeksport hingga 1 juta profil ke Constant Contact boleh mengambil masa hingga 1 jam untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="825df-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="825df-113">Bilangan profil yang boleh anda eksport ke Constant Contact adalah bergantung dan terhad pada kontrak anda dengan Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="825df-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="825df-114">Sediakan sambungan ke Constant Contact</span><span class="sxs-lookup"><span data-stu-id="825df-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="825df-115">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="825df-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="825df-116">Pilih **Tambah sambungan** dan pilih **Constant Contact** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="825df-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="825df-117">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="825df-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="825df-118">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="825df-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="825df-119">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="825df-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="825df-120">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="825df-120">Choose who can use this connection.</span></span> <span data-ttu-id="825df-121">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="825df-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="825df-122">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="825df-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="825df-123">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="825df-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="825df-124">Pilih **Sambung** untuk memulakan sambungan ke Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="825df-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="825df-125">Pilih **Sahkan dengan AdRoll** dan berikan kelayakan pentadbir anda untuk Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="825df-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="825df-126">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="825df-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="825df-127">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="825df-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="825df-128">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="825df-128">Configure an export</span></span>

<span data-ttu-id="825df-129">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="825df-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="825df-130">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="825df-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="825df-131">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="825df-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="825df-132">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="825df-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="825df-133">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="825df-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="825df-134">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="825df-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="825df-135">Masukkan [**ID Senarai Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists) anda.</span><span class="sxs-lookup"><span data-stu-id="825df-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="825df-136">Buka senarai dalam Constant Contact untuk mencari ID senarai dalam URL.</span><span class="sxs-lookup"><span data-stu-id="825df-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="825df-137">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="825df-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="825df-138">Ia diperlukan untuk mengeksport segmen ke Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="825df-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="825df-139">Secara alternatif, anda boleh mengeksport Nama pertama dan Nama akhir sebagai medan tambahan untuk mencipta lebih banyak e-mel peribadi.</span><span class="sxs-lookup"><span data-stu-id="825df-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="825df-140">Pilih **Tambah atribut** untuk memetakan medan ini.</span><span class="sxs-lookup"><span data-stu-id="825df-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="825df-141">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="825df-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="825df-142">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="825df-142">Select **Save**.</span></span>

<span data-ttu-id="825df-143">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="825df-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="825df-144">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="825df-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="825df-145">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="825df-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="825df-146">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="825df-146">Data privacy and compliance</span></span>

<span data-ttu-id="825df-147">Apabila anda mendayakan Dynamics 365 Customer Insights untuk memindahkan data ke Constant Contact, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="825df-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="825df-148">Microsoft akan memindahkan data tersebut atas arahan anda, tetapi anda bertanggungjawab untuk memastikan Constant Contact memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki.</span><span class="sxs-lookup"><span data-stu-id="825df-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="825df-149">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="825df-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="825df-150">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="825df-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
