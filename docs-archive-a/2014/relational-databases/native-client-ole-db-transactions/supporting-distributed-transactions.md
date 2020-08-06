---
title: Supporto di transazioni distribuite | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- distributed transactions [OLE DB]
- MS DTC
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
- ITransactionJoin interface
- MS DTC, about distributed transaction support
ms.assetid: d250b43b-9260-4ea4-90cc-57d9a2f67ea7
author: rothja
ms.author: jroth
ms.openlocfilehash: 5a30a44dc007852922aa71685728b26e5bb872c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722727"
---
# <a name="supporting-distributed-transactions"></a><span data-ttu-id="9e444-102">Supporto di transazioni distribuite</span><span class="sxs-lookup"><span data-stu-id="9e444-102">Supporting Distributed Transactions</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="9e444-103">I consumer del provider OLE DB di Native client possono utilizzare il metodo **ITransactionJoin:: JoinTransaction** per partecipare a una transazione distribuita coordinata da Microsoft Distributed Transaction Coordinator (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="9e444-103">Native Client OLE DB provider consumers can use the **ITransactionJoin::JoinTransaction** method to participate in a distributed transaction coordinated by Microsoft Distributed Transaction Coordinator (MS DTC).</span></span>  
  
 <span data-ttu-id="9e444-104">MS DTC espone oggetti COM che consentono ai client di avviare e partecipare a transazioni coordinate tra più connessioni a un'ampia gamma di archivi dati.</span><span class="sxs-lookup"><span data-stu-id="9e444-104">MS DTC exposes COM objects that allow clients to initiate and participate in coordinated transactions across multiple connections to a variety of data stores.</span></span> <span data-ttu-id="9e444-105">Per avviare una transazione, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumer del provider di OLE DB di Native client utilizza l'interfaccia **ITRANSACTIONDISPENSER** di MS DTC.</span><span class="sxs-lookup"><span data-stu-id="9e444-105">To initiate a transaction, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer uses the MS DTC **ITransactionDispenser** interface.</span></span> <span data-ttu-id="9e444-106">Il membro **BeginTransaction** di **ITransactionDispenser** restituisce un riferimento in un oggetto della transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="9e444-106">The **BeginTransaction** member of **ITransactionDispenser** returns a reference on a distributed transaction object.</span></span> <span data-ttu-id="9e444-107">Questo riferimento viene passato al [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native client utilizzando **JoinTransaction**.</span><span class="sxs-lookup"><span data-stu-id="9e444-107">This reference is passed to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider using **JoinTransaction**.</span></span>  
  
 <span data-ttu-id="9e444-108">MS DTC supporta il commit asincrono e l'interruzione nelle transazioni distribuite.</span><span class="sxs-lookup"><span data-stu-id="9e444-108">MS DTC supports asynchronous commit and abort on distributed transactions.</span></span> <span data-ttu-id="9e444-109">Come notifica sullo stato della transazione asincrona, il consumer implementa l'interfaccia **ITransactionOutcomeEvents** e connette l'interfaccia a un oggetto transazione MS DTC.</span><span class="sxs-lookup"><span data-stu-id="9e444-109">For notification on asynchronous transaction status, the consumer implements the **ITransactionOutcomeEvents** interface and connects the interface to an MS DTC transaction object.</span></span>  
  
 <span data-ttu-id="9e444-110">Per le transazioni distribuite, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client implementa i parametri **ITransactionJoin:: JoinTransaction** come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9e444-110">For distributed transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransactionJoin::JoinTransaction** parameters as follows.</span></span>  
  
|<span data-ttu-id="9e444-111">Parametro</span><span class="sxs-lookup"><span data-stu-id="9e444-111">Parameter</span></span>|<span data-ttu-id="9e444-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e444-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e444-113">*punkTransactionCoord*</span><span class="sxs-lookup"><span data-stu-id="9e444-113">*punkTransactionCoord*</span></span>|<span data-ttu-id="9e444-114">Puntatore a un oggetto transazione MS DTC.</span><span class="sxs-lookup"><span data-stu-id="9e444-114">A pointer to an MS DTC transaction object.</span></span>|  
|<span data-ttu-id="9e444-115">*IsoLevel*</span><span class="sxs-lookup"><span data-stu-id="9e444-115">*IsoLevel*</span></span>|<span data-ttu-id="9e444-116">Ignorato dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client.</span><span class="sxs-lookup"><span data-stu-id="9e444-116">Ignored by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="9e444-117">Il livello di isolamento per le transazioni coordinate da MS DTC viene determinato quando il consumer acquisisce un oggetto transazione da MS DTC.</span><span class="sxs-lookup"><span data-stu-id="9e444-117">The isolation level for MS DTC-coordinated transactions is determined when the consumer acquires a transaction object from MS DTC.</span></span>|  
|<span data-ttu-id="9e444-118">*IsoFlags*</span><span class="sxs-lookup"><span data-stu-id="9e444-118">*IsoFlags*</span></span>|<span data-ttu-id="9e444-119">Deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="9e444-119">Must be 0.</span></span> <span data-ttu-id="9e444-120">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce XACT_E_NOISORETAIN se un altro valore viene specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9e444-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOISORETAIN if any other value is specified by the consumer.</span></span>|  
|<span data-ttu-id="9e444-121">*POtherOptions*</span><span class="sxs-lookup"><span data-stu-id="9e444-121">*POtherOptions*</span></span>|<span data-ttu-id="9e444-122">Se non è NULL, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client richiede l'oggetto Options dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9e444-122">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider requests the options object from the interface.</span></span> <span data-ttu-id="9e444-123">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce XACT_E_NOTIMEOUT se il membro *ulTIMEOUT* dell'oggetto options è diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="9e444-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTIMEOUT if the options object's *ulTimeout* member is not zero.</span></span> <span data-ttu-id="9e444-124">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client ignora il valore del membro *szDescription* .</span><span class="sxs-lookup"><span data-stu-id="9e444-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider ignores the value of the *szDescription* member.</span></span>|  
  
 <span data-ttu-id="9e444-125">In questo esempio viene coordinata la transazione tramite MS DTC.</span><span class="sxs-lookup"><span data-stu-id="9e444-125">This example coordinates transaction by using MS DTC.</span></span>  
  
```  
// Interfaces used in the example.  
IDBCreateSession*       pIDBCreateSession   = NULL;  
ITransactionJoin*       pITransactionJoin   = NULL;  
IDBCreateCommand*       pIDBCreateCommand   = NULL;  
IRowset*                pIRowset            = NULL;  
  
// Transaction dispenser and transaction from MS DTC.  
ITransactionDispenser*  pITransactionDispenser = NULL;  
ITransaction*           pITransaction       = NULL;  
  
    HRESULT             hr;  
  
// Get the command creation interface for the session.  
if (FAILED(hr = pIDBCreateSession->CreateSession(NULL,  
     IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand)))  
    {  
    // Process error from session creation. Release any references and  
    // return.  
    }  
  
// Get a transaction dispenser object from MS DTC and  
// start a transaction.  
if (FAILED(hr = DtcGetTransactionManager(NULL, NULL,  
    IID_ITransactionDispenser, 0, 0, NULL,  
    (void**) &pITransactionDispenser)))  
    {  
    // Process error message from MS DTC, release any references,  
    // and then return.  
    }  
if (FAILED(hr = pITransactionDispenser->BeginTransaction(  
    NULL, ISOLATIONLEVEL_READCOMMITTED, ISOFLAG_RETAIN_DONTCARE,  
    NULL, &pITransaction)))  
    {  
    // Process error message from MS DTC, release any references,  
    // and then return.  
    }  
  
// Join the transaction.  
if (FAILED(pIDBCreateCommand->QueryInterface(IID_ITransactionJoin,  
    (void**) &pITransactionJoin)))  
    {  
    // Process failure to get an interface, release any references, and  
    // then return.  
    }  
if (FAILED(pITransactionJoin->JoinTransaction(  
    (IUnknown*) pITransaction, 0, 0, NULL)))  
    {  
    // Process join failure, release any references, and then return.  
    }  
  
// Get data into a rowset, then update the data. Functions are not  
// illustrated in this example.  
if (FAILED(hr = ExecuteCommand(pIDBCreateCommand, &pIRowset)))  
    {  
    // Release any references and return.  
    }  
  
// If rowset data update fails, then terminate the transaction, else  
// commit. The example doesn't retain the rowset.  
if (FAILED(hr = UpdateDataInRowset(pIRowset, bDelayedUpdate)))  
    {  
    // Get error from update, then abort.  
    pITransaction->Abort(NULL, FALSE, FALSE);  
    }  
else  
    {  
    if (FAILED(hr = pITransaction->Commit(FALSE, 0, 0)))  
        {  
        // Get error from failed commit.  
        //  
        // If a distributed commit fails, application logic could  
        // analyze failure and retry. In this example, terminate. The   
        // consumer must resolve this somehow.  
        pITransaction->Abort(NULL, FALSE, FALSE);  
        }  
    }  
  
if (FAILED(hr))  
    {  
    // Update of data or commit failed. Release any references and  
    // return.  
    }  
  
// Un-enlist from the distributed transaction by setting   
// the transaction object pointer to NULL.  
if (FAILED(pITransactionJoin->JoinTransaction(  
    (IUnknown*) NULL, 0, 0, NULL)))  
    {  
    // Process failure, and then return.  
    }  
  
// Release any references and continue.  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e444-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e444-126">See Also</span></span>  
 [<span data-ttu-id="9e444-127">Transazioni</span><span class="sxs-lookup"><span data-stu-id="9e444-127">Transactions</span></span>](transactions.md)  
  
  
