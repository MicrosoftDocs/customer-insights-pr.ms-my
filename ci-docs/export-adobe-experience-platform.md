---
title: Eksport segmen ke Adobe Experience Platform (pratonton)
description: Ketahui cara menggunakan segmen Wawasan Pelanggan dalam Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195301"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Eksport segmen ke Adobe Experience Platform (pratonton)

Eksport segmen yang menyasarkan khalayak yang berkaitan kepada Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Gambar rajah proses langkah digariskan dalam artikel ini.":::

## <a name="prerequisites"></a>Prasyarat

- Lesen Adobe Experience Platform.
- Lesen Adobe Standard Kempen.
- [Nama akaun](/azure/storage/blobs/create-data-lake-storage-account) Azure Blob Storage dan kunci akaun. Untuk mencari nama dan kunci, lihat [Menguruskan tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Gambaran Keseluruhan Kempen

Untuk lebih memahami cara anda boleh menggunakan segmen daripada Wawasan Pelanggan dalam Adobe Experience Platform, mari lihat kempen sampel rekaan.

Mari kita anggap bahawa syarikat anda menawarkan perkhidmatan berasaskan langganan bulanan kepada pelanggan anda di Amerika Syarikat. Anda ingin mengenal pasti pelanggan yang langganan perlu diperbaharui dalam tempoh lapan hari akan datang tetapi belum memperbaharui langganan mereka. Untuk menyimpan pelanggan ini, anda mahu menghantar mereka tawaran promosi melalui e-mel, menggunakan Adobe Experience Platform.

Dalam contoh ini, kami ingin menjalankan kempen e-mel promosi sekali. Artikel ini tidak meliputi penggunaan kes menjalankan kempen lebih daripada sekali.

## <a name="identify-your-target-audience"></a>Kenal pasti khalayak sasaran anda

Dalam senario kami, kami menganggap bahawa alamat e-mel pelanggan tersedia dalam Wawasan Pelanggan dan pilihan promosi mereka dianalisis untuk mengenal pasti ahli segmen.

Segmen [yang anda tentukan dalam Wawasan](segments.md) Pelanggan dipanggil **ChurnProneCustomers** dan anda merancang untuk menghantar promosi e-mel kepada pelanggan ini.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Petikan skrin halaman segmen dengan segmen ChurnProneCustomers dicipta.":::

E-mel tawaran yang ingin anda hantar akan mengandungi nama pertama, nama akhir dan tarikh tamat langganan pelanggan. Pelanggan dimaklumkan tentang diskaun yang akan mereka dapat jika mereka memperbaharui langganan mereka sebelum ia berakhir.

## <a name="export-your-target-audience"></a>Eksport khalayak sasaran anda

Kami akan mengkonfigurasi eksport daripada Wawasan Pelanggan kepada akaun Storan Azure Blob.

### <a name="set-up-connection-to-azure-blob-storage"></a>Sediakan sambungan ke Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Azure Blob Storage**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama akaun**, **Kekunci akaun** dan **Bekas** untuk akaun Storan Blob anda di tempat anda mahu mengeksport segmen.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Petikan skrin konfigurasi akaun storan. ":::

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

### <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Storan Blob Azure. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Pilih segmen yang ingin anda eksport. Dalam contoh ini, ia **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Petikan skrin antara muka pengguna pemilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Pastikan bilangan rekod dalam segmen yang dieksport adalah dalam had yang dibenarkan bagi lesen Adobe Campaign Standard.

Data yang dieksport disimpan dalam bekas Storan Azure Blob yang anda konfigurasikan. Laluan folder berikut dicipta secara automatik dalam bekas anda:

- Untuk entiti sumber dan entiti yang dijana oleh sistem:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- *model.json* untuk entiti yang dieksport ditempatkan di peringkat *%ExportDestinationName%*.

  Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Takrifkan Model Data Pengalaman (XDM) dalam Adobe Experience Platform

Sebelum data yang dieksport dari Wawasan Pelanggan boleh digunakan dalam Adobe Experience Platform, tentukan skema Model Data Pengalaman dan [konfigurasikan data untuk Profil](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) Pelanggan Masa Nyata.

Ketahui [maksud XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) dan fahami [asas komposisi skema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Import data ke dalam Adobe Experience Platform

Import data khalayak yang disediakan daripada Wawasan Pelanggan ke dalam Adobe Experience Platform.

1. [Cipta sambungan](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started) sumber Storan Azure Blob.

1. [Konfigurasikan aliran](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) data untuk sambungan kumpulan storan awan untuk mengimport output segmen daripada Wawasan Pelanggan ke dalam Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Cipta khalayak dalam Adobe Campaign Standard

Untuk menghantar e-mel bagi kempen ini, kami akan menggunakan Adobe Campaign Standard.

1. [Cipta khalayak](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) dalam Adobe Standard Kempen menggunakan data dalam Adobe Experience Platform.

1. [Gunakan pembina](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) segmen dalam Adobe Standard Kempen untuk menentukan khalayak berdasarkan data dalam Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Cipta dan hantar e-mel menggunakan Adobe Campaign Standard

Cipta kandungan e-mel dan kemudian [uji dan hantar](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-mel anda.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mel sampel dengan tawaran pembaharuan daripada Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
