---
title: Supporto delle transazioni locali | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- autocommit mode
- transactions [OLE DB]
- ITransactionLocal interface
- SQL Server Native Client OLE DB provider, transactions
- local transactions [OLE DB]
ms.assetid: 78f2e5fc-b6fb-4eda-9f71-991a4d6c4902
author: rothja
ms.author: jroth
ms.openlocfilehash: a9bc11a038e56517aa42619117c371c1319b9ffe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636035"
---
# <a name="supporting-local-transactions"></a><span data-ttu-id="fcd6b-102">Supporto delle transazioni locali</span><span class="sxs-lookup"><span data-stu-id="fcd6b-102">Supporting Local Transactions</span></span>
  <span data-ttu-id="fcd6b-103">Una sessione delimita l'ambito della transazione per una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transazione locale del provider OLE DB di Native Client.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-103">A session delimits transaction scope for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider local transaction.</span></span> <span data-ttu-id="fcd6b-104">Quando, alla direzione di un consumer, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client invia una richiesta a un'istanza connessa di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , la richiesta costituisce un'unità di lavoro per il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-104">When, at the direction of a consumer, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider submits a request to a connected instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the request constitutes a unit of work for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="fcd6b-105">Nelle transazioni locali viene sempre eseguito il wrapping di una o più unità di lavoro in una singola [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sessione del provider OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-105">Local transactions always wrap one or more units of work on a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider session.</span></span>  
  
 <span data-ttu-id="fcd6b-106">Utilizzando la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] modalità autocommit del provider OLE DB Native client predefinita, una singola unità di lavoro viene considerata come ambito di una transazione locale.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-106">Using the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider autocommit mode, a single unit of work is treated as the scope of a local transaction.</span></span> <span data-ttu-id="fcd6b-107">Solo un unità partecipa alla transazione locale.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-107">Only one unit participates in the local transaction.</span></span> <span data-ttu-id="fcd6b-108">Quando viene creata una sessione, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client inizia una transazione per la sessione.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-108">When a session is created, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider begins a transaction for the session.</span></span> <span data-ttu-id="fcd6b-109">Al completamento di un'unità, viene eseguito il commit del lavoro.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-109">Upon successful completion of a work unit, the work is committed.</span></span> <span data-ttu-id="fcd6b-110">In caso di errore, viene eseguito il rollback di eventuali lavori iniziati e viene segnalato l'errore al consumer.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-110">On failure, any work begun is rolled back and the error is reported to the consumer.</span></span> <span data-ttu-id="fcd6b-111">In entrambi i casi, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client inizia una nuova transazione locale per la sessione in modo che tutto il lavoro venga eseguito all'interno di una transazione.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-111">In either case, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider begins a new local transaction for the session so that all work is conducted within a transaction.</span></span>  
  
 <span data-ttu-id="fcd6b-112">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumer del provider OLE DB di Native client può indirizzare un controllo più preciso sull'ambito della transazione locale tramite l'interfaccia **ITransactionLocal** .</span><span class="sxs-lookup"><span data-stu-id="fcd6b-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer can direct more precise control over local transaction scope by using the **ITransactionLocal** interface.</span></span> <span data-ttu-id="fcd6b-113">Quando una sessione del consumer inizia una transazione, tutte le unità di lavoro della sessione che si trovano tra il punto di inizio della transazione e le chiamate finali al metodo **Commit** o **Abort** vengono trattate come un'unità atomica.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-113">When a consumer session initiates a transaction, all session work units between the transaction start point and the eventual **Commit** or **Abort** method calls are treated as an atomic unit.</span></span> <span data-ttu-id="fcd6b-114">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client inizia in modo implicito una transazione quando viene indirizzata dal consumer.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implicitly begins a transaction when directed to do so by the consumer.</span></span> <span data-ttu-id="fcd6b-115">Se il consumer non richiede la memorizzazione, la sessione ripristina il comportamento a livello di transazione padre, più comunemente la modalità AutoCommit.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-115">If the consumer does not request retention, the session reverts to parent transaction-level behavior, most commonly autocommit mode.</span></span>  
  
 <span data-ttu-id="fcd6b-116">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta i parametri **ITransactionLocal:: StartTransaction** come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **ITransactionLocal::StartTransaction** parameters as follows.</span></span>  
  
