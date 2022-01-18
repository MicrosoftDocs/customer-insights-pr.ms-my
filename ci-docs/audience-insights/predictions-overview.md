---
title: Gambaran keseluruhan tentang senario ramalan yang disokong
description: Senario dan pilihan ramalan dilindungi oleh aplikasi Dynamics 365 Customer Insights.
ms.date: 12/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5972d5b191ded7db14e2ebe9a4a26570a8ea60ba
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978024"
---
# <a name="predictions-overview"></a>Gambaran keseluruhan ramalan

Dynamics 365 Customer Insights dilengkapi dengan pelbagai pilihan yang memanfaatkan AI dan pembelajaran mesin untuk meramalkan data. 

## <a name="out-of-box-models"></a>Model luar kotak

Cara paling mudah untuk bermula dengan meramalkan data adalah model yang ditakrif lebih awal, sering dirujuk sebagai model luar kotak. Mereka hanya memerlukan data dan struktur tertentu untuk menjana cerapan dengan cepat. Pada masa ini, model berikut tersedia: 

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

- [Nilai sepanjang hayat pelanggan](predict-customer-lifetime-value.md): Meramalkan potensi hasil pelanggan dalam keseluruhan interaksi dengan perniagaan.
- [Pengesyoran produk](predict-product-recommendation.md): Mencadangkan set pengesyoran produk ramalan berdasarkan tingkah laku pembelian dan pelanggan dengan corak pembelian yang sama.
- [Pulangan langganan](predict-subscription-churn.md): Meramalkan sama ada pelanggan berisiko untuk tidak menggunakan lagi produk atau perkhidmatan langganan syarikat anda.
- [Pulangan transaksi](predict-transactional-churn.md): Meramalkan jika pelanggan tidak lagi membeli produk atau perkhidmatan anda dalam tempoh masa tertentu.
- [Analisis sentimen](sentiment-analysis.md) : Menganalisis sentimen maklum balas pelanggan dan mengenal pasti aspek perniagaan yang sering disebutkan.

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

- [Pulangan transaksi](predict-transactional-churn.md): Meramalkan jika pelanggan tidak lagi membeli produk atau perkhidmatan anda dalam tempoh masa tertentu.

---


## <a name="azure-machine-learning-integration"></a>Penyepaduan Pembelajaran Mesin Azure

Jika sesebuah organisasi sudah menggunakan senario pembelajaran mesin berdasarkan eksperimen Pembelajaran Mesin Azure, ciri model tersuai dalam Customer Insights membantu untuk menyambungkan titik. Cipta aliran kerja yang membantu anda memilih data yang ingin anda janakan cerapan dan petakan hasil kepada profil pelanggan anda yang disatukan. Untuk mendapatkan maklumat lanjut, lihat [Model pembelajaran mesin tersuai](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder ramalan

Kadang-kadang, set data tidak lengkap dan beberapa nilai tidak diisi. Customer Insights boleh membantu untuk meramalkan nilai yang tidak diisi untuk entiti dan segmen Pelanggan. Untuk mendapatkan maklumat lanjut, lihat [Lengkapkan data separa anda dengan ramalan](predictions.md).
