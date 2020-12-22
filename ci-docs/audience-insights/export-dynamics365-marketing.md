---
title: Eksport data Customer Insights ke Dynamics 365 Marketing
description: Ketahui bagaimana mengkonfigur sambungan ke Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643784"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="6994a-103">Penyambung untuk Dynamics 365 Marketing (pratonton)</span><span class="sxs-lookup"><span data-stu-id="6994a-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6994a-104">Gunakan [segmen](segments.md) untuk menjana kumpulan tertentu kempen dan kenalan pelanggan dengan Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="6994a-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="6994a-105">Untuk maklumat lanjut, lihat [Gunakan segmen daripada Dynamics 365 Customer Insights dengan Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="6994a-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="6994a-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="6994a-106">Prerequisite</span></span>

<span data-ttu-id="6994a-107">Rekod kenalan [daripada Dynamics 365 Marketing yang diinges Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="6994a-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="6994a-108">Konfigur penyambung untuk Pemasaran</span><span class="sxs-lookup"><span data-stu-id="6994a-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="6994a-109">Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.</span><span class="sxs-lookup"><span data-stu-id="6994a-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6994a-110">Di bawah **Dynamics 365 Marketing**, pilih **Sediakan**.</span><span class="sxs-lookup"><span data-stu-id="6994a-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="6994a-111">Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="6994a-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="6994a-112">Masukkan URL Pemasaran organisasi anda dalam medan **Alamat pelayan**.</span><span class="sxs-lookup"><span data-stu-id="6994a-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="6994a-113">Dalam bahagian **Akaun pentadbir pelayan**, pilih **Daftar masuk** dan pilih akaun Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="6994a-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="6994a-114">Petakan medan ID pelanggan ke ID Kenalan Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6994a-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="6994a-115">Pilih **Seterusnya**.</span><span class="sxs-lookup"><span data-stu-id="6994a-115">Select **Next**.</span></span>

1. <span data-ttu-id="6994a-116">Pilih satu atau lebih segmen.</span><span class="sxs-lookup"><span data-stu-id="6994a-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="6994a-117">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="6994a-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6994a-118">Mengeksport data</span><span class="sxs-lookup"><span data-stu-id="6994a-118">Export the data</span></span>

<span data-ttu-id="6994a-119">Anda boleh [eksport data atas permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6994a-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6994a-120">Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6994a-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
