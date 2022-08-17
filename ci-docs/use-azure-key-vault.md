---
title: Bawa Azure key vault anda sendiri (pratonton)
description: Ketahui cara mengkonfigurasi Wawasan Pelanggan untuk menggunakan peti besi kunci Azure anda sendiri untuk menguruskan rahsia.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246166"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Bawa Azure key vault anda sendiri (pratonton)

Memautkan peti besi [kunci Azure khusus](/azure/key-vault/general/basic-concepts) ke persekitaran Wawasan Pelanggan membantu organisasi memenuhi keperluan pematuhan.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Pautkan peti besi utama ke persekitaran Wawasan Pelanggan

Sediakan peti besi kunci khusus untuk pentas dan gunakan rahsia dalam sempadan pematuhan organisasi.

### <a name="prerequisites"></a>Prasyarat

- Langganan Azure yang aktif.

- Peranan [Pentadbir](permissions.md#admin) [yang](permissions.md#add-users) ditugaskan dalam Wawasan Pelanggan.

- [Peranan Penyumbang](/azure/role-based-access-control/built-in-roles#contributor) dan [Pentadbir](/azure/role-based-access-control/built-in-roles#user-access-administrator) Akses Pengguna pada peti besi utama atau kumpulan sumber yang dimiliki oleh peti besi utama. Untuk mendapatkan maklumat lanjut, pergi ke [Tambah atau alih keluar tugasan peranan Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal). Jika anda tidak mempunyai peranan Pentadbir Capaian Pengguna pada peti besi kunci, sediakan keizinan kawalan capaian berasaskan peranan untuk prinsipal perkhidmatan Azure secara Dynamics 365 Customer Insights berasingan. Ikuti langkah untuk [menggunakan prinsipal perkhidmatan Azure](connect-service-principal.md) untuk key vault yang sepatutnya dipautkan.

- Peti besi kunci mesti mempunyai firewall Key Vault **dilumpuhkan**.

- Peti besi kunci berada di lokasi [Azure yang sama](https://azure.microsoft.com/global-infrastructure/geographies/#overview) dengan persekitaran Wawasan Pelanggan. Dalam Wawasan Pelanggan, pergi ke **Sistem** > **Pentadbir** dan **tab Perihal** untuk melihat rantau persekitaran.

### <a name="recommendations"></a>Pengesyoran

- [Gunakan peti besi](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) kunci berasingan atau khusus yang hanya mengandungi rahsia yang diperlukan untuk Wawasan Pelanggan.

- Ikuti [amalan terbaik untuk menggunakan Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) untuk akses kawalan, sandaran, audit dan pilihan pemulihan.

### <a name="link-a-key-vault-to-the-environment"></a>Pautkan key vault ke persekitaran

1. Pergi ke **Keselamatan** > **Pentadbir**, kemudian pilih tab **Peti Besi** Kekunci.
1. Pada jubin **Key Vault**, pilih **Sediakan**.
1. Pilih **Langganan**.
1. Pilih key vault daripada senarai juntai bawah **Key Vault**. Jika terlalu banyak peti besi utama tersedia, pilih kumpulan sumber untuk mengehadkan hasil carian.
1. Semak [Privasi data dan pematuhan](connections.md#data-privacy-and-compliance) dan pilih **Saya bersetuju**.
1. Pilih **Simpan**.

Jubin **Key Vault** menunjukkan nama peti besi kunci terpaut, langganan dan kumpulan sumber. Ia bersedia untuk digunakan dalam persediaan sambungan.
Untuk butiran tentang keizinan pada peti besi kunci yang diberikan kepada Wawasan Pelanggan, pergi ke [Keizinan yang diberikan pada peti besi](#permissions-granted-on-the-key-vault) kunci.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Gunakan key vault dalam persediaan sambungan

Apabila [menyediakan sambungan](connections.md) ke [sistem pihak](#supported-connection-types) ketiga yang disokong, gunakan rahsia dari Key Vault yang dipautkan untuk mengkonfigurasi sambungan.

1. Pergi ke **Pentadbir** > **Sambungan**.
1. Pilih **Tambah sambungan**.
1. Untuk jenis sambungan yang disokong, togol **Gunakan Key Vault** tersedia jika anda telah memautkan key vault.
1. Daripada memasukkan rahsia secara manual, pilih nama rahsia yang menunjuk kepada nilai rahsia dalam peti besi utama.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Anak tetingkap sambungan dengan sambungan SFTP yang menggunakan rahsia Key Vault.":::

1. Pilih **Simpan** untuk mencipta sambungan.

## <a name="supported-connection-types"></a>Jenis sambungan yang disokong

Sambungan [eksport](export-destinations.md) berikut adalah disokong:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Kebenaran yang diberikan pada peti besi kunci

Keizinan berikut diberikan kepada Wawasan Pelanggan pada peti besi kunci terpaut jika sama ada [dasar](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) akses Key Vault atau [kawalan](/azure/key-vault/general/rbac-guide?tabs=azure-cli) akses berasaskan peranan Azure didayakan.

### <a name="key-vault-access-policy"></a>Dasar akses Key Vault

| Jenis        | Keizinan          |
| ----------- | -------------------- |
| Kekunci         | [Dapatkan Kekunci](/rest/api/keyvault/keys/get-keys/get-keys), [Dapatkan kekunci](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Rahsia      | [Dapatkan Rahsia](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Dapatkan Rahsia](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Sijil | [Dapatkan Sijil](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Dapatkan Sijil](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Nilai sebelumnya ialah minimum untuk disenaraikan dan dibaca semasa pelaksanaan.

### <a name="azure-role-based-access-control"></a>Kawalan akses berdasarkan peranan Azure

Peranan [Pengguna](/azure/key-vault/general/rbac-guide?tabs=azure-cli) Pembaca Vault Kunci dan Rahsia Vault Utama akan ditambah untuk Wawasan Pelanggan.

## <a name="frequently-asked-questions"></a>Soalan lazim

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Bolehkah Wawasan Pelanggan menulis rahsia atau menulis ganti rahsia ke dalam peti besi utama?

Tidak. Hanya keizinan baca dan senarai yang digariskan dalam [keizinan yang](#permissions-granted-on-the-key-vault) diberikan diberikan kepada Wawasan Pelanggan. Sistem tidak boleh menambah, memadam atau menulis ganti rahsia dalam key vault. Ini juga sebab mengapa anda tidak boleh memasukkan kelayakan apabila sambungan menggunakan Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Bolehkah saya menukar sambungan daripada menggunakan rahsia Key Vault untuk pengesahan lalai?

Tidak. Anda tidak boleh mengubah kembali ke sambungan lalai selepas anda mengkonfigurasi dengan menggunakan rahsia daripada key vault yang dipautkan. Cipta sambungan berasingan dan padamkan yang lama jika anda tidak memerlukannya lagi.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Bagaimanakah saya boleh membatalkan akses kepada peti besi utama untuk Wawasan Pelanggan?

[Jika dasar](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) akses Key Vault atau [kawalan](/azure/key-vault/general/rbac-guide?tabs=azure-cli) akses berasaskan peranan Azure didayakan, alih keluar keizinan untuk prinsipal `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` perkhidmatan dengan nama `Dynamics 365 AI for Customer Insights`. Semua sambungan yang menggunakan key vault akan berhenti berfungsi.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Satu rahsia yang digunakan dalam sambungan telah dialih keluar dari key vault. Apakah yang saya boleh lakukan?

Pemberitahuan muncul dalam Wawasan Pelanggan apabila rahsia yang dikonfigurasi daripada peti besi kunci tidak dapat diakses lagi. Dayakan [padam lembut](/azure/key-vault/general/soft-delete-overview) pada key vault untuk memulihkan rahsia jika ia dialih keluar secara tidak sengaja.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Sambungan tidak berfungsi, tetapi rahsia saya berada dalam key vault. Apa yang mungkin menjadi punca?

Pemberitahuan muncul dalam Wawasan Pelanggan apabila ia tidak dapat mengakses peti besi kunci. Mungkin sebabnya:

- Keizinan untuk prinsipal perkhidmatan Wawasan Pelanggan telah dialih keluar. Mereka perlu dipulihkan secara manual.

- Tembok api pada key vault didayakan. Tembok api mesti dinyahdayakan untuk menjadikan peti besi kunci boleh dicapai untuk Wawasan Pelanggan sekali lagi.
