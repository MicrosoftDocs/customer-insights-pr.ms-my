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
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="97468-103">Cipta segmen berdasarkan model ramalan (pratonton)</span><span class="sxs-lookup"><span data-stu-id="97468-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="97468-104">Keputusan ramalan kadang kala hanya diguna pakai pada subset pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="97468-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="97468-105">Tingkatkan pemperibadian pengesyoran dengan mencipta segmen daripada hasil model ramalan.</span><span class="sxs-lookup"><span data-stu-id="97468-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="97468-106">Sebagai contoh, anda mungkin mahu memberikan pengesyoran khusus kepada pelanggan yang lebih suka jenis perkhidmatan tertentu.</span><span class="sxs-lookup"><span data-stu-id="97468-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="97468-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="97468-107">Prerequisites</span></span>

- <span data-ttu-id="97468-108">Sekurang-kurangnya [Keizinan penyumbang](permissions.md) dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="97468-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="97468-109">Pengesyoran produk, pulangan transaksi, pulangan langganan atau model nilai sepanjang hayat pelanggan dikonfigurasikan dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="97468-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="97468-110">Semak keperluan untuk menyediakan model yang berbeza:</span><span class="sxs-lookup"><span data-stu-id="97468-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="97468-111">Model pengesyoran produk</span><span class="sxs-lookup"><span data-stu-id="97468-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="97468-112">Model pulangan langganan</span><span class="sxs-lookup"><span data-stu-id="97468-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="97468-113">Model pulangan transaksi</span><span class="sxs-lookup"><span data-stu-id="97468-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="97468-114">Model nilai sepanjang hayat pelanggan</span><span class="sxs-lookup"><span data-stu-id="97468-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="97468-115">Cipta segmen pelanggan berdasarkan ramalan</span><span class="sxs-lookup"><span data-stu-id="97468-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="97468-116">Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.</span><span class="sxs-lookup"><span data-stu-id="97468-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="97468-117">Pilih elipsis menegak bersebelahan dengan model yang anda mahu semak dan pilih **Lihat**.</span><span class="sxs-lookup"><span data-stu-id="97468-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="97468-118">Pada halaman hasil, pilih **Cipta segmen**.</span><span class="sxs-lookup"><span data-stu-id="97468-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="97468-119">Untuk maklumat lanjut mengenai halaman keputusan, kaji semula artikel mengenai model.</span><span class="sxs-lookup"><span data-stu-id="97468-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Tangkapan skrin halaman hasil ramalan dengan serlahan pada tindakan segmen Cipta.":::

1. <span data-ttu-id="97468-121">Cipta segmen baharu berdasarkan pada entiti output untuk model terpilih.</span><span class="sxs-lookup"><span data-stu-id="97468-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="97468-122">Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).</span><span class="sxs-lookup"><span data-stu-id="97468-122">For more information, see [Create and manage segments](segments.md).</span></span>