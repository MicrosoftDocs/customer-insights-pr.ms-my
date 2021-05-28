---
title: Kad Pelanggan Tambahan untuk aplikasi Dynamics 365
description: Tunjukkan data daripada wawasan khalayak dalam aplikasi Dynamics 365 dengan tambahan ini.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059599"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="0fe30-103">Tambahan Kad Pelanggan (pratonton)</span><span class="sxs-lookup"><span data-stu-id="0fe30-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0fe30-104">Dapatkan pandangan 360 darjah pelanggan anda secara langsung dalam aplikasi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0fe30-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="0fe30-105">Dengan Kad Pelanggan Tambahan dipasang dalam aplikasi Dynamics 365 yang disokong, anda boleh memilih untuk memaparkan demografi, wawasan dan garis masa aktiviti.</span><span class="sxs-lookup"><span data-stu-id="0fe30-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="0fe30-106">Tambahan akan mendapatkan data daripada Customer Insights tanpa mempengaruhi data dalam aplikasi Dynamics 365 yang disambung.</span><span class="sxs-lookup"><span data-stu-id="0fe30-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0fe30-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="0fe30-107">Prerequisites</span></span>

- <span data-ttu-id="0fe30-108">Tambahan hanya berfungsi dengan aplikasi berpandukan model Dynamics 365 seperti Jualan atau Khidmat Pelanggan versi 9.0 dan kemudian.</span><span class="sxs-lookup"><span data-stu-id="0fe30-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="0fe30-109">Untuk memetakan data Dynamics 365 anda ke profil pelanggan wawasan khalayak, data perlu [diinges daripada aplikasi Dynamics 365 menggunakan penyambung Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="0fe30-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="0fe30-110">Semua pengguna Dynamics 365 bagi Kad Pelanggan Tambahan mesti [ditambah sebagai pengguna](permissions.md) dalam wawasan khalayak untuk melihat data.</span><span class="sxs-lookup"><span data-stu-id="0fe30-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="0fe30-111">[Keupayaan carian dan penapis yang dikonfigurasi](search-filter-index.md) dalam wawasan khalayak diperlukan bagi mencari data untuk berfungsi.</span><span class="sxs-lookup"><span data-stu-id="0fe30-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="0fe30-112">Setiap kawalan tambahan bergantung pada data tertentu dalam wawasan khalayak:</span><span class="sxs-lookup"><span data-stu-id="0fe30-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="0fe30-113">Langkah kawalan: Memerlukan [langkah yang dikonfigurasikan](measures.md).</span><span class="sxs-lookup"><span data-stu-id="0fe30-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="0fe30-114">Kawalan kecerdasan: Memerlukan data yang dijana menggunakan [ramalan](predictions.md) atau [model tersuai](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="0fe30-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="0fe30-115">Kawalan demografi: Medan demografi (seperti umur atau jantina) boleh didapati dalam profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="0fe30-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="0fe30-116">Kawalan pengayaan: Memerlukan [pengayaan](enrichment-hub.md) aktif digunakan pada profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="0fe30-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="0fe30-117">Kawalan garis masa: Memerlukan [aktiviti yang dikonfigurasikan](activities.md).</span><span class="sxs-lookup"><span data-stu-id="0fe30-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="0fe30-118">Pasangkan Tambahan Kad Pelanggan</span><span class="sxs-lookup"><span data-stu-id="0fe30-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="0fe30-119">Tambahan Kad Pelanggan ialah penyelesaian untuk aplikasi penglibatan pelanggan dalam Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0fe30-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="0fe30-120">Untuk memasang penyelesaian, pergi ke AppSource dan Cari **Kad Pelanggan Dinamik**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="0fe30-121">Pilih [Tambahan Kad Pelanggan pada AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) dan pilih **Dapatkannya Sekarang**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="0fe30-122">Anda mungkin perlu mendaftar masuk dengan kelayakan pentadbir anda bagi aplikasi Dynamics 365 untuk memasang penyelesaian.</span><span class="sxs-lookup"><span data-stu-id="0fe30-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="0fe30-123">Ia boleh mengambil sedikit masa untuk penyelesaian dipasangkan ke persekitaran anda.</span><span class="sxs-lookup"><span data-stu-id="0fe30-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="0fe30-124">Konfigurasi Tambahan Kad Pelanggan</span><span class="sxs-lookup"><span data-stu-id="0fe30-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="0fe30-125">Sebagai pentadbir, pergi ke bahagian **Tetapan** dalam Dynamics 365 dan pilih **Penyelesaian**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="0fe30-126">Pilih pautan **Nama Paparan** untuk penyelesaian **(Pratonton) Tambahan Kad Pelanggan Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0fe30-127">![Pilih nama paparan](media/select-display-name.png "Pilih nama paparan")</span><span class="sxs-lookup"><span data-stu-id="0fe30-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="0fe30-128">Pilih **Log masuk** dan masukkan kelayakan akaun pentadbir yang anda gunakan untuk mengkonfigurasi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0fe30-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0fe30-129">Periksa sama ada penghalang timbul pelayar tidak menyekat tetingkap pengesahan apabila anda memilih butang **Log masuk**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="0fe30-130">Pilih persekitaran Customer Insights yang anda mahu ambil data daripadanya.</span><span class="sxs-lookup"><span data-stu-id="0fe30-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="0fe30-131">Takrifkan pemetaan medan ke rekod dalam aplikasi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0fe30-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="0fe30-132">Bergantung pada data anda dalam Customer Insights yang anda boleh pilih untuk memetakan pilihan berikut:</span><span class="sxs-lookup"><span data-stu-id="0fe30-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="0fe30-133">Untuk memetakan dengan kenalan, pilih medan dalam entiti Pelanggan yang sepadan dengan ID entiti kenalan anda.</span><span class="sxs-lookup"><span data-stu-id="0fe30-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="0fe30-134">Untuk memetakan dengan akaun, pilih medan dalam entiti Pelanggan yang sepadan dengan ID entiti kenalan anda.</span><span class="sxs-lookup"><span data-stu-id="0fe30-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0fe30-135">![Medan ID Kenalan](media/contact-id-field.png "Medan ID kenalan")</span><span class="sxs-lookup"><span data-stu-id="0fe30-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="0fe30-136">Pilih **Simpan konfigurasi** untuk menyimpan tetapan.</span><span class="sxs-lookup"><span data-stu-id="0fe30-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="0fe30-137">Seterusnya, anda perlu menugaskan peranan keselamatan dalam Dynamics 365 supaya pengguna boleh menyesuaikan dan melihat kad pelanggan.</span><span class="sxs-lookup"><span data-stu-id="0fe30-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="0fe30-138">Dalam Dynamics 365, pergi ke **Tetapan** > **Keselamatan** > **Pengguna**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="0fe30-139">Pilih pengguna untuk mengedit peranan pengguna dan pilih **Urus peranan**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="0fe30-140">Peruntukkan peranan **Penyesuai Kad Customer Insights** kepada pengguna yang akan menyesuaikan kandungan yang ditunjukkan pada kad untuk seluruh organisasi.</span><span class="sxs-lookup"><span data-stu-id="0fe30-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="0fe30-141">Tambah kawalan Kad Pelanggan pada borang</span><span class="sxs-lookup"><span data-stu-id="0fe30-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="0fe30-142">Untuk menambah kawalan Kad Pelanggan kepada borang Kenalan anda, pergi ke **Tetapan** > **Penyesuaian** dalam Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0fe30-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="0fe30-143">Pilih **Sesuaikan Sistem**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="0fe30-144">Semak lalu kepada entiti **Kenalan**, kembangkannya dan pilih **Borang**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="0fe30-145">Pilih borang kenalan yang anda mahu tambah kawalan Kad Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="0fe30-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0fe30-146">![Pilih borang Kenalan](media/contact-active-forms.png "Pilih borang Kenalan")</span><span class="sxs-lookup"><span data-stu-id="0fe30-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="0fe30-147">Untuk menambah kawalan, di dalam editor borang, seret sebarang medan daripada **Peneroka Medan** ke tempat anda mahu kawalan tersebut timbul.</span><span class="sxs-lookup"><span data-stu-id="0fe30-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="0fe30-148">Pilih medan pada borang yang anda baru tambah dan kemudian pilih **Tukar Ciri-Ciri**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="0fe30-149">Pergi ke tab **Kawalan** dan pilih **Tambah Kawalan**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="0fe30-150">Pilih salah satu kawalan tersuai yang tersedia dan pilih **Tambah**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="0fe30-151">Di dalam dialog **Ciri-Ciri Medan**, kosongkan kotak semak **Label paparan pada borang**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="0fe30-152">Pilih pilihan **Web** untuk kawalan.</span><span class="sxs-lookup"><span data-stu-id="0fe30-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="0fe30-153">Untuk kawalan Pengayaan, pilih jenis pengayaan yang anda mahu paparkan dengan mengkonfigurasikan medan **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="0fe30-154">Tambah kawalan pengayaan berasingan untuk setiap jenis pengayaan.</span><span class="sxs-lookup"><span data-stu-id="0fe30-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="0fe30-155">Pilih **Simpan** dan **Terbitkan** untuk menerbitkan borang kenalan yang dikemas kini.</span><span class="sxs-lookup"><span data-stu-id="0fe30-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="0fe30-156">Pergi ke borang kenalan yang diterbitkan.</span><span class="sxs-lookup"><span data-stu-id="0fe30-156">Go to the published contact form.</span></span> <span data-ttu-id="0fe30-157">Anda akan nampak kawalan yang baru ditambah.</span><span class="sxs-lookup"><span data-stu-id="0fe30-157">You'll see the newly added control.</span></span> <span data-ttu-id="0fe30-158">Anda mungkin perlu log masuk pertama kali anda menggunakannya.</span><span class="sxs-lookup"><span data-stu-id="0fe30-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="0fe30-159">Untuk sesuaikan apa yang anda mahu tunjukkan pada kawalan tersuai, pilih butang edit di sudut kanan atas.</span><span class="sxs-lookup"><span data-stu-id="0fe30-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="0fe30-160">Naik Taraf Tambahan Kad Pelanggan</span><span class="sxs-lookup"><span data-stu-id="0fe30-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="0fe30-161">Tambahan Kad Pelanggan tidak naik taraf secara automatik.</span><span class="sxs-lookup"><span data-stu-id="0fe30-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="0fe30-162">Untuk naik taraf kepada versi terkini, ikuti prosedur ini dalam aplikasi Dynamics 365 yang mempunyai Tambahan yang dipasang.</span><span class="sxs-lookup"><span data-stu-id="0fe30-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="0fe30-163">Dalam aplikasi Dynamics 365, pergi ke **Tetapan** > **Penyesuaian** dan pilih **Penyelesaian**.</span><span class="sxs-lookup"><span data-stu-id="0fe30-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="0fe30-164">Dalam jadual tambahan, cari **CustomerInsightsCustomerCard** dan pilih baris.</span><span class="sxs-lookup"><span data-stu-id="0fe30-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="0fe30-165">Pilih **Gunakan Naik Taraf Penyelesaian** dalam bar tindakan.</span><span class="sxs-lookup"><span data-stu-id="0fe30-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Naik taraf penyelesaian dalam kawasan Penyesuaian aplikasi Dynamics 365":::

1. <span data-ttu-id="0fe30-167">Selepas memulakan proses naik taraf, anda akan melihat penunjuk memuat sehingga naik taraf selesai.</span><span class="sxs-lookup"><span data-stu-id="0fe30-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="0fe30-168">Jika tiada versi lebih baharu, naik taraf itu akan menunjukkan mesej ralat.</span><span class="sxs-lookup"><span data-stu-id="0fe30-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
