---
title: Export data Customer Insights ke Adobe Campaign Standard
description: Ketahui cara menggunakan segmen Wawasan Pelanggan dalam Adobe Standard Kempen.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643452"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Gunakan segmen Customer Insights dalam Adobe Campaign Standard (pratonton)

Sebagai pengguna Dynamics 365 Customer Insights, anda mungkin telah membuat segmen untuk menjadikan kempen pemasaran anda lebih cekap dengan menyasarkan khalayak yang berkaitan. Untuk menggunakan segmen daripada Wawasan Adobe Experience Platform Pelanggan dan aplikasi seperti Adobe Standard Kempen, anda perlu mengikuti beberapa langkah yang digariskan dalam artikel ini.

:::image type="content" source="media/ACS-flow.png" alt-text="Gambar rajah proses langkah digariskan dalam artikel ini.":::

## <a name="prerequisites"></a>Prasyarat

-   Lesen Dynamics 365 Customer Insights
-   Lesen Adobe Campaign Standard
-   Akaun Storan Blob Azure

## <a name="campaign-overview"></a>Gambaran keseluruhan kempen

Untuk lebih memahami cara anda boleh menggunakan segmen daripada Wawasan Pelanggan dalam Adobe Experience Platform, mari lihat kempen sampel rekaan.

Mari kita anggap bahawa syarikat anda menawarkan perkhidmatan berasaskan langganan bulanan kepada pelanggan anda di Amerika Syarikat. Anda ingin mengenal pasti pelanggan yang langganan perlu diperbaharui dalam tempoh lapan hari akan datang tetapi belum memperbaharui langganan mereka. Untuk menyimpan pelanggan ini, anda mahu menghantar mereka tawaran promosi melalui e-mel, menggunakan Adobe Campaign Standard.

Dalam contoh ini, kami ingin menjalankan kempen e-mel promosi sekali. Artikel ini tidak meliputi penggunaan kes menjalankan kempen lebih daripada sekali. Walau bagaimanapun, Wawasan Pelanggan dan Adobe Standard Kempen boleh dikonfigurasikan untuk berfungsi untuk senario kempen berulang juga.

## <a name="identify-your-target-audience"></a>Kenal pasti khalayak sasaran anda

Dalam senario kami, kami menganggap bahawa alamat e-mel pelanggan tersedia dan pilihan promosi mereka dianalisis untuk mengenal pasti ahli segmen.

Segmen [yang anda tentukan dalam Wawasan](segments.md) Pelanggan dipanggil **ChurnProneCustomers** dan anda merancang untuk menghantar promosi e-mel kepada pelanggan ini.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Petikan skrin halaman segmen dengan segmen ChurnProneCustomers dicipta.":::

E-mel tawaran yang ingin anda hantar akan mengandungi nama pertama, nama akhir dan tarikh tamat langganan pelanggan. Pelanggan dimaklumkan tentang diskaun yang akan mereka dapat jika mereka memperbaharui langganan mereka sebelum ia berakhir.

## <a name="export-your-target-audience"></a>Eksport khalayak sasaran anda

### <a name="configure-a-connection"></a>Konfigurasikan sambungan

Dengan khalayak sasaran kami dikenal pasti, kami boleh mengkonfigurasi eksport ke akaun Storan Azure Blob.

1. Dalam Wawasan Pelanggan, pergi ke **Sambungan Pentadbir** > **·**.

