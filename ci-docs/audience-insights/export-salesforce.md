---
title: Eksport data Customer Insights pada Salesforce Marketing Cloud
description: Ketahui cara mengkonfigurasikan sambungan dan mengeksport pada Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314648"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="6c15a-103">Segmen eksport dan data lain pada Salesforce Marketing Cloud (pratonton)</span><span class="sxs-lookup"><span data-stu-id="6c15a-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="6c15a-104">Gunakan data pelanggan anda dalam Salesforce Marketing Cloud dengan mengeksport data itu melalui lokasi Protokol Pemindahan Fail Selamat (SFTP).</span><span class="sxs-lookup"><span data-stu-id="6c15a-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="6c15a-105">Prasyarat untuk sambungan</span><span class="sxs-lookup"><span data-stu-id="6c15a-105">Prerequisites for connection</span></span>

- <span data-ttu-id="6c15a-106">Ketersediaan hos SFTP dan kelayakan pentadbir yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="6c15a-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="6c15a-107">Cara menyediakan lokasi SFTP untuk Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="6c15a-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="6c15a-108">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="6c15a-108">Known limitations</span></span>

- <span data-ttu-id="6c15a-109">Masa jalanan eksport bergantung pada prestasi sistem anda.</span><span class="sxs-lookup"><span data-stu-id="6c15a-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="6c15a-110">Kami mengesyorkan dua CPU teras dan 1 Gb memori sebagai konfigurasi minimum pelayan anda.</span><span class="sxs-lookup"><span data-stu-id="6c15a-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="6c15a-111">Mengeksport entiti dengan sehingga 100 juta profil pelanggan boleh mengambil masa 90 minit apabila menggunakan konfigurasi minimum yang disyorkan.</span><span class="sxs-lookup"><span data-stu-id="6c15a-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="6c15a-112">Sediakan sambungan kepada Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="6c15a-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="6c15a-113">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="6c15a-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6c15a-114">Pilih **Tambah sambungan** dan pilih **Salesforce Marketing Cloud** untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="6c15a-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="6c15a-115">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="6c15a-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6c15a-116">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="6c15a-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6c15a-117">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="6c15a-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6c15a-118">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="6c15a-118">Choose who can use this connection.</span></span> <span data-ttu-id="6c15a-119">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="6c15a-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6c15a-120">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6c15a-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6c15a-121">Menyediakan **Nama pengguna**, **Kata laluan**, **Nama hos**, dan **Eksport folder** untuk akaun SFTP anda.</span><span class="sxs-lookup"><span data-stu-id="6c15a-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="6c15a-122">Pilih **Sahkan** untuk menguji sambungan.</span><span class="sxs-lookup"><span data-stu-id="6c15a-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="6c15a-123">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="6c15a-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6c15a-124">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="6c15a-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6c15a-125">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="6c15a-125">Configure an export</span></span>

<span data-ttu-id="6c15a-126">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="6c15a-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6c15a-127">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6c15a-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6c15a-128">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="6c15a-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6c15a-129">Untuk mencipta eksport baharu, pilih **Tambah destinasi**.</span><span class="sxs-lookup"><span data-stu-id="6c15a-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6c15a-130">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian SFTP.</span><span class="sxs-lookup"><span data-stu-id="6c15a-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="6c15a-131">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="6c15a-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6c15a-132">Pilih sama ada anda mahu mengeksport data **Gzipped** atau **Unzipped** dan **penyahhad medan** untuk fail yang dieksport.</span><span class="sxs-lookup"><span data-stu-id="6c15a-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="6c15a-133">Pilih entiti, contohnya segmen, yang anda mahu mengeksport.</span><span class="sxs-lookup"><span data-stu-id="6c15a-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6c15a-134">Setiap entiti yang dipilih akan dibahagikan kepada lima fail output apabila dieksport.</span><span class="sxs-lookup"><span data-stu-id="6c15a-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="6c15a-135">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="6c15a-135">Select **Save**.</span></span>

<span data-ttu-id="6c15a-136">Menyimpan eksport tidak menjalankan eksport dengan serta-merta.</span><span class="sxs-lookup"><span data-stu-id="6c15a-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6c15a-137">Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6c15a-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6c15a-138">Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6c15a-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="6c15a-139">Import data Customer Insights daripada from lokasi pada Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="6c15a-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="6c15a-140">Cipta [sambungan data dalam Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) untuk mengimport fail data Customer Insights daripada lokasi SFTP.</span><span class="sxs-lookup"><span data-stu-id="6c15a-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="6c15a-141">[Import data daripada lokasi SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) ke dalam sambungan data Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="6c15a-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="6c15a-142">Sediakan automasi untuk mengimport data ke dalam sambungan data.</span><span class="sxs-lookup"><span data-stu-id="6c15a-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="6c15a-143">Ketahui lebih lanjut tentang [automasi penurunan fail dan automasi berjadual](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="6c15a-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="6c15a-144">Tentukan [automasi penurunan fail](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) atau [automasi berjadual](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="6c15a-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="6c15a-145">Berikut ialah contoh bagi [automasi dengan SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="6c15a-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6c15a-146">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="6c15a-146">Data privacy and compliance</span></span>

<span data-ttu-id="6c15a-147">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data melalui SFTP, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="6c15a-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6c15a-148">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa destinasi eksport memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="6c15a-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6c15a-149">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6c15a-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6c15a-150">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="6c15a-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
