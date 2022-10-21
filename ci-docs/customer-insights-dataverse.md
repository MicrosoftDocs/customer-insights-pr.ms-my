---
title: Gunakan data Customer Insights dalam Microsoft Dataverse
description: Ketahui cara menyambungkan Wawasan Pelanggan dan Microsoft Dataverse memahami entiti output yang dieksport ke Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671262"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Gunakan data Customer Insights dalam Microsoft Dataverse

Customer Insights menyediakan pilihan untuk menjadikan entiti output tersedia dalam [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Integrasi ini membolehkan perkongsian data yang mudah dan pembangunan tersuai melalui pendekatan kod rendah / tanpa kod. Entiti [output](#output-entities) tersedia sebagai jadual dalam Dataverse persekitaran. Anda boleh menggunakan data untuk sebarang aplikasi lain berdasarkan Dataverse jadual. Jadual ini membolehkan senario seperti aliran kerja automatik melalui Power Automate atau membina aplikasi dengan Power Apps.

Menyambung ke persekitaran anda juga membolehkan anda Dataverse [menelan data daripada sumber data di premis menggunakan Power Platform aliran data dan get laluan](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Prasyarat

- Wawasan Pelanggan dan Dataverse persekitaran mesti dihoskan di rantau yang sama.
- Peranan pentadbir global yang ditubuhkan dalam persekitaran Dataverse. Sahkan sama ada persekitaran ini [Dataverse dikaitkan dengan](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) kumpulan keselamatan tertentu dan pastikan anda ditambahkan pada kumpulan keselamatan tersebut.
- Tiada persekitaran Wawasan Pelanggan lain yang telah dikaitkan dengan persekitaran yang Dataverse ingin anda sambungkan. Ketahui cara [mengalih keluar sambungan sedia ada kepada Dataverse persekitaran](#remove-an-existing-connection-to-a-dataverse-environment).
- Persekitaran yang Microsoft Dataverse disambungkan ke satu akaun storan jika anda mengkonfigurasi persekitaran untuk [menggunakan anda Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse Kelayakan kapasiti storan

Langganan Wawasan Pelanggan melayakkan anda mendapat kapasiti tambahan untuk kapasiti [Dataverse storan sedia ada](/power-platform/admin/capacity-storage) organisasi anda. Kapasiti tambahan bergantung pada bilangan profil yang digunakan oleh langganan anda.

**Contoh:**

Dengan mengandaikan anda mendapat storan pangkalan data 15 GB dan storan fail 20 GB setiap 100,000 profil pelanggan. Jika langganan anda termasuk 300,000 profil pelanggan, jumlah kapasiti storan anda ialah 45 GB (3 x 15 GB) storan pangkalan data dan storan fail 60 GB (3 x 20 GB). Begitu juga, jika anda mempunyai langganan B-to-B dengan akaun 30K, jumlah kapasiti storan anda ialah storan pangkalan data 45 GB (3 x 15 GB) dan storan fail 60 GB (3 x 20 GB).

Kapasiti log tidak bertambah dan ditetapkan untuk organisasi anda.

Untuk maklumat lanjut tentang kelayakan kapasiti terperinci, lihat [Panduan](https://go.microsoft.com/fwlink/?LinkId=866544) Pelesenan Dynamics 365.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Sambungkan persekitaran ke Dataverse Wawasan Pelanggan

Langkah ini **Microsoft Dataverse** membolehkan anda menghubungkan Wawasan Pelanggan dengan persekitaran anda Dataverse sambil [mewujudkan persekitaran](create-environment.md) Wawasan Pelanggan.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="perkongsian data dengan Microsoft Dataverse auto-enabled untuk persekitaran baharu.":::

1. Berikan URL kepada persekitaran anda atau biarkan kosong untuk dicipta untuk anda Dataverse.

   > [!NOTE]
   > Selepas mewujudkan hubungan antara Wawasan Pelanggan dan Dataverse, jangan ubah nama organisasi untuk persekitaran Dataverse. Nama organisasi digunakan dalam Dataverse URL dan nama yang diubah memutuskan sambungan dengan Wawasan Pelanggan.

   [Power Platform Pentadbir boleh mengawal orang yang boleh mencipta persekitaran Dataverse baharu](/power-platform/admin/control-environment-creation). Jika anda cuba menyediakan persekitaran Wawasan Pelanggan baharu dan tidak dapat, pentadbir mungkin telah melumpuhkan penciptaan Dataverse persekitaran untuk semua orang kecuali pentadbir.

1. Jika anda menggunakan akaun Storan Tasik Data anda sendiri:
   1. Pilih **Dayakan perkongsian** data dengan Dataverse.
   1. **Masukkan pengecam Keizinan**. Untuk mendapatkan pengecam keizinan, [dayakan perkongsian data dengan Dataverse daripada anda sendiri Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Dayakan perkongsian data dengan Dataverse daripada anda sendiri Azure Data Lake Storage (pratonton)

Dalam [akaun anda sendiri Azure Data Lake Storage, sahkan pengguna yang menyediakan persekitaran Wawasan Pelanggan mempunyai sekurang-kurangnya](own-data-lake-storage.md) keizinan Pembaca **Data Blob Storan pada** bekas dalam akaun`customerinsights` storan.

> [!NOTE]
> Perkongsian data hanya boleh digunakan jika anda menggunakan akaun anda sendiri Azure Data Lake Storage. Seting ini tidak tersedia jika persekitaran Wawasan Pelanggan menggunakan storan lalai Dataverse.

### <a name="limitations"></a>Batasan

- Hanya pemetaan satu-ke-satu antara Dataverse organisasi dan Azure Data Lake Storage akaun. Dataverse Setelah organisasi disambungkan ke akaun storan, ia tidak boleh bersambung ke akaun storan lain. Had ini menghalang Dataverse daripada mengisi berbilang akaun storan.
- Perkongsian data tidak akan berfungsi jika persediaan Azure Private Link diperlukan untuk mengakses akaun anda Azure Data Lake Storage kerana ia berada di belakang tembok api. Dataverse pada masa ini tidak menyokong sambungan ke titik akhir peribadi melalui Pautan Peribadi.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Sediakan kumpulan keselamatan sendiri Azure Data Lake Storage

1. Cipta dua kumpulan keselamatan pada langganan Azure anda - satu kumpulan keselamatan Pembaca **dan satu** **kumpulan keselamatan Penyumbang** dan tetapkan perkhidmatan sebagai Microsoft Dataverse pemilik untuk kedua-dua kumpulan keselamatan.

1. Urus Senarai Kawalan Akses (ACL) pada bekas dalam `customerinsights` akaun storan anda melalui kumpulan keselamatan ini.
   1. Tambah perkhidmatan dan Microsoft Dataverse sebarang aplikasi perniagaan berasaskan seperti Dataverse Pemasaran Dynamics 365 kepada **kumpulan keselamatan Pembaca** dengan **keizinan baca sahaja**.
   1. Tambah *aplikasi Wawasan Pelanggan sahaja* kepada **kumpulan keselamatan Penyumbang** untuk memberikan kedua-dua **keizinan baca dan tulis** untuk menulis profil dan pandangan.

### <a name="set-up-powershell"></a>Menyediakan PowerShell

Sediakan PowerShell untuk melaksanakan skrip PowerShell.

1. Pasang versi terkini [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. Pada PC anda, pilih kekunci Windows pada papan kekunci anda dan cari untuk **Windows PowerShell** dan pilih **Jalankan sebagai pentadbir**.
   1. Dalam tetingkap PowerShell yang terbuka, masukkan `Install-Module AzureAD`.

1. Import tiga modul.
   1. Dalam tetingkap PowerShell, masukkan `Install-Module -Name Az.Accounts` dan ikuti langkah-langkah.
   1. Ulangi untuk `Install-Module -Name Az.Resources` dan `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Melaksanakan skrip PowerShell dan mendapatkan Pengecam Keizinan

1. Muat turun dua skrip PowerShell yang perlu anda jalankan dari repo [GitHub jurutera](https://github.com/trin-msft/byol) kami.
   - `CreateSecurityGroups.ps1`: Memerlukan keizinan pentadbir penyewa.
   - `ByolSetup.ps1`: Memerlukan keizinan Pemilik Data Blob Storan di peringkat akaun storan/bekas. Skrip ini akan mencipta kebenaran untuk anda. Tugasan peranan anda boleh dialih keluar secara manual selepas berjaya menjalankan skrip.

1. Laksanakan `CreateSecurityGroups.ps1` dalam Windows PowerShell dengan menyediakan ID langganan Azure yang mengandungi anda Azure Data Lake Storage. Buka skrip PowerShell dalam editor untuk menyemak maklumat tambahan dan logik yang dilaksanakan.

   Skrip ini mencipta dua kumpulan keselamatan pada langganan Azure anda: satu untuk kumpulan Pembaca dan satu lagi untuk kumpulan Penyumbang. Microsoft Dataverse Perkhidmatan adalah pemilik untuk kedua-dua kumpulan keselamatan ini.

1. Simpan kedua-dua nilai ID kumpulan keselamatan yang dijana oleh skrip ini untuk digunakan dalam `ByolSetup.ps1` skrip.

   > [!NOTE]
   > Penciptaan kumpulan keselamatan boleh dinyahdayakan pada penyewa anda. Dalam kes itu, persediaan manual diperlukan dan pentadbir anda Azure AD perlu [mendayakan penciptaan kumpulan keselamatan](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Laksanakan `ByolSetup.ps1` dalam Windows PowerShell dengan menyediakan ID langganan Azure yang mengandungi Azure Data Lake Storage anda, nama akaun storan, nama kumpulan sumber dan nilai ID kumpulan keselamatan Pembaca dan Penyumbang. Buka skrip PowerShell dalam editor untuk menyemak maklumat tambahan dan logik yang dilaksanakan.

   Skrip ini menambah kawalan akses berasaskan peranan yang diperlukan untuk perkhidmatan dan Microsoft Dataverse mana-mana Dataverse aplikasi perniagaan berasaskan. Ia juga mengemas kini Senarai Kawalan Akses (ACL) pada `customerinsights` bekas untuk kumpulan keselamatan yang `CreateSecurityGroups.ps1` dicipta dengan skrip. Kumpulan Penyumbang diberikan keizinan rwx *dan kumpulan Pembaca diberikan* *keizinan r-x* sahaja.

1. Salin rentetan output yang kelihatan seperti: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Masukkan rentetan output yang disalin ke dalam **medan pengecam** Keizinan langkah konfigurasi persekitaran untuk Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opsyen konfigurasi untuk mendayakan perkongsian data daripada anda sendiri Azure Data Lake Storage dengan Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Mengalih keluar sambungan sedia ada kepada Dataverse persekitaran

Apabila menyambung ke Dataverse persekitaran, mesej **ralat Organisasi CDS ini telah dilampirkan pada contoh** Wawasan Pelanggan yang lain bermaksud bahawa persekitaran telah Dataverse digunakan dalam persekitaran Wawasan Pelanggan. Anda boleh mengalih keluar sambungan sedia ada sebagai pentadbir global pada Dataverse persekitaran. Ia boleh mengambil masa beberapa jam untuk mengisi perubahan.

1. Pergi ke [Power Apps](https://make.powerapps.com).
1. Pilih persekitaran daripada pemilih persekitaran.
1. Pergi ke **Penyelesaian**.
1. Nyahpasang atau padamkan penyelesaian **Dynamics 365 Customer Insights bernama Tambahan Kad Pelanggan (Pratonton)**.

ATAU

1. Buka persekitaran anda Dataverse.
1. Pergi ke **Penyelesaian** > **Tetapan** Lanjutan.
1. Nyahpasang **penyelesaian CustomerInsightsCustomerCard**.

Sekiranya penyingkiran sambungan gagal kerana kebergantungan, anda juga perlu mengeluarkan kebergantungan. Untuk maklumat lanjut, lihat [Mengalih keluar kebergantungan](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entiti output

Sesetengah entiti output daripada Wawasan Pelanggan tersedia sebagai jadual dalam Dataverse. Bahagian di bawah menerangkan skema yang dijangka bagi jadual ini.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Pengayaan](#enrichment)
- [Ramalan](#prediction)
- [Keahlian segmen](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Jadual ini mengandungi profil pelanggan yang disatukan daripada Customer Insights. Skema untuk profil pelanggan bersatu bergantung pada entiti dan atribut yang digunakan dalam proses penyatuan data. Skema profil pelanggan biasanya mengandungi subset atribut daripada [definisi Common Data Model bagi CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Untuk senario B-to-B, profil pelanggan mengandungi akaun bersatu, dan skema biasanya mengandungi subset atribut daripada [definisi Model Data Biasa Akaun](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

ContactProfile mengandungi maklumat bersatu tentang kenalan. Kenalan ialah [individu yang dipetakan pada akaun](data-unification-contacts.md) dalam senario B-to-B.

| Column                       | Taip                | Description     |
| ---------------------------- | ------------------- | --------------- |
|  Tarikh lahir            | TarikhMasa       |  Tarikh lahir kenalan               |
|  Bandar                 | Teks |  Bandar alamat hubungan               |
|  ContactId            | Teks |  ID profil kenalan               |
|  ContactProfileId     | Pengecam unik   |  GUID untuk kenalan               |
|  CountryOrRegion      | Teks |  Negara/Rantau alamat hubungan               |
|  CustomerId           | Teks |  ID akaun kenalan dipetakan kepada               |
|  EntityName           | Teks |  Entiti dari mana data berasal                |
|  FirstName            | Teks |  Nama pertama kenalan               |
|  Jantina               | Teks |  Jantina kenalan               |
|  ID                   | Teks |  GUID deterministik berdasarkan`Identifier`               |
|  Pengecam           | Teks |  ID dalaman profil kenalan: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Teks |  Tajuk kerja kenalan               |
|  LastName             | Teks |  Nama akhir kenalan               |
|  PostalCode           | Teks |  Poskod alamat hubungan               |
|  PrimaryEmail         | Teks |  Alamat e-mel kenalan               |
|  Telefon Utama         | Teks |  Nombor telefon kenalan               |
|  StateOrProvince      | Teks |  Negeri atau wilayah alamat hubungan               |
|  Alamat Jalan        | Teks |  Jalan alamat hubungan               |

### <a name="alternatekey"></a>AlternateKey

Jadual AlternateKey mengandungi kunci entiti, yang mengambil bahagian dalam proses penyatuan.

|Column  |Taip  |Description  |
|---------|---------|---------|
|DataSourceName    |Teks         | Nama sumber data. Contohnya: `datasource5`        |
|EntityName        | Teks        | Nama entiti dalam Wawasan Pelanggan. Contohnya: `contact1`        |
|AlternateValue    |Teks         |ID alternatif yang dipetakan kepada ID pelanggan. Contoh: `cntid_1078`         |
|KeyRing           | Teks        | Nilai JSON  </br> Sampel: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Teks        | ID profil pelanggan yang disatukan.         |
|AlternateKeyId     | Pengecam unik        |  AlternateKey deterministic GUID berdasarkan`Identifier`      |
|Pengecam |   Teks      |   `DataSourceName|EntityName|AlternateValue`  </br> Sampel: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Jadual ini mengandungi aktiviti oleh pengguna yang tersedia dalam Customer Insights.

| Column            | Taip        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Teks      | ID profil pelanggan                                                                      |
| ActivityId        | Teks      | ID Dalaman aktiviti pelanggan (kunci utama)                                       |
| SourceEntityName  | Teks      | Nama entiti sumber                                                                |
| SourceActivityId  | Teks      | Kunci utama daripada entiti sumber                                                       |
| ActivityType      | Teks      | Jenis aktiviti semantik atau nama aktiviti tersuai                                        |
| ActivityTimeStamp | TarikhMasa    | Setem masa aktiviti                                                                      |
| Gelaran             | Teks      | Tajuk atau nama aktiviti                                                               |
| Description       | Teks      | Perihalan aktiviti                                                                     |
| URL               | Teks      | Pautan ke URL luaran yang khusus untuk aktiviti                                         |
| SemanticData      | Teks | Termasuk senarai pasangan nilai utama untuk medan pemetaan semantik yang khusus untuk jenis aktiviti |
| RangeIndex        | Teks      | Cap masa unix digunakan untuk menyusun garis masa aktiviti dan pertanyaan julat yang berkesan |
| UnifiedActivityId   | Pengecam unik | ID Dalaman aktiviti pelanggan (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Jadual ini mengandungi data output langkah berasaskan atribut pelanggan.

| Column             | Taip             | Description                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Teks           | ID profil pelanggan        |
| Langkah           | Teks      | Termasuk senarai pasangan nilai utama untuk nama dan nilai ukuran bagi pelanggan yang ditetapkan |
| Pengecam | Teks           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Pengecam unik     | ID profil pelanggan |

### <a name="enrichment"></a>Pengayaan

Jadual ini mengandungi output proses pengayaan.

| Column               | Taip             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Teks           | ID profil pelanggan                                 |
| EnrichmentProvider   | Teks           | Nama pembekal untuk pengayaan                                  |
| EnrichmentType       | Teks           | Jenis pengayaan                                      |
| Nilai               | Teks      | Senarai atribut yang dihasilkan oleh proses pengayaan |
| EnrichmentId | Pengecam unik            | GUID deterministik dijana daripada`Identifier` |
| Pengecam   | Teks           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Ramalan

Jadual ini mengandungi output ramalan model.

| Column               | Taip        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Teks      | ID profil pelanggan                                  |
| ModelProvider        | Teks      | Nama pembekal model                                      |
| Model                | Teks      | Nama model                                                |
| Nilai               | Teks | Senarai atribut yang dihasilkan oleh model |
| RamalanId | Pengecam unik       | GUID deterministik dijana daripada`Identifier` |
| Pengecam   | Teks      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Keahlian segmen

Jadual ini mengandungi maklumat keahlian segmen profil pelanggan.

| Column        | Taip | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Teks       | ID Profil Pelanggan        |
| SegmentProvider      | Teks       | Aplikasi yang menerbitkan segmen.      |
| SegmentMembershipType | Teks       | Jenis pelanggan untuk rekod keahlian segmen ini. Menyokong pelbagai jenis seperti Pelanggan, Hubungan atau Akaun. Lalai: Pelanggan  |
| Segmen       | Teks  | Senarai segmen unik profil pelanggan adalah ahli      |
| Pengecam  | Teks   | Pengecam unik rekod keahlian segmen. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Pengecam unik      | GUID deterministik dijana daripada`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