1. Pilih **Tambah sambungan** dan pilih **Adobe Campaign** untuk mengkonfigurasi sambungan atau pilih **Sediakan** dalam jubin **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Jubin konfigurasi untuk Adobe Campaign Standard.":::

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Masukkan **Nama akaun**, **Kekunci akaun**, dan **Bekas** untuk akaun Storan Blob Azure anda di tempat anda mahu mengeksport segmen.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Petikan skrin konfigurasi akaun storan. "::: 

   - Untuk mengetahui lebih lanjut tentang cara mencari nama akaun dan kunci akaun Azure Blob Storage, lihat [Urus tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).

   - Untuk mengetahui cara untuk mencipta bekas, lihat [Cipta bekas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pilih **Simpan** untuk melengkapkan sambungan.

### <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport** pilih sambungan daripada bahagian Adobe Campaign. Jika anda tidak melihat nama bahagian ini, maka tiada sambungan jenis ini tersedia untuk anda.

1. Pilih segmen yang ingin anda eksport. Dalam contoh ini, ia **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Petikan skrin antara muka pengguna pemilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. Pilih **Seterusnya**.

1. Kini kami memetakan **medan Sumber** daripada segmen Wawasan Pelanggan kepada **nama medan Sasaran** dalam Adobe skema profil Standard Kempen.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Pemetaan medan untuk penyambung Adobe Campaign Standard.":::

   Jika anda ingin menambah lebih banyak atribut, pilih **Tambah atribut**. Nama sasaran boleh berbeza daripada nama medan sumber supaya anda masih boleh memetakan output segmen daripada Wawasan Pelanggan kepada Adobe Standard Kempen jika medan tidak mempunyai nama yang sama dalam kedua-dua sistem.

   > [!NOTE]
   > Alamat e-mel digunakan sebagai medan identiti, tetapi anda boleh menggunakan sebarang pengecam lain daripada profil pelanggan untuk memetakan data kepada Adobe Standard Kempen.

1. Pilih **Simpan**.

Selepas menyimpan destinasi eksport, anda akan menemuinya dalam **Data** > **Eksport**.

Anda kini boleh [mengeksport segmen atas permintaan](export-destinations.md#run-exports-on-demand). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md).

> [!NOTE]
> Pastikan bilangan rekod dalam segmen yang dieksport adalah dalam had yang dibenarkan bagi lesen Adobe Campaign Standard.

Data yang dieksport disimpan dalam bekas Storan Blob Azure yang anda konfigurasikan di atas. Laluan folder berikut dicipta secara automatik dalam bekas anda:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurasikan Adobe Campaign Standard

Segmen yang dieksport mengandungi lajur yang anda pilih semasa menentukan destinasi eksport dalam langkah sebelumnya. Data ini boleh digunakan untuk [mencipta profil dalam Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Untuk menggunakan segmen dalam Adobe Campaign Standard, kami perlu melanjutkan skema profil dalam Adobe Campaign Standard termasuk dua medan tambahan. Ketahui cara untuk [melanjutkan sumber profil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) dengan medan baharu dalam Adobe Campaign Standard.

Dalam contoh kami, medan ini ialah *Nama Segmen dan Tarikh Segmen (pilihan)*.

Kami akan menggunakan medan ini untuk mengenal pasti profil dalam Adobe Campaign Standard yang kami mahu sasarkan untuk kempen ini.

Jika tiada rekod lain dalam Adobe Campaign Standard, selain daripada apa yang anda akan import, anda boleh melangkau langkah ini.

## <a name="import-data-into-adobe-campaign-standard"></a>Import data ke dalam Adobe Campaign Standard

Sekarang semuanya sudah ada, kita perlu mengimport data khalayak yang disediakan dari Wawasan Pelanggan ke dalam Adobe Standard Kempen untuk membuat profil. Ketahui [Cara mengimport profil dalam Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) menggunakan aliran kerja.

Aliran kerja import dalam imej di bawah telah dikonfigurasikan untuk dijalankan setiap lapan jam dan mencari segmen Wawasan Pelanggan yang dieksport (.csv fail dalam Azure Blob Storage). Aliran kerja mengekstrak kandungan fail .csv dalam susunan lajur yang ditentukan. Aliran kerja ini telah dibina untuk melaksanakan pengendalian ralat asas dan memastikan setiap rekod mempunyai alamat e-mel sebelum penghidratan data dalam Adobe Campaign Standard. Aliran kerja juga mengekstrak nama segmen daripada nama fail sebelum upserting ke dalam data profil Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Syot layar aliran kerja import dalam antara muka pengguna Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Dapatkan khalayak dalam Adobe Campaign Standard

Sebaik sahaja data diimport ke dalam Adobe Campaign Standard, anda [boleh mencipta aliran kerja](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) dan [pertanyaan](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) pelanggan berdasarkan pada *Nama Segmen* dan *Tarikh Segmen* untuk memilih profil yang telah dikenal pasti untuk kempen sampel kami.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Cipta dan hantar e-mel menggunakan Adobe Campaign Standard

Cipta kandungan e-mel dan kemudian [uji dan hantar](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-mel anda.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mel sampel dengan tawaran pembaharuan daripada Adobe Campaign Standard.":::
