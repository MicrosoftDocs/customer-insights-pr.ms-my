---
title: Panduan sampel ramalan nilai sepanjang hayat pelanggan
description: Gunakan panduan sampel ini untuk mencuba model ramalan nilai sepanjang hayat pelanggan.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129956"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="d17da-103">Panduan sampel ramalan nilai sepanjang hayat pelanggan (CLV)</span><span class="sxs-lookup"><span data-stu-id="d17da-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="d17da-104">Panduan ini akan menerangkan kepada anda contoh akhir ramalan nilai sepanjang hayat Pelanggan (CLV) dalam Customer Insights menggunakan data sampel.</span><span class="sxs-lookup"><span data-stu-id="d17da-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="d17da-105">Senario</span><span class="sxs-lookup"><span data-stu-id="d17da-105">Scenario</span></span>

<span data-ttu-id="d17da-106">Contoso ialah sebuah syarikat yang menghasilkan mesin kopi dan kopi berkualiti tinggi.</span><span class="sxs-lookup"><span data-stu-id="d17da-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="d17da-107">Mereka menjual produk melalui laman web Contoso Coffee mereka.</span><span class="sxs-lookup"><span data-stu-id="d17da-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="d17da-108">Syarikat ingin memahami nilai (hasil) yang boleh dijana oleh pelanggan mereka dalam tempoh 12 bulan akan datang.</span><span class="sxs-lookup"><span data-stu-id="d17da-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="d17da-109">Mengetahui nilai yang diharapkan pelanggan mereka dalam tempoh 12 bulan akan datang akan membantu mereka mengemudi usaha pemasaran mereka ke atas pelanggan bernilai tinggi.</span><span class="sxs-lookup"><span data-stu-id="d17da-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d17da-110">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="d17da-110">Prerequisites</span></span>

- <span data-ttu-id="d17da-111">Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam cerapan khalayak.</span><span class="sxs-lookup"><span data-stu-id="d17da-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="d17da-112">Kami mengesyorkan agar anda melaksanakan langkah berikut [dalam persekitaran baharu](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="d17da-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="d17da-113">Tugas 1 - Inges data</span><span class="sxs-lookup"><span data-stu-id="d17da-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="d17da-114">Semak artikel [tentang pengingesan data](data-sources.md) dan [mengimport sumber data menggunakan penyambung Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="d17da-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="d17da-115">Maklumat berikut menganggap anda membiasakan diri dengan pengingesan data secara umum.</span><span class="sxs-lookup"><span data-stu-id="d17da-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="d17da-116">Inges data pelanggan daripada platform e-Dagang</span><span class="sxs-lookup"><span data-stu-id="d17da-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="d17da-117">Cipta sumber data bernama **e-Dagang**, pilih pilihan import dan pilih penyambung **Teks/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d17da-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d17da-118">Masukkan URL untuk kenalan e-Dagang [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="d17da-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="d17da-119">Semasa mengedit data, pilih **Ubah** dan kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="d17da-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d17da-120">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="d17da-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="d17da-121">**DateOfBirth**: Tarikh</span><span class="sxs-lookup"><span data-stu-id="d17da-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="d17da-122">**CreatedOn**: Zon waktu tarikh</span><span class="sxs-lookup"><span data-stu-id="d17da-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tarikh lahir kepada tarikh ini.":::

