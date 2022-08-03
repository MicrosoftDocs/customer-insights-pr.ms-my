---
title: Gunakan data Customer Insights dalam Microsoft Dataverse
description: Ketahui cara menyambungkan Wawasan Pelanggan dan Microsoft Dataverse dan memahami entiti output yang dieksport ke Dataverse.
ms.date: 07/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 89ff629033230de3c6252b6a3a16816d9b3c1287
ms.sourcegitcommit: 85b198de71ff2916fee5500ed7c37c823c889bbb
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/15/2022
ms.locfileid: "9153415"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Gunakan data Customer Insights dalam Microsoft Dataverse

Wawasan Pelanggan menyediakan pilihan untuk menjadikan entiti output tersedia sebagai [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Integrasi ini membolehkan perkongsian data yang mudah dan pembangunan tersuai melalui pendekatan kod rendah / tanpa kod. Entiti [output](#output-entities) tersedia sebagai jadual dalam Dataverse persekitaran. Anda boleh menggunakan data untuk sebarang aplikasi lain berdasarkan Dataverse jadual. Jadual ini membolehkan senario seperti aliran kerja automatik melalui Power Automate atau membina aplikasi dengan Power Apps.

Menyambung ke persekitaran anda Dataverse juga membolehkan [anda menelan data daripada sumber data di premis menggunakan Power Platform aliran data dan get laluan](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Prasyarat

- Wawasan Pelanggan dan Dataverse persekitaran mesti dihoskan di rantau yang sama.
- Anda mesti mempunyai peranan pentadbir global dalam Dataverse persekitaran. Sahkan sama ada persekitaran ini [Dataverse dikaitkan dengan](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) kumpulan keselamatan tertentu dan pastikan anda ditambahkan pada kumpulan keselamatan tersebut.
- Tiada persekitaran Wawasan Pelanggan lain yang telah dikaitkan dengan persekitaran yang Dataverse anda ingin sambungkan. Ketahui cara mengalih [keluar sambungan sedia ada ke Dataverse persekitaran](#remove-an-existing-connection-to-a-dataverse-environment).
- Persekitaran Microsoft Dataverse hanya boleh menyambung ke satu akaun storan. Ia hanya terpakai jika anda mengkonfigurasi persekitaran untuk [menggunakan Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse kelayakan kapasiti storan

Langganan Wawasan Pelanggan memberi anda kapasiti tambahan untuk kapasiti [Dataverse storan sedia ada](/power-platform/admin/capacity-storage) organisasi anda. Kapasiti tambahan bergantung pada bilangan profil yang digunakan oleh langganan anda.

**Contoh:**

Dengan mengandaikan anda mendapat storan pangkalan data 15 GB dan storan fail 20 GB setiap 100,000 profil pelanggan. Jika langganan anda termasuk 300,000 profil pelanggan, jumlah kapasiti storan anda ialah storan pangkalan data 45 GB (3 x 15 GB) dan storan fail 60 GB (3 x 20 GB). Begitu juga, jika anda mempunyai langganan B2B dengan akaun 30K, jumlah kapasiti storan anda ialah storan pangkalan data 45 GB (3 x 15 GB), dan storan fail 60 GB (3 x 20 GB).

Kapasiti log tidak tambahan dan tetap untuk organisasi anda.

Untuk maklumat lanjut tentang kelayakan kapasiti terperinci, lihat [Panduan](https://go.microsoft.com/fwlink/?LinkId=866544) Pelesenan Dynamics 365.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Dataverse Menyambungkan persekitaran ke Wawasan Pelanggan

Langkah ini **Microsoft Dataverse** membolehkan anda menyambungkan Wawasan Pelanggan dengan persekitaran anda Dataverse sambil [mencipta persekitaran](create-environment.md) Wawasan Pelanggan.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="perkongsian data dengan Microsoft Dataverse auto didayakan untuk persekitaran baru bersih.":::

Pentadbir boleh mengkonfigurasi Wawasan Pelanggan untuk menyambungkan persekitaran sedia ada Dataverse. Dengan menyediakan URL kepada Dataverse persekitaran, ia menyambung ke persekitaran Wawasan Pelanggan baharu mereka. Selepas mewujudkan sambungan antara Wawasan Pelanggan dan Dataverse, jangan ubah nama organisasi untuk Dataverse persekitaran. Nama organisasi digunakan dalam Dataverse URL dan nama yang diubah memecahkan sambungan dengan Wawasan Pelanggan.

Jika anda tidak mahu menggunakan persekitaran sedia ada Dataverse, sistem mencipta persekitaran baharu untuk data Wawasan Pelanggan dalam penyewa anda. [Power Platform pentadbir boleh mengawal orang yang boleh mencipta persekitaran](/power-platform/admin/control-environment-creation). Apabila anda menyediakan persekitaran Wawasan Pelanggan baharu dan pentadbir telah menyahdayakan penciptaan Dataverse persekitaran untuk semua orang kecuali pentadbir, anda mungkin tidak dapat mencipta persekitaran baharu.

**Mendayakan perkongsian** data dengan memilih Dataverse kotak semak perkongsian data.

Jika anda menggunakan akaun Storan Tasik Data anda sendiri, anda juga memerlukan **pengecam Keizinan**. Untuk maklumat lanjut cara mendapatkan pengecam keizinan, semak semula seksyen berikut.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Mendayakan perkongsian data dengan Dataverse daripada anda sendiri Azure Data Lake Storage (Pratonton)

Mendayakan perkongsian data dengan Microsoft Dataverse masa persekitaran [anda menggunakan akaun Azure Data Lake Storage anda sendiri](own-data-lake-storage.md) memerlukan beberapa konfigurasi tambahan. Pengguna yang menyediakan persekitaran Wawasan Pelanggan mesti mempunyai sekurang-kurangnya **keizinan Pembaca** Data Blob Storan pada *bekas CustomerInsights* dalam Azure Data Lake Storage akaun.

1. Cipta dua kumpulan keselamatan pada langganan Azure anda - satu **kumpulan keselamatan Pembaca** dan satu **kumpulan keselamatan Penyumbang** dan tetapkan Microsoft Dataverse perkhidmatan sebagai pemilik untuk kedua-dua kumpulan keselamatan.
2. Urus Senarai Kawalan Akses (ACL) pada bekas CustomerInsights dalam akaun storan anda melalui kumpulan keselamatan ini. Microsoft Dataverse Tambahkan perkhidmatan dan sebarang Dataverse aplikasi perniagaan berasaskan seperti Dynamics 365 Marketing kepada **kumpulan keselamatan Pembaca** dengan **keizinan baca sahaja**. Tambah *hanya* aplikasi Wawasan Pelanggan kepada **kumpulan keselamatan Penyumbang** untuk memberikan kedua-dua **keizinan baca dan tulis** untuk menulis profil dan cerapan.

### <a name="limitations"></a>Batasan

Terdapat dua batasan apabila menggunakan Dataverse dengan akaun anda sendiri Azure Data Lake Storage:

- Ada pemetaan satu-ke-satu antara Dataverse organisasi dan rekening Azure Data Lake Storage. Dataverse Setelah organisasi disambungkan ke akaun storan, ia tidak dapat menyambung ke akaun storan lain. Had ini menghalang bahawa a Dataverse tidak mengisi berbilang akaun storan.
- Perkongsian data tidak akan berfungsi jika persediaan Azure Private Link diperlukan untuk mengakses akaun anda Azure Data Lake Storage kerana ia berada di belakang tembok api. Dataverse pada masa ini tidak menyokong sambungan ke titik akhir peribadi melalui Pautan Peribadi.

### <a name="set-up-powershell"></a>Sediakan PowerShell

Untuk melaksanakan skrip PowerShell, anda perlu menyediakan PowerShell dengan sewajarnya.

1. Pasang versi [Azure Active Directory terkini PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. Pada PC anda, pilih kekunci Windows pada papan kekunci anda dan cari untuk **Windows PowerShell** dan pilih **Jalankan sebagai pentadbir**.
   1. Dalam tetingkap PowerShell yang terbuka, masukkan `Install-Module AzureAD`.
2. Import tiga modul.
    1. Dalam tetingkap PowerShell, masukkan `Install-Module -Name Az.Accounts` dan ikuti langkah-langkah.
    1. Ulangi untuk `Install-Module -Name Az.Resources` dan `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Langkah konfigurasi

1. Muat turun dua skrip PowerShell yang perlu anda jalankan dari repo [GitHub jurutera](https://github.com/trin-msft/byol) kami.
    1. `CreateSecurityGroups.ps1`
       - Anda memerlukan *keizinan pentadbir* penyewa untuk menjalankan skrip PowerShell ini.
       - Skrip PowerShell ini mencipta dua kumpulan keselamatan pada langganan Azure anda. Satu untuk kumpulan Pembaca dan satu lagi untuk kumpulan Penyumbang dan akan menjadikan Microsoft Dataverse perkhidmatan sebagai pemilik untuk kedua-dua kumpulan keselamatan ini.
       - Laksanakan skrip PowerShell ini dalam Windows PowerShell dengan menyediakan ID langganan Azure yang mengandungi .Azure Data Lake Storage Buka skrip PowerShell dalam editor untuk menyemak maklumat tambahan dan logik yang dilaksanakan.
       - Simpan kedua-dua nilai ID kumpulan keselamatan yang dijana oleh skrip ini kerana kami akan menggunakannya dalam `ByolSetup.ps1` skrip.

        > [!NOTE]
        > Penciptaan kumpulan keselamatan boleh dilumpuhkan pada penyewa anda. Dalam kes itu, persediaan manual diperlukan dan pentadbir anda Azure AD perlu [mendayakan penciptaan kumpulan keselamatan](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Anda memerlukan *keizinan Pemilik* Data Blob Storan pada tahap akaun storan/bekas untuk menjalankan skrip ini atau skrip ini akan mencipta satu untuk anda. Tugasan peranan anda boleh dialih keluar secara manual selepas berjaya menjalankan skrip.
        - Skrip PowerShell ini menambah kawalan akses berasaskan peranan yang diperlukan untuk Microsoft Dataverse perkhidmatan dan sebarang Dataverse aplikasi perniagaan berasaskan peranan. Ia juga mengemas kini Senarai Kawalan Akses (ACL) pada bekas CustomerInsights untuk kumpulan keselamatan yang `CreateSecurityGroups.ps1` dicipta dengan skrip. Kumpulan Penyumbang akan mempunyai *keizinan rwx* dan kumpulan Pembaca akan mempunyai *keizinan r-x* sahaja.
        - Laksanakan skrip PowerShell ini dalam Windows PowerShell dengan menyediakan ID langganan Azure yang mengandungi nama akaun storan anda Azure Data Lake Storage, nama kumpulan sumber dan nilai ID kumpulan keselamatan Pembaca dan Penyumbang. Buka skrip PowerShell dalam editor untuk menyemak maklumat tambahan dan logik yang dilaksanakan.
        - Salin rentetan output selepas berjaya menjalankan skrip. Rentetan output kelihatan seperti ini: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Masukkan rentetan output yang disalin dari atas ke dalam **medan Pengecam** keizinan langkah konfigurasi persekitaran untuk Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Pilihan konfigurasi untuk membolehkan perkongsian data daripada anda sendiri Azure Data Lake Storage dengan Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Mengalih keluar sambungan sedia ada ke Dataverse persekitaran

Apabila menyambung ke Dataverse persekitaran, mesej **ralat Organisasi CDS ini telah dilampirkan pada contoh** Wawasan Pelanggan yang Dataverse lain bermakna persekitaran telah digunakan dalam persekitaran Wawasan Pelanggan. Anda boleh mengalih keluar sambungan sedia ada sebagai pentadbir global pada Dataverse persekitaran. Ia boleh mengambil masa beberapa jam untuk mengisi perubahan.

1. Pergi ke [Power Apps](https://make.powerapps.com).
1. Pilih persekitaran daripada pemilih persekitaran.
1. Pergi ke **Penyelesaian**
1. Nyahpasang atau padamkan penyelesaian bernama **Dynamics 365 Customer Insights Tambahan Kad Pelanggan (Pratonton)**.

ATAU

1. Buka persekitaran anda Dataverse.
1. Pergi ke **Penyelesaian** > **Seting** Lanjutan.
1. **Nyahpasang penyelesaian CustomerInsightsCustomerCard**.

Sekiranya penyingkiran sambungan gagal kerana kebergantungan, anda juga perlu mengeluarkan kebergantungan. Untuk maklumat lanjut, lihat [Mengalih keluar kebergantungan](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entiti output

Sesetengah entiti output daripada Wawasan Pelanggan tersedia sebagai jadual dalam Dataverse. Bahagian di bawah menerangkan skema yang dijangka bagi jadual ini.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Pengayaan](#enrichment)
- [Ramalan](#prediction)
- [Keahlian segmen](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Jadual ini mengandungi profil pelanggan yang disatukan daripada Customer Insights. Skema untuk profil pelanggan bersatu bergantung kepada entiti dan atribut yang digunakan dalam proses penyatuan data. Skema profil pelanggan biasanya mengandungi subset atribut daripada [definisi Common Data Model bagi CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Jadual AlternateKey mengandungi kunci entiti, yang mengambil bahagian dalam proses penyatuan.

|Column  |Jenis  |Penerangan  |
|---------|---------|---------|
|DataSourceName    |Jalur         | Nama sumber data. Contohnya: `datasource5`        |
|EntityName        | String        | Nama entiti dalam Wawasan Pelanggan. Contohnya: `contact1`        |
|AlternateValue    |String         |ID alternatif yang dipetakan kepada ID pelanggan. Contoh: `cntid_1078`         |
|KeyRing           | Teks berbilang baris        | Nilai JSON  </br> Sampel: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Jalur        | ID profil pelanggan yang disatukan.         |
|AlternateKeyId     | GUID         |  GUID berketentuan AlternateKey berdasarkan msdynci_identifier       |
|msdynci_identifier |   Jalur      |   `DataSourceName|EntityName|AlternateValue`  </br> Sampel: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Jadual ini mengandungi aktiviti oleh pengguna yang tersedia dalam Customer Insights.

| Column            | Jenis        | Penerangan                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Jalur      | ID Profil Pelanggan                                                                      |
| ActivityId        | Jalur      | ID Dalaman aktiviti pelanggan (kunci utama)                                       |
| SourceEntityName  | Jalur      | Nama entiti sumber                                                                |
| SourceActivityId  | Jalur      | Kunci utama daripada entiti sumber                                                       |
| ActivityType      | Jalur      | Jenis aktiviti semantik atau nama aktiviti tersuai                                        |
| ActivityTimeStamp | DATETIME    | Cap Masa aktiviti                                                                      |
| Gelaran             | Jalur      | Tajuk atau nama aktiviti                                                               |
| Penerangan       | Jalur      | Perihalan aktiviti                                                                     |
| URL               | Jalur      | Pautan ke URL luaran yang khusus untuk aktiviti                                         |
| SemanticData      | Rentetan JSON | Termasuk senarai pasangan nilai utama untuk medan pemetaan semantik yang khusus untuk jenis aktiviti |
| RangeIndex        | Jalur      | Cap masa unix digunakan untuk menyusun garis masa aktiviti dan pertanyaan julat yang berkesan |
| mydynci_unifiedactivityid   | GUID | ID Dalaman aktiviti pelanggan (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Jadual ini mengandungi data output langkah berasaskan atribut pelanggan.

| Column             | Jenis             | Penerangan                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Jalur           | ID profil pelanggan        |
| Ukuran           | Rentetan JSON      | Termasuk senarai pasangan nilai utama untuk nama dan nilai ukuran bagi pelanggan yang ditetapkan | 
| msdynci_identifier | Jalur           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID profil pelanggan |


### <a name="enrichment"></a>Pengayaan

Jadual ini mengandungi output proses pengayaan.

| Column               | Jenis             |  Penerangan                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Jalur           | ID profil pelanggan                                 |
| EnrichmentProvider   | Jalur           | Nama pembekal untuk pengayaan                                  |
| EnrichmentType       | Jalur           | Jenis pengayaan                                      |
| Nilai               | Rentetan JSON      | Senarai atribut yang dihasilkan oleh proses pengayaan |
| msdynci_enrichmentid | GUID             | GUID berketentuan yang dijana daripada msdynci_identifier |
| msdynci_identifier   | Jalur           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Ramalan

Jadual ini mengandungi output ramalan model.

| Column               | Jenis        | Penerangan                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Jalur      | ID Profil Pelanggan                                  |
| ModelProvider        | Jalur      | Nama pembekal model                                      |
| Model                | Jalur      | Nama model                                                |
| Nilai               | Rentetan JSON | Senarai atribut yang dihasilkan oleh model |
| msdynci_predictionid | GUID        | GUID berketentuan yang dijana daripada msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Keahlian segmen

Jadual ini mengandungi maklumat keahlian segmen profil pelanggan.

| Column        | Taip | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID Profil Pelanggan        |
| SegmentProvider      | String       | Apl yang menerbitkan segmen.      |
| SegmentMembershipType | String       | Jenis pelanggan rekod keahlian segmen ini. Menyokong pelbagai jenis seperti Pelanggan, Kenalan atau Akaun. Lalai: Pelanggan  |
| Segmen       | Rentetan JSON  | Senarai segmen unik profil pelanggan adalah ahli      |
| msdynci_identifier  | String   | Pengenalpasti unik rekod keahlian segmen. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID penentu dijana daripada`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
