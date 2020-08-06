---
title: Utilizzare cursori (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], how to topics
ms.assetid: c502736f-bca0-45c3-ae25-d2ad52d296bf
author: rothja
ms.author: jroth
ms.openlocfilehash: e08156b03407c7a05d86278c11482a568d651f5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623233"
---
# <a name="use-cursors-odbc"></a><span data-ttu-id="4f264-102">Utilizzare cursori (ODBC)</span><span class="sxs-lookup"><span data-stu-id="4f264-102">Use Cursors (ODBC)</span></span>
    
### <a name="to-use-cursors"></a><span data-ttu-id="4f264-103">Per utilizzare i cursori</span><span class="sxs-lookup"><span data-stu-id="4f264-103">To use cursors</span></span>  
  
1.  <span data-ttu-id="4f264-104">Chiamare [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) per impostare gli attributi del cursore desiderati:</span><span class="sxs-lookup"><span data-stu-id="4f264-104">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the desired cursor attributes:</span></span>  
  
     <span data-ttu-id="4f264-105">Impostare gli attributi SQL_ATTR_CURSOR_TYPE e SQL_ATTR_CONCURRENCY (opzione consigliata).</span><span class="sxs-lookup"><span data-stu-id="4f264-105">Set the SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY attributes (this is the preferred option).</span></span>  
  
     <span data-ttu-id="4f264-106">Oppure</span><span class="sxs-lookup"><span data-stu-id="4f264-106">Or</span></span>  
  
     <span data-ttu-id="4f264-107">Impostare gli attributi SQL_CURSOR_SCROLLABLE e SQL_CURSOR_SENSITIVITY.</span><span class="sxs-lookup"><span data-stu-id="4f264-107">Set the SQL_CURSOR_SCROLLABLE and SQL_CURSOR_SENSITIVITY attributes.</span></span>  
  
2.  <span data-ttu-id="4f264-108">Chiamare [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) per impostare le dimensioni del set di righe usando l'attributo SQL_ATTR_ROW_ARRAY_SIZE.</span><span class="sxs-lookup"><span data-stu-id="4f264-108">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the rowset size by using the SQL_ATTR_ROW_ARRAY_SIZE attribute.</span></span>  
  
3.  <span data-ttu-id="4f264-109">Facoltativamente, è possibile chiamare [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) per impostare un nome di cursore se gli aggiornamenti posizionati verranno eseguiti usando la clausola WHERE CURRENT OF.</span><span class="sxs-lookup"><span data-stu-id="4f264-109">Optionally, call [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) to set a cursor name if positioned updates will be done by using the WHERE CURRENT OF clause.</span></span>  
  
4.  <span data-ttu-id="4f264-110">Eseguire l'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="4f264-110">Execute the SQL statement.</span></span>  
  
5.  <span data-ttu-id="4f264-111">Facoltativamente, è possibile chiamare [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md) per ottenere il nome del cursore se gli aggiornamenti posizionati verranno eseguiti usando la clausola WHERE CURRENT OF e se con [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) non è stato fornito un nome di cursore al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="4f264-111">Optionally, call [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md) to get the cursor name if positioned updates will be done by using the WHERE CURRENT OF clause and a cursor name was not supplied with [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) in Step 3.</span></span>  
  
6.  <span data-ttu-id="4f264-112">Chiamare [SQLNumResultCols](../../native-client-odbc-api/sqlnumresultcols.md) per ottenere il numero di colonne (C) nel set di righe.</span><span class="sxs-lookup"><span data-stu-id="4f264-112">Call [SQLNumResultCols](../../native-client-odbc-api/sqlnumresultcols.md) to get the number of columns (C) in the rowset.</span></span>  
  
     <span data-ttu-id="4f264-113">Utilizzare un'associazione per colonna.</span><span class="sxs-lookup"><span data-stu-id="4f264-113">Use column-wise binding.</span></span>  
  
     <span data-ttu-id="4f264-114">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="4f264-114">\- or -</span></span>  
  
     <span data-ttu-id="4f264-115">Utilizzare un'associazione per riga.</span><span class="sxs-lookup"><span data-stu-id="4f264-115">Use row-wise binding.</span></span>  
  
7.  <span data-ttu-id="4f264-116">Recuperare i set di righe dal cursore nel modo desiderato.</span><span class="sxs-lookup"><span data-stu-id="4f264-116">Fetch rowsets from the cursor as desired.</span></span>  
  
