---
title: Gunakan akaun Gen2 anda sendiri Azure Data Lake Storage
author: mukeshpo
description: Ketahui tentang keperluan untuk menggunakan akaun anda sendiri Azure Data Lake Storage untuk menyimpan data Wawasan Pelanggan.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304392"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Gunakan akaun Gen2 anda sendiri Azure Data Lake Storage

Dynamics 365 Customer Insights memberi anda pilihan untuk menyimpan semua data anda dalam [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction). Dengan menyimpan data ke Data Lake Storage, anda bersetuju bahawa data akan dipindahkan ke dan disimpan di lokasi geografi yang sesuai untuk akaun storan Azure tersebut. Untuk maklumat lanjut, lihat [Pusat Amanah Microsoft](https://www.microsoft.com/trust-center).

Pentadbir dalam Wawasan Pelanggan boleh [mencipta persekitaran](create-environment.md) dan [menentukan opsyen](create-environment.md#step-2-configure-data-storage) storan data dalam proses.

## <a name="prerequisites"></a>Prasyarat

- Azure Data Lake Storage akaun mesti berada dalam rantau Azure yang sama yang anda pilih semasa mencipta persekitaran Wawasan Pelanggan. Untuk mengetahui rantau persekitaran, pergi ke **Sistem** > **Pentadbir** > **Perihal** dalam Wawasan Pelanggan.
- Akaun Penyimpanan Tasik Data mestilah Gen2. Akaun storan Azure Data Lake Gen1 tidak disokong.
- Akaun Penyimpanan Tasik Data mesti didayakan [ruang](/azure/storage/blobs/data-lake-storage-namespace) nama hierarki.
- Bekas yang `customerinsights` dinamakan perlu wujud pada akaun simpanan. Ciptanya sebelum anda menggunakan Storan Tasik Data anda sendiri dalam Wawasan Pelanggan.
- Pentadbir yang menyediakan persekitaran Wawasan Pelanggan memerlukan peranan Penyumbang Data Blob Storan atau Pemilik Data Blob Storan pada akaun storan atau `customerinsights` bekas. Untuk maklumat lanjut tentang memperuntukkan kebenaran dalam akaun storan, lihat [Mencipta akaun](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) storan.

## <a name="connect-customer-insights-with-your-storage-account"></a>Sambungkan Wawasan Pelanggan dengan akaun storan anda

Apabila anda membuat persekitaran baru, pastikan akaun Penyimpanan Tasik Data wujud dan semua prasyarat dipenuhi.

1. **Dalam langkah Penyimpanan data** semasa penciptaan persekitaran, tetapkan **Simpan data** output kepada **Azure Data Lake Storage Gen2**.
1. Pilih cara **menyambungkan storan** anda. Anda boleh memilih antara opsyen berasaskan sumber dan opsyen berasaskan langganan untuk pengesahan. Untuk maklumat lanjut, lihat [Menyambung ke Azure Data Lake Storage akaun menggunakan Azure Service Principal](connect-service-principal.md).
   - Untuk **langganan** Azure, pilih **langganan**, **kumpulan** Sumber dan **akaun** Storan yang mengandungi `customerinsights` bekas.
   - Untuk **kunci** Akaun, berikan **nama** Akaun dan **kunci** Akaun untuk akaun Penyimpanan Tasik Data. Menggunakan kaedah pengesahan ini menunjukkan bahawa anda dimaklumkan jika organisasi anda memutarkan kekunci. Anda mesti [mengemas kini konfigurasi](manage-environments.md#edit-an-existing-environment) persekitaran dengan kunci baharu apabila ia diputar.
1. Pilih jika anda ingin menggunakan Azure Private Link untuk menyambung ke akaun storan dan [mencipta sambungan ke Pautan](security-overview.md#set-up-an-azure-private-link) Peribadi.

Apabila proses sistem seperti pengingesan data selesai, sistem mencipta folder yang sepadan dalam akaun storan. Fail data dan fail model.json dicipta dan ditambah pada folder berdasarkan nama proses.

Jika anda mencipta berbilang persekitaran Customer Insights dan memilih untuk menyimpan entiti output daripada persekitaran tersebut ke akaun storan anda, Customer Insights mencipta folder berasingan untuk setiap persekitaran dengan `ci_environmentID` di dalam bekas.