1. <span data-ttu-id="d17da-124">Dalam medan 'Nama' pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="d17da-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="d17da-125">**Simpan** sumber data.</span><span class="sxs-lookup"><span data-stu-id="d17da-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="d17da-126">Inges data pembelian dalam talian</span><span class="sxs-lookup"><span data-stu-id="d17da-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="d17da-127">Tambahkan set data lain pada sumber data **e-Dagang** yang sama.</span><span class="sxs-lookup"><span data-stu-id="d17da-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="d17da-128">Pilih penyambung **Teks/CSV** semula.</span><span class="sxs-lookup"><span data-stu-id="d17da-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="d17da-129">Masukkan URL untuk data **Pembelian Dalam Talian** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="d17da-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="d17da-130">Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="d17da-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d17da-131">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="d17da-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="d17da-132">**PurchasedOn** : Tarikh/Masa</span><span class="sxs-lookup"><span data-stu-id="d17da-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="d17da-133">**TotalPrice** : Mata Wang</span><span class="sxs-lookup"><span data-stu-id="d17da-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="d17da-134">Dalam medan **Nama** pada anak tetingkap sisi, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="d17da-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="d17da-135">**Simpan** sumber data.</span><span class="sxs-lookup"><span data-stu-id="d17da-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="d17da-136">Ingest data pelanggan daripada skema kesetiaan</span><span class="sxs-lookup"><span data-stu-id="d17da-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="d17da-137">Cipta sumber data bernama **LoyaltyScheme**, pilih pilihan import dan pilih penyambung **Teks/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d17da-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d17da-138">Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="d17da-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="d17da-139">Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="d17da-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d17da-140">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="d17da-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="d17da-141">**DateOfBirth**: Tarikh</span><span class="sxs-lookup"><span data-stu-id="d17da-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="d17da-142">**RewardsPoints**: Nombor Bulat</span><span class="sxs-lookup"><span data-stu-id="d17da-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="d17da-143">**CreatedOn**: Tarikh/Masa</span><span class="sxs-lookup"><span data-stu-id="d17da-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="d17da-144">Dalam medan **Nama** pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d17da-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="d17da-145">**Simpan** sumber data.</span><span class="sxs-lookup"><span data-stu-id="d17da-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="d17da-146">Inges data pelanggan daripada ulasan laman web</span><span class="sxs-lookup"><span data-stu-id="d17da-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="d17da-147">Cipta sumber data bernama **Laman Web**, pilih pilihan import dan pilih penyambung **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d17da-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d17da-148">Masukkan URL untuk kenalan e-Dagang https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="d17da-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="d17da-149">Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="d17da-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d17da-150">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="d17da-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="d17da-151">**ReviewRating**: Nombor perpuluhan</span><span class="sxs-lookup"><span data-stu-id="d17da-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="d17da-152">**ReviewDate**: Tarikh</span><span class="sxs-lookup"><span data-stu-id="d17da-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="d17da-153">Dalam medan 'Nama' pada anak tetingkap sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **Ulasan**.</span><span class="sxs-lookup"><span data-stu-id="d17da-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="d17da-154">**Simpan** sumber data.</span><span class="sxs-lookup"><span data-stu-id="d17da-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="d17da-155">Tugas 2 - Penyatuan data</span><span class="sxs-lookup"><span data-stu-id="d17da-155">Task 2 - Data unification</span></span>

<span data-ttu-id="d17da-156">Selepas pengingesan data, kami kini memulakan proses penyatuan data untuk mencipta profil pelanggan yang disatukan.</span><span class="sxs-lookup"><span data-stu-id="d17da-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="d17da-157">Untuk mendapatkan maklumat lanjut, lihat [Penyatuan data](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="d17da-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="d17da-158">Petakan</span><span class="sxs-lookup"><span data-stu-id="d17da-158">Map</span></span>

1. <span data-ttu-id="d17da-159">Selepas menginges data, petakan kenalan daripada data e-Dagang dan Kesetiaan kepada jenis data umum.</span><span class="sxs-lookup"><span data-stu-id="d17da-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="d17da-160">Pergi ke **Data** > **Satukan** > **Peta**.</span><span class="sxs-lookup"><span data-stu-id="d17da-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="d17da-161">Pilih entiti yang mewakili profil pelanggan – **eCommerceContacts** dan **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d17da-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="d17da-162">Kemudian, pilih **Guna**.</span><span class="sxs-lookup"><span data-stu-id="d17da-162">Then, select **Apply**.</span></span>

   ![menyatukan sumber data e-Dagang dan kesetiaan.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="d17da-164">Pilih **ContactId** sebagai kunci utama untuk **eCommerceContacts** dan **LoyaltyID** sebagai kunci utama untuk **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d17da-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Menyatukan LoyaltyId sebagai kunci utama.](media/unify-loyaltyid.png)

1. <span data-ttu-id="d17da-166">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="d17da-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="d17da-167">Padankan</span><span class="sxs-lookup"><span data-stu-id="d17da-167">Match</span></span>

1. <span data-ttu-id="d17da-168">Pergi ke tab **Padanan** dan pilih **Tetapkan Urutan**.</span><span class="sxs-lookup"><span data-stu-id="d17da-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="d17da-169">Dalam senarai juntai bawah **Utama**, pilih **eCommerceContacts : e-Dagang** sebagai sumber utama dan menyertakan semua rekod.</span><span class="sxs-lookup"><span data-stu-id="d17da-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="d17da-170">Dalam senarai juntai bawah **Entiti 2**, pilih **loyCustomers : LoyaltyScheme** dan menyertakan semua rekod.</span><span class="sxs-lookup"><span data-stu-id="d17da-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Menyatukan padanan e-Dagang dan Kesetiaan.](media/unify-match-order.png)

