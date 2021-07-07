---
title: Eksport data daripada Customer Insights
description: Urus eksport untuk berkongsi data.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305489"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="25078-103">Eksport gambaran keseluruhan (pratonton)</span><span class="sxs-lookup"><span data-stu-id="25078-103">Exports (preview) overview</span></span>

<span data-ttu-id="25078-104">Halaman **Eksport** menunjukkan semua eksport yang dikonfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="25078-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="25078-105">Eksport berkongsi data tertentu dengan pelbagai aplikasi.</span><span class="sxs-lookup"><span data-stu-id="25078-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="25078-106">Ia termasuk profil pelanggan atau entiti, skema, dan butiran pemetaan.</span><span class="sxs-lookup"><span data-stu-id="25078-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="25078-107">Setiap eksport memerlukan [sambungan, yang disediakan oleh pentadbir, untuk menguruskan pengesahan dan akses](connections.md).</span><span class="sxs-lookup"><span data-stu-id="25078-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="25078-108">Pergi ke **Data** > **Eksport** untuk melihat halaman eksport.</span><span class="sxs-lookup"><span data-stu-id="25078-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="25078-109">Semua peranan pengguna boleh melihat eksport yang dikonfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="25078-109">All user roles can view configured exports.</span></span> <span data-ttu-id="25078-110">Gunakan medan carian dalam bar perintah untuk mencari eksport mengikut nama, nama sambungan atau jenis sambungan.</span><span class="sxs-lookup"><span data-stu-id="25078-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="25078-111">Sediakan eksport baharu</span><span class="sxs-lookup"><span data-stu-id="25078-111">Set up a new export</span></span>

<span data-ttu-id="25078-112">Untuk menyediakan atau mengedit eksport, anda perlu mempunyai sambungan yang tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="25078-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="25078-113">Sambungan bergantung kepada [peranan pengguna](permissions.md) anda:</span><span class="sxs-lookup"><span data-stu-id="25078-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="25078-114">Pentadbir mempunyai akses ke semua sambungan.</span><span class="sxs-lookup"><span data-stu-id="25078-114">Administrators have access to all connections.</span></span> <span data-ttu-id="25078-115">Mereka juga boleh mencipta sambungan baharu apabila menyediakan eksport.</span><span class="sxs-lookup"><span data-stu-id="25078-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="25078-116">Penyumbang boleh mempunyai akses ke sambungan tertentu.</span><span class="sxs-lookup"><span data-stu-id="25078-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="25078-117">Mereka bergantung kepada pentadbir untuk mengkonfigurasi dan berkongsi sambungan.</span><span class="sxs-lookup"><span data-stu-id="25078-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="25078-118">Senarai eksport menunjukkan penyumbang sama ada mereka boleh mengedit atau hanya melihat eksport dalam lajur **Keizinan anda**.</span><span class="sxs-lookup"><span data-stu-id="25078-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="25078-119">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="25078-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="25078-120">Penonton hanya boleh melihat eksport sedia ada tetapi tidak menciptanya.</span><span class="sxs-lookup"><span data-stu-id="25078-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="25078-121">Tentukan eksport baharu</span><span class="sxs-lookup"><span data-stu-id="25078-121">Define a new export</span></span>

1. <span data-ttu-id="25078-122">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="25078-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="25078-123">Pilih **Tambah eksport** untuk mencipta eksport baharu.</span><span class="sxs-lookup"><span data-stu-id="25078-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="25078-124">Dalam anak tetingkap **Sediakan eksport**, pilih sambungan yang hendak digunakan.</span><span class="sxs-lookup"><span data-stu-id="25078-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="25078-125">[Sambungan](connections.md) diurus oleh pentadbir.</span><span class="sxs-lookup"><span data-stu-id="25078-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="25078-126">Berikan butiran yang diperlukan dan pilih **Simpan** untuk mencipta eksport.</span><span class="sxs-lookup"><span data-stu-id="25078-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="25078-127">Tentukan eksport baharu berdasarkan eksport yang sedia ada</span><span class="sxs-lookup"><span data-stu-id="25078-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="25078-128">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="25078-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="25078-129">Dalam senarai eksport, pilih eksport yang ingin anda duplikasi.</span><span class="sxs-lookup"><span data-stu-id="25078-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="25078-130">Pilih **Cipta duplikasi** dalam bar perintah untuk membuka anak tetingkap **Sediakan eksport** dengan butiran eksport yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="25078-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="25078-131">Semak dan sesuaikan eksport dan pilih **Simpan** untuk mencipta eksport baharu.</span><span class="sxs-lookup"><span data-stu-id="25078-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="25078-132">Edit eksport</span><span class="sxs-lookup"><span data-stu-id="25078-132">Edit an export</span></span>

