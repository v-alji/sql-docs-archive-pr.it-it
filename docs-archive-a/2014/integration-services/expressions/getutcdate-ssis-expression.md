---
title: GETUTCDATE (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], GETUTCDATE
- current date
- UTC time
- GETUTCDATE function
ms.assetid: 2282339c-c24f-493e-8e66-181ea8af5ad0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f157ab5641e521a42cb3c96c96446b31de5dfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716532"
---
# <a name="getutcdate-ssis-expression"></a><span data-ttu-id="ec89e-102">GETUTCDATE (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="ec89e-102">GETUTCDATE (SSIS Expression)</span></span>
  <span data-ttu-id="ec89e-103">Viene restituita la data corrente del sistema in base all'ora UTC (Universal Time Coordinated o ora di Greenwich) utilizzando un formato DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="ec89e-103">Returns the current date of the system in UTC time (Universal Time Coordinate or Greenwich Mean Time) using a DT_DBTIMESTAMP format.</span></span> <span data-ttu-id="ec89e-104">La funzione GETUTCDATE non accetta argomenti.</span><span class="sxs-lookup"><span data-stu-id="ec89e-104">The GETUTCDATE function takes no arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec89e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec89e-105">Syntax</span></span>  
  
```  
  
GETUTCDATE()  
```  
  
## <a name="arguments"></a><span data-ttu-id="ec89e-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ec89e-106">Arguments</span></span>  
 <span data-ttu-id="ec89e-107">nessuno</span><span class="sxs-lookup"><span data-stu-id="ec89e-107">None</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ec89e-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="ec89e-108">Result Types</span></span>  
 <span data-ttu-id="ec89e-109">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="ec89e-109">DT_DBTIMESTAMP</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="ec89e-110">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="ec89e-110">Expression Examples</span></span>  
 <span data-ttu-id="ec89e-111">In questo esempio viene restituito l'anno della data corrente in base all'ora UTC (Universal Time Coordinated o ora di Greenwich).</span><span class="sxs-lookup"><span data-stu-id="ec89e-111">This example returns the year of the current date in UTC time.</span></span>  
  
```  
DATEPART("year",GETUTCDATE())  
```  
  
 <span data-ttu-id="ec89e-112">In questo esempio viene restituito il numero di giorni tra una data nella colonna **ModifiedDate** e la data UTC corrente.</span><span class="sxs-lookup"><span data-stu-id="ec89e-112">This example returns the number of days between a date in the **ModifiedDate** column and the current UTC date.</span></span>  
  
```  
DATEDIFF("dd",ModifiedDate,GETUTCDATE())  
```  
  
 <span data-ttu-id="ec89e-113">In questo esempio vengono aggiunti tre mesi alla data UTC corrente.</span><span class="sxs-lookup"><span data-stu-id="ec89e-113">This example adds three months to the current UTC date.</span></span>  
  
```  
DATEADD("Month",3,GETUTCDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec89e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec89e-114">See Also</span></span>  
 <span data-ttu-id="ec89e-115">[GETDATE &#40;espressione SSIS&#41;](getdate-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ec89e-115">[GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md) </span></span>  
 [<span data-ttu-id="ec89e-116">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="ec89e-116">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
