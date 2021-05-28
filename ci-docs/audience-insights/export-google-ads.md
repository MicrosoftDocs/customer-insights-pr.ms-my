---
title: Eksport data Customer Insights ke Google Ads
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976329"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="96945-103">Eksport segmen ke Google ads (pratonton)</span><span class="sxs-lookup"><span data-stu-id="96945-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="96945-104">Eksport segmen profil pelanggan disatukan ke senarai khalayak Google Ads dan gunakannya untuk mengiklan pada Google Search, Gmail, YouTube dan Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="96945-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="96945-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="96945-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="96945-106">Anda mempunyai [Akaun Google Ads](https://ads.google.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="96945-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="96945-107">Anda mempunyai [token Pembangun Google ads yang diluluskan](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="96945-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="96945-108">Anda memenuhi keperluan [Dasar Padanan Pelanggan](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="96945-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="96945-109">Anda memenuhi keperluan [saiz senarai pemasaran semula](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="96945-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="96945-110">Terdapat khalayak sedia ada dalam Google Ads dan ID yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="96945-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="96945-111">Untuk maklumat lanjut, lihat [Khalayak Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="96945-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="96945-112">Anda telah [mengkonfigurasi segmen](segments.md)</span><span class="sxs-lookup"><span data-stu-id="96945-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="96945-113">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel, nama pertama dan nama akhir</span><span class="sxs-lookup"><span data-stu-id="96945-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="96945-114">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="96945-114">Known limitations</span></span>

- <span data-ttu-id="96945-115">Hingga 1 juta profil bagi setiap eksport ke Google ads.</span><span class="sxs-lookup"><span data-stu-id="96945-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="96945-116">Mengeksport ke Google Ads adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="96945-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="96945-117">Mengeksport segmen dengan jumlah 1 juta profil boleh mengambil masa hingga 5 minit kerana had pada bahagian pembekal.</span><span class="sxs-lookup"><span data-stu-id="96945-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="96945-118">Pemadanan dalam Google Ads boleh mengambil masa hingga 48 jam.</span><span class="sxs-lookup"><span data-stu-id="96945-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="96945-119">Sediakan sambungan ke Google Ads</span><span class="sxs-lookup"><span data-stu-id="96945-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="96945-120">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="96945-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="96945-121">Pilih **Tambah sambungan** dan pilih **Google Ads** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="96945-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="96945-122">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="96945-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="96945-123">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="96945-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="96945-124">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="96945-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="96945-125">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="96945-125">Choose who can use this connection.</span></span> <span data-ttu-id="96945-126">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="96945-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="96945-127">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="96945-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="96945-128">Masukkan **[ID pelanggan Google Ads](https://support.google.com/google-ads/answer/1704344)** anda.</span><span class="sxs-lookup"><span data-stu-id="96945-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="96945-129">Masukkan **[Token pembangun diluluskan Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** anda.</span><span class="sxs-lookup"><span data-stu-id="96945-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="96945-130">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="96945-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="96945-131">Pilih **Sahkan dengan Google Ads** dan berikan kelayakan Google ads anda..</span><span class="sxs-lookup"><span data-stu-id="96945-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="96945-132">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="96945-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="96945-133">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="96945-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="96945-134">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="96945-134">Configure an export</span></span>

<span data-ttu-id="96945-135">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="96945-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="96945-136">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="96945-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="96945-137">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="96945-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="96945-138">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="96945-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="96945-139">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Google Ads.</span><span class="sxs-lookup"><span data-stu-id="96945-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="96945-140">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="96945-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="96945-141">Masukkan **[ID khalayak Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** anda dan pilih **Sambung** untuk memulakan sambungan ke Google Ads.</span><span class="sxs-lookup"><span data-stu-id="96945-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="96945-142">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="96945-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="96945-143">Ulangi langkah yang sama untuk medan **Nama pertama** and **Nama akhir**.</span><span class="sxs-lookup"><span data-stu-id="96945-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="96945-144">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="96945-144">Select the segments you want to export.</span></span> <span data-ttu-id="96945-145">Anda boleh mengeksport hingga 1 juta profil pelanggan dalam jumlah keseluruhan Google ads.</span><span class="sxs-lookup"><span data-stu-id="96945-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="96945-146">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="96945-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="96945-147">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="96945-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="96945-148">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="96945-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="96945-149">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="96945-149">Data privacy and compliance</span></span>

<span data-ttu-id="96945-150">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Google Ads, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="96945-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="96945-151">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Google Ads memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki.</span><span class="sxs-lookup"><span data-stu-id="96945-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="96945-152">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="96945-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="96945-153">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="96945-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
