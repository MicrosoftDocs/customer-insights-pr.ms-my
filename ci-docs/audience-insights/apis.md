---
title: Kerja dengan API
description: Gunakan API dan fahami pengehadan.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304753"
---
# <a name="work-with-customer-insights-apis"></a>Gunakan Customer Insights API

Dynamics 365 Customer Insights menyediakan API untuk membina aplikasi anda sendiri berdasarkan data anda dalam Customer Insights.

> [!IMPORTANT]
> Butiran API ini, disenaraikan pada [rujukan API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Ia termasuk maklumat tambahan mengenai operasi, parameter dan respons.

Artikel ini menerangkan cara mengakses API Customer Insights, mencipta Pendaftaran Aplikasi Azure dan bermula dengan pustaka klien yang tersedia.

## <a name="get-started-trying-the-customer-insights-apis"></a>Mula mencuba Customer Insights API

1. [Daftar Masuk](https://home.ci.ai.dynamics.com) ke Customer Insights. Jika anda tidak mempunyai langganan lagi, [daftar untuk percubaan Customer Insights](https://aka.ms/tryci).

1. Untuk mendayakan API pada persekitaran Customer Insights anda, pergi ke **Pentadbir** > **Keizinan**. Anda memerlukan keizinan pentadbir untuk berbuat demikian.

1. Pergi ke tab **API** dan pilih butang **Daya**.    
 
   Mendayakan API mencipta kunci langganan utama dan sekunder untuk tika anda yang akan digunakan dalam permintaan API. Anda boleh menjana semula kunci dengan memilih **Jana semula utama** atau **Jana semula sekunder** pada **Pentadbir** > **Keizinan** > **API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Dayakan Customer Insights API":::

1. Pilih **Terokai API kami** untuk [mencuba API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Pilih operasi API dan pilih **Cuba**.

1. Dalam anak tetingkap sisi, tetapkan nilai dalam menu juntai bawah **Kebenaran** untuk **tersirat**. Pengepala `Authorization` akan ditambahkan dengan token pembawa. Kunci langganan anda akan diisi secara automatik.
  
1. Secara alternatif, tambah semua parameter pertanyaan yang perlu.

1. Tatal ke bahagian bawah tetingkap sisi dan pilih **Hantar**.

Respons HTTP tidak lama lagi akan muncul di bawah.

   :::image type="content" source="media/try-apis.gif" alt-text="Cara menguji API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Cipta pendaftaran aplikasi baharu dalam portal Azure

Langkah-langkah ini membantu anda bermula dengan menggunakan API Customer Insights dalam aplikasi Azure menggunakan keizinan yang ditugaskan. Pastikan untuk melengkapkan [bahagian Bermula](#get-started-trying-the-customer-insights-apis) terlebih dahulu.

1. Daftar masuk ke [portal Azure](https://portal.azure.com) dengan akaun yang boleh mengakses data Customer Insights.

1. Di sebelah kiri, pilih **Pendaftaran aplikasi**.

1. Pilih **Pendaftaran baharu**, berikan nama aplikasi dan pilih jenis akaun.
 
   Secara alternatif, tambah URL hala semula. http://localhost adalah mencukupi untuk membangunkan aplikasi pada komputer tempatan anda.

1. Pada pendaftaran Aplikasi baharu anda, pergi ke **Keizinan API**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Cara menetapkan keizinan API dalam pendaftaran Aplikasi.":::

1. Pilih **Tambah keizinan** dan pilih **Customer Insights** dalam tetingkap sisi.

1. Untuk **Jenis keizinan**, pilih **Keizinan yang ditugaskan** dan kemudian pilih keizinan **user_impersonation**.

1. Pilih **Tambah keizinan**. Jika anda perlu mengakses API tanpa mendaftar masuk pengguna, semak bahagian [Keizinan aplikasi pelayan ke pelayan](#server-to-server-application-permissions).

1. Pilih **Berikan keizinan pentadbir untuk...** untuk melengkapkan pendaftaran aplikasi.

Anda boleh menggunakan Aplikasi/ID Klien untuk pendaftaran aplikasi ini dengan Pustaka Pengesahan Microsoft (MSAL) untuk mendapatkan token pembawa untuk menghantar dengan permintaan anda kepada API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Cara memberikan persetujuan pentadbir.":::

Untuk mendapatkan maklumat lanjut tentang MSAL, lihat [Gambaran Keseluruhan Pustaka Pengesahan Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Untuk mendapatkan maklumat lanjut tentang pendaftaran aplikasi dalam Azure, lihat [Daftar aplikasi](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Untuk mendapatkan maklumat tentang penggunaan API dalam pustaka klien kami, lihat [Pustaka klien Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Keizinan aplikasi pelayan ke pelayan

[Bahagian pendaftaran aplikasi](#create-a-new-app-registration-in-the-azure-portal) menggariskan cara untuk mendaftar aplikasi yang memerlukan pengguna mendaftar masuk untuk pengesahan. Ketahui cara untuk mencipta pendaftaran aplikasi yang tidak memerlukan interaksi pengguna dan boleh dijalankan pada pelayan.

1. Pada pendaftaran Aplikasi anda dalam portal Azure, pergi ke **Keizinan API**.

1. Pilih **Tambah keizinan**. 

1. Pilih tab **API organisasi saya menggunakan** dan pilih **Dynamics 365 AI untuk Customer Insights** daripada senarai. 

1. Untuk **Jenis keizinan**, pilih **Keizinan aplikasi** dan kemudian pilih keizinan **CustomerInsights.Api.All**.

1. Pilih **Tambah keizinan**.

1. Kembali ke **Keizinan API** untuk pendaftaran aplikasi anda.

1. Pilih **Berikan keizinan pentadbir untuk...** untuk melengkapkan pendaftaran aplikasi.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Cara memberikan persetujuan pentadbir.":::

1. Untuk menyimpulkan, kami perlu menambah nama pendaftaran aplikasi sebagai pengguna dalam Customer Insights.  
   
   Buka Customer Insights, pergi ke **Pentadbir** > **Keizinan** dan pilih **Tambah pengguna**.

1. Cari nama pendaftaran aplikasi anda, pilih nama daripada hasil carian dan pilih **Simpan**.

## <a name="customer-insights-client-libraries"></a>Pustaka klien Customer Insights

Bahagian ini membantu anda mula menggunakan pustaka klien yang tersedia untuk Customer Insights API. Semua kod sumber pustaka dan aplikasi sampel boleh ditemui pada [halaman Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Ketahui cara untuk mula menggunakan pustaka klien C# daripada NuGet.org. Untuk mendapatkan maklumat lanjut tentang pakej NuGet, lihat [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Buat masa ini, pakej ini mensasarkan rangka kerja netstandard2.0 dan netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Tambah pustaka klien C# untuk projek C#

1. Dalam Visual Studio, buka **Pengurus Pakej NuGet** untuk projek anda.

1. Cari **Microsoft.Dynamics.CustomerInsights.Api**.

1. Pilih **Pasang** untuk menambah pakej ke projek.
 
   Secara alternatif, jalankan perintah ini dalam **Konsol Pengurus Pakej NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Tambah pakej NuGet ke projek Visual Studio":::

#### <a name="use-the-c-client-library"></a>Gunakan pustaka klien C#

1. Gunakan [Pustaka Pengesahan Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) untuk memperoleh `AccessToken` menggunakan [pendaftaran aplikasi Azure](#create-a-new-app-registration-in-the-azure-portal) anda yang sedia ada.

1. Selepas berjaya mengesahkan dan memperolehi token, bina `HttpClient` yang baharu atau gunakan yang sedia ada dengan **"Pengesahan" DefaultRequestHeaders** tambahan ditetapkan kepada **<access token> Pembawa** dan **Ocp-Apim-Subscription-Key** ditetapkan kepada [**kunci langganan** daripada persekitaran Customer Insights anda](#get-started-trying-the-customer-insights-apis).   
 
   Tetapkan semula pengepala **Pengesahan** apabila sesuai. Contohnya, apabila token tamat tempoh.

1. Hantar `HttpClient` ini ke dalam pembinaan klien `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Sampel httpclient":::

1. Buat panggilan dengan klien pada "kaedah lanjutan"—contohnya, `GetAllInstancesAsync`. Jika akses kepada dasar `Microsoft.Rest.HttpOperationResponse` diutamakan, gunakan "kaedah mesej http"—contohnya, `GetAllInstancesWithHttpMessagesAsync`.

1. Respons mungkin akan menjadi jenis `object` kerana kaedah boleh kembali pelbagai jenis (contohnya, `IList<InstanceInfo>` dan `ApiErrorResult`). Untuk menyemak jenis pengembalian, anda boleh menyiarkan objek dengan selamat ke dalam jenis respons yang ditentukan pada [halaman butiran API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) untuk operasi tersebut.    
   
   Jika maklumat lanjut mengenai permintaan diperlukan, gunakan **kaedah mesej http** untuk mengakses objek respons mentah.

### <a name="nodejs-package"></a>Pakej NodeJS

Gunakan pustaka klien NodeJS yang tersedia melalui NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Pakej Python

Gunakan pustaka klien Python yang tersedia melalui PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
