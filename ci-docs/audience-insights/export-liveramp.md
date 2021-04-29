---
title: LiveRamp penyambung
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760338"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="6aa94-103">Eksport segmen ke LiveRamp&reg; (pratonton)</span><span class="sxs-lookup"><span data-stu-id="6aa94-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="6aa94-104">Aktifkan data anda dalam LiveRamp untuk berhubung dengan lebih daripada 500 platform merentasi digital, sosial, dan TV.</span><span class="sxs-lookup"><span data-stu-id="6aa94-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="6aa94-105">Bekerja dengan data anda dalam LiveRamp untuk mensasar, menahan, dan memperibadikan kempen iklan.</span><span class="sxs-lookup"><span data-stu-id="6aa94-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="6aa94-106">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="6aa94-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="6aa94-107">Anda memerlukan langganan LiveRamp untuk menggunakan penyambung ini.</span><span class="sxs-lookup"><span data-stu-id="6aa94-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="6aa94-108">Untuk mendapatkan langganan, [hubungi LiveRamp](https://liveramp.com/contact/) secara terus.</span><span class="sxs-lookup"><span data-stu-id="6aa94-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="6aa94-109">[Ketahui lanjut tentang Penyertaan LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="6aa94-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="6aa94-110">Sediakan sambungan ke LiveRamp</span><span class="sxs-lookup"><span data-stu-id="6aa94-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="6aa94-111">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="6aa94-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6aa94-112">Pilih **Tambah sambungan** dan pilih **LiveRamp** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="6aa94-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="6aa94-113">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="6aa94-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6aa94-114">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="6aa94-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6aa94-115">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="6aa94-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6aa94-116">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="6aa94-116">Choose who can use this connection.</span></span> <span data-ttu-id="6aa94-117">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="6aa94-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6aa94-118">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6aa94-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6aa94-119">Sediakan **Nama Pengguna** dan **Kata Laluan** untuk akaun LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="6aa94-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="6aa94-120">Kelayakan ini berkemungkinan berbeza daripada kelayakan Penyertaan LiveRamp anda.</span><span class="sxs-lookup"><span data-stu-id="6aa94-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="6aa94-121">Pilih **Sahkan** untuk menguji sambungan ke LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="6aa94-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="6aa94-122">Selepas pengesahan berjaya, sediakan keizinan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="6aa94-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="6aa94-123">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="6aa94-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6aa94-124">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="6aa94-124">Configure an export</span></span>

<span data-ttu-id="6aa94-125">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="6aa94-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6aa94-126">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6aa94-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6aa94-127">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="6aa94-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6aa94-128">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="6aa94-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6aa94-129">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="6aa94-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="6aa94-130">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="6aa94-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6aa94-131">Dalam medan **Pilih pengecam kunci anda**, pilih **E-mel**,  **Nama dan alamat**, atau **Telefon** untuk menghantar ke LiveRamp untuk penyelesaian identiti.</span><span class="sxs-lookup"><span data-stu-id="6aa94-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6aa94-132">![Penyambung LiveRamp dengan atribut pemetaan](media/export-liveramp-segments.png "Penyambung LiveRamp dengan atribut pemetaan")</span><span class="sxs-lookup"><span data-stu-id="6aa94-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="6aa94-133">Petakan atribut yang sepadan daripada entiti pelanggan disatukan anda untuk pengecam kunci yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="6aa94-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="6aa94-134">Pilih **Tambah atribut** untuk memetakan lebih banyak atribut untuk dihantar ke LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="6aa94-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="6aa94-135">Menghantar lebih banyak atribut pengecam kunci ke LiveRamp mempunyai kemungkinan besar untuk anda mendapatkan kadar pemadanan yang tinggi.</span><span class="sxs-lookup"><span data-stu-id="6aa94-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="6aa94-136">Pilih segmen yang anda mahu eksport ke LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="6aa94-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="6aa94-137">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="6aa94-137">Select **Save**.</span></span>

<span data-ttu-id="6aa94-138">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="6aa94-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6aa94-139">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6aa94-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6aa94-140">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6aa94-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6aa94-141">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="6aa94-141">Data privacy and compliance</span></span>

<span data-ttu-id="6aa94-142">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke LiveRamp, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="6aa94-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6aa94-143">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa LiveRamp memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="6aa94-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6aa94-144">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6aa94-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6aa94-145">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="6aa94-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
