---
title: Eksport segmen ke Adobe Experience Platform (pratonton)
description: Ketahui cara menggunakan segmen Wawasan Pelanggan dalam Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: c29b8264019669ffd954a298ce3a633c852477fa
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052522"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Eksport segmen ke Adobe Experience Platform (pratonton)

Sebagai pengguna Dynamics 365 Customer Insights, anda mungkin telah membuat segmen untuk menjadikan kempen pemasaran anda lebih cekap dengan menyasarkan khalayak yang berkaitan. Untuk menggunakan segmen daripada Wawasan Adobe Experience Platform Pelanggan dan aplikasi seperti Adobe Standard Kempen, anda perlu mengikuti beberapa langkah yang digariskan dalam artikel ini.

:::image type="content" source="media/AEP-flow.png" alt-text="Gambar rajah proses langkah digariskan dalam artikel ini.":::

## <a name="prerequisites"></a>Prasyarat

-   Lesen Dynamics 365 Customer Insights
-   Lesen Adobe Experience Platform
-   Lesen Adobe Campaign Standard
-   Akaun Storan Blob Azure

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

Dengan khalayak sasaran kami dikenal pasti, kami boleh mengkonfigurasi eksport daripada Wawasan Pelanggan kepada akaun Storan Azure Blob.

### <a name="configure-a-connection"></a>Konfigurasikan sambungan

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Storan Blob Azure** atau pilih **Sediakan** dalam jubin **Storan Blob Azure** untuk mengkonfigurasikan sambungan.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Jubin konfigurasi untuk Storan Blob Azure."::: 

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama akaun**, **Kekunci akaun** dan **Bekas** untuk akaun Storan Blob anda di tempat anda mahu mengeksport segmen.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Petikan skrin konfigurasi akaun storan. "::: 
   
    - Untuk mengetahui lebih lanjut tentang cara mencari nama akaun dan kekunci akaun Storan Blob, lihat [Urus tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).
    - Untuk mengetahui cara untuk mencipta bekas, lihat [Cipta bekas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pilih **Simpan** untuk melengkapkan sambungan. 

### <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Storan Blob Azure. Jika anda tidak melihat nama bahagian ini, maka tiada sambungan jenis ini tersedia untuk anda.

1. Pilih segmen yang ingin anda eksport. Dalam contoh ini, ia **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Petikan skrin antara muka pengguna pemilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. Pilih **Simpan**.

Selepas menyimpan destinasi eksport, anda akan menemuinya dalam **Data** > **Eksport**.

Anda kini boleh [mengeksport segmen atas permintaan](export-destinations.md#run-exports-on-demand). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md).

> [!NOTE]
> Pastikan bilangan rekod dalam segmen yang dieksport adalah dalam had yang dibenarkan bagi lesen Adobe Campaign Standard.

Data yang dieksport disimpan dalam bekas Storan Blob Azure yang anda konfigurasikan di atas. Laluan folder berikut dicipta secara automatik dalam bekas anda:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* untuk entiti yang dieksport ditempatkan di peringkat *%ExportDestinationName%*.

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Takrifkan Model Data Pengalaman (XDM) dalam Adobe Experience Platform

Sebelum data yang dieksport daripada Wawasan Pelanggan boleh digunakan dalam Adobe Experience Platform, kita perlu menentukan skema Model Data Pengalaman dan [mengkonfigurasi data untuk Profil](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) Pelanggan Masa Nyata.

Ketahui [maksud XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) dan fahami [asas komposisi skema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Import data ke dalam Adobe Experience Platform

Sekarang bahawa semuanya sudah ada, kita perlu mengimport data khalayak yang disediakan dari Wawasan Pelanggan ke dalam Adobe Experience Platform.

Pertama, [cipta sambungan sumber Storan Blob Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Selepas menentukan sambungan sumber, [konfigurasikan aliran](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) data untuk sambungan kumpulan storan awan untuk mengimport output segmen daripada Wawasan Pelanggan ke dalam Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Cipta khalayak dalam Adobe Campaign Standard

Untuk menghantar e-mel bagi kempen ini, kami akan menggunakan Adobe Campaign Standard. Selepas mengimport data ke dalam Adobe Experience Platform, kami perlu [mencipta khalayak](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) dalam Adobe Campaign Standard menggunakan data dalam Adobe Experience Platform.


Ketahui cara [menggunakan pembina segmen](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) dalam Adobe Campaign Standard untuk mentakrifkan khalayak berdasarkan data dalam Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Cipta dan hantar e-mel menggunakan Adobe Campaign Standard

Cipta kandungan e-mel dan kemudian [uji dan hantar](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-mel anda.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="E-mel sampel dengan tawaran pembaharuan daripada Adobe Campaign Standard.":::
