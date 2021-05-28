---
title: Eksport data Customer Insights ke Pengurus Iklan Facebook
description: Ketahui cara untuk mengkonfigurasikan sambungan dan Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976053"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="b1e87-103">Eksport senarai segmen ke Facebook Ads Manager (pratonton)</span><span class="sxs-lookup"><span data-stu-id="b1e87-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="b1e87-104">Eksport segmen profil pelanggan disatukan ke Pengurus Iklan Facebook untuk mencipta kempen pada Facebook dan Instagram.</span><span class="sxs-lookup"><span data-stu-id="b1e87-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="b1e87-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="b1e87-105">Prerequisites for connection</span></span>

- <span data-ttu-id="b1e87-106">Anda perlu mempunyai [Akaun iklan **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) yang termasuk [Akaun Perniagaan **Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="b1e87-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="b1e87-107">Anda perlu menjadi pentadbir pada [Akaun Iklan **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="b1e87-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b1e87-108">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="b1e87-108">Known limitations</span></span>

- <span data-ttu-id="b1e87-109">Sehingga 10 juta profil pelanggan bagi setiap eksport ke Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="b1e87-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="b1e87-110">Eksport ke Facebook Ads Manager adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="b1e87-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="b1e87-111">Cipta atau kemas kini khalayak tersuai dalam Facebook bagi jenis *senarai pelanggan* sahaja.</span><span class="sxs-lookup"><span data-stu-id="b1e87-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="b1e87-112">Mengeksport segmen dengan jumlah 10 juta profil boleh mengambil masa sehingga 90 minit untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="b1e87-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="b1e87-113">Sediakan sambungan ke Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="b1e87-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="b1e87-114">Sebelum pengguna boleh mencipta eksport, pentadbir mesti mengkonfigurasikan sambungan ke perkhidmatan dan membenarkan penyumbang untuk menggunakan sambungan.</span><span class="sxs-lookup"><span data-stu-id="b1e87-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="b1e87-115">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="b1e87-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b1e87-116">Pilih **Tambah sambungan** dan pilih **Facebook Ads Manager** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="b1e87-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="b1e87-117">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="b1e87-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b1e87-118">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="b1e87-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b1e87-119">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="b1e87-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b1e87-120">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="b1e87-120">Choose who can use this connection.</span></span> <span data-ttu-id="b1e87-121">Jika anda tidak mengambil tindakan, lalai akan menjadi **Pentadbir**.</span><span class="sxs-lookup"><span data-stu-id="b1e87-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="b1e87-122">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b1e87-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b1e87-123">Sahkan dengan Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="b1e87-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="b1e87-124">Pilih **Teruskan dengan Facebook** untuk mendaftar masuk ke Akaun Iklan Facebook.</span><span class="sxs-lookup"><span data-stu-id="b1e87-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="b1e87-125">Benarkan keizinan **ads_management** selepas pengesahan dengan Facebook.</span><span class="sxs-lookup"><span data-stu-id="b1e87-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="b1e87-126">Pilih **Akaun Iklan Facebook** yang anda ingin kendalikan.</span><span class="sxs-lookup"><span data-stu-id="b1e87-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="b1e87-127">Pilih **Khalayak tersuai sedia ada** daripada senarai juntai bawah atau cipta **Khalayak tersuai baharu**.</span><span class="sxs-lookup"><span data-stu-id="b1e87-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="b1e87-128">Untuk maklumat lanjut, lihat [**Khalayak dalam Pengurus Iklan Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="b1e87-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="b1e87-129">Anda hanya boleh mencipta atau mengemas kini khalayak tersuai di Facebook untuk jenis *senarai pelanggan* dengan eksport ini.</span><span class="sxs-lookup"><span data-stu-id="b1e87-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="b1e87-130">Dalam sesetengah kes, anda melihat khalayak tersuai untuk pelbagai jenis dalam senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="b1e87-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="b1e87-131">Memilih jenis yang berbeza daripada *senarai pelanggan* akan menggagalkan eksport.</span><span class="sxs-lookup"><span data-stu-id="b1e87-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="b1e87-132">Semak **Privasi data dan pematuhan** dan pilih **Saya bersetuju**.</span><span class="sxs-lookup"><span data-stu-id="b1e87-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="b1e87-133">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="b1e87-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b1e87-134">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="b1e87-134">Configure an export</span></span>

<span data-ttu-id="b1e87-135">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="b1e87-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b1e87-136">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b1e87-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b1e87-137">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="b1e87-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b1e87-138">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="b1e87-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="b1e87-139">Dalam **Sambungan untuk eksport**, pilih sambungan daripada bahagian **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="b1e87-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="b1e87-140">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="b1e87-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b1e87-141">Dalam **Pilih medan pengecam kunci anda**, pilih **E-mel**, **Nama dan alamat**, atau **Telefon** untuk dihantar ke Pengurus Iklan Facebook.</span><span class="sxs-lookup"><span data-stu-id="b1e87-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="b1e87-142">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="b1e87-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b1e87-143">Petakan atribut yang sepadan daripada entiti pelanggan disatukan anda untuk pengecam kunci yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="b1e87-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="b1e87-144">[TIP] Peluang terbaik untuk padanan berlaku jika anda memilih **E-mel** sebagai pengecam kunci.</span><span class="sxs-lookup"><span data-stu-id="b1e87-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="b1e87-145">Menambah pengecam tambahan mungkin meningkatkan pemadanan.</span><span class="sxs-lookup"><span data-stu-id="b1e87-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="b1e87-146">Pilih **Tambah atribut** untuk memetakan lebih banyak atribut untuk dihantar kepada Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="b1e87-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="b1e87-147">Atribut daripada Facebook Ads Manager dipetakan pada nama mesra pengguna berikut: **FN** = **Nama Pertama**, **LN** = **Nama Keluarga**, **FI** = **Parap Pertama**, **PHONE** = **Telefon**, **GEN** = **Jantina**, **DOB** = **Tarikh Lahir**, **ST** = **Negeri**, **CT** = **Bandar**, **ZIP** = **Poskod/Kod Zip**, **COUNTRY** = **Negara/Rantau**</span><span class="sxs-lookup"><span data-stu-id="b1e87-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="b1e87-148">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="b1e87-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="b1e87-149">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="b1e87-149">Select **Save**.</span></span>

<span data-ttu-id="b1e87-150">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="b1e87-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b1e87-151">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b1e87-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b1e87-152">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b1e87-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b1e87-153">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="b1e87-153">Data privacy and compliance</span></span>

<span data-ttu-id="b1e87-154">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Pengurus Iklan Facebook, anda membenarkan penghantaran data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="b1e87-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b1e87-155">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Iklan Facebook memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki.</span><span class="sxs-lookup"><span data-stu-id="b1e87-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b1e87-156">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b1e87-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b1e87-157">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="b1e87-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
