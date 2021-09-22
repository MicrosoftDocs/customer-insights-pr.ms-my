---
title: Peranan dan keizinan
description: Gambaran keseluruhan peranan dan keizinan yang tersedia untuk ahli ruang kerja.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036704"
---
# <a name="roles-and-permissions"></a>Peranan dan keizinan

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ruang kerja ialah cara anda menyimpan dan mengurus peristiwa dan laporan. Ahli ialah pengguna yang boleh mengakses ruang kerja. Anda boleh menugaskan ahli ke ruang kerja anda dan mentakrifkan peranan dan keizinan mereka. Peranan pentadbir menguruskan ruang kerja dan persekitaran dan mengkonfigurasi cerapan penglibatan untuk pengguna lain. Peranan penyumbang menjurus ke arah penganalisis yang tidak perlu mengkonfigurasi cerapan penglibatan tetapi mahu mencipta laporan, corong atau segmen mereka sendiri.

## <a name="permissions"></a>Keizinan
  
Carta berikut mengenal pasti keizinan untuk setiap peranan. 

| Keizinan | Pentadbir persekitaran | Pentadbir ruang kerja | Penyumbang persekitaran | Penyumbang ruang kerja | 
|--|--|--|--|--|
| Cipta persekitaran (pencipta secara automatik menjadi pentadbir persekitaran) | X* | X* | X* | X* |  
| Konfigurasikan persekitaran (ahli persekitaran, padam persekitaran) | X |  |  |  |  
| Cipta ruang kerja | X |  |  |  |  
| Konfigurasikan ruang kerja (ahli ruang kerja, padam ruang kerja) | X | X |  |  |  
| Konfigurasikan peristiwa dan peristiwa diperhalus | X | X | |  |  
| Lihat peristiwa ruang kerja dan acara diperhalus | X | X | |  |  
| Lihat sumber ruang kerja (laporan, segmen dan metrik)| X | X | X | X |  
| Cipta laporan dan corong tersuai | X | X | X | X |  
| Cipta metrik asas dan dimensi| X | X |  |  |  
| Cipta segmen| X | X | X | X |  

*Hanya boleh mencipta persekitaran percubaan dalam pratonton. 

## <a name="add-members"></a>Tambah ahli

Anda boleh menambah dan mengalih keluar ahli daripada ruang kerja dan persekitaran. Untuk maklumat lanjut, lihat [Persekitaran dan ruang kerja](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
