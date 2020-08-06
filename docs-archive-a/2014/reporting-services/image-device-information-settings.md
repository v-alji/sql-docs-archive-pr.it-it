---
title: Impostazioni relative alle informazioni sul dispositivo di acquisizione immagini | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- images [Reporting Services], rendering
- device information settings [Reporting Services], IMAGE rendering
ms.assetid: edad9498-69f7-4726-8699-fa615f704dff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4a177b114e331a817427fbd2ce703afa21390a9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726676"
---
# <a name="image-device-information-settings"></a>Impostazioni relative alle informazioni sul dispositivo di acquisizione immagini
  Nella tabella seguente sono elencate le impostazioni relative alle informazioni sul dispositivo per il rendering nel formato IMAGE.  
  
|Impostazione|valore|  
|-------------|-----------|  
|**Colonne**|Numero di colonne da impostare per il report. Questo valore ha la priorità sulle impostazioni originali del report.|  
|**ColumnSpacing**|Spaziatura delle colonne da impostare per il report. Questo valore ha la priorità sulle impostazioni originali del report.|  
|`DpiX`|Risoluzione orizzontale dell'immagine di output. Il valore predefinito è **96**. Si applica `BMP` ai `GIF` formati di output,, `PNG` e `TIFF` .|  
|`DpiY`|Risoluzione verticale dell'immagine di output. Il valore predefinito è **96**. Si applica `BMP` ai `GIF` formati di output,, `PNG` e `TIFF` .|  
|**EndPage**|Ultima pagina del report di cui eseguire il rendering. Il valore predefinito è il valore di `StartPage`.|  
|**MarginBottom**|Valore in pollici del margine inferiore da impostare per il report. È necessario includere un numero intero o un valore decimale seguito da "in", ad esempio `1in`. Questo valore ha la priorità sulle impostazioni originali del report.|  
|**MarginLeft**|Valore in pollici del margine sinistro da impostare per il report. È necessario includere un numero intero o un valore decimale seguito da "in", ad esempio `1in`. Questo valore ha la priorità sulle impostazioni originali del report.|  
|**MarginRight**|Valore in pollici del margine destro da impostare per il report. È necessario includere un numero intero o un valore decimale seguito da "in", ad esempio `1in`. Questo valore ha la priorità sulle impostazioni originali del report.|  
|**MarginTop**|Valore in pollici del margine superiore da impostare per il report. È necessario includere un numero intero o un valore decimale seguito da "in", ad esempio `1in`. Questo valore ha la priorità sulle impostazioni originali del report.|  
|**OutputFormat**|Uno dei formati di output supportati [!INCLUDE[ndptecgdiexpanded](../includes/ndptecgdiexpanded-md.md)] ([!INCLUDE[ndptecgdi](../includes/ndptecgdi-md.md)]): `BMP`, `EMF`, `GIF`, `JPEG`, `PNG` o `TIFF`.|  
|**PageHeight**|Altezza di pagina in pollici da impostare per il report. È necessario includere un numero intero o un valore decimale seguito da "in", ad esempio `11in`. Questo valore ha la priorità sulle impostazioni originali del report.|  
|**PageWidth**|Larghezza di pagina in pollici da impostare per il report. È necessario includere un numero intero o un valore decimale seguito da "in", ad esempio `8.5in`. Questo valore ha la priorità sulle impostazioni originali del report.|  
|**PrintDpiX**|Risoluzione orizzontale dell'immagine di output. Il valore predefinito è `300`. Si applica al formato di output Enhanced MetaFile ( `EMF` ).|  
|**PrintDpiY**|Risoluzione verticale dell'immagine di output. Il valore predefinito è `300`. Si applica al formato di output Enhanced MetaFile ( `EMF` ).|  
|`StartPage`|Prima pagina del report di cui eseguire il rendering. Il valore `0` indica che viene eseguito il rendering di tutte le pagine. Il valore predefinito è `1`.|  
  
## <a name="see-also"></a>Vedere anche  
 [Passaggio delle impostazioni delle informazioni sul dispositivo alle estensioni per il rendering](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md)   
 [Personalizzare i parametri di estensione per il rendering in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [Riferimento tecnico &#40;SSRS&#41;](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
