---
title: Utilizzo di SQL Server set di risultati predefiniti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetStmtAttr function
- ODBC cursors, default result sets
- cursors [ODBC], default result sets
- default result sets
- result sets [ODBC], default
- ODBC applications, cursors
ms.assetid: ee1db3e5-60eb-4425-8a6b-977eeced3f98
author: rothja
ms.author: jroth
ms.openlocfilehash: 18cd10dd95329f68a42497d2bea5ce63f345ceff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626769"
---
# <a name="using-sql-server-default-result-sets"></a><span data-ttu-id="16b56-102">Utilizzo dei set di risultati predefiniti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="16b56-102">Using SQL Server Default Result Sets</span></span>
  <span data-ttu-id="16b56-103">Gli attributi predefiniti del cursore ODBC sono:</span><span class="sxs-lookup"><span data-stu-id="16b56-103">The default ODBC cursor attributes are:</span></span>  
  
```  
SQLSetStmtAttr(hstmt, SQL_ATTR_CURSOR_TYPE, SQL_CURSOR_FORWARD_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_CONCURRENCY, SQL_CONCUR_READ_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ROW_ARRAY_SIZE, 1, SQL_IS_INTEGER);  
```  
  
 <span data-ttu-id="16b56-104">Ogni volta che questi attributi sono impostati sui valori predefiniti, il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native client utilizza un [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] set di risultati predefinito.</span><span class="sxs-lookup"><span data-stu-id="16b56-104">Whenever these attributes are set to their defaults, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver uses a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result set.</span></span> <span data-ttu-id="16b56-105">I set di risultati predefiniti possono essere utilizzati per qualsiasi istruzione SQL supportata da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e rappresentano il metodo più efficiente per trasferire un intero set di risultati al client.</span><span class="sxs-lookup"><span data-stu-id="16b56-105">Default result sets can be used for any SQL statement supported by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and are the most efficient method of transferring an entire result set to the client.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]<span data-ttu-id="16b56-106">è stato introdotto il supporto per MARS (Multiple Active Result Sets); le applicazioni possono ora disporre di più set di risultati predefiniti attivi per connessione.</span><span class="sxs-lookup"><span data-stu-id="16b56-106">introduced support for multiple active result sets (MARS); applications can now have more than one active default result set per connection.</span></span> <span data-ttu-id="16b56-107">Per impostazione predefinita, la funzionalità MARS non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="16b56-107">MARS is not enabled by default.</span></span>  
  
 <span data-ttu-id="16b56-108">Prima di [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], i set di risultati predefiniti non supportavano più istruzioni attive nella stessa connessione.</span><span class="sxs-lookup"><span data-stu-id="16b56-108">Before [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], default result sets did not support multiple active statements on the same connection.</span></span> <span data-ttu-id="16b56-109">Dopo l'esecuzione di un'istruzione SQL in una connessione, il server non accetta comandi dal client in tale connessione finché non sono state elaborate tutte le righe del set di risultati, ad eccezione di una richiesta per annullare il resto del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="16b56-109">After an SQL statement is executed on a connection, the server does not accept commands (except a request to cancel the rest of the result set) from the client on that connection until all the rows in the result set have been processed.</span></span> <span data-ttu-id="16b56-110">Per annullare il resto di un set di risultati parzialmente elaborato, chiamare [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) o [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) con il parametro *fOption* impostato su SQL_CLOSE.</span><span class="sxs-lookup"><span data-stu-id="16b56-110">To cancel the remainder of a partially processed result set, call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) or [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with the *fOption* parameter set to SQL_CLOSE.</span></span> <span data-ttu-id="16b56-111">Per completare un set di risultati parzialmente elaborato e verificare la presenza di un altro set di risultati, chiamare [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md).</span><span class="sxs-lookup"><span data-stu-id="16b56-111">To finish a partially processed result set and test for the presence of another result set, call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md).</span></span> <span data-ttu-id="16b56-112">Se un'applicazione ODBC tenta di eseguire un comando su un handle di connessione prima che un set di risultati predefinito venga elaborato completamente, la chiamata genera SQL_ERROR e una chiamata a **SQLGetDiagRec** restituisce:</span><span class="sxs-lookup"><span data-stu-id="16b56-112">If an ODBC application attempts a command on a connection handle before a default result set has been completely processed, the call generates SQL_ERROR and a call to **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState: "HY000", pfNativeError: 0  
szErrorMsg: "[Microsoft][SQL Server Native Client]  
                Connection is busy with results for another hstmt."  
```  
  
## <a name="see-also"></a><span data-ttu-id="16b56-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16b56-113">See Also</span></span>  
 [<span data-ttu-id="16b56-114">Modalità di implementazione dei cursori</span><span class="sxs-lookup"><span data-stu-id="16b56-114">How Cursors Are Implemented</span></span>](how-cursors-are-implemented.md)  
  
  
