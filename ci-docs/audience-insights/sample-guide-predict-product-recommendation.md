---
title: Panduan sampel ramalan pengesyoran produk
description: Gunakan panduan sampel ini untuk mencuba model ramalan pengesyoran produk di luar kotak.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270516"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="813f8-103">Panduan sampel untuk ramalan pengesyoran produk (pratonton)</span><span class="sxs-lookup"><span data-stu-id="813f8-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="813f8-104">Kami akan menerangkan kepada anda contoh ramalan pengesyoran produk hujung ke hujung menggunakan data sampel yang diberikan di bawah.</span><span class="sxs-lookup"><span data-stu-id="813f8-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="813f8-105">Senario</span><span class="sxs-lookup"><span data-stu-id="813f8-105">Scenario</span></span>

<span data-ttu-id="813f8-106">Contoso ialah sebuah syarikat yang menghasilkan mesin kopi dan kopi berkualiti tinggi, yang mereka jual melalui laman web Contoso Coffee mereka.</span><span class="sxs-lookup"><span data-stu-id="813f8-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="813f8-107">Matlamat mereka ialah untuk memahami produk yang sepatutnya mereka syorkan kepada pelanggan berulang mereka.</span><span class="sxs-lookup"><span data-stu-id="813f8-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="813f8-108">Mengetahui perkara yang pelanggan lebih **mungkin akan membeli**, boleh membantu mereka menyimpan usaha pemasaran dengan menumpukan perhatian kepada perkara tertentu.</span><span class="sxs-lookup"><span data-stu-id="813f8-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="813f8-109">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="813f8-109">Prerequisites</span></span>

- <span data-ttu-id="813f8-110">Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="813f8-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="813f8-111">Kami mengesyorkan agar anda melaksanakan langkah berikut [dalam persekitaran baharu](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="813f8-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="813f8-112">Tugas 1 - Inges data</span><span class="sxs-lookup"><span data-stu-id="813f8-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="813f8-113">Semak semula artikel [tentang pengingesan data](data-sources.md) dan [mengimport sumber data menggunakan penyambung Power Query](connect-power-query.md) secara khusus.</span><span class="sxs-lookup"><span data-stu-id="813f8-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="813f8-114">Maklumat berikut menganggap anda membiasakan diri dengan pengingesan data secara umum.</span><span class="sxs-lookup"><span data-stu-id="813f8-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="813f8-115">Inges data pelanggan daripada platform e-Dagang</span><span class="sxs-lookup"><span data-stu-id="813f8-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="813f8-116">Cipta sumber data bernama **e-Dagang**, pilih pilihan import dan pilih penyambung **Teks/CSV**.</span><span class="sxs-lookup"><span data-stu-id="813f8-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="813f8-117">Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="813f8-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="813f8-118">Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="813f8-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="813f8-119">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="813f8-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="813f8-120">**DateOfBirth**: Tarikh</span><span class="sxs-lookup"><span data-stu-id="813f8-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="813f8-121">**CreatedOn**: Zon waktu tarikh</span><span class="sxs-lookup"><span data-stu-id="813f8-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tarikh lahir kepada tarikh ini.":::

