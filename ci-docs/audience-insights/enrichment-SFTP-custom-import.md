---
title: Pengayaan dengan import tersuai SFTP
description: Maklumat umum tentang pengayaan import tersuai SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896292"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="48c79-103">Perkayakan profil pelanggan dengan data tersuai (pratonton)</span><span class="sxs-lookup"><span data-stu-id="48c79-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="48c79-104">Import tersuai Protokol Pemindahan Fail Selamat (SFTP) membolehkan anda mengimport data yang tidak perlu melalui proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="48c79-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="48c79-105">Ia adalah cara yang fleksibel, selamat dan mudah untuk membawa masuk data anda.</span><span class="sxs-lookup"><span data-stu-id="48c79-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="48c79-106">Import tersuai SFTP boleh digunakan dalam kombinasi dengan [Eksport SFTP](export-sftp.md) membolehkan anda mengeksport data profil pelanggan yang diperlukan untuk pengayaan.</span><span class="sxs-lookup"><span data-stu-id="48c79-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="48c79-107">Data kemudian boleh diproses, diperkaya dan import tersuai SFTP boleh digunakan untuk membawa data yang diperkaya kembali kepada keupayaan wawasan khalayak Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="48c79-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="48c79-108">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="48c79-108">Prerequisites</span></span>

