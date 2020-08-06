---
title: Comportamenti del cursore | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- scrollable cursors [SQL Server]
- SQL Server Native Client ODBC driver, cursors
- version-based optimistic concurrency
- cursors [ODBC], cursor behaviors
- ODBC applications, cursors
- SQL_ATTR_CURSOR_SENSITIVITY option
- SQL_ATTR_CURSOR_SCROLLABLE option
- sensitivity behavior of cursor
- ODBC cursors, cursor behaviors
ms.assetid: 742ddcd2-232b-4aa1-9212-027df120ad35
author: rothja
ms.author: jroth
ms.openlocfilehash: 89c7c4e9a8dcffe03dd12f8013d5ed43810547f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628647"
---
# <a name="cursor-behaviors"></a><span data-ttu-id="cfbd1-102">Comportamenti dei cursori</span><span class="sxs-lookup"><span data-stu-id="cfbd1-102">Cursor Behaviors</span></span>
  <span data-ttu-id="cfbd1-103">ODBC supporta le opzioni ISO per la specifica del comportamento dei cursori mediante lo scorrimento e la sensibilità.</span><span class="sxs-lookup"><span data-stu-id="cfbd1-103">ODBC supports the ISO options for specifying the behavior of cursors by specifying their scrollability and sensitivity.</span></span> <span data-ttu-id="cfbd1-104">Questi comportamenti vengono specificati impostando le opzioni SQL_ATTR_CURSOR_SCROLLABLE e SQL_ATTR_CURSOR_SENSITIVITY in una chiamata a [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="cfbd1-104">These behaviors are specified by setting the SQL_ATTR_CURSOR_SCROLLABLE and SQL_ATTR_CURSOR_SENSITIVITY options on a call to [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="cfbd1-105">Il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client implementa queste opzioni richiedendo cursori server con le caratteristiche seguenti.</span><span class="sxs-lookup"><span data-stu-id="cfbd1-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver implements these options by requesting server cursors with the following characteristics.</span></span>  
  
|<span data-ttu-id="cfbd1-106">Impostazioni del comportamento del cursore</span><span class="sxs-lookup"><span data-stu-id="cfbd1-106">Cursor behavior settings</span></span>|<span data-ttu-id="cfbd1-107">Caratteristiche del cursore server richieste</span><span class="sxs-lookup"><span data-stu-id="cfbd1-107">Server cursor characteristics requested</span></span>|  
|------------------------------|---------------------------------------------|  
|<span data-ttu-id="cfbd1-108">SQL_SCROLLABLE e SQL_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="cfbd1-108">SQL_SCROLLABLE and SQL_SENSITIVE</span></span>|<span data-ttu-id="cfbd1-109">Cursore gestito da keyset e concorrenza ottimistica basata sulla versione</span><span class="sxs-lookup"><span data-stu-id="cfbd1-109">Keyset-driven cursor and version-based optimistic concurrency</span></span>|  
|<span data-ttu-id="cfbd1-110">SQL_SCROLLABLE e SQL_INSENSITIVE</span><span class="sxs-lookup"><span data-stu-id="cfbd1-110">SQL_SCROLLABLE and SQL_INSENSITIVE</span></span>|<span data-ttu-id="cfbd1-111">Cursore statico e concorrenza di sola lettura</span><span class="sxs-lookup"><span data-stu-id="cfbd1-111">Static cursor and read-only concurrency</span></span>|  
|<span data-ttu-id="cfbd1-112">SQL_SCROLLABLE e SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="cfbd1-112">SQL_SCROLLABLE and SQL_UNSPECIFIED</span></span>|<span data-ttu-id="cfbd1-113">Cursore statico e concorrenza di sola lettura</span><span class="sxs-lookup"><span data-stu-id="cfbd1-113">Static cursor and read-only concurrency</span></span>|  
|<span data-ttu-id="cfbd1-114">SQL_NONSCROLLABLE e SQL_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="cfbd1-114">SQL_NONSCROLLABLE and SQL_SENSITIVE</span></span>|<span data-ttu-id="cfbd1-115">Cursore forward-only e concorrenza ottimistica basata sulla versione</span><span class="sxs-lookup"><span data-stu-id="cfbd1-115">Forward-only cursor and version-based optimistic concurrency</span></span>|  
|<span data-ttu-id="cfbd1-116">SQL_NONSCROLLABLE e SQL_INSENSITIVE</span><span class="sxs-lookup"><span data-stu-id="cfbd1-116">SQL_NONSCROLLABLE and SQL_INSENSITIVE</span></span>|<span data-ttu-id="cfbd1-117">Set di risultati predefinito (forward only, di sola lettura)</span><span class="sxs-lookup"><span data-stu-id="cfbd1-117">Default result set (forward-only, read-only)</span></span>|  
|<span data-ttu-id="cfbd1-118">SQL_NONSCROLLABLE e SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="cfbd1-118">SQL_NONSCROLLABLE and SQL_UNSPECIFIED</span></span>|<span data-ttu-id="cfbd1-119">Set di risultati predefinito (forward only, di sola lettura)</span><span class="sxs-lookup"><span data-stu-id="cfbd1-119">Default result set (forward-only, read-only)</span></span>|  
  
 <span data-ttu-id="cfbd1-120">Per la concorrenza ottimistica basata sulla versione è richiesta una colonna **timestamp** nella tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="cfbd1-120">Version-based optimistic concurrency requires a **timestamp** column in the underlying table.</span></span> <span data-ttu-id="cfbd1-121">Se è richiesto il controllo della concorrenza ottimistica basata sulla versione in una tabella che non dispone di una colonna di tipo **timestamp** , il server utilizza la concorrenza ottimistica basata sui valori.</span><span class="sxs-lookup"><span data-stu-id="cfbd1-121">If version-based optimistic concurrency control is requested on a table that does not have a **timestamp** column, the server uses values-based optimistic concurrency.</span></span>  
  
## <a name="scrollability"></a><span data-ttu-id="cfbd1-122">Scorrimento</span><span class="sxs-lookup"><span data-stu-id="cfbd1-122">Scrollability</span></span>  
 <span data-ttu-id="cfbd1-123">Quando SQL_ATTR_CURSOR_SCROLLABLE è impostato su SQL_SCROLLABLE, il cursore supporta tutti i valori diversi per il parametro *FetchOrientation* di [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="cfbd1-123">When SQL_ATTR_CURSOR_SCROLLABLE is set to SQL_SCROLLABLE, the cursor supports all the different values for the *FetchOrientation* parameter of [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span></span> <span data-ttu-id="cfbd1-124">Quando SQL_ATTR_CURSOR_SCROLLABLE è impostato su SQL_NONSCROLLABLE, il cursore supporta solo un valore *FetchOrientation* di SQL_FETCH_NEXT.</span><span class="sxs-lookup"><span data-stu-id="cfbd1-124">When SQL_ATTR_CURSOR_SCROLLABLE is set to SQL_NONSCROLLABLE, the cursor only supports a *FetchOrientation* value of SQL_FETCH_NEXT.</span></span>  
  
## <a name="sensitivity"></a><span data-ttu-id="cfbd1-125">Sensibilità</span><span class="sxs-lookup"><span data-stu-id="cfbd1-125">Sensitivity</span></span>  
 <span data-ttu-id="cfbd1-126">Quando SQL_ATTR_CURSOR_SENSITIVITY è impostato su SQL_SENSITIVE, il cursore riflette le modifiche dei dati apportate dall'utente corrente di cui è stato eseguito il commit da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="cfbd1-126">When SQL_ATTR_CURSOR_SENSITIVITY is set to SQL_SENSITIVE, the cursor reflects data modifications made by the current user or committed by other users.</span></span> <span data-ttu-id="cfbd1-127">Quando SQL_ATTR_CURSOR_SENSITIVITY è impostato su SQL_INSENSITIVE, il cursore non riflette le modifiche dei dati.</span><span class="sxs-lookup"><span data-stu-id="cfbd1-127">When SQL_ATTR_CURSOR_SENSITIVITY is set to SQL_INSENSITIVE, the cursor does not reflect data modifications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfbd1-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfbd1-128">See Also</span></span>  
 [<span data-ttu-id="cfbd1-129">Utilizzo di cursori &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="cfbd1-129">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
