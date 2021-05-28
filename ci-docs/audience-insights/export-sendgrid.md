---
title: Eksport data Customer Insights ke SendGrid
description: Ketahui cara untuk mengkonfigurasikan sambungan dan eksport ke SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976927"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="dafa3-103">Eksport segmen ke SendGrid (pratonton)</span><span class="sxs-lookup"><span data-stu-id="dafa3-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="dafa3-104">Eksport segmen bagi profil pelanggan disatukan untuk senarai kenalan SendGrid dan gunakannya untuk kempen dan pemasaran e-mel dalam SendGrid.</span><span class="sxs-lookup"><span data-stu-id="dafa3-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="dafa3-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="dafa3-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="dafa3-106">Anda mempunyai [Akaun SendGrid](https://sendgrid.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="dafa3-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="dafa3-107">Terdapat senarai kenalan sedia ada dalam SendGrid dan ID yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="dafa3-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="dafa3-108">Untuk mendapatkan maklumat lanjut, lihat [SendGrid - Urus kenalan](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="dafa3-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="dafa3-109">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="dafa3-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="dafa3-110">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="dafa3-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="dafa3-111">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="dafa3-111">Known limitations</span></span>

- <span data-ttu-id="dafa3-112">Sehingga 100'000 profil dalam jumlah keseluruhan ke SendGrid.</span><span class="sxs-lookup"><span data-stu-id="dafa3-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="dafa3-113">Mengeksport ke SendGrid adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="dafa3-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="dafa3-114">Mengeksport sehingga 100'000 profil ke SendGrid boleh mengambil masa hingga beberapa jam untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="dafa3-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="dafa3-115">Bilangan profil yang boleh anda eksport ke SendGrid bergantung dan terhad pada kontrak anda dengan SendGrid.</span><span class="sxs-lookup"><span data-stu-id="dafa3-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="dafa3-116">Sediakan sambungan ke SendGrid</span><span class="sxs-lookup"><span data-stu-id="dafa3-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="dafa3-117">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="dafa3-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dafa3-118">Pilih **Tambah sambungan** dan pilih **SendGrid** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="dafa3-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="dafa3-119">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="dafa3-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="dafa3-120">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="dafa3-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="dafa3-121">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="dafa3-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dafa3-122">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="dafa3-122">Choose who can use this connection.</span></span> <span data-ttu-id="dafa3-123">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="dafa3-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dafa3-124">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="dafa3-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dafa3-125">Masukkan **Kekunci API SendGrid** [Kekunci API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="dafa3-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="dafa3-126">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="dafa3-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="dafa3-127">Pilih **Sambung** untuk memulakan sambungan ke SendGrid.</span><span class="sxs-lookup"><span data-stu-id="dafa3-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="dafa3-128">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="dafa3-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="dafa3-129">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="dafa3-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="dafa3-130">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="dafa3-130">Configure an export</span></span>

<span data-ttu-id="dafa3-131">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="dafa3-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dafa3-132">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="dafa3-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dafa3-133">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="dafa3-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dafa3-134">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="dafa3-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="dafa3-135">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian SendGrid.</span><span class="sxs-lookup"><span data-stu-id="dafa3-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="dafa3-136">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="dafa3-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="dafa3-137">Masukkan **[ID senarai SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** anda.</span><span class="sxs-lookup"><span data-stu-id="dafa3-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="dafa3-138">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="dafa3-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="dafa3-139">Ulangi langkah yang sama untuk medan pilihan lain seperti **Nama pertama**, **Nama akhir**, **Negara/Rantau**, **Negeri**. **Bandar** dan **Poskod**.</span><span class="sxs-lookup"><span data-stu-id="dafa3-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="dafa3-140">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="dafa3-140">Select the segments you want to export.</span></span> <span data-ttu-id="dafa3-141">Kami amat **mengesyorkan untuk tidak mengeksport lebih daripada 100'000 profil pelanggan dalam jumlah** ke SendGrid.</span><span class="sxs-lookup"><span data-stu-id="dafa3-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="dafa3-142">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="dafa3-142">Select **Save**.</span></span>

<span data-ttu-id="dafa3-143">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="dafa3-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dafa3-144">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dafa3-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dafa3-145">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dafa3-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dafa3-146">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="dafa3-146">Data privacy and compliance</span></span>

<span data-ttu-id="dafa3-147">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke SendGrid, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="dafa3-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dafa3-148">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa SendGrid memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki.</span><span class="sxs-lookup"><span data-stu-id="dafa3-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="dafa3-149">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dafa3-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dafa3-150">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="dafa3-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]