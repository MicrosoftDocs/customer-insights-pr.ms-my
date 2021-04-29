---
title: Sambungan ke perkhidmatan lain daripada Customer Insights.
description: Kongsi data ke perkhidmatan lain.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896108"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="8c547-103">Gambaran keseluruhan sambungan (pratonton)</span><span class="sxs-lookup"><span data-stu-id="8c547-103">Connections (preview) overview</span></span>

<span data-ttu-id="8c547-104">Sambungan adalah kunci untuk mendayakan perkongsian data ke dan daripada Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8c547-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="8c547-105">Setiap sambungan mewujudkan perkongsian data dengan perkhidmatan tertentu.</span><span class="sxs-lookup"><span data-stu-id="8c547-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="8c547-106">Sambungan adalah asas untuk [mengkonfigurasikan pengayaan pihak ketiga](enrichment-hub.md) dan [mengkonfigurasi eksport](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8c547-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="8c547-107">Sambungan yang sama boleh digunakan beberapa kali.</span><span class="sxs-lookup"><span data-stu-id="8c547-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="8c547-108">Sebagai contoh, satu sambungan ke Dynamics 365 Marketing berfungsi untuk berbilang eksport dan satu sambungan Leadspace boleh digunakan untuk beberapa pengayaan.</span><span class="sxs-lookup"><span data-stu-id="8c547-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="8c547-109">Pergi ke **Pentadbir** > **Sambungan** untuk mencipta dan melihat sambungan.</span><span class="sxs-lookup"><span data-stu-id="8c547-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="8c547-110">Tab **Sambungan** menunjukkan anda semua sambungan aktif.</span><span class="sxs-lookup"><span data-stu-id="8c547-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="8c547-111">Senarai menunjukkan baris untuk setiap sambungan.</span><span class="sxs-lookup"><span data-stu-id="8c547-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="8c547-112">Dapatkan gambaran keseluruhan pantas, perihalan, dan ketahui perkara yang boleh anda lakukan dengan setiap pilihan kebolehsambungan pad tab **Temui**.</span><span class="sxs-lookup"><span data-stu-id="8c547-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="8c547-113">Eksport</span><span class="sxs-lookup"><span data-stu-id="8c547-113">Exports</span></span>

<span data-ttu-id="8c547-114">Hanya pentadbir boleh mengkonfigurasikan sambungan baharu, tetapi mereka boleh memberikan akses kepada penyumbang untuk menggunakan sambungan yang sedia ada.</span><span class="sxs-lookup"><span data-stu-id="8c547-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="8c547-115">Pentadbir mengawal tempat data boleh pergi, penyumbang mentakrifkan muatan dan kekerapan untuk memenuhi keperluan mereka.</span><span class="sxs-lookup"><span data-stu-id="8c547-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="8c547-116">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8c547-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="8c547-117">Pengayaan</span><span class="sxs-lookup"><span data-stu-id="8c547-117">Enrichments</span></span>

<span data-ttu-id="8c547-118">Hanya pentadbir boleh mengkonfigurasikan sambungan baharu tetapi sambungan yang dicipta sentiasa tersedia untuk pentadbir dan penyumbang.</span><span class="sxs-lookup"><span data-stu-id="8c547-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="8c547-119">Pentadbir mengurus kelayakan dan memberi keizinan kepada pemindahan data.</span><span class="sxs-lookup"><span data-stu-id="8c547-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="8c547-120">Sambungan boleh digunakan oleh pentadbir dan penyumbang untuk pengayaan.</span><span class="sxs-lookup"><span data-stu-id="8c547-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="8c547-121">Tambah sambungan baharu</span><span class="sxs-lookup"><span data-stu-id="8c547-121">Add a new connection</span></span>

