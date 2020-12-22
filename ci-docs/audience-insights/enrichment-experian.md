---
title: Pengayaan dengan Experian pengayaan pihak ketiga
description: Maklumat umum tentang pengayaan pihak ketiga Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668823"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="a55aa-103">Perkayakan profil pelanggan dengan demografik daripada Experian (pratonton)</span><span class="sxs-lookup"><span data-stu-id="a55aa-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="a55aa-104">Experian adalah peneraju global dalam pelaporan kredit pengguna dan perniagaan serta perkhidmatan pemasaran.</span><span class="sxs-lookup"><span data-stu-id="a55aa-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="a55aa-105">Dengan perkhidmatan pengayaan data Experian, anda boleh membina pemahaman lebih mendalam mengenai pelanggan anda dengan memperkayakan profil pelanggan anda dengan data demografi seperti saiz isi rumah, pendapatan dan banyak lagi.</span><span class="sxs-lookup"><span data-stu-id="a55aa-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a55aa-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="a55aa-106">Prerequisites</span></span>

<span data-ttu-id="a55aa-107">Untuk mengkonfigurasikan Experian, prasyarat berikut mesti dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="a55aa-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a55aa-108">Anda mempunyai langganan Experian yang aktif.</span><span class="sxs-lookup"><span data-stu-id="a55aa-108">You have an active Experian subscription.</span></span> <span data-ttu-id="a55aa-109">Untuk mendapatkan langganan, [hubungi Experian](https://www.experian.com/marketing-services/contact) secara terus.</span><span class="sxs-lookup"><span data-stu-id="a55aa-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="a55aa-110">[Ketahui lanjut tentang Pengayaan Data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="a55aa-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="a55aa-111">Anda mempunyai ID pengguna, ID Pihak dan Nombor Model untuk akaun Pengangkutan Selamat (ST) didayakan SSH yang telah dicipta oleh Experian untuk anda.</span><span class="sxs-lookup"><span data-stu-id="a55aa-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="a55aa-112">Anda mempunyai keizinan [Pentadbir](permissions.md#administrator) dalam wawasan khalayak.</span><span class="sxs-lookup"><span data-stu-id="a55aa-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="a55aa-113">Konfigurasi</span><span class="sxs-lookup"><span data-stu-id="a55aa-113">Configuration</span></span>

1. <span data-ttu-id="a55aa-114">Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.</span><span class="sxs-lookup"><span data-stu-id="a55aa-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="a55aa-115">Pilih **Perkayakan data saya** pada jubin Experian.</span><span class="sxs-lookup"><span data-stu-id="a55aa-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a55aa-116">![Jubin Experian](media/experian-tile.png "Jubin Experian")</span><span class="sxs-lookup"><span data-stu-id="a55aa-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="a55aa-117">Pilih **Mari bermula** dan masukkan ID Pengguna, ID Pihak dan Nombor Model untuk akaun Pengangkutan Selamat Experian anda.</span><span class="sxs-lookup"><span data-stu-id="a55aa-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="a55aa-118">Semak semula dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="a55aa-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="a55aa-119">Sahkan semua input dengan memilih **Gunakan**.</span><span class="sxs-lookup"><span data-stu-id="a55aa-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="a55aa-120">Petakan medan anda</span><span class="sxs-lookup"><span data-stu-id="a55aa-120">Map your fields</span></span>

1. <span data-ttu-id="a55aa-121">Pilih **Tambah data** dan pilih pengecam kunci anda daripada **Nama dan Alamat**, **E-mel** atau **Telefon** untuk menghantar ke Experian bagi penyelesaian identiti.</span><span class="sxs-lookup"><span data-stu-id="a55aa-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="a55aa-122">Lebih atribut pengecam kunci yang dihantar kepada Experian mungkin akan menghasilkan kadar padanan yang lebih tinggi.</span><span class="sxs-lookup"><span data-stu-id="a55aa-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="a55aa-123">Pilih **Seterusnya** dan petakan atribut yang sepadan daripada entiti pelanggan disatukan anda untuk medan pengecam kunci yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="a55aa-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="a55aa-124">Pilih **Tambah atribut** untuk memetakan sebarang atribut tambahan yang anda mahu hantar ke Experian.</span><span class="sxs-lookup"><span data-stu-id="a55aa-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="a55aa-125">Pilih **Simpan** untuk melengkapkan pemetaan medan.</span><span class="sxs-lookup"><span data-stu-id="a55aa-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a55aa-126">![Memetakan medan Experian](media/experian-field-mapping.png "Memetakan medan Experian")</span><span class="sxs-lookup"><span data-stu-id="a55aa-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a55aa-127">Keputusan pengayaan</span><span class="sxs-lookup"><span data-stu-id="a55aa-127">Enrichment results</span></span>

<span data-ttu-id="a55aa-128">Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah.</span><span class="sxs-lookup"><span data-stu-id="a55aa-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a55aa-129">Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a55aa-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a55aa-130">Masa pemprosesan akan bergantung pada saiz data pelanggan anda dan proses pengayaan yang ditetapkan untuk akaun anda oleh Experian.</span><span class="sxs-lookup"><span data-stu-id="a55aa-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="a55aa-131">Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="a55aa-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="a55aa-132">Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="a55aa-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a55aa-133">Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.</span><span class="sxs-lookup"><span data-stu-id="a55aa-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a55aa-134">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="a55aa-134">Next steps</span></span>

<span data-ttu-id="a55aa-135">Bina di atas data pelanggan anda yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="a55aa-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a55aa-136">Cipta [segmen](segments.md), [ukur](measures.md) dan juga [eksport data](export-destinations.md) untuk menghantar pengalaman diperibadikan kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="a55aa-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a55aa-137">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="a55aa-137">Data privacy and compliance</span></span>

<span data-ttu-id="a55aa-138">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Experian, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="a55aa-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a55aa-139">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Experian memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="a55aa-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a55aa-140">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a55aa-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a55aa-141">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="a55aa-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
