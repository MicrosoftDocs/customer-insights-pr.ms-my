---
title: Eksport data Customer Insights ke Adobe Campaign Standard
description: Ketahui cara menggunakan segmen wawasan khalayak dalam Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596326"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Gunakan segmen Customer Insights dalam Adobe Campaign Standard (pratonton)

Sebagai pengguna wawasan khalayak untuk Dynamics 365 Customer Insights, anda mungkin telah mencipta segmen untuk menjadikan kempen pemasaran anda lebih cekap dengan menyasarkan khalayak yang berkaitan. Untuk menggunakan segmen daripada wawasan khalayak dalam Platform Pengalaman Adobe dan aplikasi seperti Adobe Campaign Standard, anda perlu mengikuti beberapa langkah yang digariskan dalam artikel ini.

:::image type="content" source="media/ACS-flow.png" alt-text="Gambar rajah proses langkah digariskan dalam artikel ini.":::

## <a name="prerequisites"></a>Prasyarat

-   Lesen Dynamics 365 Customer Insights
-   Lesen Adobe Campaign Standard
-   Akaun Storan Blob Azure

## <a name="campaign-overview"></a>Gambaran Keseluruhan Kempen

Untuk lebih memahami cara anda boleh menggunakan segmen daripada wawasan khalayak dalam Platform Pengalaman Adobe, mari kita lihat kempen sampel rekaan.

Mari kita anggap bahawa syarikat anda menawarkan perkhidmatan berasaskan langganan bulanan kepada pelanggan anda di Amerika Syarikat. Anda ingin mengenal pasti pelanggan yang langganan perlu diperbaharui dalam tempoh lapan hari akan datang tetapi belum memperbaharui langganan mereka. Untuk mengekalkan pelanggan ini, anda ingin menghantar tawaran promosi kepada mereka melalui e-mel, menggunakan Adobe Campaign Standard.

Dalam contoh ini, kami ingin menjalankan kempen e-mel promosi sekali. Artikel ini tidak meliputi penggunaan kes menjalankan kempen lebih daripada sekali. Walau bagaimanapun, wawasan khalayak dan Adobe Campaign Standard juga boleh dikonfigurasikan untuk berfungsi bagi senario kempen berulang.

## <a name="identify-your-target-audience"></a>Kenal pasti khalayak sasaran anda

Dalam senario ini, kami menganggap bahawa alamat e-mel pelanggan tersedia dalam wawasan khalayak dan pilihan promosi mereka dianalisis untuk mengenal pasti ahli segmen.

[Segmen yang anda takrifkan dalam wawasan khalayak](segments.md) dipanggil **ChurnProneCustomers** dan anda merancang untuk menghantar promosi e-mel kepada pelanggan ini.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Petikan skrin halaman segmen dengan segmen ChurnProneCustomers dicipta.":::

E-mel tawaran yang ingin anda hantar akan mengandungi nama pertama, nama akhir dan tarikh tamat langganan pelanggan. Pelanggan dimaklumkan tentang diskaun yang akan mereka dapat jika mereka memperbaharui langganan mereka sebelum ia berakhir.

## <a name="export-your-target-audience"></a>Eksport khalayak sasaran anda

Dengan khalayak sasaran kami yang dikenal pasti, kami boleh mengkonfigurasikan eksport daripada wawasan khalayak ke akaun Storan Blob Azure.

1. Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.

1. Dalam jubin **Adobe Campaign**, pilih **Sediakan**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Jubin konfigurasi untuk Adobe Campaign Standard.":::