8.  <span data-ttu-id="4f264-117">Chiamare [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) per determinare se è disponibile un altro set di risultati.</span><span class="sxs-lookup"><span data-stu-id="4f264-117">Call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) to determine if another result set is available.</span></span>  
  
    -   <span data-ttu-id="4f264-118">Se viene restituito SQL_SUCCESS, è disponibile un altro set di risultati.</span><span class="sxs-lookup"><span data-stu-id="4f264-118">If it returns SQL_SUCCESS, another result set is available.</span></span>  
  
    -   <span data-ttu-id="4f264-119">Se viene restituito SQL_NO_DATA, non è più disponibile alcun set di risultati.</span><span class="sxs-lookup"><span data-stu-id="4f264-119">If it returns SQL_NO_DATA, no more result sets are available.</span></span>  
  
    -   <span data-ttu-id="4f264-120">Se viene restituito SQL_SUCCESS_WITH_INFO o SQL_ERROR, chiamare [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) per determinare se è disponibile l'output da un'istruzione PRINT o RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="4f264-120">If it returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) to determine if the output from a PRINT or RAISERROR statement is available.</span></span>  
  
     <span data-ttu-id="4f264-121">Se si utilizzano parametri di istruzione associati per i parametri di output o il valore restituito di una stored procedure, utilizzare i dati disponibili nei buffer dei parametri associati.</span><span class="sxs-lookup"><span data-stu-id="4f264-121">If bound statement parameters are used for output parameters or the return value of a stored procedure, use the data now available in the bound parameter buffers.</span></span>  
  
     <span data-ttu-id="4f264-122">Quando si utilizzano parametri associati, ogni chiamata a [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) o [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) eseguirà l'istruzione SQL S volte, in cui S è il numero di elementi nella matrice dei parametri associati.</span><span class="sxs-lookup"><span data-stu-id="4f264-122">When bound parameters are used, each call to [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) or [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) will have executed the SQL statement S times, where S is the number of elements in the array of bound parameters.</span></span> <span data-ttu-id="4f264-123">Di conseguenza, vi saranno S set di risultati da elaborare, in cui ogni set di risultati comprende tutti i set di risultati, i parametri di output e i codici restituiti utilizzati normalmente da una singola esecuzione dell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="4f264-123">This means that there will be S sets of results to process, where each set of results comprises all of the result sets, output parameters, and return codes usually returned by a single execution of the SQL statement.</span></span>  
  
     <span data-ttu-id="4f264-124">Si noti che quando un set di risultati contiene righe di calcolo, ogni riga di calcolo viene resa disponibile come set di risultati distinto.</span><span class="sxs-lookup"><span data-stu-id="4f264-124">Note that when a result set contains compute rows, each compute row is made available as a separate result set.</span></span> <span data-ttu-id="4f264-125">Tali set di risultati di calcolo vengono intercalati all'interno delle normali righe e le suddividono in più set di risultati.</span><span class="sxs-lookup"><span data-stu-id="4f264-125">These compute result sets are interspersed within the normal rows and break normal rows into multiple result sets.</span></span>  
  
9. <span data-ttu-id="4f264-126">Facoltativamente, è possibile chiamare [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) con SQL_UNBIND per rilasciare qualsiasi buffer delle colonne associate.</span><span class="sxs-lookup"><span data-stu-id="4f264-126">Optionally, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with SQL_UNBIND to release any bound column buffers.</span></span>  
  
10. <span data-ttu-id="4f264-127">Se è disponibile un altro set di risultati, andare al passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="4f264-127">If another result set is available, go to Step 6.</span></span>  
  
     <span data-ttu-id="4f264-128">Nel passaggio 9 la chiamata a [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) in un set di risultati parzialmente elaborato cancella il resto del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="4f264-128">In Step 9, calling [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) on a partially processed result set clears the remainder of the result set.</span></span> <span data-ttu-id="4f264-129">Un altro modo per cancellare un set di risultati parzialmente elaborato consiste nel chiamare [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="4f264-129">Another way to clear a partially processed result set is to call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
     <span data-ttu-id="4f264-130">È possibile controllare il tipo di cursore utilizzato impostando SQL_ATTR_CURSOR_TYPE e SQL_ATTR_CONCURRENCY oppure impostando SQL_ATTR_CURSOR_SENSITIVITY e SQL_ATTR_CURSOR_SCROLLABLE.</span><span class="sxs-lookup"><span data-stu-id="4f264-130">You can control the type of cursor used by setting either SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY, or by setting SQL_ATTR_CURSOR_SENSITIVITY and SQL_ATTR_CURSOR_SCROLLABLE.</span></span> <span data-ttu-id="4f264-131">È consigliabile non combinare i due metodi di definizione del comportamento del cursore.</span><span class="sxs-lookup"><span data-stu-id="4f264-131">You should not mix the two methods of specifying cursor behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f264-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f264-132">See Also</span></span>  
 [<span data-ttu-id="4f264-133">Procedure per l'utilizzo di cursori &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4f264-133">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](using-cursors-how-to-topics-odbc.md)  
  
  