1. <span data-ttu-id="25078-133">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="25078-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="25078-134">Dalam senarai eksport, pilih eksport yang ingin anda edit.</span><span class="sxs-lookup"><span data-stu-id="25078-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="25078-135">Pilih **Edit** dalam bar perintah.</span><span class="sxs-lookup"><span data-stu-id="25078-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="25078-136">Ubah nilai yang anda mahu kemas kini dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="25078-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="25078-137">Lihat eksport dan butiran eksport</span><span class="sxs-lookup"><span data-stu-id="25078-137">View exports and export details</span></span>

<span data-ttu-id="25078-138">Selepas mencipta destinasi eksport, ia disenaraikan dalam **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="25078-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="25078-139">Semua pengguna boleh melihat data mana yang dikongsi dan status terkininya.</span><span class="sxs-lookup"><span data-stu-id="25078-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="25078-140">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="25078-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="25078-141">Pengguna tanpa keizinan mengedit, pilih **Lihat** dan bukannya **Edit** untuk melihat butiran eksport.</span><span class="sxs-lookup"><span data-stu-id="25078-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="25078-142">Anak tetingkap sisi menunjukkan konfigurasi eksport.</span><span class="sxs-lookup"><span data-stu-id="25078-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="25078-143">Tanpa keizinan edit, anda tidak boleh mengubah nilai.</span><span class="sxs-lookup"><span data-stu-id="25078-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="25078-144">Pilih **Tutup** untuk kembali ke halaman eksport.</span><span class="sxs-lookup"><span data-stu-id="25078-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="25078-145">Jadualkan dan jalankan eksport</span><span class="sxs-lookup"><span data-stu-id="25078-145">Schedule and run exports</span></span>

