---
title: Urus peraturan persetujuan lalai pada segmen
description: Dengan keupayaan pengurusan persetujuan, anda boleh menyahdayakan atau mengubah peraturan persetujuan lalai jika penggantian didayakan.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755227"
---
# <a name="disable-or-change-default-consent-rules"></a>Menyahdayakan atau mengubah peraturan persetujuan lalai

Jika organisasi anda menggunakan [keupayaan](consent-management/overview.md) pengurusan persetujuan dengan Dynamics 365 Customer Insights, [pentadbir boleh menguatkuasakan peraturan](activate-consent.md) persetujuan untuk segmen. 

Dengan peraturan persetujuan yang dikuatkuasakan di kawasan segmen, setiap segmen memberitahu tentang keadaan pemeriksaan dan peraturan persetujuan. Jika penggantian dibenarkan, peraturan persetujuan lalai dimatikan untuk segmen tertentu. Setiap pencipta segmen boleh menambah lebih banyak peraturan persetujuan di atas peraturan lalai pada segmen. 

## <a name="for-administrators"></a>Untuk pentadbir

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Pembina segmen dengan pilihan peraturan persetujuan.":::

**Untuk menyahaktifkan peraturan persetujuan lalai:**

1. **Dalam pemberitahuan Peraturan** Persetujuan, pilih **Lihat butiran**. 

1. **Tetapkan togol peraturan** persetujuan Lalai kepada **Mati**.

**Untuk menambah lebih banyak peraturan persetujuan:**

1. **Dalam pemberitahuan Peraturan** Persetujuan, pilih **Lihat butiran**. 

1. Pilih **Tambah peraturan** persetujuan dan pilih peraturan persetujuan daripada **juntai bawah Pilih jenis** data persetujuan.

1. Pilih **Simpan** untuk menggunakan peraturan baru pada segmen.

## <a name="for-contributors"></a>Bagi penyumbang

Untuk mencipta segmen tanpa peraturan persetujuan yang dikuatkuasakan, anda perlu bekerjasama dengan pentadbir anda untuk menyahdayakannya pada segmen anda. Walau bagaimanapun, anda boleh menambah peraturan persetujuan anda sendiri pada segmen yang anda miliki dan uruskan.

Ini adalah proses tiga langkah: 
1. [Buat segmen](segments.md) dalam Wawasan Pelanggan dan simpannya. 

1. Kongsi nama segmen dengan pentadbir anda dan minta mereka [mendayakan penggantian untuk segmen](activate-consent.md) anda. 

1. Buka segmen anda sekali lagi. **Dalam pemberitahuan Peraturan** persetujuan, pilih **Lihat butiran** dan tambah peraturan persetujuan yang anda ingin gunakan. Kemudian, **Simpan** dan **Jalankan** segmen anda.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
