---
title: Eksport data Customer Insights ke hos SFTP
description: Ketahui cara mengkonfigurasi sambungan dan mengeksport ke lokasi SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124330"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a><span data-ttu-id="558b9-103">Eksport segmen dan data lain ke SFTP (pratonton)</span><span class="sxs-lookup"><span data-stu-id="558b9-103">Export segments and other data to SFTP (preview)</span></span>

<span data-ttu-id="558b9-104">Gunakan data pelanggan anda dalam aplikasi pihak ketiga dengan mengeksportnya ke lokasi Protokol Pemindahan Fail Selamat (SFTP).</span><span class="sxs-lookup"><span data-stu-id="558b9-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="558b9-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="558b9-105">Prerequisites for connection</span></span>

- <span data-ttu-id="558b9-106">Ketersediaan hos SFTP dan kelayakan yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="558b9-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="558b9-107">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="558b9-107">Known limitations</span></span>

- <span data-ttu-id="558b9-108">Masa jalanan eksport bergantung pada prestasi sistem anda.</span><span class="sxs-lookup"><span data-stu-id="558b9-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="558b9-109">Kami mengesyorkan dua CPU teras dan 1 Gb memori sebagai konfigurasi minimum pelayan anda.</span><span class="sxs-lookup"><span data-stu-id="558b9-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="558b9-110">Mengeksport entiti sehingga 100 juta profil pelanggan boleh mengambil masa 90 minit apabila menggunakan konfigurasi minimum yang disyorkan iaitu dua CPU teras dan 1 Gb memori.</span><span class="sxs-lookup"><span data-stu-id="558b9-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="558b9-111">Sediakan sambungan ke SFTP</span><span class="sxs-lookup"><span data-stu-id="558b9-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="558b9-112">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="558b9-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="558b9-113">Pilih **Tambah sambungan** dan pilih **SFTP** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="558b9-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="558b9-114">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="558b9-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="558b9-115">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="558b9-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="558b9-116">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="558b9-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="558b9-117">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="558b9-117">Choose who can use this connection.</span></span> <span data-ttu-id="558b9-118">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="558b9-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="558b9-119">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="558b9-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="558b9-120">Menyediakan **Nama pengguna**, **Kata laluan**, **Nama hos**, dan **Eksport folder** untuk akaun SFTP anda.</span><span class="sxs-lookup"><span data-stu-id="558b9-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="558b9-121">Pilih **Sahkan** untuk menguji sambungan.</span><span class="sxs-lookup"><span data-stu-id="558b9-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="558b9-122">Pilih sama ada anda mahu mengeksport data **Gzipped** atau **Unzipped** dan **penyahhad medan** untuk fail yang dieksport.</span><span class="sxs-lookup"><span data-stu-id="558b9-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="558b9-123">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="558b9-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="558b9-124">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="558b9-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="558b9-125">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="558b9-125">Configure an export</span></span>

<span data-ttu-id="558b9-126">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="558b9-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="558b9-127">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="558b9-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="558b9-128">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="558b9-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="558b9-129">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="558b9-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="558b9-130">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian SFTP.</span><span class="sxs-lookup"><span data-stu-id="558b9-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="558b9-131">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="558b9-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="558b9-132">Pilih entiti, contohnya segmen, yang anda mahu mengeksport.</span><span class="sxs-lookup"><span data-stu-id="558b9-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="558b9-133">Setiap entiti yang dipilih akan dibahagikan kepada lima fail output apabila dieksport.</span><span class="sxs-lookup"><span data-stu-id="558b9-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="558b9-134">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="558b9-134">Select **Save**.</span></span>

<span data-ttu-id="558b9-135">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="558b9-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="558b9-136">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="558b9-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="558b9-137">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="558b9-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="558b9-138">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="558b9-138">Data privacy and compliance</span></span>

<span data-ttu-id="558b9-139">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data melalui SFTP, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="558b9-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="558b9-140">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa destinasi eksport memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="558b9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="558b9-141">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="558b9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="558b9-142">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="558b9-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
