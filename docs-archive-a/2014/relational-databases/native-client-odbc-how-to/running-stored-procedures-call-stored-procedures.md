---
title: Stored procedure call (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], calling
ms.assetid: 31176be8-d40e-4f93-8d44-a46e804a3e2d
author: rothja
ms.author: jroth
ms.openlocfilehash: d98d623dbbb4701bb59c95df502d0063d528d0d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628642"
---
# <a name="call-stored-procedures-odbc"></a><span data-ttu-id="6e806-102">Chiamare stored procedure (ODBC)</span><span class="sxs-lookup"><span data-stu-id="6e806-102">Call Stored Procedures (ODBC)</span></span>
  <span data-ttu-id="6e806-103">Quando un'istruzione SQL chiama un stored procedure utilizzando la clausola di escape ODBC CALL, il driver Microsoft SQL Server invia la procedura a SQL Server utilizzando il meccanismo RPC (Remote stored procedure call).</span><span class="sxs-lookup"><span data-stu-id="6e806-103">When a SQL statement calls a stored procedure using the ODBC CALL escape clause, the Microsoft SQL Server driver sends the procedure to SQL Server using the remote stored procedure call (RPC) mechanism.</span></span> <span data-ttu-id="6e806-104">Le richieste RPC ignorano la maggior parte dell'analisi delle istruzioni e dell'elaborazione dei parametri in SQL Server e sono più veloci rispetto a un'istruzione Transact-SQL EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="6e806-104">RPC requests bypass much of the statement parsing and parameter processing in SQL Server and are faster than using the Transact-SQL EXECUTE statement.</span></span>  
  
 <span data-ttu-id="6e806-105">Per un'applicazione di esempio in cui viene illustrata questa funzionalità, vedere [elaborare i codici restituiti e i parametri di Output &#40;&#41;ODBC ](running-stored-procedures-process-return-codes-and-output-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="6e806-105">For a sample application that demonstrates this feature, see [Process Return Codes and Output Parameters &#40;ODBC&#41;](running-stored-procedures-process-return-codes-and-output-parameters.md).</span></span>  
  
### <a name="to-run-a-procedure-as-an-rpc"></a><span data-ttu-id="6e806-106">Per eseguire una procedura come RPC</span><span class="sxs-lookup"><span data-stu-id="6e806-106">To run a procedure as an RPC</span></span>  
  
1.  <span data-ttu-id="6e806-107">Costruire un'istruzione SQL che utilizzi la sequenza di escape ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="6e806-107">Construct a SQL statement that uses the ODBC CALL escape sequence.</span></span> <span data-ttu-id="6e806-108">Nell'istruzione vengono utilizzati marcatori di parametro per ogni parametro di input, input/output e di output e per il valore restituito della procedura, se disponibile:</span><span class="sxs-lookup"><span data-stu-id="6e806-108">The statement uses parameter markers for each input, input/output, and output parameter, and for the procedure return value (if any):</span></span>  
  
    ```  
    {? = CALL procname (?,?)}  
    ```  
  
2.  <span data-ttu-id="6e806-109">Chiamare [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) per ogni parametro di input, di input/output e di output e per il valore restituito della procedura, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="6e806-109">Call [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) for each input, input/output, and output parameter, and for the procedure return value (if any).</span></span>  
  
3.  <span data-ttu-id="6e806-110">Eseguire l'istruzione con [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span><span class="sxs-lookup"><span data-stu-id="6e806-110">Execute the statement with [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e806-111">Se un'applicazione invia una procedura utilizzando la sintassi Transact-SQL EXECUTE, invece della sequenza di escape ODBC CALL, il driver ODBC di SQL Server passa la chiamata di procedura a SQL Server come istruzione SQL anziché come chiamata RPC.</span><span class="sxs-lookup"><span data-stu-id="6e806-111">If an application submits a procedure using the Transact-SQL EXECUTE syntax (as opposed to the ODBC CALL escape sequence), the SQL Server ODBC driver passes the procedure call to SQL Server as a SQL statement rather than as an RPC.</span></span> <span data-ttu-id="6e806-112">Se viene utilizzata l'istruzione Transact-SQL EXECUTE, inoltre, i parametri di output non vengono restituiti.</span><span class="sxs-lookup"><span data-stu-id="6e806-112">Also, output parameters are not returned if the Transact-SQL EXECUTE statement is used.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e806-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e806-113">See Also</span></span>  
 <span data-ttu-id="6e806-114">[Procedure per l'esecuzione di stored procedure &#40;ODBC&#41;](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="6e806-114">[Running Stored Procedures How-to Topics &#40;ODBC&#41;](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md) </span></span>  
 <span data-ttu-id="6e806-115">[Invio in batch di chiamate a stored procedure](../native-client-odbc-stored-procedures/batching-stored-procedure-calls.md) </span><span class="sxs-lookup"><span data-stu-id="6e806-115">[Batching Stored Procedure Calls](../native-client-odbc-stored-procedures/batching-stored-procedure-calls.md) </span></span>  
 <span data-ttu-id="6e806-116">[Esecuzione di stored procedure](../native-client-odbc-stored-procedures/running-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="6e806-116">[Running Stored Procedures](../native-client-odbc-stored-procedures/running-stored-procedures.md) </span></span>  
 <span data-ttu-id="6e806-117">[Chiamata di una stored procedure](../native-client-odbc-stored-procedures/calling-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="6e806-117">[Calling a Stored Procedure](../native-client-odbc-stored-procedures/calling-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="6e806-118">Procedure</span><span class="sxs-lookup"><span data-stu-id="6e806-118">Procedures</span></span>](../native-client-odbc-queries/executing-statements/procedures.md)  
  
  
