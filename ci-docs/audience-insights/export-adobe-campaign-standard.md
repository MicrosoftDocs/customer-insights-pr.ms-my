---
title: Eksport data Customer Insights ke Adobe Campaign Standard
description: Ketahui cara menggunakan segmen wawasan khalayak dalam Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760292"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="39b65-103">Gunakan segmen Customer Insights dalam Adobe Campaign Standard (pratonton)</span><span class="sxs-lookup"><span data-stu-id="39b65-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="39b65-104">Sebagai pengguna wawasan khalayak untuk Dynamics 365 Customer Insights, anda mungkin telah mencipta segmen untuk menjadikan kempen pemasaran anda lebih cekap dengan menyasarkan khalayak yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="39b65-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="39b65-105">Untuk menggunakan segmen daripada wawasan khalayak dalam Platform Pengalaman Adobe dan aplikasi seperti Adobe Campaign Standard, anda perlu mengikuti beberapa langkah yang digariskan dalam artikel ini.</span><span class="sxs-lookup"><span data-stu-id="39b65-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Gambar rajah proses langkah digariskan dalam artikel ini.":::

## <a name="prerequisites"></a><span data-ttu-id="39b65-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="39b65-107">Prerequisites</span></span>

-   <span data-ttu-id="39b65-108">Lesen Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="39b65-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="39b65-109">Lesen Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="39b65-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="39b65-110">Akaun Storan Blob Azure</span><span class="sxs-lookup"><span data-stu-id="39b65-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="39b65-111">Gambaran Keseluruhan Kempen</span><span class="sxs-lookup"><span data-stu-id="39b65-111">Campaign Overview</span></span>

<span data-ttu-id="39b65-112">Untuk lebih memahami cara anda boleh menggunakan segmen daripada wawasan khalayak dalam Platform Pengalaman Adobe, mari kita lihat kempen sampel rekaan.</span><span class="sxs-lookup"><span data-stu-id="39b65-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="39b65-113">Mari kita anggap bahawa syarikat anda menawarkan perkhidmatan berasaskan langganan bulanan kepada pelanggan anda di Amerika Syarikat.</span><span class="sxs-lookup"><span data-stu-id="39b65-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="39b65-114">Anda ingin mengenal pasti pelanggan yang langganan perlu diperbaharui dalam tempoh lapan hari akan datang tetapi belum memperbaharui langganan mereka.</span><span class="sxs-lookup"><span data-stu-id="39b65-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="39b65-115">Untuk mengekalkan pelanggan ini, anda ingin menghantar tawaran promosi kepada mereka melalui e-mel, menggunakan Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="39b65-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="39b65-116">Dalam contoh ini, kami ingin menjalankan kempen e-mel promosi sekali.</span><span class="sxs-lookup"><span data-stu-id="39b65-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="39b65-117">Artikel ini tidak meliputi penggunaan kes menjalankan kempen lebih daripada sekali.</span><span class="sxs-lookup"><span data-stu-id="39b65-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="39b65-118">Walau bagaimanapun, wawasan khalayak dan Adobe Campaign Standard juga boleh dikonfigurasikan untuk berfungsi bagi senario kempen berulang.</span><span class="sxs-lookup"><span data-stu-id="39b65-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="39b65-119">Kenal pasti khalayak sasaran anda</span><span class="sxs-lookup"><span data-stu-id="39b65-119">Identify your target audience</span></span>

<span data-ttu-id="39b65-120">Dalam senario ini, kami menganggap bahawa alamat e-mel pelanggan tersedia dalam wawasan khalayak dan pilihan promosi mereka dianalisis untuk mengenal pasti ahli segmen.</span><span class="sxs-lookup"><span data-stu-id="39b65-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="39b65-121">[Segmen yang anda takrifkan dalam wawasan khalayak](segments.md) dipanggil **ChurnProneCustomers** dan anda merancang untuk menghantar promosi e-mel kepada pelanggan ini.</span><span class="sxs-lookup"><span data-stu-id="39b65-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Petikan skrin halaman segmen dengan segmen ChurnProneCustomers dicipta.":::

