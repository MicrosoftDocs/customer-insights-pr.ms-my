---
title: Cipta dan urus tindakan
description: Takrifkan ukuran untuk menganalisis dan mencerminkan prestasi perniagaan anda.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304811"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="eee2c-103">Takrifkan dan urus tindakan</span><span class="sxs-lookup"><span data-stu-id="eee2c-103">Define and manage measures</span></span>

<span data-ttu-id="eee2c-104">Langkah ini membantu anda untuk lebih memahami tingkah laku pelanggan dan prestasi perniagaan.</span><span class="sxs-lookup"><span data-stu-id="eee2c-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="eee2c-105">Mereka melihat nilai yang relevan daripada [profil disatukan](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="eee2c-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="eee2c-106">Contohnya, perniagaan ingin melihat *jumlah perbelanjaan setiap pelanggan* untuk memahami sejarah pembelian pelanggan individu atau mengukur *jumlah jualan syarikat* untuk memahami hasil peringkat agregat dalam keseluruhan perniagaan.</span><span class="sxs-lookup"><span data-stu-id="eee2c-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="eee2c-107">Ukuran dicipta menggunakan pembina ukuran, platform pertanyaan data dengan pelbagai pengendali dan pilihan pemetaan yang mudah.</span><span class="sxs-lookup"><span data-stu-id="eee2c-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="eee2c-108">Ia membolehkan anda menapis data, mengumpulkan hasil, mengesan [laluan perhubungan entiti](relationships.md) dan pratonton output.</span><span class="sxs-lookup"><span data-stu-id="eee2c-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="eee2c-109">Gunakan pembina ukuran untuk merancang aktiviti perniagaan dengan bertanya pada data pelanggan dan mendapatkan wawasan.</span><span class="sxs-lookup"><span data-stu-id="eee2c-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="eee2c-110">Sebagai contoh, mencipta ukuran *jumlah perbelanjaan setiap pelanggan* dan *jumlah pulangan setiap pelanggan* membantu mengenal pasti kumpulan pelanggan yang mempunyai perbelanjaan tinggi tetapi pulangan tinggi.</span><span class="sxs-lookup"><span data-stu-id="eee2c-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="eee2c-111">Anda boleh [mencipta segmen](segments.md) untuk memacu tindakan terbaik seterusnya.</span><span class="sxs-lookup"><span data-stu-id="eee2c-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="eee2c-112">Bina ukuran anda sendiri dari mula</span><span class="sxs-lookup"><span data-stu-id="eee2c-112">Build your own measure from scratch</span></span>

<span data-ttu-id="eee2c-113">Bahagian ini membimbing anda mencipta ukuran baharu dari awal.</span><span class="sxs-lookup"><span data-stu-id="eee2c-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="eee2c-114">Anda boleh membina ukuran dengan atribut data daripada entiti data yang mempunyai persediaan untuk berhubung dengan entiti Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="eee2c-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="eee2c-115">Dalam wawasan khalayak, pergi ke **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="eee2c-116">Pilih **Baharu** dan pilih **Bina yang anda sendiri**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="eee2c-117">Pilih **Edit nama** dan berikan **Nama** untuk langkah itu.</span><span class="sxs-lookup"><span data-stu-id="eee2c-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="eee2c-118">Jika konfigurasi ukuran baharu anda hanya mempunyai dua medan—contohnya, CustomerID dan satu pengiraan—output akan ditambahkan sebagai lajur baharu pada entiti dijana sistem yang dipanggil Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="eee2c-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="eee2c-119">Dan anda akan dapat melihat nilai ukuran dalam profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="eee2c-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="eee2c-120">Ukuran lain akan menjana entiti mereka sendiri.</span><span class="sxs-lookup"><span data-stu-id="eee2c-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="eee2c-121">Dalam kawasan konfigurasi, pilih fungsi pengagregatan daripada menu juntai bawah **Pilih Fungsi**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="eee2c-122">Fungsi pengagregatan termasuk:</span><span class="sxs-lookup"><span data-stu-id="eee2c-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="eee2c-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="eee2c-123">**Sum**</span></span>
   - <span data-ttu-id="eee2c-124">**Purata**</span><span class="sxs-lookup"><span data-stu-id="eee2c-124">**Average**</span></span>
   - <span data-ttu-id="eee2c-125">**Bilangan**</span><span class="sxs-lookup"><span data-stu-id="eee2c-125">**Count**</span></span>
   - <span data-ttu-id="eee2c-126">**Kira Unik**</span><span class="sxs-lookup"><span data-stu-id="eee2c-126">**Count Unique**</span></span>
   - <span data-ttu-id="eee2c-127">**Maksimum**</span><span class="sxs-lookup"><span data-stu-id="eee2c-127">**Max**</span></span>
   - <span data-ttu-id="eee2c-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="eee2c-128">**Min**</span></span>
   - <span data-ttu-id="eee2c-129">**Pertama**: mengambil kira nilai pertama bagi rekod data</span><span class="sxs-lookup"><span data-stu-id="eee2c-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="eee2c-130">**Terakhir**: ambil nilai terakhir yang ditambah ke rekod data</span><span class="sxs-lookup"><span data-stu-id="eee2c-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operator untuk mengukur pengiraan.":::

