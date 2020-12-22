---
title: Eksport data Customer Insights ke hos SFTP
description: Ketahui cara mengkonfigurasi sambungan ke hos SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643514"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="f80cc-103">Penyambung untuk SFTP (pratonton)</span><span class="sxs-lookup"><span data-stu-id="f80cc-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="f80cc-104">Gunakan data pelanggan anda dalam aplikasi pihak ketiga dengan mengeksportnya ke hos Protokol Pemindahan Fail Selamat (SFTP).</span><span class="sxs-lookup"><span data-stu-id="f80cc-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f80cc-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="f80cc-105">Prerequisites</span></span>

- <span data-ttu-id="f80cc-106">Ketersediaan hos SFTP dan kelayakan yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="f80cc-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="f80cc-107">Sambung ke SFTP</span><span class="sxs-lookup"><span data-stu-id="f80cc-107">Connect to SFTP</span></span>

1. <span data-ttu-id="f80cc-108">Pergi ke **Pentadbir** > **Destinasi Eksport**.</span><span class="sxs-lookup"><span data-stu-id="f80cc-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f80cc-109">Di bawah **SFTP**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="f80cc-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="f80cc-110">Berikan destinasi anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="f80cc-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f80cc-111">Menyediakan **Nama pengguna**, **Kata laluan** dan **Nama hos** untuk akaun SFTP anda.</span><span class="sxs-lookup"><span data-stu-id="f80cc-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="f80cc-112">Contoh: Jika folder akar pelayan SFTP anda adalah /root/folder dan anda mahu data dieksport ke /root/folder/ci_export_destination_folder, hos tersebut sepatutnya menjadi sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="f80cc-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="f80cc-113">Pilih **Sahkan** untuk menguji sambungan.</span><span class="sxs-lookup"><span data-stu-id="f80cc-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="f80cc-114">Selepas pengesahan berjaya, pilih jika anda mahu mengeksport data **Dizip** atau **Dinyahzip** dan pilih **pembatas medan** untuk fail yang dieksport.</span><span class="sxs-lookup"><span data-stu-id="f80cc-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="f80cc-115">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="f80cc-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f80cc-116">Pilih **Seterusnya** untuk memulakan konfigurasi eksport.</span><span class="sxs-lookup"><span data-stu-id="f80cc-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="f80cc-117">Konfigurasi sambungan</span><span class="sxs-lookup"><span data-stu-id="f80cc-117">Configure the connection</span></span>

1. <span data-ttu-id="f80cc-118">Pilih **atribut pelanggan** yang anda mahu eksport.</span><span class="sxs-lookup"><span data-stu-id="f80cc-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="f80cc-119">Anda boleh eksport satu atau berbilang atribut.</span><span class="sxs-lookup"><span data-stu-id="f80cc-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="f80cc-120">Pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="f80cc-120">Select **Next**.</span></span>

1. <span data-ttu-id="f80cc-121">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="f80cc-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="f80cc-122">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="f80cc-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f80cc-123">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="f80cc-123">Export the data</span></span>

<span data-ttu-id="f80cc-124">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f80cc-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f80cc-125">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f80cc-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f80cc-126">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="f80cc-126">Data privacy and compliance</span></span>

<span data-ttu-id="f80cc-127">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data melalui SFTP, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="f80cc-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f80cc-128">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa destinasi eksport memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="f80cc-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f80cc-129">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f80cc-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f80cc-130">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="f80cc-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
