---
title: Esecuzione di operazioni asincrone |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- initialization [SQL Server Native Client]
- database connections [SQL Server Native Client]
- data access [SQL Server Native Client], asynchronous operations
- connections [SQL Server Native Client]
- asynchronous operations [SQL Server Native Client]
- rowsets [SQL Server], initializing
- SQLNCLI, asynchronous operations
- SQL Server Native Client, asynchronous operations
ms.assetid: 8fbd84b4-69cb-4708-9f0f-bbdf69029bcc
author: rothja
ms.author: jroth
ms.openlocfilehash: 4f7e8f4481923cd7da537f921248865d4fff7280
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714263"
---
# <a name="performing-asynchronous-operations"></a><span data-ttu-id="c91d7-102">Esecuzione di operazioni asincrone</span><span class="sxs-lookup"><span data-stu-id="c91d7-102">Performing Asynchronous Operations</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="c91d7-103">consente alle applicazioni di eseguire operazioni asincrone sul database.</span><span class="sxs-lookup"><span data-stu-id="c91d7-103">allows applications to perform asynchronous database operations.</span></span> <span data-ttu-id="c91d7-104">L'elaborazione asincrona consente la restituzione immediata dei metodi senza bloccare il thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="c91d7-104">Asynchronous processing enables methods to return immediately without blocking on the calling thread.</span></span> <span data-ttu-id="c91d7-105">Questa caratteristica offre molto della potenza e della flessibilità del multithreading, senza richiedere allo sviluppatore la creazione esplicita di thread o la gestione della sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="c91d7-105">This allows much of the power and flexibility of multithreading, without requiring the developer to explicitly create threads or handle synchronization.</span></span> <span data-ttu-id="c91d7-106">Le applicazioni richiedono l'elaborazione asincrona in caso di inizializzazione di una connessione al database o di inizializzazione del risultato dall'esecuzione di un comando.</span><span class="sxs-lookup"><span data-stu-id="c91d7-106">Applications request asynchronous processing when initializing a database connection, or when initializing the result from the execution of a command.</span></span>  
  