1. <span data-ttu-id="eee2c-132">Pilih **Tambah atribut** untuk memilih data yang anda perlukan untuk mencipta ukuran ini.</span><span class="sxs-lookup"><span data-stu-id="eee2c-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="eee2c-133">Pilih tab **Atribut**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="eee2c-134">Entiti data: Pilih entiti yang termasuk atribut yang anda mahu ukur.</span><span class="sxs-lookup"><span data-stu-id="eee2c-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="eee2c-135">Atribut data: Pilih atribut yang anda mahu gunakan dalam fungsi pengagregatan untuk mengira ukuran.</span><span class="sxs-lookup"><span data-stu-id="eee2c-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="eee2c-136">Anda hanya boleh memilih satu atribut pada satu masa.</span><span class="sxs-lookup"><span data-stu-id="eee2c-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="eee2c-137">Anda juga boleh memilih atribut data daripada ukuran sedia ada dengan memilih tab **Ukuran**. Atau, anda boleh mencari nama entiti atau ukuran.</span><span class="sxs-lookup"><span data-stu-id="eee2c-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="eee2c-138">Pilih **Tambah** untuk menambah atribut terpilih pada ukuran.</span><span class="sxs-lookup"><span data-stu-id="eee2c-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Pilih atribut untuk digunakan dalam pengiraan.":::

1. <span data-ttu-id="eee2c-140">Untuk membina lebih banyak ukuran rumit, anda boleh menambah lebih banyak atribut atau menggunakan operator matematik dalam fungsi ukuran anda.</span><span class="sxs-lookup"><span data-stu-id="eee2c-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Cipta ukuran rumit dengan operator matematik.":::

1. <span data-ttu-id="eee2c-142">Untuk menambah penapis, pilih **Penapis** dalam kawasan konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="eee2c-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="eee2c-143">Dalam bahagian **Tambah atribut** anak tetingkap **Penapis**, pilih atribut yang mahu anda gunakan untuk mencipta penapis.</span><span class="sxs-lookup"><span data-stu-id="eee2c-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="eee2c-144">Tetapkan operator penapis untuk mentakrifkan penapis bagi setiap atribut yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="eee2c-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="eee2c-145">Pilih **Gunakan** untuk menambah penapis terpilih pada ukuran.</span><span class="sxs-lookup"><span data-stu-id="eee2c-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="eee2c-146">Untuk menambah dimensi pilih **Dimensi** dalam kawasan konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="eee2c-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="eee2c-147">Dimensi akan ditunjukkan sebagai lajur dalam mengukur entiti output.</span><span class="sxs-lookup"><span data-stu-id="eee2c-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="eee2c-148">Pilih **Edit dimensi** untuk menambah atribut data yang anda mahu kumpulkan nilai ukuran.</span><span class="sxs-lookup"><span data-stu-id="eee2c-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="eee2c-149">Sebagai contoh, bandar atau jantina.</span><span class="sxs-lookup"><span data-stu-id="eee2c-149">For example, city or gender.</span></span> <span data-ttu-id="eee2c-150">Secara lalai, dimensi *CustomerID* dipilih untuk mencipta *ukuran peringkat pelanggan*.</span><span class="sxs-lookup"><span data-stu-id="eee2c-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="eee2c-151">Anda boleh mengalih keluar dimensi lalai jika anda mahu mencipta *ukuran peringkat perniagaan*.</span><span class="sxs-lookup"><span data-stu-id="eee2c-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="eee2c-152">Pilih **Selesai** untuk menambah dimensi pada ukuran.</span><span class="sxs-lookup"><span data-stu-id="eee2c-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="eee2c-153">Jika terdapat nilai dalam data anda yang perlu anda gantikan dengan integer—contohnya, gantikan *nol* dengan *0*—pilih **Peraturan**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="eee2c-154">Konfigurasikan peraturan dan pastikan anda memilih hanya nombor keseluruhan sebagai pengganti.</span><span class="sxs-lookup"><span data-stu-id="eee2c-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="eee2c-155">Jika terdapat berbilang laluan antara entiti data yang anda petakan dengan entiti *Pelanggan*, anda perlu memilih salah satu daripada [laluan perhubungan entiti](relationships.md) yang dikenal pasti.</span><span class="sxs-lookup"><span data-stu-id="eee2c-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="eee2c-156">Hasil ukuran mungkin berbeza-beza bergantung pada laluan yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="eee2c-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="eee2c-157">Pilih **Keutamaan data** dan pilih laluan entiti yang sepatutnya boleh digunakan untuk mengenal pasti langkah anda.</span><span class="sxs-lookup"><span data-stu-id="eee2c-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="eee2c-158">Jika hanya terdapat laluan tunggal kepada entiti *Pelanggan*, kawalan ini tidak akan ditunjukkan.</span><span class="sxs-lookup"><span data-stu-id="eee2c-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="eee2c-159">Pilih **Selesai** untuk menggunakan pilihan anda.</span><span class="sxs-lookup"><span data-stu-id="eee2c-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pilih laluan entiti untuk ukuran.":::

