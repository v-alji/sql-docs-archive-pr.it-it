---
title: Transazioni in ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, transactions
- transactions [ODBC]
- ODBC, transactions
ms.assetid: c5a87fa5-827a-4e6f-a0d9-924bac881eb0
author: rothja
ms.author: jroth
ms.openlocfilehash: 386b248edfdb6e0ac5eb97b3aeb6c0bbc505a5a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626058"
---
# <a name="transactions-in-odbc"></a><span data-ttu-id="08123-102">Transazioni in ODBC</span><span class="sxs-lookup"><span data-stu-id="08123-102">Transactions in ODBC</span></span>
  <span data-ttu-id="08123-103">Le transazioni in ODBC vengono gestite a livello di connessione.</span><span class="sxs-lookup"><span data-stu-id="08123-103">Transactions in ODBC are managed at the connection level.</span></span> <span data-ttu-id="08123-104">Quando un'applicazione completa una transazione, esegue il commit o il rollback di tutte le operazioni effettuate tramite tutti gli handle di istruzione nella connessione.</span><span class="sxs-lookup"><span data-stu-id="08123-104">When an application completes a transaction, it commits or rolls back all work completed through all statement handles on that connection.</span></span> <span data-ttu-id="08123-105">Per eseguire il commit o il rollback di una transazione, le applicazioni devono chiamare [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) anziché inviare un'istruzione commit o rollback.</span><span class="sxs-lookup"><span data-stu-id="08123-105">To commit or roll back a transaction, applications should call [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) instead of submitting a COMMIT or ROLLBACK statement.</span></span>  
  
 <span data-ttu-id="08123-106">Un'applicazione chiama [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) per passare tra le due modalità ODBC di gestione delle transazioni:</span><span class="sxs-lookup"><span data-stu-id="08123-106">An application calls [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) to switch between the two ODBC modes of managing transactions:</span></span>  
  
-   <span data-ttu-id="08123-107">Modalità autocommit</span><span class="sxs-lookup"><span data-stu-id="08123-107">Autocommit mode</span></span>  
  
     <span data-ttu-id="08123-108">Di ogni istruzione completata correttamente viene automaticamente eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="08123-108">Each statement is automatically committed when it is completed successfully.</span></span> <span data-ttu-id="08123-109">Quando si utilizza la modalità autocommit, non sono necessarie altre funzioni di gestione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="08123-109">When you run in autocommit mode, no other transaction management functions are required.</span></span>  
  
-   <span data-ttu-id="08123-110">Modalità di commit manuale</span><span class="sxs-lookup"><span data-stu-id="08123-110">Manual-commit mode</span></span>  
  
     <span data-ttu-id="08123-111">Tutte le istruzioni eseguite sono incluse nella stessa transazione fino a quando non vengono arrestate in modo specifico chiamando **SQLEndTran**.</span><span class="sxs-lookup"><span data-stu-id="08123-111">All executed statements are included in the same transaction until it is specifically stopped by calling **SQLEndTran**.</span></span>  
  
 <span data-ttu-id="08123-112">La modalità autocommit è la modalità di esecuzione delle transazioni predefinita per ODBC.</span><span class="sxs-lookup"><span data-stu-id="08123-112">Autocommit mode is the default transaction mode for ODBC.</span></span> <span data-ttu-id="08123-113">Quando viene stabilita una connessione, è in modalità autocommit fino a quando non viene chiamato **SQLSetConnectAttr** per passare alla modalità di commit manuale impostando la modalità autocommit.</span><span class="sxs-lookup"><span data-stu-id="08123-113">When a connection is made, it is in autocommit mode until **SQLSetConnectAttr** is called to switch to manual-commit mode by setting autocommit mode off.</span></span> <span data-ttu-id="08123-114">Quando un'applicazione disattiva l'autocommit, l'istruzione successiva inviata al database avvia una transazione.</span><span class="sxs-lookup"><span data-stu-id="08123-114">When an application turns autocommit off, the next statement sent to the database starts a transaction.</span></span> <span data-ttu-id="08123-115">La transazione rimane attiva fino a quando l'applicazione non chiama **SQLEndTran** con le opzioni SQL_COMMIT o SQL_ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="08123-115">The transaction then remains in effect until the application calls **SQLEndTran** with either the SQL_COMMIT or SQL_ROLLBACK options.</span></span> <span data-ttu-id="08123-116">Il comando inviato al database dopo **SQLEndTran** avvia la transazione successiva.</span><span class="sxs-lookup"><span data-stu-id="08123-116">The command sent to the database after **SQLEndTran** starts the next transaction.</span></span>  
  
 <span data-ttu-id="08123-117">Se un'applicazione passa dalla modalità di commit manuale alla modalità autocommit, il driver esegue il commit di tutte le transazioni attualmente aperte nella connessione.</span><span class="sxs-lookup"><span data-stu-id="08123-117">If an application switches from manual-commit to autocommit mode, the driver commits any transactions currently open on the connection.</span></span>  
  
 <span data-ttu-id="08123-118">Le applicazioni ODBC non devono utilizzare istruzioni per transazioni Transact-SQL quali BEGIN TRANSACTION, COMMIT TRANSACTION o ROLLBACK TRANSACTION, in quanto tali istruzioni possono provocare un comportamento imprevedibile nel driver.</span><span class="sxs-lookup"><span data-stu-id="08123-118">ODBC applications should not use Transact-SQL transaction statements such as BEGIN TRANSACTION, COMMIT TRANSACTION, or ROLLBACK TRANSACTION because this can cause indeterminate behavior in the driver.</span></span> <span data-ttu-id="08123-119">Un'applicazione ODBC deve essere eseguita in modalità autocommit e non utilizzare le istruzioni o le funzioni di gestione delle transazioni oppure essere eseguita in modalità con commit manuale e utilizzare la funzione ODBC **SQLEndTran** per eseguire il commit o il rollback delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="08123-119">An ODBC application should run in autocommit mode and not use any transaction management functions or statements, or run in manual-commit mode and use the ODBC **SQLEndTran** function to either commit or roll back transactions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08123-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08123-120">See Also</span></span>  
 [<span data-ttu-id="08123-121">Esecuzione di transazioni &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="08123-121">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
