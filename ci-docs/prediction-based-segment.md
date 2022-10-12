---
title: Mencipta segmen berdasarkan model ramalan
description: Cipta segmen berdasarkan entiti output untuk model ramalan.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610431"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Cipta segmen berdasarkan model ramalan (pratonton)

Keputusan ramalan kadang kala hanya diguna pakai pada subset pelanggan anda. Tingkatkan pemperibadian pengesyoran dengan mencipta segmen daripada hasil model ramalan. Sebagai contoh, anda mungkin mahu memberikan pengesyoran khusus kepada pelanggan yang lebih suka jenis perkhidmatan tertentu.

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.

- Pengesyoran produk, pulangan transaksi, pulangan langganan atau model nilai sepanjang hayat pelanggan dikonfigurasikan dalam Customer Insights. Semak keperluan untuk menyediakan model yang berbeza:

  - [Model pengesyoran produk](predict-product-recommendation.md)
  - [Model pulangan langganan](predict-subscription-churn.md)
  - [Model pulangan transaksi](predict-transactional-churn.md)
  - [Model nilai sepanjang hayat pelanggan](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Cipta segmen pelanggan berdasarkan ramalan

1. Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.

1. Pilih model yang anda ingin semak semula dan pilih **Lihat**.

1. Pada halaman hasil, pilih **Cipta segmen**. Untuk maklumat lanjut mengenai halaman keputusan, kaji semula artikel mengenai model.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Tangkapan skrin halaman hasil ramalan dengan serlahan pada tindakan segmen Cipta.":::

1. Buat segmen baharu menggunakan atribut daripada entiti output model yang dipilih. Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).

> [!TIP]
> Anda juga boleh mencipta segmen untuk model ramalan daripada **halaman Segmen** dengan **memilih Baharu** dan memilih **Cipta daripada** > **Kecerdasan**. Untuk maklumat lanjut, lihat [Mencipta segmen baharu dengan segmen](segment-quick.md) pantas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
