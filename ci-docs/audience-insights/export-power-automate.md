---
title: Penyambung Power Automate | Microsoft Docs
description: Cipta aliran dalam Microsoft Power Automate daripada Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976099"
---
# <a name="power-automate-connector-preview"></a>Penyambung Power Automate (pratonton)

Pencetus peristiwa khusus untuk berlaku secara automatik apabila data anda berubah dan uruskan aliran yang lebih kompleks dalam [Power Automate](https://flow.microsoft.com/) secara langsung.

## <a name="power-automate-triggers"></a>Power Automate pencetus

Gunakan pencetus untuk mencipta aliran awan dan mengautomasikan tugas berulang, seperti pemberitahuan atau tindakan yang lebih lanjut. 

- Pencetus apabila muat semula sumber data gagal. 
- Pencetus apabila muat semula sumber data berjaya.
- Pencetus apabila ambang bersilang pada segmen. Pencetus dihadkan untuk melintas di atas ambang.
- Pencetus apabila ambang bersilang pada ukuran perniagaan. Hanya ukuran perniagaan tanpa dimensi disokong. Pencetus dihadkan melintas di atas ambang.
- Tercetus apabila segar semula penuh (sumber data, segmen, langkah,...) telah dilengkapkan.
- Tercetus apabila segar semula proses penyatuan (peta, padan, cantum) selesai.

[Konfigurasikan pencetus anda dalam Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate tindakan
Penyambung Power Automate menyediakan tindakan lain selain pencetus yang tersedia. Untuk maklumat lanjut, lihat [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Cipta aliran Power Automate

1. Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.

1. Pada jubin **Power Automate**, pilih **Sediakan**.

1. Penyambung Customer Insights (pratonton) dalam Power Automate terbuka. **Log masuk** ke Power Automate.

1. Pilih salah satu pencetus yang ada dan tambahkan lebih banyak langkah ke aliran baharu anda. Untuk maklumat lanjut, lihat [Cipta aliran awan dalam Power Automate](/power-automate/get-started-logic-flow).

Contoh cara menggunakan aliran: 
- Siarkan mesej ke saluran Microsoft Teams jika segar semula sumber data gagal. 
- Hantar e-mel kepada pemilik data apabila ambang pada segmen dilanggar.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
