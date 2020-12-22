---
title: Eksport data Customer Insights ke Google Ads
description: Ketahui cara mengkonfigurasi sambungan ke Google ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568475"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="b59b7-103">Penyambung untuk Google Ads (pratonton)</span><span class="sxs-lookup"><span data-stu-id="b59b7-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="b59b7-104">Eksport segmen profil pelanggan disatukan ke senarai khalayak Google Ads dan gunakannya untuk mengiklan pada Google Search, Gmail, YouTube dan Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="b59b7-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b59b7-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="b59b7-105">Prerequisites</span></span>

-   <span data-ttu-id="b59b7-106">Anda mempunyai [Akaun Google Ads](https://ads.google.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="b59b7-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b59b7-107">Terdapat khalayak sedia ada dalam Google Ads dan ID yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="b59b7-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="b59b7-108">Untuk maklumat lanjut, lihat [Khalayak Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="b59b7-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="b59b7-109">Anda telah [mengkonfigurasi segmen](segments.md)</span><span class="sxs-lookup"><span data-stu-id="b59b7-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="b59b7-110">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel, nama pertama dan nama akhir</span><span class="sxs-lookup"><span data-stu-id="b59b7-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="b59b7-111">Sambungkan dengan Google Ads</span><span class="sxs-lookup"><span data-stu-id="b59b7-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="b59b7-112">Pergi ke **Pentadbir** > **Destinasi Eksport**.</span><span class="sxs-lookup"><span data-stu-id="b59b7-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b59b7-113">Di bawah **Google Ads**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="b59b7-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="b59b7-114">Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="b59b7-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b59b7-115">Masukkan **[ID pelanggan Google Ads](https://support.google.com/google-ads/answer/1704344)** anda.</span><span class="sxs-lookup"><span data-stu-id="b59b7-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="b59b7-116">Masukkan **[Token pembangun diluluskan Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** anda.</span><span class="sxs-lookup"><span data-stu-id="b59b7-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="b59b7-117">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="b59b7-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b59b7-118">Masukkan **[ID khalayak Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** anda dan pilih **Sambung** untuk memulakan sambungan ke Google Ads.</span><span class="sxs-lookup"><span data-stu-id="b59b7-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="b59b7-119">Pilih **Sahkan dengan Google Ads** dan berikan kelayakan Google ads anda..</span><span class="sxs-lookup"><span data-stu-id="b59b7-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="b59b7-120">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="b59b7-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Eksport petikan skrin untuk sambungan Google Ads":::

1. <span data-ttu-id="b59b7-122">Pilih **Seterusnya** untuk konfigurasi eksport.</span><span class="sxs-lookup"><span data-stu-id="b59b7-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b59b7-123">Konfigurasi penyambung</span><span class="sxs-lookup"><span data-stu-id="b59b7-123">Configure the connector</span></span>

1. <span data-ttu-id="b59b7-124">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="b59b7-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b59b7-125">Ulangi langkah yang sama untuk medan **Nama pertama** dan **Nama akhir**.</span><span class="sxs-lookup"><span data-stu-id="b59b7-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="b59b7-126">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="b59b7-126">Select the segments you want to export.</span></span> <span data-ttu-id="b59b7-127">Anda boleh mengeksport hingga 1 juta profil pelanggan dalam jumlah keseluruhan Google ads.</span><span class="sxs-lookup"><span data-stu-id="b59b7-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="b59b7-128">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="b59b7-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b59b7-129">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="b59b7-129">Export the data</span></span>

<span data-ttu-id="b59b7-130">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b59b7-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b59b7-131">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b59b7-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b59b7-132">Dalam Google ads, anda kini boleh mencari segmen anda di bawah [Khalayak Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="b59b7-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b59b7-133">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="b59b7-133">Known limitations</span></span>

- <span data-ttu-id="b59b7-134">Hingga 1 juta profil bagi setiap eksport ke Google ads.</span><span class="sxs-lookup"><span data-stu-id="b59b7-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="b59b7-135">Mengeksport ke Google Ads adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="b59b7-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="b59b7-136">Mengeksport segmen dengan jumlah 1 juta profil boleh mengambil masa hingga 5 minit kerana had pada bahagian pembekal.</span><span class="sxs-lookup"><span data-stu-id="b59b7-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="b59b7-137">Pemadanan dalam Google Ads boleh mengambil masa hingga 48 jam.</span><span class="sxs-lookup"><span data-stu-id="b59b7-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b59b7-138">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="b59b7-138">Data privacy and compliance</span></span>

<span data-ttu-id="b59b7-139">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Google Ads, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="b59b7-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b59b7-140">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Google Ads memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki.</span><span class="sxs-lookup"><span data-stu-id="b59b7-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b59b7-141">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b59b7-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b59b7-142">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="b59b7-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
