---
title: Pengayaan dengan pengayaan pihak ketiga Experian
description: Maklumat umum tentang pengayaan pihak ketiga Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309831"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="853a6-103">Memperkaya profil pelanggan dengan demografi daripada Experian (pratonton)</span><span class="sxs-lookup"><span data-stu-id="853a6-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="853a6-104">Experian ialah peneraju global dalam pelaporan kredit pengguna dan perniagaan serta perkhidmatan pemasaran.</span><span class="sxs-lookup"><span data-stu-id="853a6-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="853a6-105">Dengan perkhidmatan pengayaan data Experian, anda boleh membina pemahaman yang lebih mendalam tentang pelanggan anda dengan memperkaya profil pelanggan anda menggunakan data demografi seperti saiz isi rumah, pendapatan dan banyak lagi.</span><span class="sxs-lookup"><span data-stu-id="853a6-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="853a6-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="853a6-106">Prerequisites</span></span>

<span data-ttu-id="853a6-107">Untuk mengkonfigurasikan Experian, prasyarat berikut mesti dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="853a6-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="853a6-108">Anda mesti mempunyai langganan Experian yang aktif.</span><span class="sxs-lookup"><span data-stu-id="853a6-108">You have an active Experian subscription.</span></span> <span data-ttu-id="853a6-109">Untuk mendapatkan langganan, [hubungi Experian](https://www.experian.com/marketing-services/contact) secara terus.</span><span class="sxs-lookup"><span data-stu-id="853a6-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="853a6-110">[Ketahui lebih lanjut tentang Pengayaan Data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="853a6-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="853a6-111">Sambungan Experian telah dikonfigurasikan oleh pentadbir *atau* anda mempunyai keizinan [pentadbir](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="853a6-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="853a6-112">Anda juga memerlukan ID Pengguna, ID Pihak dan Nombor Model untuk akaun Pengangkutan Selamat (ST) didayakan SSH anda yang Experian cipta untuk anda.</span><span class="sxs-lookup"><span data-stu-id="853a6-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="853a6-113">Negara/rantau yang disokong</span><span class="sxs-lookup"><span data-stu-id="853a6-113">Supported countries/regions</span></span>

<span data-ttu-id="853a6-114">Pada masa ini, kami menyokong pengayaan profil pelanggan di Amerika Syarikat sahaja.</span><span class="sxs-lookup"><span data-stu-id="853a6-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="853a6-115">Konfigurasikan pengayaan</span><span class="sxs-lookup"><span data-stu-id="853a6-115">Configure the enrichment</span></span>

1. <span data-ttu-id="853a6-116">Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.</span><span class="sxs-lookup"><span data-stu-id="853a6-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="853a6-117">Pilih **Perkayakan data saya** pada jubin Experian.</span><span class="sxs-lookup"><span data-stu-id="853a6-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="853a6-118">![Experian Jubin](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="853a6-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="853a6-119">Pilih [sambungan](connections.md) daripada senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="853a6-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="853a6-120">Hubungi pentadbir jika tiada sambungan tersedia.</span><span class="sxs-lookup"><span data-stu-id="853a6-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="853a6-121">Jika anda seorang pentadbir, anda boleh mencipta sambungan dengan memilih **Tambah sambungan** dan memilih Experian daripada senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="853a6-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="853a6-122">Pilih **Sambung kepada Experian** untuk mengesahkan pilihan sambungan.</span><span class="sxs-lookup"><span data-stu-id="853a6-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="853a6-123">Pilih **Seterusnya** dan pilih **Set data pelanggan** yang anda mahu perkayakan dengan data demografi daripada Experian.</span><span class="sxs-lookup"><span data-stu-id="853a6-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="853a6-124">Anda boleh memilih entiti **Pelanggan** untuk memperkayakan semua profil pelanggan anda atau pilih entiti segmen untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="853a6-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Tangkapan skrin apabila memilih set data pelanggan.":::

1. <span data-ttu-id="853a6-126">Pilih **Seterusnya** dan tentukan jenis medan daripada profil anda yang disatukan harus digunakan untuk mencari data demografi yang sepadan daripada Experian.</span><span class="sxs-lookup"><span data-stu-id="853a6-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="853a6-127">Sekurang-kurangnya salah satu medan **Nama dan alamat**, **Telefon** atau **E-mel** diperlukan.</span><span class="sxs-lookup"><span data-stu-id="853a6-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="853a6-128">Untuk mendapatkan ketepatan padanan yang lebih tinggi, maksimum dua medan lain boleh ditambah.</span><span class="sxs-lookup"><span data-stu-id="853a6-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="853a6-129">Pemilihan ini akan mempengaruhi medan pemetaan yang anda boleh akses dalam langkah seterusnya.</span><span class="sxs-lookup"><span data-stu-id="853a6-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="853a6-130">Lebih banyak atribut pengecam utama dihantar kepada Experian mungkin menghasilkan kadar padanan yang lebih tinggi.</span><span class="sxs-lookup"><span data-stu-id="853a6-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="853a6-131">Pilih **Seterusnya** untuk memulakan pemetaan medan.</span><span class="sxs-lookup"><span data-stu-id="853a6-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="853a6-132">Tentukan jenis medan daripada profil anda yang disatukan yang harus digunakan untuk mencari data demografi yang sepadan daripada Experian.</span><span class="sxs-lookup"><span data-stu-id="853a6-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="853a6-133">Medan yang diperlukan ditandakan.</span><span class="sxs-lookup"><span data-stu-id="853a6-133">Required fields are marked.</span></span>

1. <span data-ttu-id="853a6-134">Berikan nama untuk pengayaan dan nama untuk entiti output.</span><span class="sxs-lookup"><span data-stu-id="853a6-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="853a6-135">Pilih **Simpan pengayaan** selepas menyemak pilihan anda.</span><span class="sxs-lookup"><span data-stu-id="853a6-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="853a6-136">Konfigurasikan sambungan untuk Experian</span><span class="sxs-lookup"><span data-stu-id="853a6-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="853a6-137">Anda perlu menjadi pentadbir untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="853a6-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="853a6-138">Pilih **Tambah sambungan** apabila mengkonfigurasikan pengayaan *atau* pergi ke **Pentadbir** > **Sambungan** dan pilih **Sediakan** pada jubin Experian.</span><span class="sxs-lookup"><span data-stu-id="853a6-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="853a6-139">Pilih **Mulakan**.</span><span class="sxs-lookup"><span data-stu-id="853a6-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="853a6-140">Masukkan nama untuk sambungan dalam kotak **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="853a6-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="853a6-141">Masukkan ID Pengguna, ID Pihak, dan Nombor Model yang sah untuk akaun Pengangkutan Selamat Experian anda.</span><span class="sxs-lookup"><span data-stu-id="853a6-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="853a6-142">Semak dan berikan persetujuan anda untuk **privasi dan pematuhan Data** dengan memilih **Saya bersetuju**.</span><span class="sxs-lookup"><span data-stu-id="853a6-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="853a6-143">Pilih **Sahkan** untuk mengesahkan konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="853a6-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="853a6-144">Selepas melengkapkan pengesahan, pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="853a6-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Anak tetingkap konfigurasi sambungan Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="853a6-146">Keputusan pengayaan</span><span class="sxs-lookup"><span data-stu-id="853a6-146">Enrichment results</span></span>

<span data-ttu-id="853a6-147">Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah.</span><span class="sxs-lookup"><span data-stu-id="853a6-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="853a6-148">Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="853a6-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="853a6-149">Masa pemprosesan akan bergantung pada saiz data pelanggan anda dan proses pengayaan yang disediakan untuk akaun anda oleh Experian.</span><span class="sxs-lookup"><span data-stu-id="853a6-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="853a6-150">Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="853a6-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="853a6-151">Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="853a6-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="853a6-152">Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.</span><span class="sxs-lookup"><span data-stu-id="853a6-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="853a6-153">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="853a6-153">Next steps</span></span>

<span data-ttu-id="853a6-154">Bina di atas data pelanggan anda yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="853a6-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="853a6-155">Cipta [segmen](segments.md) dan [langkah](measures.md) dan juga [eksport data](export-destinations.md) untuk menyampaikan pengalaman yang diperibadikan kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="853a6-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="853a6-156">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="853a6-156">Data privacy and compliance</span></span>

<span data-ttu-id="853a6-157">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data kepada Experian, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data sensitif yang berpotensi seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="853a6-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="853a6-158">Microsoft akan memindahkan data tersebut atas arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa Experian memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki.</span><span class="sxs-lookup"><span data-stu-id="853a6-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="853a6-159">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="853a6-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="853a6-160">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="853a6-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
