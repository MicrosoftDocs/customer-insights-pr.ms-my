---
title: Langganan panduan sampel ramalan pulangan
description: Gunakan panduan sampel ini untuk mencuba model ramalan pulangan langganan luar kotak.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653991"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="bb68f-103">Panduan sampel ramalan pulangan langganan (pratonton)</span><span class="sxs-lookup"><span data-stu-id="bb68f-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="bb68f-104">Kami akan menerangkan kepada anda contoh ramalan pulangan langganan hujung ke hujung menggunakan data sampel yang diberikan di bawah.</span><span class="sxs-lookup"><span data-stu-id="bb68f-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="bb68f-105">Senario</span><span class="sxs-lookup"><span data-stu-id="bb68f-105">Scenario</span></span>

<span data-ttu-id="bb68f-106">Contoso ialah sebuah syarikat yang menghasilkan mesin kopi dan kopi berkualiti tinggi, yang mereka jual melalui laman web Contoso Coffee mereka.</span><span class="sxs-lookup"><span data-stu-id="bb68f-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="bb68f-107">Mereka baru memulakan perniagaan langganan untuk pelanggan mereka untuk mendapatkan kopi secara tetap.</span><span class="sxs-lookup"><span data-stu-id="bb68f-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="bb68f-108">Matlamat mereka ialah untuk memahami, pelanggan yang melanggan yang mana mungkin membatalkan langganan mereka dalam beberapa bulan akan datang.</span><span class="sxs-lookup"><span data-stu-id="bb68f-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="bb68f-109">Mengetahui pelanggan mereka yang **cenderung untuk memulangkan**, boleh membantu mereka menjimatkan usaha pemasaran dengan memberikan tumpuan dalam mengekalkan mereka.</span><span class="sxs-lookup"><span data-stu-id="bb68f-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb68f-110">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="bb68f-110">Prerequisites</span></span>

