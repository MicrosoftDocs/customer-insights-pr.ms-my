---
title: Sampel SDK Android
description: Projek sampel untuk mengetahui tentang SDK Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229929"
---
# <a name="run-the-android-sdk-sample"></a>Jalankan sampel SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Projek Android sampel ini membantu anda memahami cara SDK berfungsi dalam aplikasi. Anda tidak perlu menulis kod. Hanya tambah kunci pengingesan anda dan anda boleh terus melihat peristiwa dalam ruang kerja anda.

## <a name="prerequisites"></a>Prasyarat

- [Android Studio](https://developer.android.com/studio)
- [Kunci pengingesan](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Muat turun sampel SDK Android

1. [Muat turun cerapan penglibatan sampel SDK Android](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Nyahzip fail dimampatkan `ei-android-sample.zip`.
1. Buka folder yang tidak dizipkan dalam Android Studio.
1. Dalam fail `AndroidManifest.xml`, gantikan rentetan `"Your-Ingestion-Key"` dengan kunci pengingesan ruang kerja anda daripada cerapan penglibatan di bawah **Pentadbir** > **Ruang Kerja** > **Panduan pemasangan**. 

   > [!NOTE]
   > Anda tidak perlu menggantikan bahagian `${applicationId}`. Ia perlu diisi secara automatik.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Pilih **Jalankan** untuk memulakan projek sampel.
1. Lihat peristiwa dalam ruang kerja anda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
