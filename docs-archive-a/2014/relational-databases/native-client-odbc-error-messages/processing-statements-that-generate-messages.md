---
title: Elaborazione di istruzioni che generano messaggi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- PRINT statement
- messages [ODBC], statements generating messages
- statements [ODBC], message generation
- errors [ODBC], statements generating messages
- SQL Server Native Client ODBC driver, errors
- STATISTICS IO option
- STATISTICS TIME option
- DBCC statements
- SQLExecute function
- RAISERROR statement
- SQLGetDiagRec function
- ODBC error handling, statements generating messages
- SQLExecDirect function
ms.assetid: 672ebdc5-7fa1-4ceb-8d52-fd25ef646654
author: rothja
ms.author: jroth
ms.openlocfilehash: c26376eabb756d356dd71fb3bd8284a6b11dced7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714339"
---
# <a name="processing-statements-that-generate-messages"></a><span data-ttu-id="43629-102">Elaborazione di istruzioni che generano messaggi</span><span class="sxs-lookup"><span data-stu-id="43629-102">Processing Statements That Generate Messages</span></span>
  <span data-ttu-id="43629-103">Le opzioni STATISTICS TIME e STATISTICS IO dell'istruzione SET [!INCLUDE[tsql](../../includes/tsql-md.md)] vengono utilizzate per ottenere informazioni utili per la diagnosi di query con esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="43629-103">The [!INCLUDE[tsql](../../includes/tsql-md.md)] SET statement options STATISTICS TIME and STATISTICS IO are used to get information that aids in diagnosing long-running queries.</span></span> <span data-ttu-id="43629-104">Le versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supportano inoltre l'opzione SHOWPLAN per l'analisi di piani di query.</span><span class="sxs-lookup"><span data-stu-id="43629-104">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] also support the SHOWPLAN option for analyzing query plans.</span></span> <span data-ttu-id="43629-105">È possibile impostare queste opzioni in un'applicazione ODBC eseguendo le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43629-105">An ODBC application can set these options by executing the following statements:</span></span>  
  
```  
SQLExecDirect(hstmt, "SET SHOWPLAN ON", SQL_NTS);  
SQLExecDirect(hstmt, "SET STATISTICS TIME ON", SQL_NTS90  
);  
SQLExecDirect(hstmt, "SET STATISTICS IO ON", SQL_NTS);  
```  
  
 <span data-ttu-id="43629-106">Quando SET STATISTICs TIME o SET SHOWPLAN sono ON, **SQLExecute** e **SQLExecDirect** restituiscono SQL_SUCCESS_WITH_INFO e, a quel punto, l'applicazione può recuperare l'output di Showplan o Statistics time chiamando **SQLGetDiagRec** fino a quando non restituisce SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="43629-106">When SET STATISTICS TIME or SET SHOWPLAN are ON, **SQLExecute** and **SQLExecDirect** return SQL_SUCCESS_WITH_INFO, and, at that point, the application can retrieve the SHOWPLAN or STATISTICS TIME output by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="43629-107">Ogni riga di dati SHOWPLAN viene restituita nel formato:</span><span class="sxs-lookup"><span data-stu-id="43629-107">Each line of SHOWPLAN data comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError=6223,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]   
              Table Scan"  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="43629-108">versione 7.0 ha sostituito l'opzione SHOWPLAN con SHOWPLAN_ALL e SHOWPLAN_TEXT. Entrambe restituiscono l'output come set di risultati, non come set di messaggi.</span><span class="sxs-lookup"><span data-stu-id="43629-108">version 7.0 replaced the SHOWPLAN option with SHOWPLAN_ALL and SHOWPLAN_TEXT, both of which return output as a result set, not a set of messages.</span></span>  
  
 <span data-ttu-id="43629-109">Ogni riga di dati STATISTICS TIME viene restituita nel formato:</span><span class="sxs-lookup"><span data-stu-id="43629-109">Each line of STATISTICS TIME comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError= 3613,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
   SQL Server Parse and Compile Time: cpu time = 0 ms."  
```  
  
 <span data-ttu-id="43629-110">L'output di SET STATISTICS IO non è disponibile fino alla fine di un set di risultati.</span><span class="sxs-lookup"><span data-stu-id="43629-110">The output of SET STATISTICS IO is not available until the end of a result set.</span></span> <span data-ttu-id="43629-111">Per ottenere l'output di STATISTICs IO, l'applicazione chiama **SQLGetDiagRec** quando **SQLFetch** o [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md) restituisce SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="43629-111">To get STATISTICS IO output, the application calls **SQLGetDiagRec** at the time **SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md) returns SQL_NO_DATA.</span></span> <span data-ttu-id="43629-112">L'output di STATISTICS IO viene restituito nel formato:</span><span class="sxs-lookup"><span data-stu-id="43629-112">The output of STATISTICS IO comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError= 3615,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Table: testshow  scan count 1,  logical reads: 1,  
   physical reads: 0."  
```  
  