## <a name="opening-and-closing-a-database-connection"></a><span data-ttu-id="c91d7-107">Apertura e chiusura di una connessione al database</span><span class="sxs-lookup"><span data-stu-id="c91d7-107">Opening and Closing a Database Connection</span></span>  
 <span data-ttu-id="c91d7-108">Quando si utilizza il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider di OLE DB di Native client, le applicazioni progettate per inizializzare un oggetto origine dati in modo asincrono possono impostare il bit DBPROPVAL_ASYNCH_INITIALIZE nella proprietà DBPROP_INIT_ASYNCH prima di chiamare **IDBInitialize:: Initialize**.</span><span class="sxs-lookup"><span data-stu-id="c91d7-108">When using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, applications designed to initialize a data source object asynchronously can set the DBPROPVAL_ASYNCH_INITIALIZE bit in the DBPROP_INIT_ASYNCH property prior to calling **IDBInitialize::Initialize**.</span></span> <span data-ttu-id="c91d7-109">Quando questa proprietà è impostata, il provider restituisce immediatamente dalla chiamata a **Initialize** S_OK, se l'operazione è stata completata immediatamente, o DB_S_ASYNCHRONOUS, se l'inizializzazione continua in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="c91d7-109">When this property is set, the provider returns immediately from the call to **Initialize** with either S_OK, if the operation has completed immediately, or DB_S_ASYNCHRONOUS, if the initialization is continuing asynchronously.</span></span> <span data-ttu-id="c91d7-110">Le applicazioni possono eseguire query per l'interfaccia **IDBAsynchStatus** o [ISSAsynchStatus](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)nell'oggetto origine dati, quindi chiamare **IDBAsynchStatus:: GetStatus** o[ISSAsynchStatus:: WaitForAsynchCompletion](../../native-client-ole-db-interfaces/issasynchstatus-waitforasynchcompletion-ole-db.md) per ottenere lo stato dell'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="c91d7-110">Applications can query for the **IDBAsynchStatus** or [ISSAsynchStatus](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)interface on the data source object, and then call **IDBAsynchStatus::GetStatus** or[ISSAsynchStatus::WaitForAsynchCompletion](../../native-client-ole-db-interfaces/issasynchstatus-waitforasynchcompletion-ole-db.md) to get the status of the initialization.</span></span>  
  
 <span data-ttu-id="c91d7-111">È stata inoltre aggiunta la proprietà SSPROP_ISSAsynchStatus al set di proprietà DBPROPSET_SQLSERVERROWSET.</span><span class="sxs-lookup"><span data-stu-id="c91d7-111">In addition, the SSPROP_ISSAsynchStatus property has been added to the DBPROPSET_SQLSERVERROWSET property set.</span></span> <span data-ttu-id="c91d7-112">I provider che supportano l'interfaccia **ISSAsynchStatus** devono implementare questa proprietà con un valore VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="c91d7-112">Providers that support the **ISSAsynchStatus** interface must implement this property with a value of VARIANT_TRUE.</span></span>  
  
 <span data-ttu-id="c91d7-113">È possibile chiamare **IDBAsynchStatus::Abort** o [ISSAsynchStatus::Abort](../../native-client-ole-db-interfaces/issasynchstatus-abort-ole-db.md) per annullare la chiamata a **Initialize** asincrona.</span><span class="sxs-lookup"><span data-stu-id="c91d7-113">**IDBAsynchStatus::Abort** or [ISSAsynchStatus::Abort](../../native-client-ole-db-interfaces/issasynchstatus-abort-ole-db.md) can be called to cancel the asynchronous **Initialize** call.</span></span> <span data-ttu-id="c91d7-114">Il consumer deve richiedere in modo esplicito l'inizializzazione asincrona dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c91d7-114">The consumer must explicitly request Asynchronous Data Source Initialization.</span></span> <span data-ttu-id="c91d7-115">In caso contrario, **IDBInitialize::Initialize** non restituisce nulla fino a quando l'oggetto origine dati non viene inizializzato completamente.</span><span class="sxs-lookup"><span data-stu-id="c91d7-115">Otherwise, **IDBInitialize::Initialize** does not return until the data source object is completely initialized.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c91d7-116">Gli oggetti origine dati utilizzati per il pool di connessioni non possono chiamare l'interfaccia **ISSAsynchStatus** nel [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider OLE DB di Native Client.</span><span class="sxs-lookup"><span data-stu-id="c91d7-116">Data source objects used for connection pooling cannot call the **ISSAsynchStatus** interface in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="c91d7-117">L'interfaccia **ISSAsynchStatus** non è esposta per gli oggetti di origine dati inseriti in pool.</span><span class="sxs-lookup"><span data-stu-id="c91d7-117">The **ISSAsynchStatus** interface is not exposed for pooled data source objects.</span></span>  
>   
>  <span data-ttu-id="c91d7-118">Se un'applicazione forza in modo esplicito l'uso del motore del cursore, **IOpenRowset::OpenRowset** e **IMultipleResults::GetResult** non supporteranno l'elaborazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="c91d7-118">If an application explicitly forces use of the cursor engine, **IOpenRowset::OpenRowset** and **IMultipleResults::GetResult** will not support asynchronous processing.</span></span>  
>   
>  <span data-ttu-id="c91d7-119">Inoltre, la DLL proxy/stub di comunicazione remota (in MDAC 2,8) non è in grado di chiamare l'interfaccia **ISSAsynchStatus** in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="c91d7-119">In addition, the remoting proxy/stub dll (in MDAC 2.8) cannot call the **ISSAsynchStatus** interface in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="c91d7-120">L'interfaccia **ISSAsynchStatus** non è esposta attraverso i servizi remoti.</span><span class="sxs-lookup"><span data-stu-id="c91d7-120">The **ISSAsynchStatus** interface is not exposed through remoting.</span></span>  
>   
>  <span data-ttu-id="c91d7-121">I componenti del servizio non supportano **ISSAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="c91d7-121">Service Components do not support **ISSAsynchStatus**.</span></span>  
  
