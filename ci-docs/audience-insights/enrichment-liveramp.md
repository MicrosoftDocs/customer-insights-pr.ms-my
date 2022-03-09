---
title: Pengayaan data identiti LiveRamp
description: Memperkayakan profil pelanggan dengan data LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373073"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Memperkayakan profil pelanggan dengan data identiti daripada LiveRamp (Pratonton) 

LiveRamp menyediakan resolusi identiti luar talian yang menentukan dan penyatuan data pelanggan. Anda boleh memetakan pengecam peribadi dalam data pelanggan anda ke graf identiti AbiliTec dan menerima ID AbiliTec. Anda kemudian boleh menggunakan ID ini untuk penyatuan data pelanggan anda yang lebih baik. 

## <a name="prerequisites"></a>Prasyarat 

Untuk mengkonfigurasi pengayaan, prasyarat berikut mesti dipenuhi: 

- Anda mempunyai langganan LiveRamp yang aktif. Untuk mendapatkan langganan, hubungi pasukan akaun LiveRamp anda atau untuk [dynamics@liveramp.com](mailto:dynamics@liveramp.com) mendapatkan maklumat lanjut.   

- Langganan AbiliTec yang aktif dengan ID pelanggan dan rahsia untuk mengakses API. Untuk maklumat lanjut, lihat [Hab Pembangun API AbiliTec](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Negara/rantau yang disokong 

Kami kini menyokong memperkayakan profil pelanggan dengan data LiveRamp di Amerika Syarikat sahaja. 

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan 

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**. 

1. Pilih **Memperkayakan data** saya pada **jubin Identiti**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Jubin identiti dalam halaman gambaran keseluruhan pengayaan.":::

1. Pilih [sambungan](connections.md) daripada senarai juntai bawah. Hubungi pentadbir jika tiada sambungan tersedia. Jika anda seorang pentadbir, anda boleh mencipta sambungan dengan **memilih Tambah sambungan**. Pilih **LiveRamp** daripada senarai juntai bawah. 

1. Pilih **Seterusnya** dan pilih set **data Pelanggan yang** anda ingin perkayakan dengan data identiti daripada LiveRamp. Anda boleh memilih *entiti Pelanggan* untuk memperkayakan semua profil pelanggan anda atau memilih *entiti segmen* untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut. 

1. Pilih **Seterusnya** dan takrifkan jenis medan daripada profil bersatu anda yang patut digunakan untuk mencari data identiti yang sepadan daripada LiveRamp. Sekurang-kurangnya satu medan **Nama dan alamat**, **Telefon** atau **E-mel** diperlukan. 

   > [!TIP]
   > Lebih banyak pengecam dan medan utama yang anda petakan, semakin banyak kemungkinan kadar padanan yang lebih tinggi 

1. Petakan medan daripada entiti Pelanggan *bersatu* anda yang akan digunakan untuk dipadankan dengan graf ID AbiliTec LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Pilihan pemetaan data untuk pengayaan LiveRamp.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan. 

1. **Sediakan Nama** untuk pengayaan dan **entiti** Output. 

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda. 

## <a name="configure-the-connection-for-liveramp"></a>Konfigurasikan sambungan untuk LiveRamp 

Anda perlu menjadi pentadbir untuk [mengkonfigurasi sambungan](connections.md). Pilih **Tambah sambungan** apabila mengkonfigurasi pengayaan atau pergi ke **Sambungan Pentadbir** > **dan** pilih **Sediakan** pada **jubin LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Anak tetingkap konfigurasi untuk menyediakan sambungan ke perkhidmatan LiveRamp AbiliTec.":::

1. Untuk **nama** Paparan, masukkan nama sambungan. 

1. Sediakan ID pelanggan LiveRamp yang sah dan rahsia. 

1. Semak semula dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**. 

1. Pilih **Sahkan** untuk mengesahkan konfigurasi. 

1. Untuk melengkapkan sambungan, pilih **Simpan**. 

## <a name="enrichment-results"></a>Keputusan pengayaan 

Untuk memulakan proses pengayaan, pilih Jalankan dari bar perintah. Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian [daripada segar semula berta penjadualan](system.md#schedule-tab). Masa pemprosesan bergantung pada saiz data pelanggan anda. 

Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **pengayaan** saya. Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya. 

Anda boleh mengakses pandangan terperinci setiap profil yang diperkaya dengan **memilihMakanpkan data yang diperkaya**. 

## <a name="next-steps"></a>Langkah-langkah berikutnya

Bina di atas data pelanggan anda yang diperkaya. Gunakan ID AbiliTec untuk menyatukan profil pelanggan ke dalam pandangan berasaskan seseorang. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan 

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke LiveRamp, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan liveRamp memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, semak kenyataan [Privasi](https://go.microsoft.com/fwlink/?linkid=396732) Microsoft. Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]