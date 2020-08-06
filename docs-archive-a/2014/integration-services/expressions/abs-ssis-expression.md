---
title: ABS (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- ABS function
- absolute positive value
ms.assetid: 156747f6-e016-44cf-9a9f-ae8e4a1b4f17
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2f429dda94282646ef769a1c393f9fa54b56e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635189"
---
# <a name="abs-ssis-expression"></a>ABS (espressione SSIS)
  Restituisce il valore positivo assoluto di un'espressione numerica.  
  
## <a name="syntax"></a>Sintassi  
  
```  
  
ABS(numeric_expression)  
```  
  
## <a name="arguments"></a>Argomenti  
 *numeric_expression*  
 Espressione numerica con o senza segno.  
  
## <a name="result-types"></a>Tipi restituiti  
 Tipo di dati dell'espressione numerica inviata alla funzione.  
  
## <a name="remarks"></a>Osservazioni  
 Se l'argomento è Null, ABS restituirà Null.  
  
## <a name="expression-examples"></a>Esempi di espressione  
 In questi esempi la funzione ABS viene applicata a un numero positivo e a un numero negativo. In entrambi i casi viene restituito 1,23.  
  
```  
ABS(-1.23)  
ABS(1.23)  
```  
  
 In questo esempio la funzione ABS viene applicata a un'espressione che esegue una sottrazione tra i valori delle variabili **HighTemperature** e **LowTempature**.  
  
```  
ABS(@HighTemperature - @LowTemperature)  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni &#40;espressione SSIS&#41;](functions-ssis-expression.md)  
  
  
