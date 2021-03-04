---
title: Eksport data Customer Insights ke Marketo
description: Ketahui cara mengkonfigurasi sambungan ke Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267092"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="edcb0-103">Penyambung untuk Marketo (pratonton)</span><span class="sxs-lookup"><span data-stu-id="edcb0-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="edcb0-104">Eksport segmen profil pelanggan disatukan untuk menjana kempen, menyediakan pemasaran e-mel dan gunakan kumpulan pelanggan tertentu dengan Marketo.</span><span class="sxs-lookup"><span data-stu-id="edcb0-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="edcb0-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="edcb0-105">Prerequisites</span></span>

-   <span data-ttu-id="edcb0-106">Anda mempunyai [Akaun Marketo](https://login.marketo.com/) dan kelayakan pentadbir yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="edcb0-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="edcb0-107">Terdapat senarai sedia ada dalam Marketo dan ID yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="edcb0-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="edcb0-108">Untuk maklumat lanjut, lihat [Senarai Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="edcb0-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="edcb0-109">Anda telah [mengkonfigurasi segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="edcb0-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="edcb0-110">Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.</span><span class="sxs-lookup"><span data-stu-id="edcb0-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="edcb0-111">Sambung ke Marketo</span><span class="sxs-lookup"><span data-stu-id="edcb0-111">Connect to Marketo</span></span>

1. <span data-ttu-id="edcb0-112">Pergi ke **Pentadbir** > **Destinasi Eksport**.</span><span class="sxs-lookup"><span data-stu-id="edcb0-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="edcb0-113">Di bawah **Marketo**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="edcb0-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="edcb0-114">Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="edcb0-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="edcb0-115">Masukkan **[ID klien Marketo, Rahsia pelanggan dan Nama hos Titik tamat REST](https://developers.marketo.com/rest-api/authentication/)** anda.</span><span class="sxs-lookup"><span data-stu-id="edcb0-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="edcb0-116">Masukkan **[ID senarai Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** anda</span><span class="sxs-lookup"><span data-stu-id="edcb0-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="edcb0-117">Pilih **Saya setuju** untuk mengesahkan **Privasi data dan pematuhan** dan pilih **Sambung** untuk memulakan sambungan ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="edcb0-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="edcb0-118">Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="edcb0-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Eksport tangkap skrin untuk sambungan Marketo":::

1. <span data-ttu-id="edcb0-120">Pilih **Seterusnya** untuk konfigurasi eksport.</span><span class="sxs-lookup"><span data-stu-id="edcb0-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="edcb0-121">Konfigurasi penyambung</span><span class="sxs-lookup"><span data-stu-id="edcb0-121">Configure the connector</span></span>

1. <span data-ttu-id="edcb0-122">Dalam bahagian **Pemadanan data**, dalam medan **E-mel**, pilih medan dalam profil pelanggan disatukan anda yang mewakili alamat e-mel pelanggan.</span><span class="sxs-lookup"><span data-stu-id="edcb0-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="edcb0-123">Secara alternatif, anda boleh mengeksport **Nama pertama**, **Nama akhir**, **Bandar**, **Negeri**, dan **Negara/Rantau** sebagai medan tambahan untuk mencipta lebih banyak e-mel peribadi.</span><span class="sxs-lookup"><span data-stu-id="edcb0-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="edcb0-124">Pilih **Tambah atribut** untuk memetakan medan ini.</span><span class="sxs-lookup"><span data-stu-id="edcb0-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="edcb0-125">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="edcb0-125">Select the segments you want to export.</span></span> <span data-ttu-id="edcb0-126">Anda boleh mengeksport hingga 1 juta jumlah profil pelanggan ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="edcb0-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Pilih medan dan segmen untuk eksport ke Marketo":::

1. <span data-ttu-id="edcb0-128">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="edcb0-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="edcb0-129">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="edcb0-129">Export the data</span></span>

<span data-ttu-id="edcb0-130">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="edcb0-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="edcb0-131">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="edcb0-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="edcb0-132">Dalam Marketo, anda kini boleh mencari segmen anda di bawah [Senarai Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="edcb0-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="edcb0-133">Had diketahui</span><span class="sxs-lookup"><span data-stu-id="edcb0-133">Known limitations</span></span>

- <span data-ttu-id="edcb0-134">Hingga 1 juta profil bagi setiap eksport ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="edcb0-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="edcb0-135">Mengeksport ke Marketo adalah terhad kepada segmen.</span><span class="sxs-lookup"><span data-stu-id="edcb0-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="edcb0-136">Mengeksport segmen dengan sejumlah 1 juta profil boleh mengambil masa sehingga 3 jam.</span><span class="sxs-lookup"><span data-stu-id="edcb0-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="edcb0-137">Bilangan profil yang boleh anda eksport ke Marketo bergantung dan terhad pada kontrak anda dengan Marketo.</span><span class="sxs-lookup"><span data-stu-id="edcb0-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="edcb0-138">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="edcb0-138">Data privacy and compliance</span></span>

<span data-ttu-id="edcb0-139">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Marketo, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="edcb0-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="edcb0-140">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Marketo memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="edcb0-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="edcb0-141">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="edcb0-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="edcb0-142">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="edcb0-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]