5. <span data-ttu-id="813f8-123">Dalam medan 'Nama' pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="813f8-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="813f8-124">**Simpan** sumber data.</span><span class="sxs-lookup"><span data-stu-id="813f8-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="813f8-125">Inges data pembelian dalam talian</span><span class="sxs-lookup"><span data-stu-id="813f8-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="813f8-126">Tambahkan set data lain pada sumber data **e-Dagang** yang sama.</span><span class="sxs-lookup"><span data-stu-id="813f8-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="813f8-127">Pilih penyambung **Teks/CSV** semula.</span><span class="sxs-lookup"><span data-stu-id="813f8-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="813f8-128">Masukkan URL untuk data **Pembelian Dalam Talian** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="813f8-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="813f8-129">Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="813f8-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="813f8-130">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="813f8-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="813f8-131">**PurchasedOn** : Tarikh/Masa</span><span class="sxs-lookup"><span data-stu-id="813f8-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="813f8-132">**TotalPrice** : Mata Wang</span><span class="sxs-lookup"><span data-stu-id="813f8-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="813f8-133">Dalam medan **Nama** pada anak tetingkap sisi, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="813f8-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="813f8-134">Simpan sumber data.</span><span class="sxs-lookup"><span data-stu-id="813f8-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="813f8-135">Ingest data pelanggan daripada skema kesetiaan</span><span class="sxs-lookup"><span data-stu-id="813f8-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="813f8-136">Cipta sumber data bernama **LoyaltyScheme**, pilih pilihan import dan pilih penyambung **Teks/CSV**.</span><span class="sxs-lookup"><span data-stu-id="813f8-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="813f8-137">Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="813f8-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="813f8-138">Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="813f8-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="813f8-139">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="813f8-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="813f8-140">**DateOfBirth**: Tarikh</span><span class="sxs-lookup"><span data-stu-id="813f8-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="813f8-141">**RewardsPoints**: Nombor Bulat</span><span class="sxs-lookup"><span data-stu-id="813f8-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="813f8-142">**CreatedOn**: Tarikh/Masa</span><span class="sxs-lookup"><span data-stu-id="813f8-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="813f8-143">Dalam medan **Nama** pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="813f8-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="813f8-144">Simpan sumber data.</span><span class="sxs-lookup"><span data-stu-id="813f8-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="813f8-145">Tugas 2 - Penyatuan data</span><span class="sxs-lookup"><span data-stu-id="813f8-145">Task 2 - Data unification</span></span>

<span data-ttu-id="813f8-146">Selepas menginges data, kini kita memulakan proses **Petaan, Padanan, Gabungan** untuk mencipta profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="813f8-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="813f8-147">Untuk mendapatkan maklumat lanjut, lihat [Penyatuan data](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="813f8-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="813f8-148">Petakan</span><span class="sxs-lookup"><span data-stu-id="813f8-148">Map</span></span>

1. <span data-ttu-id="813f8-149">Selepas menginges data, petakan kenalan daripada data e-Dagang dan Kesetiaan kepada jenis data umum.</span><span class="sxs-lookup"><span data-stu-id="813f8-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="813f8-150">Pergi ke **Data** > **Satukan** > **Peta**.</span><span class="sxs-lookup"><span data-stu-id="813f8-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="813f8-151">Pilih entiti yang mewakili profil pelanggan – **eCommerceContacts** dan **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="813f8-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![menyatukan sumber data e-Dagang dan kesetiaan.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="813f8-153">Pilih **ContactId** sebagai kunci utama untuk **eCommerceContacts** dan **LoyaltyID** sebagai kunci utama untuk **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="813f8-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Menyatukan LoyaltyId sebagai kunci utama.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="813f8-155">Padankan</span><span class="sxs-lookup"><span data-stu-id="813f8-155">Match</span></span>

1. <span data-ttu-id="813f8-156">Pergi ke tab **Padanan** dan pilih **Tetapkan Urutan**.</span><span class="sxs-lookup"><span data-stu-id="813f8-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="813f8-157">Dalam senarai juntai bawah **Utama**, pilih **eCommerceContacts : e-Dagang** sebagai sumber utama dan menyertakan semua rekod.</span><span class="sxs-lookup"><span data-stu-id="813f8-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="813f8-158">Dalam senarai juntai bawah **Entiti 2**, pilih **loyCustomers : LoyaltyScheme** dan menyertakan semua rekod.</span><span class="sxs-lookup"><span data-stu-id="813f8-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Menyatukan padanan e-Dagang dan Kesetiaan.](media/unify-match-order.png)

