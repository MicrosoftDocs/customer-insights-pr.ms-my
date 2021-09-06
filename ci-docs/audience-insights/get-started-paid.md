---
title: Cipta dan konfigurasikan lesen berbayar Customer Insights
description: Langkah-langkah untuk mendapatkan langganan berlesen untuk Dynamics 365 Customer Insights dan mengkonfigurasikannya.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034463"
---
# <a name="get-started-with-a-paid-subscription"></a>Mari bermula dengan langganan berbayar

Artikel ini menerangkan cara untuk mencipta persekitaran baharu selepas organisasi anda telah membeli langganan Dynamics 365 Customer Insights. Jika anda ingin membeli Customer Insights, pilihan kenalan kami disenaraikan di [laman web Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Jika anda ingin mencuba perkhidmatan dan ciri, lihat [Sediakan persekitaran percubaan](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Cipta persekitaran dalam organisasi sedia ada

Selepas membeli lesen langganan untuk Customer Insights, pentadbir global penyewa Microsoft 365 menerima e-mel yang menjemput mereka untuk mencipta persekitaran. Pergi ke [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) untuk bermula. 

Customer Insights tidak dilesenkan bagi setiap pengguna, jadi ia tidak akan ditunjukkan di kawasan Lesen. Jika anda sedang mencari lesen di pusat pentadbir Microsoft 365, pergi ke **Produk anda**. 

> [!NOTE]
> Organisasi boleh mencipta *dua* persekitaran untuk setiap lesen Customer Insights. Jika organisasi anda membeli lebih daripada satu lesen, sila [hubungi pasukan sokongan kami](https://go.microsoft.com/fwlink/?linkid=2079641) untuk meningkatkan bilangan persekitaran yang tersedia. Untuk maklumat lanjut tentang kapasiti dan kapasiti tambahan, muat turun [panduan pelesenan Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Untuk mencipta persekitaran:

1. Dalam dialog **Cipta persekitaran**, pilih **Persekitaran Baharu**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog untuk mencipta persekitaran Customer Insights baharu.":::

   Kami mengesyorkan untuk mula menyediakan persekitaran dari awal. Walau bagaimanapun, jika anda seorang pentadbir atau ahli persekitaran percubaan, anda boleh [menyalin data daripada persekitaran lain](manage-environments.md#copy-the-environment-configuration), dengan memilih **Salin daripada persekitaran sedia ada**. Anda akan melihat semua persekitaran yang tersedia dalam organisasi anda yang boleh anda salin data daripadanya.

1. Sediakan butiran berikut:
   - **Nama**: Nama untuk persekitaran ini. Medan ini sudah diisikan jika anda telah menyalin persekitaran sedia ada tetapi anda boleh mengubahnya.
   - **Rantau**: Rantau yang perkhidmatan diatur letak dan dihoskan di dalamnya.
   - **Jenis**: Pilih sama ada anda mahu mencipta persekitaran pengeluaran atau kotak pasir. Persekitaran kotak pasir tidak membenarkan segar semula data berjadual dan bertujuan untuk pra-pelaksanaan dan ujian.
   
1. Secara pilihan, anda boleh memilih **Tetapan lanjutan**:

   - **Simpan semua data pada**: Menentukan tempat anda mahu menyimpan data keluaran yang dijanakan daripada Customer Insights. Anda akan mempunyai dua pilihan: **Storan persekitaran** (Azure Data Lake  yang diuruskan oleh pasukan Customer Insights) dan **Azure Data Lake Storage** (Azure Data Lake Storage anda sendiri). Secara lalai, pilihan storan Customer Insights dipilih.

     > [!NOTE]
     > Dengan menyimpan data di Azure Data Lake Storage, anda bersetuju bahawa data akan dipindahkan dan disimpan di lokasi geografi yang sesuai untuk akaun storan Azure tersebut, yang mungkin berbeza daripada lokasi data yang disimpan dalam Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat Amanah Microsoft.](https://www.microsoft.com/trust-center)
     >
     > Pada masa ini, entiti yang diinjes daripada aliran data Power BI disimpan dalam Data Lake yang diuruskan oleh Microsoft Dataverse. 
     > 
     > Kami menyokong akaun Azure Data Lake Storage sahaja dari rantau Azure yang sama yang anda pilih semasa mencipta persekitaran. 
     > 
     > Kami menyokong akaun Azure Data Lake Storage sahaja yang mempunyai ruang nama berhierarki didayakan.


   - Untuk pilihan Azure Data Lake Storage, anda boleh memilih antara pilihan berasaskan sumber dan pilihan berasaskan langganan untuk pengesahan. Untuk maklumat lanjut, lihat [Sambungkan cerapan khalayak ke akaun Azure Data Lake Storage Gen2 dengan prinsipal perkhidmatan Azure](connect-service-principal.md). Nama **Bekas** tidak boleh ditukar dan akan menjadi `customerinsights`.
   
   - Jika anda ingin menggunakan [model luar kotak](predictions-overview.md#out-of-box-models), konfigurasikan perkongsian data dengan Microsoft Dataverse, atau dayakan pengingesan data daripada sumber data di premis, sediakan URL persekitaran Microsoft Dataverse di bawah **Konfigurasikan perkongsian data dengan Microsoft Dataverse dan dayakan keupayaan tambahan**. Pilih **Dayakan perkongsian data** untuk berkongsi data output Customer Insights dengan Microsoft Dataverse Data Lake Terurus.

     > [!NOTE]
     > - Perkongsian data dengan Microsoft Dataverse Data Lake Terurus pada masa ini tidak disokong apabila anda menyimpan semua data ke Azure Data Lake Storage anda sendiri.
     > - [Ramalan nilai yang hilang dalam entiti](predictions.md) pada masa ini tidak disokong apabila anda mendayakan perkongsian data dengan Data Lake Terurus Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Pilihan konfigurasi untuk mendayakan perkongsian data dengan Microsoft Dataverse.":::

   Apabila proses sistem seperti pengingesan data selesai, sistem mencipta folder yang sepadan dalam akaun storan yang anda tentukan. Fail data dan fail model.json dicipta dan ditambah pada folder berdasarkan nama proses.

   Jika anda mencipta berbilang persekitaran Customer Insights dan memilih untuk menyimpan entiti output daripada persekitaran tersebut dalam akaun storan anda, folder berasingan akan dicipta untuk setiap persekitaran dengan ci_<environmentid> dalam container.

1. Pilih **Cipta** untuk menyediakan persekitaran. 

## <a name="configure-an-environment"></a>Konfigurasikan persekitaran

Semak artikel berikut untuk membantu anda bermula dengan mengkonfigurasikan Customer Insights. 

- [Tambah lebih ramai pengguna dan peruntukkan keizinan](permissions.md).
- [Injes sumber data anda](data-sources.md) dan jalankannya melalui [proses penyatuan data](data-unification.md) untuk mendapatkan [profil pelanggan disatukan](customer-profiles.md).
- [Perkayakan profil pelanggan disatukan](enrichment-hub.md) atau [jalankan model ramalan](predictions-overview.md).
- Cipta [segmen](segments.md) kepada pelanggan kumpulan dan [ukur](measures.md) semakan KPI.
- Sediakan [sambungan](connections.md) dan [eksport](export-destinations.md) untuk memproses subset data anda dalam aplikasi lain.
