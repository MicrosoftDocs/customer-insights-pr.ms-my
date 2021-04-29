---
title: Eksport data Customer Insights ke Platform Pengalaman Adobe
description: Ketahui cara menggunakan segmen wawasan khalayak dalam Platform Pengalaman Adobe.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760112"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="73e13-103">Gunakan segmen Customer Insights dalam Platform Pengalaman Adobe (pratonton)</span><span class="sxs-lookup"><span data-stu-id="73e13-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="73e13-104">Sebagai pengguna wawasan khalayak untuk Dynamics 365 Customer Insights, anda mungkin telah mencipta segmen untuk menjadikan kempen pemasaran anda lebih cekap dengan menyasarkan khalayak yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="73e13-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="73e13-105">Untuk menggunakan segmen daripada wawasan khalayak dalam Platform Pengalaman Adobe dan aplikasi seperti Adobe Campaign Standard, anda perlu mengikuti beberapa langkah yang digariskan dalam artikel ini.</span><span class="sxs-lookup"><span data-stu-id="73e13-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Gambar rajah proses langkah digariskan dalam artikel ini.":::

## <a name="prerequisites"></a><span data-ttu-id="73e13-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="73e13-107">Prerequisites</span></span>

-   <span data-ttu-id="73e13-108">Lesen Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="73e13-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="73e13-109">Lesen Platform Pengalaman Adobe</span><span class="sxs-lookup"><span data-stu-id="73e13-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="73e13-110">Lesen Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="73e13-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="73e13-111">Akaun Storan Blob Azure</span><span class="sxs-lookup"><span data-stu-id="73e13-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="73e13-112">Gambaran Keseluruhan Kempen</span><span class="sxs-lookup"><span data-stu-id="73e13-112">Campaign Overview</span></span>

<span data-ttu-id="73e13-113">Untuk lebih memahami cara anda boleh menggunakan segmen daripada wawasan khalayak dalam Platform Pengalaman Adobe, mari kita lihat kempen sampel rekaan.</span><span class="sxs-lookup"><span data-stu-id="73e13-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="73e13-114">Mari kita anggap bahawa syarikat anda menawarkan perkhidmatan berasaskan langganan bulanan kepada pelanggan anda di Amerika Syarikat.</span><span class="sxs-lookup"><span data-stu-id="73e13-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="73e13-115">Anda ingin mengenal pasti pelanggan yang langganan perlu diperbaharui dalam tempoh lapan hari akan datang tetapi belum memperbaharui langganan mereka.</span><span class="sxs-lookup"><span data-stu-id="73e13-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="73e13-116">Untuk mengekalkan pelanggan ini, anda ingin menghantar tawaran promosi kepada mereka melalui e-mel, menggunakan Platform Pengalaman Adobe.</span><span class="sxs-lookup"><span data-stu-id="73e13-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="73e13-117">Dalam contoh ini, kami ingin menjalankan kempen e-mel promosi sekali.</span><span class="sxs-lookup"><span data-stu-id="73e13-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="73e13-118">Artikel ini tidak meliputi penggunaan kes menjalankan kempen lebih daripada sekali.</span><span class="sxs-lookup"><span data-stu-id="73e13-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="73e13-119">Kenal pasti khalayak sasaran anda</span><span class="sxs-lookup"><span data-stu-id="73e13-119">Identify your target audience</span></span>

<span data-ttu-id="73e13-120">Dalam senario ini, kami menganggap bahawa alamat e-mel pelanggan tersedia dalam wawasan khalayak dan pilihan promosi mereka dianalisis untuk mengenal pasti ahli segmen.</span><span class="sxs-lookup"><span data-stu-id="73e13-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="73e13-121">[Segmen yang anda takrifkan dalam wawasan khalayak](segments.md) dipanggil **ChurnProneCustomers** dan anda merancang untuk menghantar promosi e-mel kepada pelanggan ini.</span><span class="sxs-lookup"><span data-stu-id="73e13-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Petikan skrin halaman segmen dengan segmen ChurnProneCustomers dicipta.":::

<span data-ttu-id="73e13-123">E-mel tawaran yang ingin anda hantar akan mengandungi nama pertama, nama akhir dan tarikh tamat langganan pelanggan.</span><span class="sxs-lookup"><span data-stu-id="73e13-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="73e13-124">Pelanggan dimaklumkan tentang diskaun yang akan mereka dapat jika mereka memperbaharui langganan mereka sebelum ia berakhir.</span><span class="sxs-lookup"><span data-stu-id="73e13-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="73e13-125">Eksport khalayak sasaran anda</span><span class="sxs-lookup"><span data-stu-id="73e13-125">Export your target audience</span></span>

<span data-ttu-id="73e13-126">Dengan khalayak sasaran kami yang dikenal pasti, kami boleh mengkonfigurasikan eksport daripada wawasan khalayak ke akaun Storan Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="73e13-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="73e13-127">Konfigurasikan sambungan</span><span class="sxs-lookup"><span data-stu-id="73e13-127">Configure a connection</span></span>

1. <span data-ttu-id="73e13-128">Pergi ke **Pentadbir** > **Sambungan**.</span><span class="sxs-lookup"><span data-stu-id="73e13-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="73e13-129">Pilih **Tambah sambungan** dan pilih **Storan Blob Azure** atau pilih **Sediakan** dalam jubin **Storan Blob Azure**:</span><span class="sxs-lookup"><span data-stu-id="73e13-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Jubin konfigurasi untuk Storan Blob Azure."::: <span data-ttu-id="73e13-131">Untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="73e13-131">to configure the connection.</span></span>

