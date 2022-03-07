---
title: Sumber data pengayaan
description: Memperkayakan sumber data sebelum melalui proses penyatuan data.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: eebaaf18795e80dd1ba16a15a23844d685c94c6e
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373070"
---
# <a name="enrichment-for-data-sources-preview"></a>Pengayaan untuk sumber data (pratonton)

Gunakan data daripada sumber seperti Microsoft dan rakan kongsi lain untuk memperkayakan data pelanggan anda sebelum penyatuan data. Sumber data pengayaan membantu menghasilkan kesempurnaan dan kualiti data yang lebih tinggi yang dapat membantu mencapai hasil yang lebih baik sebaik sahaja anda menyatukan data anda. Sebagai contoh, menggunakan format yang dinormalisasi dan diseragamkan untuk alamat meningkatkan kualiti hasil padanan. Untuk senarai pengayaan yang disokong, lihat [pilihan pengayaan sumber data yang disokong](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Memperkayakan sumber data

Anda mesti mempunyai keizinan Penyumbang atau Pentadbir untuk mencipta atau mengedit pengayaan. Untuk maklumat lanjut, lihat [Keizinan](permissions.md).  

1. Pergi ke **DataUnify** > **·**. Pilih entiti yang anda mahu memperkayakan dan memilih satu atribut sebagai kunci utama untuk entiti. Untuk maklumat lanjut, lihat [Pilih kekunci utama](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Pergi **Data** > **Sumber data**.
 
1. Pilih elipsis menegak di sebelah sumber data yang anda ingin memperkayakan dan pilih **Enrich**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Halaman pengayaan sumber data.":::

   Tab **Discover** memaparkan pilihan [pengayaan sumber data yang](#supported-data-source-enrichments) disokong.

1. Pilih **Memperkayakan data** saya untuk mengkonfigurasi pengayaan sumber data. Nama entiti output diisi secara automatik.

## <a name="supported-data-source-enrichments"></a>Pengayaan sumber data yang disokong

Pengayaan berikut kini tersedia untuk sumber data. Semak langkah terperinci untuk pengayaan untuk mengetahui cara mengkonfigurasinya.

- [Alamat dipertingkatkan](enrichment-enhanced-addresses.md)
- [Data identiti dari LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Menguruskan pengayaan sumber data sedia ada

Pergi ke tab **Pengayaan Saya** untuk melihat semua pengayaan yang dikonfigurasikan.

Pilih pengayaan untuk melihat pilihan yang tersedia. Anda juga boleh memilih elipsis (...) pada item senarai untuk melihat pilihan. Jika anda mengkonfigurasi beberapa pengayaan, anda boleh menggunakan kotak carian untuk mencarinya dengan cepat.

Anda boleh melihat, mengedit, menjalankan atau memadam pengayaan sumber data. Untuk maklumat lanjut, lihat [Menguruskan pengayaan](enrichment-hub.md) sedia ada.
