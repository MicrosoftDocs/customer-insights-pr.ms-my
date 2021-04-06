---
title: Eksport data Customer Insights ke AdRoll
description: Ketahui cara mengkonfigurasikan sambungan ke AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697085"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="9d1fd-103">Penyambung untuk AdRoll (pratonton)</span><span class="sxs-lookup"><span data-stu-id="9d1fd-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="9d1fd-104">Eksport segmen profil pelanggan yang disatukan ke AdRoll dan gunakan segmen tersebut untuk pengiklanan.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="9d1fd-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="9d1fd-105">Prerequisites</span></span>

-   <span data-ttu-id="9d1fd-106">Anda mempunyai [Akaun AdRoll](https://www.adroll.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9d1fd-107">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="9d1fd-108">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="9d1fd-109">Sambung kepada AdRoll</span><span class="sxs-lookup"><span data-stu-id="9d1fd-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="9d1fd-110">Pergi ke **Pentadbir** > **Destinasi Eksport**.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9d1fd-111">Di bawah **AdRoll**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="9d1fd-112">Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Anak tetingkap konfigurasi untuk sambungan AdRoll.":::

1. <span data-ttu-id="9d1fd-114">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9d1fd-115">Pilih **Sambung** untuk memulakan sambungan ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="9d1fd-116">Pilih **Sahkan dengan AdRoll** dan berikan kelayakan pentadbir anda untuk AdRoll.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="9d1fd-117">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9d1fd-118">Masukkan **ID Pengiklan AdRoll** anda [AdRoll yang Boleh Diiklankan](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="9d1fd-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="9d1fd-119">Pilih **Seterusnya** untuk konfigurasi eksport.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="9d1fd-120">Konfigurasi penyambung</span><span class="sxs-lookup"><span data-stu-id="9d1fd-120">Configure the connector</span></span>

1. <span data-ttu-id="9d1fd-121">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="9d1fd-122">Ia diperlukan untuk mengeksport segmen ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="9d1fd-123">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-123">Select the segments you want to export.</span></span> <span data-ttu-id="9d1fd-124">Pilih segmen dengan sekurang-kurangnya 100 ahli.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="9d1fd-125">Anda tidak boleh mengeksport segmen yang lebih kecil.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-125">You can't export smaller segments.</span></span> <span data-ttu-id="9d1fd-126">Selain itu, saiz maksimum segmen untuk mengeksport ialah 250,000 ahli bagi setiap eksport.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="9d1fd-127">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9d1fd-128">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="9d1fd-128">Export the data</span></span>

<span data-ttu-id="9d1fd-129">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9d1fd-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9d1fd-130">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9d1fd-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9d1fd-131">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="9d1fd-131">Known limitations</span></span>

- <span data-ttu-id="9d1fd-132">Anda boleh mengeksport hingga 250,000 profil bagi setiap eksport ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="9d1fd-133">Anda tidak boleh mengeksport segmen yang kurang daripada 100 profil ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="9d1fd-134">Mengeksport ke AdRoll adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="9d1fd-135">Mengeksport hingga 250,000 profil ke AdRoll mungkin mengambil masa hingga 10 minit untuk selesai.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="9d1fd-136">Bilangan profil yang boleh anda eksport ke AdRoll bergantung dan terhad pada kontrak anda dengan AdRoll.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9d1fd-137">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="9d1fd-137">Data privacy and compliance</span></span>

<span data-ttu-id="9d1fd-138">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke AdRoll, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif yang berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9d1fd-139">Microsoft akan memindahkan data sedemikian mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa AdRoll memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9d1fd-140">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9d1fd-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="9d1fd-141">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="9d1fd-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