1. <span data-ttu-id="eee2c-161">Untuk menambah lebih banyak pengiraan untuk ukuran, pilih **Pengiraan baharu**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="eee2c-162">Anda hanya boleh menggunakan entiti pada laluan entiti yang sama untuk pengiraan baharu.</span><span class="sxs-lookup"><span data-stu-id="eee2c-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="eee2c-163">Lebih banyak pengiraan akan ditunjukkan sebagai lajur baharu dalam mengukur entiti output.</span><span class="sxs-lookup"><span data-stu-id="eee2c-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="eee2c-164">Pilih **...** pada pengiraan untuk **Duplikasi**, **Nama semula** atau **Alih keluar** pengiraan daripada ukuran.</span><span class="sxs-lookup"><span data-stu-id="eee2c-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="eee2c-165">Dalam kawasan **Pratonton**, anda akan melihat skema data bagi entiti output ukuran, termasuk penapis dan dimensi.</span><span class="sxs-lookup"><span data-stu-id="eee2c-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="eee2c-166">Pratonton bertindak balas secara dinamik kepada perubahan dalam konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="eee2c-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="eee2c-167">Pilih **Jalankan** untuk mengira hasil bagi langkah yang dikonfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="eee2c-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="eee2c-168">Pilih **Simpan dan tutup** jika anda mahu menyimpan konfigurasi semasa dan jalankan ukuran kemudian.</span><span class="sxs-lookup"><span data-stu-id="eee2c-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="eee2c-169">Pergi ke **Langkah** untuk melihat langkah yang baharu dicipta dalam senarai.</span><span class="sxs-lookup"><span data-stu-id="eee2c-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="eee2c-170">Gunakan templat untuk membina langkah</span><span class="sxs-lookup"><span data-stu-id="eee2c-170">Use a template to build a measure</span></span>

