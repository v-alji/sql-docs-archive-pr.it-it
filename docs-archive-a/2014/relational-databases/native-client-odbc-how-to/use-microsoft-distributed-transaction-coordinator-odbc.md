---
title: Usare Microsoft Distributed Transaction Coordinator (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MS DTC, using
ms.assetid: 12a275e1-8c7e-436d-8a4e-b7bee853b35c
author: rothja
ms.author: jroth
ms.openlocfilehash: f7b7da33066a9f4edd01037738ed91155340e6ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627686"
---
# <a name="use-microsoft-distributed-transaction-coordinator-odbc"></a><span data-ttu-id="45a7f-102">Utilizzare Microsoft Distributed Transaction Coordinator (ODBC).</span><span class="sxs-lookup"><span data-stu-id="45a7f-102">Use Microsoft Distributed Transaction Coordinator (ODBC)</span></span>
    
### <a name="to-update-two-or-more-sql-servers-by-using-ms-dtc"></a><span data-ttu-id="45a7f-103">Per aggiornare due o più computer SQL Server mediante MS DTC</span><span class="sxs-lookup"><span data-stu-id="45a7f-103">To update two or more SQL Servers by using MS DTC</span></span>  
  
1.  <span data-ttu-id="45a7f-104">Connettersi a MS DTC utilizzando la funzione MS DTC OLE DtcGetTransactionManager.</span><span class="sxs-lookup"><span data-stu-id="45a7f-104">Connect to MS DTC by using the MS DTC OLE DtcGetTransactionManager function.</span></span> <span data-ttu-id="45a7f-105">Per informazioni su MS DTC, vedere Microsoft Distributed Transaction Coordinator.</span><span class="sxs-lookup"><span data-stu-id="45a7f-105">For information about MS DTC, see Microsoft Distributed Transaction Coordinator.</span></span>  
  
2.  <span data-ttu-id="45a7f-106">Chiamare SQL DriverConnect una volta per ogni connessione Microsoft SQL Server che si desidera stabilire.</span><span class="sxs-lookup"><span data-stu-id="45a7f-106">Call SQL DriverConnect once for each Microsoft SQL Server connection you want to establish.</span></span>  
  
3.  <span data-ttu-id="45a7f-107">Chiamare la funzione MS DTC OLE ITransactionDispenser::BeginTransaction per iniziare una transazione MS DTC e ottenere un oggetto Transaction che rappresenta la transazione.</span><span class="sxs-lookup"><span data-stu-id="45a7f-107">Call the MS DTC OLE ITransactionDispenser::BeginTransaction function to begin an MS DTC transaction and obtain a Transaction object that represents the transaction.</span></span>  
  
4.  <span data-ttu-id="45a7f-108">Chiamare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) una o più volte per ogni connessione ODBC che si desidera integrare nella transazione MS DTC.</span><span class="sxs-lookup"><span data-stu-id="45a7f-108">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) one or more times for each ODBC connection you want to enlist in the MS DTC transaction.</span></span> <span data-ttu-id="45a7f-109">Il secondo parametro [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) deve essere SQL_ATTR_ENLIST_IN_DTC mentre il terzo parametro deve essere l'oggetto Transaction, ottenuto nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="45a7f-109">[SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) second parameter must be SQL_ATTR_ENLIST_IN_DTC and third parameter must be the Transaction object (obtained in Step 3).</span></span>  
  
5.  <span data-ttu-id="45a7f-110">Chiamare [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) una volta per ogni computer SQL Server da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="45a7f-110">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) once for each SQL Server you want to update.</span></span>  
  
6.  <span data-ttu-id="45a7f-111">Chiamare la funzione MS DTC OLE ITransaction::Commit per eseguire il commit della transazione MS DTC.</span><span class="sxs-lookup"><span data-stu-id="45a7f-111">Call the MS DTC OLE ITransaction::Commit function to commit the MS DTC transaction.</span></span> <span data-ttu-id="45a7f-112">L'oggetto Transaction non è più valido.</span><span class="sxs-lookup"><span data-stu-id="45a7f-112">The Transaction object is no longer valid.</span></span>  
  
 <span data-ttu-id="45a7f-113">Per eseguire una serie di transazioni MS DTC, ripetere i passaggi da 3 a 6.</span><span class="sxs-lookup"><span data-stu-id="45a7f-113">To perform a series of MS DTC transactions, repeat Steps 3 through 6.</span></span>  
  
 <span data-ttu-id="45a7f-114">Per rilasciare il riferimento all'oggetto Transaction, chiamare la funzione MS DTC OLE ITransaction::Return.</span><span class="sxs-lookup"><span data-stu-id="45a7f-114">To release the reference to the Transaction object, call the MS DTC OLE ITransaction::Return function.</span></span>  
  
 <span data-ttu-id="45a7f-115">Per usare una connessione ODBC con una transazione MS DTC e quindi usare la stessa connessione con una transazione di SQL Server locale, chiamare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_DTC_DONE.</span><span class="sxs-lookup"><span data-stu-id="45a7f-115">To use an ODBC connection with an MS DTC transaction, and then use the same connection with a local SQL Server transaction, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_DTC_DONE.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45a7f-116">È inoltre possibile chiamare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) e [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) per ogni computer SQL Server anziché come suggerito nei passaggi 4 e 5.</span><span class="sxs-lookup"><span data-stu-id="45a7f-116">You can also call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) and [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) in turn for each SQL Server instead of calling them as suggested earlier in Steps 4 and 5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a7f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45a7f-117">See Also</span></span>  
 [<span data-ttu-id="45a7f-118">Esecuzione di transazioni &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="45a7f-118">Performing Transactions &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