1. <span data-ttu-id="73e13-132">Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="73e13-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="73e13-133">Nama dan jenis sambungan menerangkan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="73e13-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="73e13-134">Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.</span><span class="sxs-lookup"><span data-stu-id="73e13-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="73e13-135">Pilih individu yang boleh menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="73e13-135">Choose who can use this connection.</span></span> <span data-ttu-id="73e13-136">Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir.</span><span class="sxs-lookup"><span data-stu-id="73e13-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="73e13-137">Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="73e13-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="73e13-138">Masukkan **Nama akaun**, **Kekunci akaun**, dan **Bekas** untuk akaun storan Blob anda di tempat anda mahu mengeksport segmen.</span><span class="sxs-lookup"><span data-stu-id="73e13-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Petikan skrin konfigurasi akaun storan. "::: 
   
    - <span data-ttu-id="73e13-140">Untuk mengetahui lebih lanjut tentang cara untuk mencari nama akaun dan kekunci akaun storan Blob, lihat [Urus tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="73e13-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="73e13-141">Untuk mengetahui cara untuk mencipta bekas, lihat [Cipta bekas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="73e13-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="73e13-142">Pilih **Simpan** untuk melengkapkan sambungan.</span><span class="sxs-lookup"><span data-stu-id="73e13-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="73e13-143">Konfigurasikan eksport</span><span class="sxs-lookup"><span data-stu-id="73e13-143">Configure an export</span></span>

<span data-ttu-id="73e13-144">Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini.</span><span class="sxs-lookup"><span data-stu-id="73e13-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="73e13-145">Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="73e13-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="73e13-146">Pergi ke **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="73e13-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="73e13-147">Untuk mencipta eksport baharu, pilih **Tambah eksport**.</span><span class="sxs-lookup"><span data-stu-id="73e13-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="73e13-148">Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Storan Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="73e13-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="73e13-149">Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.</span><span class="sxs-lookup"><span data-stu-id="73e13-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="73e13-150">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="73e13-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="73e13-151">Dalam contoh ini, ia **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="73e13-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Petikan skrin antara muka pengguna pemilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. <span data-ttu-id="73e13-153">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="73e13-153">Select **Save**.</span></span>

<span data-ttu-id="73e13-154">Selepas menyimpan destinasi eksport, anda akan menemuinya dalam **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="73e13-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="73e13-155">Anda kini boleh [mengeksport segmen atas permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="73e13-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="73e13-156">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md).</span><span class="sxs-lookup"><span data-stu-id="73e13-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="73e13-157">Pastikan bilangan rekod dalam segmen yang dieksport berada dalam had lesen Adobe Campaign Standard anda yang dibenarkan.</span><span class="sxs-lookup"><span data-stu-id="73e13-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="73e13-158">Data yang dieksport disimpan dalam bekas storan Blob Azure yang anda konfigurasikan di atas.</span><span class="sxs-lookup"><span data-stu-id="73e13-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="73e13-159">Laluan folder berikut dicipta secara automatik dalam bekas anda:</span><span class="sxs-lookup"><span data-stu-id="73e13-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="73e13-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="73e13-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="73e13-161">Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="73e13-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="73e13-162">*model.json* untuk entiti yang dieksport ditempatkan di peringkat *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="73e13-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="73e13-163">Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="73e13-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="73e13-164">Takrifkan Model Data Pengalaman (XDM) dalam Platform Pengalaman Adobe</span><span class="sxs-lookup"><span data-stu-id="73e13-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="73e13-165">Sebelum data yang dieksport daripada wawasan khalayak boleh digunakan dalam Platform Pengalaman Adobe, kami perlu mentakrifkan skema Model Data Pengalaman dan [mengkonfigurasikan data untuk Profil Pelanggan Masa Nyata](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="73e13-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="73e13-166">Ketahui [maksud XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) dan fahami [asas komposisi skema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="73e13-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="73e13-167">Import data ke dalam Platform Pengalaman Adobe</span><span class="sxs-lookup"><span data-stu-id="73e13-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="73e13-168">Kini semua yang diperlukan telah tersedia, kami perlu mengimport data khalayak yang disediakan daripada wawasan khalayak ke dalam Platform Pengalaman Adobe.</span><span class="sxs-lookup"><span data-stu-id="73e13-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="73e13-169">Pertama, [cipta sambungan sumber Storan Blob Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="73e13-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="73e13-170">Selepas mentakrifkan sambungan sumber, [konfigurasikan aliran data](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) untuk sambungan kelompok storan awan untuk mengimport output segmen daripada wawasan khalayak ke dalam Platform Pengalaman Adobe.</span><span class="sxs-lookup"><span data-stu-id="73e13-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="73e13-171">Cipta khalayak dalam Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="73e13-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="73e13-172">Untuk menghantar e-mel bagi kempen ini, kami akan menggunakan Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="73e13-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="73e13-173">Selepas mengimport data ke dalam Platform Pengalaman Adobe, kami perlu [mencipta khalayak](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) dalam Adobe Campaign Standard menggunakan data dalam Platform Pengalaman Adobe.</span><span class="sxs-lookup"><span data-stu-id="73e13-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="73e13-174">Ketahui cara [menggunakan pembina segmen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) dalam Adobe Campaign Standard untuk mentakrifkan khalayak berdasarkan data dalam Platform Pengalaman Adobe.</span><span class="sxs-lookup"><span data-stu-id="73e13-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="73e13-175">Cipta dan hantar e-mel menggunakan Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="73e13-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="73e13-176">Cipta kandungan e-mel dan kemudian [uji dan hantar](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-mel anda.</span><span class="sxs-lookup"><span data-stu-id="73e13-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mel sampel dengan tawaran pembaharuan daripada Adobe Campaign Standard.":::
