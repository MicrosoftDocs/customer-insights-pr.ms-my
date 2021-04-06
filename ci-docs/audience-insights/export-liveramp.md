---
title: LiveRamp penyambung
description: Ketahui cara untuk mengeksport data ke LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597568"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="09cf8-103">Penyambung LiveRamp&reg; (pratonton)</span><span class="sxs-lookup"><span data-stu-id="09cf8-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="09cf8-104">Aktifkan data anda dalam LiveRamp untuk menyambung dengan 500 platform merentasi ekosistem digital, sosial, dan TV.</span><span class="sxs-lookup"><span data-stu-id="09cf8-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="09cf8-105">Bekerja dengan data anda dalam LiveRamp untuk mensasar, menahan, dan memperibadikan kempen iklan.</span><span class="sxs-lookup"><span data-stu-id="09cf8-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="09cf8-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="09cf8-106">Prerequisites</span></span>

- <span data-ttu-id="09cf8-107">Anda memerlukan langganan LiveRamp untuk menggunakan penyambung ini.</span><span class="sxs-lookup"><span data-stu-id="09cf8-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="09cf8-108">Untuk mendapatkan langganan, [hubungi LiveRamp](https://liveramp.com/contact/) secara terus.</span><span class="sxs-lookup"><span data-stu-id="09cf8-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="09cf8-109">[Ketahui lanjut tentang Penyertaan LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="09cf8-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="09cf8-110">Sambung ke LiveRamp</span><span class="sxs-lookup"><span data-stu-id="09cf8-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="09cf8-111">Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.</span><span class="sxs-lookup"><span data-stu-id="09cf8-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="09cf8-112">Dalam jubin **LiveRamp**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="09cf8-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="09cf8-113">Berikan destinasi anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="09cf8-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="09cf8-114">Sediakan **Nama Pengguna** dan **Kata Laluan** untuk akaun LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="09cf8-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="09cf8-115">Kelayakan ini berkemungkinan berbeza daripada kelayakan Penyertaan LiveRamp anda.</span><span class="sxs-lookup"><span data-stu-id="09cf8-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="09cf8-116">Pilih **Sahkan** untuk menguji sambungan ke LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="09cf8-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="09cf8-117">Selepas pengesahan berjaya, sediakan keizinan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="09cf8-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="09cf8-118">Pilih **Seterusnya** untuk menyediakan penyambung LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="09cf8-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="09cf8-119">Konfigurasi penyambung</span><span class="sxs-lookup"><span data-stu-id="09cf8-119">Configure the connector</span></span>

1. <span data-ttu-id="09cf8-120">Dalam medan **Pilih pengecam kunci anda**, pilih **E-mel**,  **Nama dan alamat**, atau **Telefon** untuk menghantar ke LiveRamp untuk penyelesaian identiti.</span><span class="sxs-lookup"><span data-stu-id="09cf8-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="09cf8-121">Petakan atribut yang sepadan daripada entiti pelanggan disatukan anda untuk pengecam kunci yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="09cf8-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="09cf8-122">Pilih **Tambah atribut** untuk memetakan atribut tambahan untuk dihantar ke LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="09cf8-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="09cf8-123">Menghantar lebih banyak atribut pengecam kunci ke LiveRamp mempunyai kemungkinan besar untuk anda mendapatkan kadar pemadanan yang tinggi.</span><span class="sxs-lookup"><span data-stu-id="09cf8-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="09cf8-124">Pilih segmen yang anda mahu eksport ke LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="09cf8-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="09cf8-125">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="09cf8-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="09cf8-126">![Penyambung LiveRamp dengan atribut pemetaan](media/export-liveramp-segments.png "Penyambung LiveRamp dengan atribut pemetaan")</span><span class="sxs-lookup"><span data-stu-id="09cf8-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="09cf8-127">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="09cf8-127">Export the data</span></span>

<span data-ttu-id="09cf8-128">Eksport akan bermula sebentar lagi jika kesemua prasyarat untuk mengeksport telah lengkap.</span><span class="sxs-lookup"><span data-stu-id="09cf8-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="09cf8-129">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="09cf8-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="09cf8-130">Sebaik sahaja eksport berjaya diselesaikan, anda boleh mendaftar masuk ke Penyertaan LiveRamp untuk mengaktifkan dan mengedarkan data anda.</span><span class="sxs-lookup"><span data-stu-id="09cf8-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="09cf8-131">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="09cf8-131">Data privacy and compliance</span></span>

<span data-ttu-id="09cf8-132">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke LiveRamp, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="09cf8-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="09cf8-133">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa LiveRamp memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="09cf8-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="09cf8-134">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="09cf8-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="09cf8-135">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="09cf8-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]