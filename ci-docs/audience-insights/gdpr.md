---
title: Permintaan Hak Subjek Data (DSR) di bawah GDPR | Microsoft Docs
description: Respons kepada Permintaan Subjek Data untuk keupayaan Insights khalayak Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9c453c9b416bff0e6362a8ccf7ff534f4efa1e00
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597522"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="e2d43-103">Permintaan Hak Subjek Data (DSR) di bawah GDPR</span><span class="sxs-lookup"><span data-stu-id="e2d43-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="e2d43-104">Respons kepada permintaan padam subjek data GDPR untuk keupayaan Insights khalayak Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e2d43-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="e2d43-105">"Hak untuk pemadaman" dengan memadam data peribadi daripada data pelanggan organisasi adalah perlindungan utama dalam Peraturan Perlindungan Data Umum (GDPR).</span><span class="sxs-lookup"><span data-stu-id="e2d43-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="e2d43-106">Mengeluarkan data peribadi termasuk mengeluarkan semua data peribadi dan log janaan sistem kecuali maklumat log audit.</span><span class="sxs-lookup"><span data-stu-id="e2d43-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="e2d43-107">Urus permintaan padam subjek data</span><span class="sxs-lookup"><span data-stu-id="e2d43-107">Manage data subject delete requests</span></span>

<span data-ttu-id="e2d43-108">Insights khalayak menawarkan pengalaman dalam produk untuk memadamkan data peribadi untuk pelanggan atau pengguna khusus:</span><span class="sxs-lookup"><span data-stu-id="e2d43-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="e2d43-109">**Urus permintaan padam untuk data pelanggan**: Data pelanggan dalam Customer Insights telah ditelan daripada sumber data asal luaran kepada Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e2d43-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="e2d43-110">Semua permintaan penghapusan GDPR mesti dilaksanakan di dalam sumber data asal.</span><span class="sxs-lookup"><span data-stu-id="e2d43-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="e2d43-111">**Urus permintaan padam untuk data pengguna Customer Insights**: Data untuk pengguna dicipta oleh Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e2d43-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="e2d43-112">Semua permintaan penghapusan GDPR mesti dilakukan di dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e2d43-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="e2d43-113">Urus permintaan penghapusan untuk data pelanggan</span><span class="sxs-lookup"><span data-stu-id="e2d43-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="e2d43-114">Pentadbir Customer Insights boleh mengikut langkah ini untuk mengalih keluar data pelanggan yang telah dipadamkan dalam sumber data:</span><span class="sxs-lookup"><span data-stu-id="e2d43-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="e2d43-115">Daftar masuk ke Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e2d43-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="e2d43-116">Dalam Insights khalayak, pergi ke **Data** > **Sumber data**</span><span class="sxs-lookup"><span data-stu-id="e2d43-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="e2d43-117">Untuk setiap sumber data dalam senarai yang mengandungi data pelanggan yang dipadamkan:</span><span class="sxs-lookup"><span data-stu-id="e2d43-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="e2d43-118">Pilih (...) dan kemudian pilih **Muat Semula**.</span><span class="sxs-lookup"><span data-stu-id="e2d43-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="e2d43-119">Semak status sumber data di bawah **Status**.</span><span class="sxs-lookup"><span data-stu-id="e2d43-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="e2d43-120">Tanda semak bermaksud segar semula berjaya.</span><span class="sxs-lookup"><span data-stu-id="e2d43-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="e2d43-121">Segi tiga amaran bermaksud berlaku suatu kesalahan.</span><span class="sxs-lookup"><span data-stu-id="e2d43-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="e2d43-122">Jika segi tiga amaran dipaparkan, hubungi D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e2d43-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e2d43-123">![Urus permintaan penghapusan GDPR untuk data pelanggan](media/gdpr-data-sources.png "Urus permintaan penghapusan GDPR untuk data pelanggan")</span><span class="sxs-lookup"><span data-stu-id="e2d43-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="e2d43-124">Urus permintaan padam untuk data pengguna</span><span class="sxs-lookup"><span data-stu-id="e2d43-124">Manage delete requests for user data</span></span>

