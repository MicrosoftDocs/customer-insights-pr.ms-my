---
title: Penyambung Power Automate | Microsoft Docs
description: Mencipta aliran dalam Microsoft Power Automate daripada Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406434"
---
# <a name="power-automate-connector-preview"></a>Penyambung Power Automate (pratonton)

Pencetus peristiwa khusus untuk berlaku secara automatik apabila data anda berubah dan uruskan aliran yang lebih kompleks dalam [Power Automate](https://flow.microsoft.com/) secara langsung.

## <a name="power-automate-triggers"></a>Power Automate pencetus

Anda boleh menggunakan pelbagai pencetus yang membolehkan anda mencipta aliran untuk mengautomatikkan tugas berulang, seperti pemberitahuan atau tindakan yang lebih lanjut. 

- Pencetus apabila muat semula sumber data gagal. 
- Pencetus apabila muat semula sumber data berjaya.
- Pencetus apabila ambang bersilang pada segmen. Pencetus dihadkan untuk melintas di atas ambang.
- Pencetus apabila ambang bersilang pada ukuran perniagaan. Pencetus dihadkan melintas di atas ambang.
- Tercetus apabila segar semula penuh (sumber data, segmen, langkah,...) telah dilengkapkan.
- Tercetus apabila segar semula proses penyatuan (peta, padan, cantum) selesai.

[Konfigurasikan pencetus anda dalam Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate tindakan
Penyambung Power Automate menyediakan tindakan lain selain pencetus yang tersedia. Untuk maklumat lanjut, lihat [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Cipta aliran Power Automate dalam Insights khalayak

1. Dalam Insights khalayak, pergi ke **Pentadbir** > **Sistem**.

1. Pada halaman **Sistem**, pilih tab **Status**.

1. Dalam bahagian **Sumber Data**, pilih **Aliran** dan pilih **Cipta aliran** daripada senarai juntai bawah.
   > [!div class="mx-imgBorder"]
   > Penyambung ![Power Automate menunjukan tindakan Mencipta Aliran](media/power-automate-connector-create-flow.png "Penyambung Power Automate menunjukkan tindakan Cipta Aliran")

1. Dalam Power Automate, pilih salah satu daripada pencetus yang tersedia untuk mencipta aliran keutamaan anda. Jika anda sedang mencipta aliran pertama anda, anda akan perlu membuat pengesahan dengan penyambung Power Automate terlebih dahulu.
