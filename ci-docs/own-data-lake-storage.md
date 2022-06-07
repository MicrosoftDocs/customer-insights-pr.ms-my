---
title: Gunakan akaun Gen2 anda sendiri Azure Data Lake Storage
author: mukeshpo
description: Ketahui tentang keperluan untuk menggunakan akaun anda sendiri Azure Data Lake Storage untuk menyimpan data Wawasan Pelanggan.
ms.author: mukeshpo
ms.date: 05/30/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 9fcd7645e34bf310ac3a1b98a0dd9a60598b19dc
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833951"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Gunakan akaun Gen2 anda sendiri Azure Data Lake Storage

Dynamics 365 Customer Insights memberi anda pilihan untuk menyimpan semua data anda dalam [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Dengan menyimpan data ke Data Lake Storage, anda bersetuju bahawa data akan dipindahkan dan disimpan di lokasi geografi yang sesuai untuk akaun storan Azure tersebut. Untuk maklumat lanjut, lihat [Pusat Amanah Microsoft](https://www.microsoft.com/trust-center).

Pentadbir dalam Wawasan Pelanggan boleh [mencipta persekitaran](create-environment.md) dan [menentukan pilihan](create-environment.md#step-2-configure-data-storage) storan data dalam proses tersebut.

## <a name="prerequisites-to-use-your-storage-account"></a>Prasyarat untuk menggunakan akaun storan anda

- Azure Data Lake Storage akaun mesti berada dalam rantau Azure yang sama yang anda pilih semasa mencipta persekitaran Wawasan Pelanggan. Anda boleh menyemak kawasan persekitaran Wawasan Pelanggan di bawah **Sistem** > **Pentadbir** > **Perihal**.
- Storan Tasik Data mestilah Gen2 dan mempunyai [ruang nama hierarki yang didayakan](/azure/storage/blobs/create-data-lake-storage-account). Akaun storan Gen1 tidak disokong.
- Bekas yang dinamakan `customerinsights` mesti wujud pada akaun storan. Anda perlu menciptanya sebelum anda menggunakan Storan Tasik Data anda sendiri dalam Wawasan Pelanggan. Pentadbir yang menyediakan persekitaran Wawasan Pelanggan memerlukan peranan Penyumbang Data Blob Storan atau Pemilik Data Blob Storan pada akaun storan atau `customerinsights` bekas. Untuk maklumat lanjut tentang memperuntukkan keizinan dalam akaun storan, lihat [Mencipta akaun](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) storan.

## <a name="connect-customer-insights-with-your-storage-account"></a>Sambungkan Wawasan Pelanggan dengan akaun storan anda

Apabila anda mencipta persekitaran baharu, pastikan akaun Storan Tasik Data wujud dan semua prasyarat dipenuhi.

1. **Dalam langkah storan data** semasa penciptaan persekitaran, setkan **Simpan data** output kepada **Azure Data Lake Storage Gen2**.
1. Pilih cara **Menyambungkan storan** anda. Anda boleh memilih antara pilihan berasaskan sumber dan pilihan berasaskan langganan untuk pengesahan. Untuk maklumat lanjut, lihat [Menyambung ke Azure Data Lake Storage akaun menggunakan Azure Service Principal](connect-service-principal.md).
   - Untuk **langganan** Azure, pilih **akaun** Langganan **,** kumpulan **Sumber dan** Storan yang mengandungi `customerinsights` bekas.
   - Untuk **kunci** Akaun, berikan **nama** Akaun dan **kunci** Akaun untuk akaun Storan Data Lake. Menggunakan kaedah pengesahan ini menunjukkan bahawa anda dimaklumkan jika organisasi anda memutarkan kekunci. Anda mesti [mengemas kini konfigurasi](manage-environments.md#edit-an-existing-environment) persekitaran dengan kekunci baru apabila ia diputar.

Apabila proses sistem seperti pengambilan data selesai, sistem mencipta folder yang sepadan dalam akaun storan. Fail data dan fail *model.json* dicipta dan ditambah ke folder berdasarkan nama proses.

Jika anda mencipta berbilang persekitaran Customer Insights dan memilih untuk menyimpan entiti output daripada persekitaran tersebut ke akaun storan anda, Customer Insights mencipta folder berasingan untuk setiap persekitaran dengan `ci_environmentID` di dalam bekas.
