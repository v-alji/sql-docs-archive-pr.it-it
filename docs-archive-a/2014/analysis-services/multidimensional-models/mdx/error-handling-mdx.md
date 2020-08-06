---
title: Gestione degli errori (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [MDX], exceptions
- exceptions [MDX]
ms.assetid: bc6ff0af-9fe6-44d6-bc3c-801d71ea41a9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 357194b9f789fdeacfb65ce3c894d4747867eafb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635828"
---
# <a name="error-handling-mdx"></a><span data-ttu-id="1829a-102">Gestione degli errori (MDX)</span><span class="sxs-lookup"><span data-stu-id="1829a-102">Error Handling (MDX)</span></span>
  <span data-ttu-id="1829a-103">Ogni cubo può controllare la modalità con cui verranno gestiti gli errori di uno script MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="1829a-103">Each cube can control how errors within a Multidimensional Expressions (MDX) script are handled.</span></span> <span data-ttu-id="1829a-104">Per la gestione degli errori viene utilizzato l'enumeratore `ScriptErrorHandlingMode`.</span><span class="sxs-lookup"><span data-stu-id="1829a-104">Error handling is done through the `ScriptErrorHandlingMode` enumerator.</span></span> <span data-ttu-id="1829a-105">I possibili valori dell'enumeratore sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="1829a-105">The possible values for this enumerator are:</span></span>  
  
 `IgnoreNone`  
 <span data-ttu-id="1829a-106">Determina la generazione di un errore da parte del server quando viene [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] rilevato un errore nello script MDX.</span><span class="sxs-lookup"><span data-stu-id="1829a-106">Causes the server to raise an error when [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] finds any error in the MDX script.</span></span>  
  
 `IgnoreAll`  
 <span data-ttu-id="1829a-107">Induce il server a ignorare tutti i comandi dello script MDX che contengono un errore, compresi gli errori di sintassi e gli errori di risoluzione dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1829a-107">Causes the server to ignore all commands in the MDX script that contain an error, including syntax errors, name resolution errors, and more.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1829a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1829a-108">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Cube.ScriptErrorHandlingMode%2A>  
  
  
