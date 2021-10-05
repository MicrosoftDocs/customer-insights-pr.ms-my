---
title: Mari bermula dengan SDK Android
description: Ketahui cara memeribadikan dan menjalankan SDK Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a060ac60db71a7b0fb8c0d7a3b0e266004fbee6a
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494286"
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

## <a name="integrate-the-sdk-into-your-application"></a>Mengintegrasikan SDK ke dalam aplikasi anda
Mulakan proses dengan memilih ruang kerja, memilih platform mudah alih Android, dan memuat turun SDK Android.

- Gunakan penukar ruang kerja dalam anak tetingkap navigasi kiri untuk memilih ruang kerja anda.

- Jika anda tidak mempunyai ruang kerja yang sedia ada, pilih **Ruang Kerja Baharu** dan ikut langkah untuk mencipta [ruang kerja baharu](create-workspace.md).

- Selepas anda mencipta ruang kerja, pergi ke **Pentadbir** > **Ruang Kerja** dan kemudian pilih **Panduan pemasangan**. 

## <a name="configure-the-sdk"></a>Konfigurasikan SDK

Setelah anda memuat turun SDK, anda boleh bekerja dengannya dalam Android Studio untuk mendayakan dan menentukan peristiwa. Terdapat dua cara untuk berbuat demikian:
### <a name="option-1-using-jitpack-recommended"></a>Pilihan 1: Menggunakan JitPack (disyorkan)
1. Tambahkan repositori JitPack pada akar `build.gradle` anda:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Tambahkan kebersandaran:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-using-download-link"></a>Pilihan 2: Menggunakan pautan muat turun
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

1. Tambahkan keizinan untuk rangkaian dan Internet dalam fail `AndroidManifest.xml` anda yang terletak di bawah folder `manifests`. 
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```
    
1. Sediakan cerapan penglibatan konfigurasi SDK melalui fail `AndroidManifest.xml` anda. 

## <a name="enable-auto-instrumentation"></a>Dayakan autopengalatan
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

1. Dayakan atau nyahdayakan autorekod peristiwa `View` dengan menetapkan medan `autoCapture` di atas kepada `true` atau `false`. Pada masa ini, peristiwa `Action` perlu ditambahkan secara manual.

1. (Pilihan) Konfigurasi lain termasuk menetapkan URL pengumpul titik tamat. Tetapan ini boleh ditambah di bawah metadata utama pengingesan dalam `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="implement-custom-events"></a>Melaksanakan peristiwa tersuai

Selepas anda memulakan SDK, anda boleh bekerja dengan peristiwa dan sifat dalam persekitaran `MainActivity`.

    
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

## <a name="set-user-details-for-your-event-optional"></a>Tetapkan butiran pengguna untuk peristiwa anda (pilihan)

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