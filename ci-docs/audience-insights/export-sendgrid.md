---
title: Eksport data Customer Insights ke SendGrid
description: Ketahui cara mengkonfigurasi sambungan ke SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597292"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="08d43-103">Penyambung untuk SendGrid (pratonton)</span><span class="sxs-lookup"><span data-stu-id="08d43-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="08d43-104">Eksport segmen bagi profil pelanggan disatukan untuk senarai kenalan SendGrid dan gunakannya untuk kempen dan pemasaran e-mel dalam SendGrid.</span><span class="sxs-lookup"><span data-stu-id="08d43-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="08d43-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="08d43-105">Prerequisites</span></span>

-   <span data-ttu-id="08d43-106">Anda mempunyai [Akaun SendGrid](https://sendgrid.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="08d43-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="08d43-107">Terdapat senarai kenalan sedia ada dalam SendGrid dan ID yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="08d43-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="08d43-108">Untuk mendapatkan maklumat lanjut, lihat [SendGrid - Urus kenalan](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="08d43-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="08d43-109">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="08d43-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="08d43-110">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="08d43-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="08d43-111">Sambung kepada SendGrid</span><span class="sxs-lookup"><span data-stu-id="08d43-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="08d43-112">Pergi ke **Pentadbir** > **Destinasi Eksport**.</span><span class="sxs-lookup"><span data-stu-id="08d43-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="08d43-113">Di bawah **SendGrid**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="08d43-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="08d43-114">Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="08d43-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Anak tetingkap konfigurasi eksport SendGrid.":::

1. <span data-ttu-id="08d43-116">Masukkan **Kekunci API SendGrid** [Kekunci API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="08d43-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="08d43-117">Masukkan **[ID senarai SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** anda.</span><span class="sxs-lookup"><span data-stu-id="08d43-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="08d43-118">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="08d43-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="08d43-119">Pilih **Sambung** untuk memulakan sambungan ke SendGrid.</span><span class="sxs-lookup"><span data-stu-id="08d43-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="08d43-120">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="08d43-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="08d43-121">Pilih **Seterusnya** untuk konfigurasi eksport.</span><span class="sxs-lookup"><span data-stu-id="08d43-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="08d43-122">Konfigurasi penyambung</span><span class="sxs-lookup"><span data-stu-id="08d43-122">Configure the connector</span></span>

1. <span data-ttu-id="08d43-123">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="08d43-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="08d43-124">Ulangi langkah yang sama untuk medan pilihan lain seperti **Nama pertama**, **Nama akhir**, **Negara/Rantau**, **Negeri**. **Bandar** dan **Poskod**.</span><span class="sxs-lookup"><span data-stu-id="08d43-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="08d43-125">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="08d43-125">Select the segments you want to export.</span></span> <span data-ttu-id="08d43-126">Kami amat **mengesyorkan untuk tidak mengeksport lebih daripada 100'000 profil pelanggan dalam jumlah** ke SendGrid.</span><span class="sxs-lookup"><span data-stu-id="08d43-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="08d43-127">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="08d43-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="08d43-128">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="08d43-128">Export the data</span></span>

<span data-ttu-id="08d43-129">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="08d43-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="08d43-130">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="08d43-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="08d43-131">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="08d43-131">Known limitations</span></span>

- <span data-ttu-id="08d43-132">Sehingga 100'000 profil dalam jumlah keseluruhan ke SendGrid.</span><span class="sxs-lookup"><span data-stu-id="08d43-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="08d43-133">Mengeksport ke SendGrid adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="08d43-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="08d43-134">Mengeksport sehingga 100'000 profil ke SendGrid boleh mengambil masa hingga beberapa jam untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="08d43-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="08d43-135">Bilangan profil yang boleh anda eksport ke SendGrid bergantung dan terhad pada kontrak anda dengan SendGrid.</span><span class="sxs-lookup"><span data-stu-id="08d43-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="08d43-136">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="08d43-136">Data privacy and compliance</span></span>

<span data-ttu-id="08d43-137">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke SendGrid, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="08d43-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="08d43-138">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa SendGrid memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki.</span><span class="sxs-lookup"><span data-stu-id="08d43-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="08d43-139">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="08d43-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="08d43-140">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="08d43-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]