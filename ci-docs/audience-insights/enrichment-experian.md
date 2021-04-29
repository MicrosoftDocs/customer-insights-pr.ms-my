---
title: Pengayaan dengan Experian pengayaan pihak ketiga
description: Maklumat umum tentang pengayaan pihak ketiga Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896384"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="aa46e-103">Perkayakan profil pelanggan dengan demografik daripada Experian (pratonton)</span><span class="sxs-lookup"><span data-stu-id="aa46e-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="aa46e-104">Experian adalah peneraju global dalam pelaporan kredit pengguna dan perniagaan serta perkhidmatan pemasaran.</span><span class="sxs-lookup"><span data-stu-id="aa46e-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="aa46e-105">Dengan perkhidmatan pengayaan data Experian, anda boleh membina pemahaman lebih mendalam mengenai pelanggan anda dengan memperkayakan profil pelanggan anda dengan data demografi seperti saiz isi rumah, pendapatan dan banyak lagi.</span><span class="sxs-lookup"><span data-stu-id="aa46e-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aa46e-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="aa46e-106">Prerequisites</span></span>

<span data-ttu-id="aa46e-107">Untuk mengkonfigurasikan Experian, prasyarat berikut mesti dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="aa46e-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="aa46e-108">Anda mempunyai langganan Experian yang aktif.</span><span class="sxs-lookup"><span data-stu-id="aa46e-108">You have an active Experian subscription.</span></span> <span data-ttu-id="aa46e-109">Untuk mendapatkan langganan, [hubungi Experian](https://www.experian.com/marketing-services/contact) secara terus.</span><span class="sxs-lookup"><span data-stu-id="aa46e-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="aa46e-110">[Ketahui lanjut tentang Pengayaan Data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="aa46e-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="aa46e-111">Sambungan Experian telah dikonfigurasikan oleh pentadbir *atau* anda mempunyai keizinan [pentadbir](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="aa46e-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="aa46e-112">Anda juga memerlukan ID pengguna, ID Parti dan Nombor Model untuk akaun Pengangkutan Selamat (ST) yang Didayakan oleh SSH yang dicipta oleh Experian untuk anda.</span><span class="sxs-lookup"><span data-stu-id="aa46e-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="aa46e-113">Konfigurasikan pengayaan</span><span class="sxs-lookup"><span data-stu-id="aa46e-113">Configure the enrichment</span></span>

1. <span data-ttu-id="aa46e-114">Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.</span><span class="sxs-lookup"><span data-stu-id="aa46e-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="aa46e-115">Pilih **Perkayakan data saya** pada jubin Experian.</span><span class="sxs-lookup"><span data-stu-id="aa46e-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aa46e-116">![Jubin Experian](media/experian-tile.png "Jubin Experian")</span><span class="sxs-lookup"><span data-stu-id="aa46e-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="aa46e-117">Pilih [sambungan](connections.md) daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="aa46e-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="aa46e-118">Hubungi pentadbir jika tiada sambungan tersedia.</span><span class="sxs-lookup"><span data-stu-id="aa46e-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="aa46e-119">Jika anda seorang pentadbir, anda boleh mencipta sambungan dengan memilih **Tambah sambungan** dan memilih Experian daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="aa46e-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="aa46e-120">Pilih **Sambung ke Experian** untuk mengesahkan pilihan penyambungan.</span><span class="sxs-lookup"><span data-stu-id="aa46e-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="aa46e-121">Pilih **Seterusnya** dan pilih **Set data pelanggan** yang anda mahu perkayakan dengan data demografi daripada Experian.</span><span class="sxs-lookup"><span data-stu-id="aa46e-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="aa46e-122">Anda boleh memilih entiti **Pelanggan** untuk memperkayakan semua profil pelanggan anda atau pilih entiti segmen untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="aa46e-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Tangkapan skrin apabila memilih set data pelanggan.":::

1. <span data-ttu-id="aa46e-124">Pilih **Seterusnya** dan tentukan jenis medan daripada profil anda yang disatukan yang perlu digunakan untuk mencari data demografi yang sepadan daripada Experian.</span><span class="sxs-lookup"><span data-stu-id="aa46e-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="aa46e-125">Sekurang-kurangnya salah satu medan **Nama dan alamat**, **Telefon** atau **E-mel** diperlukan.</span><span class="sxs-lookup"><span data-stu-id="aa46e-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="aa46e-126">Untuk mendapatkan ketepatan padanan yang lebih tinggi, maksimum dua medan lain boleh ditambah.</span><span class="sxs-lookup"><span data-stu-id="aa46e-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="aa46e-127">Pemilihan ini akan mempengaruhi medan pemetaan yang anda boleh akses dalam langkah seterusnya.</span><span class="sxs-lookup"><span data-stu-id="aa46e-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="aa46e-128">Lebih atribut pengecam kunci yang dihantar kepada Experian mungkin akan menghasilkan kadar padanan yang lebih tinggi.</span><span class="sxs-lookup"><span data-stu-id="aa46e-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="aa46e-129">Pilih **Seterusnya** untuk memulakan pemetaan medan.</span><span class="sxs-lookup"><span data-stu-id="aa46e-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="aa46e-130">Tentukan jenis medan daripada profil anda yang disatukan yang perlu digunakan untuk mencari data demografi yang sepadan daripada Experian.</span><span class="sxs-lookup"><span data-stu-id="aa46e-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="aa46e-131">Medan yang diperlukan ditandakan.</span><span class="sxs-lookup"><span data-stu-id="aa46e-131">Required fields are marked.</span></span>

1. <span data-ttu-id="aa46e-132">Berikan nama untuk pengayaan dan nama untuk entiti output.</span><span class="sxs-lookup"><span data-stu-id="aa46e-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="aa46e-133">Pilih **Simpan pengayaan** selepas menyemak pilihan anda.</span><span class="sxs-lookup"><span data-stu-id="aa46e-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="aa46e-134">Konfigurasikan sambungan untuk Experian</span><span class="sxs-lookup"><span data-stu-id="aa46e-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="aa46e-135">Anda perlu menjadi pentadbir untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="aa46e-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="aa46e-136">Pilih **Tambah sambungan** apabila mengkonfigurasikan pengayaan *atau* pergi ke **Pentadbir** > **Sambungan** dan pilih **Sediakan** pada jubin Experian.</span><span class="sxs-lookup"><span data-stu-id="aa46e-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="aa46e-137">Pilih **Mulakan**.</span><span class="sxs-lookup"><span data-stu-id="aa46e-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="aa46e-138">Masukkan nama untuk sambungan dalam kotak **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="aa46e-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="aa46e-139">Masukkan ID Pengguna, ID Parti dan Nombor Model yang sah untuk akaun Pengangkutan Selamat Experian anda.</span><span class="sxs-lookup"><span data-stu-id="aa46e-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="aa46e-140">Semak dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="aa46e-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="aa46e-141">Pilih **Sahkan** untuk mengesahkan konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="aa46e-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="aa46e-142">Selepas melengkapkan pengesahan, pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="aa46e-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Anak tetingkap konfigurasi sambungan Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="aa46e-144">Keputusan pengayaan</span><span class="sxs-lookup"><span data-stu-id="aa46e-144">Enrichment results</span></span>

<span data-ttu-id="aa46e-145">Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah.</span><span class="sxs-lookup"><span data-stu-id="aa46e-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="aa46e-146">Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="aa46e-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="aa46e-147">Masa pemprosesan akan bergantung pada saiz data pelanggan anda dan proses pengayaan yang ditetapkan untuk akaun anda oleh Experian.</span><span class="sxs-lookup"><span data-stu-id="aa46e-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="aa46e-148">Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="aa46e-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="aa46e-149">Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="aa46e-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="aa46e-150">Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.</span><span class="sxs-lookup"><span data-stu-id="aa46e-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aa46e-151">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="aa46e-151">Next steps</span></span>

<span data-ttu-id="aa46e-152">Bina di atas data pelanggan anda yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="aa46e-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="aa46e-153">Cipta [segmen](segments.md), [ukur](measures.md) dan juga [eksport data](export-destinations.md) untuk menghantar pengalaman diperibadikan kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="aa46e-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="aa46e-154">Privasi data dan pematuhan</span><span class="sxs-lookup"><span data-stu-id="aa46e-154">Data privacy and compliance</span></span>

<span data-ttu-id="aa46e-155">Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Experian, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi.</span><span class="sxs-lookup"><span data-stu-id="aa46e-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="aa46e-156">Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Experian memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki.</span><span class="sxs-lookup"><span data-stu-id="aa46e-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="aa46e-157">Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="aa46e-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="aa46e-158">Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.</span><span class="sxs-lookup"><span data-stu-id="aa46e-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
