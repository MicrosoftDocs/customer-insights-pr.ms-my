---
title: Gambaran keseluruhan tentang senario ramalan yang disokong
description: Senario dan pilihan ramalan dilindungi oleh aplikasi Dynamics 365 Customer Insights.
ms.date: 09/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: be452e4f1515f637f6edbc3ae3aaf6a3d3471489
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618854"
---
# <a name="predictions-overview"></a>Gambaran keseluruhan ramalan

Dynamics 365 Customer Insights dilengkapi dengan pelbagai pilihan yang memanfaatkan AI dan pembelajaran mesin untuk meramalkan data. 

## <a name="out-of-box-models"></a>Model luar kotak

Cara paling mudah untuk bermula dengan meramalkan data adalah model yang ditakrif lebih awal, sering dirujuk sebagai model luar kotak. Mereka hanya memerlukan data dan struktur tertentu untuk menjana cerapan dengan cepat. Pada masa ini, model berikut tersedia: 

# <a name="individual-customers-b2c"></a>[Pelanggan individu (B2C)](#tab/b2c)

- [Nilai sepanjang hayat pelanggan](predict-customer-lifetime-value.md): Meramalkan potensi hasil pelanggan dalam keseluruhan interaksi dengan perniagaan.
- [Pengesyoran produk](predict-product-recommendation.md): Mencadangkan set pengesyoran produk ramalan berdasarkan tingkah laku pembelian dan pelanggan dengan corak pembelian yang sama.
- [Pulangan langganan](predict-subscription-churn.md): Meramalkan sama ada pelanggan berisiko untuk tidak menggunakan lagi produk atau perkhidmatan langganan syarikat anda.
- [Pulangan transaksi](predict-transactional-churn.md): Meramalkan jika pelanggan tidak lagi membeli produk atau perkhidmatan anda dalam tempoh masa tertentu.

# <a name="business-accounts-b2b"></a>[Akaun perniagaan (B2B)](#tab/b2b)

- [Pulangan transaksi](predict-transactional-churn.md): Meramalkan jika pelanggan tidak lagi membeli produk atau perkhidmatan anda dalam tempoh masa tertentu.

---


## <a name="azure-machine-learning-integration"></a>Penyepaduan Pembelajaran Mesin Azure

Jika sesebuah organisasi sudah menggunakan senario pembelajaran mesin berdasarkan eksperimen Pembelajaran Mesin Azure, ciri model tersuai dalam Customer Insights membantu untuk menyambungkan titik. Cipta aliran kerja yang membantu anda memilih data yang ingin anda janakan cerapan dan petakan hasil kepada profil pelanggan anda yang disatukan. Untuk mendapatkan maklumat lanjut, lihat [Model pembelajaran mesin tersuai](custom-models.md).

## <a name="ai-builder-prediction"></a>Ramalan AI Builder

Kadang-kadang, set data tidak lengkap dan beberapa nilai tidak diisi. Customer Insights boleh membantu untuk meramalkan nilai yang tidak diisi untuk entiti dan segmen Pelanggan. Untuk mendapatkan maklumat lanjut, lihat [Lengkapkan data separa anda dengan ramalan](predictions.md).
