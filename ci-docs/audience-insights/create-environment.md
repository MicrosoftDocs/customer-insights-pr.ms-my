---
title: Cipta persekitaran dalam Customer Insights
description: Langkah untuk mencipta persekitaran dengan langganan berlesen untuk Dynamics 365 Customer Insights.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 914af46d2d82f3556d149f2836680c902f826d50
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673402"
---
# <a name="create-an-environment-in-audience-insights"></a>Cipta persekitaran dalam cerapan khalayak

Artikel ini menerangkan cara untuk mencipta persekitaran baharu selepas organisasi anda telah membeli langganan Dynamics 365 Customer Insights. 

Organisasi boleh mencipta *dua* persekitaran untuk setiap lesen Customer Insights. Jika organisasi anda membeli lebih daripada satu lesen, [hubungi pasukan sokongan kami](https://go.microsoft.com/fwlink/?linkid=2079641) untuk menambah bilangan persekitaran yang tersedia. Untuk maklumat lanjut tentang kapasiti dan kapasiti tambahan, muat turun [panduan pelesenan Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Jika anda sedang mencari untuk mencuba perkhidmatan ini, lihat [Sediakan persekitaran percubaan](../trial-signup.md).

## <a name="create-a-new-environment"></a>Cipta persekitaran baharu

Selepas membeli lesen langganan untuk Customer Insights, pentadbir global penyewa Microsoft 365 menerima e-mel yang menjemput mereka untuk mencipta persekitaran. Pergi ke [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) untuk bermula. 

Pengalaman dipandu membantu anda melalui langkah untuk mengumpulkan semua maklumat yang diperlukan untuk persekitaran baharu. Anda memerlukan [keizinan pentadbir](permissions.md) dalam cerapan khalayak untuk mencipta atau mengurus persekitaran.

1. Dalam cerapan khalayak, buka pemilih persekitaran dan pilih **+ Baharu**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Pilih pemilih persekitaran.":::

1. Ikuti pengalaman dipandu yang digariskan dalam bahagian berikut.

### <a name="step-1-provide-environment-information"></a>Langkah 1: Memberikan maklumat persekitaran

Dalam langkah **Maklumat asas**, pilih sama ada anda mahu mencipta persekitaran dari awal atau [menyalin data daripada persekitaran lain](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog untuk mencipta persekitaran Customer Insights baharu.":::

Sediakan butiran berikut:
   - **Nama**: Nama untuk persekitaran ini. Medan ini sudah diisikan jika anda telah menyalin persekitaran sedia ada tetapi anda boleh mengubahnya.
   - **Pilih perniagaan anda**: Pilih khalayak utama untuk persekitaran baharu. Anda boleh bekerja dengan pengguna individu (niaga-ke-pengguna) atau niaga-ke-niaga [akaun perniagaan](work-with-business-accounts.md).
   - **Jenis**: Pilih sama ada anda mahu mencipta persekitaran pengeluaran atau kotak pasir. Persekitaran kotak pasir tidak membenarkan segar semula data berjadual dan bertujuan untuk pra-pelaksanaan dan ujian. Persekitaran Kotak Pasir menggunakan cerapan utama yang sama dengan persekitaran pengeluaran dipilih pada masa ini.
   - **Rantau**: Rantau yang perkhidmatan diatur letak dan dihoskan di dalamnya.

### <a name="step-2-configure-data-storage"></a>Langkah 2: Konfigurasikan storan data

Dalam langkah **Storan data**, pilih tempat untuk menyimpan data daripada cerapan khalayak.

Anda akan mempunyai dua pilihan: **Storan Customer Insights** (Azure danau data yang diuruskan oleh pasukan Customer Insights) dan **Azure Data Lake Storage** (Azure Data Lake Storage anda sendiri). Secara lalai, pilihan storan Customer Insights dipilih.

:::image type="content" source="media/data-storage-environment.png" alt-text="Pilih Azure Data Lake Storage untuk menyimpan data cerapan khalayak anda.":::

Dengan menyimpan data kepada Azure Data Lake Storage, anda bersetuju bahawa data akan dipindahkan ke dan disimpan dalam lokasi geografi yang sesuai untuk akaun storan Azure tersebut. Lokasi ini mungkin berbeza dari mana data yang disimpan dalam Dynamics 365 Customer Insights. Ketahui lebih lanjut [Pusat Amanah Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights sedang menyokong yang berikut:
> - Entiti yang diinjes daripada aliran data Power BI yang disimpan dalam Data Lake terurus Microsoft Dataverse.  
> - Azure Data Lake Storage akaun daripada rantau Azure yang sama yang anda pilih semasa mencipta persekitaran.
> - Azure Data Lake Storage akaun yang mempunyai *ruang nama berhierarki* didayakan.

Untuk pilihan Azure Data Lake Storage, anda boleh memilih antara pilihan berasaskan sumber dan pilihan berasaskan langganan untuk pengesahan. Untuk mendapatkan maklumat lanjut, lihat [Sambung ke akaun Azure Data Lake Storage dengan menggunakan prinsipal perkhidmatan Azure](connect-service-principal.md). Nama **Bekas** akan menjadi `customerinsights` dan tidak boleh ditukar.

Apabila proses sistem seperti penginjesan data selesai, sistem mencipta folder yang sepadan dalam akaun storan yang anda tentukan. Fail data dan fail *model.json* dicipta dan ditambah ke folder berdasarkan nama proses.

Jika anda mencipta berbilang persekitaran Customer Insights dan memilih untuk menyimpan entiti output daripada persekitaran tersebut ke akaun storan anda, Customer Insights mencipta folder berasingan untuk setiap persekitaran dengan `ci_environmentID` di dalam bekas.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Langkah 3: Sambungkan ke Microsoft Dataverse
   
Langkah **Microsoft Dataverse** ini membolehkan anda menyambungkan Customer Insights dengan persekitaran Dataverse anda.

Untuk menggunakan [model ramalan di luar kotak](predictions-overview.md#out-of-box-models), konfigurasikan perkongsian data dengan Dataverse. Atau anda boleh mendayakan penginjesan data daripada sumber data di premis, menyediakan URL persekitaran Microsoft Dataverse yang mentadbir organisasi anda. Pilih **Dayakan perkongsian data** untuk berkongsi data output Customer Insights dengan danau data terurus Dataverse.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Pilihan konfigurasi untuk mendayakan perkongsian data dengan Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights tidak menyokong senario perkongsian data berikut:
> - Jika anda menyimpan semua data kepada Azure Data Lake Storage anda sendiri anda tidak akan dapat mendayakan perkongsian data dengan danau data terurus Dataverse.
> - Jika anda mendayakan perkongsian data dengan Dataverse, anda tidak akan dapat [mencipta nilai yang diramalkan atau hilang dalam entiti](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Langkah 4: Muktamadkan tetapan

Dalam langkah **Semak**, pergi ke semua tetapan yang ditetapkan. Apabila semuanya kelihatan lengkap, pilih **Cipta** untuk menetapkan persekitaran. 

Anda juga boleh mengubah kebanyakan tetapan kemudian. Untuk maklumat lanjut, lihat [Uruskan persekitaran](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Bekerja dengan persekitaran baharu anda

Semak semula artikel berikut untuk membantu anda bermula dengan mengkonfigurasi Customer Insights: 

- [Tambah lebih ramai pengguna dan peruntukkan keizinan](permissions.md).
- [Injes sumber data anda](data-sources.md) dan jalankannya melalui [proses penyatuan data](data-unification.md) untuk mendapatkan [profil pelanggan disatukan](customer-profiles.md).
- [Perkayakan profil pelanggan disatukan](enrichment-hub.md) atau [jalankan model ramalan](predictions-overview.md).
- [Cipta segmen](segments.md) untuk mengelompokkan pelanggan dan [ukuran](measures.md) untuk menyemak semula KPI.
- [Sediakan sambungan](connections.md) dan [eksport](export-destinations.md) untuk memproses subset data anda dalam aplikasi lain.
