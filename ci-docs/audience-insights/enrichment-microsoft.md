---
title: Perkayakan profil pelanggan dengan data daripada Microsoft
description: Gunakan data proprietari daripada Microsoft untuk memperkayakan data pelanggan anda dengan afiniti jenama dan tarikan.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896613"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="01543-103">Mengayakan profil pelanggan dengan persamaan jenama dan kepentingan (pratonton)</span><span class="sxs-lookup"><span data-stu-id="01543-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="01543-104">Gunakan data proprietari daripada Microsoft untuk memperkayakan data pelanggan anda dengan afiniti jenama dan tarikan.</span><span class="sxs-lookup"><span data-stu-id="01543-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="01543-105">Afiniti ini ditentukan berdasarkan data daripada orang dengan demografi yang sama kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="01543-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="01543-106">Maklumat ini membantu anda untuk memahami dengan lebih baik dan membahagikan pelanggan anda berdasarkan afiniti mereka kepada jenama dan kepentingan khusus.</span><span class="sxs-lookup"><span data-stu-id="01543-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="01543-107">Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan** untuk [mengkonfigurasi dan melihat pengayaan](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="01543-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="01543-108">Untuk mengkonfigurasikan pengayaan afiniti jenama pergi ke tab **Temui** dan pilih **Perkayakan data saya** pada jubin **Jenama**.</span><span class="sxs-lookup"><span data-stu-id="01543-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="01543-109">Untuk mengkonfigurasikan pengayaan afiniti kepentingan, pergi ke tab **Temui** dan pilih **Perkayakan data saya** pada jubin **Kepentingan**.</span><span class="sxs-lookup"><span data-stu-id="01543-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01543-110">![Jubin jenama & Minat](media/BrandsInterest-tile-Hub.png "Jubin jenama & Minat")</span><span class="sxs-lookup"><span data-stu-id="01543-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="01543-111">Cara kami menentukan afiniti</span><span class="sxs-lookup"><span data-stu-id="01543-111">How we determine affinities</span></span>

<span data-ttu-id="01543-112">Kami menggunakan data carian dalam talian Microsoft untuk mencari afiniti untuk jenama dan minat merentasi pelbagai segmen demografik (ditakrifkan mengikut umur, jantina atau lokasi).</span><span class="sxs-lookup"><span data-stu-id="01543-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="01543-113">Jumlah carian dalam talian untuk sesebuah jenama atau faedah menentukan jumlah persamaan bahagian demografi berbanding segmen lain yang mempunyai persamaan jenama atau kepentingan.</span><span class="sxs-lookup"><span data-stu-id="01543-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="01543-114">Jenama atau minat.</span><span class="sxs-lookup"><span data-stu-id="01543-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="01543-115">Tahap dan skor perkaitan</span><span class="sxs-lookup"><span data-stu-id="01543-115">Affinity level and score</span></span>

<span data-ttu-id="01543-116">Pada setiap profil pelanggan yang diperkaya, kami menyediakan dua nilai yang berkaitan – tahap perkaitan dan skor perkaitan.</span><span class="sxs-lookup"><span data-stu-id="01543-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="01543-117">Nilai ini membantu anda menentukan kekuatan perkaitan itu untuk bahagian demografi profil, untuk jenama atau minat, berbanding dengan segmen demografi lain.</span><span class="sxs-lookup"><span data-stu-id="01543-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="01543-118">*Tahap perkaitan* terdiri daripada empat peringkat dan *skor perkaitan* akan dikira berdasarkan skala 100 mata yang memetakan kepada tahap perkaitan.</span><span class="sxs-lookup"><span data-stu-id="01543-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="01543-119">Peringkat perkaitan</span><span class="sxs-lookup"><span data-stu-id="01543-119">Affinity level</span></span> |<span data-ttu-id="01543-120">Skor perkaitan</span><span class="sxs-lookup"><span data-stu-id="01543-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="01543-121">Sangat tinggi</span><span class="sxs-lookup"><span data-stu-id="01543-121">Very high</span></span>     | <span data-ttu-id="01543-122">85-100</span><span class="sxs-lookup"><span data-stu-id="01543-122">85-100</span></span>       |
|<span data-ttu-id="01543-123">Tinggi</span><span class="sxs-lookup"><span data-stu-id="01543-123">High</span></span>     | <span data-ttu-id="01543-124">70-84</span><span class="sxs-lookup"><span data-stu-id="01543-124">70-84</span></span>        |
|<span data-ttu-id="01543-125">Sederhana</span><span class="sxs-lookup"><span data-stu-id="01543-125">Medium</span></span>     | <span data-ttu-id="01543-126">35-69</span><span class="sxs-lookup"><span data-stu-id="01543-126">35-69</span></span>        |
|<span data-ttu-id="01543-127">Rendah</span><span class="sxs-lookup"><span data-stu-id="01543-127">Low</span></span>     | <span data-ttu-id="01543-128">1-34</span><span class="sxs-lookup"><span data-stu-id="01543-128">1-34</span></span>        |

