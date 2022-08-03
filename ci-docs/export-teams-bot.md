---
title: Pasukan bot untuk Dynamics 365 Customer Insights (pratonton)
description: Carian profil pelanggan disatukan dalam Microsoft Teams dengan bantuan bot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195853"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Pasukan bot untuk Dynamics 365 Customer Insights (pratonton)

Sambung dengan Microsoft Teams untuk membolehkan bot mencari profil pelanggan disatukan dalam saluran Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Bot Teams menunjukkan rekod pelanggan":::

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya satu [sumber data ditambah](data-sources.md).
- [Proses penyatuan](data-unification.md) adalah lengkap.
- Medan ditambah ke [indeks carian & penapis](search-filter-index.md).
- Customer Insights dan Teams adalah dalam organisasi yang sama.
- Persekitaran anda mempunyai khalayak sasaran utama yang ditetapkan kepada pelanggan individu. Akaun perniagaan tidak disokong.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Konfigurasi bot

1. Pergi ke **Pentadbir** > **Sambungan**.
1. Pada jubin Microsoft Teams, pilih **Sediakan**.
1. Anda dihalakan semula ke kawasan **Aplikasi** dalam Teams. Anda juga boleh membuka Teams dan memilih **Aplikasi** di bahagian bawah sudut kiri atau [dapatkannya daripada AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) secara terus.
1. Cari **Customer Insights** dan pilih aplikasi.
1. Pilih **Tambah**.
1. Log masuk ke Wawasan Pelanggan dalam Pasukan. Mesej selamat datang dipaparkan.

## <a name="things-you-can-do-with-the-bot"></a>Perkara yang anda boleh lakukan dengan bot

Bot menyediakan keupayaan carian untuk profil pelanggan disatukan.

- Masukkan **carian** diikuti dengan nama, alamat e-mel atau sebarang medan lain pada profil pelanggan bersatu yang ditambahkan pada indeks carian & penapis.

  Anda akan mendapat kad dengan sehingga 15 medan daripada profil pelanggan yang terhasil. Berbilang padanan mengembalikan senarai hasil di mana anda boleh memilih profil. Untuk mencari padanan yang tepat, tambahkan istilah carian dalam petikan berganda.

- Jika organisasi anda mengekalkan berbilang persekitaran Wawasan Pelanggan dalam organisasi yang sama, masukkan **suis** untuk memilih persekitaran yang anda ingin sambungkan bot.

- Masukkan **bantuan** untuk melihat senarai perintah yang tersedia untuk bot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]