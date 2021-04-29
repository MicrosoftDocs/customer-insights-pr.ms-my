---
title: Eksport data Customer Insights ke Mailchimp
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759889"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="fa918-103">Eksport senarai segmen ke Mailchimp (pratonton)</span><span class="sxs-lookup"><span data-stu-id="fa918-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="fa918-104">Segmen eksport profil pelanggan disatukan ke Mailchimp untuk mencipta surat berita dan kempen e-mel.</span><span class="sxs-lookup"><span data-stu-id="fa918-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="fa918-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="fa918-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="fa918-106">Anda mempunyai [Akaun Mailchimp](https://mailchimp.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="fa918-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fa918-107">Terdapat khalayak sedia ada dalam Mailchimp dan ID yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="fa918-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="fa918-108">Untuk maklumat lanjut, lihat [Khalayak Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="fa918-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="fa918-109">Anda telah [mengkonfigurasi segmen](segments.md)</span><span class="sxs-lookup"><span data-stu-id="fa918-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="fa918-110">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="fa918-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fa918-111">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="fa918-111">Known limitations</span></span>

- <span data-ttu-id="fa918-112">Hingga 1 juta profil bagi setiap eksport ke Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="fa918-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="fa918-113">Mengeksport ke Mailchimp adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="fa918-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="fa918-114">Mengeksport segmen dengan 1 juta profil boleh mengambil masa sehingga tiga jam.</span><span class="sxs-lookup"><span data-stu-id="fa918-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="fa918-115">Bilangan profil yang boleh anda eksport ke Mailchimp bergantung dan terhad pada kontrak anda dengan Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="fa918-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="fa918-116">Sediakan sambungan ke Mailchimp</span><span class="sxs-lookup"><span data-stu-id="fa918-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="fa918-117">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="fa918-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="fa918-118">Pilih **Tambah sambungan** dan pilih **Autopilot** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="fa918-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="fa918-119">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="fa918-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="fa918-120">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="fa918-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="fa918-121">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="fa918-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="fa918-122">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="fa918-122">Choose who can use this connection.</span></span> <span data-ttu-id="fa918-123">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="fa918-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="fa918-124">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="fa918-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="fa918-125">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="fa918-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fa918-126">Pilih **Sambung** untuk memulakan sambungan ke Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="fa918-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="fa918-127">Pilih **Sahkan dengan Mailchimp** dan berikan kelayakan Mailchimp anda.</span><span class="sxs-lookup"><span data-stu-id="fa918-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="fa918-128">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="fa918-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="fa918-129">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="fa918-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="fa918-130">Konfigurasi penyambung</span><span class="sxs-lookup"><span data-stu-id="fa918-130">Configure the connector</span></span>

<span data-ttu-id="fa918-131">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="fa918-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="fa918-132">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="fa918-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fa918-133">Pergi ke **Data**> **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="fa918-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="fa918-134">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="fa918-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="fa918-135">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="fa918-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="fa918-136">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="fa918-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="fa918-137">Masukkan **[ID khalayak Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="fa918-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="fa918-138">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="fa918-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="fa918-139">Selain itu, anda boleh mengeksport **Nama pertama** dan **Nama keluarga** untuk mencipta e-mel yang lebih diperibadikan.</span><span class="sxs-lookup"><span data-stu-id="fa918-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="fa918-140">Pilih **Tambah atribut** untuk memetakan medan ini.</span><span class="sxs-lookup"><span data-stu-id="fa918-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="fa918-141">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="fa918-141">Select the segments you want to export.</span></span> <span data-ttu-id="fa918-142">Anda boleh mengeksport hingga 1 juta jumlah profil pelanggan ke Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="fa918-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="fa918-143">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="fa918-143">Select **Save**.</span></span>

<span data-ttu-id="fa918-144">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="fa918-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="fa918-145">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fa918-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fa918-146">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fa918-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fa918-147">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="fa918-147">Data privacy and compliance</span></span>

<span data-ttu-id="fa918-148">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Mailchimp, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="fa918-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fa918-149">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Mailchimp memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="fa918-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fa918-150">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fa918-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fa918-151">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="fa918-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
