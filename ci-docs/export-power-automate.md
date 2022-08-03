---
title: Power Automate| penyambung (pratonton) Dokumen Microsoft
description: Cipta aliran dalam Microsoft Power Automate daripada Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196129"
---
# <a name="power-automate-connector-preview"></a>Penyambung Power Automate (pratonton)

Pencetus peristiwa khusus untuk berlaku secara automatik apabila data anda berubah dan uruskan aliran yang lebih kompleks dalam [Microsoft Power Automate](https://flow.microsoft.com/) secara langsung.

## <a name="known-limitations"></a>Had diketahui

- Maksimum 100 panggilan setiap 60 saat. [Gunakan parameter](/connectors/customerinsights/#get-items-from-an-entity) $skip untuk memanggil titik akhir API beberapa kali.

## <a name="power-automate-triggers"></a>Power Automate pencetus

Gunakan pencetus untuk mencipta aliran awan dan mengautomasikan tugas berulang, seperti pemberitahuan atau tindakan yang lebih lanjut. Gunakan pencetus apabila:

- Segar semula sumber data gagal.
- Segar semula sumber data berjaya.
- Ambang diseberang pada segmen. Pencetus dihadkan untuk melintas di atas ambang.
- Ambang diseberang pada langkah perniagaan. Hanya ukuran perniagaan tanpa dimensi disokong. Pencetus dihadkan untuk melintas di atas ambang.
- Segar semula berjadual penuh telah selesai. Pencetus ini tidak berfungsi untuk menyegar semula yang dimulakan secara manual.
- Segar semula proses penyatuan telah selesai.

[Konfigurasikan pencetus anda dalam Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate tindakan

Penyambung Power Automate menyediakan tindakan lain selain pencetus yang tersedia. Untuk maklumat lanjut, lihat [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Cipta aliran Power Automate

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pada jubin **Power Automate**, pilih **Sediakan**.

1. Penyambung Customer Insights (pratonton) dalam Power Automate terbuka. **Log masuk** ke Power Automate.

1. Pilih salah satu pencetus yang ada dan tambahkan lebih banyak langkah ke aliran baharu anda. Untuk maklumat lanjut, lihat [Cipta aliran awan dalam Power Automate](/power-automate/get-started-logic-flow).

Contoh cara menggunakan aliran: 
- Siarkan mesej ke saluran Microsoft Teams jika segar semula sumber data gagal. 
- Hantar e-mel kepada pemilik data apabila ambang pada segmen dilanggar.

[!INCLUDE [footer-include](includes/footer-banner.md)]
