---
title: Peranan dan keizinan
description: Gambaran keseluruhan peranan dan keizinan yang tersedia untuk ahli ruang kerja.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645548"
---
# <a name="roles-and-permissions"></a>Peranan dan keizinan

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ruang kerja ialah tempat anda menyimpan dan mengurus peristiwa dan laporan. Untuk mendapatkan maklumat lanjut, lihat [Cipta ruang kerja dan tambah ahli](create-workspace.md). 

Ruang kerja boleh termasuk peranan dan keizinan berikut:

- Peranan *Ahli* ialah pengguna yang boleh mengakses ruang kerja. Anda boleh menugaskan ahli ke ruang kerja anda dan mentakrifkan peranan dan keizinan mereka. 
- Peranan *Pentadbir* menguruskan ruang kerja dan persekitaran dan mengkonfigurasi cerapan penglibatan untuk pengguna lain. 
- Peranan *Penyumbang* menjurus ke arah penganalisis yang tidak perlu mengkonfigurasikan cerapan penglibatan tetapi mahu mencipta laporan, corong atau segmen mereka sendiri.

## <a name="permissions"></a>Keizinan
  
Jadual berikut mengenal pasti keizinan untuk setiap peranan. 

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
