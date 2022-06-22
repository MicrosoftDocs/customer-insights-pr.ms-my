---
title: Cara - Buat persekitaran baru
description: Langkah-langkah untuk mewujudkan persekitaran dengan untuk Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 6dfaa09cd80498e9a4e4dea6a07ce6e9d29105e2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011622"
---
# <a name="how-to-create-a-new-environment"></a>Cara: Buat persekitaran baru

Selepas [membeli lesen langganan untuk Dynamics 365 Customer Insights](paid-license.md), pentadbir Microsoft 365 global penyewa menerima e-mel yang menjemput mereka untuk mewujudkan persekitaran. Pergi ke [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) untuk bermula. Dalam senario ini, anda boleh pergi terus ke [Langkah 1: Berikan maklumat asas](#step-1-provide-basic-information).

Selepas persekitaran pertama dicipta, pentadbir Microsoft 365 global penyewa boleh [menambah pengguna membentuk organisasi mereka sebagai pentadbir](permissions.md). Melangkah ke hadapan, pentadbir ini boleh menguruskan pengguna dan persekitaran. Jika organisasi anda membeli lebih daripada satu lesen untuk Wawasan Pelanggan, [hubungi pasukan](https://go.microsoft.com/fwlink/?linkid=2079641) sokongan kami untuk meningkatkan bilangan persekitaran yang tersedia. Untuk maklumat lanjut tentang kapasiti dan kapasiti tambahan, semak [panduan](https://go.microsoft.com/fwlink/?LinkId=866544) pelesenan Dynamics 365.

> [!TIP]
> Jika anda sedang mencari untuk mencuba perkhidmatan ini, lihat [Sediakan persekitaran percubaan](trial-signup.md).

## <a name="prerequisites"></a>Prasyarat

Anda memerlukan [keizinan](permissions.md) pentadbir dalam Wawasan Pelanggan untuk mencipta atau mengurus persekitaran.

## <a name="start-the-environment-creation-process"></a>Mulakan proses penciptaan persekitaran

1. Buka pemilih persekitaran dan pilih **+ Baru**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Pilih pemilih persekitaran.":::

1. Ikuti pengalaman berpandu yang digariskan dalam seksyen berikut untuk menyediakan semua maklumat yang diperlukan untuk persekitaran baharu. Jika anda mengkonfigurasi persekitaran lebih awal, anda juga [boleh menyalin konfigurasi](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Langkah 1: Berikan maklumat asas

Dalam langkah **Maklumat asas**, pilih sama ada anda mahu mencipta persekitaran dari awal atau [menyalin data daripada persekitaran lain](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog untuk mencipta persekitaran Customer Insights baharu.":::

Sediakan butiran berikut:

- **Nama**: Nama untuk persekitaran ini. Medan ini sudah diisikan jika anda telah menyalin persekitaran sedia ada tetapi anda boleh mengubahnya.
- **Pilih perniagaan anda**: Pilih khalayak utama untuk persekitaran baharu. Anda boleh bekerja dengan pengguna individu (niaga-ke-pengguna) atau niaga-ke-niaga [akaun perniagaan](work-with-business-accounts.md). Jika organisasi anda terutamanya menjalankan perniagaan dengan individu, seperti peruncit atau kedai kopi, pilih pengguna individu. Sekiranya khalayak utama anda adalah syarikat lain, seperti pengeluar kereta atau syarikat kertas, pilih akaun perniagaan.
- **Jenis**: Pilih sama ada anda mahu mencipta persekitaran pengeluaran atau kotak pasir. Persekitaran kotak pasir tidak membenarkan segar semula data berjadual dan bertujuan untuk pra-pelaksanaan dan ujian. Persekitaran Kotak Pasir menggunakan cerapan utama yang sama dengan persekitaran pengeluaran dipilih pada masa ini.
- **Rantau**: Rantau yang perkhidmatan diatur letak dan dihoskan di dalamnya. Untuk [menggunakan akaun Azure Data Lake Storage anda sendiri](own-data-lake-storage.md) atau [menyambung ke organisasi Microsoft Dataverse sedia ada](customer-insights-dataverse.md), persekitaran Wawasan Pelanggan mesti berada di rantau yang sama.

## <a name="step-2-configure-data-storage"></a>Langkah 2: Konfigurasikan storan data

**Dalam langkah Storan** data, pilih tempat untuk menyimpan data Wawasan Pelanggan.

Terdapat dua pilihan yang boleh anda pilih:

- **Storan** Wawasan Pelanggan: Storan data diuruskan oleh pasukan Wawasan Pelanggan. Ini adalah pilihan lalai dan melainkan terdapat keperluan khusus untuk menyimpan data dalam akaun storan anda sendiri, kami mengesyorkan menggunakan pilihan ini.
- **Azure Data Lake Storage**: Tentukan akaun anda sendiri Azure Data Lake Storage untuk menyimpan data supaya anda mempunyai kawalan penuh di mana data disimpan. Untuk maklumat lanjut, lihat [Gunakan akaun Azure Data Lake Storage anda sendiri](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Pilih pilihan pilihan untuk menyimpan data anda.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Langkah 3: Sambungkan ke Microsoft Dataverse

Langkah **Microsoft Dataverse** ini membolehkan anda menyambungkan Customer Insights dengan persekitaran Dataverse anda. Kongsi data dengan Dataverse untuk menggunakannya dengan aplikasi perniagaan berdasarkan Dataverse, seperti Dynamics 365 Marketing atau aplikasi berpandukan model dalam Power Apps.


Biarkan medan ini kosong jika anda tidak mempunyai persekitaran anda sendiri Dataverse dan kami akan mencipta satu untuk anda.

Untuk maklumat lanjut, lihat [Bekerja dengan data Wawasan Pelanggan dalam Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="perkongsian data dengan Microsoft Dataverse auto didayakan untuk persekitaran baru bersih.":::

### <a name="step-4-finalize-the-settings"></a>Langkah 4: Muktamadkan tetapan

**Dalam langkah Semak Semula**, pergi melalui semua tetapan yang ditentukan. Apabila semuanya kelihatan lengkap, pilih **Cipta** untuk menetapkan persekitaran.

Anda boleh menukar beberapa tetapan kemudian. Untuk maklumat lanjut, lihat [Uruskan persekitaran](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Bekerja dengan persekitaran baharu anda

Semak semula artikel berikut untuk membantu anda bermula dengan mengkonfigurasi Customer Insights:

- [Tambah lebih ramai pengguna dan peruntukkan keizinan](permissions.md).
- [Injes sumber data anda](data-sources.md) dan jalankannya melalui [proses penyatuan data](data-unification.md) untuk mendapatkan [profil pelanggan disatukan](customer-profiles.md).
- [Perkayakan profil pelanggan disatukan](enrichment-hub.md) atau [jalankan model ramalan](predictions-overview.md).
- [Cipta segmen](segments.md) untuk mengelompokkan pelanggan dan [ukuran](measures.md) untuk menyemak semula KPI.
- [Sediakan sambungan](connections.md) dan [eksport](export-destinations.md) untuk memproses subset data anda dalam aplikasi lain.

## <a name="copy-the-environment-configuration"></a>Salin konfigurasi persekitaran

Sebagai pentadbir, anda boleh memilih untuk menyalin konfigurasi daripada persekitaran sedia ada apabila anda mencipta konfigurasi baharu.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Syot layar pilihan tetapan dalam tetapan persekitaran.":::

Anda akan melihat semua persekitaran yang tersedia dalam organisasi anda yang boleh anda salin data daripadanya.

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

## <a name="set-up-a-copied-environment"></a>Sediakan persekitaran yang disalin

Apabila anda menyalin konfigurasi persekitaran, anda perlu melalui beberapa langkah tambahan untuk mengesahkan kelayakan:

- Profil pelanggan. Pertama, sahkan dan jejaki sumber data anda dan jalankan penyatuan data untuk mencipta semula profil pelanggan.
- Kelayakan sumber data. Anda perlu memberikan kelayakan untuk setiap sumber data untuk mengesahkan dan menyegar semula sumber data secara manual.
- Sumber data dari folder Model Data Biasa dan Dataverse. Anda perlu mencipta sumber data tersebut secara manual dengan nama yang sama seperti dalam persekitaran sumber.
- Rahsia sambungan yang digunakan untuk eksport dan pengayaan. Anda perlu membenarkan semula sambungan dan kemudian mengaktifkan semula pengayaan dan eksport.

Anda akan melihat mesej pengesahan apabila persekitaran yang disalin telah dicipta. Pilih **Pergi ke sumber data** untuk melihat senarai sumber data.

Semua sumber data akan menunjukkan status **Kelayakan Diperlukan**. Edit sumber data dan masukkan kelayakan untuk menyegarkan semula.

:::image type="content" source="media/data-sources-copied.png" alt-text="Senarai sumber data yang telah disalin dan memerlukan pengesahan.":::

Selepas menyegar semula sumber data, pergi ke **Data** > **Satukan**. Di sini anda akan menemui tetapan daripada persekitaran sumber. Mengeditnya seperti yang diperlukan atau pilih **Jalankan** untuk memulakan proses data penyatuan dan mencipta entiti pelanggan disatukan.

Apabila data penyatuan selesai, pergi ke **Langkah-langkah** dan **Segmen** untuk menyegarkan semula juga.

Sebelum anda mengaktifkan semula eksport dan pengayaan, pergi ke **Sambungan** > **Pentadbir** untuk membenarkan semula sambungan dalam persekitaran baharu anda.

[!INCLUDE [footer-include](includes/footer-banner.md)]
