---
title: Modifiche al comportamento della lunghezza della stringa e della sottostringa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2119b7ba-2e52-44bf-ac57-82c2d46a48ff
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1188823a877b4c5dc9cef13431492dfe3b303e23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628221"
---
# <a name="changes-to-behavior-of-string-length-and-substring"></a><span data-ttu-id="d9f9e-102">Modifiche al comportamento di sottostringa e lunghezza stringa</span><span class="sxs-lookup"><span data-stu-id="d9f9e-102">Changes to behavior of string-length and substring</span></span>
  <span data-ttu-id="d9f9e-103">La [funzione String-length &#40;&#41;XQuery](/sql/xquery/functions-on-string-values-string-length) e la [funzione SUBSTRING &#40;le funzioni&#41;XQuery](/sql/xquery/functions-on-string-values-substring) possono restituire risultati diversi se utilizzate con database XML che contengono caratteri surrogati.</span><span class="sxs-lookup"><span data-stu-id="d9f9e-103">The [string-length Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) and [substring Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) functions may return different results when used with XML databases that contain surrogate characters.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d9f9e-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9f9e-104">Description</span></span>  
 <span data-ttu-id="d9f9e-105">Quando un database è impostato per essere compatibile con [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , il comportamento della [funzione di lunghezza stringa &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) e la [funzione substring &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) funzioni cambiano quando si gestiscono caratteri supplementari Unicode.</span><span class="sxs-lookup"><span data-stu-id="d9f9e-105">When a database is set to be compatible with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the behavior of the [string-length Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) and [substring Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) functions changes when dealing with Unicode supplementary characters.</span></span> <span data-ttu-id="d9f9e-106">Ogni carattere supplementare Unicode, definito mediante un punto di codice maggiore di U+FFFF, viene contato come un carattere anziché due da queste funzioni, come nelle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="d9f9e-106">Each Unicode supplementary character, which is defined by having a code point larger than U+FFFF, is counted as one character by these functions rather than two, as it was in previous versions.</span></span>  
  
 <span data-ttu-id="d9f9e-107">Per ulteriori informazioni sui caratteri surrogati, vedere [surrogati e caratteri supplementari](https://go.microsoft.com/fwlink/?LinkId=178317).</span><span class="sxs-lookup"><span data-stu-id="d9f9e-107">For more information about surrogate characters, see [Surrogates and Supplementary Characters](https://go.microsoft.com/fwlink/?LinkId=178317).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f9e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9f9e-108">See Also</span></span>  
 <span data-ttu-id="d9f9e-109">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="d9f9e-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="d9f9e-110">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="d9f9e-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](https://docs.microsoft.com/sql/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
