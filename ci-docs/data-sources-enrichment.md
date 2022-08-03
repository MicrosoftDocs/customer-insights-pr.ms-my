---
title: Pengayaan untuk sumber data (pratonton)
description: Memperkayakan sumber data sebelum melalui proses penyatuan data.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207194"
---
# <a name="enrichment-for-data-sources-preview"></a>Pengayaan untuk sumber data (pratonton)

Gunakan data daripada sumber seperti Microsoft dan rakan kongsi lain untuk memperkayakan data pelanggan anda sebelum penyatuan data. Pengayaan sumber data membantu menghasilkan kesempurnaan dan kualiti data yang lebih tinggi yang boleh membantu mencapai hasil yang lebih baik sebaik sahaja anda menyatukan data anda. Sebagai contoh, menggunakan format yang normal dan standard untuk alamat meningkatkan kualiti hasil padanan. Untuk senarai pengayaan yang disokong, lihat [opsyen pengayaan sumber data yang disokong](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Memperkayakan sumber data

Anda mesti mempunyai keizinan [Penyumbang atau Pentadbir](permissions.md) untuk mencipta atau mengedit pengayaan.  

1. Pergi ke **Data** > **Unify**. Pilih entiti yang anda ingin memperkayakan dan pilih satu atribut sebagai [kunci](map-entities.md#select-primary-key-and-semantic-type-for-attributes) utama untuk entiti.

1. Pergi **Data** > **Sumber data**.

1. Pilih elipsis menegak (&vellip;) di sebelah sumber data anda ingin memperkayakan dan pilih **Enrich**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Halaman sumber data dengan Enrich diserlahkan":::

   Tab **Discover** memaparkan [opsyen](#supported-data-source-enrichments) pengayaan sumber data yang disokong.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Halaman pengayaan sumber data.":::

1. Pilih **Memperkayakan data** saya untuk mengkonfigurasi pengayaan sumber data. Nama entiti output diisi secara automatik.

## <a name="supported-data-source-enrichments"></a>Pengayaan sumber data yang disokong

Pengayaan berikut kini tersedia untuk sumber data. Semak langkah-langkah terperinci untuk pengayaan untuk mengetahui cara mengkonfigurasinya.

- [Alamat dipertingkatkan](enrichment-enhanced-addresses.md)
- [Data syarikat dipertingkat](enrichment-enhanced-company-data.md)
- [Data identiti dari LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Menguruskan pengayaan sumber data sedia ada

Pergi ke **Data** > **Pengayaan**. **Pada tab Pengayaan saya**, lihat pengayaan yang dikonfigurasi, status mereka, bilangan pelanggan yang diperkaya dan kali terakhir data disegarkan semula. Anda boleh mengisih senarai pengayaan mengikut mana-mana lajur atau menggunakan kotak carian untuk mencari pengayaan yang anda ingin uruskan.

Pilih pengayaan untuk melihat pilihan yang tersedia. Anda juga boleh memilih elipsis menegak (&vellip;) pada item senarai untuk melihat pilihan.

Anda boleh melihat, mengedit, menjalankan atau memadam pengayaan sumber data. Untuk maklumat lanjut, lihat [Menguruskan pengayaan](enrichment-hub.md#manage-existing-enrichments) sedia ada.