4. <span data-ttu-id="813f8-160">Pilih **Cipta peraturan baharu**</span><span class="sxs-lookup"><span data-stu-id="813f8-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="813f8-161">Tambah syarat pertama anda menggunakan FullName.</span><span class="sxs-lookup"><span data-stu-id="813f8-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="813f8-162">Untuk eCommerceContacts pilih **FullName** dalam senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="813f8-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="813f8-163">Untuk loyCustomers, pilih **FullName** dalam senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="813f8-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="813f8-164">Pilih senarai juntai bawah **Menormalkan** dan pilih **Jenis (Telefon, Nama, Alamat, ...)**.</span><span class="sxs-lookup"><span data-stu-id="813f8-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="813f8-165">Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.</span><span class="sxs-lookup"><span data-stu-id="813f8-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="813f8-166">Masukkan nama **FullName, Email** untuk peraturan baharu.</span><span class="sxs-lookup"><span data-stu-id="813f8-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="813f8-167">Tambah syarat kedua untuk alamat e-mel dengan memilih **Tambah Syarat**</span><span class="sxs-lookup"><span data-stu-id="813f8-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="813f8-168">Untuk entiti eCommerceContacts, pilih **EMail** dalam senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="813f8-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="813f8-169">Untuk entiti loyCustomers, pilih **EMail** dalam senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="813f8-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="813f8-170">Biarkan Menormalkan kosong.</span><span class="sxs-lookup"><span data-stu-id="813f8-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="813f8-171">Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.</span><span class="sxs-lookup"><span data-stu-id="813f8-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Menyatukan peraturan padanan untuk nama dan e-mel.](media/unify-match-rule.png)

7. <span data-ttu-id="813f8-173">Pilih **Simpan** dan **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="813f8-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="813f8-174">Gabungkan</span><span class="sxs-lookup"><span data-stu-id="813f8-174">Merge</span></span>

1. <span data-ttu-id="813f8-175">Pergi ke tab **Gabungan**.</span><span class="sxs-lookup"><span data-stu-id="813f8-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="813f8-176">Pada **ContactId** untuk entiti **loyCustomers**, tukar nama paparan kepada **ContactIdLOYALTY** untuk membezakannya daripada ID lain yang diinges.</span><span class="sxs-lookup"><span data-stu-id="813f8-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![namakan semula contactid daripada ID kesetiaan.](media/unify-merge-contactid.png)

1. <span data-ttu-id="813f8-178">Pilih **Simpan** dan **Jalankan** untuk memulakan Proses Gabungan.</span><span class="sxs-lookup"><span data-stu-id="813f8-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="813f8-179">Tugas 3 - Mengkonfigurasikan ramalan pengesyoran produk</span><span class="sxs-lookup"><span data-stu-id="813f8-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="813f8-180">Dengan adanya profil pelanggan disatukan, kini kami dapat menjalankan ramalan pulangan langganan.</span><span class="sxs-lookup"><span data-stu-id="813f8-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="813f8-181">Pergi ke **Kecerdasan** > **Ramalan** pilih **Pengesyoran produk**.</span><span class="sxs-lookup"><span data-stu-id="813f8-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="813f8-182">Pilih **Mulakan**.</span><span class="sxs-lookup"><span data-stu-id="813f8-182">Select **Get started**.</span></span>

1. <span data-ttu-id="813f8-183">Namakan model **Ramalan Model Pengesyoran Produk OOB** dan entiti output **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="813f8-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="813f8-184">Takrifkan tiga syarat untuk model:</span><span class="sxs-lookup"><span data-stu-id="813f8-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="813f8-185">**Bilangan produk**: Tetapkan nilai ini kepada **5**.</span><span class="sxs-lookup"><span data-stu-id="813f8-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="813f8-186">Tetapan ini mentakrifkan bilangan produk yang anda mahu cadangkan kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="813f8-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="813f8-187">**Cadangkan pelanggan produk yang dibeli baru-baru ini?**: Pilih **Ya** untuk menunjukkan bahawa anda mahu sertakan produk dalam pengesyoran yang pelanggan anda telah beli sebelum ini.</span><span class="sxs-lookup"><span data-stu-id="813f8-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="813f8-188">**Tetingkap lihat kembali:** Pilih sekurang-kurangnya **365 hari**.</span><span class="sxs-lookup"><span data-stu-id="813f8-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="813f8-189">Tetapan ini menakrifkan sejauh mana model akan melihat kembali pada aktiviti pelanggan untuk menggunakannya sebagai input kepada pengesyoran mereka.</span><span class="sxs-lookup"><span data-stu-id="813f8-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Keutaaman model untuk model pengesyoran produk.":::

