---
title: Perkayakan profil pelanggan dengan data daripada Microsoft
description: Gunakan data proprietari daripada Microsoft untuk memperkayakan data pelanggan anda dengan afiniti jenama dan tarikan.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305167"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="fe11b-103">Mengayakan profil pelanggan dengan persamaan jenama dan kepentingan (pratonton)</span><span class="sxs-lookup"><span data-stu-id="fe11b-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="fe11b-104">Gunakan data proprietari daripada Microsoft untuk memperkayakan data pelanggan anda dengan afiniti jenama dan tarikan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="fe11b-105">Afiniti ini adalah berdasarkan data daripada orang yang mempunyai demografi yang serupa dengan pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="fe11b-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="fe11b-106">Maklumat ini membantu anda untuk memahami dengan lebih baik dan membahagikan pelanggan anda berdasarkan afiniti mereka kepada jenama dan kepentingan khusus.</span><span class="sxs-lookup"><span data-stu-id="fe11b-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="fe11b-107">Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan** untuk [mengkonfigurasi dan melihat pengayaan](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="fe11b-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="fe11b-108">Untuk mengkonfigurasikan pengayaan afiniti jenama pergi ke tab **Temui** dan pilih **Perkayakan data saya** pada jubin **Jenama**.</span><span class="sxs-lookup"><span data-stu-id="fe11b-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="fe11b-109">Untuk mengkonfigurasikan pengayaan afiniti kepentingan, pergi ke tab **Temui** dan pilih **Perkayakan data saya** pada jubin **Kepentingan**.</span><span class="sxs-lookup"><span data-stu-id="fe11b-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fe11b-110">![Jubin Jenama dan Minat](media/BrandsInterest-tile-Hub.png "Jubin Jenama dan Minat")</span><span class="sxs-lookup"><span data-stu-id="fe11b-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="fe11b-111">Cara kami menentukan afiniti</span><span class="sxs-lookup"><span data-stu-id="fe11b-111">How we determine affinities</span></span>

<span data-ttu-id="fe11b-112">Kami menggunakan data carian dalam talian Microsoft untuk mencari afiniti untuk jenama dan minat merentasi pelbagai segmen demografik (ditakrifkan mengikut umur, jantina atau lokasi).</span><span class="sxs-lookup"><span data-stu-id="fe11b-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="fe11b-113">Jumlah carian dalam talian untuk sesebuah jenama atau faedah menentukan jumlah persamaan bahagian demografi berbanding segmen lain yang mempunyai persamaan jenama atau kepentingan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="fe11b-114">Tahap dan skor perkaitan</span><span class="sxs-lookup"><span data-stu-id="fe11b-114">Affinity level and score</span></span>

<span data-ttu-id="fe11b-115">Pada setiap profil pelanggan yang diperkaya, kami menyediakan dua nilai yang berkaitan: tahap afiniti dan skor afiniti.</span><span class="sxs-lookup"><span data-stu-id="fe11b-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="fe11b-116">Nilai ini membantu anda menentukan kekuatan perkaitan itu untuk bahagian demografi profil, untuk jenama atau minat, berbanding dengan segmen demografi lain.</span><span class="sxs-lookup"><span data-stu-id="fe11b-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="fe11b-117">*Tahap perkaitan* terdiri daripada empat peringkat dan *skor perkaitan* akan dikira berdasarkan skala 100 mata yang memetakan kepada tahap perkaitan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="fe11b-118">Peringkat perkaitan</span><span class="sxs-lookup"><span data-stu-id="fe11b-118">Affinity level</span></span> |<span data-ttu-id="fe11b-119">Skor perkaitan</span><span class="sxs-lookup"><span data-stu-id="fe11b-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="fe11b-120">Sangat tinggi</span><span class="sxs-lookup"><span data-stu-id="fe11b-120">Very high</span></span>     | <span data-ttu-id="fe11b-121">85-100</span><span class="sxs-lookup"><span data-stu-id="fe11b-121">85-100</span></span>       |
|<span data-ttu-id="fe11b-122">Tinggi</span><span class="sxs-lookup"><span data-stu-id="fe11b-122">High</span></span>     | <span data-ttu-id="fe11b-123">70-84</span><span class="sxs-lookup"><span data-stu-id="fe11b-123">70-84</span></span>        |
|<span data-ttu-id="fe11b-124">Sederhana</span><span class="sxs-lookup"><span data-stu-id="fe11b-124">Medium</span></span>     | <span data-ttu-id="fe11b-125">35-69</span><span class="sxs-lookup"><span data-stu-id="fe11b-125">35-69</span></span>        |
|<span data-ttu-id="fe11b-126">Rendah</span><span class="sxs-lookup"><span data-stu-id="fe11b-126">Low</span></span>     | <span data-ttu-id="fe11b-127">1-34</span><span class="sxs-lookup"><span data-stu-id="fe11b-127">1-34</span></span>        |

<span data-ttu-id="fe11b-128">Bergantung pada butiran yang anda mahu untuk mengukur perkaitan, anda boleh menggunakan sama ada tahap atau skor perkaitan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="fe11b-129">Skor perkaitan memberikan anda kawalan yang lebih tepat.</span><span class="sxs-lookup"><span data-stu-id="fe11b-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="fe11b-130">Negara/rantau yang disokong</span><span class="sxs-lookup"><span data-stu-id="fe11b-130">Supported countries/regions</span></span>

<span data-ttu-id="fe11b-131">Kami kini menyokong pilihan negara/rantau berikut: Australia, Kanada (Bahasa Inggeris), Perancis, Jerman, United Kingdom atau Amerika Syarikat (Bahasa Inggeris).</span><span class="sxs-lookup"><span data-stu-id="fe11b-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="fe11b-132">Untuk memilih negara atau rantau, buka **Pengayaan jenama** atau **Pengayaan minat** dan pilih **Tukar** di sebelah **Negara/Rantau**.</span><span class="sxs-lookup"><span data-stu-id="fe11b-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="fe11b-133">Dalam anak tetingkap **Tetapan Negara/Rantau**, pilih pilihan dan pilih **Gunakan**.</span><span class="sxs-lookup"><span data-stu-id="fe11b-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="fe11b-134">Implikasi berkaitan dengan pemilihan negara</span><span class="sxs-lookup"><span data-stu-id="fe11b-134">Implications related to country selection</span></span>

- <span data-ttu-id="fe11b-135">Apabila [memilih jenama anda sendiri](#define-your-brands-or-interests), sistem memberikan cadangan berdasarkan negara atau rantau yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="fe11b-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="fe11b-136">Apabila [memilih industri](#define-your-brands-or-interests), anda akan mendapat jenama atau minat yang paling berkaitan berdasarkan negara atau rantau yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="fe11b-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="fe11b-137">Apabila [memperkaya profil](#refresh-enrichment), kami akan memperkaya semua profil pelanggan yang data diperoleh untuk jenama dan minat yang dipilih, termasuk profil yang tidak berada di negara atau rantau yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="fe11b-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="fe11b-138">Sebagai contoh, jika anda memilih Jerman, kami akan memperkayakan profil yang terletak di Amerika Syarikat jika kami mempunyai data yang tersedia untuk jenama dan minat yang dipilih di Amerika Syarikat.</span><span class="sxs-lookup"><span data-stu-id="fe11b-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="fe11b-139">Konfigurasikan pengayaan</span><span class="sxs-lookup"><span data-stu-id="fe11b-139">Configure enrichment</span></span>

<span data-ttu-id="fe11b-140">Pengalaman berpandu membantu anda melalui konfigurasi pengayaan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="fe11b-141">Takrifkan jenama dan kepentingan anda</span><span class="sxs-lookup"><span data-stu-id="fe11b-141">Define your brands or interests</span></span>

<span data-ttu-id="fe11b-142">Pilih sehingga lima jenama atau minat menggunakan satu atau kedua-dua pilihan ini:</span><span class="sxs-lookup"><span data-stu-id="fe11b-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="fe11b-143">**Industri**: Pilih industri anda daripada senarai juntai bawah dan kemudian pilih daripada jenama atau minat popular untuk industri tersebut.</span><span class="sxs-lookup"><span data-stu-id="fe11b-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="fe11b-144">**Pilih sendiri**: Masukkan jenama atau minat yang berkaitan dengan organisasi anda dan kemudian pilih daripada cadangan yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="fe11b-145">Jika kami tidak menyenaraikan jenama atau minat yang anda cari, hantar maklum balas kepada kami menggunakan pautan **Cadangkan**.</span><span class="sxs-lookup"><span data-stu-id="fe11b-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="fe11b-146">Semak keutamaan pengayaan</span><span class="sxs-lookup"><span data-stu-id="fe11b-146">Review enrichment preferences</span></span>

<span data-ttu-id="fe11b-147">Semak keutamaan pengayaan lalai anda dan kemas kini apabila diperlukan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Tangkapan skrin tetingkap keutamaan pengayaan.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="fe11b-149">Pilih entiti untuk memperkaya</span><span class="sxs-lookup"><span data-stu-id="fe11b-149">Select entity to enrich</span></span>

<span data-ttu-id="fe11b-150">Pilih **Entiti yang diperkaya** dan pilih set data yang anda mahu perkayakan dengan data syarikat daripada Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fe11b-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="fe11b-151">Anda boleh memilih entiti Pelanggan untuk memperkayakan semua profil pelanggan anda atau pilih entiti segmen untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="fe11b-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="fe11b-152">Petakan medan anda</span><span class="sxs-lookup"><span data-stu-id="fe11b-152">Map your fields</span></span>

<span data-ttu-id="fe11b-153">Medan peta daripada entiti pelanggan disatukan anda untuk mentakrifkan segmen demografi yang anda mahu sistem gunakan untuk memperkaya data pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="fe11b-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="fe11b-154">Peta Negara/Rantau dan sekurang-kurangnya atribut Tarikh Lahir atau Jantina.</span><span class="sxs-lookup"><span data-stu-id="fe11b-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="fe11b-155">Di samping itu, anda mesti memetakan sekurang-kurangnya satu daripada Bandar (dan Negeri/Wilayah) atau Poskod.</span><span class="sxs-lookup"><span data-stu-id="fe11b-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="fe11b-156">Pilih **Edit** untuk mentakrifkan pemetaan medan dan pilih **Gunakan** apabila anda selesai.</span><span class="sxs-lookup"><span data-stu-id="fe11b-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="fe11b-157">Pilih **Simpan** untuk melengkapkan pemetaan medan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="fe11b-158">Format dan nilai berikut disokong (nilai tidak sensitif huruf):</span><span class="sxs-lookup"><span data-stu-id="fe11b-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="fe11b-159">**Tarikh Lahir**: Kami mengesyorkan bahawa tarikh lahir ditukarkan ke jenis DateTime semasa pengingesan data.</span><span class="sxs-lookup"><span data-stu-id="fe11b-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="fe11b-160">Sebagai alternatif, ia boleh menjadi rentetan dalam format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyy-MM-dd" atau "yyyy-MM-ddTHH:mm:ss".</span><span class="sxs-lookup"><span data-stu-id="fe11b-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="fe11b-161">**Jantina**: Lelaki, Perempuan,Tidak Diketahui.</span><span class="sxs-lookup"><span data-stu-id="fe11b-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="fe11b-162">**Poskod**: Kod ZIP lima digit untuk Amerika Syarikat, poskod standard di mana-mana sahaja.</span><span class="sxs-lookup"><span data-stu-id="fe11b-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="fe11b-163">**Bandar**: Nama bandar dalam bahasa Inggeris.</span><span class="sxs-lookup"><span data-stu-id="fe11b-163">**City**: City name in English.</span></span>
- <span data-ttu-id="fe11b-164">**Negeri/Wilayah**: Singkatan dua huruf untuk Amerika Syarikat dan Kanada.</span><span class="sxs-lookup"><span data-stu-id="fe11b-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="fe11b-165">Singkatan dua atau tiga huruf untuk Australia.</span><span class="sxs-lookup"><span data-stu-id="fe11b-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="fe11b-166">Tidak terpakai untuk Perancis, Jerman atau UK.</span><span class="sxs-lookup"><span data-stu-id="fe11b-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="fe11b-167">**Negara/Rantau**:</span><span class="sxs-lookup"><span data-stu-id="fe11b-167">**Country/Region**:</span></span>

  - <span data-ttu-id="fe11b-168">AS: Amerika Syarikat, Amerika Syarikat, USA, AS, Amerika</span><span class="sxs-lookup"><span data-stu-id="fe11b-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="fe11b-169">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="fe11b-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="fe11b-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain dan Northern Ireland, United Kingdom of Great Britain</span><span class="sxs-lookup"><span data-stu-id="fe11b-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="fe11b-171">AU: Australia, AU, Komanwel Australia</span><span class="sxs-lookup"><span data-stu-id="fe11b-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="fe11b-172">FR: Bahasa Perancis, FR, French Republic</span><span class="sxs-lookup"><span data-stu-id="fe11b-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="fe11b-173">DE: Jerman, Jerman, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span><span class="sxs-lookup"><span data-stu-id="fe11b-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="fe11b-174">Semak dan namakan pengayaan</span><span class="sxs-lookup"><span data-stu-id="fe11b-174">Review and name the enrichment</span></span>

<span data-ttu-id="fe11b-175">Akhir sekali, anda boleh menyemak maklumat dan memberikan nama untuk pengayaan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Halaman semakan dan penamaan minat.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="fe11b-177">Pengayaan segar semula</span><span class="sxs-lookup"><span data-stu-id="fe11b-177">Refresh enrichment</span></span>

<span data-ttu-id="fe11b-178">Jalankan pengayaan selepas mengkonfigurasi jenama, kepentingan dan pemetaan medan untuk demografi.</span><span class="sxs-lookup"><span data-stu-id="fe11b-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="fe11b-179">Untuk memulakan proses, pilih **Jalankan** pada halaman konfigurasi jenama dan kepentingan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="fe11b-180">Selain itu, anda boleh membiarkan sistem jalankan pengayaan secara automatik sebagai sebahagian daripada segar semula yang dijadualkan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="fe11b-181">Bergantung pada saiz data pelanggan anda, ia mungkin mengambil masa beberapa minit untuk jangka masa pengayaan dilengkapkan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="fe11b-182">Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="fe11b-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="fe11b-183">Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="fe11b-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="fe11b-184">Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja.</span><span class="sxs-lookup"><span data-stu-id="fe11b-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="fe11b-185">Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda akan menemukan maklumat tambahan: masa pemprosesan, tarikh pemprosesan terakhir serta semua ralat dan amaran yang berkaitan dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="fe11b-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="fe11b-186">Keputusan pengayaan</span><span class="sxs-lookup"><span data-stu-id="fe11b-186">Enrichment results</span></span>

<span data-ttu-id="fe11b-187">Selepas menjalankan proses pengayaan, pergi ke **Pengayaan saya** untuk menyemak semula jumlah bilangan pelanggan yang diperkayakan dan pecahan jenama dan kepentingan dalam proses pelanggan yang diperkayakan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Pratonton keputusan selepas menjalankan proses pengayaan":::

<span data-ttu-id="fe11b-189">Kaji semula data yang diperkaya dengan memilih **Lihat data diperkaya** dalam carta.</span><span class="sxs-lookup"><span data-stu-id="fe11b-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="fe11b-190">Data diperkaya untuk jenama pergi kepada entiti **PersamaanJenamaDaripadaMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="fe11b-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="fe11b-191">Data untuk kepentingan adalah dalam entiti **PersamaanKepentinganDaripadaMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="fe11b-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="fe11b-192">Anda juga akan menemui entiti ini yang disenaraikan dalam kumpulan **Pengayaan** dalam **Entiti** > **Data**.</span><span class="sxs-lookup"><span data-stu-id="fe11b-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="fe11b-193">Lihat data pengayaan pada kad pelanggan</span><span class="sxs-lookup"><span data-stu-id="fe11b-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="fe11b-194">Jenama dan afiniti berkepentingan juga boleh dilihat pada kad pelanggan individu.</span><span class="sxs-lookup"><span data-stu-id="fe11b-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="fe11b-195">Pergi ke **Pelanggan** dan pilih profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="fe11b-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="fe11b-196">Dalam kad pelanggan, anda akan menemui carta untuk jenama atau kepentingan yang orang dalam profil demografik pelanggan mempunyai afiniti untuknya.</span><span class="sxs-lookup"><span data-stu-id="fe11b-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kad pelanggan dengan data diperkaya":::

## <a name="next-steps"></a><span data-ttu-id="fe11b-198">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="fe11b-198">Next steps</span></span>

<span data-ttu-id="fe11b-199">Bina di atas data pelanggan anda yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="fe11b-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fe11b-200">Cipta [Segmen](segments.md) dan [Langkah](measures.md) dan juga [eksport data](export-destinations.md) untuk menyampaikan pengalaman yang diperibadikan kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="fe11b-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
