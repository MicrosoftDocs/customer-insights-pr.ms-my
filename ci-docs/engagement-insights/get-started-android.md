---
title: Mari bermula dengan SDK Android
description: Ketahui cara memeribadikan dan menjalankan SDK Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036929"
---
# <a name="get-started-with-the-android-sdk"></a>Mari bermula dengan SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tutorial ini membimbing anda melalui proses memodelkan aplikasi Android anda dengan SDK cerapan penglibatan Dynamics 365 Customer Insights. Anda akan mula melihat peristiwa dalam portal anda dalam masa lima minit atau lebih awal.

## <a name="configuration-options"></a>Pilihan konfigurasi
Pilihan konfigurasi berikut boleh dihantar ke SDK:

- **ingestionKey**: Kunci pengingesan digunakan untuk menghantar peristiwa pada ruang kerja anda.

## <a name="prerequisites"></a>Prasyarat

- Android Studio

- Tahap API Android Minimum: 16 (Jelly Bean)

- Kunci pengingesan (lihat di bawah untuk arahan cara memperoleh)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Langkah 1. Mengintegrasikan SDK ke dalam aplikasi anda
Mulakan proses dengan memilih ruang kerja, memilih platform mudah alih Android, dan memuat turun SDK Android.

- Gunakan penukar ruang kerja dalam anak tetingkap navigasi kiri untuk memilih ruang kerja anda.

- Jika anda tidak mempunyai ruang kerja yang sedia ada, pilih **Ruang Kerja Baharu** dan ikut langkah untuk mencipta [ruang kerja baharu](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Langkah 2. Konfigurasikan SDK

1. Selepas anda mencipta ruang kerja, pergi ke **Pentadbir** > **Ruang Kerja** dan kemudian pilih **Panduan pemasangan**. 

1. Muat turun [cerapan penglibatan SDK Android](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip), dan letakkan fail `eiandroidsdk-debug.aar` dalam folder `libs`.

1. Buka fail `build.gradle` tahap projek anda dan tambah cebisan berikut:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Sediakan cerapan penglibatan konfigurasi SDK melalui fail `AndroidManifest.xml` anda yang terletak di bawah folder `manifests`. 
1. Salin cebisan XML daripada **Panduan pemasangan**. `Your-Ingestion-Key` perlu diisi secara automatik.

   > [!NOTE]
   > Anda tidak perlu menggantikan bahagian `${applicationId}`. Ia perlu diisi secara automatik.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Dayakan atau nyahdayakan autorekod peristiwa `View` dengan menetapkan medan `autoCapture` di atas kepada `true` atau `false`.

1. (Pilihan) Konfigurasi lain termasuk menetapkan URL pengumpul titik tamat. Tetapan ini boleh ditambah di bawah metadata utama pengingesan dalam `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Langkah 3. Asalkan SDK daripada MainActivity 

Selepas anda memulakan SDK, anda boleh bekerja dengan peristiwa dan sifat dalam persekitaran MainActivity.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Tetapkan sifat untuk semua acara (pilihan)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Jenis berikut disokong untuk sifat peristiwa konteks:
- Jalur
- Tarikh
- Ganda
- Panjang
- Boolean
- UUID

### <a name="track-an-event"></a>Jejak peristiwa

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Tetapkan butiran pengguna untuk peristiwa anda (pilihan)

SDK membolehkan anda mentakrifkan maklumat pengguna yang boleh dihantar dengan setiap peristiwa. Anda boleh menentukan maklumat pengguna dengan memanggil API `setUser(user: User)` pada tahap `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Kelas data `User` mengandungi sifat rentetan berikut:

- **localId**: ID tempatan pengguna.
- **authId**: ID pengguna yang disahkan.
- **authType**: Jenis pengesahan yang digunakan untuk mendapatkan ID pengguna yang disahkan.
- **name**: Nama pengguna.
- **email**: Alamat e-mel pengguna.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
