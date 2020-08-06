---
title: Dimensioni set di righe cursore | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], rowset size
- ODBC cursors, rowset size
- rowsets [ODBC]
ms.assetid: 2febe2ae-fdc1-490e-a79f-c516bc8e7c3f
author: rothja
ms.author: jroth
ms.openlocfilehash: 83c4e55025e6e3724f354f022760b7ba1e2f10e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635545"
---
# <a name="cursor-rowset-size"></a><span data-ttu-id="ca5d5-102">Dimensione del set di righe del cursore</span><span class="sxs-lookup"><span data-stu-id="ca5d5-102">Cursor Rowset Size</span></span>
  <span data-ttu-id="ca5d5-103">I cursori ODBC non si limitano a recuperare una sola riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-103">ODBC cursors are not limited to fetching one row at a time.</span></span> <span data-ttu-id="ca5d5-104">Possono recuperare più righe in ogni chiamata a **SQLFetch** o [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="ca5d5-104">They can retrieve multiple rows in each call to **SQLFetch** or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md).</span></span> <span data-ttu-id="ca5d5-105">Quando si utilizza un database client/server come Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], è consigliabile recuperare diverse righe contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-105">When you are working with a client/server database such as Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it is more efficient to fetch several rows at a time.</span></span> <span data-ttu-id="ca5d5-106">Il numero di righe restituite in un recupero è denominato dimensione del set di righe e viene specificato tramite il SQL_ATTR_ROW_ARRAY_SIZE di [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="ca5d5-106">The number of rows returned on a fetch is called the rowset size and is specified by using the SQL_ATTR_ROW_ARRAY_SIZE of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
```  
SQLUINTEGER uwRowsize;  
SQLSetStmtAttr(m_hstmt, SQL_ATTR_ROW_ARRAY_SIZE, (SQLPOINTER)uwRowsetSize, SQL_IS_UINTEGER);  
```  
  
 <span data-ttu-id="ca5d5-107">I cursori con una dimensione del set di righe maggiore di 1 vengono definiti cursori a blocchi.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-107">Cursors with a rowset size greater than 1 are called block cursors.</span></span>  
  
 <span data-ttu-id="ca5d5-108">Sono disponibili due opzioni per associare le colonne dei set di risultati per i cursori a blocchi:</span><span class="sxs-lookup"><span data-stu-id="ca5d5-108">There are two options for binding result set columns for block cursors:</span></span>  
  
-   <span data-ttu-id="ca5d5-109">Associazione per colonna</span><span class="sxs-lookup"><span data-stu-id="ca5d5-109">Column-wise binding</span></span>  
  
     <span data-ttu-id="ca5d5-110">Ogni colonna viene associata a una matrice di variabili.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-110">Each column is bound to an array of variables.</span></span> <span data-ttu-id="ca5d5-111">Ogni matrice include lo stesso numero di elementi come dimensione del set di righe.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-111">Each array has the same number of elements as the rowset size.</span></span>  
  
-   <span data-ttu-id="ca5d5-112">Associazione per riga</span><span class="sxs-lookup"><span data-stu-id="ca5d5-112">Row-wise binding</span></span>  
  
     <span data-ttu-id="ca5d5-113">Una matrice viene compilata utilizzando strutture che contengono i dati e gli indicatori per tutte le colonne di una riga.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-113">An array is built using structures that hold the data and indicators for all the columns in a row.</span></span> <span data-ttu-id="ca5d5-114">La matrice include lo stesso numero di strutture come dimensione del set di righe.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-114">The array has the same number of structures as the rowset size.</span></span>  
  
 <span data-ttu-id="ca5d5-115">Quando si utilizza l'associazione per colonna o per riga, ogni chiamata a **SQLFetch** o **SQLFetchScroll** riempie le matrici associate con i dati del set di righe recuperato.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-115">When either column-wise or row-wise binding is used, each call to **SQLFetch** or **SQLFetchScroll** fills the bound arrays with data from the rowset retrieved.</span></span>  
  
 <span data-ttu-id="ca5d5-116">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) può essere utilizzato anche per recuperare i dati delle colonne da un cursore a blocchi.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-116">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) can also be used to retrieve column data from a block cursor.</span></span> <span data-ttu-id="ca5d5-117">Poiché **SQLGetData** funziona una riga alla volta, è necessario chiamare **SQLSetPos** per impostare una riga specifica nel set di righe come riga corrente prima di chiamare **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-117">Because **SQLGetData** works one row at a time, **SQLSetPos** must be called to set a specific row in the rowset as the current row before calling **SQLGetData**.</span></span>  
  
 <span data-ttu-id="ca5d5-118">Il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native Client offre un'ottimizzazione utilizzando i set di righe per recuperare rapidamente un intero set di risultati.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-118">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver offers an optimization using rowsets to retrieve a whole result set quickly.</span></span> <span data-ttu-id="ca5d5-119">Per utilizzare questa ottimizzazione, impostare gli attributi del cursore sulle impostazioni predefinite (di sola lettura, di sola lettura, dimensioni del set di righe = 1) al momento della chiamata a **SQLExecDirect** o **SQLExecute** .</span><span class="sxs-lookup"><span data-stu-id="ca5d5-119">To use this optimization, set the cursor attributes to their defaults (forward-only, read-only, rowset size = 1) at the time **SQLExecDirect** or **SQLExecute** is called.</span></span> <span data-ttu-id="ca5d5-120">Il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native Client configura un set di risultati predefinito.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-120">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver sets up a default result set.</span></span> <span data-ttu-id="ca5d5-121">Questa soluzione risulta più efficiente dei cursori del server quando si trasferiscono risultati al client senza scorrimento.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-121">This is more efficient than server cursors when transferring results to the client without scrolling.</span></span> <span data-ttu-id="ca5d5-122">Al termine dell'esecuzione dell'istruzione, aumentare la dimensione del set di righe e utilizzare l'associazione per colonna o per riga.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-122">After the statement has been executed, increase the rowset size and use either column-wise or row-wise binding.</span></span> <span data-ttu-id="ca5d5-123">Questo consente di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizzare un set di risultati predefinito per inviare le righe di risultati in modo efficiente al client, mentre il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native client estrae continuamente le righe dai buffer di rete nel client.</span><span class="sxs-lookup"><span data-stu-id="ca5d5-123">This lets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] use a default result set to send result rows efficiently to the client, while the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver continuously pulls rows from the network buffers on the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca5d5-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca5d5-124">See Also</span></span>  
 [<span data-ttu-id="ca5d5-125">Proprietà del cursore</span><span class="sxs-lookup"><span data-stu-id="ca5d5-125">Cursor Properties</span></span>](cursor-properties.md)  
  
  
