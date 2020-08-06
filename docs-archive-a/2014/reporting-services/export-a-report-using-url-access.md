---
title: Esportare un report tramite l'accesso con URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- formats [Reporting Services], URL rendering
- URL access [Reporting Services], rendering formats
ms.assetid: 6a3b7fc3-3d91-4d12-8371-42ea12e74517
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 69f340855e37ffde49aec0af096c094a142659d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711755"
---
# <a name="export-a-report-using-url-access"></a><span data-ttu-id="5a6da-102">Esportare un report tramite l'accesso con URL</span><span class="sxs-lookup"><span data-stu-id="5a6da-102">Export a Report Using URL Access</span></span>
  <span data-ttu-id="5a6da-103">Facoltativamente, è possibile specificare il formato in cui eseguire il rendering di un report utilizzando il parametro *RS: Format* .</span><span class="sxs-lookup"><span data-stu-id="5a6da-103">You can optionally specify the format in which to render a report by using the *rs:Format* parameter.</span></span> <span data-ttu-id="5a6da-104">Ad esempio per ottenere una copia PDF di un report direttamente da un server di report in modalità nativa:</span><span class="sxs-lookup"><span data-stu-id="5a6da-104">For example, to get a PDF copy of a report directly from a native mode report server:</span></span>  
  
```  
http://myrshost/ReportServer?/myreport&rs:Format=PDF  
```  
  
 <span data-ttu-id="5a6da-105">Da un server di report in modalità integrata SharePoint:</span><span class="sxs-lookup"><span data-stu-id="5a6da-105">And, from a SharePoint integrated mode report server:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/myrereport.rdl&rs:Format=PDF  
```  
  
 <span data-ttu-id="5a6da-106">I valori validi per questo parametro sono basati sulle estensioni per il rendering di report installate nel server di report a cui si sta effettuando l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5a6da-106">Valid values for this parameter are based on the report rendering extensions that are installed on the report server being accessed.</span></span> <span data-ttu-id="5a6da-107">Le estensioni comuni sono HTML4.0, MHTML, IMAGE, EXCEL, WORD, CSV, PDF, XML e NULL.</span><span class="sxs-lookup"><span data-stu-id="5a6da-107">Common extensions are HTML4.0, MHTML, IMAGE, EXCEL, WORD, CSV, PDF, XML, and NULL.</span></span> <span data-ttu-id="5a6da-108">Se un'estensione per il rendering specificata non è installata nel server di report, il rendering del report non viene eseguito e un errore viene generato e visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="5a6da-108">If a specified rendering extension is not installed on the report server, the report is not rendered and an error is generated and displayed in the browser.</span></span>  
  
 <span data-ttu-id="5a6da-109">Se non si include il parametro *Format* come parte dell'URL, il server di report rileva il browser ed esegue il rendering del report nel formato HTML appropriato.</span><span class="sxs-lookup"><span data-stu-id="5a6da-109">If you do not include the *Format* parameter as part of the URL, the report server detects the browser and renders the report in the appropriate HTML format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a6da-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a6da-110">See Also</span></span>  
 <span data-ttu-id="5a6da-111">[Accesso con URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5a6da-111">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="5a6da-112">Riferimento ai parametri di accesso con URL</span><span class="sxs-lookup"><span data-stu-id="5a6da-112">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
