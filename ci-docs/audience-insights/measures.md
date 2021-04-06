---
title: Cipta dan urus tindakan
description: Takrifkan ukuran untuk menganalisis dan mencerminkan prestasi perniagaan anda.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654743"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="45243-103">Takrifkan dan urus tindakan</span><span class="sxs-lookup"><span data-stu-id="45243-103">Define and manage measures</span></span>

<span data-ttu-id="45243-104">Ukuran membantu anda untuk lebih memahami tingkah laku pelanggan dan prestasi perniagaan dengan mendapatkan nilai yang relevan dari [profil disatukan](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="45243-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="45243-105">Contohnya, sebuah perniagaan ingin melihat *jumlah perbelanjaan setiap pelanggan* untuk memahami sejarah pembelian pelanggan individu.</span><span class="sxs-lookup"><span data-stu-id="45243-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="45243-106">Atau ukuran *jumlah jualan keseluruhan syarikat* untuk memahami perolehan peringkat agregat dalam keseluruhan perniagaan.</span><span class="sxs-lookup"><span data-stu-id="45243-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="45243-107">Ukuran dicipta menggunakan pembina ukuran, platform pertanyaan data dengan pelbagai pengendali dan pilihan pemetaan yang mudah.</span><span class="sxs-lookup"><span data-stu-id="45243-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="45243-108">Ia membolehkan anda menapis data, mengumpulkan hasil, mengesan [laluan perhubungan entiti](relationships.md) dan pratonton output.</span><span class="sxs-lookup"><span data-stu-id="45243-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="45243-109">Gunakan pembina ukuran untuk merancang aktiviti perniagaan dengan bertanya pada data pelanggan dan mendapatkan wawasan.</span><span class="sxs-lookup"><span data-stu-id="45243-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="45243-110">Sebagai contoh, mencipta ukuran *jumlah perbelanjaan setiap pelanggan* dan *jumlah pulangan setiap pelanggan* membantu mengenal pasti kumpulan pelanggan yang mempunyai perbelanjaan tinggi tetapi pulangan tinggi.</span><span class="sxs-lookup"><span data-stu-id="45243-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="45243-111">Anda boleh [mencipta segmen](segments.md) untuk memacu tindakan terbaik seterusnya.</span><span class="sxs-lookup"><span data-stu-id="45243-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="45243-112">Cipta ukuran</span><span class="sxs-lookup"><span data-stu-id="45243-112">Create a measure</span></span>

<span data-ttu-id="45243-113">Bahagian ini membimbing anda mencipta ukuran baharu dari awal.</span><span class="sxs-lookup"><span data-stu-id="45243-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="45243-114">Anda boleh membina ukuran dengan atribut data daripada entiti data yang mempunyai persediaan untuk berhubung dengan entiti Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="45243-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="45243-115">Dalam wawasan khalayak, pergi ke **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="45243-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="45243-116">Pilih **Baharu**.</span><span class="sxs-lookup"><span data-stu-id="45243-116">Select **New**.</span></span>

1. <span data-ttu-id="45243-117">Pilih **Edit nama** dan berikan **Nama** untuk langkah itu.</span><span class="sxs-lookup"><span data-stu-id="45243-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="45243-118">Jika konfigurasi ukuran baharu anda hanya mempunyai dua medan, sebagai contog, CustomerID dan satu pengiraan, output akan ditambah sebagai lajur baharu kepada entiti yang dijana oleh sistem yang dipanggil Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="45243-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="45243-119">Dan anda akan dapat melihat nilai ukuran dalam profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="45243-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="45243-120">Ukuran lain akan menjana entiti mereka sendiri.</span><span class="sxs-lookup"><span data-stu-id="45243-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="45243-121">Dalam kawasan konfigurasi, pilih fungsi pengagregatan daripada menu ke bawah **Pilih Fungsi**.</span><span class="sxs-lookup"><span data-stu-id="45243-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="45243-122">Fungsi pengagregatan termasuk:</span><span class="sxs-lookup"><span data-stu-id="45243-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="45243-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="45243-123">**Sum**</span></span>
   - <span data-ttu-id="45243-124">**Purata**</span><span class="sxs-lookup"><span data-stu-id="45243-124">**Average**</span></span>
   - <span data-ttu-id="45243-125">**Bilangan**</span><span class="sxs-lookup"><span data-stu-id="45243-125">**Count**</span></span>
   - <span data-ttu-id="45243-126">**Kira Unik**</span><span class="sxs-lookup"><span data-stu-id="45243-126">**Count Unique**</span></span>
   - <span data-ttu-id="45243-127">**Maksimum**</span><span class="sxs-lookup"><span data-stu-id="45243-127">**Max**</span></span>
   - <span data-ttu-id="45243-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="45243-128">**Min**</span></span>
   - <span data-ttu-id="45243-129">**Pertama**: mengambil kira nilai pertama bagi rekod data</span><span class="sxs-lookup"><span data-stu-id="45243-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="45243-130">**Terakhir**: ambil nilai terakhir yang ditambah ke rekod data</span><span class="sxs-lookup"><span data-stu-id="45243-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operator untuk mengukur pengiraan.":::

1. <span data-ttu-id="45243-132">Pilih **Tambah atribut** untuk memilih data yang anda perlukan untuk mencipta ukuran ini.</span><span class="sxs-lookup"><span data-stu-id="45243-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="45243-133">Pilih tab **Atribut**.</span><span class="sxs-lookup"><span data-stu-id="45243-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="45243-134">Entiti data: Pilih entiti yang termasuk atribut yang anda mahu ukur.</span><span class="sxs-lookup"><span data-stu-id="45243-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="45243-135">Atribut data: Pilih atribut yang anda mahu gunakan dalam fungsi pengagregatan untuk mengira ukuran.</span><span class="sxs-lookup"><span data-stu-id="45243-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="45243-136">Anda hanya boleh memilih satu atribut pada satu masa.</span><span class="sxs-lookup"><span data-stu-id="45243-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="45243-137">Anda juga boleh memilih atribut data daripada ukuran sedia ada dengan memilih tab **Ukuran**. Atau, anda boleh mencari nama entiti atau ukuran.</span><span class="sxs-lookup"><span data-stu-id="45243-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="45243-138">Pilih **Tambah** untuk menambah atribut terpilih pada ukuran.</span><span class="sxs-lookup"><span data-stu-id="45243-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Pilih atribut untuk digunakan dalam pengiraan.":::

1. <span data-ttu-id="45243-140">Untuk membina lebih banyak ukuran rumit, anda boleh menambah lebih banyak atribut atau menggunakan operator matematik dalam fungsi ukuran anda.</span><span class="sxs-lookup"><span data-stu-id="45243-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Cipta ukuran rumit dengan operator matematik.":::

1. <span data-ttu-id="45243-142">Untuk menambah penapis, pilih **Penapis** dalam kawasan konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="45243-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="45243-143">Dalam bahagian **Tambah atribut** bagi anak tetingkap **Penapis**, pilih atribut yang anda mahu gunakan untuk mencipta penapis.</span><span class="sxs-lookup"><span data-stu-id="45243-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="45243-144">Tetapkan operator penapis untuk mentakrifkan penapis bagi setiap atribut yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="45243-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="45243-145">Pilih **Gunakan** untuk menambah penapis terpilih pada ukuran.</span><span class="sxs-lookup"><span data-stu-id="45243-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="45243-146">Untuk menambah dimensi pilih **Dimensi** dalam kawasan konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="45243-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="45243-147">Dimensi akan ditunjukkan sebagai lajur dalam mengukur entiti output.</span><span class="sxs-lookup"><span data-stu-id="45243-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="45243-148">Pilih **Edit dimensi** untuk menambah atribut data yang anda mahu kumpulkan nilai ukuran.</span><span class="sxs-lookup"><span data-stu-id="45243-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="45243-149">Sebagai contoh, bandar atau jantina.</span><span class="sxs-lookup"><span data-stu-id="45243-149">For example, city or gender.</span></span> <span data-ttu-id="45243-150">Secara lalai, dimensi *CustomerID* dipilih untuk mencipta *ukuran peringkat pelanggan*.</span><span class="sxs-lookup"><span data-stu-id="45243-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="45243-151">Anda boleh mengalih keluar dimensi lalai jika anda mahu mencipta *ukuran peringkat perniagaan*.</span><span class="sxs-lookup"><span data-stu-id="45243-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="45243-152">Pilih **Selesai** untuk menambah dimensi pada ukuran.</span><span class="sxs-lookup"><span data-stu-id="45243-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="45243-153">Jika terdapat berbilang laluan antara entiti data yang anda petakan dengan entiti *Pelanggan*, anda perlu memilih salah satu daripada [laluan perhubungan entiti](relationships.md) yang dikenal pasti.</span><span class="sxs-lookup"><span data-stu-id="45243-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="45243-154">Hasil ukuran mungkin berbeza-beza bergantung pada laluan yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="45243-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="45243-155">Pilih **Keutamaan data** dan pilih laluan entiti yang sepatutnya boleh digunakan untuk mengenal pasti langkah anda.</span><span class="sxs-lookup"><span data-stu-id="45243-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="45243-156">Jika hanya terdapat laluan tunggal kepada entiti *Pelanggan*, kawalan ini tidak akan ditunjukkan.</span><span class="sxs-lookup"><span data-stu-id="45243-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="45243-157">Pilih **Selesai** untuk menggunakan pilihan anda.</span><span class="sxs-lookup"><span data-stu-id="45243-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pilih laluan entiti untuk ukuran.":::

1. <span data-ttu-id="45243-159">Untuk menambah lebih banyak pengiraan untuk ukuran, pilih **Pengiraan baharu**.</span><span class="sxs-lookup"><span data-stu-id="45243-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="45243-160">Anda hanya boleh menggunakan entiti pada laluan entiti yang sama untuk pengiraan baharu.</span><span class="sxs-lookup"><span data-stu-id="45243-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="45243-161">Lebih banyak pengiraan akan ditunjukkan sebagai lajur baharu dalam mengukur entiti output.</span><span class="sxs-lookup"><span data-stu-id="45243-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="45243-162">Pilih **...** pada pengiraan untuk **Duplikasi**, **Nama semula** atau **Alih keluar** pengiraan daripada ukuran.</span><span class="sxs-lookup"><span data-stu-id="45243-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="45243-163">Dalam kawasan **Pratonton**, anda akan melihat skema data bagi entiti output ukuran, termasuk penapis dan dimensi.</span><span class="sxs-lookup"><span data-stu-id="45243-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="45243-164">Pratonton bertindak balas secara dinamik kepada perubahan dalam konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="45243-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="45243-165">Pilih **Jalankan** untuk mengira hasil bagi langkah yang dikonfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="45243-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="45243-166">Pilih **Simpan dan tutup** jika anda mahu menyimpan konfigurasi semasa dan jalankan ukuran kemudian.</span><span class="sxs-lookup"><span data-stu-id="45243-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="45243-167">Pergi ke **Langkah** untuk melihat langkah yang baharu dicipta dalam senarai.</span><span class="sxs-lookup"><span data-stu-id="45243-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="45243-168">Urus tindakan anda</span><span class="sxs-lookup"><span data-stu-id="45243-168">Manage your measures</span></span>

<span data-ttu-id="45243-169">Selepas [mencipta ukuran](#create-a-measure), anda akan melihat senarai ukuran pada halaman **Langkah**.</span><span class="sxs-lookup"><span data-stu-id="45243-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="45243-170">Anda akan menemui maklumat tentang jenis ukuran, pencipta, tarikh penciptaan, status dan keadaan.</span><span class="sxs-lookup"><span data-stu-id="45243-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="45243-171">Apabila anda memilih ukuran daripada senarai, anda boleh pratonton output dan muat turun fail .CSV.</span><span class="sxs-lookup"><span data-stu-id="45243-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="45243-172">Untuk menyegarkan semula semua tindakan pada masa yang sama, pilih **Segar semula semua** tanpa memilih tindakan khusus.</span><span class="sxs-lookup"><span data-stu-id="45243-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="45243-173">![Tindakan untuk mengurus langkah tunggal](media/measure-actions.png "Tindakan untuk mengurus langkah tunggal")</span><span class="sxs-lookup"><span data-stu-id="45243-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="45243-174">Pilih ukuran daripada senarai untuk pilihan berikut:</span><span class="sxs-lookup"><span data-stu-id="45243-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="45243-175">Pilih nama langkah untuk melihat butiran.</span><span class="sxs-lookup"><span data-stu-id="45243-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="45243-176">**Edit** konfigurasi langkah.</span><span class="sxs-lookup"><span data-stu-id="45243-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="45243-177">**Segar semula** ukuran berdasarkan data terkini.</span><span class="sxs-lookup"><span data-stu-id="45243-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="45243-178">**Nama semula** langkah.</span><span class="sxs-lookup"><span data-stu-id="45243-178">**Rename** the measure.</span></span>
- <span data-ttu-id="45243-179">**Padam** langkah.</span><span class="sxs-lookup"><span data-stu-id="45243-179">**Delete** the measure.</span></span>
- <span data-ttu-id="45243-180">**Aktifkan** atau **Nyahaktifkan**.</span><span class="sxs-lookup"><span data-stu-id="45243-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="45243-181">Langkah tidak aktif tidak akan dapat disegar semula semasa [segar semula yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="45243-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="45243-182">Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="45243-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="45243-183">Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="45243-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="45243-184">Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja.</span><span class="sxs-lookup"><span data-stu-id="45243-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="45243-185">Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="45243-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="45243-186">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="45243-186">Next step</span></span>

<span data-ttu-id="45243-187">Anda boleh menggunakan ukuran sedia ada untuk mencipta [segmen pelanggan](segments.md).</span><span class="sxs-lookup"><span data-stu-id="45243-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]