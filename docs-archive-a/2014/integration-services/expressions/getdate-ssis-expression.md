---
title: GETDATE (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- current date
- GETDATE function
- dates [Integration Services], GETDATE
ms.assetid: 6d20ec93-3244-4d63-baf6-70eff7bd598c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0acb384a8c3c3dfdae55c7172f341f9e32765e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627308"
---
# <a name="getdate-ssis-expression"></a><span data-ttu-id="0f657-102">GETDATE (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="0f657-102">GETDATE (SSIS Expression)</span></span>
  <span data-ttu-id="0f657-103">Viene restituita la data corrente del sistema in formato DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="0f657-103">Returns the current date of the system in a DT_DBTIMESTAMP format.</span></span> <span data-ttu-id="0f657-104">La funzione GETDATE non accetta argomenti.</span><span class="sxs-lookup"><span data-stu-id="0f657-104">The GETDATE function takes no arguments.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f657-105">La lunghezza del risultato restituito dalla funzione GETDATE è 29 caratteri.</span><span class="sxs-lookup"><span data-stu-id="0f657-105">The length of the return result from the GETDATE function is 29 characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f657-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f657-106">Syntax</span></span>  
  
```  
  
GETDATE()  
```  
  
## <a name="arguments"></a><span data-ttu-id="0f657-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0f657-107">Arguments</span></span>  
 <span data-ttu-id="0f657-108">nessuno</span><span class="sxs-lookup"><span data-stu-id="0f657-108">None</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0f657-109">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="0f657-109">Result Types</span></span>  
 <span data-ttu-id="0f657-110">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="0f657-110">DT_DBTIMESTAMP</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="0f657-111">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="0f657-111">Expression Examples</span></span>  
 <span data-ttu-id="0f657-112">In questo esempio viene restituito l'anno della data corrente.</span><span class="sxs-lookup"><span data-stu-id="0f657-112">This example returns the year of the current date.</span></span>  
  
```  
DATEPART("year",GETDATE())  
```  
  
 <span data-ttu-id="0f657-113">Questo esempio restituisce il numero di giorni tra una data nella colonna **ModifiedDate** e la data corrente.</span><span class="sxs-lookup"><span data-stu-id="0f657-113">This example returns the number of days between a date in the **ModifiedDate** column and the current date.</span></span>  
  
```  
DATEDIFF("dd",ModifiedDate,GETDATE())  
```  
  
 <span data-ttu-id="0f657-114">In questo esempio vengono aggiunti tre mesi alla data corrente.</span><span class="sxs-lookup"><span data-stu-id="0f657-114">This example adds three months to the current date.</span></span>  
  
```  
DATEADD("Month",3,GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f657-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f657-115">See Also</span></span>  
 <span data-ttu-id="0f657-116">[GETUTCDATE &#40;espressione SSIS&#41;](getutcdate-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="0f657-116">[GETUTCDATE &#40;SSIS Expression&#41;](getutcdate-ssis-expression.md) </span></span>  
 [<span data-ttu-id="0f657-117">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0f657-117">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