|<span data-ttu-id="fcd6b-117">Parametro</span><span class="sxs-lookup"><span data-stu-id="fcd6b-117">Parameter</span></span>|<span data-ttu-id="fcd6b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcd6b-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fcd6b-119">*isoLevel*[in]</span><span class="sxs-lookup"><span data-stu-id="fcd6b-119">*isoLevel*[in]</span></span>|<span data-ttu-id="fcd6b-120">Il livello di isolamento da utilizzare con questa transazione.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-120">The isolation level to be used with this transaction.</span></span> <span data-ttu-id="fcd6b-121">Nelle transazioni locali il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fcd6b-121">In local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports the following:</span></span><br /><br /> <span data-ttu-id="fcd6b-122">-ISOLATIONLEVEL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="fcd6b-122">-   ISOLATIONLEVEL_UNSPECIFIED</span></span><br /><span data-ttu-id="fcd6b-123">-ISOLATIONLEVEL_CHAOS</span><span class="sxs-lookup"><span data-stu-id="fcd6b-123">-   ISOLATIONLEVEL_CHAOS</span></span><br /><span data-ttu-id="fcd6b-124">-ISOLATIONLEVEL_READUNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="fcd6b-124">-   ISOLATIONLEVEL_READUNCOMMITTED</span></span><br /><span data-ttu-id="fcd6b-125">-ISOLATIONLEVEL_READCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="fcd6b-125">-   ISOLATIONLEVEL_READCOMMITTED</span></span><br /><span data-ttu-id="fcd6b-126">-ISOLATIONLEVEL_REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="fcd6b-126">-   ISOLATIONLEVEL_REPEATABLEREAD</span></span><br /><span data-ttu-id="fcd6b-127">-ISOLATIONLEVEL_CURSORSTABILITY</span><span class="sxs-lookup"><span data-stu-id="fcd6b-127">-   ISOLATIONLEVEL_CURSORSTABILITY</span></span><br /><span data-ttu-id="fcd6b-128">-ISOLATIONLEVEL_REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="fcd6b-128">-   ISOLATIONLEVEL_REPEATABLEREAD</span></span><br /><span data-ttu-id="fcd6b-129">-ISOLATIONLEVEL_SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="fcd6b-129">-   ISOLATIONLEVEL_SERIALIZABLE</span></span><br /><span data-ttu-id="fcd6b-130">-ISOLATIONLEVEL_ISOLATED</span><span class="sxs-lookup"><span data-stu-id="fcd6b-130">-   ISOLATIONLEVEL_ISOLATED</span></span><br /><span data-ttu-id="fcd6b-131">-ISOLATIONLEVEL_SNAPSHOT **Nota:** a partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , ISOLATIONLEVEL_SNAPSHOT è valido per l'argomento *isoLevel* , indipendentemente dal fatto che il controllo delle versioni sia abilitato per il database.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-131">-   ISOLATIONLEVEL_SNAPSHOT **Note:**  Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], ISOLATIONLEVEL_SNAPSHOT is valid for the *isoLevel* argument whether or not versioning is enabled for the database.</span></span> <span data-ttu-id="fcd6b-132">Se tuttavia l'utente tenta di eseguire un'istruzione e il controllo delle versioni non è abilitato e/o il database non è di sola lettura, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-132">However, an error will occur if the user attempts to execute a statement and versioning is not enabled and/or the database is not read-only.</span></span> <span data-ttu-id="fcd6b-133">Si verifica poi l'errore XACT_E_ISOLATIONLEVEL se ISOLATIONLEVEL_SNAPSHOT è specificato come *isoLevel* ed è stata stabilita una connessione a una versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precedente a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcd6b-133">In addition, the error XACT_E_ISOLATIONLEVEL will occur if ISOLATIONLEVEL_SNAPSHOT is specified as the *isoLevel* when connected to a version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>|  
|<span data-ttu-id="fcd6b-134">*isoFlags*[in]</span><span class="sxs-lookup"><span data-stu-id="fcd6b-134">*isoFlags*[in]</span></span>|<span data-ttu-id="fcd6b-135">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce un errore per qualsiasi valore diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns an error for any value other than zero.</span></span>|  
|<span data-ttu-id="fcd6b-136">*pOtherOptions*[in]</span><span class="sxs-lookup"><span data-stu-id="fcd6b-136">*pOtherOptions*[in]</span></span>|<span data-ttu-id="fcd6b-137">Se non è NULL, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client richiede l'oggetto Options dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-137">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider requests the options object from the interface.</span></span> <span data-ttu-id="fcd6b-138">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce XACT_E_NOTIMEOUT se il membro *ulTIMEOUT* dell'oggetto options è diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-138">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTIMEOUT if the options object's *ulTimeout* member is not zero.</span></span> <span data-ttu-id="fcd6b-139">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client ignora il valore del membro *szDescription* .</span><span class="sxs-lookup"><span data-stu-id="fcd6b-139">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider ignores the value of the *szDescription* member.</span></span>|  
|<span data-ttu-id="fcd6b-140">*pulTransactionLevel*[out]</span><span class="sxs-lookup"><span data-stu-id="fcd6b-140">*pulTransactionLevel*[out]</span></span>|<span data-ttu-id="fcd6b-141">Se non è NULL, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce il livello annidato della transazione.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-141">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns the nested level of the transaction.</span></span>|  
  
 <span data-ttu-id="fcd6b-142">Per le transazioni locali, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client implementa i parametri **ITransaction:: Abort** come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-142">For local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransaction::Abort** parameters as follows.</span></span>  
  
