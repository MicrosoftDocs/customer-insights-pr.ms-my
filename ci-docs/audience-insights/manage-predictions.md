---
title: Tugas dikongsi untuk senario ramalan
description: Ketahui cara mengurus, menyelesaikan masalah dan memperhalus ramalan.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095734"
---
# <a name="manage-predictions"></a><span data-ttu-id="c2f5d-103">Urus ramalan</span><span class="sxs-lookup"><span data-stu-id="c2f5d-103">Manage predictions</span></span>

<span data-ttu-id="c2f5d-104">Artikel ini membincangkan beberapa tugas yang paling banyak senario ramalan berkongsi.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="c2f5d-105">Selesaikan ramalan yang gagal</span><span class="sxs-lookup"><span data-stu-id="c2f5d-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="c2f5d-106">Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="c2f5d-107">Pilih elipsis menegak bersebelahan dengan ramalan yang anda mahu lihat log ralatnya.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="c2f5d-108">Pilih **Log**.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-108">Select **Logs**.</span></span>

1. <span data-ttu-id="c2f5d-109">Semak semula semua ralat.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-109">Review all the errors.</span></span> <span data-ttu-id="c2f5d-110">Terdapat beberapa jenis ralat yang boleh berlaku dan ia menghuraikan keadaan yang menyebabkan ralat tersebut.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="c2f5d-111">Contohnya, ralat bahawa data tidak mencukupi untuk meramal secara tepat pada lazimnya diselesaikan dengan memuatkan data tambahan ke dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="c2f5d-112">Laporan kebolehgunaan data input</span><span class="sxs-lookup"><span data-stu-id="c2f5d-112">Input data usability report</span></span>

<span data-ttu-id="c2f5d-113">Laporan kebolehgunaan data input menyediakan pandangan ralat disatukan dan amaran bahawa ramalan luar kotak anda mungkin menjana.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="c2f5d-114">Ia juga memberi pengesyoran cara meningkatkan prestasi model.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="c2f5d-115">Laporan tersedia selepas model selesai proses latihan.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="c2f5d-116">Ia dicipta untuk setiap model secara berasingan, tanpa mengira jika ia berjaya sepenuhnya atau tidak.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="c2f5d-117">Pada masa ini, ciri ini hanya berfungsi untuk model Pulangan Transaksi.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="c2f5d-118">Lihat laporan kebolehgunaan data input</span><span class="sxs-lookup"><span data-stu-id="c2f5d-118">View the input data usability report</span></span>

<span data-ttu-id="c2f5d-119">Selepas model luar kotak telah melengkapkan langkah latihan, lihat laporan:</span><span class="sxs-lookup"><span data-stu-id="c2f5d-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="c2f5d-120">Pilih elips di sebelah nama model dan pilih **Laporan kebolehgunaan data input**.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="c2f5d-121">Pilih status model pilih **Lihat laporan kebolehgunaan data input** dalam anak tetingkap sisi.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="c2f5d-122">Memilih salah satu model dalam senarai dan pilih **Laporan kebolehgunaan data input** dalam bar perintah.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="c2f5d-123">Buka halaman hasil model dan pilih **Laporan kebolehgunaan data input** dalam bar perintah.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="c2f5d-124">Maklumat dalam laporan kebolehgunaan data input</span><span class="sxs-lookup"><span data-stu-id="c2f5d-124">Information in the input data usability report</span></span>

<span data-ttu-id="c2f5d-125">Lajur berikut dalam laporan mengandungi maklumat yang berguna untuk meningkatkan data untuk model.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Contoh laporan kebolehgunaan data input yang menunjukkan jadual dengan ralat, amaran dan pengesyoran.":::

- <span data-ttu-id="c2f5d-127">Nama: Nama deskriptif ralat, amaran atau pengesyoran.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="c2f5d-128">Langkah: Fasa model, latihan atau skor yang dirujuk maklumat.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="c2f5d-129">Keadaan: Keterukan maklumat (ralat, amaran, pengesyoran).</span><span class="sxs-lookup"><span data-stu-id="c2f5d-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="c2f5d-130">Nama lajur: Lajur dalam entiti yang perlu diubah suai untuk meningkatkan prestasi model.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="c2f5d-131">Nama entiti: Nama entiti yang perlu diubah suai untuk meningkatkan prestasi model.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="c2f5d-132">Butiran: Butiran tentang ralat, amaran atau pengesyoran.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="c2f5d-133">Segar semula ramalan</span><span class="sxs-lookup"><span data-stu-id="c2f5d-133">Refresh a prediction</span></span>

<span data-ttu-id="c2f5d-134">Ramalan akan menyegar semula secara automatik pada [jadual yang sama data anda menyegar semula](system.md#schedule-tab) seperti yang dikonfigurasikan dalam tetapan.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="c2f5d-135">Anda boleh juga menyegarkannya semula secara manual.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="c2f5d-136">Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="c2f5d-137">Pilih elipsis menegak di sebelah ramalan yang anda mahu segar semula.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="c2f5d-138">Pilih **Segar Semula**.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="c2f5d-139">Padamkan ramalan</span><span class="sxs-lookup"><span data-stu-id="c2f5d-139">Delete a prediction</span></span>

<span data-ttu-id="c2f5d-140">Memadamkan ramalan juga mengalih keluar entiti outputnya.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="c2f5d-141">Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="c2f5d-142">Pilih elipsis menegak di sebelah ramalan yang anda mahu padamkan.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="c2f5d-143">Pilih **Padam**.</span><span class="sxs-lookup"><span data-stu-id="c2f5d-143">Select **Delete**.</span></span>
