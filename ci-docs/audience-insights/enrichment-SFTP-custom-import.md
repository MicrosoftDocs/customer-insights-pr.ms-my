---
title: Pengayaan dengan import tersuai SFTP
description: Maklumat umum tentang pengayaan import tersuai SFTP.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595866"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="987f7-103">Perkayakan profil pelanggan dengan data tersuai (pratonton)</span><span class="sxs-lookup"><span data-stu-id="987f7-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="987f7-104">Import tersuai Protokol Pemindahan Fail Selamat (SFTP) mendayakan anda mengimport data yang tidak perlu melalui proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="987f7-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="987f7-105">Ia adalah cara yang fleksibel, selamat dan mudah untuk membawa masuk data anda.</span><span class="sxs-lookup"><span data-stu-id="987f7-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="987f7-106">Import tersuai SFTP boleh digunakan dalam kombinasi dengan [Eksport SFTP](export-sftp.md) membolehkan anda mengeksport data profil pelanggan yang diperlukan untuk pengayaan.</span><span class="sxs-lookup"><span data-stu-id="987f7-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="987f7-107">Data kemudian boleh diproses, diperkaya dan import tersuai SFTP boleh digunakan untuk membawa data yang diperkaya kembali kepada keupayaan wawasan khalayak Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="987f7-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="987f7-108">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="987f7-108">Prerequisites</span></span>

<span data-ttu-id="987f7-109">Untuk mengkonfigurasi import tersuai SFTP, prasyarat berikut mesti dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="987f7-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="987f7-110">Anda mempunyai kelayakan pengguna (nama pengguna dan kata laluan) untuk lokasi SFTP data yang akan diimport.</span><span class="sxs-lookup"><span data-stu-id="987f7-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="987f7-111">Anda mempunyai URL dan nombor port (kebiasaannya 22) untuk hos STFP.</span><span class="sxs-lookup"><span data-stu-id="987f7-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="987f7-112">Anda mempunyai nama fail dan lokasi fail untuk diimport pada hos SFTP.</span><span class="sxs-lookup"><span data-stu-id="987f7-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="987f7-113">Terdapat fail *model.json* yang menentukan skema untuk data yang akan diimport.</span><span class="sxs-lookup"><span data-stu-id="987f7-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="987f7-114">Fail ini mestilah dalam direktori yang sama dengan fail untuk diimport.</span><span class="sxs-lookup"><span data-stu-id="987f7-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="987f7-115">Anda mempunyai keizinan [Pentadbir](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="987f7-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="987f7-116">Konfigurasi</span><span class="sxs-lookup"><span data-stu-id="987f7-116">Configuration</span></span>

1. <span data-ttu-id="987f7-117">Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.</span><span class="sxs-lookup"><span data-stu-id="987f7-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="987f7-118">Pada **Jubin import tersuai SFTP**, pilih **Perkayakan data saya**.</span><span class="sxs-lookup"><span data-stu-id="987f7-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="987f7-119">![Jubin Import tersuai SFTP](media/SFTP_Custom_Import_tile.png "Jubin Import tersuai SFTP")</span><span class="sxs-lookup"><span data-stu-id="987f7-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="987f7-120">Pilih **Mari Bermula** dan berikan kelayakan dan alamat untuk pelayan SFTP.</span><span class="sxs-lookup"><span data-stu-id="987f7-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="987f7-121">Contohnya, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="987f7-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="987f7-122">Masukkan nama fail yang mengandungi data dan laluan ke fail pada pelayan SFTP jika ia bukan dalam folder induk.</span><span class="sxs-lookup"><span data-stu-id="987f7-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="987f7-123">Sahkan semua input dengan memilih **Sambung ke Import Tersuai**.</span><span class="sxs-lookup"><span data-stu-id="987f7-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="987f7-124">![Terbang keluar Konfigurasi Import Tersuai SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Terbang keluar Konfigurasi Import Tersuai SFTP")</span><span class="sxs-lookup"><span data-stu-id="987f7-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="987f7-125">Mentakrifkan pemetaan medan</span><span class="sxs-lookup"><span data-stu-id="987f7-125">Defining field mappings</span></span> 

<span data-ttu-id="987f7-126">Direktori yang mengandungi fail untuk diimport pada pelayan SFTP juga mesti mengandungi fail *model.json*.</span><span class="sxs-lookup"><span data-stu-id="987f7-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="987f7-127">Fail ini mentakrifkan skema untuk digunakan bagi mengimport data.</span><span class="sxs-lookup"><span data-stu-id="987f7-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="987f7-128">Skema perlu menggunakan [Model Data Tersuai](/common-data-model/) untuk menentukan pemetaan medan.</span><span class="sxs-lookup"><span data-stu-id="987f7-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="987f7-129">Contoh mudah fail model.json kelihatan seperti ini:</span><span class="sxs-lookup"><span data-stu-id="987f7-129">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="987f7-130">Keputusan pengayaan</span><span class="sxs-lookup"><span data-stu-id="987f7-130">Enrichment results</span></span>

<span data-ttu-id="987f7-131">Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah.</span><span class="sxs-lookup"><span data-stu-id="987f7-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="987f7-132">Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="987f7-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="987f7-133">Masa pemprosesan akan bergantung pada saiz data yang akan diimport dan sambungan ke pelayan SFTP.</span><span class="sxs-lookup"><span data-stu-id="987f7-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="987f7-134">Selepas proses pengayaan selesai, anda boleh menyemak data pengayaan tersuai anda yang baru diimport di bawah **Pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="987f7-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="987f7-135">Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="987f7-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="987f7-136">Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.</span><span class="sxs-lookup"><span data-stu-id="987f7-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="987f7-137">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="987f7-137">Next steps</span></span>

<span data-ttu-id="987f7-138">Bina di atas data pelanggan anda yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="987f7-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="987f7-139">Cipta [segmen](segments.md), [ukuran](measures.md) dan [eksport data](export-destinations.md) untuk menyampaikan pengalaman diperibadikan kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="987f7-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]