1. Berikan **Nama paparan** untuk destinasi eksport baharu ini dan kemudian masukkan **Nama akaun**, **Kunci akaun** dan **Bekas** akaun Storan Blob Azure tempat yang ingin anda eksport segmen itu.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Petikan skrin konfigurasi akaun storan. "::: 

   - Untuk mengetahui lanjut tentang cara mencari nama akaun dan kunci akaun storan Blob Azure, lihat [Urus tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).

   - Untuk mengetahui cara untuk mencipta bekas, lihat [Cipta bekas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pilih **Seterusnya**.

1. Pilih segmen yang ingin anda eksport. Dalam contoh ini, ia **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Petikan skrin antara muka pengguna pemilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. Pilih **Seterusnya**.

1. Sekarang kami memetakan medan **Sumber** daripada segmen wawasan khalayak kepada nama medan **Sasaran** dalam skema profil Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Pemetaan medan untuk penyambung Adobe Campaign Standard.":::

   Jika anda ingin menambah lebih banyak atribut, pilih **Tambah atribut**. Nama sasaran boleh berbeza daripada nama medan sumber supaya anda masih boleh memetakan output segmen daripada wawasan khalayak kepada Adobe Campaign Standard jika medan tidak mempunyai nama yang sama dalam dua sistem.

   > [!NOTE]
   > Alamat e-mel digunakan sebagai medan identiti, tetapi anda boleh menggunakan mana-mana pengecam lain daripada profil pelanggan wawasan khalayak anda untuk memetakan data ke Adobe Campaign Standard.

1. Pilih **Simpan**.

Selepas menyimpan destinasi eksport, anda dapati ia di **Pentadbir** > **Eksport** > **Destinasi eksport saya**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Petikan skrin dengan senarai eksport dan segmen sampel yang diserlahkan.":::

Anda kini boleh [mengeksport segmen atas permintaan](export-destinations.md#export-data-on-demand). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md).

> [!NOTE]
> Pastikan bilangan rekod dalam segmen yang dieksport berada dalam had lesen Adobe Campaign Standard anda yang dibenarkan.

Data yang dieksport disimpan dalam bekas storan Blob Azure yang anda konfigurasikan di atas. Laluan folder berikut dicipta secara automatik dalam bekas anda:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurasikan Adobe Campaign Standard

Apabila segmen daripada wawasan khalayak dieksport, ia mengandungi lajur yang anda pilih semasa mentakrifkan destinasi eksport dalam langkah sebelumnya. Data ini boleh digunakan untuk [mencipta profil dalam Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Untuk menggunakan segmen dalam Adobe Campaign Standard, kami perlu melanjutkan skema profil dalam Adobe Campaign Standard untuk menyertakan dua medan tambahan. Ketahui cara [melanjutkan sumber profil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) dengan medan baharu dalam Adobe Campaign Standard.

Dalam contoh kami, medan ini ialah *Nama Segmen dan Tarikh Segmen (pilihan).*

Kami akan menggunakan medan ini untuk mengenal pasti profil dalam Adobe Campaign Standard yang ingin kami sasarkan untuk kempen ini.

Jika tiada rekod lain dalam Adobe Campaign Standard, selain daripada rekod yang akan anda import, anda boleh melangkau langkah ini.

## <a name="import-data-into-adobe-campaign-standard"></a>Import data ke dalam Adobe Campaign Standard

Kini semua yang diperlukan telah tersedia, kami perlu mengimport data khalayak yang disediakan daripada wawasan khalayak ke dalam Adobe Campaign Standard untuk mencipta profil. Ketahui [cara mengimport profil dalam Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) menggunakan aliran kerja.

Aliran kerja import dalam imej di bawah telah dikonfigurasikan untuk berjalan setiap 8 jam dan mencari segmen wawasan khalayak yang dieksport (fail .csv dalam Storan Blob Azure). Aliran kerja mengekstrak kandungan fail .csv dalam susunan lajur yang ditentukan. Aliran kerja ini telah dibina untuk melakukan pengendalian ralat asas dan memastikan setiap rekod mempunyai alamat e-mel sebelum menghidratkan data dalam Adobe Campaign Standard. Aliran kerja juga mengekstrak nama segmen daripada nama fail sebelum upsert ke dalam data Profil ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Petikan skrin aliran kerja import dalam antara muka pengguna Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Dapatkan semula khalayak dalam Adobe Campaign Standard

Sebaik sahaja data diimport ke dalam Adobe Campaign Standard, anda [boleh mencipta aliran kerja](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) dan [bertanyakan](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) kepada pelanggan berdasarkan *Nama Segmen* dan *Tarikh Segmen* untuk memilih profil yang dikenal pasti untuk kempen sampel kami.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Cipta dan hantar e-mel menggunakan Adobe Campaign Standard

Cipta kandungan e-mel dan kemudian [uji dan hantar](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-mel anda.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mel sampel dengan tawaran pembaharuan daripada Adobe Campaign Standard.":::