---
title: Power Automate| penyambung (pratonton) Dokumen Microsoft
description: Cipta aliran dalam Microsoft Power Automate daripada Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29a861dad926072f6f849d738d868f0f3b9306be
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082454"
---
# <a name="power-automate-connector-preview"></a>Penyambung Power Automate (pratonton)

Pencetus peristiwa khusus untuk berlaku secara automatik apabila data anda berubah dan uruskan aliran yang lebih kompleks dalam [Microsoft Power Automate](https://flow.microsoft.com/) secara langsung.

## <a name="known-limitations"></a>Had diketahui

- Anda boleh melakukan maksimum 100 panggilan setiap 60 saat. Anda boleh memanggil titik akhir API beberapa kali dengan menggunakan parameter $skip. [Ketahui lebih lanjut tentang parameter $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Power Automate pencetus

Gunakan pencetus untuk mencipta aliran awan dan mengautomasikan tugas berulang, seperti pemberitahuan atau tindakan yang lebih lanjut.

- Pencetus apabila muat semula sumber data gagal.
- Pencetus apabila muat semula sumber data berjaya.
- Pencetus apabila ambang bersilang pada segmen. Pencetus dihadkan untuk melintas di atas ambang.
- Pencetus apabila ambang bersilang pada ukuran perniagaan. Hanya ukuran perniagaan tanpa dimensi disokong. Pencetus dihadkan untuk melintas di atas ambang.
- Tercetus apabila segar semula penuh (sumber data, segmen, langkah,...) telah selesai.
- Pencetus apabila segar semula proses penyatuan selesai.

[Konfigurasikan pencetus anda dalam Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate tindakan

Penyambung Power Automate menyediakan tindakan lain selain pencetus yang tersedia. Untuk maklumat lanjut, lihat [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Cipta aliran Power Automate

1. Pergi ke **Pentadbir** > **Destinasi Eksport**.

1. Pada jubin **Power Automate**, pilih **Sediakan**.

1. Penyambung Customer Insights (pratonton) dalam Power Automate terbuka. **Log masuk** ke Power Automate.

1. Pilih salah satu pencetus yang ada dan tambahkan lebih banyak langkah ke aliran baharu anda. Untuk maklumat lanjut, lihat [Cipta aliran awan dalam Power Automate](/power-automate/get-started-logic-flow).

Contoh cara menggunakan aliran: 
- Siarkan mesej ke saluran Microsoft Teams jika segar semula sumber data gagal. 
- Hantar e-mel kepada pemilik data apabila ambang pada segmen dilanggar.



[!INCLUDE [footer-include](includes/footer-banner.md)]
