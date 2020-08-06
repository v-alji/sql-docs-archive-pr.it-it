---
title: Liberazione di un handle di istruzione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- reusing statement handles
- freeing statement handles
- statements [ODBC], statement handles
- SQLFreeStmt function
- ODBC applications, statements
- statement handles [ODBC]
ms.assetid: 96fdff84-0ca7-460a-a240-94ee826ea41c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8d7a1e93d222e2b87058bc878f7eca85313b4108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624106"
---
# <a name="freeing-a-statement-handle"></a><span data-ttu-id="91846-102">Rilascio di un handle di istruzione</span><span class="sxs-lookup"><span data-stu-id="91846-102">Freeing a Statement Handle</span></span>
  <span data-ttu-id="91846-103">È più efficiente riutilizzare handle di istruzione anziché eliminarli e allocarne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="91846-103">It is more efficient to reuse statement handles than to drop them and allocate new ones.</span></span> <span data-ttu-id="91846-104">Prima di eseguire una nuova istruzione SQL su un handle di istruzione, le applicazioni devono verificare che le impostazioni delle istruzioni correnti siano corrette.</span><span class="sxs-lookup"><span data-stu-id="91846-104">Before executing a new SQL statement on a statement handle, applications should verify that the current statement settings are appropriate.</span></span> <span data-ttu-id="91846-105">Tra le impostazioni sono inclusi gli attributi di istruzione, le associazioni di parametri e le associazioni dei set di risultati.</span><span class="sxs-lookup"><span data-stu-id="91846-105">These include statement attributes, parameter bindings, and result set bindings.</span></span> <span data-ttu-id="91846-106">In genere, i parametri e i set di risultati per l'istruzione SQL precedente devono essere non associati chiamando [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) con le opzioni SQL_RESET_PARAMS e SQL_UNBIND e quindi riassociati per la nuova istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="91846-106">Generally, parameters and result sets for the old SQL statement must be unbound by calling [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with the SQL_RESET_PARAMS and SQL_UNBIND options and then re-bound for the new SQL statement.</span></span>  
  
 <span data-ttu-id="91846-107">Al termine dell'utilizzo dell'istruzione, l'applicazione chiama [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) per liberare l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="91846-107">When the application has finished using the statement, it calls [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) to free the statement.</span></span> <span data-ttu-id="91846-108">Si noti che **Disconnect** libera automaticamente tutte le istruzioni in una connessione.</span><span class="sxs-lookup"><span data-stu-id="91846-108">Note that **SQLDisconnect** automatically frees all statements on a connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91846-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91846-109">See Also</span></span>  
 [<span data-ttu-id="91846-110">Esecuzione di query &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="91846-110">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