<span data-ttu-id="01543-129">Bergantung pada butiran yang anda mahu untuk mengukur perkaitan, anda boleh menggunakan sama ada tahap atau skor perkaitan.</span><span class="sxs-lookup"><span data-stu-id="01543-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="01543-130">Skor perkaitan memberikan anda kawalan yang lebih tepat.</span><span class="sxs-lookup"><span data-stu-id="01543-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="01543-131">Negara/rantau yang disokong</span><span class="sxs-lookup"><span data-stu-id="01543-131">Supported countries/regions</span></span>

<span data-ttu-id="01543-132">Kami kini menyokong pilihan negara/rantau berikut: Australia, Kanada (Bahasa Inggeris), Perancis, Jerman, United Kingdom atau Amerika Syarikat (Bahasa Inggeris).</span><span class="sxs-lookup"><span data-stu-id="01543-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="01543-133">Untuk memilih negara, buka **Pengayaan jenama** atau **Pengayaan minat** dan pilih **Tukar** bersebelahan dengan **Negara/Rantau**.</span><span class="sxs-lookup"><span data-stu-id="01543-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="01543-134">Dalam anak tetingkap **Tetapan Negara/Rantau**, pilih pilihan dan pilih **Gunakan**.</span><span class="sxs-lookup"><span data-stu-id="01543-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="01543-135">Implikasi berkaitan dengan pemilihan negara</span><span class="sxs-lookup"><span data-stu-id="01543-135">Implications related to country selection</span></span>