## <a name="using-dbcc-statements"></a><span data-ttu-id="43629-113">Utilizzo di istruzioni DBCC</span><span class="sxs-lookup"><span data-stu-id="43629-113">Using DBCC Statements</span></span>  
 <span data-ttu-id="43629-114">Le istruzioni DBCC restituiscono i dati come messaggi, non come set di risultati.</span><span class="sxs-lookup"><span data-stu-id="43629-114">DBCC statements return their data as messages, not result sets.</span></span> <span data-ttu-id="43629-115">**SQLExecDirect** o **sqlexecute** restituisce SQL_SUCCESS_WITH_INFO e l'applicazione recupera l'output chiamando **SQLGetDiagRec** fino a quando non restituisce SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="43629-115">**SQLExecDirect** or **SQLExecute** return SQL_SUCCESS_WITH_INFO, and the application retrieves the output by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span>  
  
 <span data-ttu-id="43629-116">Nell'istruzione seguente, ad esempio, viene restituito SQL_SUCCESS_WITH_INFO:</span><span class="sxs-lookup"><span data-stu-id="43629-116">For example, the following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect(hstmt, "DBCC CHECKTABLE(Authors)", SQL_NTS);  
```  
  
 <span data-ttu-id="43629-117">Le chiamate a **SQLGetDiagRec** restituiscono:</span><span class="sxs-lookup"><span data-stu-id="43629-117">Calls to **SQLGetDiagRec** return:</span></span>  
  
```  
szSqlState = "01000", *pfNativeError = 2536,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Checking authors"  
szSqlState = "01000", *pfNativeError = 2579,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   The total number of data pages in this table is 1."  
szSqlState = "01000", *pfNativeError = 7929,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Table has 23 data rows."  
szSqlState = "01000", *pfNativeError = 2528  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   DBCC execution completed. If DBCC printed error messages,  
   see your System Administrator."  
```  
  
## <a name="using-print-and-raiserror-statements"></a><span data-ttu-id="43629-118">Utilizzo delle istruzioni PRINT e RAISERROR</span><span class="sxs-lookup"><span data-stu-id="43629-118">Using PRINT and RAISERROR Statements</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]<span data-ttu-id="43629-119">Anche le istruzioni PRINT e RAISERROR restituiscono dati chiamando **SQLGetDiagRec**.</span><span class="sxs-lookup"><span data-stu-id="43629-119">PRINT and RAISERROR statements also return data by calling **SQLGetDiagRec**.</span></span> <span data-ttu-id="43629-120">Le istruzioni PRINT fanno sì che l'esecuzione dell'istruzione SQL restituisca SQL_SUCCESS_WITH_INFO e una chiamata successiva a **SQLGetDiagRec** restituisca un valore *SQLSTATE* di 01000.</span><span class="sxs-lookup"><span data-stu-id="43629-120">PRINT statements cause the SQL statement execution to return SQL_SUCCESS_WITH_INFO, and a subsequent call to **SQLGetDiagRec** returns a *SQLState* of 01000.</span></span> <span data-ttu-id="43629-121">Un'istruzione RAISERROR con livello di gravità dieci o inferiore si comporta esattamente come PRINT.</span><span class="sxs-lookup"><span data-stu-id="43629-121">A RAISERROR with a severity of ten or lower behaves the same as PRINT.</span></span> <span data-ttu-id="43629-122">Un'istruzione RAISERROR con un livello di gravità pari a 11 causa la restituzione di SQL_ERROR da parte di Execute e una chiamata successiva a **SQLGetDiagRec** restituisce *SQLSTATE* 42000.</span><span class="sxs-lookup"><span data-stu-id="43629-122">A RAISERROR with a severity of 11 or higher causes the execute to return SQL_ERROR, and a subsequent call to **SQLGetDiagRec** returns *SQLState* 42000.</span></span> <span data-ttu-id="43629-123">Nell'istruzione seguente, ad esempio, viene restituito SQL_SUCCESS_WITH_INFO:</span><span class="sxs-lookup"><span data-stu-id="43629-123">For example, the following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect (hstmt, "PRINT  'Some message' ", SQL_NTS);  
```  
  
 <span data-ttu-id="43629-124">La chiamata a **SQLGetDiagRec** restituisce:</span><span class="sxs-lookup"><span data-stu-id="43629-124">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "01000", *pfNative Error = 0,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Some message"  
```  
  
 <span data-ttu-id="43629-125">Nell'istruzione seguente, ad esempio, viene restituito SQL_SUCCESS_WITH_INFO:</span><span class="sxs-lookup"><span data-stu-id="43629-125">The following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect (hstmt, "RAISERROR ('Sample error 1.', 10, -1)",  
   SQL_NTS)  
```  
  
 <span data-ttu-id="43629-126">La chiamata a **SQLGetDiagRec** restituisce:</span><span class="sxs-lookup"><span data-stu-id="43629-126">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "01000", *pfNative Error = 50000,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Sample error 1."  
