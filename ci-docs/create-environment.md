---
title: Cipta persekitaran baharu
description: Langkah-langkah untuk mewujudkan persekitaran dalam Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304255"
---
# <a name="create-a-new-environment"></a>Cipta persekitaran baharu

Selepas [membeli lesen langganan untuk Dynamics 365 Customer Insights](paid-license.md), pentadbir Microsoft 365 global penyewa menerima e-mel yang menjemput mereka untuk mencipta persekitaran. Pergi ke [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) untuk bermula. Dalam senario ini, mulakan dengan [Langkah 1: Berikan maklumat asas](#step-1-provide-basic-information).

Selepas persekitaran pertama dicipta, pentadbir Microsoft 365 global penyewa boleh [menambah pengguna dari organisasi mereka sebagai pentadbir](permissions.md). Pentadbir ini kemudiannya boleh menguruskan pengguna dan persekitaran. Jika organisasi anda membeli lebih daripada satu lesen untuk Wawasan Pelanggan, [hubungi pasukan](https://go.microsoft.com/fwlink/?linkid=2079641) sokongan kami untuk menambah bilangan persekitaran yang tersedia. Untuk maklumat lanjut mengenai kapasiti dan kapasiti tambahan, semak [panduan](https://go.microsoft.com/fwlink/?LinkId=866544) pelesenan Dynamics 365. Sebaik sahaja anda mempunyai keupayaan untuk mencipta persekitaran tambahan, pergi ke [Mulakan proses](#start-the-environment-creation-process) penciptaan persekitaran.

> [!TIP]
> Jika anda sedang mencari untuk mencuba perkhidmatan ini, lihat [Sediakan persekitaran percubaan](trial-signup.md).

## <a name="prerequisites"></a>Prasyarat

[Keizinan pentadbir](permissions.md) dalam Wawasan Pelanggan

## <a name="start-the-environment-creation-process"></a>Mulakan proses penciptaan persekitaran

1. Buka pemilih persekitaran dan pilih **+ Baharu**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Pilih pemilih persekitaran.":::

1. Ikuti pengalaman berpandu yang digariskan dalam seksyen berikut untuk menyediakan semua maklumat yang diperlukan untuk persekitaran baru.

## <a name="step-1-provide-basic-information"></a>Langkah 1: Berikan maklumat asas

1. Pilih sama ada anda ingin mencipta persekitaran dari awal atau menyalin data dari persekitaran lain. [Menyalin data daripada persekitaran](#copy-the-environment-configuration) lain memerlukan langkah tambahan.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog untuk mencipta persekitaran Customer Insights baharu.":::

1. Sediakan butiran berikut:

   - **Nama**: Nama untuk persekitaran ini. Medan ini sudah diisikan jika anda telah menyalin persekitaran sedia ada tetapi anda boleh mengubahnya.
   - **Pilih perniagaan** anda: Khalayak utama untuk persekitaran baharu: pengguna individu (B-to-C) atau [akaun](work-with-business-accounts.md) perniagaan (B-to-B). Jika organisasi anda kebanyakannya menjalankan perniagaan dengan individu, seperti peruncit atau kedai kopi, pilih pengguna individu. Jika khalayak utama anda adalah syarikat lain, seperti pengeluar kereta atau syarikat kertas, pilih akaun perniagaan.
   - **Jenis**: Jenis persekitaran: pengeluaran atau kotak pasir. Persekitaran kotak pasir tidak membenarkan segar semula data berjadual dan bertujuan untuk pra-pelaksanaan dan ujian. Persekitaran Kotak Pasir menggunakan cerapan utama yang sama dengan persekitaran pengeluaran dipilih pada masa ini.
   - **Rantau**: Rantau di mana perkhidmatan itu digunakan dan dihoskan. Untuk [menggunakan akaun Azure Data Lake Storage anda sendiri](own-data-lake-storage.md) atau [menyambung kepada organisasi Microsoft Dataverse yang sedia](customer-insights-dataverse.md) ada, persekitaran Wawasan Pelanggan mesti berada di rantau yang sama.

1. Pilih **Seterusnya**.

## <a name="step-2-configure-data-storage"></a>Langkah 2: Konfigurasikan storan data

1. Pilih tempat untuk menyimpan data Wawasan Pelanggan:

   - **Storan** Wawasan Pelanggan: Storan data diuruskan secara automatik. Ini adalah pilihan lalai dan melainkan terdapat keperluan khusus untuk menyimpan data dalam akaun storan anda sendiri, kami mengesyorkan menggunakan pilihan ini.
   - **Azure Data Lake Storage**: Akaun anda sendiri Azure Data Lake Storage untuk menyimpan data supaya anda mempunyai kawalan penuh di mana data disimpan. Ikut langkah dalam [Gunakan akaun Azure Data Lake Storage anda sendiri](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Pilih pilihan pilihan untuk menyimpan data anda.":::

1. Pilih **Seterusnya**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Langkah 3: Sambungkan ke Microsoft Dataverse

Jika anda mempunyai Dataverse persekitaran, sambungkan Wawasan Pelanggan. Kongsi data dengan Dataverse menggunakannya dengan aplikasi perniagaan berdasarkan Dataverse, seperti Dynamics 365 Pemasaran atau aplikasi yang didorong oleh model dalam Power Apps.

1. Ikuti langkah-langkah dalam [Mengendalikan data Wawasan Pelanggan dalam Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="perkongsian data dengan Microsoft Dataverse auto didayakan untuk persekitaran baharu bersih.":::

1. Pilih **Seterusnya**.

## <a name="step-4-finalize-the-settings"></a>Langkah 4: Muktamadkan tetapan

Semak semula seting yang ditentukan. Apabila semuanya kelihatan lengkap, pilih **Cipta** untuk menetapkan persekitaran.

Untuk mengubah beberapa seting kemudian, lihat [Menguruskan persekitaran](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Bekerja dengan persekitaran baharu anda

Semak semula artikel berikut untuk membantu anda bermula dengan mengkonfigurasi Customer Insights:

- [Tambah lebih ramai pengguna dan peruntukkan keizinan](permissions.md).
- [Injes sumber data anda](data-sources.md) dan jalankannya melalui [proses penyatuan data](data-unification.md) untuk mendapatkan [profil pelanggan disatukan](customer-profiles.md).
- [Perkayakan profil pelanggan disatukan](enrichment-hub.md) atau [jalankan model ramalan](predictions-overview.md).
- [Cipta segmen](segments.md) untuk mengelompokkan pelanggan dan [ukuran](measures.md) untuk menyemak semula KPI.
- [Sediakan sambungan](connections.md) dan [eksport](export-destinations.md) untuk memproses subset data anda dalam aplikasi lain.

## <a name="copy-the-environment-configuration"></a>Salin konfigurasi persekitaran

Sebagai pentadbir, jika anda memilih untuk menyalin konfigurasi daripada persekitaran sedia ada, pilih daripada senarai semua persekitaran yang tersedia dalam organisasi anda.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Syot layar pilihan tetapan dalam tetapan persekitaran.":::

Tetapan konfigurasi berikut disalin:

- Sumber data yang diimport melalui Power Query
- Konfigurasi penyatuan data
- Segmen
- Langkah
- Perhubungan
- Aktiviti
- Indeks carian & tapis
- Eksport
- Segar semula jadual
- Pengayaan
- Ramalan model
- Penugasan peranan

### <a name="set-up-a-copied-environment"></a>Menyediakan persekitaran yang disalin

Apabila anda menyalin konfigurasi persekitaran, mesej pengesahan dipaparkan apabila persekitaran yang disalin telah dicipta. Laksanakan langkah-langkah berikut untuk mengesahkan kelayakan.

1. Pilih **Pergi ke sumber data** untuk melihat senarai sumber data. Semua sumber data menunjukkan **status Kelayakan Diperlukan**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Senarai sumber data yang telah disalin dan memerlukan pengesahan.":::

1. Edit sumber data dan masukkan kelayakan untuk menyegarkan semula. Sumber data daripada folder Model Data Biasa dan Dataverse mesti dicipta secara manual dengan nama yang sama seperti dalam persekitaran sumber.

1. Selepas menyegar semula sumber data, pergi ke **Data** > **Satukan**. Di sini anda akan menemui tetapan daripada persekitaran sumber. Editnya mengikut keperluan atau pilih **Menyatukan** > **profil pelanggan dan kebergantungan untuk memulakan proses penyatuan data dan mewujudkan entiti pelanggan bersatu**.

   > [!TIP]
   > Untuk akaun dan kenalan, pilih **Menyatukan akaun** > **Menyatukan profil dan kebergantungan**.

1. Apabila penyatuan data selesai, pergi ke **Ukuran** dan **Segmen** untuk menyegar semulanya.

1. Pergi ke **Sambungan** > **Pentadbir** untuk mengesahkan semula sambungan dalam persekitaran baru anda.

1. Pergi ke **Pengayaan** > **Data** dan **Eksport** > **Data** untuk mengaktifkannya semula.

[!INCLUDE [footer-include](includes/footer-banner.md)]