1. <span data-ttu-id="d17da-172">Pilih **Tambah peraturan**</span><span class="sxs-lookup"><span data-stu-id="d17da-172">Select **Add rule**</span></span>

1. <span data-ttu-id="d17da-173">Tambah syarat pertama anda menggunakan FullName.</span><span class="sxs-lookup"><span data-stu-id="d17da-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="d17da-174">Untuk eCommerceContacts pilih **FullName** dalam senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="d17da-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="d17da-175">Untuk loyCustomers, pilih **FullName** dalam senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="d17da-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="d17da-176">Pilih senarai juntai bawah **Normalkan** dan pilih **Jenis (Telefon, Nama, Alamat, ...)**.</span><span class="sxs-lookup"><span data-stu-id="d17da-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="d17da-177">Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.</span><span class="sxs-lookup"><span data-stu-id="d17da-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="d17da-178">Masukkan nama **FullName, Email** untuk peraturan baharu.</span><span class="sxs-lookup"><span data-stu-id="d17da-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="d17da-179">Tambah syarat kedua untuk alamat e-mel dengan memilih **Tambah Syarat**</span><span class="sxs-lookup"><span data-stu-id="d17da-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="d17da-180">Untuk entiti eCommerceContacts, pilih **EMail** dalam senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="d17da-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="d17da-181">Untuk entiti loyCustomers, pilih **EMail** dalam senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="d17da-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="d17da-182">Biarkan Menormalkan kosong.</span><span class="sxs-lookup"><span data-stu-id="d17da-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="d17da-183">Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.</span><span class="sxs-lookup"><span data-stu-id="d17da-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Menyatukan peraturan padanan untuk nama dan e-mel.](media/unify-match-rule.png)

1. <span data-ttu-id="d17da-185">Pilih **Selesai**.</span><span class="sxs-lookup"><span data-stu-id="d17da-185">Select **Done**.</span></span>

1. <span data-ttu-id="d17da-186">Pilih **Simpan** dan **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="d17da-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="d17da-187">Gabungkan</span><span class="sxs-lookup"><span data-stu-id="d17da-187">Merge</span></span>

1. <span data-ttu-id="d17da-188">Pergi ke tab **Gabungan**.</span><span class="sxs-lookup"><span data-stu-id="d17da-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="d17da-189">Pada **ContactId** untuk entiti **loyCustomers**, tukar nama paparan kepada **ContactIdLOYALTY** untuk membezakannya daripada ID lain yang diinges.</span><span class="sxs-lookup"><span data-stu-id="d17da-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![namakan semula contactid daripada ID kesetiaan.](media/unify-merge-contactid.png)

