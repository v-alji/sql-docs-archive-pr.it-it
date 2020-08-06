---
title: Utilizzo di cursori (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC cursors, about ODBC cursors
- ODBC applications, cursors
- cursors [ODBC]
- ODBC cursors
ms.assetid: 51322f92-0d76-44c9-9c33-9223676cf1d3
author: rothja
ms.author: jroth
ms.openlocfilehash: 61afedab4f4a1e309a08d9c2421ca7889811da8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723820"
---
# <a name="using-cursors-odbc"></a><span data-ttu-id="20a8a-102">Uso dei cursori (ODBC)</span><span class="sxs-lookup"><span data-stu-id="20a8a-102">Using Cursors (ODBC)</span></span>
  <span data-ttu-id="20a8a-103">ODBC supporta un modello di cursore che consente:</span><span class="sxs-lookup"><span data-stu-id="20a8a-103">ODBC supports a cursor model that allows:</span></span>  
  
-   <span data-ttu-id="20a8a-104">Diversi tipi di cursori.</span><span class="sxs-lookup"><span data-stu-id="20a8a-104">Several types of cursors.</span></span>  
  
-   <span data-ttu-id="20a8a-105">Scorrimento e posizionamento all'interno di un cursore.</span><span class="sxs-lookup"><span data-stu-id="20a8a-105">Scrolling and positioning within a cursor.</span></span>  
  
-   <span data-ttu-id="20a8a-106">Diverse opzioni di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="20a8a-106">Several concurrency options.</span></span>  
  
-   <span data-ttu-id="20a8a-107">Aggiornamenti posizionati.</span><span class="sxs-lookup"><span data-stu-id="20a8a-107">Positioned updates.</span></span>  
  
 <span data-ttu-id="20a8a-108">Le applicazioni ODBC raramente dichiarano e aprono cursori o utilizzano istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] correlate ai cursori.</span><span class="sxs-lookup"><span data-stu-id="20a8a-108">ODBC applications rarely declare and open cursors or use any cursor-related [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="20a8a-109">ODBC apre automaticamente un cursore per ogni set di risultati restituito da un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="20a8a-109">ODBC automatically opens a cursor for every result set returned from an SQL statement.</span></span> <span data-ttu-id="20a8a-110">Le caratteristiche dei cursori vengono controllate dagli attributi di istruzione impostati con [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) prima dell'esecuzione dell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="20a8a-110">The characteristics of the cursors are controlled by statement attributes set with [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) before the SQL statement is executed.</span></span> <span data-ttu-id="20a8a-111">Le funzioni delle API ODBC per l'elaborazione di set di risultati supportano l'intervallo completo delle funzionalità del cursore, inclusi il recupero, lo scorrimento e gli aggiornamenti posizionati.</span><span class="sxs-lookup"><span data-stu-id="20a8a-111">The ODBC API functions for processing result sets support the full range of cursor functionality, including fetching, scrolling, and positioned updates.</span></span>  
  
 <span data-ttu-id="20a8a-112">Di seguito viene presentato un confronto tra il funzionamento dei cursori nelle applicazioni ODBC e negli script [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20a8a-112">This is a comparison of how [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts and ODBC applications work with cursors.</span></span>  
  
|<span data-ttu-id="20a8a-113">Action</span><span class="sxs-lookup"><span data-stu-id="20a8a-113">Action</span></span>|[!INCLUDE[tsql](../../includes/tsql-md.md)]|<span data-ttu-id="20a8a-114">ODBC</span><span class="sxs-lookup"><span data-stu-id="20a8a-114">ODBC</span></span>|  
|------------|------------------------|----------|  
|<span data-ttu-id="20a8a-115">Definire il comportamento del cursore</span><span class="sxs-lookup"><span data-stu-id="20a8a-115">Define cursor behavior</span></span>|<span data-ttu-id="20a8a-116">Specificare tramite parametri DECLARE CURSOR</span><span class="sxs-lookup"><span data-stu-id="20a8a-116">Specify through DECLARE CURSOR parameters</span></span>|<span data-ttu-id="20a8a-117">Impostare gli attributi del cursore utilizzando [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)</span><span class="sxs-lookup"><span data-stu-id="20a8a-117">Set cursor attributes by using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)</span></span>|  
|<span data-ttu-id="20a8a-118">Aprire un cursore</span><span class="sxs-lookup"><span data-stu-id="20a8a-118">Open a cursor</span></span>|<span data-ttu-id="20a8a-119">DICHIARARE il cursore aperto *cursor_name*</span><span class="sxs-lookup"><span data-stu-id="20a8a-119">DECLARE CURSOR OPEN *cursor_name*</span></span>|<span data-ttu-id="20a8a-120">**SQLExecDirect** o **SQLExecute**</span><span class="sxs-lookup"><span data-stu-id="20a8a-120">**SQLExecDirect** or **SQLExecute**</span></span>|  
|<span data-ttu-id="20a8a-121">Recuperare righe</span><span class="sxs-lookup"><span data-stu-id="20a8a-121">Fetch rows</span></span>|<span data-ttu-id="20a8a-122">FETCH</span><span class="sxs-lookup"><span data-stu-id="20a8a-122">FETCH</span></span>|<span data-ttu-id="20a8a-123">**SQLFetch** o [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)</span><span class="sxs-lookup"><span data-stu-id="20a8a-123">**SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)</span></span>|  
|<span data-ttu-id="20a8a-124">Aggiornamento posizionato</span><span class="sxs-lookup"><span data-stu-id="20a8a-124">Positioned update</span></span>|<span data-ttu-id="20a8a-125">Clausola WHERE CURRENT OF su UPDATE o DELETE</span><span class="sxs-lookup"><span data-stu-id="20a8a-125">WHERE CURRENT OF clause on UPDATE or DELETE</span></span>|<span data-ttu-id="20a8a-126">**SQLSetPos**</span><span class="sxs-lookup"><span data-stu-id="20a8a-126">**SQLSetPos**</span></span>|  
|<span data-ttu-id="20a8a-127">Chiudere un cursore</span><span class="sxs-lookup"><span data-stu-id="20a8a-127">Close a cursor</span></span>|<span data-ttu-id="20a8a-128">Chiudi *cursor_name* deallocare</span><span class="sxs-lookup"><span data-stu-id="20a8a-128">CLOSE *cursor_name* DEALLOCATE</span></span>|[<span data-ttu-id="20a8a-129">SQLCloseCursor</span><span class="sxs-lookup"><span data-stu-id="20a8a-129">SQLCloseCursor</span></span>](../native-client-odbc-api/sqlclosecursor.md)|  
  
 <span data-ttu-id="20a8a-130">I cursori server implementati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supportano la funzionalità del modello del cursore ODBC.</span><span class="sxs-lookup"><span data-stu-id="20a8a-130">The server cursors implemented in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support the functionality of the ODBC cursor model.</span></span> <span data-ttu-id="20a8a-131">Il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client utilizza cursori server per supportare la funzionalità del cursore dell'API ODBC.</span><span class="sxs-lookup"><span data-stu-id="20a8a-131">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client driver uses server cursors to support the cursor functionality of the ODBC API.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20a8a-132">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="20a8a-132">In This Section</span></span>  
  
