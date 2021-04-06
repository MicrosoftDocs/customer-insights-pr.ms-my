---
title: Eksport data Customer Insights ke Platform Pengalaman Adobe
description: Ketahui cara menggunakan segmen wawasan khalayak dalam Platform Pengalaman Adobe.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596280"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="4deb6-103">Gunakan segmen Customer Insights dalam Platform Pengalaman Adobe (pratonton)</span><span class="sxs-lookup"><span data-stu-id="4deb6-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="4deb6-104">Sebagai pengguna wawasan khalayak untuk Dynamics 365 Customer Insights, anda mungkin telah mencipta segmen untuk menjadikan kempen pemasaran anda lebih cekap dengan menyasarkan khalayak yang berkaitan.</span><span class="sxs-lookup"><span data-stu-id="4deb6-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="4deb6-105">Untuk menggunakan segmen daripada wawasan khalayak dalam Platform Pengalaman Adobe dan aplikasi seperti Adobe Campaign Standard, anda perlu mengikuti beberapa langkah yang digariskan dalam artikel ini.</span><span class="sxs-lookup"><span data-stu-id="4deb6-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Gambar rajah proses langkah digariskan dalam artikel ini.":::

## <a name="prerequisites"></a><span data-ttu-id="4deb6-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="4deb6-107">Prerequisites</span></span>

-   <span data-ttu-id="4deb6-108">Lesen Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="4deb6-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="4deb6-109">Lesen Platform Pengalaman Adobe</span><span class="sxs-lookup"><span data-stu-id="4deb6-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="4deb6-110">Lesen Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="4deb6-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="4deb6-111">Akaun Storan Blob Azure</span><span class="sxs-lookup"><span data-stu-id="4deb6-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="4deb6-112">Gambaran Keseluruhan Kempen</span><span class="sxs-lookup"><span data-stu-id="4deb6-112">Campaign Overview</span></span>

<span data-ttu-id="4deb6-113">Untuk lebih memahami cara anda boleh menggunakan segmen daripada wawasan khalayak dalam Platform Pengalaman Adobe, mari kita lihat kempen sampel rekaan.</span><span class="sxs-lookup"><span data-stu-id="4deb6-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="4deb6-114">Mari kita anggap bahawa syarikat anda menawarkan perkhidmatan berasaskan langganan bulanan kepada pelanggan anda di Amerika Syarikat.</span><span class="sxs-lookup"><span data-stu-id="4deb6-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="4deb6-115">Anda ingin mengenal pasti pelanggan yang langganan perlu diperbaharui dalam tempoh lapan hari akan datang tetapi belum memperbaharui langganan mereka.</span><span class="sxs-lookup"><span data-stu-id="4deb6-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="4deb6-116">Untuk mengekalkan pelanggan ini, anda ingin menghantar tawaran promosi kepada mereka melalui e-mel, menggunakan Platform Pengalaman Adobe.</span><span class="sxs-lookup"><span data-stu-id="4deb6-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="4deb6-117">Dalam contoh ini, kami ingin menjalankan kempen e-mel promosi sekali.</span><span class="sxs-lookup"><span data-stu-id="4deb6-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="4deb6-118">Artikel ini tidak meliputi penggunaan kes menjalankan kempen lebih daripada sekali.</span><span class="sxs-lookup"><span data-stu-id="4deb6-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="4deb6-119">Kenal pasti khalayak sasaran anda</span><span class="sxs-lookup"><span data-stu-id="4deb6-119">Identify your target audience</span></span>

<span data-ttu-id="4deb6-120">Dalam senario ini, kami menganggap bahawa alamat e-mel pelanggan tersedia dalam wawasan khalayak dan pilihan promosi mereka dianalisis untuk mengenal pasti ahli segmen.</span><span class="sxs-lookup"><span data-stu-id="4deb6-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="4deb6-121">[Segmen yang anda takrifkan dalam wawasan khalayak](segments.md) dipanggil **ChurnProneCustomers** dan anda merancang untuk menghantar promosi e-mel kepada pelanggan ini.</span><span class="sxs-lookup"><span data-stu-id="4deb6-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Petikan skrin halaman segmen dengan segmen ChurnProneCustomers dicipta.":::

<span data-ttu-id="4deb6-123">E-mel tawaran yang ingin anda hantar akan mengandungi nama pertama, nama akhir dan tarikh tamat langganan pelanggan.</span><span class="sxs-lookup"><span data-stu-id="4deb6-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="4deb6-124">Pelanggan dimaklumkan tentang diskaun yang akan mereka dapat jika mereka memperbaharui langganan mereka sebelum ia berakhir.</span><span class="sxs-lookup"><span data-stu-id="4deb6-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="4deb6-125">Eksport khalayak sasaran anda</span><span class="sxs-lookup"><span data-stu-id="4deb6-125">Export your target audience</span></span>

<span data-ttu-id="4deb6-126">Dengan khalayak sasaran kami yang dikenal pasti, kami boleh mengkonfigurasikan eksport daripada wawasan khalayak ke akaun Storan Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="4deb6-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="4deb6-127">Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.</span><span class="sxs-lookup"><span data-stu-id="4deb6-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4deb6-128">Dalam jubin **Storan Blob Azure**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="4deb6-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Jubin konfigurasi untuk Storan Blob Azure.":::

