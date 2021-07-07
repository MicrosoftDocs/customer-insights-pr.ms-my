---
title: Eksport data Customer Insights pada Salesforce Marketing Cloud
description: Ketahui cara mengkonfigurasikan sambungan dan mengeksport pada Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314648"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Segmen eksport dan data lain pada Salesforce Marketing Cloud (pratonton)

Gunakan data pelanggan anda dalam Salesforce Marketing Cloud dengan mengeksport data itu melalui lokasi Protokol Pemindahan Fail Selamat (SFTP).

## <a name="prerequisites-for-connection"></a>Prasyarat untuk sambungan

- Ketersediaan hos SFTP dan kelayakan pentadbir yang sepadan. [Cara menyediakan lokasi SFTP untuk Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a>Had diketahui

- Masa jalanan eksport bergantung pada prestasi sistem anda. Kami mengesyorkan dua CPU teras dan 1 Gb memori sebagai konfigurasi minimum pelayan anda. 
- Mengeksport entiti dengan sehingga 100 juta profil pelanggan boleh mengambil masa 90 minit apabila menggunakan konfigurasi minimum yang disyorkan. 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Sediakan sambungan kepada Salesforce Marketing Cloud

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Salesforce Marketing Cloud** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Menyediakan **Nama pengguna**, **Kata laluan**, **Nama hos**, dan **Eksport folder** untuk akaun SFTP anda.

1. Pilih **Sahkan** untuk menguji sambungan.

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian SFTP. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Pilih sama ada anda mahu mengeksport data **Gzipped** atau **Unzipped** dan **penyahhad medan** untuk fail yang dieksport.

1. Pilih entiti, contohnya segmen, yang anda mahu mengeksport.

   > [!NOTE]
   > Setiap entiti yang dipilih akan dibahagikan kepada lima fail output apabila dieksport. 

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Import data Customer Insights daripada from lokasi pada Salesforce Marketing Cloud

1. Cipta [sambungan data dalam Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) untuk mengimport fail data Customer Insights daripada lokasi SFTP.

2. [Import data daripada lokasi SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) ke dalam sambungan data Salesforce Marketing Cloud. 

3. Sediakan automasi untuk mengimport data ke dalam sambungan data. Ketahui lebih lanjut tentang [automasi penurunan fail dan automasi berjadual](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Tentukan [automasi penurunan fail](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) atau [automasi berjadual](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Berikut ialah contoh bagi [automasi dengan SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data melalui SFTP, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa destinasi eksport memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.

[!INCLUDE[footer-include](../includes/footer-banner.md)]