```  
  
 <span data-ttu-id="43629-127">L'istruzione seguente restituisce SQL_ERROR:</span><span class="sxs-lookup"><span data-stu-id="43629-127">The following statement returns SQL_ERROR:</span></span>  
  
```  
SQLExecDirect (hstmt, "RAISERROR ('Sample error 2.', 11, -1)", SQL_NTS)  
```  
  
 <span data-ttu-id="43629-128">La chiamata a **SQLGetDiagRec** restituisce:</span><span class="sxs-lookup"><span data-stu-id="43629-128">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "42000", *pfNative Error = 50000,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Sample error 2."  
```  
  
 <span data-ttu-id="43629-129">La durata della chiamata di **SQLGetDiagRec** è fondamentale quando in un set di risultati viene inclusa l'output delle istruzioni Print o RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="43629-129">The timing of calling **SQLGetDiagRec** is critical when output from PRINT or RAISERROR statements is included in a result set.</span></span> <span data-ttu-id="43629-130">La chiamata a **SQLGetDiagRec** per recuperare l'output di Print o RAISERROR deve essere eseguita subito dopo l'istruzione che riceve SQL_ERROR o SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="43629-130">The call to **SQLGetDiagRec** to retrieve the PRINT or RAISERROR output must be made immediately after the statement that receives SQL_ERROR or SQL_SUCCESS_WITH_INFO.</span></span> <span data-ttu-id="43629-131">Si tratta di un processo diretto quando viene eseguita una sola istruzione SQL, come negli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="43629-131">This is straightforward when only a single SQL statement is executed, as in the examples above.</span></span> <span data-ttu-id="43629-132">In questi casi, la chiamata a **SQLExecDirect** o **sqlexecute** restituisce SQL_ERROR o SQL_SUCCESS_WITH_INFO e **SQLGetDiagRec** può essere chiamato.</span><span class="sxs-lookup"><span data-stu-id="43629-132">In these cases, the call to **SQLExecDirect** or **SQLExecute** returns SQL_ERROR or SQL_SUCCESS_WITH_INFO and **SQLGetDiagRec** can then be called.</span></span> <span data-ttu-id="43629-133">Il processo è meno diretto quando vengono codificati i cicli per gestire l'output di un batch di istruzioni SQL o quando vengono eseguite le stored procedure di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43629-133">It is less straightforward when coding loops to handle the output of a batch of SQL statements or when executing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures.</span></span>  
  
 <span data-ttu-id="43629-134">In questo caso, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] restituisce un set di risultati per ogni istruzione SELECT eseguita in un batch o in una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="43629-134">In this case, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns a result set for every SELECT statement executed in a batch or stored procedure.</span></span> <span data-ttu-id="43629-135">Se il batch o la stored procedure contiene le istruzioni PRINT o RAISERROR, il relativo output viene interfacciato con il set di risultati dell'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="43629-135">If the batch or procedure contains PRINT or RAISERROR statements, the output for these is interleaved with the SELECT statement result sets.</span></span> <span data-ttu-id="43629-136">Se la prima istruzione del batch o della procedura è PRINT o RAISERROR, **SQLExecute** o **SQLExecDirect** restituisce SQL_SUCCESS_WITH_INFO o SQL_ERROR e l'applicazione deve chiamare **SQLGetDiagRec** fino a quando non restituisce SQL_NO_DATA per recuperare le informazioni di stampa o RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="43629-136">If the first statement in the batch or procedure is a PRINT or RAISERROR, the **SQLExecute** or **SQLExecDirect** returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, and the application needs to call **SQLGetDiagRec** until it returns SQL_NO_DATA to retrieve the PRINT or RAISERROR information.</span></span>  
  
 <span data-ttu-id="43629-137">Se l'istruzione PRINT o RAISERROR viene restituita dopo un'istruzione SQL, ad esempio un'istruzione SELECT, le informazioni di stampa o RAISERROR vengono restituite quando si [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md)posizioni del set di risultati contenente l'errore.</span><span class="sxs-lookup"><span data-stu-id="43629-137">If the PRINT or RAISERROR statement comes after an SQL statement (such as a SELECT statement), then the PRINT or RAISERROR information is returned when [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md)positions on the result set containing the error.</span></span> <span data-ttu-id="43629-138">**SQLMoreResults** restituisce SQL_SUCCESS_WITH_INFO o SQL_ERROR a seconda della gravità del messaggio.</span><span class="sxs-lookup"><span data-stu-id="43629-138">**SQLMoreResults** returns SQL_SUCCESS_WITH_INFO or SQL_ERROR depending on the severity of the message.</span></span> <span data-ttu-id="43629-139">I messaggi vengono recuperati chiamando **SQLGetDiagRec** fino a quando non viene restituito SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="43629-139">Messages are retrieved by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43629-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43629-140">See Also</span></span>  
 [<span data-ttu-id="43629-141">Gestione di errori e messaggi</span><span class="sxs-lookup"><span data-stu-id="43629-141">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
