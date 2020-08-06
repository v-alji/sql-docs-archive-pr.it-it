---
title: Esecuzione di transazioni distribuite | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MS DTC, performing distributed transactions
- SQL Server Native Client ODBC driver, transactions
- distributed transactions [ODBC]
- transactions [ODBC]
- ODBC, transactions
ms.assetid: 2c17fba0-7a3c-453c-91b7-f801e7b39ccb
author: rothja
ms.author: jroth
ms.openlocfilehash: 9ec23fd1883749e35e67f888e26bdf031ccf7fb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626061"
---
# <a name="performing-distributed-transactions"></a><span data-ttu-id="9aada-102">Esecuzione delle transazioni distribuite</span><span class="sxs-lookup"><span data-stu-id="9aada-102">Performing Distributed Transactions</span></span>
  <span data-ttu-id="9aada-103">Microsoft Distributed Transaction Coordinator (MS DTC) consente alle applicazioni di estendere le transazioni su due o più istanze di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)],</span><span class="sxs-lookup"><span data-stu-id="9aada-103">The Microsoft Distributed Transaction Coordinator (MS DTC) allows applications to extend transactions across two or more instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9aada-104">nonché di partecipare a transazioni gestite da gestori transazioni conformi allo standard DTP XA dell'Open Group.</span><span class="sxs-lookup"><span data-stu-id="9aada-104">It also allows applications to participate in transactions managed by transaction managers that comply with the Open Group DTP XA standard.</span></span>  
  
 <span data-ttu-id="9aada-105">In genere tutti i comandi di gestione delle transazioni vengono inviati al server tramite il driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="9aada-105">Normally, all transaction management commands are sent through the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver to the server.</span></span> <span data-ttu-id="9aada-106">L'applicazione avvia una transazione chiamando [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) con la modalità autocommit disattivata.</span><span class="sxs-lookup"><span data-stu-id="9aada-106">The application starts a transaction by calling [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) with the autocommit mode turned off.</span></span> <span data-ttu-id="9aada-107">L'applicazione esegue quindi gli aggiornamenti che compongono la transazione e chiama [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) con l'opzione SQL_COMMIT o SQL_ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="9aada-107">The application then performs the updates comprising the transaction and calls [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) with either the SQL_COMMIT or SQL_ROLLBACK option.</span></span>  
  
 <span data-ttu-id="9aada-108">Quando si utilizza MS DTC, tuttavia, MS DTC diventa la gestione transazioni e l'applicazione non utilizza più **SQLEndTran**.</span><span class="sxs-lookup"><span data-stu-id="9aada-108">When using MS DTC, however, MS DTC becomes the transaction manager and the application no longer uses **SQLEndTran**.</span></span>  
  
 <span data-ttu-id="9aada-109">Dopo aver eseguito l'integrazione in una transazione distribuita e, successivamente, aver effettuato la stessa operazione in una seconda transazione distribuita, il driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client viene escluso dalla transazione distribuita originale e ne viene eseguita l'integrazione nella nuova transazione.</span><span class="sxs-lookup"><span data-stu-id="9aada-109">When enlisted in a distributed transaction, and then enlist in a second distributed transaction, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver defects from the original distributed transaction and enlists in the new transaction.</span></span> <span data-ttu-id="9aada-110">Per ulteriori informazioni, vedere [DTC Programmer ' s Reference](https://msdn.microsoft.com/library/ms686108\(VS.85\).aspx).</span><span class="sxs-lookup"><span data-stu-id="9aada-110">For more information, see [DTC Programmer's Reference](https://msdn.microsoft.com/library/ms686108\(VS.85\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aada-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9aada-111">See Also</span></span>  
 [<span data-ttu-id="9aada-112">Esecuzione di transazioni &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="9aada-112">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
