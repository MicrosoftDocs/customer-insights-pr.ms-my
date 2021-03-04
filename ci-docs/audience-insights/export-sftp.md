---
title: Eksport data Customer Insights ke hos SFTP
description: Ketahui cara mengkonfigurasi sambungan ke hos SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268009"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="8b68e-103">Penyambung untuk SFTP (pratonton)</span><span class="sxs-lookup"><span data-stu-id="8b68e-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="8b68e-104">Gunakan data pelanggan anda dalam aplikasi pihak ketiga dengan mengeksportnya ke hos Protokol Pemindahan Fail Selamat (SFTP).</span><span class="sxs-lookup"><span data-stu-id="8b68e-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8b68e-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="8b68e-105">Prerequisites</span></span>

- <span data-ttu-id="8b68e-106">Ketersediaan hos SFTP dan kelayakan yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="8b68e-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="8b68e-107">Sambung kepada SFTP</span><span class="sxs-lookup"><span data-stu-id="8b68e-107">Connect to SFTP</span></span>

1. <span data-ttu-id="8b68e-108">Pergi ke **Pentadbir** > **Destinasi Eksport**.</span><span class="sxs-lookup"><span data-stu-id="8b68e-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8b68e-109">Di bawah **SFTP**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="8b68e-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="8b68e-110">Berikan destinasi anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="8b68e-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8b68e-111">Menyediakan **Nama pengguna**, **Kata laluan**, **Nama hos**, dan **Eksport folder** untuk akaun SFTP anda.</span><span class="sxs-lookup"><span data-stu-id="8b68e-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="8b68e-112">Pilih **Sahkan** untuk menguji sambungan.</span><span class="sxs-lookup"><span data-stu-id="8b68e-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="8b68e-113">Selepas pengesahan berjaya, pilih sama ada anda mahu mengeksport data anda **Digzip** atau **Dinyahzip** dan pilih **pemisah medan** untuk fail yang dieksport.</span><span class="sxs-lookup"><span data-stu-id="8b68e-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="8b68e-114">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="8b68e-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8b68e-115">Pilih **Seterusnya** untuk memulakan konfigurasi eksport.</span><span class="sxs-lookup"><span data-stu-id="8b68e-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="8b68e-116">Konfigurasi eksport</span><span class="sxs-lookup"><span data-stu-id="8b68e-116">Configure the export</span></span>

1. <span data-ttu-id="8b68e-117">Pilih entiti, contohnya segmen, yang anda mahu mengeksport.</span><span class="sxs-lookup"><span data-stu-id="8b68e-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8b68e-118">Setiap entiti yang dipilih akan meningkat kepada lima fail output apabila dieksport.</span><span class="sxs-lookup"><span data-stu-id="8b68e-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="8b68e-119">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="8b68e-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8b68e-120">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="8b68e-120">Export the data</span></span>

<span data-ttu-id="8b68e-121">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8b68e-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8b68e-122">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8b68e-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8b68e-123">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="8b68e-123">Known limitations</span></span>

- <span data-ttu-id="8b68e-124">Masa jalanan eksport bergantung pada prestasi sistem anda.</span><span class="sxs-lookup"><span data-stu-id="8b68e-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="8b68e-125">Kami mengesyorkan dua CPU teras dan 1 Gb memori sebagai konfigurasi minimum pelayan anda.</span><span class="sxs-lookup"><span data-stu-id="8b68e-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="8b68e-126">Mengeksport entiti sehingga 100 juta profil pelanggan boleh mengambil masa 90 minit apabila menggunakan konfigurasi minimum yang disyorkan iaitu dua CPU teras dan 1 Gb memori.</span><span class="sxs-lookup"><span data-stu-id="8b68e-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8b68e-127">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="8b68e-127">Data privacy and compliance</span></span>

<span data-ttu-id="8b68e-128">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data melalui SFTP, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="8b68e-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8b68e-129">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa destinasi eksport memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="8b68e-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8b68e-130">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8b68e-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8b68e-131">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="8b68e-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]