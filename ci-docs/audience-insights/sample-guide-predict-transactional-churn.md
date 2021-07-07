---
title: Panduan sampel ramalan pulangan transaksi
description: Gunakan panduan sampel ini untuk mencuba model ramalan pulangan transaksi luar kotak.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306131"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="2aaa1-103">Panduan sampel ramalan pulangan transaksi (pratonton)</span><span class="sxs-lookup"><span data-stu-id="2aaa1-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="2aaa1-104">Panduan ini akan menerangkan kepada anda contoh menyeluruh ramalan Pulangan Transaksi dalam Customer Insights menggunakan data yang disediakan di bawah.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="2aaa1-105">Semua data yang digunakan dalam panduan ini bukan data pelanggan sebenar dan merupakan sebahagian daripada set data Contoso yang terdapat dalam persekitaran *Demo* dalam Langganan Customer Insights anda.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="2aaa1-106">Senario</span><span class="sxs-lookup"><span data-stu-id="2aaa1-106">Scenario</span></span>

<span data-ttu-id="2aaa1-107">Contoso ialah sebuah syarikat yang menghasilkan mesin kopi dan kopi berkualiti tinggi, yang menjual melalui laman web Contoso Coffee mereka.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="2aaa1-108">Matlamat mereka adalah untuk mengetahui pelanggan yang biasanya membeli produk mereka secara tetap, akan berhenti menjadi pelanggan aktif dalam masa 60 hari akan datang.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="2aaa1-109">Mengetahui pelanggan mereka yang **cenderung untuk memulangkan**, boleh membantu mereka menjimatkan usaha pemasaran dengan memberikan tumpuan dalam mengekalkan mereka.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2aaa1-110">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="2aaa1-110">Prerequisites</span></span>

