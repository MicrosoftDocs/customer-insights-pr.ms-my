---
title: Bawa Azure key vault anda sendiri untuk menguruskan rahsia
description: Ketahui cara mengkonfigurasi Customer Insights untuk menggunakan Azure key vault anda sendiri.
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
ms.openlocfilehash: 418575f724090628da8bd01e2569a4cb9e646337
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376519"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Bawa Azure key vault anda sendiri (pratonton)

Memautkan yang ditetapkan [Azure key vault](/azure/key-vault/general/basic-concepts) kepada persekitaran cerapan khalayak membantu organisasi untuk memenuhi keperluan pematuhan.
Key vault yang ditetapkan boleh digunakan untuk peringkat dan menggunakan rahsia dalam sempadan pematuhan organisasi. Cerapan khalayak boleh menggunakan rahsia dalam Azure Key Vault untuk [menyediakan sambungan](connections.md) kepada sistem pihak ketiga.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Pautkan key vault untuk persekitaran cerapan khalayak

### <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi key vault dalam cerapan khalayak, prasyarat berikut mesti dipenuhi:

- Anda mempunyai langganan Azure aktif.

- Anda mempunyai peranan [Pentadbir](permissions.md#admin) dalam wawasan khalayak. Ketahui lebih lanjut tentang [keizinan pengguna dalam cerapan khalayak](permissions.md#assign-roles-and-permissions).

- Anda mempunyai [Penyumbang](/azure/role-based-access-control/built-in-roles#contributor) dan peranan [Pentadbir Akses Pengguna](/azure/role-based-access-control/built-in-roles#user-access-administrator) pada key vault atau kumpulan sumber pemilik key vault. Untuk mendapatkan maklumat lanjut, pergi ke [Tambah atau alih keluar tugasan peranan Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal). Jika anda tidak mempunyai peranan Pentadbir Akses Pengguna pada key vault, anda mesti menyediakan keizinan kawalan akses berdasarkan peranan untuk prinsipal perkhidmatan Azure untuk Dynamics 365 Customer Insights secara berasingan. Ikuti langkah untuk [menggunakan prinsipal perkhidmatan Azure](connect-service-principal.md) untuk key vault yang sepatutnya dipautkan.

- Key vault mesti mempunyai tembok api Key Vault **dinyahdayakan**.

- Key vault ialah sama dengan [Lokasi Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) sebagai persekitaran cerapan khalayak. Rantau persekitaran dalam cerapan khalayak disenaraikan di bawah **Pentadbir** > **Sistem** > **Tentang** > **Rantau**.

### <a name="link-a-key-vault-to-the-environment"></a>Pautkan key vault ke persekitaran

1. Pergi ke **Pentadbir** > **Sistem** dan kemudian pilih tab **Keselamatan**.
1. Pada jubin **Key Vault**, pilih **Sediakan**.
1. Pilih **Langganan**.
1. Pilih key vault daripada senarai juntai bawah **Key Vault**. Jika terlalu banyak key vaults ditunjukkan, pilih kumpulan sumber untuk mengehadkan hasil carian.
1. Terima pernyataan **Privasi dan pematuhan data**.
1. Pilih **Simpan**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Langkah untuk menyediakan key vault dalam cerapan khalayak.":::

Jubin **Key Vault** kini menunjukkan nama key vault yang dipautkan, kumpulan sumber dan langganan. Ia bersedia untuk digunakan dalam persediaan sambungan.
Untuk butiran tentang keizinan yang pada key vault diberikan kepada cerapan khalayak, pergi ke [Keizinan yang diberikan pada key vault untuk cerapan khalayak](#permissions-granted-on-the-key-vault-to-audience-insights), kemudian dalam artikel ini.

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Keizinan yang diberikan pada key vault untuk cerapan khalayak

Keizinan berikut diberikan pada cerapan khalayak pada key vault yang dipautkan jika sama ada [dasar akses Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) atau [kawalan akses berasaskan peranan Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) didayakan.

### <a name="key-vault-access-policy"></a>Dasar akses Key Vault

| Jenis        | Keizinan          |
| ----------- | -------------------- |
| Kekunci         | [Dapatkan Kekunci](/rest/api/keyvault/get-keys), [Dapatkan kekunci](/rest/api/keyvault/get-key)                                 |
| Rahsia      | [Dapatkan Rahsia](/rest/api/keyvault/get-secrets), [Dapatkan Rahsia](/rest/api/keyvault/get-secret)                     |
| Sijil | [Dapatkan Sijil](/rest/api/keyvault/get-certificates), [Dapatkan Sijil](/rest/api/keyvault/get-certificate) |

Nilai sebelumnya ialah minimum untuk disenaraikan dan dibaca semasa pelaksanaan.

### <a name="azure-role-based-access-control"></a>Kawalan akses berdasarkan peranan Azure

Pembaca Key Vault dan peranan Pengguna Rahsia Key Vault akan ditambah untuk cerapan khalayak. Untuk butiran tentang peranan ini, pergi ke [Peranan Azure terbina untuk operasi satah data Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Pengesyoran

- Gunakan key vault yang berasingan atau ditetapkan yang hanya mengandungi rahsia yang diperlukan untuk cerapan khalayak. Baca lebih lanjut tentang mengapa [key vaults berasingan disyorkan](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Ikuti [amalan terbaik untuk menggunakan Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) untuk akses kawalan, sandaran, audit dan pilihan pemulihan.

## <a name="frequently-asked-questions"></a>Soalan lazim

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Bolehkah cerapan khalayak menulis rahsia atau menulis ganti rahsia ke dalam key vault?

Tidak. Hanya keizinan baca dan senarai yang digariskan dalam bahagian [keizinan yang diberikan](#permissions-granted-on-the-key-vault-to-audience-insights) lebih awal dalam artikel ini diberikan kepada cerapan khalayak. Sistem tidak boleh menambah, memadam atau menulis ganti rahsia dalam key vault. Ini juga sebab mengapa anda tidak boleh memasukkan kelayakan apabila sambungan menggunakan Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Bolehkah saya menukar sambungan daripada menggunakan rahsia Key Vault untuk pengesahan lalai?

Tidak. Anda tidak boleh mengubah kembali ke sambungan lalai selepas anda mengkonfigurasi dengan menggunakan rahsia daripada key vault yang dipautkan. Cipta sambungan berasingan dan padamkan yang lama jika anda tidak memerlukannya lagi.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Bagaimanakah saya boleh membatalkan akses kepada key vault untuk cerapan khalayak?

Bergantung pada sama ada [dasar akses Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) atau [kawalan akses berdasarkan peranan Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) didayakan, anda perlu mengalih keluar keizinan untuk prinsipal perkhidmatan `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` dengan nama tersebut `Dynamics 365 AI for Customer Insights`. Semua sambungan yang menggunakan key vault akan berhenti berfungsi.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Satu rahsia yang digunakan dalam sambungan telah dialih keluar dari key vault. Apakah yang saya boleh lakukan?

Pemberitahuan muncul dalam cerapan khalayak apabila rahsia yang dikonfigurasikan dari key vault tidak dapat dicapai lagi. Dayakan [padam lembut](/azure/key-vault/general/soft-delete-overview) pada key vault untuk memulihkan rahsia jika ia dialih keluar secara tidak sengaja.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Sambungan tidak berfungsi, tetapi rahsia saya berada dalam key vault. Apa yang mungkin menjadi punca?

Pemberitahuan muncul dalam cerapan khalayak apabila ia tidak boleh mengakses key vault. Mungkin sebabnya:

- Keizinan untuk prinsipal perkhidmatan cerapan khalayak telah dialih keluar. Mereka perlu dipulihkan secara manual.

- Tembok api pada key vault didayakan. Tembok api mesti dinyahdayakan untuk menjadikan key vault boleh dicapai untuk cerapan khalayak semula.