-   [<span data-ttu-id="20a8a-133">Modalità di implementazione dei cursori</span><span class="sxs-lookup"><span data-stu-id="20a8a-133">How Cursors Are Implemented</span></span>](implementation/how-cursors-are-implemented.md)  
  
-   [<span data-ttu-id="20a8a-134">Tipi di cursore</span><span class="sxs-lookup"><span data-stu-id="20a8a-134">Cursor Types</span></span>](cursor-types.md)  
  
-   [<span data-ttu-id="20a8a-135">Comportamenti dei cursori</span><span class="sxs-lookup"><span data-stu-id="20a8a-135">Cursor Behaviors</span></span>](cursor-behaviors.md)  
  
-   [<span data-ttu-id="20a8a-136">Proprietà del cursore</span><span class="sxs-lookup"><span data-stu-id="20a8a-136">Cursor Properties</span></span>](properties/cursor-properties.md)  
  
-   [<span data-ttu-id="20a8a-137">Dettagli sulla programmazione dei cursori &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="20a8a-137">Cursor Programming Details &#40;ODBC&#41;</span></span>](programming/cursor-programming-details-odbc.md)  
  
-   [<span data-ttu-id="20a8a-138">Scorrimento e recupero di righe</span><span class="sxs-lookup"><span data-stu-id="20a8a-138">Scrolling and Fetching Rows</span></span>](../native-client-ole-db-rowsets/fetching-rows.md)  
  
-   [<span data-ttu-id="20a8a-139">Aggiornamenti posizionati &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="20a8a-139">Positioned Updates &#40;ODBC&#41;</span></span>](positioned-updates-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="20a8a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20a8a-140">See Also</span></span>  
 <span data-ttu-id="20a8a-141">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="20a8a-141">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 <span data-ttu-id="20a8a-142">[Chiudi &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/close-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="20a8a-142">[CLOSE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/close-transact-sql) </span></span>  
 <span data-ttu-id="20a8a-143">[Cursori](../../relational-databases/cursors.md) </span><span class="sxs-lookup"><span data-stu-id="20a8a-143">[Cursors](../../relational-databases/cursors.md) </span></span>  
 <span data-ttu-id="20a8a-144">[Deallocazione &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/deallocate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="20a8a-144">[DEALLOCATE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/deallocate-transact-sql) </span></span>  
 <span data-ttu-id="20a8a-145">[DECLARE CURSOR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="20a8a-145">[DECLARE CURSOR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span></span>  
 <span data-ttu-id="20a8a-146">[FETCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/fetch-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="20a8a-146">[FETCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/fetch-transact-sql) </span></span>  
 [<span data-ttu-id="20a8a-147">OPEN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="20a8a-147">OPEN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/open-transact-sql)  
  
  
