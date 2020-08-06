---
title: Modalità asincrona e SQLCancel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- asynchronous operations [SQL Server Native Client]
- SQLCancel function
- SQLSetConnectAttr function
- SQL Server Native Client, asynchronous operations
- ODBC functions
- ODBC applications, asynchronous operations
- SQL Server Native Client ODBC driver, asynchronous mode
ms.assetid: f31702a2-df76-4589-ac3b-da5412c03dc2
author: rothja
ms.author: jroth
ms.openlocfilehash: 9071c6821e6edeb577b639223e42899d2927bced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635511"
---
# <a name="asynchronous-mode-and-sqlcancel"></a><span data-ttu-id="f73f8-102">Modalità asincrona e SQLCancel</span><span class="sxs-lookup"><span data-stu-id="f73f8-102">Asynchronous Mode and SQLCancel</span></span>
  <span data-ttu-id="f73f8-103">Alcune funzioni ODBC possono essere utilizzate in modo sincrono o in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="f73f8-103">Some ODBC functions can operate either synchronously or asynchronously.</span></span> <span data-ttu-id="f73f8-104">Le operazioni asincrone possono essere abilitate per un handle di istruzione o per un handle di connessione.</span><span class="sxs-lookup"><span data-stu-id="f73f8-104">The application can enable asynchronous operations for either a statement handle or a connection handle.</span></span> <span data-ttu-id="f73f8-105">Se l'opzione viene impostata per un handle di connessione, sarà valida per tutti gli handle di istruzione nell'handle di connessione.</span><span class="sxs-lookup"><span data-stu-id="f73f8-105">If the option is set for a connection handle, it affects all statement handles on the connection handle.</span></span> <span data-ttu-id="f73f8-106">Per abilitare o disabilitare le operazioni asincrone vengono utilizzate le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f73f8-106">The application uses the following statements to enable or disable asynchronous operations:</span></span>  
  
```  
SQLSetConnectAttr(hdbc, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_ON, SQL_IS_INTEGER);  
SQLSetConnectAttr(hdbc, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_OFF, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_ON, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_OFF, SQL_IS_INTEGER);  
```  
  
 <span data-ttu-id="f73f8-107">Quando una funzione ODBC viene chiamata in modalità sincrona, il driver restituisce il controllo all'applicazione solo dopo la notifica del completamento del comando da parte del server.</span><span class="sxs-lookup"><span data-stu-id="f73f8-107">When an application calls an ODBC function in synchronous mode, the driver does not return control to the application until it is notified that the server has completed the command.</span></span>  
  
 <span data-ttu-id="f73f8-108">In modalità asincrona, il driver restituisce immediatamente il controllo all'applicazione, anche prima dell'invio del comando al server.</span><span class="sxs-lookup"><span data-stu-id="f73f8-108">When operating asynchronously, the driver immediately returns control to the application, even before sending the command to the server.</span></span> <span data-ttu-id="f73f8-109">Il driver imposta il codice restituito su SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="f73f8-109">The driver sets the return code to SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="f73f8-110">È quindi possibile eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="f73f8-110">The application can then perform other work.</span></span>  
  
 <span data-ttu-id="f73f8-111">Durante il controllo del completamento del comando, viene effettuata la stessa chiamata di funzione con gli stessi parametri al driver.</span><span class="sxs-lookup"><span data-stu-id="f73f8-111">When the application tests for completion of the command, it makes the same function call with the same parameters to the driver.</span></span> <span data-ttu-id="f73f8-112">Se il driver non riceve una risposta dal server, restituirà nuovamente SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="f73f8-112">If the driver has not yet received an answer from the server, it will again return SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="f73f8-113">È necessario controllare periodicamente il comando finché il codice restituito non sia diverso da SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="f73f8-113">The application must test the command periodically until the return code is something other than SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="f73f8-114">Quando si ottiene un codice restituito diverso, anche SQL_ERROR, è possibile determinare che il comando è stato completato.</span><span class="sxs-lookup"><span data-stu-id="f73f8-114">When the application gets some other return code, even SQL_ERROR, it can determine that the command has completed.</span></span>  
  
 <span data-ttu-id="f73f8-115">A volte un comando rimane in attesa per molto tempo.</span><span class="sxs-lookup"><span data-stu-id="f73f8-115">Sometimes a command is outstanding for a long time.</span></span> <span data-ttu-id="f73f8-116">Se l'applicazione deve annullare il comando senza attendere una risposta, è possibile eseguire questa operazione chiamando **SQLCancel** con lo stesso handle di istruzione del comando in attesa.</span><span class="sxs-lookup"><span data-stu-id="f73f8-116">If the application needs to cancel the command without waiting for a reply, it can do so by calling **SQLCancel** with the same statement handle as the outstanding command.</span></span> <span data-ttu-id="f73f8-117">Questa è l'unica volta in cui deve essere utilizzato **SQLCancel** .</span><span class="sxs-lookup"><span data-stu-id="f73f8-117">This is the only time **SQLCancel** should be used.</span></span> <span data-ttu-id="f73f8-118">Alcuni programmatori utilizzano **SQLCancel** quando elaborano in modo parziale un set di risultati e desiderano annullare il resto del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="f73f8-118">Some programmers use **SQLCancel** when they have processed part way through a result set and want to cancel the rest of the result set.</span></span> <span data-ttu-id="f73f8-119">È necessario utilizzare [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) o [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) per annullare il resto di un set di risultati in attesa, non **SQLCancel**.</span><span class="sxs-lookup"><span data-stu-id="f73f8-119">[SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) or [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) should be used to cancel the remainder of an outstanding result set, not **SQLCancel**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f73f8-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f73f8-120">See Also</span></span>  
 [<span data-ttu-id="f73f8-121">Creazione di un'applicazione driver ODBC di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="f73f8-121">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
  
