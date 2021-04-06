---
title: Pasang dan konfigurasi Tambahan Kad Pelanggan
description: Pasang dan konfigurasi tambahan Kad Pelanggan untuk Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597338"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="99533-103">Tambahan Kad Pelanggan (pratonton)</span><span class="sxs-lookup"><span data-stu-id="99533-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="99533-104">Dapatkan pandangan 360 darjah pelanggan anda secara langsung dalam aplikasi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="99533-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="99533-105">Lihat demografi, wawasan dan tempoh masa aktiviti dengan Tambahan Kad Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="99533-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="99533-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="99533-106">Prerequisites</span></span>

- <span data-ttu-id="99533-107">Aplikasi Dynamics 365 (seperti Hab Jualan atau Hab Customer Service), versi 9.0 dan kemudian dengan Antara Muka Disatukan didayakan.</span><span class="sxs-lookup"><span data-stu-id="99533-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="99533-108">Profil pelanggan yang [diinges daripada aplikasi Dynamics 365 yang menggunakan Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="99533-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="99533-109">Pengguna Tambahan Kad Pelanggan perlu [ditambah sebagai pengguna](permissions.md) dalam cerapan khalayak.</span><span class="sxs-lookup"><span data-stu-id="99533-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="99533-110">[Mengkonfigurasi keupayaan carian dan penapis](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="99533-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="99533-111">Kawalan demografi: Medan demografi (seperti umur atau jantina) boleh didapati dalam profil pelanggan disatukan.</span><span class="sxs-lookup"><span data-stu-id="99533-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="99533-112">Kawalan pengayaan: Memerlukan [pengayaan](enrichment-hub.md) aktif digunakan pada profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="99533-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="99533-113">Kawalan kepintaran: Memerlukan data yang dihasilkan menggunakan Pembelajaran Mesin Azure ([Ramalan](predictions.md) atau [Model Tersuai](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="99533-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="99533-114">Langkah kawalan: Memerlukan [langkah yang dikonfigurasikan](measures.md).</span><span class="sxs-lookup"><span data-stu-id="99533-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="99533-115">Kawalan garis masa: Memerlukan [aktiviti yang dikonfigurasikan](activities.md).</span><span class="sxs-lookup"><span data-stu-id="99533-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="99533-116">Pasangkan Tambahan Kad Pelanggan</span><span class="sxs-lookup"><span data-stu-id="99533-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="99533-117">Tambahan Kad Pelanggan ialah penyelesaian untuk aplikasi penglibatan pelanggan dalam Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="99533-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="99533-118">Untuk memasang penyelesaian, pergi ke AppSource dan Cari **Kad Pelanggan Dinamik**.</span><span class="sxs-lookup"><span data-stu-id="99533-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="99533-119">Pilih [Tambahan Kad Pelanggan pada AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) dan pilih **Dapatkannya Sekarang**.</span><span class="sxs-lookup"><span data-stu-id="99533-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="99533-120">Anda mungkin perlu mendaftar masuk dengan kelayakan pentadbir anda bagi aplikasi Dynamics 365 untuk memasang penyelesaian.</span><span class="sxs-lookup"><span data-stu-id="99533-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="99533-121">Ia boleh mengambil sedikit masa untuk penyelesaian dipasangkan ke persekitaran anda.</span><span class="sxs-lookup"><span data-stu-id="99533-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="99533-122">Konfigurasi Tambahan Kad Pelanggan</span><span class="sxs-lookup"><span data-stu-id="99533-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="99533-123">Sebagai pentadbir, pergi ke bahagian **Tetapan** dalam Dynamics 365 dan pilih **Penyelesaian**.</span><span class="sxs-lookup"><span data-stu-id="99533-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="99533-124">Pilih pautan **Nama Paparan** untuk penyelesaian **(Pratonton) Tambahan Kad Pelanggan Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="99533-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="99533-125">![Pilih nama paparan](media/select-display-name.png "Pilih nama paparan")</span><span class="sxs-lookup"><span data-stu-id="99533-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="99533-126">Pilih **Log masuk** dan masukkan kelayakan akaun pentadbir yang anda gunakan untuk mengkonfigurasi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="99533-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="99533-127">Periksa sama ada penghalang timbul pelayar tidak menyekat tetingkap pengesahan apabila anda memilih butang **Log masuk**.</span><span class="sxs-lookup"><span data-stu-id="99533-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="99533-128">Pilih persekitaran yang ingin anda ambil data daripadanya.</span><span class="sxs-lookup"><span data-stu-id="99533-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="99533-129">Takrifkan pemetaan medan kepada rekod dalam aplikasi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="99533-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="99533-130">Untuk memetakan dengan kenalan, pilih medan dalam entiti Pelanggan yang sepadan dengan ID entiti kenalan anda.</span><span class="sxs-lookup"><span data-stu-id="99533-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="99533-131">Untuk memetakan dengan akaun, pilih medan dalam entiti Pelanggan yang sepadan dengan ID entiti kenalan anda.</span><span class="sxs-lookup"><span data-stu-id="99533-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="99533-132">![Medan ID Kenalan](media/contact-id-field.png "Medan ID kenalan")</span><span class="sxs-lookup"><span data-stu-id="99533-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="99533-133">Pilih **Simpan konfigurasi** untuk menyimpan tetapan.</span><span class="sxs-lookup"><span data-stu-id="99533-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="99533-134">Seterusnya, anda perlu menugaskan peranan keselamatan dalam Dynamics 365 supaya pengguna boleh menyesuaikan dan melihat kad pelanggan.</span><span class="sxs-lookup"><span data-stu-id="99533-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="99533-135">Dalam Dynamics 365, pergi ke **Tetapan** > **Keselamatan** > **Pengguna**.</span><span class="sxs-lookup"><span data-stu-id="99533-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="99533-136">Pilih pengguna untuk mengedit peranan pengguna dan pilih **Urus peranan**.</span><span class="sxs-lookup"><span data-stu-id="99533-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="99533-137">Peruntukkan peranan **Penyesuai Kad Customer Insights** kepada pengguna yang akan menyesuaikan kandungan yang ditunjukkan pada kad untuk seluruh organisasi.</span><span class="sxs-lookup"><span data-stu-id="99533-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="99533-138">Tambah kawalan Kad Pelanggan pada borang</span><span class="sxs-lookup"><span data-stu-id="99533-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="99533-139">Untuk menambah kawalan Kad Pelanggan kepada borang Kenalan anda, pergi ke **Tetapan** > **Penyesuaian** dalam Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="99533-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="99533-140">Pilih **Sesuaikan Sistem**.</span><span class="sxs-lookup"><span data-stu-id="99533-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="99533-141">Semak lalu kepada entiti **Kenalan**, kembangkannya dan pilih **Borang**.</span><span class="sxs-lookup"><span data-stu-id="99533-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="99533-142">Pilih borang kenalan yang anda mahu tambah kawalan Kad Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="99533-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="99533-143">![Pilih borang Kenalan](media/contact-active-forms.png "Pilih borang Kenalan")</span><span class="sxs-lookup"><span data-stu-id="99533-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="99533-144">Untuk menambah kawalan, di dalam editor borang, seret sebarang medan daripada **Peneroka Medan** ke tempat anda mahu kawalan tersebut timbul.</span><span class="sxs-lookup"><span data-stu-id="99533-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="99533-145">Pilih medan pada borang yang anda baru tambah dan kemudian pilih **Tukar Ciri-Ciri**.</span><span class="sxs-lookup"><span data-stu-id="99533-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="99533-146">Pergi ke tab **Kawalan** dan pilih **Tambah Kawalan**.</span><span class="sxs-lookup"><span data-stu-id="99533-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="99533-147">Pilih salah satu kawalan tersuai yang tersedia dan pilih **Tambah**.</span><span class="sxs-lookup"><span data-stu-id="99533-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="99533-148">Di dalam dialog **Ciri-Ciri Medan**, kosongkan kotak semak **Label paparan pada borang**.</span><span class="sxs-lookup"><span data-stu-id="99533-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="99533-149">Pilih pilihan **Web** untuk kawalan.</span><span class="sxs-lookup"><span data-stu-id="99533-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="99533-150">Untuk kawalan Pengayaan, pilih jenis pengayaan yang anda mahu paparkan dengan mengkonfigurasikan medan **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="99533-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="99533-151">Tambah kawalan pengayaan berasingan untuk setiap jenis pengayaan.</span><span class="sxs-lookup"><span data-stu-id="99533-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="99533-152">Pilih **Simpan** dan **Terbitkan** untuk menerbitkan borang kenalan yang dikemas kini.</span><span class="sxs-lookup"><span data-stu-id="99533-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="99533-153">Pergi ke borang kenalan yang diterbitkan.</span><span class="sxs-lookup"><span data-stu-id="99533-153">Go to the published contact form.</span></span> <span data-ttu-id="99533-154">Anda akan nampak kawalan yang baru ditambah.</span><span class="sxs-lookup"><span data-stu-id="99533-154">You'll see the newly added control.</span></span> <span data-ttu-id="99533-155">Anda mungkin perlu log masuk pertama kali anda menggunakannya.</span><span class="sxs-lookup"><span data-stu-id="99533-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="99533-156">Untuk sesuaikan apa yang anda mahu tunjukkan pada kawalan tersuai, pilih butang edit di sudut kanan atas.</span><span class="sxs-lookup"><span data-stu-id="99533-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="99533-157">Naik Taraf Tambahan Kad Pelanggan</span><span class="sxs-lookup"><span data-stu-id="99533-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="99533-158">Tambahan Kad Pelanggan tidak naik taraf secara automatik.</span><span class="sxs-lookup"><span data-stu-id="99533-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="99533-159">Untuk naik taraf kepada versi terkini, ikuti prosedur ini dalam aplikasi Dynamics 365 yang mempunyai Tambahan yang dipasang.</span><span class="sxs-lookup"><span data-stu-id="99533-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="99533-160">Dalam aplikasi Dynamics 365, pergi ke **Tetapan** > **Penyesuaian** dan pilih **Penyelesaian**.</span><span class="sxs-lookup"><span data-stu-id="99533-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="99533-161">Dalam jadual tambahan, cari **CustomerInsightsCustomerCard** dan pilih baris.</span><span class="sxs-lookup"><span data-stu-id="99533-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="99533-162">Pilih **Gunakan Naik Taraf Penyelesaian** dalam bar tindakan.</span><span class="sxs-lookup"><span data-stu-id="99533-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Naik taraf penyelesaian dalam kawasan Penyesuaian aplikasi Dynamics 365":::

1. <span data-ttu-id="99533-164">Selepas memulakan proses naik taraf, anda akan melihat penunjuk memuat sehingga naik taraf selesai.</span><span class="sxs-lookup"><span data-stu-id="99533-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="99533-165">Jika tiada versi lebih baharu, naik taraf itu akan menunjukkan mesej ralat.</span><span class="sxs-lookup"><span data-stu-id="99533-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]