<span data-ttu-id="eee2c-171">Anda boleh menggunakan templat pratakrif untuk langkah yang biasa digunakan untuk menciptanya.</span><span class="sxs-lookup"><span data-stu-id="eee2c-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="eee2c-172">Penerangan terperinci mengenai templat dan pengalaman berpandu membantu anda dengan penciptaan langkah yang cekap.</span><span class="sxs-lookup"><span data-stu-id="eee2c-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="eee2c-173">Templat dibina pada data yang dipetakan daripada entit *Aktiviti Disatukan*.</span><span class="sxs-lookup"><span data-stu-id="eee2c-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="eee2c-174">Oleh itu, pastikan anda telah mengkonfigurasikan [aktiviti pelanggan](activities.md) sebelum anda mencipta langkah daripada templat.</span><span class="sxs-lookup"><span data-stu-id="eee2c-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="eee2c-175">Templat langkah yang tersedia:</span><span class="sxs-lookup"><span data-stu-id="eee2c-175">Available measure templates:</span></span> 
- <span data-ttu-id="eee2c-176">Purata nilai transaksi (ATV)</span><span class="sxs-lookup"><span data-stu-id="eee2c-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="eee2c-177">Jumlah nilai transaksi</span><span class="sxs-lookup"><span data-stu-id="eee2c-177">Total transaction value</span></span>
- <span data-ttu-id="eee2c-178">Purata hasil harian</span><span class="sxs-lookup"><span data-stu-id="eee2c-178">Average daily revenue</span></span>
- <span data-ttu-id="eee2c-179">Purata hasil tahunan</span><span class="sxs-lookup"><span data-stu-id="eee2c-179">Average yearly revenue</span></span>
- <span data-ttu-id="eee2c-180">Kiraan transaksi</span><span class="sxs-lookup"><span data-stu-id="eee2c-180">Transaction count</span></span>
- <span data-ttu-id="eee2c-181">Mata kesetiaan diperoleh</span><span class="sxs-lookup"><span data-stu-id="eee2c-181">Loyalty points earned</span></span>
- <span data-ttu-id="eee2c-182">Mata kesetiaan ditebus</span><span class="sxs-lookup"><span data-stu-id="eee2c-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="eee2c-183">Baki mata kesetiaan</span><span class="sxs-lookup"><span data-stu-id="eee2c-183">Loyalty points balance</span></span>
- <span data-ttu-id="eee2c-184">Jangka hayat pelanggan aktif</span><span class="sxs-lookup"><span data-stu-id="eee2c-184">Active customer lifespan</span></span>
- <span data-ttu-id="eee2c-185">Tempoh keahlian kesetiaan</span><span class="sxs-lookup"><span data-stu-id="eee2c-185">Loyalty membership duration</span></span>
- <span data-ttu-id="eee2c-186">Masa sejak pembelian terakhir</span><span class="sxs-lookup"><span data-stu-id="eee2c-186">Time since last purchase</span></span>

<span data-ttu-id="eee2c-187">Prosedur berikut menggariskan langkah untuk membina langkah baharu menggunakan templat.</span><span class="sxs-lookup"><span data-stu-id="eee2c-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="eee2c-188">Dalam wawasan khalayak, pergi ke **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="eee2c-189">Pilih **Baharu** dan pilih **Pilih templat**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Syot layar menu juntai bawah apabila mencipta ukuran baharu dengan serlahkan pada templat.":::

1. <span data-ttu-id="eee2c-191">Cari templat yang sesuai dengan keperluan anda dan pilih **Pilih templat**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="eee2c-192">Semak data yang diperlukan dan pilih **Mari bermula** jika anda mempunyai semua data di tempatnya.</span><span class="sxs-lookup"><span data-stu-id="eee2c-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="eee2c-193">Dalam anak tetingkap **Edit nama**, tetapkan nama untuk langkah anda dan entiti output.</span><span class="sxs-lookup"><span data-stu-id="eee2c-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="eee2c-194">Pilih **Selesai**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-194">Select **Done**.</span></span>

1. <span data-ttu-id="eee2c-195">Dalam bahagian **Tetapkan tempoh masa**, takrifkan tempoh masa data untuk digunakan.</span><span class="sxs-lookup"><span data-stu-id="eee2c-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="eee2c-196">Pilih jika anda mahu ukuran baharu untuk merangkumi keseluruhan set data dengan memilih **Sepanjang masa**, atau jika anda mahu ukuran itu memberikan tumpuan kepada **Tempoh masa tertentu**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Tangkapan skrin menunjukkan bahagian tempoh masa apabila mengkonfigurasikan langkah daripada templat.":::

