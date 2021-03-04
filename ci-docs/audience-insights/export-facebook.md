---
title: Eksport data Customer Insights ke Pengurus Iklan Facebook
description: Ketahui cara mengkonfigurasi sambungan ke Pengurus Iklan Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269985"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="c5507-103">Penyambung untuk Pengurus Iklan Facebook (pratonton)</span><span class="sxs-lookup"><span data-stu-id="c5507-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="c5507-104">Eksport segmen profil pelanggan disatukan ke Pengurus Iklan Facebook untuk mencipta kempen pada Facebook dan Instagram.</span><span class="sxs-lookup"><span data-stu-id="c5507-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c5507-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="c5507-105">Prerequisites</span></span>

- <span data-ttu-id="c5507-106">Anda perlu mempunyai [Akaun Iklan **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) yang merangkumi [Akaun Perniagaan **Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="c5507-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="c5507-107">Anda perlu menjadi pentadbir pada [Akaun Iklan **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="c5507-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="c5507-108">Connect ke Pengurus Iklan Facebook</span><span class="sxs-lookup"><span data-stu-id="c5507-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="c5507-109">Pergi ke **Pentadbir** > **Destinasi Eksport**.</span><span class="sxs-lookup"><span data-stu-id="c5507-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c5507-110">Di bawah Pengurus Iklan **Facebook**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="c5507-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="c5507-111">Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="c5507-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c5507-112">Pilih **Teruskan dengan Facebook** untuk mendaftar masuk ke Akaun Iklan Facebook.</span><span class="sxs-lookup"><span data-stu-id="c5507-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="c5507-113">Benarkan keizinan **ads_management** selepas pengesahan dengan Facebook.</span><span class="sxs-lookup"><span data-stu-id="c5507-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="c5507-114">Pilih **Akaun Iklan Facebook** yang anda ingin kendalikan.</span><span class="sxs-lookup"><span data-stu-id="c5507-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="c5507-115">Pilih **Khalayak tersuai sedia ada** daripada senarai juntai bawah atau cipta **Khalayak tersuai baharu**.</span><span class="sxs-lookup"><span data-stu-id="c5507-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="c5507-116">Untuk maklumat lanjut, lihat [**Khalayak dalam Pengurus Iklan Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="c5507-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="c5507-117">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="c5507-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c5507-118">Pilih **Seterusnya** untuk konfigurasi eksport.</span><span class="sxs-lookup"><span data-stu-id="c5507-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c5507-119">Konfigurasi penyambung</span><span class="sxs-lookup"><span data-stu-id="c5507-119">Configure the connector</span></span>

1. <span data-ttu-id="c5507-120">Dalam **Pilih medan pengecam kunci anda**, pilih **E-mel**, **Nama dan alamat**, atau **Telefon** untuk dihantar ke Pengurus Iklan Facebook.</span><span class="sxs-lookup"><span data-stu-id="c5507-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="c5507-121">Petakan atribut yang sepadan daripada entiti pelanggan disatukan anda untuk pengecam kunci yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="c5507-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="c5507-122">[TIP] Peluang terbaik untuk padanan berlaku jika anda memilih **E-mel** sebagai pengecam kunci.</span><span class="sxs-lookup"><span data-stu-id="c5507-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="c5507-123">Menambah pengecam tambahan mungkin meningkatkan pemadanan.</span><span class="sxs-lookup"><span data-stu-id="c5507-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="c5507-124">Pilih **Tambah atribut** bagi memetakan atribut tambahan untuk dihantar ke Pengurus Iklan Facebook.</span><span class="sxs-lookup"><span data-stu-id="c5507-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="c5507-125">Atribut daripada Pengurus Iklan Facebook dipetakan pada nama mesra pengguna berikut: **FN** = **Nama Pertama**, **LN** = **Nama Terakhir**, **FI** = **Parap Pertama**, **PHONE** = **Telefon**, **GEN** = **Jantina**, **DOB** = **Tarikh lahir**, **ST** = **Negeri**, **CT** = **Bandar**, **ZIP** = **Poskod / Kod Zip**, **COUNTRY** = **Negara / Rantau**</span><span class="sxs-lookup"><span data-stu-id="c5507-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="c5507-126">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="c5507-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="c5507-127">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="c5507-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c5507-128">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="c5507-128">Export the data</span></span>

<span data-ttu-id="c5507-129">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c5507-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c5507-130">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c5507-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c5507-131">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="c5507-131">Known limitations</span></span>

- <span data-ttu-id="c5507-132">Sehingga 10 juta profil pelanggan setiap eksport ke Pengurus Iklan Facebook</span><span class="sxs-lookup"><span data-stu-id="c5507-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="c5507-133">Eksport ke Pengurus Iklan Facebook adalah terhad kepada segmen</span><span class="sxs-lookup"><span data-stu-id="c5507-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="c5507-134">Mengeksport segmen dengan jumlah 10 juta profil boleh mengambil masa sehingga 90 minit untuk selesai</span><span class="sxs-lookup"><span data-stu-id="c5507-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c5507-135">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="c5507-135">Data privacy and compliance</span></span>

<span data-ttu-id="c5507-136">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Pengurus Iklan Facebook, anda membenarkan penghantaran data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="c5507-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c5507-137">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Iklan Facebook memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki.</span><span class="sxs-lookup"><span data-stu-id="c5507-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="c5507-138">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c5507-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c5507-139">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="c5507-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]