<span data-ttu-id="39b65-123">E-mel tawaran yang ingin anda hantar akan mengandungi nama pertama, nama akhir dan tarikh tamat langganan pelanggan.</span><span class="sxs-lookup"><span data-stu-id="39b65-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="39b65-124">Pelanggan dimaklumkan tentang diskaun yang akan mereka dapat jika mereka memperbaharui langganan mereka sebelum ia berakhir.</span><span class="sxs-lookup"><span data-stu-id="39b65-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="39b65-125">Eksport khalayak sasaran anda</span><span class="sxs-lookup"><span data-stu-id="39b65-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="39b65-126">Konfigurasikan sambungan</span><span class="sxs-lookup"><span data-stu-id="39b65-126">Configure a connection</span></span>

<span data-ttu-id="39b65-127">Dengan khalayak sasaran kami yang dikenal pasti, kami boleh mengkonfigurasikan eksport daripada wawasan khalayak ke akaun Storan Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="39b65-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="39b65-128">Dalam wawasan khalayak, pergi ke **Pergi ke** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="39b65-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="39b65-129">Pilih **Tambah sambungan** dan pilih **Adobe Campaign** untuk mengkonfigurasikan sambungan atau pilih **Sediakan** dalam jubin **Adobe Campaign**</span><span class="sxs-lookup"><span data-stu-id="39b65-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Jubin konfigurasi untuk Adobe Campaign Standard.":::