1. <span data-ttu-id="eee2c-198">Dalam bahagian seterusnya, pilih **Tambah data** untuk memilih aktiviti dan memetakan data yang sepadan daripada entiti *Aktiviti Disatukan* anda.</span><span class="sxs-lookup"><span data-stu-id="eee2c-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="eee2c-199">Langkah 1 daripada 2: Di bawah **Jenis aktiviti**, pilih jenis entiti yang anda mahu gunakan.</span><span class="sxs-lookup"><span data-stu-id="eee2c-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="eee2c-200">Untuk **Aktiviti**, pilih entiti yang anda mahu petakan.</span><span class="sxs-lookup"><span data-stu-id="eee2c-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="eee2c-201">Langkah 2 daripada 2: Pilih atribut daripada entiti *Aktiviti Disatukan* untuk komponen yang diperlukan oleh formula.</span><span class="sxs-lookup"><span data-stu-id="eee2c-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="eee2c-202">Contohnya, untuk nilai transaksi Purata, ia merupakan atribut yang mewakili nilai Transaksi.</span><span class="sxs-lookup"><span data-stu-id="eee2c-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="eee2c-203">Untuk **Cap waktu aktiviti**, pilih atribut daripada entiti Aktiviti Disatukan yang mewakili tarikh dan masa aktiviti.</span><span class="sxs-lookup"><span data-stu-id="eee2c-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="eee2c-204">Sebaik sahaja pemetaan data berjaya, anda boleh melihat status sebagai **Lengkap** dan nama aktiviti dan atribut yang dipetakan.</span><span class="sxs-lookup"><span data-stu-id="eee2c-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Tangkapan skrin konfigurasi templat langkah yang lengkap.":::

1. <span data-ttu-id="eee2c-206">Anda kini boleh memilih **Jalankan** untuk mengira keputusan ukuran.</span><span class="sxs-lookup"><span data-stu-id="eee2c-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="eee2c-207">Untuk memperhalusi kemudian, pilih **Simpan draf**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="eee2c-208">Urus tindakan anda</span><span class="sxs-lookup"><span data-stu-id="eee2c-208">Manage your measures</span></span>

<span data-ttu-id="eee2c-209">Anda boleh mendapatkan senarai langkah pada halaman **Langkah**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="eee2c-210">Anda akan menemui maklumat tentang jenis ukuran, pencipta, tarikh penciptaan, status dan keadaan.</span><span class="sxs-lookup"><span data-stu-id="eee2c-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="eee2c-211">Apabila anda memilih ukuran daripada senarai, anda boleh pratonton output dan memuat turun fail CSV.</span><span class="sxs-lookup"><span data-stu-id="eee2c-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="eee2c-212">Untuk menyegarkan semula semua tindakan pada masa yang sama, pilih **Segar semula semua** tanpa memilih tindakan khusus.</span><span class="sxs-lookup"><span data-stu-id="eee2c-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="eee2c-213">![Tindakan untuk menguruskan langkah tunggal.](media/measure-actions.png "Tindakan untuk menguruskan langkah tunggal.")</span><span class="sxs-lookup"><span data-stu-id="eee2c-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="eee2c-214">Pilih ukuran daripada senarai untuk pilihan berikut:</span><span class="sxs-lookup"><span data-stu-id="eee2c-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="eee2c-215">Pilih nama langkah untuk melihat butiran.</span><span class="sxs-lookup"><span data-stu-id="eee2c-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="eee2c-216">**Edit** konfigurasi langkah.</span><span class="sxs-lookup"><span data-stu-id="eee2c-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="eee2c-217">**Segar semula** ukuran berdasarkan data terkini.</span><span class="sxs-lookup"><span data-stu-id="eee2c-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="eee2c-218">**Nama semula** langkah.</span><span class="sxs-lookup"><span data-stu-id="eee2c-218">**Rename** the measure.</span></span>
- <span data-ttu-id="eee2c-219">**Padam** langkah.</span><span class="sxs-lookup"><span data-stu-id="eee2c-219">**Delete** the measure.</span></span>
- <span data-ttu-id="eee2c-220">**Aktifkan** atau **Nyahaktifkan**.</span><span class="sxs-lookup"><span data-stu-id="eee2c-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="eee2c-221">Langkah tidak aktif tidak akan dapat disegar semula semasa [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eee2c-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="eee2c-222">Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="eee2c-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="eee2c-223">Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="eee2c-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="eee2c-224">Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja.</span><span class="sxs-lookup"><span data-stu-id="eee2c-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="eee2c-225">Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda akan menemukan maklumat tambahan: masa pemprosesan, tarikh pemprosesan terakhir serta semua ralat dan amaran yang berkaitan dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="eee2c-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="eee2c-226">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="eee2c-226">Next step</span></span>

<span data-ttu-id="eee2c-227">Anda boleh menggunakan langkah sedia ada untuk mencipta [segmen pelanggan](segments.md).</span><span class="sxs-lookup"><span data-stu-id="eee2c-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
