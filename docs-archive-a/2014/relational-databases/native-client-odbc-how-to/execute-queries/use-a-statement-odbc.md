---
title: Utilizzare un'istruzione (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC]
ms.assetid: f7573f8f-6f21-4e03-8dd5-a5f2ea4878cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ff3bc8c545cc9b55f0da3bb31d68d1ecbb5b547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723812"
---
# <a name="use-a-statement-odbc"></a><span data-ttu-id="5ea42-102">Utilizzare un'istruzione (ODBC)</span><span class="sxs-lookup"><span data-stu-id="5ea42-102">Use a Statement (ODBC)</span></span>
    
### <a name="to-use-a-statement"></a><span data-ttu-id="5ea42-103">Per utilizzare un'istruzione</span><span class="sxs-lookup"><span data-stu-id="5ea42-103">To use a statement</span></span>  
  
1.  <span data-ttu-id="5ea42-104">Chiamare [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) con *HandleType* impostato su SQL_HANDLE_STMT per allocare un handle di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5ea42-104">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a *HandleType* of SQL_HANDLE_STMT to allocate a statement handle.</span></span>  
  
2.  <span data-ttu-id="5ea42-105">È inoltre possibile chiamare [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) per impostare le opzioni dell'istruzione o [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) per ottenere gli attributi dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="5ea42-105">Optionally, call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set statement options or [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) to get statement attributes.</span></span>  
  
     <span data-ttu-id="5ea42-106">Per utilizzare i cursori server, è necessario impostare gli attributi del cursore su valori diversi da quelli predefiniti.</span><span class="sxs-lookup"><span data-stu-id="5ea42-106">To use server cursors, you must set cursor attributes to values other than their defaults.</span></span>  
  
3.  <span data-ttu-id="5ea42-107">Facoltativamente, se l'istruzione viene eseguita più volte, è possibile preparare l'istruzione per l'esecuzione con la [funzione SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360).</span><span class="sxs-lookup"><span data-stu-id="5ea42-107">Optionally, if the statement will be executed several times, prepare the statement for execution with [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360).</span></span>  
  