<span data-ttu-id="e2d43-125">Pentadbir Customer Insights boleh mengikut langkah ini untuk menghapuskan data pengguna Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="e2d43-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="e2d43-126">Daftar masuk ke Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e2d43-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="e2d43-127">Dalam Insights khalayak, pergi ke **Pentadbir** > **Keizinan**.</span><span class="sxs-lookup"><span data-stu-id="e2d43-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="e2d43-128">Tandakan kotak semak untuk pengguna yang anda mahu hapuskan.</span><span class="sxs-lookup"><span data-stu-id="e2d43-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="e2d43-129">Pilih **Alih keluar**.</span><span class="sxs-lookup"><span data-stu-id="e2d43-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e2d43-130">![Pengendalian permintaan padam GDPR untuk data pengguna](media/gdpr-permissions.png "Pengendalian permintaan padam GDPR untuk data pengguna")</span><span class="sxs-lookup"><span data-stu-id="e2d43-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="e2d43-131">Respons kepada permintaan export subjek data GDPR</span><span class="sxs-lookup"><span data-stu-id="e2d43-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="e2d43-132">Sebagai sebahagian daripada komitmen kami untuk bekerjasama dengan anda dalam perjalanan anda kepada Peraturan Perlindungan Data Umum (GDPR), kami telah membangunkan dokumentasi untuk membantu persediaan anda.</span><span class="sxs-lookup"><span data-stu-id="e2d43-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="e2d43-133">Dokumentasi ini memerihalkan langkah yang boleh anda lakukan hari ini untuk menyokong pematuhan GDPR apabila menggunakan Insights khalayak.</span><span class="sxs-lookup"><span data-stu-id="e2d43-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="e2d43-134">Urus permintaan eksport dan pandangan</span><span class="sxs-lookup"><span data-stu-id="e2d43-134">Manage export and view requests</span></span>

<span data-ttu-id="e2d43-135">Hak kemudahalihan data membenarkan subjek data untuk meminta salinan data peribadi mereka dalam format elektronik (ditakrifkan sebagai "berstruktur, biasa digunakan, mesin boleh dibaca dan format saling boleh kendali") yang boleh dihantar kepada pengawal data yang lain.</span><span class="sxs-lookup"><span data-stu-id="e2d43-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="e2d43-136">Eksport data pelanggan (pentadbir penyewa)</span><span class="sxs-lookup"><span data-stu-id="e2d43-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="e2d43-137">Pentadbir penyewa boleh mengikuti langkah-langkah ini untuk mengeksport data:</span><span class="sxs-lookup"><span data-stu-id="e2d43-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="e2d43-138">Hantar e-mel kepada D365CI@microsoft.com untuk menentukan alamat e-mel pelanggan di dalam permintaan.</span><span class="sxs-lookup"><span data-stu-id="e2d43-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="e2d43-139">Pasukan Customer Insights akan menghantar e-mel kepada alamat e-mel pentadbir penyewa berdaftar, meminta pengesahan untuk mengeksport data.</span><span class="sxs-lookup"><span data-stu-id="e2d43-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="e2d43-140">Memberitahu pengesahan untuk mengeksport data untuk pelanggan yang diminta.</span><span class="sxs-lookup"><span data-stu-id="e2d43-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="e2d43-141">Menerima data yang dieksport melalui alamat e-mel pentadbir penyewa.</span><span class="sxs-lookup"><span data-stu-id="e2d43-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="e2d43-142">Eksport data pengguna (pentadbir penyewa)</span><span class="sxs-lookup"><span data-stu-id="e2d43-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="e2d43-143">Hantar e-mel kepada D365CI@microsoft.com untuk menentukan alamat e-mel pengguna di dalam permintaan.</span><span class="sxs-lookup"><span data-stu-id="e2d43-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="e2d43-144">Pasukan Customer Insights akan menghantar e-mel kepada alamat e-mel pentadbir penyewa berdaftar, meminta pengesahan untuk mengeksport data.</span><span class="sxs-lookup"><span data-stu-id="e2d43-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="e2d43-145">Memberitahu pengesahan untuk mengeksport data untuk pengguna yang diminta.</span><span class="sxs-lookup"><span data-stu-id="e2d43-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="e2d43-146">Menerima data yang dieksport melalui alamat e-mel pentadbir penyewa.</span><span class="sxs-lookup"><span data-stu-id="e2d43-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]