<span data-ttu-id="25078-146">Setiap eksport yang dikonfigurasikan mempunyai jadual segar semula.</span><span class="sxs-lookup"><span data-stu-id="25078-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="25078-147">Semasa segar semula, sistem mencari data baharu atau yang dikemas kini untuk disertakan dalam eksport.</span><span class="sxs-lookup"><span data-stu-id="25078-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="25078-148">Secara lalai, eksport dijalankan sebagai sebahagian daripada setiap [segar semula sistem yang dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="25078-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="25078-149">Anda boleh menyesuaikan jadual segar semula atau mematikan proses itu untuk menjalankan eksport secara manual.</span><span class="sxs-lookup"><span data-stu-id="25078-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="25078-150">Jadual eksport bergantung pada keadaan persekitaran anda.</span><span class="sxs-lookup"><span data-stu-id="25078-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="25078-151">Jika terdapat kemas kini yang sedang berjalan pada [kebergantungan](system.md#refresh-policies) apabila eksport yang dijadualkan harus bermula, sistem akan melengkapkan kemas kini terlebih dahulu dan kemudian menjalankan eksport.</span><span class="sxs-lookup"><span data-stu-id="25078-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="25078-152">Anda boleh melihat masa eksport disegarkan semula buat kali terakhir dalam lajur **Disegar semula**.</span><span class="sxs-lookup"><span data-stu-id="25078-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="25078-153">Jadualkan eksport</span><span class="sxs-lookup"><span data-stu-id="25078-153">Schedule exports</span></span>

<span data-ttu-id="25078-154">Anda boleh menentukan jadual segar semula tersuai untuk eksport individu atau beberapa eksport secara serentak.</span><span class="sxs-lookup"><span data-stu-id="25078-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="25078-155">Jadual yang ditentukan pada masa ini disenaraikan dalam lajur **Jadual** senarai eksport.</span><span class="sxs-lookup"><span data-stu-id="25078-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="25078-156">Keizinan untuk menukar jadual adalah sama seperti untuk [mengedit dan menentukan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="25078-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="25078-157">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="25078-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="25078-158">Pilih eksport yang ingin anda jadualkan.</span><span class="sxs-lookup"><span data-stu-id="25078-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="25078-159">Pilih **Jadual** dalam bar perintah.</span><span class="sxs-lookup"><span data-stu-id="25078-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="25078-160">Dalam anak tetingkap **Eksport jadual**, tetapkan **Jalankan jadual** ke **Hidup** untuk menjalankan eksport secara automatik.</span><span class="sxs-lookup"><span data-stu-id="25078-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="25078-161">Tetapkan ke **Mati** untuk menyegarkan semula jadual secara manual.</span><span class="sxs-lookup"><span data-stu-id="25078-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="25078-162">Untuk eksport yang disegarkan semula secara automatik, pilih nilai **Ulangan** dan tentukan butiran untuk eksport tersebut.</span><span class="sxs-lookup"><span data-stu-id="25078-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="25078-163">Masa yang ditentukan terpakai kepada semua tika ulangan.</span><span class="sxs-lookup"><span data-stu-id="25078-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="25078-164">Sudah tiba masanya eksport harus mula menyegarkan semula.</span><span class="sxs-lookup"><span data-stu-id="25078-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="25078-165">Gunakan dan aktifkan perubahan anda dengan memilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="25078-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="25078-166">Apabila mengedit jadual untuk beberapa eksport, anda perlu membuat pilihan di bawah **Simpan atau ganti jadual**:</span><span class="sxs-lookup"><span data-stu-id="25078-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="25078-167">**Simpan jadual individu**: Teruskan dengan jadual yang ditentukan sebelumnya untuk eksport yang dipilih dan hanya nyahdayakan atau dayakan jadual tersebut.</span><span class="sxs-lookup"><span data-stu-id="25078-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="25078-168">**Tentukan jadual baharu untuk semua eksport yang dipilih**: Gantikan jadual sedia ada bagi eksport yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="25078-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="25078-169">Jalankan eksport atas permintaan</span><span class="sxs-lookup"><span data-stu-id="25078-169">Run exports on demand</span></span>

<span data-ttu-id="25078-170">Untuk mengeksport data tanpa menunggu segar semula berjadual, pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="25078-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="25078-171">Untuk menjalankan semua eksport, pilih **Jalankan semua** dalam bar perintah.</span><span class="sxs-lookup"><span data-stu-id="25078-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="25078-172">Tindakan ini hanya akan menjalankan eksport yang mempunyai jadual aktif.</span><span class="sxs-lookup"><span data-stu-id="25078-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="25078-173">Untuk menjalankan eksport tunggal, pilih dalam senarai dan pilih **Jalankan** dalam bar perintah.</span><span class="sxs-lookup"><span data-stu-id="25078-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="25078-174">Itulah cara anda menjalankan eksport tanpa jadual aktif.</span><span class="sxs-lookup"><span data-stu-id="25078-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="25078-175">Alih keluar Eksport</span><span class="sxs-lookup"><span data-stu-id="25078-175">Remove an Export</span></span>

1. <span data-ttu-id="25078-176">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="25078-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="25078-177">Pilih eksport yang ingin anda alih keluar.</span><span class="sxs-lookup"><span data-stu-id="25078-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="25078-178">Pilih **Alih Keluar** dalam bar perintah.</span><span class="sxs-lookup"><span data-stu-id="25078-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="25078-179">Sahkan pengalihan keluar dengan memilih **Alih keluar** pada skrin pengesahan.</span><span class="sxs-lookup"><span data-stu-id="25078-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
