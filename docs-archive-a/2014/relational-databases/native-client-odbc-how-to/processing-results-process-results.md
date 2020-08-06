---
title: Risultati processo (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- processing results [ODBC]
ms.assetid: 4810fe3f-78ee-4f0d-8bcc-a4659fbcf46f
author: rothja
ms.author: jroth
ms.openlocfilehash: 8a22e9d7280f88de7799c31d2d0611e5299043d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722759"
---
# <a name="process-results-odbc"></a><span data-ttu-id="b8f15-102">Elaborare i risultati (ODBC)</span><span class="sxs-lookup"><span data-stu-id="b8f15-102">Process Results (ODBC)</span></span>
    
### <a name="to-process-results"></a><span data-ttu-id="b8f15-103">Per elaborare i risultati</span><span class="sxs-lookup"><span data-stu-id="b8f15-103">To process results</span></span>  
  
1.  <span data-ttu-id="b8f15-104">Recuperare le informazioni sul set di risultati.</span><span class="sxs-lookup"><span data-stu-id="b8f15-104">Retrieve result set information.</span></span>  
  
2.  <span data-ttu-id="b8f15-105">Se si usano colonne associate, per ogni colonna con cui si intende eseguire l'associazione, chiamare [SQLBindCol](../native-client-odbc-api/sqlbindcol.md) per associare un buffer del programma alla colonna.</span><span class="sxs-lookup"><span data-stu-id="b8f15-105">If bound columns are used, for each column you want to bind to, call [SQLBindCol](../native-client-odbc-api/sqlbindcol.md) to bind a program buffer to the column.</span></span>  
  
3.  <span data-ttu-id="b8f15-106">Per ogni riga del set di risultati, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8f15-106">For each row in the result set:</span></span>  
  
    -   <span data-ttu-id="b8f15-107">Chiamare [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) per ottenere la riga successiva.</span><span class="sxs-lookup"><span data-stu-id="b8f15-107">Call [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) to get the next row.</span></span>  
  
    -   <span data-ttu-id="b8f15-108">Se si utilizzano colonne associate, utilizzare i dati disponibili nei relativi buffer.</span><span class="sxs-lookup"><span data-stu-id="b8f15-108">If bound columns are used, use the data now available in the bound column buffers.</span></span>  
  
    -   <span data-ttu-id="b8f15-109">Se si usano colonne non associate, chiamare [SQLGetData](../native-client-odbc-api/sqlgetdata.md) una o più volte per ottenere i dati relativi alle colonne non associate dopo l'ultima colonna associata.</span><span class="sxs-lookup"><span data-stu-id="b8f15-109">If unbound columns are used, call [SQLGetData](../native-client-odbc-api/sqlgetdata.md) one or more times to get the data for unbound columns after the last bound column.</span></span> <span data-ttu-id="b8f15-110">Le chiamate a `SQLGetData` devono essere effettuate nell'ordine di numero di colonna crescente.</span><span class="sxs-lookup"><span data-stu-id="b8f15-110">Calls to `SQLGetData` should be in increasing order of column number.</span></span>  
  
    -   <span data-ttu-id="b8f15-111">Chiamare `SQLGetData` più volte per ottenere dati da una colonna di tipo text o image.</span><span class="sxs-lookup"><span data-stu-id="b8f15-111">Call `SQLGetData` multiple times to get data from a text or image column.</span></span>  
  
4.  <span data-ttu-id="b8f15-112">Quando [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) segnala la fine del set di risultati restituendo SQL_NO_DATA, chiamare [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) per determinare se è disponibile un altro set di risultati.</span><span class="sxs-lookup"><span data-stu-id="b8f15-112">When [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) signals the end of the result set by returning SQL_NO_DATA, call [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) to determine if another result set is available.</span></span>  
  
    -   <span data-ttu-id="b8f15-113">Se viene restituito SQL_SUCCESS, è disponibile un altro set di risultati.</span><span class="sxs-lookup"><span data-stu-id="b8f15-113">If it returns SQL_SUCCESS, another result set is available.</span></span>  
  
    -   <span data-ttu-id="b8f15-114">Se viene restituito SQL_NO_DATA, non è più disponibile alcun set di risultati.</span><span class="sxs-lookup"><span data-stu-id="b8f15-114">If it returns SQL_NO_DATA, no more result sets are available.</span></span>  
  
    -   <span data-ttu-id="b8f15-115">Se viene restituito SQL_SUCCESS_WITH_INFO o SQL_ERROR, chiamare [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) per determinare se è disponibile l'output da un'istruzione PRINT o RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="b8f15-115">If it returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) to determine if the output from a PRINT or RAISERROR statement is available.</span></span>  
  
         <span data-ttu-id="b8f15-116">Se si utilizzano parametri di istruzione associati per i parametri di output o il valore restituito di una stored procedure, utilizzare i dati disponibili nei buffer dei parametri associati.</span><span class="sxs-lookup"><span data-stu-id="b8f15-116">If bound statement parameters are used for output parameters or the return value of a stored procedure, use the data now available in the bound parameter buffers.</span></span> <span data-ttu-id="b8f15-117">Inoltre, quando si utilizzano parametri associati, ogni chiamata a [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) o [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) eseguirà l'istruzione SQL *S* volte, dove *S* è il numero di elementi nella matrice dei parametri associati.</span><span class="sxs-lookup"><span data-stu-id="b8f15-117">Also, when bound parameters are used, each call to [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) or [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) will have executed the SQL statement *S* times, where *S* is the number of elements in the array of bound parameters.</span></span> <span data-ttu-id="b8f15-118">Ciò significa che saranno presenti *i* set di risultati da elaborare, in cui ogni set di risultati comprende tutti i set di risultati, i parametri di output e i codici restituiti restituiti in genere da una singola esecuzione dell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="b8f15-118">This means that there will be *S* sets of results to process, where each set of results comprises all of the result sets, output parameters, and return codes usually returned by a single execution of the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b8f15-119">Quando un set di risultati contiene righe di calcolo, ogni riga di calcolo viene resa disponibile come set di risultati distinto.</span><span class="sxs-lookup"><span data-stu-id="b8f15-119">When a result set contains compute rows, each compute row is made available as a separate result set.</span></span> <span data-ttu-id="b8f15-120">Tali set di risultati di calcolo vengono intercalati all'interno delle normali righe e le suddividono in più set di risultati.</span><span class="sxs-lookup"><span data-stu-id="b8f15-120">These compute result sets are interspersed within the normal rows and break normal rows into multiple result sets.</span></span>  
  
5.  <span data-ttu-id="b8f15-121">Facoltativamente, è possibile chiamare [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) con SQL_UNBIND per rilasciare qualsiasi buffer delle colonne associate.</span><span class="sxs-lookup"><span data-stu-id="b8f15-121">Optionally, call [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with SQL_UNBIND to release any bound column buffers.</span></span>  
  
6.  <span data-ttu-id="b8f15-122">Se è disponibile un altro set di risultati, andare al passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="b8f15-122">If another result set is available, go to Step 1.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8f15-123">Per annullare l'elaborazione di un set di risultati prima che [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) restituisca SQL_NO_DATA, chiamare [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="b8f15-123">To cancel processing a result set before [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) returns SQL_NO_DATA, call [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8f15-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8f15-124">See Also</span></span>  
 [<span data-ttu-id="b8f15-125">Procedure per l'elaborazione dei risultati &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b8f15-125">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
  
