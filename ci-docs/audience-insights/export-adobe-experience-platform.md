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
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Gunakan segmen Customer Insights dalam Platform Pengalaman Adobe (pratonton)

Sebagai pengguna wawasan khalayak untuk Dynamics 365 Customer Insights, anda mungkin telah mencipta segmen untuk menjadikan kempen pemasaran anda lebih cekap dengan menyasarkan khalayak yang berkaitan. Untuk menggunakan segmen daripada wawasan khalayak dalam Platform Pengalaman Adobe dan aplikasi seperti Adobe Campaign Standard, anda perlu mengikuti beberapa langkah yang digariskan dalam artikel ini.

:::image type="content" source="media/AEP-flow.png" alt-text="Gambar rajah proses langkah digariskan dalam artikel ini.":::

## <a name="prerequisites"></a>Prasyarat

-   Lesen Dynamics 365 Customer Insights
-   Lesen Platform Pengalaman Adobe
-   Lesen Adobe Campaign Standard
-   Akaun Storan Blob Azure

## <a name="campaign-overview"></a>Gambaran Keseluruhan Kempen

Untuk lebih memahami cara anda boleh menggunakan segmen daripada wawasan khalayak dalam Platform Pengalaman Adobe, mari kita lihat kempen sampel rekaan.

Mari kita anggap bahawa syarikat anda menawarkan perkhidmatan berasaskan langganan bulanan kepada pelanggan anda di Amerika Syarikat. Anda ingin mengenal pasti pelanggan yang langganan perlu diperbaharui dalam tempoh lapan hari akan datang tetapi belum memperbaharui langganan mereka. Untuk mengekalkan pelanggan ini, anda ingin menghantar tawaran promosi kepada mereka melalui e-mel, menggunakan Platform Pengalaman Adobe.

Dalam contoh ini, kami ingin menjalankan kempen e-mel promosi sekali. Artikel ini tidak meliputi penggunaan kes menjalankan kempen lebih daripada sekali.

## <a name="identify-your-target-audience"></a>Kenal pasti khalayak sasaran anda

Dalam senario ini, kami menganggap bahawa alamat e-mel pelanggan tersedia dalam wawasan khalayak dan pilihan promosi mereka dianalisis untuk mengenal pasti ahli segmen.

[Segmen yang anda takrifkan dalam wawasan khalayak](segments.md) dipanggil **ChurnProneCustomers** dan anda merancang untuk menghantar promosi e-mel kepada pelanggan ini.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Petikan skrin halaman segmen dengan segmen ChurnProneCustomers dicipta.":::

E-mel tawaran yang ingin anda hantar akan mengandungi nama pertama, nama akhir dan tarikh tamat langganan pelanggan. Pelanggan dimaklumkan tentang diskaun yang akan mereka dapat jika mereka memperbaharui langganan mereka sebelum ia berakhir.

## <a name="export-your-target-audience"></a>Eksport khalayak sasaran anda

Dengan khalayak sasaran kami yang dikenal pasti, kami boleh mengkonfigurasikan eksport daripada wawasan khalayak ke akaun Storan Blob Azure.

1. Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.

1. Dalam jubin **Storan Blob Azure**, pilih **Sediakan**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Jubin konfigurasi untuk Storan Blob Azure.":::

1. Berikan **Nama paparan** untuk destinasi eksport baharu ini dan kemudian masukkan **Nama akaun**, **Kunci akaun** dan **Bekas** akaun Storan Blob Azure tempat yang ingin anda eksport segmen itu.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Petikan skrin konfigurasi akaun storan. "::: 

   - Untuk mengetahui lanjut tentang cara mencari nama akaun dan kunci akaun storan Blob Azure, lihat [Urus tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).

   - Untuk mengetahui cara untuk mencipta bekas, lihat [Cipta bekas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pilih **Seterusnya**.

1. Pilih segmen yang ingin anda eksport. Dalam contoh ini, ia **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Petikan skrin antara muka pengguna pemilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. Pilih **Simpan**.

Selepas menyimpan destinasi eksport, anda dapati ia di **Pentadbir** > **Eksport** > **Destinasi eksport saya**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Petikan skrin dengan senarai eksport dan segmen sampel yang diserlahkan.":::

Anda kini boleh [mengeksport segmen atas permintaan](export-destinations.md#export-data-on-demand). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md).

> [!NOTE]
> Pastikan bilangan rekod dalam segmen yang dieksport berada dalam had lesen Adobe Campaign Standard anda yang dibenarkan.

Data yang dieksport disimpan dalam bekas storan Blob Azure yang anda konfigurasikan di atas. Laluan folder berikut dicipta secara automatik dalam bekas anda:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* untuk entiti yang dieksport ditempatkan di peringkat *%ExportDestinationName%*.

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Takrifkan Model Data Pengalaman (XDM) dalam Platform Pengalaman Adobe

Sebelum data yang dieksport daripada wawasan khalayak boleh digunakan dalam Platform Pengalaman Adobe, kami perlu mentakrifkan skema Model Data Pengalaman dan [mengkonfigurasikan data untuk Profil Pelanggan Masa Nyata](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Ketahui [maksud XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) dan fahami [asas komposisi skema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Import data ke dalam Platform Pengalaman Adobe

Kini semua yang diperlukan telah tersedia, kami perlu mengimport data khalayak yang disediakan daripada wawasan khalayak ke dalam Platform Pengalaman Adobe.

Pertama, [cipta sambungan sumber Storan Blob Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Selepas mentakrifkan sambungan sumber, [konfigurasikan aliran data](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) untuk sambungan kelompok storan awan untuk mengimport output segmen daripada wawasan khalayak ke dalam Platform Pengalaman Adobe.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Cipta khalayak dalam Adobe Campaign Standard

Untuk menghantar e-mel bagi kempen ini, kami akan menggunakan Adobe Campaign Standard. Selepas mengimport data ke dalam Platform Pengalaman Adobe, kami perlu [mencipta khalayak](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) dalam Adobe Campaign Standard menggunakan data dalam Platform Pengalaman Adobe.

Ketahui cara [menggunakan pembina segmen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) dalam Adobe Campaign Standard untuk mentakrifkan khalayak berdasarkan data dalam Platform Pengalaman Adobe.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Cipta dan hantar e-mel menggunakan Adobe Campaign Standard

Cipta kandungan e-mel dan kemudian [uji dan hantar](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-mel anda.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mel sampel dengan tawaran pembaharuan daripada Adobe Campaign Standard.":::