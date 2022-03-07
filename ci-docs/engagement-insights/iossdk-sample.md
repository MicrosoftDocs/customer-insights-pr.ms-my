---
title: Jalankan sampel SDK iOS
description: Projek sampel untuk mengetahui tentang SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232853"
---
# <a name="run-the-ios-sdk-sample"></a>Jalankan sampel SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Projek iOS sampel ini membantu anda memahami cara SDK berfungsi dalam aplikasi. Anda tidak perlu menulis kod. Hanya tambah kunci pengingesan anda dan anda boleh terus melihat peristiwa dalam ruang kerja anda.

## <a name="prerequisites"></a>Prasyarat

- [Xcode versi 9+](https://developer.apple.com/xcode/downloads/)
- [Kunci pengingesan](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Muat turun sampel SDK iOS

1. [Muat turun cerapan penglibatan sampel iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Nyahzip fail dimampatkan `ei-ios-sample.zip`.
1. Buka projek aplikasi sampel dalam Xcode.
1. Dalam fail `EIConfig.plist`, gantikan rentetan `“YOUR-INGESTION-KEY”` dalam medan `ingestionKey` dengan kunci pengingesan ruang kerja anda daripada cerapan penglibatan di bawah **Pentadbir** > **Ruang Kerja** > **Panduan pemasangan**.
1. Pilih **Jalankan** untuk memulakan projek sampel.
1. Lihat peristiwa dalam ruang kerja anda.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
