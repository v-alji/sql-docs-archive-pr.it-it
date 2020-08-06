---
title: Recuperare e aggiornare set di righe (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [ODBC]
ms.assetid: cf0eb3b4-8b72-49fc-a845-95edc360cf93
author: rothja
ms.author: jroth
ms.openlocfilehash: e09a3033e0883452ecd69b82c9375ed28c920da0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623237"
---
# <a name="fetch-and-update-rowsets-odbc"></a><span data-ttu-id="584cb-102">Recuperare e aggiornare set di righe (ODBC)</span><span class="sxs-lookup"><span data-stu-id="584cb-102">Fetch and Update Rowsets (ODBC)</span></span>
    
### <a name="to-fetch-and-update-rowsets"></a><span data-ttu-id="584cb-103">Per recuperare e aggiornare set di righe</span><span class="sxs-lookup"><span data-stu-id="584cb-103">To fetch and update rowsets</span></span>  
  
1.  <span data-ttu-id="584cb-104">Facoltativamente, chiamare [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) con SQL_ROW_ARRAY_SIZE per modificare il numero di righe (R) nel set di righe.</span><span class="sxs-lookup"><span data-stu-id="584cb-104">Optionally, call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) with SQL_ROW_ARRAY_SIZE to change the number of rows (R) in the rowset.</span></span>  
  
2.  <span data-ttu-id="584cb-105">Chiamare [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) o [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) per ottenere un set di righe.</span><span class="sxs-lookup"><span data-stu-id="584cb-105">Call [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) to get a rowset.</span></span>  
  
3.  <span data-ttu-id="584cb-106">Se si utilizzano colonne associate, utilizzare i valori dei dati e le lunghezze dei dati disponibili nei buffer delle colonne associate per il set di righe.</span><span class="sxs-lookup"><span data-stu-id="584cb-106">If bound columns are used, use the data values and data lengths now available in the bound column buffers for the rowset.</span></span>  
  
     <span data-ttu-id="584cb-107">Se vengono utilizzate colonne non associate, per ogni riga chiamare [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) con SQL_POSITION per impostare la posizione del cursore; quindi, per ogni colonna non associata:</span><span class="sxs-lookup"><span data-stu-id="584cb-107">If unbound columns are used, for each row call [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) with SQL_POSITION to set the cursor position; then, for each unbound column:</span></span>  
  
    -   <span data-ttu-id="584cb-108">Chiamare [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) una o più volte per ottenere i dati per le colonne non vincolate dopo l'ultima colonna associata del set di righe.</span><span class="sxs-lookup"><span data-stu-id="584cb-108">Call [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) one or more times to get the data for unbound columns after the last bound column of the rowset.</span></span> <span data-ttu-id="584cb-109">Le chiamate a [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) devono essere in ordine di numero di colonna crescente.</span><span class="sxs-lookup"><span data-stu-id="584cb-109">Calls to [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) should be in order of increasing column number.</span></span>  
  
    -   <span data-ttu-id="584cb-110">Chiamare [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) più volte per ottenere dati da una colonna di tipo text o image.</span><span class="sxs-lookup"><span data-stu-id="584cb-110">Call [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) multiple times to get data from a text or image column.</span></span>  
  
4.  <span data-ttu-id="584cb-111">Configurare tutte le colonne data-at-execution di tipo text o image.</span><span class="sxs-lookup"><span data-stu-id="584cb-111">Set up any data-at-execution text or image columns.</span></span>  
  
5.  <span data-ttu-id="584cb-112">Chiamare [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) o [SQLBulkOperations](https://go.microsoft.com/fwlink/?LinkId=58398) per impostare la posizione del cursore, aggiornare, aggiornare, eliminare o aggiungere righe all'interno del set di righe.</span><span class="sxs-lookup"><span data-stu-id="584cb-112">Call [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) or [SQLBulkOperations](https://go.microsoft.com/fwlink/?LinkId=58398) to set the cursor position, refresh, update, delete, or add row(s) within the rowset.</span></span>  
  
     <span data-ttu-id="584cb-113">Se si utilizzano colonne data-at-execution di tipo text o image per un'operazione di aggiornamento o di aggiunta, è necessario gestirle.</span><span class="sxs-lookup"><span data-stu-id="584cb-113">If data-at-execution text or image columns are used for an update or add operation, handle them.</span></span>  
  
6.  <span data-ttu-id="584cb-114">Facoltativamente, eseguire un'istruzione UPDATE o DELETE posizionata, specificando il nome del cursore, disponibile da [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md), e utilizzando un handle di istruzione diverso nella stessa connessione.</span><span class="sxs-lookup"><span data-stu-id="584cb-114">Optionally, execute a positioned UPDATE or DELETE statement, specifying the cursor name (available from [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md)) and using a different statement handle on the same connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="584cb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="584cb-115">See Also</span></span>  
 [<span data-ttu-id="584cb-116">Procedure per l'utilizzo di cursori &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="584cb-116">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](using-cursors-how-to-topics-odbc.md)  
  
  