1. <span data-ttu-id="d17da-191">Pilih **Simpan** dan **Jalankan proses gabungan dan hiliran**.</span><span class="sxs-lookup"><span data-stu-id="d17da-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="d17da-192">Tugas 3 - Konfigurasi ramalan nilai sepanjang hayat pelanggan</span><span class="sxs-lookup"><span data-stu-id="d17da-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="d17da-193">Dengan profil pelanggan yang disatukan ditetapkan, kami kini boleh menjalankan ramalan nilai sepanjang hayat pelanggan.</span><span class="sxs-lookup"><span data-stu-id="d17da-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="d17da-194">Untuk langkah-langkah terperinci, lihat [Ramalan Nilai Sepanjang Hayat (pratonton)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="d17da-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="d17da-195">Pergi ke **Kecerdasan**  > **Ramalan** dan pilih **Model nilai sepanjang hayat pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="d17da-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="d17da-196">Pergi melalui maklumat dalam anak tetingkap sisi dan pilih **Mari Bermula**.</span><span class="sxs-lookup"><span data-stu-id="d17da-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="d17da-197">Namakan model **Ramalan OOB eCommerce CLV** dan entiti output **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="d17da-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="d17da-198">Tentukan keutamaan model untuk model CLV:</span><span class="sxs-lookup"><span data-stu-id="d17da-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="d17da-199">**Tempoh masa ramalan**: **12 bulan atau 1 tahun**.</span><span class="sxs-lookup"><span data-stu-id="d17da-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="d17da-200">Tetapan ini menentukan sejauh mana masa depan untuk meramalkan nilai sepanjang hayat pelanggan.</span><span class="sxs-lookup"><span data-stu-id="d17da-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="d17da-201">**Pelanggan aktif**: Tentukan maksud pelanggan aktif untuk perniagaan anda.</span><span class="sxs-lookup"><span data-stu-id="d17da-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="d17da-202">Tetapkan tempoh masa sejarah yang pelanggan mesti mempunyai sekurang-kurangnya satu transaksi untuk dianggap aktif.</span><span class="sxs-lookup"><span data-stu-id="d17da-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="d17da-203">Model hanya akan meramalkan CLV untuk pelanggan aktif.</span><span class="sxs-lookup"><span data-stu-id="d17da-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="d17da-204">Pilih antara membiarkan model mengira tempoh masa berdasarkan data transaksi sejarah atau berikan tempoh masa tertentu.</span><span class="sxs-lookup"><span data-stu-id="d17da-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="d17da-205">Dalam panduan sampel ini, kami **membiarkan model mengira selang pembelian**, yang merupakan pilihan lalai.</span><span class="sxs-lookup"><span data-stu-id="d17da-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="d17da-206">**Pelanggan bernilai tinggi**: Tentukan pelanggan bernilai tinggi sebagai seperseratusan pelanggan teratas yang membayar.</span><span class="sxs-lookup"><span data-stu-id="d17da-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="d17da-207">Model menggunakan input ini untuk memberikan hasil yang sesuai dengan definisi perniagaan pelanggan bernilai tinggi anda.</span><span class="sxs-lookup"><span data-stu-id="d17da-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="d17da-208">Anda boleh memilih untuk membiarkan model menentukan pelanggan bernilai tinggi.</span><span class="sxs-lookup"><span data-stu-id="d17da-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="d17da-209">Ia menggunakan peraturan heuristik yang menjumlahkan seperseratusan.</span><span class="sxs-lookup"><span data-stu-id="d17da-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="d17da-210">Anda juga boleh menentukan pelanggan bernilai tinggi sebagai seperseratusan pelanggan teratas yang membayar pada masa depan.</span><span class="sxs-lookup"><span data-stu-id="d17da-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="d17da-211">Dalam panduan sampel ini, kami menentukan pelanggan bernilai tinggi secara manual sebagai **30% teratas pelanggan yang aktif membayar** dan pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="d17da-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Keutamaan melangkah dalam pengalaman berpandu untuk model CLV.":::

1. <span data-ttu-id="d17da-213">Dalam langkah **Data yang Diperlukan**, pilih **Tambah data** untuk menyediakan data sejarah transaksi.</span><span class="sxs-lookup"><span data-stu-id="d17da-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="d17da-214">Tambah entiti **eCommercePurchases: e-Dagang** dan petakan atribut yang diperlukan oleh model:</span><span class="sxs-lookup"><span data-stu-id="d17da-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="d17da-215">ID transaksi: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="d17da-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="d17da-216">Tarikh transaksi: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="d17da-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="d17da-217">Amaun transaksi: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="d17da-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="d17da-218">ID produk: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="d17da-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="d17da-219">Pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="d17da-219">Select **Next**.</span></span>