1. <span data-ttu-id="4deb6-130">Berikan **Nama paparan** untuk destinasi eksport baharu ini dan kemudian masukkan **Nama akaun**, **Kunci akaun** dan **Bekas** akaun Storan Blob Azure tempat yang ingin anda eksport segmen itu.</span><span class="sxs-lookup"><span data-stu-id="4deb6-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Petikan skrin konfigurasi akaun storan. "::: 

   - <span data-ttu-id="4deb6-132">Untuk mengetahui lanjut tentang cara mencari nama akaun dan kunci akaun storan Blob Azure, lihat [Urus tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="4deb6-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="4deb6-133">Untuk mengetahui cara untuk mencipta bekas, lihat [Cipta bekas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="4deb6-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="4deb6-134">Pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="4deb6-134">Select **Next**.</span></span>

1. <span data-ttu-id="4deb6-135">Pilih segmen yang ingin anda eksport.</span><span class="sxs-lookup"><span data-stu-id="4deb6-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="4deb6-136">Dalam contoh ini, ia **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4deb6-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Petikan skrin antara muka pengguna pemilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. <span data-ttu-id="4deb6-138">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="4deb6-138">Select **Save**.</span></span>

<span data-ttu-id="4deb6-139">Selepas menyimpan destinasi eksport, anda dapati ia di **Pentadbir** > **Eksport** > **Destinasi eksport saya**.</span><span class="sxs-lookup"><span data-stu-id="4deb6-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Petikan skrin dengan senarai eksport dan segmen sampel yang diserlahkan.":::

<span data-ttu-id="4deb6-141">Anda kini boleh [mengeksport segmen atas permintaan](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4deb6-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="4deb6-142">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md).</span><span class="sxs-lookup"><span data-stu-id="4deb6-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4deb6-143">Pastikan bilangan rekod dalam segmen yang dieksport berada dalam had lesen Adobe Campaign Standard anda yang dibenarkan.</span><span class="sxs-lookup"><span data-stu-id="4deb6-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="4deb6-144">Data yang dieksport disimpan dalam bekas storan Blob Azure yang anda konfigurasikan di atas.</span><span class="sxs-lookup"><span data-stu-id="4deb6-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="4deb6-145">Laluan folder berikut dicipta secara automatik dalam bekas anda:</span><span class="sxs-lookup"><span data-stu-id="4deb6-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="4deb6-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="4deb6-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="4deb6-147">Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="4deb6-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="4deb6-148">*model.json* untuk entiti yang dieksport ditempatkan di peringkat *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="4deb6-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="4deb6-149">Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="4deb6-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="4deb6-150">Takrifkan Model Data Pengalaman (XDM) dalam Platform Pengalaman Adobe</span><span class="sxs-lookup"><span data-stu-id="4deb6-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="4deb6-151">Sebelum data yang dieksport daripada wawasan khalayak boleh digunakan dalam Platform Pengalaman Adobe, kami perlu mentakrifkan skema Model Data Pengalaman dan [mengkonfigurasikan data untuk Profil Pelanggan Masa Nyata](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="4deb6-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="4deb6-152">Ketahui [maksud XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) dan fahami [asas komposisi skema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="4deb6-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="4deb6-153">Import data ke dalam Platform Pengalaman Adobe</span><span class="sxs-lookup"><span data-stu-id="4deb6-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="4deb6-154">Kini semua yang diperlukan telah tersedia, kami perlu mengimport data khalayak yang disediakan daripada wawasan khalayak ke dalam Platform Pengalaman Adobe.</span><span class="sxs-lookup"><span data-stu-id="4deb6-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="4deb6-155">Pertama, [cipta sambungan sumber Storan Blob Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="4deb6-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="4deb6-156">Selepas mentakrifkan sambungan sumber, [konfigurasikan aliran data](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) untuk sambungan kelompok storan awan untuk mengimport output segmen daripada wawasan khalayak ke dalam Platform Pengalaman Adobe.</span><span class="sxs-lookup"><span data-stu-id="4deb6-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="4deb6-157">Cipta khalayak dalam Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="4deb6-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="4deb6-158">Untuk menghantar e-mel bagi kempen ini, kami akan menggunakan Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="4deb6-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="4deb6-159">Selepas mengimport data ke dalam Platform Pengalaman Adobe, kami perlu [mencipta khalayak](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) dalam Adobe Campaign Standard menggunakan data dalam Platform Pengalaman Adobe.</span><span class="sxs-lookup"><span data-stu-id="4deb6-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="4deb6-160">Ketahui cara [menggunakan pembina segmen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) dalam Adobe Campaign Standard untuk mentakrifkan khalayak berdasarkan data dalam Platform Pengalaman Adobe.</span><span class="sxs-lookup"><span data-stu-id="4deb6-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="4deb6-161">Cipta dan hantar e-mel menggunakan Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="4deb6-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="4deb6-162">Cipta kandungan e-mel dan kemudian [uji dan hantar](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-mel anda.</span><span class="sxs-lookup"><span data-stu-id="4deb6-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mel sampel dengan tawaran pembaharuan daripada Adobe Campaign Standard.":::