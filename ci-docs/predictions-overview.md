---
title: Gambaran keseluruhan tentang senario ramalan yang disokong
description: Senario dan pilihan ramalan dilindungi oleh aplikasi Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643934"
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
- [Analisis sentimen](sentiment-analysis.md): Menganalisis sentimen maklum balas pelanggan dan mengenal pasti aspek perniagaan yang sering disebut.

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

- [Pulangan transaksi](predict-transactional-churn.md): Meramalkan jika pelanggan tidak lagi membeli produk atau perkhidmatan anda dalam tempoh masa tertentu.

---

> [!TIP]
> Kami mengesyorkan agar anda sentiasa menyegarkan semula model di luar kotak dengan data yang dikemas kini untuk memastikan ia memaklumkan kes penggunaan perniagaan anda dengan tepat. Data disegar semula secara ad-hoc apabila sistem menelan sumber data baru atau dikemas kini. Walau bagaimanapun, model hanya akan rescore dalam kes ini dan terus menggunakan data latihan sedia ada.
> 
> Anda boleh mengkonfigurasi **jadual** Kemas Kini dengan menetapkan jadual latihan semula model dalam pengalaman konfigurasi. Model ini akan melatih semula dan menyusun semula jadual ini, yang boleh anda ubah pada bila-bila masa.


## <a name="azure-machine-learning-integration"></a>Penyepaduan Pembelajaran Mesin Azure

Jika sesebuah organisasi sudah menggunakan senario pembelajaran mesin berdasarkan eksperimen Pembelajaran Mesin Azure, ciri model tersuai dalam Customer Insights membantu untuk menyambungkan titik. Cipta aliran kerja yang membantu anda memilih data yang ingin anda janakan cerapan dan petakan hasil kepada profil pelanggan anda yang disatukan. Untuk mendapatkan maklumat lanjut, lihat [Model pembelajaran mesin tersuai](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder ramalan

Kadang-kadang, set data tidak lengkap dan beberapa nilai tidak diisi. Customer Insights boleh membantu untuk meramalkan nilai yang tidak diisi untuk entiti dan segmen Pelanggan. Untuk mendapatkan maklumat lanjut, lihat [Lengkapkan data separa anda dengan ramalan](predictions.md).
