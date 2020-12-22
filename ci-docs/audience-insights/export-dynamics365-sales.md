---
title: Eksport data Customer Insights ke Dynamics 365 Sales
description: Ketahui bagaimana mengkonfigur sambungan ke Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643829"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="37aa6-103">Penyambung untuk Dynamics 365 Sales (pratonton)</span><span class="sxs-lookup"><span data-stu-id="37aa6-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="37aa6-104">Gunakan data pelanggan anda untuk mencipta senarai pemasaran, menyusuli aliran kerja dan menghantar promosi dengan Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="37aa6-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="37aa6-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="37aa6-105">Prerequisite</span></span>

<span data-ttu-id="37aa6-106">Rekod kenalan [daripada Dynamics 365 Sales yang diinges menggunakan Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="37aa6-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="37aa6-107">Konfigur penyambung untuk Jualan</span><span class="sxs-lookup"><span data-stu-id="37aa6-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="37aa6-108">Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.</span><span class="sxs-lookup"><span data-stu-id="37aa6-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="37aa6-109">Di bawah **Dynamics 365 Sales**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="37aa6-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="37aa6-110">Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="37aa6-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="37aa6-111">Masukkan URL Jualan organisasi anda dalam medan **Alamat pelayan**.</span><span class="sxs-lookup"><span data-stu-id="37aa6-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="37aa6-112">Dalam bahagian **Akaun pentadbir pelayan**, pilih **Daftar masuk** dan pilih akaun Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="37aa6-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="37aa6-113">Petakan medan ID pelanggan ke ID Kenalan Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="37aa6-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="37aa6-114">Pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="37aa6-114">Select **Next**.</span></span>

1. <span data-ttu-id="37aa6-115">Pilih satu atau lebih segmen.</span><span class="sxs-lookup"><span data-stu-id="37aa6-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="37aa6-116">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="37aa6-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="37aa6-117">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="37aa6-117">Export the data</span></span>

<span data-ttu-id="37aa6-118">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="37aa6-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="37aa6-119">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="37aa6-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