## <a name="execution-and-rowset-initialization"></a><span data-ttu-id="c91d7-122">Esecuzione e inizializzazione del set di righe</span><span class="sxs-lookup"><span data-stu-id="c91d7-122">Execution and Rowset Initialization</span></span>  
 <span data-ttu-id="c91d7-123">Le applicazioni progettate per aprire in modo asincrono il risultato dall'esecuzione di un comando possono impostare il bit DBPROPVAL_ASYNCH_INITIALIZE nella proprietà DBPROP_ROWSET_ASYNCH.</span><span class="sxs-lookup"><span data-stu-id="c91d7-123">Applications designed to asynchronously open the result from the execution of a command can set the DBPROPVAL_ASYNCH_INITIALIZE bit in the DBPROP_ROWSET_ASYNCH property.</span></span> <span data-ttu-id="c91d7-124">Quando questo bit viene impostato prima di chiamare **IDBInitialize::Initialize**, **ICommand::Execute**, **IOpenRowset::OpenRowset** o **IMultipleResults::GetResult**, l'argomento *riid* deve essere impostato su IID_IDBAsynchStatus, IID_ISSAsynchStatus o IID_IUnknown.</span><span class="sxs-lookup"><span data-stu-id="c91d7-124">When setting this bit prior to calling **IDBInitialize::Initialize**, **ICommand::Execute**, **IOpenRowset::OpenRowset** or **IMultipleResults::GetResult**, the *riid* argument must be set to IID_IDBAsynchStatus, IID_ISSAsynchStatus, or IID_IUnknown.</span></span>  
  
 <span data-ttu-id="c91d7-125">Il metodo restituisce immediatamente S_OK se l'inizializzazione del set di righe viene completata immediatamente oppure DB_S_ASYNCHRONOUS se il set di righe continua a essere inizializzato in modo asincrono, con *ppRowset* impostato sull'interfaccia richiesta nel set di righe.</span><span class="sxs-lookup"><span data-stu-id="c91d7-125">The method returns immediately with S_OK if the rowset initialization completes immediately, or with DB_S_ASYNCHRONOUS if the rowset continues initializing asynchronously, with *ppRowset* set to the requested interface on the rowset.</span></span> <span data-ttu-id="c91d7-126">Per il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider di OLE DB di Native client, questa interfaccia può essere solo **IDBAsynchStatus** o **ISSAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="c91d7-126">For the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, this interface can only be **IDBAsynchStatus** or **ISSAsynchStatus**.</span></span> <span data-ttu-id="c91d7-127">Finché il set di righe non è completamente inizializzato, l'interfaccia si comporta come se fosse in stato sospeso e la chiamata a **QueryInterface** per le interfacce diverse da **IID_IDBAsynchStatus** o \*\*IID_ISSAsynchStatus \*\* può restituire E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="c91d7-127">Until the rowset is fully initialized, this interface behaves as if it were in a suspended state, and calling **QueryInterface** for interfaces other than **IID_IDBAsynchStatus** or **IID_ISSAsynchStatus** may return E_NOINTERFACE.</span></span> <span data-ttu-id="c91d7-128">A meno che il consumer non richieda in modo esplicito l'elaborazione asincrona, il set di righe viene inizializzato in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="c91d7-128">Unless the consumer explicitly requests asynchronous processing, the rowset is initialized synchronously.</span></span> <span data-ttu-id="c91d7-129">Tutte le interfacce richieste sono disponibili quando **IDBAsynchStaus::GetStatus** o **ISSAsynchStatus::WaitForAsynchCompletion** restituisce l'indicazione che l'operazione asincrona è completa.</span><span class="sxs-lookup"><span data-stu-id="c91d7-129">All requested interfaces are available when **IDBAsynchStaus::GetStatus** or **ISSAsynchStatus::WaitForAsynchCompletion** returns with the indication that asynchronous operation is complete.</span></span> <span data-ttu-id="c91d7-130">Ciò non significa necessariamente che il set di righe è completamente popolato, ma che è completo e del tutto funzionale.</span><span class="sxs-lookup"><span data-stu-id="c91d7-130">This does not necessarily mean that the rowset is fully populated, but it is complete and fully functional.</span></span>  
  
 <span data-ttu-id="c91d7-131">Se il comando eseguito non restituisce un set di righe, restituisce comunque immediatamente un oggetto che supporta **IDBAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="c91d7-131">If the executed command does not return a rowset, it still returns immediately with an object that supports **IDBAsynchStatus**.</span></span>  
  
 <span data-ttu-id="c91d7-132">Se è necessario ottenere più risultati dall'esecuzione di comandi asincrona, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c91d7-132">If you need to get multiple results from asynchronous command execution, you should:</span></span>  
  
