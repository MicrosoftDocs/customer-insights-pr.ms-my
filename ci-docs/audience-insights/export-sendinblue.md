---
title: Eksport Data Customer Insights pada Sendinblue
description: Ketahui cara mengkonfigurasikan sambungan dan mengeksport pada Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314649"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="6bc88-103">Eksport segmen pada Sendinblue (pratonton)</span><span class="sxs-lookup"><span data-stu-id="6bc88-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="6bc88-104">Eksport segmen profil pelanggan disatukan untuk menjana kempen, menyediakan pemasaran e-mel dan menggunakan kumpulan pelanggan khusus dengan Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="6bc88-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="6bc88-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="6bc88-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="6bc88-106">Anda mempunyai [Akaun Sendinblue](https://www.sendinblue.com/) dan kelayakan pentadbir yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="6bc88-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6bc88-107">Terdapat senarai sedia ada dalam Sendinblue dan ID yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="6bc88-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="6bc88-108">Anda telah [mengkonfigurasi segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6bc88-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="6bc88-109">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="6bc88-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6bc88-110">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="6bc88-110">Known limitations</span></span>

- <span data-ttu-id="6bc88-111">Sehingga 1 juta profil bagi setiap eksport pada Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="6bc88-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="6bc88-112">Mengeksport pada Sendinblue terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="6bc88-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="6bc88-113">Mengeksport segmen dengan sejumlah 1 juta profil boleh mengambil masa sehingga 90 minit.</span><span class="sxs-lookup"><span data-stu-id="6bc88-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="6bc88-114">Bilangan profil yang boleh anda eksport pada Sendinblue bergantung pada dan terhad kepada kontrak anda dengan Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="6bc88-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="6bc88-115">Sediakan sambungan kepada Sendinblue</span><span class="sxs-lookup"><span data-stu-id="6bc88-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="6bc88-116">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="6bc88-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6bc88-117">Pilih **Tambah sambungan** dan pilih **Sendinblue** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="6bc88-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="6bc88-118">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="6bc88-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6bc88-119">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="6bc88-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6bc88-120">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="6bc88-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6bc88-121">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="6bc88-121">Choose who can use this connection.</span></span> <span data-ttu-id="6bc88-122">Secara lalai, ia hanya pentadbir.</span><span class="sxs-lookup"><span data-stu-id="6bc88-122">By default it's only administrators.</span></span> <span data-ttu-id="6bc88-123">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6bc88-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6bc88-124">Masukkan **[Kunci API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)** anda.</span><span class="sxs-lookup"><span data-stu-id="6bc88-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="6bc88-125">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data** dan pilih **Sambung** untuk memulakan sambungan kepada Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="6bc88-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="6bc88-126">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="6bc88-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6bc88-127">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="6bc88-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6bc88-128">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="6bc88-128">Configure an export</span></span>

<span data-ttu-id="6bc88-129">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="6bc88-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6bc88-130">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6bc88-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6bc88-131">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="6bc88-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6bc88-132">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="6bc88-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6bc88-133">Dalam medan **Sambungan untuk mengeksport**, pilih sambungan daripada bahagian Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="6bc88-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="6bc88-134">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="6bc88-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6bc88-135">Masukkan **ID senarai Sendinblue** anda</span><span class="sxs-lookup"><span data-stu-id="6bc88-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="6bc88-136">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="6bc88-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="6bc88-137">Sebagai pilihan, anda boleh mengeksport **Nama pertama**, **Nama akhir**, dan **Telefon** untuk mencipta e-mel yang lebih diperibadikan.</span><span class="sxs-lookup"><span data-stu-id="6bc88-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="6bc88-138">Pilih **Tambah atribut** untuk memetakan medan ini.</span><span class="sxs-lookup"><span data-stu-id="6bc88-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="6bc88-139">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="6bc88-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="6bc88-140">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="6bc88-140">Select **Save**.</span></span>

<span data-ttu-id="6bc88-141">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="6bc88-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6bc88-142">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6bc88-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6bc88-143">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6bc88-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6bc88-144">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="6bc88-144">Data privacy and compliance</span></span>

<span data-ttu-id="6bc88-145">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data kepada Sendinblue, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif yang berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="6bc88-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6bc88-146">Microsoft akan memindahkan data tersebut atas arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa Sendinblue memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki.</span><span class="sxs-lookup"><span data-stu-id="6bc88-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6bc88-147">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6bc88-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6bc88-148">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="6bc88-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