1. <span data-ttu-id="d17da-220">Sediakan perhubungan antara entiti **eCommercePurchases: eCommerce** dengan **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="d17da-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="d17da-221">Langkah **Data tambahan (pilihan)** membolehkan anda menambah lebih banyak data aktiviti pelanggan.</span><span class="sxs-lookup"><span data-stu-id="d17da-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="d17da-222">Data ini boleh membantu untuk mendapatkan lebih banyak cerapan untuk interaksi pelanggan dengan perniagaan anda, yang boleh menyumbang kepada CLV.</span><span class="sxs-lookup"><span data-stu-id="d17da-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="d17da-223">Menambah interaksi pelanggan utama seperti log web, log khidmat pelanggan atau sejarah program ganjaran boleh meningkatkan ketepatan ramalan.</span><span class="sxs-lookup"><span data-stu-id="d17da-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="d17da-224">Pilih **Tambah data** untuk menyertakan lebih banyak data aktiviti pelanggan.</span><span class="sxs-lookup"><span data-stu-id="d17da-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="d17da-225">Tambah entiti aktiviti pelanggan dan petakan nama medan ke medan sepadan yang diperlukan oleh model:</span><span class="sxs-lookup"><span data-stu-id="d17da-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="d17da-226">Entiti aktiviti pelanggan: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="d17da-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="d17da-227">Kunci utama: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="d17da-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="d17da-228">Cap masa: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="d17da-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="d17da-229">Peristiwa (nama aktiviti): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="d17da-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="d17da-230">Butiran (amaun atau nilai): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="d17da-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="d17da-231">Pilih **Seterusnya** dan konfigurasikan aktiviti dan perhubungan antara data transaksi dengan data pelanggan:</span><span class="sxs-lookup"><span data-stu-id="d17da-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="d17da-232">Jenis aktiviti: Pilih yang sedia ada</span><span class="sxs-lookup"><span data-stu-id="d17da-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="d17da-233">Label aktiviti: Semak</span><span class="sxs-lookup"><span data-stu-id="d17da-233">Activity label: Review</span></span>
   - <span data-ttu-id="d17da-234">Label yang sepadan: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="d17da-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="d17da-235">Entiti pelanggan: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="d17da-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="d17da-236">Perhubungan: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="d17da-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="d17da-237">Pilih **Seterusnya** untuk menetapkan jadual model.</span><span class="sxs-lookup"><span data-stu-id="d17da-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="d17da-238">Model perlu melatih dengan kerap untuk mempelajari corak baharu apabila terdapat data baharu yang diinges.</span><span class="sxs-lookup"><span data-stu-id="d17da-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="d17da-239">Untuk contoh ini, pilih **Bulanan**.</span><span class="sxs-lookup"><span data-stu-id="d17da-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="d17da-240">Selepas menyemak semula semua butiran, pilih **Simpan dan Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="d17da-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="d17da-241">Tugas 4 - Semak semula hasil dan penerangan model</span><span class="sxs-lookup"><span data-stu-id="d17da-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="d17da-242">Biarkan model melengkapkan latihan dan pemarkahan data.</span><span class="sxs-lookup"><span data-stu-id="d17da-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="d17da-243">Seterusnya, anda boleh menyemak hasil dan penjelasan model CLV.</span><span class="sxs-lookup"><span data-stu-id="d17da-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="d17da-244">Untuk mendapatkan maklumat lanjut, lihat [Semak semula status dan keputusan ramalan](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="d17da-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="d17da-245">Tugas 5 - Cipta segmen pelanggan bernilai tinggi</span><span class="sxs-lookup"><span data-stu-id="d17da-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="d17da-246">Menjalankan model mencipta entiti baharu, yang disenaraikan pada **Data** > **Entiti**.</span><span class="sxs-lookup"><span data-stu-id="d17da-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="d17da-247">Anda boleh mencipta segmen pelanggan baharu berdasarkan entiti yang dicipta oleh model.</span><span class="sxs-lookup"><span data-stu-id="d17da-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="d17da-248">Pergi ke **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="d17da-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="d17da-249">Pilih **Baharu** dan pilih **Cipta daripada** > **Kecerdasan**.</span><span class="sxs-lookup"><span data-stu-id="d17da-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Mencipta segmen dengan output model.](media/segment-intelligence.png)

1. <span data-ttu-id="d17da-251">Pilih entiti **OOBeCommerceCLVPrediction** dan tentukan segmen:</span><span class="sxs-lookup"><span data-stu-id="d17da-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="d17da-252">Medan: CLVScore</span><span class="sxs-lookup"><span data-stu-id="d17da-252">Field: CLVScore</span></span>
  - <span data-ttu-id="d17da-253">Operator: lebih daripada</span><span class="sxs-lookup"><span data-stu-id="d17da-253">Operator: greater than</span></span>
  - <span data-ttu-id="d17da-254">Nilai: 1500</span><span class="sxs-lookup"><span data-stu-id="d17da-254">Value: 1500</span></span>

1. <span data-ttu-id="d17da-255">Pilih **Semak** dan **Simpan** segmen.</span><span class="sxs-lookup"><span data-stu-id="d17da-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="d17da-256">Anda kini mempunyai segmen yang mengenal pasti pelanggan yang diramalkan untuk menjana lebih daripada $1500 pendapatan dalam tempoh 12 bulan akan datang.</span><span class="sxs-lookup"><span data-stu-id="d17da-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="d17da-257">Segmen ini akan dikemas kini secara dinamik jika lebih banyak data diinges.</span><span class="sxs-lookup"><span data-stu-id="d17da-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="d17da-258">Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d17da-258">For more information, see [Create and manage segments](segments.md).</span></span>