-   <span data-ttu-id="c91d7-133">Impostare il bit DBPROPVAL_ASYNCH_INITIALIZE della proprietà DBPROP_ROWSET_ASYNCH prima di eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="c91d7-133">Set the DBPROPVAL_ASYNCH_INITIALIZE bit of the DBPROP_ROWSET_ASYNCH property, before executing the command.</span></span>  
  
-   <span data-ttu-id="c91d7-134">Chiamare **ICommand::Execute** e richiedere **IMultipleResults**.</span><span class="sxs-lookup"><span data-stu-id="c91d7-134">Call **ICommand::Execute**, and request **IMultipleResults**.</span></span>  
  
 <span data-ttu-id="c91d7-135">Le interfacce **IDBAsynchStatus** e **ISSAsynchStatus** possono quindi essere ottenute eseguendo una query sull'interfaccia con più risultati con **QueryInterface**.</span><span class="sxs-lookup"><span data-stu-id="c91d7-135">The **IDBAsynchStatus** and **ISSAsynchStatus** interfaces can then be obtained by querying the multiple results interface using **QueryInterface**.</span></span>  
  
 <span data-ttu-id="c91d7-136">Al termine dell'esecuzione del comando, è possibile usare **IMultipleResults** normalmente, con un'eccezione dal caso sincrono: può essere restituito DB_S_ASYNCHRONOUS. In tal caso, è possibile usare **IDBAsynchStatus** o **ISSAsynchStatus** per determinare il momento in cui l'operazione è completata.</span><span class="sxs-lookup"><span data-stu-id="c91d7-136">When the command has finished executing, **IMultipleResults** can be used as normal, with one exception from the synchronous case: DB_S_ASYNCHRONOUS may be returned, in which case **IDBAsynchStatus** or **ISSAsynchStatus** can be used to determine when the operation is complete.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c91d7-137">Esempi</span><span class="sxs-lookup"><span data-stu-id="c91d7-137">Examples</span></span>  
 <span data-ttu-id="c91d7-138">Nell'esempio seguente l'applicazione chiama un metodo non bloccante, esegue altre attività di elaborazione e quindi torna a elaborare i risultati.</span><span class="sxs-lookup"><span data-stu-id="c91d7-138">In the following example, the application calls a non-blocking method, does some other processing, and then returns to process the results.</span></span> <span data-ttu-id="c91d7-139">**ISSAsynchStatus::WaitForAsynchCompletion** resta in attesa dell'oggetto evento interno fino al completamento dell'operazione di esecuzione asincrona o allo scadere della quantità di tempo specificata da *dwMilisecTimeOut*.</span><span class="sxs-lookup"><span data-stu-id="c91d7-139">**ISSAsynchStatus::WaitForAsynchCompletion** waits on the internal event object until the asynchronously executing operation is done or the amount of time specified by *dwMilisecTimeOut* is passed.</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
  
DBPROPSET CmdPropset[1];  
DBPROP CmdProperties[1];  
  
CmdPropset[0].rgProperties = CmdProperties;  
CmdPropset[0].cProperties = 1;  
CmdPropset[0].guidPropertySet = DBPROPSET_ROWSET;  
  