1. <span data-ttu-id="813f8-191">Pilih **Data yang diperlukan** dan pilih **Tambah data** untuk sejarah pembelian.</span><span class="sxs-lookup"><span data-stu-id="813f8-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="813f8-192">Tambah entiti **eCommercePurchases : e-Dagang** dan petakan medan daripada e-Dagang kepada medan berkaitan yang diperlukan oleh model.</span><span class="sxs-lookup"><span data-stu-id="813f8-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="813f8-193">Sertai entiti **eCommercePurchases : e-Dagang** dengan **eCommerceContacts : e-Dagang**.</span><span class="sxs-lookup"><span data-stu-id="813f8-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Sertai entiti e-Dagang.](media/model-purchase-join.png)

1. <span data-ttu-id="813f8-195">Pilih **Seterusnya** untuk menetapkan jadual model.</span><span class="sxs-lookup"><span data-stu-id="813f8-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="813f8-196">Model perlu dilatih secara tetap untuk belajar pola baharu apabila terdapat data baharu yang diinges.</span><span class="sxs-lookup"><span data-stu-id="813f8-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="813f8-197">Untuk contoh ini, pilih **Bulanan**.</span><span class="sxs-lookup"><span data-stu-id="813f8-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="813f8-198">Selepas menyemak semula semua butiran, pilih **Simpan dan Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="813f8-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="813f8-199">Tugas 4 - Semak semula hasil dan penerangan model</span><span class="sxs-lookup"><span data-stu-id="813f8-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="813f8-200">Biarkan model melengkapkan latihan dan pemarkahan data.</span><span class="sxs-lookup"><span data-stu-id="813f8-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="813f8-201">Anda kini boleh menyemak penerangan model pengesyoran pelanggan.</span><span class="sxs-lookup"><span data-stu-id="813f8-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="813f8-202">Untuk mendapatkan maklumat lanjut, lihat [Semak semula status dan keputusan ramalan](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="813f8-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="813f8-203">Tugas 5 - Cipta segmen produk yang dibeli tinggi</span><span class="sxs-lookup"><span data-stu-id="813f8-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="813f8-204">Menjalankan model pengeluaran mewujudkan entiti baharu yang anda boleh lihat dalam **Data** > **Entiti**.</span><span class="sxs-lookup"><span data-stu-id="813f8-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="813f8-205">Anda boleh mencipta segmen baharu berdasarkan entiti yang dicipta oleh model.</span><span class="sxs-lookup"><span data-stu-id="813f8-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="813f8-206">Pergi ke **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="813f8-206">Go to **Segments**.</span></span> <span data-ttu-id="813f8-207">Pilih **Baharu** dan pilih **Cipta daripada** > **Kecerdasan**.</span><span class="sxs-lookup"><span data-stu-id="813f8-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Mencipta segmen dengan output model.](media/segment-intelligence.png)

1. <span data-ttu-id="813f8-209">Pilih titik tamat **OOBProductRecommendationModelPrediction** dan takrifkan segmen:</span><span class="sxs-lookup"><span data-stu-id="813f8-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="813f8-210">Medan: ProductID</span><span class="sxs-lookup"><span data-stu-id="813f8-210">Field: ProductID</span></span>
   - <span data-ttu-id="813f8-211">Operatori: Nilai</span><span class="sxs-lookup"><span data-stu-id="813f8-211">Operator: Value</span></span>
   - <span data-ttu-id="813f8-212">Nilai: Pilih tiga ID produk teratas</span><span class="sxs-lookup"><span data-stu-id="813f8-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Cipta segmen daripada hasil model.":::

<span data-ttu-id="813f8-214">Anda kini mempunyai segmen yang secara dinamik dikemas kini yang mengenal pasti pelanggan yang lebih bersedia untuk membeli tiga produk paling disyorkan</span><span class="sxs-lookup"><span data-stu-id="813f8-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="813f8-215">Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).</span><span class="sxs-lookup"><span data-stu-id="813f8-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]