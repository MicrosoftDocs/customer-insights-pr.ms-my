---
title: Eksport segmen Wawasan Pelanggan ke Adobe Standard Kempen (pratonton)
description: Ketahui cara menggunakan segmen Wawasan Pelanggan dalam Adobe Standard Kempen.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195531"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Eksport segmen Wawasan Pelanggan ke Adobe Standard Kempen (pratonton)

Eksport segmen yang menyasarkan khalayak yang berkaitan ke Adobe Standard Kempen.

:::image type="content" source="media/ACS-flow.png" alt-text="Gambar rajah proses langkah digariskan dalam artikel ini.":::

## <a name="prerequisites"></a>Prasyarat

- Lesen Adobe Standard Kempen.
- [Nama akaun](/azure/storage/blobs/create-data-lake-storage-account) Azure Blob Storage dan kunci akaun. Untuk mencari nama dan kunci, lihat [Menguruskan tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Gambaran keseluruhan kempen

Untuk lebih memahami cara anda boleh menggunakan segmen daripada Wawasan Pelanggan dalam Adobe Experience Platform, mari lihat kempen sampel rekaan.

Mari kita anggap bahawa syarikat anda menawarkan perkhidmatan berasaskan langganan bulanan kepada pelanggan anda di Amerika Syarikat. Anda ingin mengenal pasti pelanggan yang langganan perlu diperbaharui dalam tempoh lapan hari akan datang tetapi belum memperbaharui langganan mereka. Untuk menyimpan pelanggan ini, anda mahu menghantar mereka tawaran promosi melalui e-mel, menggunakan Adobe Campaign Standard.

Dalam contoh ini, kami ingin menjalankan kempen e-mel promosi sekali. Artikel ini tidak meliputi penggunaan kes menjalankan kempen lebih daripada sekali. Walau bagaimanapun, Wawasan Pelanggan dan Adobe Standard Kempen boleh dikonfigurasikan untuk berfungsi untuk senario kempen berulang juga.

## <a name="identify-your-target-audience"></a>Kenal pasti khalayak sasaran anda

Dalam senario kami, kami menganggap bahawa alamat e-mel pelanggan tersedia dalam Wawasan Pelanggan dan pilihan promosi mereka dianalisis untuk mengenal pasti ahli segmen.

Segmen [yang anda tentukan dalam Wawasan](segments.md) Pelanggan dipanggil **ChurnProneCustomers** dan anda merancang untuk menghantar promosi e-mel kepada pelanggan ini.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Petikan skrin halaman segmen dengan segmen ChurnProneCustomers dicipta.":::

E-mel tawaran yang ingin anda hantar akan mengandungi nama pertama, nama akhir dan tarikh tamat langganan pelanggan. Pelanggan dimaklumkan tentang diskaun yang akan mereka dapat jika mereka memperbaharui langganan mereka sebelum ia berakhir.

## <a name="export-your-target-audience"></a>Eksport khalayak sasaran anda

### <a name="set-up-connection-to-adobe-campaign"></a>Sediakan sambungan ke Adobe Kempen

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Adobe Kempen**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Masukkan nama** Akaun, **Kunci** Akaun dan Kontena **untuk** akaun Storan Blob anda.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Petikan skrin konfigurasi akaun storan. ":::

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

### <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport** pilih sambungan daripada bahagian Adobe Campaign. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Pilih segmen yang ingin anda eksport. Dalam contoh ini, ia **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Petikan skrin antara muka pengguna pemilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. Pilih **Seterusnya**.

1. Petakan **medan Sumber** daripada segmen Wawasan Pelanggan kepada **nama medan Sasaran** dalam Adobe skema profil Standard Kempen.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Pemetaan medan untuk penyambung Adobe Campaign Standard.":::

   Jika anda ingin menambah lebih banyak atribut, pilih **Tambah atribut**. Nama sasaran boleh berbeza daripada nama medan sumber supaya anda masih boleh memetakan output segmen daripada Wawasan Pelanggan kepada Adobe Standard Kempen jika medan tidak mempunyai nama yang sama dalam kedua-dua sistem.

   > [!NOTE]
   > Alamat e-mel digunakan sebagai medan identiti, tetapi anda boleh menggunakan sebarang pengecam lain daripada profil pelanggan untuk memetakan data kepada Adobe Standard Kempen.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Pastikan bilangan rekod dalam segmen yang dieksport adalah dalam had yang dibenarkan bagi lesen Adobe Campaign Standard.

Data yang dieksport disimpan dalam bekas Storan Blob Azure yang anda konfigurasikan di atas. Laluan folder berikut dicipta secara automatik dalam bekas anda: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurasikan Adobe Campaign Standard

Segmen yang dieksport mengandungi lajur yang anda pilih semasa mengkonfigurasi eksport. Data ini boleh digunakan untuk [mencipta profil dalam Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Untuk menggunakan segmen dalam Adobe Standard Kempen, [lanjutkan skema](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) profil dalam Adobe Standard Kempen untuk memasukkan dua medan tambahan.

Dalam contoh kami, medan ini ialah Nama Segmen dan Tarikh Segmen. Kami akan menggunakan medan ini untuk mengenal pasti profil dalam Adobe Campaign Standard yang kami mahu sasarkan untuk kempen ini.

Jika tiada rekod lain dalam Adobe Standard Kempen, selain daripada apa yang akan anda import, langkau langkah ini.

## <a name="import-data-into-adobe-campaign-standard"></a>Import data ke dalam Adobe Campaign Standard

Import data khalayak yang disediakan daripada Wawasan Pelanggan ke dalam Adobe Standard Kempen untuk [mencipta profil menggunakan aliran kerja](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Aliran kerja import dalam imej di bawah telah dikonfigurasikan untuk dijalankan setiap lapan jam dan mencari segmen Wawasan Pelanggan yang dieksport (.csv fail dalam Azure Blob Storage). Aliran kerja mengekstrak kandungan fail .csv dalam susunan lajur yang ditentukan. Aliran kerja ini telah dibina untuk melaksanakan pengendalian ralat asas dan memastikan setiap rekod mempunyai alamat e-mel sebelum penghidratan data dalam Adobe Campaign Standard. Aliran kerja juga mengekstrak nama segmen daripada nama fail sebelum upserting ke dalam data profil Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Syot layar aliran kerja import dalam antara muka pengguna Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Dapatkan khalayak dalam Adobe Campaign Standard

Setelah data diimport ke dalam Adobe Standard Kempen, [buat aliran kerja](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) dan [tanya](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) pelanggan berdasarkan Nama Segmen dan Tarikh Segmen untuk memilih profil yang dikenal pasti untuk kempen sampel kami.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Cipta dan hantar e-mel menggunakan Adobe Campaign Standard

Cipta kandungan e-mel dan kemudian [uji dan hantar](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-mel anda.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mel sampel dengan tawaran pembaharuan daripada Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
