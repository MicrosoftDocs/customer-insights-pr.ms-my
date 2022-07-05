---
title: Bawa Azure key vault anda sendiri (pratonton)
description: Ketahui cara mengkonfigurasi Wawasan Pelanggan untuk menggunakan peti besi kunci Azure anda sendiri untuk menguruskan rahsia.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 8fdb131de35c7d936d2921265f03faa5682db6f6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082643"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Bawa Azure key vault anda sendiri (pratonton)

Memautkan peti besi [kunci Azure khusus](/azure/key-vault/general/basic-concepts) ke persekitaran Wawasan Pelanggan membantu organisasi memenuhi keperluan pematuhan.
Key vault yang ditetapkan boleh digunakan untuk peringkat dan menggunakan rahsia dalam sempadan pematuhan organisasi. Wawasan Pelanggan boleh menggunakan rahsia dalam Azure Key Vault untuk [menyediakan sambungan](connections.md) ke sistem pihak ketiga.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Pautkan peti besi utama ke persekitaran Wawasan Pelanggan

### <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi ruang simpan utama dalam Wawasan Pelanggan, prasyarat berikut mesti dipenuhi:

- Anda mempunyai langganan Azure aktif.

- Anda mempunyai [peranan Pentadbir](permissions.md#admin) dalam Wawasan Pelanggan. Ketahui lebih lanjut tentang [keizinan pengguna dalam Wawasan](permissions.md#assign-roles-and-permissions) Pelanggan.

- Anda mempunyai [Penyumbang](/azure/role-based-access-control/built-in-roles#contributor) dan peranan [Pentadbir Akses Pengguna](/azure/role-based-access-control/built-in-roles#user-access-administrator) pada key vault atau kumpulan sumber pemilik key vault. Untuk mendapatkan maklumat lanjut, pergi ke [Tambah atau alih keluar tugasan peranan Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal). Jika anda tidak mempunyai peranan Pentadbir Akses Pengguna pada key vault, anda mesti menyediakan keizinan kawalan akses berdasarkan peranan untuk prinsipal perkhidmatan Azure untuk Dynamics 365 Customer Insights secara berasingan. Ikuti langkah untuk [menggunakan prinsipal perkhidmatan Azure](connect-service-principal.md) untuk key vault yang sepatutnya dipautkan.

- Key vault mesti mempunyai tembok api Key Vault **dinyahdayakan**.

- Ruang simpan utama berada dalam lokasi [Azure yang sama](https://azure.microsoft.com/global-infrastructure/geographies/#overview) dengan persekitaran Wawasan Pelanggan. Kawasan persekitaran dalam Wawasan Pelanggan disenaraikan di bawah **Sistem** > **Pentadbir** > **Perihal** > **Wilayah**.

### <a name="link-a-key-vault-to-the-environment"></a>Pautkan key vault ke persekitaran

1. Pergi ke **Keselamatan** > **Pentadbir**, kemudian pilih **tab Peti Besi** Kunci.
1. Pada jubin **Key Vault**, pilih **Sediakan**.
1. Pilih **Langganan**.
1. Pilih key vault daripada senarai juntai bawah **Key Vault**. Jika terlalu banyak key vaults ditunjukkan, pilih kumpulan sumber untuk mengehadkan hasil carian.
1. Terima pernyataan **Privasi dan pematuhan data**.
1. Pilih **Simpan**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Langkah-langkah untuk menyediakan peti besi kunci terpaut dalam Wawasan Pelanggan.":::

Jubin **Key Vault** kini menunjukkan nama key vault yang dipautkan, kumpulan sumber dan langganan. Ia bersedia untuk digunakan dalam persediaan sambungan.
Untuk butiran tentang keizinan pada peti besi utama yang diberikan kepada Wawasan Pelanggan, pergi ke [Kebenaran yang diberikan pada peti besi](#permissions-granted-on-the-key-vault) utama, kemudian dalam artikel ini.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Gunakan key vault dalam persediaan sambungan

Apabila [menyediakan sambungan](connections.md) kepada sistem pihak ketiga, rahsia daripada Key Vault yang dipautkan boleh digunakan untuk mengkonfigurasikan sambungan.

1. Pergi ke **Pentadbir** > **Sambungan**.
1. Pilih **Tambah sambungan**.
1. Untuk jenis sambungan yang disokong, togol **Gunakan Key Vault** tersedia jika anda telah memautkan key vault.
1. Daripada memasukkan rahsia secara manual, anda boleh memilih nama rahsia yang menunjuk ke nilai rahsia dalam key vault.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Anak tetingkap sambungan dengan sambungan SFTP yang menggunakan rahsia Key Vault.":::

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

## <a name="permissions-granted-on-the-key-vault"></a>Kebenaran yang diberikan pada peti besi utama

Keizinan berikut diberikan kepada Wawasan Pelanggan pada peti besi kunci terpaut jika sama ada [dasar](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) akses Key Vault atau [kawalan](/azure/key-vault/general/rbac-guide?tabs=azure-cli) akses berasaskan peranan Azure didayakan.

### <a name="key-vault-access-policy"></a>Dasar akses Key Vault

| Jenis        | Keizinan          |
| ----------- | -------------------- |
| Kekunci         | [Dapatkan Kekunci](/rest/api/keyvault/keys/get-keys/get-keys), [Dapatkan kekunci](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Rahsia      | [Dapatkan Rahsia](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Dapatkan Rahsia](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Sijil | [Dapatkan Sijil](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Dapatkan Sijil](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Nilai sebelumnya ialah minimum untuk disenaraikan dan dibaca semasa pelaksanaan.

### <a name="azure-role-based-access-control"></a>Kawalan akses berdasarkan peranan Azure

Peranan Pengguna Pembaca Peti Besi Kunci dan Rahsia Peti Besi Kunci akan ditambah untuk Wawasan Pelanggan. Untuk butiran tentang peranan ini, pergi ke [Peranan Azure terbina untuk operasi satah data Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Pengesyoran

- Gunakan peti besi kunci berasingan atau khusus yang hanya mengandungi rahsia yang diperlukan untuk Wawasan Pelanggan. Baca lebih lanjut tentang mengapa [key vaults berasingan disyorkan](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Ikuti [amalan terbaik untuk menggunakan Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) untuk akses kawalan, sandaran, audit dan pilihan pemulihan.

## <a name="frequently-asked-questions"></a>Soalan lazim

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Bolehkah Wawasan Pelanggan menulis rahsia atau menulis ganti rahsia ke dalam peti besi utama?

Tidak. Hanya keizinan baca dan senarai yang digariskan dalam seksyen keizinan [yang](#permissions-granted-on-the-key-vault) diberikan sebelum ini dalam artikel ini diberikan kepada Wawasan Pelanggan. Sistem tidak boleh menambah, memadam atau menulis ganti rahsia dalam key vault. Ini juga sebab mengapa anda tidak boleh memasukkan kelayakan apabila sambungan menggunakan Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Bolehkah saya menukar sambungan daripada menggunakan rahsia Key Vault untuk pengesahan lalai?

Tidak. Anda tidak boleh mengubah kembali ke sambungan lalai selepas anda mengkonfigurasi dengan menggunakan rahsia daripada key vault yang dipautkan. Cipta sambungan berasingan dan padamkan yang lama jika anda tidak memerlukannya lagi.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Bagaimanakah saya boleh membatalkan akses kepada peti besi kunci untuk Wawasan Pelanggan?

Bergantung pada sama ada [dasar akses Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) atau [kawalan akses berdasarkan peranan Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) didayakan, anda perlu mengalih keluar keizinan untuk prinsipal perkhidmatan `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` dengan nama tersebut `Dynamics 365 AI for Customer Insights`. Semua sambungan yang menggunakan key vault akan berhenti berfungsi.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Satu rahsia yang digunakan dalam sambungan telah dialih keluar dari key vault. Apakah yang saya boleh lakukan?

Pemberitahuan muncul dalam Wawasan Pelanggan apabila rahsia yang dikonfigurasikan daripada peti besi kunci tidak boleh dicapai lagi. Dayakan [padam lembut](/azure/key-vault/general/soft-delete-overview) pada key vault untuk memulihkan rahsia jika ia dialih keluar secara tidak sengaja.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Sambungan tidak berfungsi, tetapi rahsia saya berada dalam key vault. Apa yang mungkin menjadi punca?

Pemberitahuan muncul dalam Wawasan Pelanggan apabila ia tidak dapat mengakses peti besi kunci. Mungkin sebabnya:

- Keizinan untuk prinsipal perkhidmatan Wawasan Pelanggan telah dialih keluar. Mereka perlu dipulihkan secara manual.

- Tembok api pada key vault didayakan. Firewall mesti dinyahdayakan untuk menjadikan ruang simpan kunci boleh dicapai untuk Wawasan Pelanggan sekali lagi.
