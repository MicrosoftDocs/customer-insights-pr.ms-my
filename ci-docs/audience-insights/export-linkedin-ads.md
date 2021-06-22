---
title: Eksport data Customer Insights ke LinkedIn Ads
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124527"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="13ab5-103">Eksport segmen ke LinkedIn Ads (pratonton)</span><span class="sxs-lookup"><span data-stu-id="13ab5-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="13ab5-104">Eksport segmen profil pelanggan yang disatukan kepada LinkedIn Ads untuk mencipta matched audiences.</span><span class="sxs-lookup"><span data-stu-id="13ab5-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="13ab5-105">Gunakan matched audiences untuk penyasaran syarikat dan penyasaran kenalan.</span><span class="sxs-lookup"><span data-stu-id="13ab5-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="13ab5-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="13ab5-106">Prerequisites</span></span>

-   <span data-ttu-id="13ab5-107">Anda mempunyai [akaun LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) dan kelayakan pentadbir yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="13ab5-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="13ab5-108">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="13ab5-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="13ab5-109">Profil pelanggan dalam segmen yang dieksport mengandungi medan dengan alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="13ab5-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="13ab5-110">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="13ab5-110">Known limitations</span></span>

- <span data-ttu-id="13ab5-111">Anda boleh mengeksport hingga 100K profil bagi setiap eksport ke LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="13ab5-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="13ab5-112">Mengeksport ke LinkedIn Ads dihadkan kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="13ab5-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="13ab5-113">Mengeksport hingga 100K profil ke LinkedIn Ads boleh mengambil masa hingga 10 minit untuk selesai.</span><span class="sxs-lookup"><span data-stu-id="13ab5-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="13ab5-114">Sediakan sambungan ke LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="13ab5-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="13ab5-115">Dalam wawasan khalayak, pergi ke **Pergi ke** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="13ab5-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="13ab5-116">Pilih **Tambah sambungan** dan pilih **LinkedIn Ads** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="13ab5-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="13ab5-117">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="13ab5-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="13ab5-118">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="13ab5-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="13ab5-119">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="13ab5-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="13ab5-120">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="13ab5-120">Choose who can use this connection.</span></span> <span data-ttu-id="13ab5-121">Jika anda tidak mengambil tindakan, nilai lalai ialah Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="13ab5-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="13ab5-122">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="13ab5-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="13ab5-123">Berikan [ID Akaun LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270) anda.</span><span class="sxs-lookup"><span data-stu-id="13ab5-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="13ab5-124">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="13ab5-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="13ab5-125">Pilih **Sambung** untuk memulakan sambungan ke Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="13ab5-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="13ab5-126">Pilih **Sahkan dengan LinkedIn** dan berikan kelayakan pentadbir anda untuk LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="13ab5-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="13ab5-127">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="13ab5-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="13ab5-128">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="13ab5-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="13ab5-129">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="13ab5-129">Configure an export</span></span>

<span data-ttu-id="13ab5-130">Anda boleh mengkonfigurasikan eksport jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="13ab5-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="13ab5-131">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="13ab5-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="13ab5-132">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="13ab5-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="13ab5-133">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="13ab5-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="13ab5-134">Dalam medan **Sambungan untuk eksport**, pilih sambungan daripada bahagian LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="13ab5-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="13ab5-135">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="13ab5-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="13ab5-136">Pilih sama ada anda mahu mengeksport data untuk [penyasaran kenalan](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) atau [penyasaran syarikat](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) di LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="13ab5-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="13ab5-137">Di bahagian **Pemadanan data**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="13ab5-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="13ab5-138">Ia diperlukan untuk mengeksport segmen ke LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="13ab5-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="13ab5-139">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="13ab5-139">Select the segments you want to export.</span></span> <span data-ttu-id="13ab5-140">Matched audiences dalam LinkedIn Campaign Manager akan dicipta secara automatik dengan nama segmen yang anda pilih untuk dieksport.</span><span class="sxs-lookup"><span data-stu-id="13ab5-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="13ab5-141">Setiap segmen akan menghasilkan matched audiences yang berasingan.</span><span class="sxs-lookup"><span data-stu-id="13ab5-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="13ab5-142">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="13ab5-142">Select **Save**.</span></span>

<span data-ttu-id="13ab5-143">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="13ab5-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="13ab5-144">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="13ab5-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="13ab5-145">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="13ab5-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="13ab5-146">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="13ab5-146">Data privacy and compliance</span></span>

<span data-ttu-id="13ab5-147">Apabila anda mendayakan Dynamics 365 Customer Insights untuk memindahkan data ke LinkedIn Ads, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="13ab5-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="13ab5-148">Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan LinkedIn Ads memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki.</span><span class="sxs-lookup"><span data-stu-id="13ab5-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="13ab5-149">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="13ab5-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="13ab5-150">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menghentikan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="13ab5-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
