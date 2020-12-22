---
title: Eksport data Customer Insights ke DotDigital
description: Ketahui cara mengkonfigurasi sambungan ke DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644459"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="9e42b-103">Penyambung untuk DotDigital (pratonton)</span><span class="sxs-lookup"><span data-stu-id="9e42b-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="9e42b-104">Eksport segmen profil pelanggan disatukan ke buku alamat DotDigital dan gunakannya untuk kempen, pemasaran e-mel dan untuk membina segmen pelanggan dengan DotDigital.</span><span class="sxs-lookup"><span data-stu-id="9e42b-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="9e42b-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="9e42b-105">Prerequisites</span></span>

-   <span data-ttu-id="9e42b-106">Anda mempunyai [Akaun DotDigital](https://dotdigital.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="9e42b-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9e42b-107">Terdapat buku alamat sedia ada dalam DotDigital dan ID yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="9e42b-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="9e42b-108">ID boleh ditemui dalam URL apabila anda memilih dan membuka buku alamat.</span><span class="sxs-lookup"><span data-stu-id="9e42b-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="9e42b-109">Untuk maklumat lanjut, lihat [Buku alamat DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="9e42b-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="9e42b-110">Anda mempunyai [segmen yang dikonfigurasi](segments.md) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="9e42b-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="9e42b-111">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="9e42b-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="9e42b-112">Sambung ke DotDigital</span><span class="sxs-lookup"><span data-stu-id="9e42b-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="9e42b-113">Pergi ke **Pentadbir** > **Destinasi Eksport**.</span><span class="sxs-lookup"><span data-stu-id="9e42b-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9e42b-114">Di bawah **DotDigital**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="9e42b-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="9e42b-115">Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="9e42b-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Anak tetingkap konfigurasi untuk eksport DotDigital.":::

1. <span data-ttu-id="9e42b-117">Masukkan **Nama pengguna dan kata laluan DotDigital** anda.</span><span class="sxs-lookup"><span data-stu-id="9e42b-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="9e42b-118">Masukkan **[ID buku alamat DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** anda.</span><span class="sxs-lookup"><span data-stu-id="9e42b-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="9e42b-119">Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.</span><span class="sxs-lookup"><span data-stu-id="9e42b-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9e42b-120">Pilih **Sambung** untuk memulakan sambungan ke DotDigital.</span><span class="sxs-lookup"><span data-stu-id="9e42b-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="9e42b-121">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="9e42b-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9e42b-122">Pilih **Seterusnya** untuk konfigurasi eksport.</span><span class="sxs-lookup"><span data-stu-id="9e42b-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="9e42b-123">Konfigurasi penyambung</span><span class="sxs-lookup"><span data-stu-id="9e42b-123">Configure the connector</span></span>

1. <span data-ttu-id="9e42b-124">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="9e42b-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="9e42b-125">Ulangi langkah yang sama untuk medan pilihan lain seperti **Nama pertama**, **Nama akhir**, **Nama penuh**, **Jantina** dan **Poskod**.</span><span class="sxs-lookup"><span data-stu-id="9e42b-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="9e42b-126">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="9e42b-126">Select the segments you want to export.</span></span> <span data-ttu-id="9e42b-127">Anda boleh mengeksport hingga 1 juta profil pelanggan dalam jumlah keseluruhan DotDigital.</span><span class="sxs-lookup"><span data-stu-id="9e42b-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="9e42b-128">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="9e42b-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9e42b-129">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="9e42b-129">Export the data</span></span>

<span data-ttu-id="9e42b-130">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9e42b-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9e42b-131">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9e42b-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9e42b-132">Dalam DotDigital, anda kini boleh mencari segmen anda dalam [Buku alamat DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="9e42b-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9e42b-133">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="9e42b-133">Known limitations</span></span>

- <span data-ttu-id="9e42b-134">Hingga 1 juta profil bagi setiap eksport ke DotDigital.</span><span class="sxs-lookup"><span data-stu-id="9e42b-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="9e42b-135">Mengeksport ke DotDigital adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="9e42b-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="9e42b-136">Mengeksport segmen dengan jumlah 1 juta profil boleh mengambil masa hingga 3 jam kerana had pada bahagian pembekal.</span><span class="sxs-lookup"><span data-stu-id="9e42b-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="9e42b-137">Bilangan profil yang boleh anda eksport ke DotDigital bergantung dan terhad pada kontrak anda dengan DotDigital.</span><span class="sxs-lookup"><span data-stu-id="9e42b-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9e42b-138">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="9e42b-138">Data privacy and compliance</span></span>

<span data-ttu-id="9e42b-139">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke DotDigital, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="9e42b-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9e42b-140">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa DotDigital memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki.</span><span class="sxs-lookup"><span data-stu-id="9e42b-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="9e42b-141">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9e42b-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9e42b-142">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="9e42b-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
