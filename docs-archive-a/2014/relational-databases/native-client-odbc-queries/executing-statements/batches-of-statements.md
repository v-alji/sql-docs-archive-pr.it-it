---
title: Batch di istruzioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC], batches
- batches [ODBC]
- ODBC applications, statements
- multiple statements, batches
- SQLMoreResults function
- SQLExecDirect function
ms.assetid: 057d7c1c-1428-4780-9447-a002ea741188
author: rothja
ms.author: jroth
ms.openlocfilehash: 4818b67766dafe851035041c8fd5137a0dfade73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624120"
---
# <a name="batches-of-statements"></a><span data-ttu-id="646e9-102">Batch di istruzioni</span><span class="sxs-lookup"><span data-stu-id="646e9-102">Batches of Statements</span></span>
  <span data-ttu-id="646e9-103">Un batch di [!INCLUDE[tsql](../../../includes/tsql-md.md)] istruzioni contiene due o più istruzioni, separate da un punto e virgola (;), compilate in una singola stringa passata a **SQLExecDirect** o alla [funzione SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360).</span><span class="sxs-lookup"><span data-stu-id="646e9-103">A batch of [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements contains two or more statements, separated by a semicolon (;), built into a single string passed to **SQLExecDirect** or [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360).</span></span> <span data-ttu-id="646e9-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="646e9-104">For example:</span></span>  
  
```  
SQLExecDirect(hstmt,   
    "SELECT * FROM Authors; SELECT * FROM Titles",  
    SQL_NTS);  
```  
  
 <span data-ttu-id="646e9-105">I batch possono essere più efficienti rispetto all'invio separato delle istruzioni in quanto il traffico di rete viene spesso ridotto.</span><span class="sxs-lookup"><span data-stu-id="646e9-105">Batches can be more efficient than submitting statements separately because network traffic is often reduced.</span></span> <span data-ttu-id="646e9-106">Utilizzare [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) per posizionare il set di risultati successivo al termine del set di risultati corrente.</span><span class="sxs-lookup"><span data-stu-id="646e9-106">Use [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) to get positioned on the next result set when finished with the current result set.</span></span>  
  
 <span data-ttu-id="646e9-107">I batch possono essere sempre utilizzati quando gli attributi del cursore ODBC sono impostati sui valori predefiniti di un cursore forward only in sola lettura con dimensioni del set di righe pari a 1.</span><span class="sxs-lookup"><span data-stu-id="646e9-107">Batches can always be used when the ODBC cursor attributes are set to the defaults of a forward-only, read-only cursor with a rowset size of 1.</span></span>  
  
 <span data-ttu-id="646e9-108">Se un batch viene eseguito quando si utilizzano cursori del server in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], questi ultimi vengono convertiti implicitamente in set di risultati predefiniti.</span><span class="sxs-lookup"><span data-stu-id="646e9-108">If a batch is executed when using server cursors against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the server cursor is implicitly converted to a default result set.</span></span> <span data-ttu-id="646e9-109">**SQLExecDirect** o **sqlexecute** restituiscono SQL_SUCCESS_WITH_INFO e una chiamata a **SQLGetDiagRec** restituisce:</span><span class="sxs-lookup"><span data-stu-id="646e9-109">**SQLExecDirect** or **SQLExecute** return SQL_SUCCESS_WITH_INFO, and a call to **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState = "01S02", pfNativeError = 0  
szErrorMsg = "[Microsoft][SQL Server Native Server Native Client]Cursor type changed."  
```  
  
## <a name="see-also"></a><span data-ttu-id="646e9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="646e9-110">See Also</span></span>  
 [<span data-ttu-id="646e9-111">Esecuzione di istruzioni &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="646e9-111">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements-odbc.md)  
  
  
