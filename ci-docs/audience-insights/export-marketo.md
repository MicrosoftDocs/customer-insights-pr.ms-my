---
title: Eksport data Customer Insights ke Marketo
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759832"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="074c8-103">Eksport segmen ke Marketo (pratonton)</span><span class="sxs-lookup"><span data-stu-id="074c8-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="074c8-104">Eksport segmen profil pelanggan disatukan untuk menjana kempen, menyediakan pemasaran e-mel dan gunakan kumpulan pelanggan tertentu dengan Marketo.</span><span class="sxs-lookup"><span data-stu-id="074c8-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="074c8-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="074c8-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="074c8-106">Anda mempunyai [Akaun Marketo](https://login.marketo.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="074c8-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="074c8-107">Terdapat senarai sedia ada dalam Marketo dan ID yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="074c8-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="074c8-108">Untuk maklumat lanjut, lihat [Senarai Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="074c8-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="074c8-109">Anda telah [mengkonfigurasi segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="074c8-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="074c8-110">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="074c8-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="074c8-111">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="074c8-111">Known limitations</span></span>

- <span data-ttu-id="074c8-112">Hingga 1 juta profil bagi setiap eksport ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="074c8-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="074c8-113">Mengeksport ke Marketo adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="074c8-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="074c8-114">Mengeksport segmen dengan sejumlah 1 juta profil boleh mengambil masa sehingga 3 jam.</span><span class="sxs-lookup"><span data-stu-id="074c8-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="074c8-115">Bilangan profil yang boleh anda eksport ke Marketo bergantung dan terhad pada kontrak anda dengan Marketo.</span><span class="sxs-lookup"><span data-stu-id="074c8-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="074c8-116">Sediakan sambungan ke Marketo</span><span class="sxs-lookup"><span data-stu-id="074c8-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="074c8-117">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="074c8-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="074c8-118">Pilih **Tambah sambungan** dan pilih **Marketo** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="074c8-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="074c8-119">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="074c8-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="074c8-120">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="074c8-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="074c8-121">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="074c8-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="074c8-122">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="074c8-122">Choose who can use this connection.</span></span> <span data-ttu-id="074c8-123">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="074c8-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="074c8-124">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="074c8-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="074c8-125">Masukkan **[ID klien Marketo, Rahsia pelanggan dan Nama Hos Titik Tamat REST](https://developers.marketo.com/rest-api/authentication/)** anda.</span><span class="sxs-lookup"><span data-stu-id="074c8-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="074c8-126">Pilih **Saya setuju** untuk mengesahkan **Privasi data dan pematuhan** dan pilih **Sambung** untuk memulakan sambungan ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="074c8-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="074c8-127">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="074c8-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="074c8-128">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="074c8-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="074c8-129">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="074c8-129">Configure an export</span></span>

<span data-ttu-id="074c8-130">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="074c8-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="074c8-131">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="074c8-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="074c8-132">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="074c8-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="074c8-133">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="074c8-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="074c8-134">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Marketo.</span><span class="sxs-lookup"><span data-stu-id="074c8-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="074c8-135">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="074c8-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="074c8-136">Masukkan **[ID senarai Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** anda</span><span class="sxs-lookup"><span data-stu-id="074c8-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="074c8-137">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="074c8-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="074c8-138">Selain itu, anda boleh mengeksport **Nama pertama**, **Nama terakhir**, **Bandar**, **Negeri**, dan **Negeri/Rantau**  untuk mencipta e-mel yang diperibadikan.</span><span class="sxs-lookup"><span data-stu-id="074c8-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="074c8-139">Pilih **Tambah atribut** untuk memetakan medan ini.</span><span class="sxs-lookup"><span data-stu-id="074c8-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="074c8-140">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="074c8-140">Select the segments you want to export.</span></span> <span data-ttu-id="074c8-141">Anda boleh mengeksport hingga 1 juta jumlah profil pelanggan ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="074c8-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="074c8-142">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="074c8-142">Select **Save**.</span></span>

<span data-ttu-id="074c8-143">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="074c8-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="074c8-144">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="074c8-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="074c8-145">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="074c8-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="074c8-146">Dalam Marketo, anda kini boleh mencari segmen anda di bawah [Senarai Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="074c8-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="074c8-147">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="074c8-147">Data privacy and compliance</span></span>

<span data-ttu-id="074c8-148">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Marketo, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="074c8-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="074c8-149">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Marketo memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="074c8-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="074c8-150">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="074c8-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="074c8-151">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="074c8-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]