- <span data-ttu-id="2aaa1-111">Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="2aaa1-112">Kami mengesyorkan agar anda melaksanakan langkah berikut [dalam persekitaran baharu](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="2aaa1-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="2aaa1-113">Tugas 1 - Inges data</span><span class="sxs-lookup"><span data-stu-id="2aaa1-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="2aaa1-114">Semak semula artikel [tentang pengingesan data](data-sources.md) dan [mengimport sumber data menggunakan penyambung Power Query](connect-power-query.md) secara khusus.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="2aaa1-115">Maklumat berikut menganggap anda membiasakan diri dengan pengingesan data secara umum.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="2aaa1-116">Inges data pelanggan daripada platform e-Dagang</span><span class="sxs-lookup"><span data-stu-id="2aaa1-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="2aaa1-117">Cipta sumber data bernama **e-Dagang**, pilih pilihan import dan pilih penyambung **Teks/CSV**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="2aaa1-118">Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="2aaa1-119">Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="2aaa1-120">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="2aaa1-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="2aaa1-121">**DateOfBirth**: Tarikh</span><span class="sxs-lookup"><span data-stu-id="2aaa1-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="2aaa1-122">**CreatedOn**: Zon waktu tarikh</span><span class="sxs-lookup"><span data-stu-id="2aaa1-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="2aaa1-123">![Ubah Tarikh Lahir kepada Tarikh](media/ecommerce-dob-date.PNG "ubah tarikh lahir kepada tarikh ini")</span><span class="sxs-lookup"><span data-stu-id="2aaa1-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="2aaa1-124">Dalam medan **Nama** pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="2aaa1-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="2aaa1-125">Simpan sumber data.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="2aaa1-126">Inges data pembelian dalam talian</span><span class="sxs-lookup"><span data-stu-id="2aaa1-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="2aaa1-127">Tambahkan set data lain pada sumber data **e-Dagang** yang sama.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="2aaa1-128">Pilih penyambung **Teks/CSV** semula.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="2aaa1-129">Masukkan URL untuk data **Pembelian Dalam Talian** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="2aaa1-130">Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="2aaa1-131">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="2aaa1-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="2aaa1-132">**PurchasedOn** : Tarikh/Masa</span><span class="sxs-lookup"><span data-stu-id="2aaa1-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="2aaa1-133">**TotalPrice** : Mata Wang</span><span class="sxs-lookup"><span data-stu-id="2aaa1-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="2aaa1-134">Dalam medan **Nama** pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="2aaa1-135">Simpan sumber data.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="2aaa1-136">Ingest data pelanggan daripada skema kesetiaan</span><span class="sxs-lookup"><span data-stu-id="2aaa1-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="2aaa1-137">Cipta sumber data bernama **LoyaltyScheme**, pilih pilihan import dan pilih penyambung **Teks/CSV**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="2aaa1-138">Masukkan URL untuk kenalan e-Dagang https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="2aaa1-139">Semasa mengedit data, pilih **Ubah**, kemudian **Gunakan Baris Pertama sebagai Pengepala**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="2aaa1-140">Kemas kini jenis data untuk lajur yang disenaraikan di bawah:</span><span class="sxs-lookup"><span data-stu-id="2aaa1-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="2aaa1-141">**DateOfBirth**: Tarikh</span><span class="sxs-lookup"><span data-stu-id="2aaa1-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="2aaa1-142">**RewardsPoints**: Nombor Bulat</span><span class="sxs-lookup"><span data-stu-id="2aaa1-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="2aaa1-143">**CreatedOn**: Tarikh/Masa</span><span class="sxs-lookup"><span data-stu-id="2aaa1-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="2aaa1-144">Dalam medan **Nama** pada anak tetingkap di sebelah kanan, namakan semula sumber data anda daripada **Pertanyaan** kepada **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="2aaa1-145">Simpan sumber data.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="2aaa1-146">Tugas 2 - Penyatuan data</span><span class="sxs-lookup"><span data-stu-id="2aaa1-146">Task 2 - Data unification</span></span>

<span data-ttu-id="2aaa1-147">Selepas menginges data, kini kita memulakan proses **Petaan, Padanan, Gabungan** untuk mencipta profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="2aaa1-148">Untuk mendapatkan maklumat lanjut, lihat [Penyatuan data](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="2aaa1-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="2aaa1-149">Petakan</span><span class="sxs-lookup"><span data-stu-id="2aaa1-149">Map</span></span>

1. <span data-ttu-id="2aaa1-150">Selepas menginges data, petakan kenalan daripada data e-Dagang dan Kesetiaan kepada jenis data umum.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="2aaa1-151">Pergi ke **Data** > **Satukan** > **Peta**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="2aaa1-152">Pilih entiti yang mewakili profil pelanggan – **eCommerceContacts** dan **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="menyatukan sumber data e-Dagang dan kesetiaan.":::

1. <span data-ttu-id="2aaa1-154">Pilih **ContactId** sebagai kunci utama untuk **eCommerceContacts** dan **LoyaltyID** sebagai kunci utama untuk **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Menyatukan LoyaltyId sebagai kunci utama.":::

### <a name="match"></a><span data-ttu-id="2aaa1-156">Padankan</span><span class="sxs-lookup"><span data-stu-id="2aaa1-156">Match</span></span>

1. <span data-ttu-id="2aaa1-157">Pergi ke tab **Padanan** dan pilih **Tetapkan Urutan**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="2aaa1-158">Dalam senarai juntai bawah **Utama**, pilih **eCommerceContacts : eCommerce** sebagai sumber utama dan sertakan semua rekod.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="2aaa1-159">Dalam senarai juntai bawah **Entiti 2**, pilih **loyCustomers : LoyaltyScheme** dan sertakan semua rekod.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Menyatukan padanan e-Dagang dan Kesetiaan.":::

1. <span data-ttu-id="2aaa1-161">Pilih **Cipta peraturan baharu**</span><span class="sxs-lookup"><span data-stu-id="2aaa1-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="2aaa1-162">Tambah syarat pertama anda menggunakan FullName.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="2aaa1-163">Untuk eCommerceContacts pilih **FullName** dalam menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="2aaa1-164">Untuk loyCustomers pilih **FullName** dalam menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="2aaa1-165">Pilih senarai juntai bawah **Menormalkan** dan pilih **Jenis (Telefon, Nama, Alamat, ...)**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="2aaa1-166">Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="2aaa1-167">Masukkan nama **FullName, Email** untuk peraturan baharu.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="2aaa1-168">Tambah syarat kedua untuk alamat e-mel dengan memilih **Tambah Syarat**</span><span class="sxs-lookup"><span data-stu-id="2aaa1-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="2aaa1-169">Untuk entiti eCommerceContacts, pilih **EMail** dalam menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="2aaa1-170">Untuk entiti loyCustomers, pilih **EMail** dalam menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="2aaa1-171">Biarkan Menormalkan kosong.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="2aaa1-172">Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Menyatukan peraturan padanan untuk nama dan e-mel.":::

7. <span data-ttu-id="2aaa1-174">Pilih **Simpan** dan **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="2aaa1-175">Gabungkan</span><span class="sxs-lookup"><span data-stu-id="2aaa1-175">Merge</span></span>

1. <span data-ttu-id="2aaa1-176">Pergi ke tab **Gabungan**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="2aaa1-177">Pada **ContactId** untuk entiti **loyCustomers**, tukar nama paparan kepada **ContactIdLOYALTY** untuk membezakannya daripada ID lain yang diinges.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="namakan semula contactid daripada ID kesetiaan.":::

1. <span data-ttu-id="2aaa1-179">Pilih **Simpan** dan **Jalankan** untuk memulakan Proses Gabungan.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="2aaa1-180">Tugas 3 - Konfigurasikan ramalan pulangan transaksi</span><span class="sxs-lookup"><span data-stu-id="2aaa1-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="2aaa1-181">Dengan adanya profil pelanggan disatukan, kini kami dapat menjalankan ramalan pulangan langganan.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="2aaa1-182">Untuk langkah terperinci, lihat artikel [Ramalan pulangan langganan (pratonton)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="2aaa1-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="2aaa1-183">Pergi ke **Kecerdasan** > **Teroka** dan pilih untuk menggunakan **Model pulangan pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="2aaa1-184">Pilih pilihan **Transaksi** dan pilih **Mari bermula**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="2aaa1-185">Namakan model **Ramalan Pulangan Transaksi e-Dagang OOB** dan entiti output **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="2aaa1-186">Takrifkan dua syarat untuk model pulangan:</span><span class="sxs-lookup"><span data-stu-id="2aaa1-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="2aaa1-187">**Tetingkap ramalan** : **sekurang-kurangnya 60** hari.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="2aaa1-188">Tetapan ini mentakrifkan sejauh mana kita ingin meramalkan pulangan pelanggan pada masa hadapan.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="2aaa1-189">**Takrif pulangan** : **sekurang-kurangnya 60** hari.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="2aaa1-190">Tempoh tanpa pembelian selepas itu, pelanggan dianggap membuat pulangan.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Pilih tuil model Tetingkap Ramalan dan Takrifan Pulangan.":::

1. <span data-ttu-id="2aaa1-192">Pilih **Sejarah Pembelian (diperlukan)** dan pilih **Tambah data** untuk sejarah pembelian.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="2aaa1-193">Tambah entiti **eCommercePurchases : e-Dagang** dan petakan medan daripada e-Dagang kepada medan berkaitan yang diperlukan oleh model.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="2aaa1-194">Sertai entiti **eCommercePurchases : e-Dagang** dengan **eCommerceContacts : e-Dagang**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Sertai entiti e-Dagang.":::

1. <span data-ttu-id="2aaa1-196">Pilih **Seterusnya** untuk menetapkan jadual model.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="2aaa1-197">Model perlu dilatih secara tetap untuk belajar pola baharu apabila terdapat data baharu yang diinges.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="2aaa1-198">Untuk contoh ini, pilih **Bulanan**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="2aaa1-199">Selepas menyemak semula semua butiran, pilih **Simpan dan Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="2aaa1-200">Tugas 4 - Semak semula hasil dan penerangan model</span><span class="sxs-lookup"><span data-stu-id="2aaa1-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="2aaa1-201">Biarkan model melengkapkan latihan dan pemarkahan data.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="2aaa1-202">Anda kini boleh menyemak semula penerangan model pulangan langganan.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="2aaa1-203">Untuk mendapatkan maklumat lanjut, lihat [Semak semula status dan keputusan ramalan](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="2aaa1-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="2aaa1-204">Tugas 5 - Cipta segmen pelanggan risiko pulangan tinggi</span><span class="sxs-lookup"><span data-stu-id="2aaa1-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="2aaa1-205">Menjalankan model pengeluaran mewujudkan entiti baharu yang anda boleh lihat dalam **Data** > **Entiti**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="2aaa1-206">Anda boleh mencipta segmen baharu berdasarkan entiti yang dicipta oleh model.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="2aaa1-207">Pergi ke **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-207">Go to **Segments**.</span></span> <span data-ttu-id="2aaa1-208">Pilih **Baharu** dan pilih **Cipta daripada** > **Kecerdasan**.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Mencipta segmen dengan output model.":::

1. <span data-ttu-id="2aaa1-210">Pilih titik tamat **OOBSubscriptionChurnPrediction** dan takrifkan segmen:</span><span class="sxs-lookup"><span data-stu-id="2aaa1-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="2aaa1-211">Medan: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="2aaa1-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="2aaa1-212">Operator: lebih daripada</span><span class="sxs-lookup"><span data-stu-id="2aaa1-212">Operator: greater than</span></span>
   - <span data-ttu-id="2aaa1-213">Nilai: 0.6</span><span class="sxs-lookup"><span data-stu-id="2aaa1-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Sediakan segmen pulangan langganan.":::

<span data-ttu-id="2aaa1-215">Kini anda mempunyai segmen yang dikemas kini secara dinamik yang mengenal pasti pelanggan risiko pulangan tinggi untuk perniagaan langganan ini.</span><span class="sxs-lookup"><span data-stu-id="2aaa1-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="2aaa1-216">Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).</span><span class="sxs-lookup"><span data-stu-id="2aaa1-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]