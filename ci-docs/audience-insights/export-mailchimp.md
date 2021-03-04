---
title: Eksport data Customer Insights ke Mailchimp
description: Ketahui cara mengkonfigurasi sambungan ke Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267184"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="bc9b4-103">Penyambung untuk Mailchimp (pratonton)</span><span class="sxs-lookup"><span data-stu-id="bc9b4-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="bc9b4-104">Segmen eksport profil pelanggan disatukan ke Mailchimp untuk mencipta surat berita dan kempen e-mel.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bc9b4-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="bc9b4-105">Prerequisites</span></span>

-   <span data-ttu-id="bc9b4-106">Anda mempunyai [Akaun Mailchimp](https://mailchimp.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bc9b4-107">Terdapat khalayak sedia ada dalam Mailchimp dan ID yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="bc9b4-108">Untuk maklumat lanjut, lihat [Khalayak Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="bc9b4-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="bc9b4-109">Anda telah [mengkonfigurasi segmen](segments.md)</span><span class="sxs-lookup"><span data-stu-id="bc9b4-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="bc9b4-110">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="bc9b4-111">Sambung kepada Mailchimp</span><span class="sxs-lookup"><span data-stu-id="bc9b4-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="bc9b4-112">Pergi ke **Pentadbir** > **Destinasi Eksport**.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bc9b4-113">Di bawah **Mailchimp**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="bc9b4-114">Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="bc9b4-115">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bc9b4-116">Masukkan **[ID khalayak Mailchimp](https://mailchimp.com/help/find-audience-id/)** anda dan pilih **Sambung** untuk memulakan sambungan ke Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="bc9b4-117">Pilih **Sahkan dengan Mailchimp** dan berikan kelayakan Mailchimp anda.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="bc9b4-118">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Eksport tangkap skrin untuk sambungan Customer Insights":::

1. <span data-ttu-id="bc9b4-120">Pilih **Seterusnya** untuk konfigurasi eksport.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="bc9b4-121">Konfigurasi penyambung</span><span class="sxs-lookup"><span data-stu-id="bc9b4-121">Configure the connector</span></span>

1. <span data-ttu-id="bc9b4-122">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="bc9b4-123">Secara alternatif, anda boleh mengeksport **Nama pertama** dan **Nama akhir** sebagai medan tambahan untuk mencipta lebih banyak e-mel peribadi.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="bc9b4-124">Pilih **Tambah atribut** untuk memetakan medan ini.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="bc9b4-125">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-125">Select the segments you want to export.</span></span> <span data-ttu-id="bc9b4-126">Anda boleh mengeksport hingga 1 juta jumlah profil pelanggan ke Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Pilih medan dan segmen untuk eksport ke Mailchimp":::

1. <span data-ttu-id="bc9b4-128">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="bc9b4-129">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="bc9b4-129">Export the data</span></span>

<span data-ttu-id="bc9b4-130">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bc9b4-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="bc9b4-131">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bc9b4-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bc9b4-132">Dalam Mailchimp, anda kini boleh mencari segmen anda di bawah [Khalayak Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="bc9b4-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bc9b4-133">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="bc9b4-133">Known limitations</span></span>

- <span data-ttu-id="bc9b4-134">Hingga 1 juta profil bagi setiap eksport ke Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="bc9b4-135">Mengeksport ke Mailchimp adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="bc9b4-136">Mengeksport segmen dengan 1 juta jumlah profil boleh mengambil masa hingga tiga jam kerana had pada bahagian pembekal.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="bc9b4-137">Bilangan profil yang boleh anda eksport ke Mailchimp bergantung dan terhad pada kontrak anda dengan Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bc9b4-138">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="bc9b4-138">Data privacy and compliance</span></span>

<span data-ttu-id="bc9b4-139">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Mailchimp, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bc9b4-140">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Mailchimp memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bc9b4-141">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bc9b4-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bc9b4-142">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="bc9b4-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]