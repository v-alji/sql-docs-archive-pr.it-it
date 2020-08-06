---
title: Scorrimento e recupero di righe | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- scrollable cursors [SQL Server]
- SQL Server Native Client ODBC driver, cursors
- SQLFetchScroll function
- ODBC applications, cursors
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- fetching [ODBC]
- ODBC cursors, scrolling rows
ms.assetid: 9109f10d-326b-4a6d-8c97-831f60da8c4c
author: rothja
ms.author: jroth
ms.openlocfilehash: 97586f82ddddb79581b0f9c027aa60d7822b472c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723828"
---
# <a name="scrolling-and-fetching-rows"></a><span data-ttu-id="97e5b-102">Scorrimento e recupero di righe</span><span class="sxs-lookup"><span data-stu-id="97e5b-102">Scrolling and Fetching Rows</span></span>
  <span data-ttu-id="97e5b-103">Per utilizzare un cursore scorrevole, un'applicazione ODBC deve effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="97e5b-103">To use a scrollable cursor, an ODBC application must:</span></span>  
  
-   <span data-ttu-id="97e5b-104">Impostare le funzionalità del cursore utilizzando [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="97e5b-104">Set the cursor capabilities using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
-   <span data-ttu-id="97e5b-105">Aprire il cursore utilizzando **SQLExecute** o **SQLExecDirect**.</span><span class="sxs-lookup"><span data-stu-id="97e5b-105">Open the cursor using **SQLExecute** or **SQLExecDirect**.</span></span>  
  
-   <span data-ttu-id="97e5b-106">Scorrere e recuperare righe utilizzando **SQLFetch** o [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="97e5b-106">Scroll and fetch rows using **SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span></span>  
  
 <span data-ttu-id="97e5b-107">Sia **SQLFetch** che **SQLFetchSroll** possono recuperare blocchi di righe alla volta.</span><span class="sxs-lookup"><span data-stu-id="97e5b-107">Both **SQLFetch** and **SQLFetchSroll** can fetch blocks of rows at a time.</span></span> <span data-ttu-id="97e5b-108">Il numero di righe restituite viene specificato utilizzando **SQLSetStmtAttr** per impostare il parametro SQL_ATTR_ROW_ARRAY_SIZE.</span><span class="sxs-lookup"><span data-stu-id="97e5b-108">The number of rows returned is specified by using **SQLSetStmtAttr** to set the SQL_ATTR_ROW_ARRAY_SIZE parameter.</span></span>  
  
 <span data-ttu-id="97e5b-109">Le applicazioni ODBC possono utilizzare **SQLFetch** per eseguire il recupero tramite un cursore di sola trasmissione.</span><span class="sxs-lookup"><span data-stu-id="97e5b-109">ODBC applications can use **SQLFetch** to fetch through a forward-only cursor.</span></span>  
  
 <span data-ttu-id="97e5b-110">**SQLFetchScroll** viene utilizzato per scorrere un cursore.</span><span class="sxs-lookup"><span data-stu-id="97e5b-110">**SQLFetchScroll** is used to scroll around a cursor.</span></span> <span data-ttu-id="97e5b-111">**SQLFetchScroll** supporta il recupero dei set di righe successivo, precedente, primo e ultimo, oltre al recupero relativo (recuperare il set di righe *n* righe dall'inizio del set di righe corrente) e il recupero assoluto (recuperare il set di righe a partire dalla riga *n*).</span><span class="sxs-lookup"><span data-stu-id="97e5b-111">**SQLFetchScroll** supports fetching the next, prior, first, and last rowsets in addition to relative fetching (fetch the rowset *n* rows from the start of the current rowset) and absolute fetching (fetch the rowset starting at row *n*).</span></span> <span data-ttu-id="97e5b-112">Se *n* è negativo in un recupero assoluto, le righe vengono conteggiate dalla fine del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="97e5b-112">If *n* is negative in an absolute fetch, rows are counted from the end of the result set.</span></span> <span data-ttu-id="97e5b-113">Un recupero assoluto della riga -1 indica il recupero del set di righe che inizia con l'ultima riga nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="97e5b-113">An absolute fetch of row -1 means to fetch the rowset that starts with the last row in the result set.</span></span>  
  
 <span data-ttu-id="97e5b-114">È probabile che le applicazioni che utilizzano **SQLFetchScroll** solo per le funzionalità del cursore a blocchi, ad esempio i report, attraversino il set di risultati una sola volta, utilizzando solo l'opzione per recuperare il set di righe successivo.</span><span class="sxs-lookup"><span data-stu-id="97e5b-114">Applications that use **SQLFetchScroll** only for its block cursor capabilities, such as reports, are likely to pass through the result set a single time, using only the option to fetch the next rowset.</span></span> <span data-ttu-id="97e5b-115">Le applicazioni basate sullo schermo, d'altra parte, possono sfruttare tutte le funzionalità di **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="97e5b-115">Screen-based applications, on the other hand, can take advantage of all the capabilities of **SQLFetchScroll**.</span></span> <span data-ttu-id="97e5b-116">Se l'applicazione imposta le dimensioni del set di righe sul numero di righe visualizzate sullo schermo e associa i buffer dello schermo al set di risultati, può convertire le operazioni della barra di scorrimento direttamente in chiamate a **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="97e5b-116">If the application sets the rowset size to the number of rows displayed on the screen and binds the screen buffers to the result set, it can translate scroll bar operations directly to calls to **SQLFetchScroll**.</span></span>  
  
|<span data-ttu-id="97e5b-117">Operazione della barra di scorrimento</span><span class="sxs-lookup"><span data-stu-id="97e5b-117">Scroll bar operation</span></span>|<span data-ttu-id="97e5b-118">Opzione di scorrimento SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="97e5b-118">SQLFetchScroll scrolling option</span></span>|  
|--------------------------|-------------------------------------|  
|<span data-ttu-id="97e5b-119">Su di una pagina</span><span class="sxs-lookup"><span data-stu-id="97e5b-119">Page up</span></span>|<span data-ttu-id="97e5b-120">SQL_FETCH_PRIOR</span><span class="sxs-lookup"><span data-stu-id="97e5b-120">SQL_FETCH_PRIOR</span></span>|  
|<span data-ttu-id="97e5b-121">Giù di una pagina</span><span class="sxs-lookup"><span data-stu-id="97e5b-121">Page down</span></span>|<span data-ttu-id="97e5b-122">SQL_FETCH_NEXT</span><span class="sxs-lookup"><span data-stu-id="97e5b-122">SQL_FETCH_NEXT</span></span>|  
|<span data-ttu-id="97e5b-123">Su di una riga</span><span class="sxs-lookup"><span data-stu-id="97e5b-123">Line up</span></span>|<span data-ttu-id="97e5b-124">SQL_FETCH_RELATIVE con FetchOffset uguale a-1</span><span class="sxs-lookup"><span data-stu-id="97e5b-124">SQL_FETCH_RELATIVE with FetchOffset equal to -1</span></span>|  
|<span data-ttu-id="97e5b-125">Giù di una riga</span><span class="sxs-lookup"><span data-stu-id="97e5b-125">Line down</span></span>|<span data-ttu-id="97e5b-126">SQL_FETCH_RELATIVE con FetchOffset uguale a 1</span><span class="sxs-lookup"><span data-stu-id="97e5b-126">SQL_FETCH_RELATIVE with FetchOffset equal to 1</span></span>|  
|<span data-ttu-id="97e5b-127">Casella di scorrimento all'inizio</span><span class="sxs-lookup"><span data-stu-id="97e5b-127">Scroll box to top</span></span>|<span data-ttu-id="97e5b-128">SQL_FETCH_FIRST</span><span class="sxs-lookup"><span data-stu-id="97e5b-128">SQL_FETCH_FIRST</span></span>|  
|<span data-ttu-id="97e5b-129">Casella di scorrimento alla fine</span><span class="sxs-lookup"><span data-stu-id="97e5b-129">Scroll box to bottom</span></span>|<span data-ttu-id="97e5b-130">SQL_FETCH_LAST</span><span class="sxs-lookup"><span data-stu-id="97e5b-130">SQL_FETCH_LAST</span></span>|  
|<span data-ttu-id="97e5b-131">Posizione casuale della casella di scorrimento</span><span class="sxs-lookup"><span data-stu-id="97e5b-131">Random scroll box position</span></span>|<span data-ttu-id="97e5b-132">SQL_FETCH_ABSOLUTE</span><span class="sxs-lookup"><span data-stu-id="97e5b-132">SQL_FETCH_ABSOLUTE</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="97e5b-133">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="97e5b-133">In This Section</span></span>  
  
-   [<span data-ttu-id="97e5b-134">Applicazione di segnalibri alle righe in ODBC</span><span class="sxs-lookup"><span data-stu-id="97e5b-134">Bookmarking Rows in ODBC</span></span>](scrolling-and-fetching-rows-bookmarking-rows-in-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="97e5b-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97e5b-135">See Also</span></span>  
 [<span data-ttu-id="97e5b-136">Utilizzo di cursori &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="97e5b-136">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
