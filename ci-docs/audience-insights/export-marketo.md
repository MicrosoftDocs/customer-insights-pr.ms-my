---
title: Eksport data Customer Insights ke Marketo
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059327"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="84614-103">Eksport segmen ke Marketo (pratonton)</span><span class="sxs-lookup"><span data-stu-id="84614-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="84614-104">Eksport segmen profil pelanggan disatukan untuk menjana kempen, menyediakan pemasaran e-mel dan gunakan kumpulan pelanggan tertentu dengan Marketo.</span><span class="sxs-lookup"><span data-stu-id="84614-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="84614-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="84614-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="84614-106">Anda mempunyai [Akaun Marketo](https://login.marketo.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="84614-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="84614-107">Terdapat senarai sedia ada dalam Marketo dan ID yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="84614-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="84614-108">Untuk maklumat lanjut, lihat [Senarai Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="84614-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="84614-109">Anda telah [mengkonfigurasi segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="84614-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="84614-110">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="84614-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="84614-111">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="84614-111">Known limitations</span></span>

- <span data-ttu-id="84614-112">Hingga 1 juta profil bagi setiap eksport ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="84614-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="84614-113">Mengeksport ke Marketo adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="84614-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="84614-114">Mengeksport segmen dengan sejumlah 1 juta profil boleh mengambil masa sehingga 3 jam.</span><span class="sxs-lookup"><span data-stu-id="84614-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="84614-115">Bilangan profil yang boleh anda eksport ke Marketo bergantung dan terhad pada kontrak anda dengan Marketo.</span><span class="sxs-lookup"><span data-stu-id="84614-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="84614-116">Sediakan sambungan ke Marketo</span><span class="sxs-lookup"><span data-stu-id="84614-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="84614-117">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="84614-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="84614-118">Pilih **Tambah sambungan** dan pilih **Marketo** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="84614-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="84614-119">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="84614-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="84614-120">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="84614-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="84614-121">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="84614-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="84614-122">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="84614-122">Choose who can use this connection.</span></span> <span data-ttu-id="84614-123">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="84614-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="84614-124">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="84614-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="84614-125">Masukkan **[ID klien Marketo, Rahsia pelanggan dan Nama Hos Titik Tamat REST](https://developers.marketo.com/rest-api/authentication/)** anda.</span><span class="sxs-lookup"><span data-stu-id="84614-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="84614-126">Nama hos Titik tamat REST adalah nama hos sahaja tanpa `https://`.</span><span class="sxs-lookup"><span data-stu-id="84614-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="84614-127">Contoh: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="84614-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="84614-128">Pilih **Saya setuju** untuk mengesahkan **Privasi data dan pematuhan** dan pilih **Sambung** untuk memulakan sambungan ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="84614-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="84614-129">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="84614-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="84614-130">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="84614-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="84614-131">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="84614-131">Configure an export</span></span>

<span data-ttu-id="84614-132">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="84614-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="84614-133">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="84614-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="84614-134">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="84614-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="84614-135">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="84614-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="84614-136">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Marketo.</span><span class="sxs-lookup"><span data-stu-id="84614-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="84614-137">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="84614-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="84614-138">Masukkan **[ID senarai Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** anda.</span><span class="sxs-lookup"><span data-stu-id="84614-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="84614-139">ID senarai adalah semata-mata nilai berangka.</span><span class="sxs-lookup"><span data-stu-id="84614-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="84614-140">Contohnya, jika ID senarai Marketo anda ialah ST12345A7, alih keluar aksara sebelum dan selepas angka dan masukkan `12345`.</span><span class="sxs-lookup"><span data-stu-id="84614-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="84614-141">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="84614-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="84614-142">Selain itu, anda boleh mengeksport **Nama pertama**, **Nama terakhir**, **Bandar**, **Negeri**, dan **Negeri/Rantau**  untuk mencipta e-mel yang diperibadikan.</span><span class="sxs-lookup"><span data-stu-id="84614-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="84614-143">Pilih **Tambah atribut** untuk memetakan medan ini.</span><span class="sxs-lookup"><span data-stu-id="84614-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="84614-144">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="84614-144">Select the segments you want to export.</span></span> <span data-ttu-id="84614-145">Anda boleh mengeksport hingga 1 juta jumlah profil pelanggan ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="84614-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="84614-146">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="84614-146">Select **Save**.</span></span>

<span data-ttu-id="84614-147">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="84614-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="84614-148">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="84614-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="84614-149">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="84614-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="84614-150">Dalam Marketo, anda kini boleh mencari segmen anda di bawah [Senarai Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="84614-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="84614-151">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="84614-151">Data privacy and compliance</span></span>

<span data-ttu-id="84614-152">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Marketo, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="84614-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="84614-153">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Marketo memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="84614-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="84614-154">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="84614-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="84614-155">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="84614-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