- <span data-ttu-id="01543-136">Apabila [memilih jenama anda sendiri](#define-your-brands-or-interests), sistem memberikan cadangan berdasarkan negara atau rantau yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="01543-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="01543-137">Apabila [memilih industri](#define-your-brands-or-interests), anda akan mendapat jenama atau minat yang paling berkaitan berdasarkan negara atau rantau yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="01543-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="01543-138">Apabila [memperkayakan profil](#refresh-enrichment), kami akan memperkayakan semua profil pelanggan yang membolehkan kami mendapatkan data untuk jenama dan minat yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="01543-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="01543-139">Termasuk profil yang tidak berada dalam negara atau rantau yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="01543-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="01543-140">Sebagai contoh, jika anda memilih Jerman, kami akan memperkayakan profil yang terletak di Amerika Syarikat jika kami mempunyai data yang tersedia untuk jenama dan minat yang dipilih di Amerika Syarikat.</span><span class="sxs-lookup"><span data-stu-id="01543-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="01543-141">Konfigurasikan Pengayaan</span><span class="sxs-lookup"><span data-stu-id="01543-141">Configure Enrichment</span></span>

<span data-ttu-id="01543-142">Pengalaman berpandu membantu anda melalui konfigurasi pengayaan.</span><span class="sxs-lookup"><span data-stu-id="01543-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="01543-143">Takrifkan jenama dan kepentingan anda</span><span class="sxs-lookup"><span data-stu-id="01543-143">Define your brands or interests</span></span>

<span data-ttu-id="01543-144">Pilih salah satu daripada pilihan berikut:</span><span class="sxs-lookup"><span data-stu-id="01543-144">Select one of the following options:</span></span>

- <span data-ttu-id="01543-145">**Industri**: Sistem mengenal pasti jenama dan kepentingan teratas yang berkaitan dengan industri anda dan mengayakan data pelanggan anda dengannya.</span><span class="sxs-lookup"><span data-stu-id="01543-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="01543-146">**Pilih milik anda sendiri**: Pilih sehingga lima item daripada senarai jenama dan kepentingan yang paling berkaitan dengan organisasi anda.</span><span class="sxs-lookup"><span data-stu-id="01543-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="01543-147">Untuk menambah jenama atau kepentingan, masukkannya ke dalam kawasan input untuk mendapatkan cadangan berdasarkan terma yang sepadan.</span><span class="sxs-lookup"><span data-stu-id="01543-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="01543-148">Jika kami tidak menyenaraikan jenama atau minat yang anda cari, hantar maklum balas kepada kami menggunakan pautan **Cadangkan**.</span><span class="sxs-lookup"><span data-stu-id="01543-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="01543-149">Semak keutamaan pengayaan</span><span class="sxs-lookup"><span data-stu-id="01543-149">Review enrichment preferences</span></span>

<span data-ttu-id="01543-150">Semak keutamaan pengayaan lalai anda dan kemas kini apabila diperlukan.</span><span class="sxs-lookup"><span data-stu-id="01543-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Tangkapan skrin tetingkap keutamaan pengayaan.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="01543-152">Pilih entiti untuk memperkaya</span><span class="sxs-lookup"><span data-stu-id="01543-152">Select entity to enrich</span></span>

<span data-ttu-id="01543-153">Pilih **Entiti yang diperkaya** dan pilih set data yang anda mahu perkayakan dengan data syarikat daripada Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01543-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="01543-154">Anda boleh memilih entiti Pelanggan untuk memperkayakan semua profil pelanggan anda atau pilih entiti segmen untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="01543-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="01543-155">Petakan medan anda</span><span class="sxs-lookup"><span data-stu-id="01543-155">Map your fields</span></span>

<span data-ttu-id="01543-156">Medan peta daripada entiti pelanggan disatukan anda untuk mentakrifkan segmen demografi yang anda mahu sistem gunakan untuk memperkaya data pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="01543-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="01543-157">Peta Negara/Rantau dan sekurang-kurangnya atribut Tarikh Lahir atau Jantina.</span><span class="sxs-lookup"><span data-stu-id="01543-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="01543-158">Di samping itu, anda mesti memetakan sekurang-kurangnya satu daripada Bandar (dan Negeri/Wilayah) atau Poskod.</span><span class="sxs-lookup"><span data-stu-id="01543-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="01543-159">Pilih **Edit** untuk mentakrifkan pemetaan medan dan pilih **Gunakan** apabila anda selesai.</span><span class="sxs-lookup"><span data-stu-id="01543-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="01543-160">Pilih **Simpan** untuk melengkapkan pemetaan medan.</span><span class="sxs-lookup"><span data-stu-id="01543-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="01543-161">Format dan nilai berikut disokong, nilai bukan sensitif huruf:</span><span class="sxs-lookup"><span data-stu-id="01543-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="01543-162">**Tarikh Lahir**: Kami mengesyorkan bahawa tarikh lahir ditukarkan ke jenis DateTime semasa pengingesan data.</span><span class="sxs-lookup"><span data-stu-id="01543-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="01543-163">Secara alternatif, ianya boleh menjadi rentetan dalam format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyyy-MM-dd" atau "yyyy-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="01543-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="01543-164">**Jantina**: Lelaki, Perempuan,Tidak Diketahui</span><span class="sxs-lookup"><span data-stu-id="01543-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="01543-165">**Poskod**: Kod zip lima digit untuk Amerika Syarikat, poskod standard di tempat lain</span><span class="sxs-lookup"><span data-stu-id="01543-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="01543-166">**Bandar**: Nama bandar dalam Bahasa Inggeris</span><span class="sxs-lookup"><span data-stu-id="01543-166">**City**: City name in English</span></span>
- <span data-ttu-id="01543-167">**Negeri/Wilayah**: Singkatan dua huruf untuk Amerika Syarikat dan Kanada.</span><span class="sxs-lookup"><span data-stu-id="01543-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="01543-168">Singkatan dua atau tiga huruf untuk Australia.</span><span class="sxs-lookup"><span data-stu-id="01543-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="01543-169">Tidak terpakai untuk Perancis, Jerman atau UK.</span><span class="sxs-lookup"><span data-stu-id="01543-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="01543-170">**Negara/Rantau**:</span><span class="sxs-lookup"><span data-stu-id="01543-170">**Country/Region**:</span></span>

  - <span data-ttu-id="01543-171">AS: Amerika Syarikat, Amerika Syarikat, USA, AS, Amerika</span><span class="sxs-lookup"><span data-stu-id="01543-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="01543-172">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="01543-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="01543-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain dan Northern Ireland, United Kingdom of Great Britain</span><span class="sxs-lookup"><span data-stu-id="01543-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="01543-174">AU: Australia, AU, Komanwel Australia</span><span class="sxs-lookup"><span data-stu-id="01543-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="01543-175">FR: Bahasa Perancis, FR, French Republic</span><span class="sxs-lookup"><span data-stu-id="01543-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="01543-176">DE: Jerman, Jerman, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span><span class="sxs-lookup"><span data-stu-id="01543-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="01543-177">Semak dan namakan pengayaan</span><span class="sxs-lookup"><span data-stu-id="01543-177">Review and name the enrichment</span></span>

<span data-ttu-id="01543-178">Akhir sekali, anda boleh menyemak maklumat dan memberikan nama untuk pengayaan.</span><span class="sxs-lookup"><span data-stu-id="01543-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Halaman semakan dan penamaan minat.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="01543-180">Pengayaan segar semula</span><span class="sxs-lookup"><span data-stu-id="01543-180">Refresh enrichment</span></span>

<span data-ttu-id="01543-181">Jalankan pengayaan selepas mengkonfigurasi jenama, kepentingan dan pemetaan medan untuk demografi.</span><span class="sxs-lookup"><span data-stu-id="01543-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="01543-182">Untuk memulakan proses, pilih **Jalankan** pada halaman konfigurasi jenama dan kepentingan.</span><span class="sxs-lookup"><span data-stu-id="01543-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="01543-183">Selain itu, anda boleh membiarkan sistem jalankan pengayaan secara automatik sebagai sebahagian daripada segar semula yang dijadualkan.</span><span class="sxs-lookup"><span data-stu-id="01543-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="01543-184">Bergantung pada saiz data pelanggan anda, ia mungkin mengambil masa beberapa minit untuk jangka masa pengayaan dilengkapkan.</span><span class="sxs-lookup"><span data-stu-id="01543-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="01543-185">Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="01543-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="01543-186">Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="01543-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="01543-187">Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja.</span><span class="sxs-lookup"><span data-stu-id="01543-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="01543-188">Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="01543-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="01543-189">Keputusan pengayaan</span><span class="sxs-lookup"><span data-stu-id="01543-189">Enrichment results</span></span>

<span data-ttu-id="01543-190">Selepas menjalankan proses pengayaan, pergi ke **Pengayaan saya** untuk menyemak semula jumlah bilangan pelanggan yang diperkayakan dan pecahan jenama dan kepentingan dalam proses pelanggan yang diperkayakan.</span><span class="sxs-lookup"><span data-stu-id="01543-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Pratonton keputusan selepas menjalankan proses pengayaan":::

<span data-ttu-id="01543-192">Kaji semula data yang diperkaya dengan memilih **Lihat data diperkaya** dalam carta.</span><span class="sxs-lookup"><span data-stu-id="01543-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="01543-193">Data diperkaya untuk jenama pergi kepada entiti **PersamaanJenamaDaripadaMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="01543-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="01543-194">Data untuk kepentingan adalah dalam entiti **PersamaanKepentinganDaripadaMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="01543-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="01543-195">Anda juga akan menemui entiti ini yang disenaraikan dalam kumpulan **Pengayaan** dalam **Entiti** > **Data**.</span><span class="sxs-lookup"><span data-stu-id="01543-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="01543-196">Lihat data pengayaan pada kad pelanggan</span><span class="sxs-lookup"><span data-stu-id="01543-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="01543-197">Jenama dan afiniti berkepentingan juga boleh dilihat pada kad pelanggan individu.</span><span class="sxs-lookup"><span data-stu-id="01543-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="01543-198">Pergi ke **Pelanggan** dan pilih profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="01543-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="01543-199">Dalam kad pelanggan, anda akan menemui carta untuk jenama atau kepentingan yang orang dalam profil demografik pelanggan mempunyai afiniti untuknya.</span><span class="sxs-lookup"><span data-stu-id="01543-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kad pelanggan dengan data diperkaya":::

## <a name="next-steps"></a><span data-ttu-id="01543-201">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="01543-201">Next steps</span></span>

<span data-ttu-id="01543-202">Bina di atas data pelanggan anda yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="01543-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="01543-203">Cipta [Langkah-langkah](segments.md), [Bahagain](measures.md) dan juga [eksport data](export-destinations.md) untuk menyampaikan pengalaman peribadi kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="01543-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