|<span data-ttu-id="fcd6b-143">Parametro</span><span class="sxs-lookup"><span data-stu-id="fcd6b-143">Parameter</span></span>|<span data-ttu-id="fcd6b-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcd6b-144">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fcd6b-145">*pboidReason*[in]</span><span class="sxs-lookup"><span data-stu-id="fcd6b-145">*pboidReason*[in]</span></span>|<span data-ttu-id="fcd6b-146">Ignorato se impostato.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-146">Ignored if set.</span></span> <span data-ttu-id="fcd6b-147">Può essere NULL.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-147">Can safely be NULL.</span></span>|  
|<span data-ttu-id="fcd6b-148">*fRetaining*[in]</span><span class="sxs-lookup"><span data-stu-id="fcd6b-148">*fRetaining*[in]</span></span>|<span data-ttu-id="fcd6b-149">Quando è TRUE, una nuova transazione viene iniziata implicitamente per la sessione.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-149">When TRUE, a new transaction is implicitly begun for the session.</span></span> <span data-ttu-id="fcd6b-150">È necessario che il consumer esegua il commit o termini la transazione.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-150">The transaction must be committed or terminated by the consumer.</span></span> <span data-ttu-id="fcd6b-151">Se è FALSE, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client Ripristina la modalità autocommit per la sessione.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-151">When FALSE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reverts to autocommit mode for the session.</span></span>|  
|<span data-ttu-id="fcd6b-152">*fAsync*[in]</span><span class="sxs-lookup"><span data-stu-id="fcd6b-152">*fAsync*[in]</span></span>|<span data-ttu-id="fcd6b-153">L'interruzione asincrona non è supportata dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-153">Asynchronous abort is not supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="fcd6b-154">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce XACT_E_NOTSUPPORTED se il valore non è false.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-154">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTSUPPORTED if the value is not FALSE.</span></span>|  
  
 <span data-ttu-id="fcd6b-155">Per le transazioni locali, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client implementa i parametri **ITransaction:: commit** come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-155">For local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransaction::Commit** parameters as follows.</span></span>  
  