- <span data-ttu-id="bb68f-111">Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bb68f-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="bb68f-112">Kami mengesyorkan agar anda melaksanakan langkah berikut [dalam persekitaran baharu](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="bb68f-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="bb68f-113">Tugas 1 - Inges Data</span><span class="sxs-lookup"><span data-stu-id="bb68f-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="bb68f-114">Semak semula artikel [tentang pengingesan data](data-sources.md) dan [mengimport sumber data menggunakan penyambung Power Query](connect-power-query.md) secara khusus.</span><span class="sxs-lookup"><span data-stu-id="bb68f-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="bb68f-115">Maklumat berikut menganggap anda membiasakan diri dengan pengingesan data secara umum.</span><span class="sxs-lookup"><span data-stu-id="bb68f-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="bb68f-116">Inges data pelanggan daripada platform e-Dagang</span><span class="sxs-lookup"><span data-stu-id="bb68f-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="bb68f-117">Cipta sumber data bernama **e-Dagang**, pilih pilihan import dan pilih penyambung **Teks/CSV**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="bb68f-118">Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="bb68f-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="bb68f-119">Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="bb68f-120">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="bb68f-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="bb68f-121">**DateOfBirth**: Tarikh</span><span class="sxs-lookup"><span data-stu-id="bb68f-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="bb68f-122">**CreatedOn**: Zon waktu tarikh</span><span class="sxs-lookup"><span data-stu-id="bb68f-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="bb68f-123">![Ubah Tarikh Lahir kepada Tarikh](media/ecommerce-dob-date.PNG "ubah tarikh lahir kepada tarikh ini")</span><span class="sxs-lookup"><span data-stu-id="bb68f-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="bb68f-124">Dalam medan 'Nama' pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="bb68f-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="bb68f-125">Simpan sumber data.</span><span class="sxs-lookup"><span data-stu-id="bb68f-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="bb68f-126">Ingest data pelanggan daripada skema kesetiaan</span><span class="sxs-lookup"><span data-stu-id="bb68f-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="bb68f-127">Cipta sumber data bernama **LoyaltyScheme**, pilih pilihan import dan pilih penyambung **Teks/CSV**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="bb68f-128">Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="bb68f-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="bb68f-129">Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="bb68f-130">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="bb68f-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="bb68f-131">**DateOfBirth**: Tarikh</span><span class="sxs-lookup"><span data-stu-id="bb68f-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="bb68f-132">**RewardsPoints**: Nombor Bulat</span><span class="sxs-lookup"><span data-stu-id="bb68f-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="bb68f-133">**CreatedOn**: Tarikh/Masa</span><span class="sxs-lookup"><span data-stu-id="bb68f-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="bb68f-134">Dalam medan 'Nama' pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="bb68f-135">Simpan sumber data.</span><span class="sxs-lookup"><span data-stu-id="bb68f-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="bb68f-136">Ingeskan maklumat langganan</span><span class="sxs-lookup"><span data-stu-id="bb68f-136">Ingest subscription information</span></span>

1. <span data-ttu-id="bb68f-137">Cipta sumber data bernama **SubscriptionHistory**, pilih pilihan import dan pilih penyambung **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="bb68f-138">Masukkan URL untuk kenalan e-dagang https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="bb68f-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="bb68f-139">Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="bb68f-140">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="bb68f-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="bb68f-141">**SubscriptioID**: Nombor Bulat</span><span class="sxs-lookup"><span data-stu-id="bb68f-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="bb68f-142">**SubscriptionAmount**: Mata Wang</span><span class="sxs-lookup"><span data-stu-id="bb68f-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="bb68f-143">**SubscriptionEndDate** : Tarikh/Masa</span><span class="sxs-lookup"><span data-stu-id="bb68f-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="bb68f-144">**SubscriptionEndDate**: Tarikh/Masa</span><span class="sxs-lookup"><span data-stu-id="bb68f-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="bb68f-145">**TransactionDate**: Tarikh/Masa</span><span class="sxs-lookup"><span data-stu-id="bb68f-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="bb68f-146">**IsRecurring**: Benar/Palsu</span><span class="sxs-lookup"><span data-stu-id="bb68f-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="bb68f-147">**Is_auto_renew** : Benar/Palsu</span><span class="sxs-lookup"><span data-stu-id="bb68f-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="bb68f-148">**RecurringFrequencyInMonths**: Nombor Bulat</span><span class="sxs-lookup"><span data-stu-id="bb68f-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="bb68f-149">Dalam medan 'Nama' pada anak tetingkap sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="bb68f-150">Simpan sumber data.</span><span class="sxs-lookup"><span data-stu-id="bb68f-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="bb68f-151">Inges data pelanggan daripada ulasan laman web</span><span class="sxs-lookup"><span data-stu-id="bb68f-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="bb68f-152">Cipta sumber data bernama **Laman Web**, pilih pilihan import dan pilih penyambung **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="bb68f-153">Masukkan URL untuk kenalan e-dagang https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="bb68f-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="bb68f-154">Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="bb68f-155">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="bb68f-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="bb68f-156">**ReviewRating**: Nombor Bulat</span><span class="sxs-lookup"><span data-stu-id="bb68f-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="bb68f-157">**ReviewDate**: Tarikh</span><span class="sxs-lookup"><span data-stu-id="bb68f-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="bb68f-158">Dalam medan 'Nama' pada anak tetingkap sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="bb68f-159">Tugas 2 - Penyatuan data</span><span class="sxs-lookup"><span data-stu-id="bb68f-159">Task 2 - Data unification</span></span>

<span data-ttu-id="bb68f-160">Selepas menginges data, kini kita memulakan proses **Petaan, Padanan, Gabungan** untuk mencipta profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="bb68f-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="bb68f-161">Untuk mendapatkan maklumat lanjut, lihat [Penyatuan data](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="bb68f-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="bb68f-162">Petakan</span><span class="sxs-lookup"><span data-stu-id="bb68f-162">Map</span></span>

1. <span data-ttu-id="bb68f-163">Selepas menginges data, petakan kenalan daripada data e-Dagang dan Kesetiaan kepada jenis data umum.</span><span class="sxs-lookup"><span data-stu-id="bb68f-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="bb68f-164">Pergi ke **Data** > **Satukan** > **Peta**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="bb68f-165">Pilih entiti yang mewakili profil pelanggan – **eCommerceContacts** dan **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="menyatukan sumber data e-Dagang dan kesetiaan.":::

1. <span data-ttu-id="bb68f-167">Pilih **ContactId** sebagai kunci utama untuk **eCommerceContacts** dan **LoyaltyID** sebagai kunci utama untuk **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Menyatukan LoyaltyId sebagai kunci utama.":::

### <a name="match"></a><span data-ttu-id="bb68f-169">Padankan</span><span class="sxs-lookup"><span data-stu-id="bb68f-169">Match</span></span>

1. <span data-ttu-id="bb68f-170">Pergi ke tab **Padanan** dan pilih **Tetapkan Urutan**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="bb68f-171">Dalam senarai juntai bawah **Utama**, pilih **eCommerceContacts : e-Dagang** sebagai sumber utama dan menyertakan semua rekod.</span><span class="sxs-lookup"><span data-stu-id="bb68f-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="bb68f-172">Dalam senarai juntai bawah **Entiti 2**, pilih **loyCustomers : LoyaltyScheme** dan menyertakan semua rekod.</span><span class="sxs-lookup"><span data-stu-id="bb68f-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Menyatukan padanan e-Dagang dan Kesetiaan.":::

1. <span data-ttu-id="bb68f-174">Pilih **Cipta peraturan baharu**</span><span class="sxs-lookup"><span data-stu-id="bb68f-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="bb68f-175">Tambah syarat pertama anda menggunakan FullName.</span><span class="sxs-lookup"><span data-stu-id="bb68f-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="bb68f-176">Untuk eCommerceContacts pilih **FullName** dalam senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="bb68f-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="bb68f-177">Untuk loyCustomers, pilih **FullName** dalam senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="bb68f-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="bb68f-178">Pilih senarai juntai bawah **Menormalkan** dan pilih **Jenis (Telefon, Nama, Alamat, ...)**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="bb68f-179">Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="bb68f-180">Masukkan nama **FullName, Email** untuk peraturan baharu.</span><span class="sxs-lookup"><span data-stu-id="bb68f-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="bb68f-181">Tambah syarat kedua untuk alamat e-mel dengan memilih **Tambah Syarat**</span><span class="sxs-lookup"><span data-stu-id="bb68f-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="bb68f-182">Untuk entiti eCommerceContacts, pilih **EMail** dalam senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="bb68f-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="bb68f-183">Untuk entiti loyCustomers, pilih **EMail** dalam senarai juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="bb68f-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="bb68f-184">Biarkan Menormalkan kosong.</span><span class="sxs-lookup"><span data-stu-id="bb68f-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="bb68f-185">Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Menyatukan peraturan padanan untuk nama dan e-mel.":::

7. <span data-ttu-id="bb68f-187">Pilih **Simpan** dan **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="bb68f-188">Gabungkan</span><span class="sxs-lookup"><span data-stu-id="bb68f-188">Merge</span></span>

1. <span data-ttu-id="bb68f-189">Pergi ke tab **Gabungan**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="bb68f-190">Pada **ContactId** untuk entiti **loyCustomers**, tukar nama paparan kepada **ContactIdLOYALTY** untuk membezakannya daripada ID lain yang diinges.</span><span class="sxs-lookup"><span data-stu-id="bb68f-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="namakan semula contactid daripada ID kesetiaan.":::

1. <span data-ttu-id="bb68f-192">Pilih **Simpan** dan **Jalankan** untuk memulakan Proses Gabungan.</span><span class="sxs-lookup"><span data-stu-id="bb68f-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="bb68f-193">Tugas 3 - Konfigurasikan ramalan pulangan langganan</span><span class="sxs-lookup"><span data-stu-id="bb68f-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="bb68f-194">Dengan adanya profil pelanggan disatukan, kini kami dapat menjalankan ramalan pulangan langganan.</span><span class="sxs-lookup"><span data-stu-id="bb68f-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="bb68f-195">Untuk langkah terperinci, lihat artikel [Ramalan pulangan langganan (pratonton)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="bb68f-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="bb68f-196">Pergi ke **Kecerdasan** > **Teroka** dan pilih untuk menggunakan **Model pulangan pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="bb68f-197">Pilih pilihan **Langganan** dan pilih **Mari Bermula**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="bb68f-198">Namakan model **Ramalan Pulangan Langganan OOB** dan **OOBSubscriptionChurnPrediction** entiti output.</span><span class="sxs-lookup"><span data-stu-id="bb68f-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="bb68f-199">Takrifkan dua syarat untuk model pulangan:</span><span class="sxs-lookup"><span data-stu-id="bb68f-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="bb68f-200">**Hari sejak langganan tamat**: **sekurang-kurangnya 60** hari.</span><span class="sxs-lookup"><span data-stu-id="bb68f-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="bb68f-201">Jika pelanggan tidak memperbaharui langganan dalam tempoh ini selepas langganan mereka tamat, mereka dianggap telah memberikan pulangan.</span><span class="sxs-lookup"><span data-stu-id="bb68f-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="bb68f-202">**Definisi pulangan**: **sekurang-kurangnya 93** hari.</span><span class="sxs-lookup"><span data-stu-id="bb68f-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="bb68f-203">Tempoh model meramalkan pelanggan mana yang mungkin akan memberikan pulangan.</span><span class="sxs-lookup"><span data-stu-id="bb68f-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="bb68f-204">Semakin jauh masa hadapan anda melihat, semakin kurang tepat keputusan.</span><span class="sxs-lookup"><span data-stu-id="bb68f-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Pilih Tetingkap Ramalan tuil model dan Definisi Ramalan.":::

1. <span data-ttu-id="bb68f-206">Pilih **Tambah data yang diperlukan** dan pilih **Tambah data** untuk sejarah langganan.</span><span class="sxs-lookup"><span data-stu-id="bb68f-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="bb68f-207">Tambah **Langganan: Entiti SubscriptionHistory** dan petakan medan daripada e-Dagang kepada medan berkaitan yang diperlukan oleh model.</span><span class="sxs-lookup"><span data-stu-id="bb68f-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="bb68f-208">Sertai **Langganan: Entiti SubscriptionHistory** dengan **eCommerceContacts : e-Dagang**, namakan hubungan **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Sertai entiti e-Dagang.":::

1. <span data-ttu-id="bb68f-210">Di bawah Aktiviti Pelanggan, tambah **webReviews : Entiti Laman Web** dan petakan medan daripada webReviews kepada medan berkaitan yang diperlukan oleh model.</span><span class="sxs-lookup"><span data-stu-id="bb68f-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="bb68f-211">Kunci utama: ReviewId</span><span class="sxs-lookup"><span data-stu-id="bb68f-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="bb68f-212">Cap waktu: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="bb68f-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="bb68f-213">Peristiwa: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="bb68f-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="bb68f-214">Konfigurasikan aktiviti untuk ulasan laman web.</span><span class="sxs-lookup"><span data-stu-id="bb68f-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="bb68f-215">Pilih aktiviti **Ulasan** dan sertai **webReviews: Entiti laman web** dengan **eCommerceContacts: e-Dagang**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="bb68f-216">Pilih **Seterusnya** untuk menetapkan jadual model.</span><span class="sxs-lookup"><span data-stu-id="bb68f-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="bb68f-217">Model perlu dilatih secara tetap untuk belajar pola baharu apabila terdapat data baharu yang diinges.</span><span class="sxs-lookup"><span data-stu-id="bb68f-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="bb68f-218">Untuk contoh ini, pilih **Bulanan**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="bb68f-219">Selepas menyemak semula semua butiran, pilih **Simpan dan Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="bb68f-220">Tugas 4 - Semak semula hasil dan penerangan model</span><span class="sxs-lookup"><span data-stu-id="bb68f-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="bb68f-221">Biarkan model melengkapkan latihan dan pemarkahan data.</span><span class="sxs-lookup"><span data-stu-id="bb68f-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="bb68f-222">Anda kini boleh menyemak semula penerangan model pulangan langganan.</span><span class="sxs-lookup"><span data-stu-id="bb68f-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="bb68f-223">Untuk mendapatkan maklumat lanjut, lihat [Semak semula status dan keputusan ramalan](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="bb68f-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="bb68f-224">Tugas 5 - Cipta segmen pelanggan risiko pulangan tinggi</span><span class="sxs-lookup"><span data-stu-id="bb68f-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="bb68f-225">Menjalankan model pengeluaran mewujudkan entiti baharu yang anda boleh lihat dalam **Data** > **Entiti**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="bb68f-226">Anda boleh mencipta segmen baharu berdasarkan entiti yang dicipta oleh model.</span><span class="sxs-lookup"><span data-stu-id="bb68f-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="bb68f-227">Pergi ke **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-227">Go to **Segments**.</span></span> <span data-ttu-id="bb68f-228">Pilih **Baharu** dan pilih **Cipta daripada** > **Kecerdasan**.</span><span class="sxs-lookup"><span data-stu-id="bb68f-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Mencipta segmen dengan output model.":::

1. <span data-ttu-id="bb68f-230">Pilih titik tamat **OOBSubscriptionChurnPrediction** dan takrifkan segmen:</span><span class="sxs-lookup"><span data-stu-id="bb68f-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="bb68f-231">Medan: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="bb68f-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="bb68f-232">Operator: lebih daripada</span><span class="sxs-lookup"><span data-stu-id="bb68f-232">Operator: greater than</span></span>
   - <span data-ttu-id="bb68f-233">Nilai: 0.6</span><span class="sxs-lookup"><span data-stu-id="bb68f-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Sediakan segmen pulangan langganan.":::

<span data-ttu-id="bb68f-235">Kini anda mempunyai segmen yang dikemas kini secara dinamik yang mengenal pasti pelanggan risiko pulangan tinggi untuk perniagaan langganan ini.</span><span class="sxs-lookup"><span data-stu-id="bb68f-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="bb68f-236">Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).</span><span class="sxs-lookup"><span data-stu-id="bb68f-236">For more information, see [Create and manage segments](segments.md).</span></span>
