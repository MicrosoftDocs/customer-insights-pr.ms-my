---
title: Eksport data ke Salesforce Marketing Cloud (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan mengeksport pada Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197049"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Eksport data ke Salesforce Marketing Cloud (pratonton)

Gunakan data pelanggan anda dalam Salesforce Marketing Cloud dengan mengeksport data itu melalui lokasi Protokol Pemindahan Fail Selamat (SFTP).

## <a name="prerequisites"></a>Prasyarat

- Hos [SFTP untuk Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) dan kelayakan pentadbir yang sepadan.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Sediakan sambungan ke Awan Pemasaran Salesforce

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Awan Pemasaran Salesforce**.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Secara lalai, ia hanya pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Menyediakan **Nama pengguna**, **Kata laluan**, **Nama hos**, dan **Eksport folder** untuk akaun SFTP anda.

1. Pilih **Sahkan** untuk menguji sambungan.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Pergi ke **Data** > **Eksport**.

1. Pilih **Tambah eksport**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian SFTP. Hubungi pentadbir jika tiada sambungan tersedia.

1. Masukkan nama untuk eksport.

1. Pilih sama ada anda mahu mengeksport data **Gzipped** atau **Unzipped** dan **penyahhad medan** untuk fail yang dieksport.

1. Pilih entiti, contohnya segmen, yang anda ingin eksport.

   > [!NOTE]
   > Setiap entiti yang dipilih akan dibahagikan kepada maksimum lima fail output apabila dieksport.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Import data Customer Insights daripada from lokasi pada Salesforce Marketing Cloud

1. Cipta [sambungan data dalam Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) untuk mengimport fail data Customer Insights daripada lokasi SFTP.

2. [Import data daripada lokasi SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) ke dalam sambungan data Salesforce Marketing Cloud.

3. Sediakan automasi untuk mengimport data ke dalam sambungan data. Ketahui lebih lanjut tentang [automasi penurunan fail dan automasi berjadual](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Tentukan [automasi penurunan fail](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) atau [automasi berjadual](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Berikut ialah contoh bagi [automasi dengan SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
