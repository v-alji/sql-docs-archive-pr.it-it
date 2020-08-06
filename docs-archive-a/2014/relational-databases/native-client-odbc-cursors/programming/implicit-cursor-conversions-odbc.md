---
title: Conversioni implicite di cursori (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC cursors, implicit cursor conversions
- implicit cursor conversions
- cursors [ODBC], implicit cursor conversions
ms.assetid: fe29a58d-8448-4512-9ffd-b414784ba338
author: rothja
ms.author: jroth
ms.openlocfilehash: ff8350c71a853e39ff1d35a1f3fba6e8e1944934
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635551"
---
# <a name="implicit-cursor-conversions-odbc"></a><span data-ttu-id="1f40b-102">Conversioni implicite dei cursori (ODBC)</span><span class="sxs-lookup"><span data-stu-id="1f40b-102">Implicit Cursor Conversions (ODBC)</span></span>
  <span data-ttu-id="1f40b-103">Le applicazioni possono richiedere un tipo di cursore tramite [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) e quindi eseguire un'istruzione SQL non supportata dai cursori del server del tipo richiesto.</span><span class="sxs-lookup"><span data-stu-id="1f40b-103">Applications can request a cursor type through [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) and then execute an SQL statement that is not supported by server cursors of the type requested.</span></span> <span data-ttu-id="1f40b-104">Una chiamata a **SQLExecute** o **SQLExecDirect** restituisce SQL_SUCCESS_WITH_INFO e **SQLGetDiagRec** restituisce:</span><span class="sxs-lookup"><span data-stu-id="1f40b-104">A call to **SQLExecute** or **SQLExecDirect** returns SQL_SUCCESS_WITH_INFO and **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState = "01S02", *pfNativeError = 0,  
szErrorMsg="[Microsoft][SQL Server Native Client] Cursor type changed"  
```  
  
 <span data-ttu-id="1f40b-105">L'applicazione può determinare il tipo di cursore usato chiamando **SQLGetStmtOption** impostato su SQL_CURSOR_TYPE.</span><span class="sxs-lookup"><span data-stu-id="1f40b-105">The application can determine what type of cursor is now being used by calling **SQLGetStmtOption** set to SQL_CURSOR_TYPE.</span></span> <span data-ttu-id="1f40b-106">La conversione del tipo di cursore viene applicata a una sola istruzione.</span><span class="sxs-lookup"><span data-stu-id="1f40b-106">The cursor type conversion applies to only one statement.</span></span> <span data-ttu-id="1f40b-107">Il successivo **SQLExecDirect** o **SQLExecute** verrà eseguito utilizzando le impostazioni originali del cursore dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="1f40b-107">The next **SQLExecDirect** or **SQLExecute** will be done using the original statement cursor settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f40b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f40b-108">See Also</span></span>  
 [<span data-ttu-id="1f40b-109">Dettagli sulla programmazione dei cursori &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="1f40b-109">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
