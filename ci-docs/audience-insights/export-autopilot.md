---
title: Eksport data Customer Insights ke Autopilot
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760154"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="0cb3f-103">Eksport segmen ke Autopilot (pratonton)</span><span class="sxs-lookup"><span data-stu-id="0cb3f-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="0cb3f-104">Eksport segmen bagi profil pelanggan disatukan untuk Autopilot dan gunakannya untuk pemasaran e-mel dalam Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="0cb3f-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="0cb3f-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="0cb3f-106">Anda mempunyai sebuah [Akaun Autopilot](https://www.autopilothq.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0cb3f-107">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0cb3f-108">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0cb3f-109">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="0cb3f-109">Known limitations</span></span>

- <span data-ttu-id="0cb3f-110">Anda boleh mengeksport hingga 100'000 juta jumlah profil pelanggan ke Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="0cb3f-111">Mengeksport ke Autopilot adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="0cb3f-112">Mengeksport sehingga 100'000 profil ke Autopilot boleh mengambil masa hingga beberapa jam untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="0cb3f-113">Bilangan profil yang boleh anda eksport ke Autopilot bergantung dan terhad pada kontrak anda dengan Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="0cb3f-114">Sediakan sambungan ke Autopilot</span><span class="sxs-lookup"><span data-stu-id="0cb3f-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="0cb3f-115">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0cb3f-116">Pilih **Tambah sambungan** dan pilih **Autopilot** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="0cb3f-117">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0cb3f-118">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0cb3f-119">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0cb3f-120">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-120">Choose who can use this connection.</span></span> <span data-ttu-id="0cb3f-121">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0cb3f-122">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0cb3f-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="0cb3f-123">Masukkan [Kekunci API autopilot anda](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="0cb3f-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="0cb3f-124">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0cb3f-125">Pilih **Sambung** untuk memulakan sambungan ke Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="0cb3f-126">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0cb3f-127">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0cb3f-128">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="0cb3f-128">Configure an export</span></span>

<span data-ttu-id="0cb3f-129">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0cb3f-130">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0cb3f-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0cb3f-131">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0cb3f-132">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0cb3f-133">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="0cb3f-134">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="0cb3f-135">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0cb3f-136">Ulangi langkah yang sama untuk medan pilihan lain seperti **Nama pertama**, **Nama keluarga**.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="0cb3f-137">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-137">Select the segments you want to export.</span></span> <span data-ttu-id="0cb3f-138">Kami amat **mengesyorkan untuk tidak mengeksport lebih daripada 100'000 profil pelanggan dalam jumlah** untuk Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="0cb3f-139">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-139">Select **Save**.</span></span>

<span data-ttu-id="0cb3f-140">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0cb3f-141">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0cb3f-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0cb3f-142">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0cb3f-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0cb3f-143">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="0cb3f-143">Data privacy and compliance</span></span>

<span data-ttu-id="0cb3f-144">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Autopilot, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0cb3f-145">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Autopilot memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0cb3f-146">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0cb3f-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0cb3f-147">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="0cb3f-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