4.  <span data-ttu-id="5ea42-108">Se all'istruzione sono stati associati marcatori di parametro, è possibile associare i marcatori di parametro alle variabili di programma tramite [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="5ea42-108">Optionally, if the statement has bound parameter markers, bind the parameter markers to program variables by using [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span></span> <span data-ttu-id="5ea42-109">Se l'istruzione è stata preparata, è possibile chiamare [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) e [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) per trovare il numero e le caratteristiche dei parametri.</span><span class="sxs-lookup"><span data-stu-id="5ea42-109">If the statement was prepared, you can call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) and [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to find the number and characteristics of the parameters.</span></span>  
  
5.  <span data-ttu-id="5ea42-110">Eseguire un'istruzione direttamente mediante SQLExecDirect.</span><span class="sxs-lookup"><span data-stu-id="5ea42-110">Execute a statement directly by using SQLExecDirect.</span></span>  
  
     <span data-ttu-id="5ea42-111">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="5ea42-111">\- or -</span></span>  
  
     <span data-ttu-id="5ea42-112">Se l'istruzione è stata preparata, eseguirla più volte tramite [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400).</span><span class="sxs-lookup"><span data-stu-id="5ea42-112">If the statement was prepared, execute it multiple times by using [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400).</span></span>  
  
     <span data-ttu-id="5ea42-113">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="5ea42-113">\- or -</span></span>  
  
     <span data-ttu-id="5ea42-114">Chiamare una funzione di catalogo, che restituisce i risultati.</span><span class="sxs-lookup"><span data-stu-id="5ea42-114">Call a catalog function, which returns results.</span></span>  
  
6.  <span data-ttu-id="5ea42-115">Elaborare i risultati associando le colonne del set di risultati alle variabili di programma, spostando i dati dalle colonne del set di risultati alle variabili di programma tramite [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) oppure usando una combinazione dei due metodi.</span><span class="sxs-lookup"><span data-stu-id="5ea42-115">Process the results by binding the result set columns to program variables, by moving data from the result set columns to program variables by using [SQLGetData](../../native-client-odbc-api/sqlgetdata.md), or a combination of the two methods.</span></span>  
  
     <span data-ttu-id="5ea42-116">Recuperare il set di risultati di un'istruzione una riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="5ea42-116">Fetch through the result set of a statement one row at a time.</span></span>  
  
     <span data-ttu-id="5ea42-117">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="5ea42-117">\- or -</span></span>  
  
     <span data-ttu-id="5ea42-118">Recuperare il set di risultati più righe alla volta mediante un cursore a blocchi.</span><span class="sxs-lookup"><span data-stu-id="5ea42-118">Fetch through the result set several rows at a time by using a block cursor.</span></span>  
  
     <span data-ttu-id="5ea42-119">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="5ea42-119">\- or -</span></span>  
  
     <span data-ttu-id="5ea42-120">Chiamare [SQLRowCount](../../native-client-odbc-api/sqlrowcount.md) per determinare il numero di righe interessate da un'istruzione INSERT, UPDATE o DELETE.</span><span class="sxs-lookup"><span data-stu-id="5ea42-120">Call [SQLRowCount](../../native-client-odbc-api/sqlrowcount.md) to determine the number of rows affected by an INSERT, UPDATE, or DELETE statement.</span></span>  
  
     <span data-ttu-id="5ea42-121">Se l'istruzione SQL può avere più set di risultati, chiamare [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) alla fine di ogni set di risultati per stabilire se siano presenti altri set di risultati da elaborare.</span><span class="sxs-lookup"><span data-stu-id="5ea42-121">If the SQL statement can have multiple result sets, call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) at the end of each result set to see if there are additional result sets to process.</span></span>  
  
7.  <span data-ttu-id="5ea42-122">Dopo l'elaborazione dei risultati, può essere necessario effettuare le seguenti azioni per consentire all'handle di istruzione di eseguire una nuova istruzione:</span><span class="sxs-lookup"><span data-stu-id="5ea42-122">After results are processed, the following actions may be necessary to make the statement handle available to execute a new statement:</span></span>  
  
    -   <span data-ttu-id="5ea42-123">Se [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) non è stato chiamato fino a quando non sia stato restituito SQL_NO_DATA, chiamare [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) per chiudere il cursore.</span><span class="sxs-lookup"><span data-stu-id="5ea42-123">If you did not call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) until it returned SQL_NO_DATA, call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) to close the cursor.</span></span>  
  
    -   <span data-ttu-id="5ea42-124">Se i marcatori di parametro sono stati associati alle variabili di programma, chiamare [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) con *Option* impostato su SQL_RESET_PARAMS per liberare i parametri associati.</span><span class="sxs-lookup"><span data-stu-id="5ea42-124">If you bound parameter markers to program variables, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with *Option* set to SQL_RESET_PARAMS to free the bound parameters.</span></span>  
  
    -   <span data-ttu-id="5ea42-125">Se le colonne del set di risultati sono state associate alle variabili di programma, chiamare [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) con *Option* impostato su SQL_UNBIND per liberare le colonne associate.</span><span class="sxs-lookup"><span data-stu-id="5ea42-125">If you bound result set columns to program variables, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with *Option* set to SQL_UNBIND to free the bound columns.</span></span>  
  
    -   <span data-ttu-id="5ea42-126">Per riutilizzare l'handle di istruzione, andare al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="5ea42-126">To reuse the statement handle, go to Step 2.</span></span>  
  
8.  <span data-ttu-id="5ea42-127">Chiamare [SQLFreeHandle](../../native-client-odbc-api/sqlfreehandle.md) con *HandleType* impostato su SQL_HANDLE_STMT per liberare l'handle di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5ea42-127">Call [SQLFreeHandle](../../native-client-odbc-api/sqlfreehandle.md) with a *HandleType* of SQL_HANDLE_STMT to free the statement handle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ea42-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ea42-128">See Also</span></span>  
 [<span data-ttu-id="5ea42-129">Procedure relative all'esecuzione di query &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="5ea42-129">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
