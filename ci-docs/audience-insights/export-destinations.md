---
title: Eksport data daripada Customer Insights
description: Urus eksport untuk berkongsi data.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016625"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="c8d5b-103">Eksport gambaran keseluruhan (pratonton)</span><span class="sxs-lookup"><span data-stu-id="c8d5b-103">Exports (preview) overview</span></span>

<span data-ttu-id="c8d5b-104">Halaman **Eksport** menunjukkan semua eksport yang dikonfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="c8d5b-105">Eksport berkongsi data tertentu dengan pelbagai aplikasi.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="c8d5b-106">Ia termasuk profil pelanggan atau entiti, skema, dan butiran pemetaan.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="c8d5b-107">Setiap eksport memerlukan [sambungan, yang disediakan oleh pentadbir, untuk menguruskan pengesahan dan akses](connections.md).</span><span class="sxs-lookup"><span data-stu-id="c8d5b-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="c8d5b-108">Pergi ke **Data** > **Eksport** untuk melihat halaman eksport.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="c8d5b-109">Semua peranan pengguna mempunyai akses untuk melihat eksport yang dikonfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="c8d5b-110">Penggunaan medan carian dalam bar perintah untuk mencari eksport dengan nama, nama sambungan atau jenis sambungan mereka.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="c8d5b-111">Sediakan eksport baharu</span><span class="sxs-lookup"><span data-stu-id="c8d5b-111">Set up a new export</span></span>

<span data-ttu-id="c8d5b-112">Untuk menyediakan atau mengedit eksport, anda perlu mempunyai sambungan yang tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="c8d5b-113">Sambungan bergantung kepada [peranan pengguna](permissions.md) anda:</span><span class="sxs-lookup"><span data-stu-id="c8d5b-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="c8d5b-114">Pentadbir mempunyai akses ke semua sambungan.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-114">Administrators have access to all connections.</span></span> <span data-ttu-id="c8d5b-115">Mereka juga boleh mencipta sambungan baharu apabila menyediakan eksport.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="c8d5b-116">Penyumbang boleh mempunyai akses ke sambungan tertentu.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="c8d5b-117">Mereka bergantung kepada pentadbir untuk mengkonfigurasi dan berkongsi sambungan.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="c8d5b-118">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c8d5b-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="c8d5b-119">Penonton hanya boleh melihat eksport sedia ada tetapi tidak menciptanya.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="c8d5b-120">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c8d5b-121">Pilih **Tambah eksport** untuk mencipta destinasi eksport baharu.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="c8d5b-122">Dalam anak tetingkap **Sediakan eksport**, pilih sambungan yang hendak digunakan.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="c8d5b-123">[Sambungan](connections.md) diurus oleh pentadbir.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="c8d5b-124">Berikan butiran yang diperlukan dan pilih **Simpan** untuk mencipta eksport.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="c8d5b-125">Edit eksport</span><span class="sxs-lookup"><span data-stu-id="c8d5b-125">Edit an export</span></span>

1. <span data-ttu-id="c8d5b-126">Pilih elipsis menegak untuk destinasi eksport yang anda mahu edit.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="c8d5b-127">Pilih **Edit** dari menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="c8d5b-128">Ubah nilai yang anda mahu kemas kini dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="c8d5b-129">Lihat Eksport dan butiran eksport</span><span class="sxs-lookup"><span data-stu-id="c8d5b-129">View Exports and export details</span></span>

<span data-ttu-id="c8d5b-130">Selepas membuat destinasi eksport, ia disenaraikan dalam **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="c8d5b-131">Semua pengguna boleh melihat data mana yang dikongsi dan status terkininya.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="c8d5b-132">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c8d5b-133">Pengguna tanpa keizinan edit, pilih **Lihat** dan bukannya **Edit**. Lihat butiran eksport.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="c8d5b-134">Anak tetingkap sisi ini menunjukkan persediaan eksport ini.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="c8d5b-135">Tanpa keizinan edit, anda tidak boleh mengubah nilai.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="c8d5b-136">Pilih **Tutup** untuk kembali ke halaman eksport.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="c8d5b-137">Jalankan eksport atas permintaan</span><span class="sxs-lookup"><span data-stu-id="c8d5b-137">Run exports on demand</span></span>

<span data-ttu-id="c8d5b-138">Selepas mengkonfigurasikan eksport, ia akan berjalan dengan setiap [segar semula berjadual](system.md#schedule-tab) selagi ia mempunyai sambungan kerja.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="c8d5b-139">Untuk mengeksport data tanpa menunggu segar semula berjadual, pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="c8d5b-140">Anda mempunyai dua pilihan:</span><span class="sxs-lookup"><span data-stu-id="c8d5b-140">You have two options:</span></span>

- <span data-ttu-id="c8d5b-141">Untuk menjalankan semua eksport, pilih **Jalankan semua** dalam bar perintah.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="c8d5b-142">Untuk menjalankan eksport tunggal, pilih elipsis (...) pada item senarai dan kemudian pilih **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="c8d5b-143">Alih keluar Eksport</span><span class="sxs-lookup"><span data-stu-id="c8d5b-143">Remove an Export</span></span>

1. <span data-ttu-id="c8d5b-144">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c8d5b-145">Pilih elipsis menegak untuk Eksport yang anda mahu alih keluar.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="c8d5b-146">Pilih **Alih keluar** daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="c8d5b-147">Sahkan pengalihan keluar dengan memilih **Alih keluar** pada skrin pengesahan.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
