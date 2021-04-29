---
title: Kerja dengan API
description: Gunakan API dan fahami pengehadan.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 59161456914df84d7e72402ed1f5faf70a5119ba
ms.sourcegitcommit: a39e00a50ad3eda820fd756c5611081f0ca04662
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/09/2021
ms.locfileid: "5873673"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="93b1c-103">Gunakan Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="93b1c-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="93b1c-104">Dynamics 365 Customer Insights menyediakan API untuk membina aplikasi anda sendiri berdasarkan data anda dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="93b1c-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93b1c-105">Butiran API ini, disenaraikan pada [rujukan Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="93b1c-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="93b1c-106">Ia termasuk maklumat tambahan mengenai operasi, parameter dan respons.</span><span class="sxs-lookup"><span data-stu-id="93b1c-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="93b1c-107">Artikel ini membimbing anda untuk mengakses Customer Insights API, mencipta Pendaftaran Aplikasi Azure dan membantu anda bermula dengan pustaka klien yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="93b1c-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="93b1c-108">Mula mencuba Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="93b1c-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="93b1c-109">[Daftar Masuk](https://home.ci.ai.dynamics.com) ke Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="93b1c-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="93b1c-110">Jika anda tidak mempunyai langganan lagi, [daftar untuk percubaan Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="93b1c-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="93b1c-111">Untuk mendayakan API pada persekitaran Customer Insights anda, pergi ke **Pentadbir** > **Keizinan**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="93b1c-112">Anda memerlukan keizinan pentadbir untuk berbuat demikian.</span><span class="sxs-lookup"><span data-stu-id="93b1c-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="93b1c-113">Pergi ke tab **API** dan pilih butang **Daya**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="93b1c-114">Mendayakan API mencipta kunci langganan utama dan sekunder untuk tika anda yang akan digunakan dalam permintaan API.</span><span class="sxs-lookup"><span data-stu-id="93b1c-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="93b1c-115">Anda boleh menjana semula kunci dengan memilih **Jana semula utama** atau **Jana semula sekunder** pada **Pentadbir** > **Keizinan** > **API**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Dayakan Customer Insights API":::

1. <span data-ttu-id="93b1c-117">Pilih **Terokai API kami** untuk [mencuba API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="93b1c-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="93b1c-118">Pilih operasi API dan pilih **Cuba**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="93b1c-119">Dalam anak tetingkap sisi, tetapkan nilai dalam menu juntai bawah **Pengesahan** untuk **tersirat**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="93b1c-120">Pengepala `Authorization` mendapat dengan token pembawa yang ditambah.</span><span class="sxs-lookup"><span data-stu-id="93b1c-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="93b1c-121">Kunci langganan anda akan diisi secara automatik.</span><span class="sxs-lookup"><span data-stu-id="93b1c-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="93b1c-122">Secara alternatif, tambah semua parameter pertanyaan yang perlu.</span><span class="sxs-lookup"><span data-stu-id="93b1c-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="93b1c-123">Tatal ke bahagian bawah tetingkap sisi dan pilih **Hantar**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="93b1c-124">Respons HTTP tidak lama lagi akan muncul di bawah.</span><span class="sxs-lookup"><span data-stu-id="93b1c-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="Gif animasi menunjukkan cara memilih ujian API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="93b1c-126">Cipta pendaftaran aplikasi baharu dalam portal Azure</span><span class="sxs-lookup"><span data-stu-id="93b1c-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="93b1c-127">Langkah ini membantu anda mula menggunakan Customer Insights API dalam aplikasi Azure menggunakan keizinan yang diwakilkan.</span><span class="sxs-lookup"><span data-stu-id="93b1c-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="93b1c-128">Pastikan untuk melengkapkan [bahagian Bermula](#get-started-trying-the-customer-insights-apis) terlebih dahulu.</span><span class="sxs-lookup"><span data-stu-id="93b1c-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="93b1c-129">Daftar masuk ke [portal Azure](https://portal.azure.com) dengan akaun yang boleh mengakses data Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="93b1c-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="93b1c-130">Di sebelah kiri, pilih **Pendaftaran aplikasi**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="93b1c-131">Pilih **Pendaftaran baharu**, berikan nama aplikasi dan pilih jenis akaun.</span><span class="sxs-lookup"><span data-stu-id="93b1c-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="93b1c-132">Secara alternatif, tambah URL hala semula.</span><span class="sxs-lookup"><span data-stu-id="93b1c-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="93b1c-133">http://localhost adalah mencukupi untuk membangunkan aplikasi pada komputer tempatan anda.</span><span class="sxs-lookup"><span data-stu-id="93b1c-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="93b1c-134">Pada pendaftaran Aplikasi baharu anda, pergi ke **Keizinan API**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Gif animasi untuk menetapkan keizinan API dalam pendaftaran aplikasi.":::

1. <span data-ttu-id="93b1c-136">Pilih **Tambah keizinan** dan pilih **Customer Insights** dalam tetingkap sisi.</span><span class="sxs-lookup"><span data-stu-id="93b1c-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="93b1c-137">Untuk **Jenis keizinan**, pilih **Keizinan yang diwakilkan** dan pilih keizinan **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="93b1c-138">Pilih **Tambah keizinan**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-138">Select **Add permissions**.</span></span> <span data-ttu-id="93b1c-139">Jika anda perlu mengakses API tanpa mendaftar masuk pengguna, semak bahagian [Keizinan aplikasi pelayan ke pelayan](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="93b1c-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="93b1c-140">Pilih **Berikan keizinan pentadbir untuk...** untuk melengkapkan pendaftaran aplikasi.</span><span class="sxs-lookup"><span data-stu-id="93b1c-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="93b1c-141">Anda boleh menggunakan Aplikasi/ID Klien untuk pendaftaran aplikasi ini dengan Pustaka Pengesahan Microsoft (MSAL) untuk mendapatkan token pembawa untuk menghantar dengan permintaan anda kepada API.</span><span class="sxs-lookup"><span data-stu-id="93b1c-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Gif animasi untuk memberi persetujuan pentadbir.":::

<span data-ttu-id="93b1c-143">Untuk mendapatkan maklumat lanjut tentang MSAL, lihat [Gambaran Keseluruhan Pustaka Pengesahan Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="93b1c-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="93b1c-144">Untuk mendapatkan maklumat lanjut tentang pendaftaran aplikasi dalam Azure, lihat [Pengalaman pendaftaran aplikasi portal Azure yang baharu](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="93b1c-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="93b1c-145">Untuk mendapatkan maklumat mengenai penggunaan API pustaka klien kami, lihat [Pustaka klien Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="93b1c-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="93b1c-146">Keizinan aplikasi pelayan ke pelayan</span><span class="sxs-lookup"><span data-stu-id="93b1c-146">Server-to-server application permissions</span></span>

<span data-ttu-id="93b1c-147">[Bahagian pendaftaran aplikasi](#create-a-new-app-registration-in-the-azure-portal) menggariskan cara untuk mendaftar aplikasi yang memerlukan pengguna mendaftar masuk untuk pengesahan.</span><span class="sxs-lookup"><span data-stu-id="93b1c-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="93b1c-148">Ketahui cara untuk mencipta pendaftaran aplikasi yang tidak memerlukan interaksi pengguna dan boleh dijalankan pada pelayan.</span><span class="sxs-lookup"><span data-stu-id="93b1c-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="93b1c-149">Pada pendaftaran Aplikasi anda dalam portal Azure, pergi ke **Keizinan API**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="93b1c-150">Pilih **Tambah keizinan** dan pilih **Customer Insights** dalam tetingkap sisi.</span><span class="sxs-lookup"><span data-stu-id="93b1c-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="93b1c-151">Untuk **Jenis keizinan**, pilih **Keizinan aplikasi** dan pilih keizinan **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="93b1c-152">Pilih **Tambah keizinan**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="93b1c-153">Untuk memberikan keizinan pentadbir pada keizinan Aplikasi ini, anda perlu menambah prinsipal Perkhidmatan.</span><span class="sxs-lookup"><span data-stu-id="93b1c-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="93b1c-154">Pasang modul Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="93b1c-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="93b1c-155">Sambung ke akaun AD anda: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="93b1c-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="93b1c-156">Anda boleh mencari ID penyewa anda di **Gambaran keseluruhan** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="93b1c-157">Jalankan perintah berikut untuk menambahkan Prinsipal Perkhidmatan Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Parameter AppId berkaitan dengan aplikasi Customer Insights API.</span><span class="sxs-lookup"><span data-stu-id="93b1c-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Sampel prinsipal perkhidmatan":::

1. <span data-ttu-id="93b1c-159">Kembali ke **Keizinan API** untuk pendaftaran aplikasi anda.</span><span class="sxs-lookup"><span data-stu-id="93b1c-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="93b1c-160">Pilih **Berikan keizinan pentadbir untuk...** untuk melengkapkan pendaftaran aplikasi.</span><span class="sxs-lookup"><span data-stu-id="93b1c-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Gif animasi untuk memberi persetujuan pentadbir.":::

1. <span data-ttu-id="93b1c-162">Untuk menyimpulkan, kami perlu menambah nama pendaftaran aplikasi sebagai pengguna dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="93b1c-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="93b1c-163">Buka Customer Insights, pergi ke **Pentadbir** > **Keizinan** dan pilih **Tambah pengguna**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="93b1c-164">Cari nama pendaftaran aplikasi anda, pilih nama daripada hasil carian dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="93b1c-165">Pustaka klien Customer Insights</span><span class="sxs-lookup"><span data-stu-id="93b1c-165">Customer Insights client libraries</span></span>

<span data-ttu-id="93b1c-166">Bahagian ini membantu anda mula menggunakan pustaka klien yang tersedia untuk Customer Insights API.</span><span class="sxs-lookup"><span data-stu-id="93b1c-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="93b1c-167">Semua kod sumber pustaka dan aplikasi sampel boleh ditemui pada [halaman Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="93b1c-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="93b1c-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="93b1c-168">C# NuGet</span></span>

<span data-ttu-id="93b1c-169">Ketahui cara untuk mula menggunakan pustaka klien C# daripada NuGet.org. Untuk mendapatkan maklumat lanjut tentang pakej NuGet, lihat [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="93b1c-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="93b1c-170">Buat masa ini, pakej ini mensasarkan rangka kerja netstandard2.0 dan netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="93b1c-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="93b1c-171">Tambah pustaka klien C# untuk projek C#</span><span class="sxs-lookup"><span data-stu-id="93b1c-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="93b1c-172">Dalam Visual Studio, buka **Pengurus Pakej NuGet** untuk projek anda.</span><span class="sxs-lookup"><span data-stu-id="93b1c-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="93b1c-173">Cari **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="93b1c-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="93b1c-174">Pilih **Pasang** untuk menambah pakej ke projek.</span><span class="sxs-lookup"><span data-stu-id="93b1c-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="93b1c-175">Secara alternatif, jalankan perintah ini dalam **Konsol Pengurus Pakej NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="93b1c-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Tambah pakej NuGet ke projek Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="93b1c-177">Gunakan pustaka klien C#</span><span class="sxs-lookup"><span data-stu-id="93b1c-177">Use the C# client library</span></span>

1. <span data-ttu-id="93b1c-178">Gunakan [Pustaka Pengesahan Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) untuk memperoleh `AccessToken` menggunakan [pendaftaran aplikasi Azure](#create-a-new-app-registration-in-the-azure-portal) anda yang sedia ada.</span><span class="sxs-lookup"><span data-stu-id="93b1c-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="93b1c-179">Selepas berjaya mengesahkan dan memperolehi token, bina `HttpClient` yang baharu atau gunakan yang sedia ada dengan **"Pengesahan" DefaultRequestHeaders** tambahan ditetapkan kepada **<access token> Pembawa** dan **Ocp-Apim-Subscription-Key** ditetapkan kepada [**kunci langganan** daripada persekitaran Customer Insights anda](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="93b1c-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="93b1c-180">Tetapkan semula pengepala **Pengesahan** apabila sesuai.</span><span class="sxs-lookup"><span data-stu-id="93b1c-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="93b1c-181">Contohnya, apabila token tamat tempoh.</span><span class="sxs-lookup"><span data-stu-id="93b1c-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="93b1c-182">Hantar `HttpClient` ini ke dalam pembinaan klien `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="93b1c-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Sampel httpclient":::

1. <span data-ttu-id="93b1c-184">Buat panggilan dengan klien ke "kaedah lanjutan", contohnya, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="93b1c-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="93b1c-185">Jika akses kepada `Microsoft.Rest.HttpOperationResponse` dasar diutamakan, gunakan "kaedah mesej http", contohnya, `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="93b1c-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="93b1c-186">Respons mungkin akan menjadi jenis `object` kerana kaedah boleh kembali pelbagai jenis (contohnya, `IList<InstanceInfo>` dan `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="93b1c-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="93b1c-187">Untuk menyemak jenis pengembalian, anda boleh menyiarkan objek dengan selamat ke dalam jenis respons yang ditentukan pada [halaman butiran API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) untuk operasi tersebut.</span><span class="sxs-lookup"><span data-stu-id="93b1c-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="93b1c-188">Jika maklumat lanjut mengenai permintaan diperlukan, gunakan **kaedah mesej http** untuk mengakses objek respons mentah.</span><span class="sxs-lookup"><span data-stu-id="93b1c-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="93b1c-189">Pakej NodeJS</span><span class="sxs-lookup"><span data-stu-id="93b1c-189">NodeJS package</span></span>

<span data-ttu-id="93b1c-190">Gunakan pustaka klien NodeJS yang tersedia melalui NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="93b1c-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="93b1c-191">Pakej Python</span><span class="sxs-lookup"><span data-stu-id="93b1c-191">Python package</span></span>

<span data-ttu-id="93b1c-192">Gunakan pustaka klien Python yang tersedia melalui PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="93b1c-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
