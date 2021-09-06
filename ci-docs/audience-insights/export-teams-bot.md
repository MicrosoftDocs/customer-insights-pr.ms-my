---
title: Bot untuk Microsoft Teams
description: Carian profil pelanggan disatukan dalam Microsoft Teams dengan bantuan bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 9bf401124b0ffb21b046954056141e7703386d4911f89f34ffc0fcb84bf0f4be
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032493"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Pasukan bot untuk Dynamics 365 Customer Insights (pratonton)

Sambung dengan Microsoft Teams untuk membolehkan bot mencari profil pelanggan disatukan dalam saluran Teams.

> [!div class="mx-imgBorder"]
> ![Bot Teams menunjukkan rekod pelanggan.](media/teams-bot.png "Bot Teams menunjukkan rekod pelanggan")

## <a name="prerequisites"></a>Prasyarat

Untuk menyedia dan mengkonfigurasi bot, prasyarat berikut mesti dipenuhi:

- Sekurang-kurangnya satu [sumber data ditambah](data-sources.md).
- [Proses penyatuan](data-unification.md) adalah lengkap.
- Medan ditambah ke [indeks carian dan tapisan](search-filter-index.md).
- Customer Insights dan Teams adalah dalam organisasi yang sama.

## <a name="configure-the-bot"></a>Konfigurasi bot

1. Dalam Insights khalayak, pergi ke **Pentadbir** > **Export Destinasi**.
1. Pada jubin Microsoft Teams, pilih **Sediakan**.
1. Anda dihalakan semula ke kawasan **Aplikasi** dalam Teams. Anda juga boleh membuka Teams dan memilih **Aplikasi** di bahagian bawah sudut kiri atau [dapatkannya daripada AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) secara terus.
1. Cari **Customer Insights** dan pilih aplikasi.
1. Pilih **Tambah**.
1. Selepas mendaftar masuk ke Customer Insights dalam Teams, anda akan melihat message selamat datang dan boleh bermula.

## <a name="things-you-can-do-with-the-bot"></a>Perkara yang anda boleh lakukan dengan bot

Bot menyediakan keupayaan carian untuk profil pelanggan disatukan.

- Masukkan **Cari** diikuti dengan nama, alamat e-mel, atau mana-mana medan pada profil pelanggan disatukan yang ditambah ke indeks carian dan tapisan.

  Anda akan mendapat kad dengan sehingga 15 medan daripada profil pelanggan yang terhasil. Berbilang padanan mengembalikan senarai hasil di mana anda boleh memilih profil. Anda boleh menambah istilah carian dalam petikan berganda untuk mencari padanan yang tepat.

- Jika organisasi anda mengekalkan berbilang persekitaran Customer Insights dalam organisasi yang sama, anda boleh memasukkan **switchinstance** untuk memilih persekitaran yang anda mahu sambungkan bot tersebut.

- Masukkan **bantuan** untuk melihat senarai perintah yang tersedia untuk bot.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]