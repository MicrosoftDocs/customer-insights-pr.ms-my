---
title: Eksport data Customer Insights ke DotDigital
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124422"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="e6ee1-103">Eksport segmen ke DotDigital (pratonton)</span><span class="sxs-lookup"><span data-stu-id="e6ee1-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="e6ee1-104">Eksport segmen profil pelanggan disatukan ke buku alamat DotDigital dan gunakannya untuk kempen, pemasaran e-mel dan untuk membina segmen pelanggan dengan DotDigital.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e6ee1-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="e6ee1-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e6ee1-106">Anda mempunyai [Akaun DotDigital](https://dotdigital.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e6ee1-107">Terdapat buku alamat sedia ada dalam DotDigital dan ID yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="e6ee1-108">ID boleh ditemui dalam URL apabila anda memilih dan membuka buku alamat.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="e6ee1-109">Untuk maklumat lanjut, lihat [Buku alamat DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="e6ee1-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="e6ee1-110">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e6ee1-111">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e6ee1-112">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="e6ee1-112">Known limitations</span></span>

- <span data-ttu-id="e6ee1-113">Hingga 1 juta profil bagi setiap eksport ke DotDigital.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="e6ee1-114">Mengeksport ke DotDigital adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="e6ee1-115">Mengeksport segmen dengan jumlah 1 juta profil boleh mengambil masa hingga 3 jam kerana had pada bahagian pembekal.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="e6ee1-116">Bilangan profil yang boleh anda eksport ke DotDigital bergantung dan terhad pada kontrak anda dengan DotDigital.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="e6ee1-117">Sediakan sambungan ke DotDigital</span><span class="sxs-lookup"><span data-stu-id="e6ee1-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="e6ee1-118">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e6ee1-119">Pilih **Tambah sambungan** dan pilih **DotDigital** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="e6ee1-120">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e6ee1-121">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e6ee1-122">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e6ee1-123">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-123">Choose who can use this connection.</span></span> <span data-ttu-id="e6ee1-124">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e6ee1-125">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e6ee1-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e6ee1-126">Masukkan **Nama pengguna dan kata laluan DotDigital** anda.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="e6ee1-127">Masukkan **[ID buku alamat DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** anda.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="e6ee1-128">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e6ee1-129">Pilih **Sambung** untuk memulakan sambungan ke DotDigital.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="e6ee1-130">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e6ee1-131">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="e6ee1-132">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="e6ee1-132">Configure an export</span></span>

<span data-ttu-id="e6ee1-133">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e6ee1-134">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e6ee1-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e6ee1-135">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e6ee1-136">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e6ee1-137">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian DotDigital.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="e6ee1-138">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="e6ee1-139">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e6ee1-140">Ulangi langkah yang sama untuk medan pilihan lain seperti **Nama pertama**, **Nama akhir**, **Nama penuh**, **Jantina** dan **Poskod**.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="e6ee1-141">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-141">Select the segments you want to export.</span></span> <span data-ttu-id="e6ee1-142">Anda boleh mengeksport hingga 1 juta profil pelanggan dalam jumlah keseluruhan DotDigital.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="e6ee1-143">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-143">Select **Save**.</span></span>

<span data-ttu-id="e6ee1-144">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e6ee1-145">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e6ee1-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e6ee1-146">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e6ee1-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="e6ee1-147">Dalam DotDigital, anda kini boleh mencari segmen anda dalam [Buku alamat DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="e6ee1-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e6ee1-148">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="e6ee1-148">Data privacy and compliance</span></span>

<span data-ttu-id="e6ee1-149">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke DotDigital, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e6ee1-150">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa DotDigital memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e6ee1-151">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e6ee1-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e6ee1-152">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="e6ee1-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