<span data-ttu-id="8c547-122">Untuk menambah sambungan, anda perlu mempunyai [keizinan pentadbir](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8c547-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="8c547-123">Jika anda bersambung ke perkhidmatan Microsoft lain, kami menganggap kedua-dua perkhidmatan berada dalam organisasi yang sama.</span><span class="sxs-lookup"><span data-stu-id="8c547-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="8c547-124">Pergi ke **Pentadbir** > **Sambungan (pratonton)**.</span><span class="sxs-lookup"><span data-stu-id="8c547-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="8c547-125">Pergi ke tab **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="8c547-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="8c547-126">Pilih **Tambah sambungan** untuk mencipta sambungan baharu.</span><span class="sxs-lookup"><span data-stu-id="8c547-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="8c547-127">Pilih daripada menu juntai bawah untuk jenis sambungan yang anda mahu cipta.</span><span class="sxs-lookup"><span data-stu-id="8c547-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="8c547-128">Dalam anak tetingkap **Sediakan sambungan**, berikan butiran yang diperlukan.</span><span class="sxs-lookup"><span data-stu-id="8c547-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="8c547-129">**Nama paparan** dan jenis sambungan yang menerangkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="8c547-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="8c547-130">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="8c547-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="8c547-131">Medan sebenar bergantung pada jenis perkhidmatan yang anda bersambung.</span><span class="sxs-lookup"><span data-stu-id="8c547-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="8c547-132">Anda boleh mengetahui tentang butiran jenis sambungan khusus dalam artikel mengenai perkhidmatan sasaran.</span><span class="sxs-lookup"><span data-stu-id="8c547-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="8c547-133">Untuk mencipta sambungan, pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="8c547-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="8c547-134">Anda juga boleh memilih **Sediakan** pada jubin pada tab **Temui**.</span><span class="sxs-lookup"><span data-stu-id="8c547-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="8c547-135">Benarkan penyumbang untuk menggunakan sambungan untuk eksport</span><span class="sxs-lookup"><span data-stu-id="8c547-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="8c547-136">Apabila menyediakan atau mengedit sambungan eksport, anda memilih pengguna yang dibenarkan untuk menggunakan sambungan khusus ini untuk mentakrifkan [eksport](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8c547-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="8c547-137">Secara lalai, sambungan tersedia kepada pengguna yang mempunyai peranan pentadbir.</span><span class="sxs-lookup"><span data-stu-id="8c547-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="8c547-138">Anda boleh mengubah tetapan ini di bawah **Pilih individu yang boleh menggunakan sambungan ini** dan membenarkan pengguna yang mempunyai peranan penyumbang untuk menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="8c547-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="8c547-139">Penyumbang tidak akan dapat melihat atau mengedit sambungan.</span><span class="sxs-lookup"><span data-stu-id="8c547-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="8c547-140">Mereka hanya akan melihat nama paparan dan jenis apabila mencipta eksport.</span><span class="sxs-lookup"><span data-stu-id="8c547-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="8c547-141">Dengan berkongsi sambungan, anda membenarkan penyumbang untuk menggunakan sambungan.</span><span class="sxs-lookup"><span data-stu-id="8c547-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="8c547-142">Penyumbang akan melihat sambungan dikongsi apabila mereka menyediakan eksport.</span><span class="sxs-lookup"><span data-stu-id="8c547-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="8c547-143">Mereka boleh mengurus setiap eksport yang menggunakan sambungan khusus ini.</span><span class="sxs-lookup"><span data-stu-id="8c547-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="8c547-144">Anda boleh mengubah tetapan ini di samping mengekalkan eksport yang telah ditakrifkan oleh penyumbang.</span><span class="sxs-lookup"><span data-stu-id="8c547-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="8c547-145">Edit sambungan</span><span class="sxs-lookup"><span data-stu-id="8c547-145">Edit a connection</span></span>

1. <span data-ttu-id="8c547-146">Pergi ke **Pentadbir** > **Sambungan (pratonton)**.</span><span class="sxs-lookup"><span data-stu-id="8c547-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="8c547-147">Pergi ke tab **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="8c547-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="8c547-148">Pilih elipsis menegak untuk sambungan yang anda mahu edit.</span><span class="sxs-lookup"><span data-stu-id="8c547-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="8c547-149">Pilih **Edit**.</span><span class="sxs-lookup"><span data-stu-id="8c547-149">Select **Edit**.</span></span>

1. <span data-ttu-id="8c547-150">Ubah nilai yang anda mahu kemas kini dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="8c547-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="8c547-151">Alih keluar sambungan</span><span class="sxs-lookup"><span data-stu-id="8c547-151">Remove a connection</span></span>

<span data-ttu-id="8c547-152">Jika sambungan yang anda keluarkan digunakan oleh pengayaan atau eksport, anda perlu mengalih atau mengalihnya keluar.</span><span class="sxs-lookup"><span data-stu-id="8c547-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="8c547-153">Dialog yang dialih keluar akan membimbing anda kepada pengayaan atau eksport yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="8c547-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="8c547-154">Pengayaan dan eksport yang dialih menjadi tidak aktif.</span><span class="sxs-lookup"><span data-stu-id="8c547-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="8c547-155">Anda mengaktifkan semula dengan menambah sambungan lain kepadanya pada halaman [Pengayaan](enrichment-hub.md) atau [Eksport](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8c547-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="8c547-156">Pergi ke **Pentadbir** > **Sambungan (pratonton)**.</span><span class="sxs-lookup"><span data-stu-id="8c547-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="8c547-157">Pergi ke tab **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="8c547-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="8c547-158">Pilih elipsis menegak untuk sambungan yang anda mahu alih keluar.</span><span class="sxs-lookup"><span data-stu-id="8c547-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="8c547-159">Pilih **Alih keluar** daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="8c547-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="8c547-160">Dialog pengesahan muncul.</span><span class="sxs-lookup"><span data-stu-id="8c547-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="8c547-161">Jika terdapat pengayaan atau eksport menggunakan sambungan ini, pilih butang untuk melihat apa yang menggunakan sambungan.</span><span class="sxs-lookup"><span data-stu-id="8c547-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="8c547-162">**Eksport:** Anda boleh memilih sama ada untuk mengalih keluar atau nyahsambung eksport supaya dapat mengalih keluar sambungan.</span><span class="sxs-lookup"><span data-stu-id="8c547-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="8c547-163">Untuk memutuskan sambungan eksport, pentadbir boleh menggunakan tindakan **Putuskan sambungan**.</span><span class="sxs-lookup"><span data-stu-id="8c547-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="8c547-164">Tindakan ini tersedia untuk individu dan berbilang eksport terpilih.</span><span class="sxs-lookup"><span data-stu-id="8c547-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="8c547-165">Dengan memutuskan sambungan, anda mengekalkan konfigurasi eksport, tetapi ia tidak akan berjalan sehingga sambungan yang lain ditambah padanya.</span><span class="sxs-lookup"><span data-stu-id="8c547-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="8c547-166">**Pengayaan:** Anda boleh memilih sama ada untuk mengalih keluar atau menyahaktif pengayaan supaya dapat mengalih keluar sambungan.</span><span class="sxs-lookup"><span data-stu-id="8c547-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="8c547-167">Sebaik sahaja sambungan tidak mempunyai kebergantungan, pergi kembali ke **Pentadbir** > **Sambungan** dan cuba alih keluar sambungan semula.</span><span class="sxs-lookup"><span data-stu-id="8c547-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="8c547-168">Untuk mengesahkan pemadaman, pilih **Alih keluar**.</span><span class="sxs-lookup"><span data-stu-id="8c547-168">To confirm the deletion select **Remove**.</span></span>

