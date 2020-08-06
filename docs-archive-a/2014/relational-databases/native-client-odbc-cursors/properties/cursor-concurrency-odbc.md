---
title: Concorrenza del cursore (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- concurrency [ODBC]
- cursors [ODBC], concurrency
- ODBC cursors, concurrency
ms.assetid: 68228ece-cbf1-4f19-bfdc-053884c1af48
author: rothja
ms.author: jroth
ms.openlocfilehash: c47f24152978fedf8f2c3d49ec3b721969712814
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635553"
---
# <a name="cursor-concurrency-odbc"></a><span data-ttu-id="6f9d1-102">Concorrenza dei cursori (ODBC)</span><span class="sxs-lookup"><span data-stu-id="6f9d1-102">Cursor Concurrency (ODBC)</span></span>
  <span data-ttu-id="6f9d1-103">Le operazioni dei cursori, come i tipi di cursore, sono influenzate dalle opzioni di concorrenza impostate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6f9d1-103">Cursor operations, like cursor types, are affected by the concurrency options set by the application.</span></span> <span data-ttu-id="6f9d1-104">Le opzioni di concorrenza vengono impostate utilizzando l'opzione SQL_ATTR_CONCURRENCY di [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="6f9d1-104">Concurrency options are set using the SQL_ATTR_CONCURRENCY option of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="6f9d1-105">I tipi di concorrenza sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f9d1-105">The concurrency types are:</span></span>  
  
-   <span data-ttu-id="6f9d1-106">Di sola lettura (SQL_CONCUR_READONLY)</span><span class="sxs-lookup"><span data-stu-id="6f9d1-106">Read-only (SQL_CONCUR_READONLY)</span></span>  
  
-   <span data-ttu-id="6f9d1-107">Valori (SQL_CONCUR_VALUES)</span><span class="sxs-lookup"><span data-stu-id="6f9d1-107">Values (SQL_CONCUR_VALUES)</span></span>  
  
-   <span data-ttu-id="6f9d1-108">Versione di riga (SQL_CONCUR_ROWVER)</span><span class="sxs-lookup"><span data-stu-id="6f9d1-108">Row version (SQL_CONCUR_ROWVER)</span></span>  
  
-   <span data-ttu-id="6f9d1-109">Blocco (SQL_CONCUR_LOCK)</span><span class="sxs-lookup"><span data-stu-id="6f9d1-109">Lock (SQL_CONCUR_LOCK)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f9d1-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f9d1-110">See Also</span></span>  
 [<span data-ttu-id="6f9d1-111">Proprietà del cursore</span><span class="sxs-lookup"><span data-stu-id="6f9d1-111">Cursor Properties</span></span>](cursor-properties.md)  
  
  