1. <span data-ttu-id="39b65-131">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="39b65-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="39b65-132">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="39b65-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="39b65-133">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="39b65-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="39b65-134">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="39b65-134">Choose who can use this connection.</span></span> <span data-ttu-id="39b65-135">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="39b65-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="39b65-136">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="39b65-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="39b65-137">Masukkan **Nama akaun**, **Kekunci akaun**, dan **Bekas** untuk akaun Storan Blob Azure anda di tempat anda mahu mengeksport segmen.</span><span class="sxs-lookup"><span data-stu-id="39b65-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Petikan skrin konfigurasi akaun storan. "::: 

   - <span data-ttu-id="39b65-139">Untuk mengetahui lanjut tentang cara mencari nama akaun dan kunci akaun storan Blob Azure, lihat [Urus tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="39b65-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="39b65-140">Untuk mengetahui cara untuk mencipta bekas, lihat [Cipta bekas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="39b65-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="39b65-141">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="39b65-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="39b65-142">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="39b65-142">Configure an export</span></span>

<span data-ttu-id="39b65-143">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="39b65-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="39b65-144">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="39b65-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="39b65-145">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="39b65-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="39b65-146">Untuk mencipta eksport baharu, pilih **Tambah eksport**.</span><span class="sxs-lookup"><span data-stu-id="39b65-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="39b65-147">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="39b65-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="39b65-148">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="39b65-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="39b65-149">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="39b65-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="39b65-150">Dalam contoh ini, ia **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="39b65-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Petikan skrin antara muka pengguna pemilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. <span data-ttu-id="39b65-152">Pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="39b65-152">Select **Next**.</span></span>

1. <span data-ttu-id="39b65-153">Sekarang kami memetakan medan **Sumber** daripada segmen wawasan khalayak kepada nama medan **Sasaran** dalam skema profil Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="39b65-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Pemetaan medan untuk penyambung Adobe Campaign Standard.":::

   <span data-ttu-id="39b65-155">Jika anda ingin menambah lebih banyak atribut, pilih **Tambah atribut**.</span><span class="sxs-lookup"><span data-stu-id="39b65-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="39b65-156">Nama sasaran boleh berbeza daripada nama medan sumber supaya anda masih boleh memetakan output segmen daripada wawasan khalayak kepada Adobe Campaign Standard jika medan tidak mempunyai nama yang sama dalam dua sistem.</span><span class="sxs-lookup"><span data-stu-id="39b65-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="39b65-157">Alamat e-mel digunakan sebagai medan identiti, tetapi anda boleh menggunakan mana-mana pengecam lain daripada profil pelanggan wawasan khalayak anda untuk memetakan data ke Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="39b65-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="39b65-158">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="39b65-158">Select **Save**.</span></span>

<span data-ttu-id="39b65-159">Selepas menyimpan destinasi eksport, anda akan menemuinya dalam **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="39b65-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="39b65-160">Anda kini boleh [mengeksport segmen atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="39b65-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="39b65-161">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md).</span><span class="sxs-lookup"><span data-stu-id="39b65-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="39b65-162">Pastikan bilangan rekod dalam segmen yang dieksport berada dalam had lesen Adobe Campaign Standard anda yang dibenarkan.</span><span class="sxs-lookup"><span data-stu-id="39b65-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="39b65-163">Data yang dieksport disimpan dalam bekas storan Blob Azure yang anda konfigurasikan di atas.</span><span class="sxs-lookup"><span data-stu-id="39b65-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="39b65-164">Laluan folder berikut dicipta secara automatik dalam bekas anda:</span><span class="sxs-lookup"><span data-stu-id="39b65-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="39b65-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="39b65-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="39b65-166">Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="39b65-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="39b65-167">Konfigurasikan Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="39b65-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="39b65-168">Apabila segmen daripada wawasan khalayak dieksport, ia mengandungi lajur yang anda pilih semasa mentakrifkan destinasi eksport dalam langkah sebelumnya.</span><span class="sxs-lookup"><span data-stu-id="39b65-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="39b65-169">Data ini boleh digunakan untuk [mencipta profil dalam Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="39b65-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="39b65-170">Untuk menggunakan segmen dalam Adobe Campaign Standard, kami perlu melanjutkan skema profil dalam Adobe Campaign Standard untuk menyertakan dua medan tambahan.</span><span class="sxs-lookup"><span data-stu-id="39b65-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="39b65-171">Ketahui cara [melanjutkan sumber profil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) dengan medan baharu dalam Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="39b65-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="39b65-172">Dalam contoh kami, medan ini ialah *Nama Segmen dan Tarikh Segmen (pilihan).*</span><span class="sxs-lookup"><span data-stu-id="39b65-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="39b65-173">Kami akan menggunakan medan ini untuk mengenal pasti profil dalam Adobe Campaign Standard yang ingin kami sasarkan untuk kempen ini.</span><span class="sxs-lookup"><span data-stu-id="39b65-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="39b65-174">Jika tiada rekod lain dalam Adobe Campaign Standard, selain daripada rekod yang akan anda import, anda boleh melangkau langkah ini.</span><span class="sxs-lookup"><span data-stu-id="39b65-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="39b65-175">Import data ke dalam Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="39b65-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="39b65-176">Kini semua yang diperlukan telah tersedia, kami perlu mengimport data khalayak yang disediakan daripada wawasan khalayak ke dalam Adobe Campaign Standard untuk mencipta profil.</span><span class="sxs-lookup"><span data-stu-id="39b65-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="39b65-177">Ketahui [cara mengimport profil dalam Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) menggunakan aliran kerja.</span><span class="sxs-lookup"><span data-stu-id="39b65-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="39b65-178">Aliran kerja import dalam imej di bawah telah dikonfigurasikan untuk berjalan setiap 8 jam dan mencari segmen wawasan khalayak yang dieksport (fail .csv dalam Storan Blob Azure).</span><span class="sxs-lookup"><span data-stu-id="39b65-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="39b65-179">Aliran kerja mengekstrak kandungan fail .csv dalam susunan lajur yang ditentukan.</span><span class="sxs-lookup"><span data-stu-id="39b65-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="39b65-180">Aliran kerja ini telah dibina untuk melakukan pengendalian ralat asas dan memastikan setiap rekod mempunyai alamat e-mel sebelum menghidratkan data dalam Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="39b65-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="39b65-181">Aliran kerja juga mengekstrak nama segmen daripada nama fail sebelum upsert ke dalam data Profil ACS.</span><span class="sxs-lookup"><span data-stu-id="39b65-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Petikan skrin aliran kerja import dalam antara muka pengguna Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="39b65-183">Dapatkan semula khalayak dalam Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="39b65-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="39b65-184">Sebaik sahaja data diimport ke dalam Adobe Campaign Standard, anda [boleh mencipta aliran kerja](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) dan [bertanyakan](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) kepada pelanggan berdasarkan *Nama Segmen* dan *Tarikh Segmen* untuk memilih profil yang dikenal pasti untuk kempen sampel kami.</span><span class="sxs-lookup"><span data-stu-id="39b65-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="39b65-185">Cipta dan hantar e-mel menggunakan Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="39b65-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="39b65-186">Cipta kandungan e-mel dan kemudian [uji dan hantar](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-mel anda.</span><span class="sxs-lookup"><span data-stu-id="39b65-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mel sampel dengan tawaran pembaharuan daripada Adobe Campaign Standard.":::
