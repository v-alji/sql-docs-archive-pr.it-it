---
title: Gestione dei parametri di Large Object (LOB) in CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- large data, CLR integration
- LOB data [SQL Server], CLR integration
- SqlBytes data type
- SqlChars data type
ms.assetid: d07956f6-9543-4476-9426-536f95991150
author: rothja
ms.author: jroth
ms.openlocfilehash: ee791c73a6610761c2086723f9e41c2351b37dd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725956"
---
# <a name="handling-large-object-lob-parameters-in-the-clr"></a><span data-ttu-id="4ca11-102">Gestione di parametri di tipo LOB (Large Object) in CLR</span><span class="sxs-lookup"><span data-stu-id="4ca11-102">Handling Large Object (LOB) Parameters in the CLR</span></span>
  <span data-ttu-id="4ca11-103">Utilizzare `SqlBytes` e `SqlChars` per passare rispettivamente parametri LOB di tipo binario (`varbinary(max)`) e parametri LOB di tipo carattere (`nvarchar(max)`).</span><span class="sxs-lookup"><span data-stu-id="4ca11-103">Use `SqlBytes` and `SqlChars` to pass large object (LOB) binary type (`varbinary(max)`) and LOB character type (`nvarchar(max)`) parameters, respectively.</span></span> <span data-ttu-id="4ca11-104">Questi tipi consentono di eseguire il flusso dei valori LOB dal database alla routine CLR (Common Language Runtime) anziché copiare l'intero valore nello spazio gestito.</span><span class="sxs-lookup"><span data-stu-id="4ca11-104">These types allow streaming the LOB values from the database to the common language runtime (CLR) routine, instead of copying the entire value into managed space.</span></span> <span data-ttu-id="4ca11-105">`SqlBinary` e `SqlString` devono essere utilizzati solo per i piccoli valori di stringa binari e di carattere.</span><span class="sxs-lookup"><span data-stu-id="4ca11-105">`SqlBinary` and `SqlString` should be used only for small binary and character string values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca11-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ca11-106">See Also</span></span>  
 [<span data-ttu-id="4ca11-107">Tipi di dati di SQL Server in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4ca11-107">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
