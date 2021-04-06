---
title: Eksport data Customer Insights ke Google Ads
description: Ketahui cara mengkonfigurasi sambungan ke Google ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598258"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="c1f7b-103">Penyambung untuk Google Ads (pratonton)</span><span class="sxs-lookup"><span data-stu-id="c1f7b-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="c1f7b-104">Eksport segmen profil pelanggan disatukan ke senarai khalayak Google Ads dan gunakannya untuk mengiklan pada Google Search, Gmail, YouTube dan Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c1f7b-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="c1f7b-105">Prerequisites</span></span>

-   <span data-ttu-id="c1f7b-106">Anda mempunyai [Akaun Google Ads](https://ads.google.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c1f7b-107">Terdapat khalayak sedia ada dalam Google Ads dan ID yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="c1f7b-108">Untuk maklumat lanjut, lihat [Khalayak Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="c1f7b-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="c1f7b-109">Anda telah [mengkonfigurasi segmen](segments.md)</span><span class="sxs-lookup"><span data-stu-id="c1f7b-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="c1f7b-110">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel, nama pertama dan nama akhir</span><span class="sxs-lookup"><span data-stu-id="c1f7b-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="c1f7b-111">Sambungkan dengan Google Ads</span><span class="sxs-lookup"><span data-stu-id="c1f7b-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="c1f7b-112">Pergi ke **Pentadbir** > **Destinasi Eksport**.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c1f7b-113">Di bawah **Google Ads**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="c1f7b-114">Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c1f7b-115">Masukkan **[ID pelanggan Google Ads](https://support.google.com/google-ads/answer/1704344)** anda.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="c1f7b-116">Masukkan **[Token pembangun diluluskan Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** anda.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="c1f7b-117">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c1f7b-118">Masukkan **[ID khalayak Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** anda dan pilih **Sambung** untuk memulakan sambungan ke Google Ads.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="c1f7b-119">Pilih **Sahkan dengan Google Ads** dan berikan kelayakan Google ads anda..</span><span class="sxs-lookup"><span data-stu-id="c1f7b-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="c1f7b-120">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Eksport petikan skrin untuk sambungan Google Ads":::

1. <span data-ttu-id="c1f7b-122">Pilih **Seterusnya** untuk konfigurasi eksport.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c1f7b-123">Konfigurasi penyambung</span><span class="sxs-lookup"><span data-stu-id="c1f7b-123">Configure the connector</span></span>

1. <span data-ttu-id="c1f7b-124">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c1f7b-125">Ulangi langkah yang sama untuk medan **Nama pertama** and **Nama akhir**.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="c1f7b-126">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-126">Select the segments you want to export.</span></span> <span data-ttu-id="c1f7b-127">Anda boleh mengeksport hingga 1 juta profil pelanggan dalam jumlah keseluruhan Google ads.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="c1f7b-128">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c1f7b-129">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="c1f7b-129">Export the data</span></span>

<span data-ttu-id="c1f7b-130">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c1f7b-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c1f7b-131">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c1f7b-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c1f7b-132">Dalam Google ads, anda kini boleh mencari segmen anda di bawah [Khalayak Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="c1f7b-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c1f7b-133">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="c1f7b-133">Known limitations</span></span>

- <span data-ttu-id="c1f7b-134">Hingga 1 juta profil bagi setiap eksport ke Google ads.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="c1f7b-135">Mengeksport ke Google Ads adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="c1f7b-136">Mengeksport segmen dengan jumlah 1 juta profil boleh mengambil masa hingga 5 minit kerana had pada bahagian pembekal.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="c1f7b-137">Pemadanan dalam Google Ads boleh mengambil masa hingga 48 jam.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c1f7b-138">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="c1f7b-138">Data privacy and compliance</span></span>

<span data-ttu-id="c1f7b-139">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Google Ads, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c1f7b-140">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Google Ads memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="c1f7b-141">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c1f7b-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c1f7b-142">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="c1f7b-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]