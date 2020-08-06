---
title: REVERSE (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REVERSE function
- reverse character expressions
ms.assetid: bcebcc55-7247-4896-8f53-4d582d58cfb4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2ace136eed0abcb9df7b25d9370c46d7556c1d48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716495"
---
# <a name="reverse-ssis-expression"></a>REVERSE (espressione SSIS)
  Viene restituita un'espressione di caratteri in ordine inverso.  
  
## <a name="syntax"></a>Sintassi  
  
```  
  
REVERSE(character_expression)  
```  
  
## <a name="arguments"></a>Argomenti  
 *character_expression*  
 Espressione di caratteri da invertire.  
  
## <a name="result-types"></a>Tipi restituiti  
 DT_WSTR  
  
## <a name="remarks"></a>Osservazioni  
 Il tipo di dati dell’argomento *character_expression* deve essere DT_WSTR.  
  
 Se *character_expression* è null, REVERSE restituisce un risultato null.  
  
## <a name="expression-examples"></a>Esempi di espressione  
 In questo esempio viene utilizzato un valore letterale stringa. Il risultato restituito è "ekiB niatnuoM".  
  
```  
REVERSE("Mountain Bike")  
```  
  
 In questo esempio viene utilizzata una variabile. Se **Name** contiene Touring Bike, il risultato restituito sarà "ekiB gniruoT".  
  
```  
REVERSE(@Name)  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni &#40;espressione SSIS&#41;](functions-ssis-expression.md)  
  
  
