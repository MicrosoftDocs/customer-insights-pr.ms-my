---
title: Cari dan tapis profil pelanggan
description: Cari maklumat dengan cepat tentang profil pelanggan disatukan dan tapis untuk atribut tertentu.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597154"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="e32c5-103">Profil pelanggan: Indeks carian & tapis</span><span class="sxs-lookup"><span data-stu-id="e32c5-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="e32c5-104">Hasil daripada menyatukan data pelanggan anda ialah entiti Profil Pelanggan yang menyediakan pandangan disatukan ke dalam jumlah dasar pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="e32c5-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="e32c5-105">Untuk [mendapatkan maklumat dengan pantas mengenai pelanggan atau kumpulan pelanggan tertentu](customer-profiles.md), anda boleh mengkonfigurasi keupayaan **Carian** dan **Penapis** pada halaman **Pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="e32c5-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="e32c5-106">Baca untuk mengetahui cara pentadbir boleh mengedit atribut pada halaman **Indeks carian & penapis**, yang tersedia kepada pengguna untuk carian dan penapisan.</span><span class="sxs-lookup"><span data-stu-id="e32c5-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e32c5-107">![Penapis carian](media/search-filter.png "Penapis carian")</span><span class="sxs-lookup"><span data-stu-id="e32c5-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="e32c5-108">Tambah medan dan tentukan atribut</span><span class="sxs-lookup"><span data-stu-id="e32c5-108">Add fields and specify attributes</span></span>

<span data-ttu-id="e32c5-109">Jika ia ialah kali pertama anda mentakrifkan atribut yang boleh dicari sebagai pentadbir, anda perlu mentakrifkan medan berindeks terlebih dahulu.</span><span class="sxs-lookup"><span data-stu-id="e32c5-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="e32c5-110">Kami mencadangkan anda memilih semua atribut yang pengguna boleh mencari dan menapis pelanggan pada halaman **Pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="e32c5-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="e32c5-111">Anda hanya boleh menentukan atribut yang wujud di dalam entiti Profil Pelanggan yang anda cipta semasa proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="e32c5-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="e32c5-112">Buka halaman **Pelanggan** dan pilih **Cari & indeks penapis**.</span><span class="sxs-lookup"><span data-stu-id="e32c5-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="e32c5-113">Pilih **+ Tambah** untuk menentukan medan yang berindeks.</span><span class="sxs-lookup"><span data-stu-id="e32c5-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="e32c5-114">Pilih atribut di dalam senarai yang anda mahu tambah sebagai medan berindeks.</span><span class="sxs-lookup"><span data-stu-id="e32c5-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="e32c5-115">Anda sentiasa boleh tambah lebih banyak atribut dengan memilih **Tambah**.</span><span class="sxs-lookup"><span data-stu-id="e32c5-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="e32c5-116">Anda juga boleh mengalih keluar sebarang atribut yang dipilih dengan memilih simbol **Alih Keluar**.</span><span class="sxs-lookup"><span data-stu-id="e32c5-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="e32c5-117">Terokai jadual medan pelanggan Berindeks</span><span class="sxs-lookup"><span data-stu-id="e32c5-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="e32c5-118">Maklumat berikut ditunjukkan di dalam jadual.</span><span class="sxs-lookup"><span data-stu-id="e32c5-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="e32c5-119">**Nama**: Mewakili nama atribut yang muncul dalam entiti Profil Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e32c5-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="e32c5-120">**Jenis data**: Menentukan sama ada jenis data ialah rentetan, nombor atau tarikh.</span><span class="sxs-lookup"><span data-stu-id="e32c5-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="e32c5-121">**Disertakan dalam carian**: Menentukan sama ada atribut ini boleh digunakan untuk mencari pelanggan pada halaman **Pelanggan** menggunakan medan **Carian**.</span><span class="sxs-lookup"><span data-stu-id="e32c5-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="e32c5-122">**Tambah Penapis**: Kawalan untuk mentakrifkan cara atribut ini boleh digunakan untuk menapis pada halaman **Pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="e32c5-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="e32c5-123">Mengedit pilihan penapisan untuk atribut yang diberikan</span><span class="sxs-lookup"><span data-stu-id="e32c5-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="e32c5-124">Menu **Penapis** pada halaman **Pelanggan** boleh termasuk bilangan peringkat atribut (contohnya, menapis pelanggan berdasarkan kumpulan umur berbeza).</span><span class="sxs-lookup"><span data-stu-id="e32c5-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="e32c5-125">Pilih **Tambah Penapis** untuk atribut tertentu pada halaman **Indeks Carian & penapis**.</span><span class="sxs-lookup"><span data-stu-id="e32c5-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="e32c5-126">Anda boleh mentakrifkan bilangan keputusan dan arahan yang akan diaturkan.</span><span class="sxs-lookup"><span data-stu-id="e32c5-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="e32c5-127">Bergantung pada jenis data atribut, salah satu daripada anak tetingkap berikut muncul.</span><span class="sxs-lookup"><span data-stu-id="e32c5-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="e32c5-128">Atribut jenis rentetan: Tentukan bilangan keputusan yang dikehendaki pada anak tetingkap **Pilihan penapis rentetan** dan dasar pesanan yang akan diaturkan.</span><span class="sxs-lookup"><span data-stu-id="e32c5-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="e32c5-129">Atribut jenis berangka: Tentukan selang yang termasuk pada anak tetingkap **Pilihan penapis nombor** dan dasar pesanan yang akan diaturkan.</span><span class="sxs-lookup"><span data-stu-id="e32c5-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="e32c5-130">Atribut jenis tarikh:  Tentukan selang yang termasuk pada anak tetingkap **Pilihan penapis tarikh** dan dasar pesanan yang akan diaturkan.</span><span class="sxs-lookup"><span data-stu-id="e32c5-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="e32c5-131">Pilih **Simpan** untuk menggunakan perubahan anda.</span><span class="sxs-lookup"><span data-stu-id="e32c5-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="e32c5-132">Pilih **Jalankan** sebaik sahaja anda bersedia untuk menggunakan tetapan anda.</span><span class="sxs-lookup"><span data-stu-id="e32c5-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e32c5-133">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="e32c5-133">Next steps</span></span>

<span data-ttu-id="e32c5-134">Pergi ke halaman **Pelanggan** untuk mencari profil pelanggan atau menggunakan medan diindeks untuk melihat subset semua profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e32c5-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]