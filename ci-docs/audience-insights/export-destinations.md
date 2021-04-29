---
title: Eksport data daripada Customer Insights
description: Urus eksport untuk berkongsi data.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896154"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="53567-103">Eksport gambaran keseluruhan (pratonton)</span><span class="sxs-lookup"><span data-stu-id="53567-103">Exports (preview) overview</span></span>

<span data-ttu-id="53567-104">Halaman **Eksport** menunjukkan semua eksport yang dikonfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="53567-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="53567-105">Eksport berkongsi data tertentu dengan pelbagai aplikasi.</span><span class="sxs-lookup"><span data-stu-id="53567-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="53567-106">Ia termasuk profil pelanggan atau entiti, skema, dan butiran pemetaan.</span><span class="sxs-lookup"><span data-stu-id="53567-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="53567-107">Setiap eksport memerlukan [sambungan, yang disediakan oleh pentadbir, untuk menguruskan pengesahan dan akses](connections.md).</span><span class="sxs-lookup"><span data-stu-id="53567-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="53567-108">Sehingga Mac 2021, eksport mencipta sambungan ke perkhidmatan yang sepadan secara automatik.</span><span class="sxs-lookup"><span data-stu-id="53567-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="53567-109">Eksport kini memerlukan [sambungan, dicipta dan dikongsi oleh pentadbir](connections.md) sebelum anda boleh menciptanya.</span><span class="sxs-lookup"><span data-stu-id="53567-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="53567-110">Pergi ke **Data** > **Eksport** untuk melihat halaman eksport.</span><span class="sxs-lookup"><span data-stu-id="53567-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="53567-111">Semua peranan pengguna mempunyai akses untuk melihat eksport yang dikonfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="53567-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="53567-112">Penggunaan medan carian dalam bar perintah untuk mencari eksport dengan nama, nama sambungan atau jenis sambungan mereka.</span><span class="sxs-lookup"><span data-stu-id="53567-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="53567-113">Sediakan eksport baharu</span><span class="sxs-lookup"><span data-stu-id="53567-113">Set up a new export</span></span>

<span data-ttu-id="53567-114">Untuk menyediakan atau mengedit eksport, anda perlu mempunyai sambungan yang tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="53567-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="53567-115">Sambungan bergantung kepada [peranan pengguna](permissions.md) anda:</span><span class="sxs-lookup"><span data-stu-id="53567-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="53567-116">Pentadbir mempunyai akses ke semua sambungan.</span><span class="sxs-lookup"><span data-stu-id="53567-116">Administrators have access to all connections.</span></span> <span data-ttu-id="53567-117">Mereka juga boleh mencipta sambungan baharu apabila menyediakan eksport.</span><span class="sxs-lookup"><span data-stu-id="53567-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="53567-118">Penyumbang boleh mempunyai akses ke sambungan tertentu.</span><span class="sxs-lookup"><span data-stu-id="53567-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="53567-119">Mereka bergantung kepada pentadbir untuk mengkonfigurasi dan berkongsi sambungan.</span><span class="sxs-lookup"><span data-stu-id="53567-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="53567-120">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="53567-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="53567-121">Penonton hanya boleh melihat eksport sedia ada tetapi tidak menciptanya.</span><span class="sxs-lookup"><span data-stu-id="53567-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="53567-122">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="53567-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="53567-123">Pilih **Tambah eksport** untuk mencipta destinasi eksport baharu.</span><span class="sxs-lookup"><span data-stu-id="53567-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="53567-124">Dalam anak tetingkap **Sediakan eksport**, pilih sambungan yang hendak digunakan.</span><span class="sxs-lookup"><span data-stu-id="53567-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="53567-125">[Sambungan](connections.md) diurus oleh pentadbir.</span><span class="sxs-lookup"><span data-stu-id="53567-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="53567-126">Berikan butiran yang diperlukan dan pilih **Simpan** untuk mencipta eksport.</span><span class="sxs-lookup"><span data-stu-id="53567-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="53567-127">Edit eksport</span><span class="sxs-lookup"><span data-stu-id="53567-127">Edit an export</span></span>

1. <span data-ttu-id="53567-128">Pilih elipsis menegak untuk destinasi eksport yang anda mahu edit.</span><span class="sxs-lookup"><span data-stu-id="53567-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="53567-129">Pilih **Edit** dari menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="53567-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="53567-130">Ubah nilai yang anda mahu kemas kini dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="53567-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="53567-131">Lihat Eksport dan butiran eksport</span><span class="sxs-lookup"><span data-stu-id="53567-131">View Exports and export details</span></span>

<span data-ttu-id="53567-132">Selepas membuat destinasi eksport, ia disenaraikan dalam **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="53567-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="53567-133">Semua pengguna boleh melihat data mana yang dikongsi dan status terkininya.</span><span class="sxs-lookup"><span data-stu-id="53567-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="53567-134">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="53567-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="53567-135">Pengguna tanpa keizinan edit, pilih **Lihat** dan bukannya **Edit**. Lihat butiran eksport.</span><span class="sxs-lookup"><span data-stu-id="53567-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="53567-136">Anak tetingkap sisi ini menunjukkan persediaan eksport ini.</span><span class="sxs-lookup"><span data-stu-id="53567-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="53567-137">Tanpa keizinan edit, anda tidak boleh mengubah nilai.</span><span class="sxs-lookup"><span data-stu-id="53567-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="53567-138">Pilih **Tutup** untuk kembali ke halaman eksport.</span><span class="sxs-lookup"><span data-stu-id="53567-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="53567-139">Jalankan eksport atas permintaan</span><span class="sxs-lookup"><span data-stu-id="53567-139">Run exports on demand</span></span>

<span data-ttu-id="53567-140">Selepas mengkonfigurasikan eksport, ia akan berjalan dengan setiap [segar semula berjadual](system.md#schedule-tab) selagi ia mempunyai sambungan kerja.</span><span class="sxs-lookup"><span data-stu-id="53567-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="53567-141">Untuk mengeksport data tanpa menunggu segar semula berjadual, pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="53567-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="53567-142">Anda mempunyai dua pilihan:</span><span class="sxs-lookup"><span data-stu-id="53567-142">You have two options:</span></span>

- <span data-ttu-id="53567-143">Untuk menjalankan semua eksport, pilih **Jalankan semua** dalam bar perintah.</span><span class="sxs-lookup"><span data-stu-id="53567-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="53567-144">Untuk menjalankan eksport tunggal, pilih elipsis (...) pada item senarai dan kemudian pilih **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="53567-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="53567-145">Alih keluar Eksport</span><span class="sxs-lookup"><span data-stu-id="53567-145">Remove an Export</span></span>

1. <span data-ttu-id="53567-146">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="53567-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="53567-147">Pilih elipsis menegak untuk Eksport yang anda mahu alih keluar.</span><span class="sxs-lookup"><span data-stu-id="53567-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="53567-148">Pilih **Alih keluar** daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="53567-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="53567-149">Sahkan pengalihan keluar dengan memilih **Alih keluar** pada skrin pengesahan.</span><span class="sxs-lookup"><span data-stu-id="53567-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