<span data-ttu-id="48c79-109">Untuk mengkonfigurasi import tersuai SFTP, prasyarat berikut mesti dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="48c79-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="48c79-110">Anda mempunyai nama fail dan lokasi (laluan) fail yang akan diimport pada hos SFTP.</span><span class="sxs-lookup"><span data-stu-id="48c79-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="48c79-111">Terdapat fail *model.json* yang menentukan [skema Common Data Model](/common-data-model/) untuk data yang akan diimport.</span><span class="sxs-lookup"><span data-stu-id="48c79-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="48c79-112">Fail ini mestilah dalam direktori yang sama dengan fail untuk diimport.</span><span class="sxs-lookup"><span data-stu-id="48c79-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="48c79-113">Sambungan SFTP telah dikonfigurasikan oleh pentadbir *atau* anda mempunyai keizinan [pentadbir](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="48c79-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="48c79-114">Anda memerlukan kelayakan pengguna, URL dan nombor port untuk lokasi SFTP yang mahu diimport data.</span><span class="sxs-lookup"><span data-stu-id="48c79-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="48c79-115">Konfigurasikan import</span><span class="sxs-lookup"><span data-stu-id="48c79-115">Configure the import</span></span>

1. <span data-ttu-id="48c79-116">Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.</span><span class="sxs-lookup"><span data-stu-id="48c79-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="48c79-117">Pada **jubin import tersuai SFTP**, pilih **Perkayakan data saya** dan kemudian pilih **Mari bermula**.</span><span class="sxs-lookup"><span data-stu-id="48c79-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Jubin import tersuai SFTP.":::

1. <span data-ttu-id="48c79-119">Pilih [sambungan](connections.md) daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="48c79-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="48c79-120">Hubungi pentadbir jika tiada sambungan tersedia.</span><span class="sxs-lookup"><span data-stu-id="48c79-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="48c79-121">Jika anda seorang pentadbir, anda boleh mencipta sambungan dengan memilih **Tambah sambungan** dan memilih **Import Tersuai SFTP** daripada menu juntai bawah.</span><span class="sxs-lookup"><span data-stu-id="48c79-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="48c79-122">Pilih **Sambung ke Import Tersuai** untuk mengesahkan sambungan yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="48c79-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="48c79-123">Pilih **Seterusnya** dan masukkan **Nama Fail** dan **Laluan** dalam fail data yang anda mahu import.</span><span class="sxs-lookup"><span data-stu-id="48c79-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Tangkapan skrin semasa memasuki lokasi data.":::

1. <span data-ttu-id="48c79-125">Pilih **Seterusnya** dan berikan nama untuk pengayaan dan nama untuk entiti output.</span><span class="sxs-lookup"><span data-stu-id="48c79-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="48c79-126">Pilih **Simpan pengayaan** selepas menyemak pilihan anda.</span><span class="sxs-lookup"><span data-stu-id="48c79-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="48c79-127">Konfigurasikan sambungan untuk Import Tersuai SFTP</span><span class="sxs-lookup"><span data-stu-id="48c79-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="48c79-128">Anda perlu menjadi pentadbir untuk mengkonfigurasikan sambungan.</span><span class="sxs-lookup"><span data-stu-id="48c79-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="48c79-129">Pilih **Tambah sambungan** apabila mengkonfigurasikan pengayaan *atau* pergi ke **Pentadbir** > **Sambungan** dan pilih **Sediakan** pada jubin Import Tersuai.</span><span class="sxs-lookup"><span data-stu-id="48c79-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="48c79-130">Masukkan nama untuk sambungan dalam kotak **Nama paparan**.</span><span class="sxs-lookup"><span data-stu-id="48c79-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="48c79-131">Masukkan nama pengguna, kata laluan dan hos URL yang sah untuk pelayan STFP data yang akan diimport tinggal.</span><span class="sxs-lookup"><span data-stu-id="48c79-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="48c79-132">Semak semula dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="48c79-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="48c79-133">Pilih **Sahkan** untuk mengesahkan konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="48c79-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="48c79-134">Setelah pengesahan selesai, sambungan boleh disimpan dengan mengklik **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="48c79-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="48c79-135">![Halaman konfigurasi sambungan Experian](media/enrichment-SFTP-connection.png "Halaman konfigurasi sambungan Experian")</span><span class="sxs-lookup"><span data-stu-id="48c79-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="48c79-136">Mentakrifkan pemetaan medan</span><span class="sxs-lookup"><span data-stu-id="48c79-136">Defining field mappings</span></span> 

<span data-ttu-id="48c79-137">Direktori yang mengandungi fail untuk diimport pada pelayan SFTP juga mesti mengandungi fail *model.json*.</span><span class="sxs-lookup"><span data-stu-id="48c79-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="48c79-138">Fail ini mentakrifkan skema untuk digunakan bagi mengimport data.</span><span class="sxs-lookup"><span data-stu-id="48c79-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="48c79-139">Skema perlu menggunakan [Model Data Tersuai](/common-data-model/) untuk menentukan pemetaan medan.</span><span class="sxs-lookup"><span data-stu-id="48c79-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="48c79-140">Contoh mudah fail model.json kelihatan seperti ini:</span><span class="sxs-lookup"><span data-stu-id="48c79-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="48c79-141">Keputusan pengayaan</span><span class="sxs-lookup"><span data-stu-id="48c79-141">Enrichment results</span></span>

<span data-ttu-id="48c79-142">Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah.</span><span class="sxs-lookup"><span data-stu-id="48c79-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="48c79-143">Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="48c79-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="48c79-144">Masa pemprosesan akan bergantung pada saiz data yang akan diimport dan sambungan ke pelayan SFTP.</span><span class="sxs-lookup"><span data-stu-id="48c79-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="48c79-145">Selepas proses pengayaan selesai, anda boleh menyemak data pengayaan tersuai anda yang baru diimport di bawah **Pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="48c79-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="48c79-146">Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="48c79-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="48c79-147">Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.</span><span class="sxs-lookup"><span data-stu-id="48c79-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="48c79-148">Langkah seterusnya</span><span class="sxs-lookup"><span data-stu-id="48c79-148">Next steps</span></span>

<span data-ttu-id="48c79-149">Bina di atas data pelanggan anda yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="48c79-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="48c79-150">Cipta [segmen](segments.md), [ukuran](measures.md) dan [eksport data](export-destinations.md) untuk menyampaikan pengalaman diperibadikan kepada pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="48c79-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