// Set asynch mode for command.  
CmdProperties[0].dwPropertyID = DBPROP_ROWSET_ASYNCH;  
CmdProperties[0].vValue.vt = VT_I4;  
CmdProperties[0].vValue.lVal = DBPROPVAL_ASYNCH_INITIALIZE;  
CmdProperties[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
  
hr = pICommandProps->SetProperties(1, CmdPropset);  
  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work here...  
  
   hr = pISSAsynchStatus->WaitForAsynchCompletion(dwMilisecTimeOut);  
   if ( hr == S_OK)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
      pISSAsynchStatus->Release();  
   }  
}  
```  
  
 <span data-ttu-id="c91d7-140">**ISSAsynchStatus::WaitForAsynchCompletion** resta in attesa dell'oggetto evento interno fino al completamento dell'operazione di esecuzione asincrona o al passaggio del valore *dwMilisecTimeOut*.</span><span class="sxs-lookup"><span data-stu-id="c91d7-140">**ISSAsynchStatus::WaitForAsynchCompletion** waits on the internal event object until the asynchronously executing operation is done or the *dwMilisecTimeOut* value is passed.</span></span>  
  
 <span data-ttu-id="c91d7-141">Nell'esempio seguente viene illustrata l'elaborazione asincrona con più set di risultati:</span><span class="sxs-lookup"><span data-stu-id="c91d7-141">The following example shows asynchronous processing with multiple result sets:</span></span>  
  
```  
DBPROP CmdProperties[1];  
  
// Set asynch mode for command.  
CmdProperties[0].dwPropertyID = DBPROP_ROWSET_ASYNCH;  
CmdProperties[0].vValue.vt = VT_I4;  
CmdProperties[0].vValue.lVal = DBPROPVAL_ASYNCH_INITIALIZE;  
  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_IMultipleResults,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pIMultipleResults);  
  
// Use GetResults for ISSAsynchStatus.  
hr = pIMultipleResults->GetResult(IID_ISSAsynchStatus, (void **) &pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work here...  
  
   hr = pISSAsynchStatus->WaitForAsynchCompletion(dwMilisecTimeOut);  
   if (hr == S_OK)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
      pISSAsynchStatus->Release();  
   }  
}  
```  
  
 <span data-ttu-id="c91d7-142">Per impedire il blocco, il client può controllare lo stato di un'operazione asincrona in esecuzione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c91d7-142">To prevent blocking, the client can check the status of a running asynchronous operation, as in the following example:</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);   
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   do{  
      // Do some work...  
      hr = pISSAsynchStatus->GetStatus(DB_NULL_HCHAPTER, DBASYNCHOP_OPEN, NULL, NULL, &ulAsynchPhase, NULL);  
   }while (DBASYNCHPHASE_COMPLETE != ulAsynchPhase)  
   if SUCCEEDED(hr)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
   }  
   pIDBAsynchStatus->Release();  
}  
```  
  
 <span data-ttu-id="c91d7-143">Nell'esempio seguente viene illustrato come annullare l'operazione asincrona attualmente in esecuzione:</span><span class="sxs-lookup"><span data-stu-id="c91d7-143">The following example demonstrates how you can cancel the currently running asynchronous operation:</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work...  
   hr = pISSAsynchStatus->Abort(DB_NULL_HCHAPTER, DBASYNCHOP_OPEN);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c91d7-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c91d7-144">See Also</span></span>  
 <span data-ttu-id="c91d7-145">[Funzionalità di SQL Server Native Client](sql-server-native-client-features.md) </span><span class="sxs-lookup"><span data-stu-id="c91d7-145">[SQL Server Native Client Features](sql-server-native-client-features.md) </span></span>  
 <span data-ttu-id="c91d7-146">[Proprietà e comportamenti dei set di righe](../../native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span><span class="sxs-lookup"><span data-stu-id="c91d7-146">[Rowset Properties and Behaviors](../../native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span></span>  
 [<span data-ttu-id="c91d7-147">ISSAsynchStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="c91d7-147">ISSAsynchStatus &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)  
  
  
