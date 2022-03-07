---
title: Segmen berdasarkan output ramalan
description: Cipta segmen berdasarkan entiti output untuk model ramalan.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741440"
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

1. Pilih elipsis menegak bersebelahan dengan model yang anda mahu semak dan pilih **Lihat**.

1. Pada halaman hasil, pilih **Cipta segmen**. Untuk maklumat lanjut mengenai halaman keputusan, kaji semula artikel mengenai model.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Tangkapan skrin halaman hasil ramalan dengan serlahan pada tindakan segmen Cipta.":::

1. Cipta segmen baharu berdasarkan pada entiti output untuk model terpilih. Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).