|<span data-ttu-id="fcd6b-156">Parametro</span><span class="sxs-lookup"><span data-stu-id="fcd6b-156">Parameter</span></span>|<span data-ttu-id="fcd6b-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcd6b-157">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fcd6b-158">*fRetaining*[in]</span><span class="sxs-lookup"><span data-stu-id="fcd6b-158">*fRetaining*[in]</span></span>|<span data-ttu-id="fcd6b-159">Quando è TRUE, una nuova transazione viene iniziata implicitamente per la sessione.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-159">When TRUE, a new transaction is implicitly begun for the session.</span></span> <span data-ttu-id="fcd6b-160">È necessario che il consumer esegua il commit o termini la transazione.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-160">The transaction must be committed or terminated by the consumer.</span></span> <span data-ttu-id="fcd6b-161">Se è FALSE, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client Ripristina la modalità autocommit per la sessione.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-161">When FALSE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reverts to autocommit mode for the session.</span></span>|  
|<span data-ttu-id="fcd6b-162">*grfTC*[in]</span><span class="sxs-lookup"><span data-stu-id="fcd6b-162">*grfTC*[in]</span></span>|<span data-ttu-id="fcd6b-163">Il provider di OLE DB di Native client non supporta la restituzione asincrona e la fase uno [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fcd6b-163">Asynchronous and phase one returns are not supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="fcd6b-164">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce XACT_E_NOTSUPPORTED per qualsiasi valore diverso da XACTTC_SYNC.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-164">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTSUPPORTED for any value other than XACTTC_SYNC.</span></span>|  
|<span data-ttu-id="fcd6b-165">*grfRM*[in]</span><span class="sxs-lookup"><span data-stu-id="fcd6b-165">*grfRM*[in]</span></span>|<span data-ttu-id="fcd6b-166">Deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-166">Must be 0.</span></span>|  
  
 <span data-ttu-id="fcd6b-167">I [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set di righe del provider di OLE DB di Native client nella sessione vengono conservati in un'operazione di commit o di interruzione locale in base ai valori delle proprietà del set di righe DBPROP_ABORTPRESERVE e DBPROP_COMMITPRESERVE.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-167">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets on the session are preserved on a local commit or abort operation based on the values of the rowset properties DBPROP_ABORTPRESERVE and DBPROP_COMMITPRESERVE.</span></span> <span data-ttu-id="fcd6b-168">Per impostazione predefinita, queste proprietà sono entrambe VARIANT_FALSE e tutti i [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set di righe del provider OLE DB client nativi della sessione vengono persi dopo un'operazione di interruzione o di commit.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-168">By default, these properties are both VARIANT_FALSE and all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets on the session are lost following an abort or commit operation.</span></span>  
  
 <span data-ttu-id="fcd6b-169">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non implementa l'interfaccia **ITransactionObject** .</span><span class="sxs-lookup"><span data-stu-id="fcd6b-169">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not implement the **ITransactionObject** interface.</span></span> <span data-ttu-id="fcd6b-170">Un tentativo del consumer di recuperare un riferimento dell'interfaccia restituisce E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-170">A consumer attempt to retrieve a reference on the interface returns E_NOINTERFACE.</span></span>  
  
 <span data-ttu-id="fcd6b-171">Questo esempio usa **ITransactionLocal**.</span><span class="sxs-lookup"><span data-stu-id="fcd6b-171">This example uses **ITransactionLocal**.</span></span>  
  
```  
// Interfaces used in the example.  
IDBCreateSession*   pIDBCreateSession   = NULL;  
ITransaction*       pITransaction       = NULL;  
IDBCreateCommand*   pIDBCreateCommand   = NULL;  
IRowset*            pIRowset            = NULL;  
  
HRESULT             hr;  
  
// Get the command creation and local transaction interfaces for the  
// session.  
if (FAILED(hr = pIDBCreateSession->CreateSession(NULL,  
     IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand)))  
    {  
    // Process error from session creation. Release any references and  
    // return.  
    }  
  
if (FAILED(hr = pIDBCreateCommand->QueryInterface(IID_ITransactionLocal,  
    (void**) &pITransaction)))  
    {  
    // Process error. Release any references and return.  
    }  
  
// Start the local transaction.  
if (FAILED(hr = ((ITransactionLocal*) pITransaction)->StartTransaction(  
    ISOLATIONLEVEL_REPEATABLEREAD, 0, NULL, NULL)))  
    {  
    // Process error from StartTransaction. Release any references and  
    // return.  
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
    // Get error from update, then terminate.  
    pITransaction->Abort(NULL, FALSE, FALSE);  
    }  
else  
    {  
    if (FAILED(hr = pITransaction->Commit(FALSE, XACTTC_SYNC, 0)))  
        {  
        // Get error from failed commit.  
        }  
    }  
  
if (FAILED(hr))  
    {  
    // Update of data or commit failed. Release any references and  
    // return.  
    }  
  
// Release any references and continue.  
```  
  
## <a name="see-also"></a><span data-ttu-id="fcd6b-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcd6b-172">See Also</span></span>  
 <span data-ttu-id="fcd6b-173">[Transazioni](transactions.md) </span><span class="sxs-lookup"><span data-stu-id="fcd6b-173">[Transactions](transactions.md) </span></span>  
 [<span data-ttu-id="fcd6b-174">Utilizzo dell'isolamento dello snapshot</span><span class="sxs-lookup"><span data-stu-id="fcd6b-174">Working with Snapshot Isolation</span></span>](../native-client/features/working-with-snapshot-isolation.md)  
  
  
