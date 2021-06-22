---
title: Gambaran keseluruhan tentang senario ramalan yang disokong
description: Senario dan pilihan ramalan dilindungi oleh aplikasi Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095733"
---
# <a name="predictions-overview"></a><span data-ttu-id="c9521-103">Gambaran keseluruhan ramalan</span><span class="sxs-lookup"><span data-stu-id="c9521-103">Predictions overview</span></span>

<span data-ttu-id="c9521-104">Dynamics 365 Customer Insights dilengkapi dengan pelbagai pilihan yang memanfaatkan AI dan pembelajaran mesin untuk meramalkan data.</span><span class="sxs-lookup"><span data-stu-id="c9521-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="c9521-105">Model luar kotak</span><span class="sxs-lookup"><span data-stu-id="c9521-105">Out-of-box models</span></span>

<span data-ttu-id="c9521-106">Cara paling mudah untuk bermula dengan meramalkan data adalah model yang ditakrif lebih awal, sering dirujuk sebagai model luar kotak.</span><span class="sxs-lookup"><span data-stu-id="c9521-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="c9521-107">Mereka hanya memerlukan data dan struktur tertentu untuk menjana cerapan dengan cepat.</span><span class="sxs-lookup"><span data-stu-id="c9521-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="c9521-108">Pada masa ini, model berikut tersedia:</span><span class="sxs-lookup"><span data-stu-id="c9521-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="c9521-109">[Nilai sepanjang hayat pelanggan](predict-customer-lifetime-value.md): Meramalkan potensi hasil pelanggan dalam keseluruhan interaksi dengan perniagaan.</span><span class="sxs-lookup"><span data-stu-id="c9521-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="c9521-110">[Pengesyoran produk](predict-product-recommendation.md): Mencadangkan set pengesyoran produk ramalan berdasarkan tingkah laku pembelian dan pelanggan dengan corak pembelian yang sama.</span><span class="sxs-lookup"><span data-stu-id="c9521-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="c9521-111">[Pulangan langganan](predict-subscription-churn.md): Meramalkan sama ada pelanggan berisiko untuk tidak menggunakan lagi produk atau perkhidmatan langganan syarikat anda.</span><span class="sxs-lookup"><span data-stu-id="c9521-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="c9521-112">[Pulangan transaksi](predict-transactional-churn.md): Meramalkan jika pelanggan tidak lagi membeli produk atau perkhidmatan anda dalam tempoh masa tertentu.</span><span class="sxs-lookup"><span data-stu-id="c9521-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="c9521-113">Penyepaduan Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="c9521-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="c9521-114">Jika sesebuah organisasi sudah menggunakan senario pembelajaran mesin berdasarkan eksperimen Pembelajaran Mesin Azure, ciri model tersuai dalam Customer Insights membantu untuk menyambungkan titik.</span><span class="sxs-lookup"><span data-stu-id="c9521-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="c9521-115">Cipta aliran kerja yang membantu anda memilih data yang ingin anda janakan cerapan dan petakan hasil kepada profil pelanggan anda yang disatukan.</span><span class="sxs-lookup"><span data-stu-id="c9521-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="c9521-116">Untuk mendapatkan maklumat lanjut, lihat [Model pembelajaran mesin tersuai](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="c9521-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="c9521-117">Ramalan AI Builder</span><span class="sxs-lookup"><span data-stu-id="c9521-117">AI Builder prediction</span></span>

<span data-ttu-id="c9521-118">Kadang-kadang, set data tidak lengkap dan beberapa nilai tidak diisi.</span><span class="sxs-lookup"><span data-stu-id="c9521-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="c9521-119">Customer Insights boleh membantu untuk meramalkan nilai yang tidak diisi untuk entiti dan segmen Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="c9521-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="c9521-120">Untuk mendapatkan maklumat lanjut, lihat [Lengkapkan data separa anda dengan ramalan](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="c9521-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
