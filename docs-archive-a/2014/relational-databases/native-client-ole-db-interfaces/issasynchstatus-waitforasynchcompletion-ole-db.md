---
title: ISSAsynchStatus::WaitForAsynchCompletion (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- WaitForAsynchCompletion method
ms.assetid: 9f65e9e7-eb93-47a1-bc42-acd4649fbd0e
author: rothja
ms.author: jroth
ms.openlocfilehash: f57211d1c62535828704dc971e345b412c284cf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626745"
---
# <a name="issasynchstatuswaitforasynchcompletion-ole-db"></a><span data-ttu-id="fcc7e-102">ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="fcc7e-102">ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)</span></span>
  <span data-ttu-id="fcc7e-103">Resta in attesa fino al completamento dell'operazione di esecuzione asincrona o fino al verificarsi di un timeout.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-103">Waits until the asynchronously executing operation is complete or until a time-out occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcc7e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fcc7e-104">Syntax</span></span>  
  
```  
  
HRESULT WaitForAsynchCompletion(   
  DWORD dwMillisecTimeOut);  
```  
  
## <a name="arguments"></a><span data-ttu-id="fcc7e-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="fcc7e-105">Arguments</span></span>  
 <span data-ttu-id="fcc7e-106">*dwMillisecTimeOut*[in]</span><span class="sxs-lookup"><span data-stu-id="fcc7e-106">*dwMillisecTimeOut*[in]</span></span>  
 <span data-ttu-id="fcc7e-107">Timeout in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-107">Time-out in milliseconds.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="fcc7e-108">Valori del codice restituito</span><span class="sxs-lookup"><span data-stu-id="fcc7e-108">Return Code Values</span></span>  
 <span data-ttu-id="fcc7e-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="fcc7e-109">S_OK</span></span>  
 <span data-ttu-id="fcc7e-110">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-110">The method succeeded.</span></span>  
  
 <span data-ttu-id="fcc7e-111">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="fcc7e-111">E_UNEXPECTED</span></span>  
 <span data-ttu-id="fcc7e-112">Un set di righe è in uno stato inutilizzato perché è stato chiamato **ITransaction:: commit** o **ITransaction:: Abort** oppure il set di righe è stato annullato durante la fase di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-112">A rowset is in an unused state because **ITransaction::Commit** or **ITransaction::Abort** has been called or the rowset was cancelled during its initialization phase.</span></span>  
  
 <span data-ttu-id="fcc7e-113">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="fcc7e-113">DB_E_CANCELED</span></span>  
 <span data-ttu-id="fcc7e-114">L'elaborazione asincrona è stata annullata durante il popolamento del set di righe o l'inizializzazione dell'oggetto origine dati.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-114">Asynchronous processing was cancelled during rowset population or data source object initialization.</span></span>  
  
 <span data-ttu-id="fcc7e-115">DB_S_ASYNCHRONOUS</span><span class="sxs-lookup"><span data-stu-id="fcc7e-115">DB_S_ASYNCHRONOUS</span></span>  
 <span data-ttu-id="fcc7e-116">L'operazione non è stata ancora completata anche se è stato raggiunto il timeout specificato.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-116">The operation has not yet completed even though specified time-out has been reached.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcc7e-117">Oltre ai valori di codice restituiti elencati in precedenza, il metodo **ISSAsynchStatus::WaitForAsynchCompletion** supporta anche i valori di codice restituiti dai metodi OLEDB di base **ICommand::Execute** e **IDBInitialize::Initialize**.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-117">In addition to the return code values listed above, the **ISSAsynchStatus::WaitForAsynchCompletion** method also supports the return code values returned by the core OLEDB **ICommand::Execute** and **IDBInitialize::Initialize** methods.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcc7e-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fcc7e-118">Remarks</span></span>  
 <span data-ttu-id="fcc7e-119">Il metodo **ISSAsynchStatus::WaitForAsynchCompletion** non verrà restituito fino al superamento del valore di timeout (in millisecondi) o al completamento dell'operazione in sospeso.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-119">The **ISSAsynchStatus::WaitForAsynchCompletion** method will not return until the time-out value (in milliseconds) has passed or the pending operation is done.</span></span> <span data-ttu-id="fcc7e-120">L'oggetto **Command** dispone di una proprietà **CommandTimeout** che controlla il numero di secondi di esecuzione di una query prima che si verifichi il timeout. La proprietà **CommandTimeout** verrà ignorata se utilizzata insieme al metodo **ISSAsynchStatus:: WaitForAsynchCompletion** .</span><span class="sxs-lookup"><span data-stu-id="fcc7e-120">The **Command** object has a **CommandTimeout** property that controls the number of seconds a query will run before timing out. The **CommandTimeout** property will be ignored if used in conjunction with **ISSAsynchStatus::WaitForAsynchCompletion** method.</span></span>  
  
 <span data-ttu-id="fcc7e-121">La proprietà di timeout viene ignorata per le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-121">The time-out property is ignored for asynchronous operations.</span></span> <span data-ttu-id="fcc7e-122">Il parametro di timeout di **ISSAsynchStatus::WaitForAsynchCompletion** specifica la quantità massima di tempo che deve trascorrere prima che il controllo venga restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-122">The time-out parameter of **ISSAsynchStatus::WaitForAsynchCompletion** specifies the maximum amount of time that will elapse before control is returned to the caller.</span></span> <span data-ttu-id="fcc7e-123">Se questo timeout scade, verrà restituito DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-123">If this time-out expires, DB_S_ASYNCHRONOUS will be returned.</span></span> <span data-ttu-id="fcc7e-124">I timeout non annullano mai operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-124">Time-outs never cancel asynchronous operations.</span></span> <span data-ttu-id="fcc7e-125">Se l'applicazione deve annullare un'operazione asincrona che non viene completata entro il periodo di timeout, deve attendere lo scadere del timeout e quindi annullare in modo esplicito l'operazione se viene restituito DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-125">If the application needs to cancel an asynchronous operation that does not complete within a time-out period, it must wait for the time-out and then explicitly cancel the operation if DB_S_ASYNCHRONOUS is returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcc7e-126">Quando si usano i componenti del servizio OLE DB, è possibile che venga restituito S_OK quando è previsto DB_S_ASYNCHRONOUS. Quando viene restituito S_OK o DB_S_ASYNCHRONOUS, le applicazioni devono pertanto chiamare [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) per verificare il completamento.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-126">When the OLE DB Service Components are used, S_OK may be returned when DB_S_ASYNCHRONOUS is expected, so applications should call [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) to check for completion when S_OK or DB_S_ASYNCHRONOUS is returned.</span></span>  
  
 <span data-ttu-id="fcc7e-127">Se il valore di *dwMillisecTimeOut* è impostato su INFINITE, il metodo **ISSAsynchStatus::WaitForAsynchCompletion** mantiene il blocco fino al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-127">If the *dwMillisecTimeOut* value is set to INFINITE, the **ISSAsynchStatus::WaitForAsynchCompletion** method blocks until the operation is done.</span></span> <span data-ttu-id="fcc7e-128">Se il valore di *dwMillisecTimeOut* è impostato su 0, il metodo restituirà immediatamente lo stato dell'operazione in sospeso.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-128">If the *dwMillisecTimeOut* value is set to 0, then the method will return immediately with the status of the pending operation.</span></span> <span data-ttu-id="fcc7e-129">Se il timeout scade prima del completamento dell'operazione, viene restituito DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-129">If the time-out expires before the operation is complete DB_S_ASYNCHRONOUS will be returned.</span></span>  
  
 <span data-ttu-id="fcc7e-130">Se l'operazione viene completata prima dello scadere del timeout, il valore HRESULT restituito sarà quello restituito dall'operazione, ovvero il valore HRESULT che sarebbe stato restituito se l'operazione fosse stata eseguita in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-130">If the operation completes before the time-out expires, the returned HRESULT will be the HRESULT returned by the operation (the HRESULT that would have been returned had the operation been performed synchronously).</span></span>  
  
 <span data-ttu-id="fcc7e-131">È stata inoltre aggiunta la proprietà SSPROP_ISSAsynchStatus al set di proprietà DBPROPSET_SQLSERVERROWSET.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-131">In addition, the SSPROP_ISSAsynchStatus property has been added to the DBPROPSET_SQLSERVERROWSET property set.</span></span> <span data-ttu-id="fcc7e-132">I provider che supportano l'interfaccia [ISSAsynchStatus](issasynchstatus-ole-db.md) devono implementare questa proprietà con un valore VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="fcc7e-132">Providers that support the [ISSAsynchStatus](issasynchstatus-ole-db.md) interface must implement this property with a value of VARIANT_TRUE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc7e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcc7e-133">See Also</span></span>  
 <span data-ttu-id="fcc7e-134">[Esecuzione di operazioni asincrone](../native-client/features/performing-asynchronous-operations.md) </span><span class="sxs-lookup"><span data-stu-id="fcc7e-134">[Performing Asynchronous Operations](../native-client/features/performing-asynchronous-operations.md) </span></span>  
 [<span data-ttu-id="fcc7e-135">ISSAsynchStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="fcc7e-135">ISSAsynchStatus &#40;OLE DB&#41;</span></span>](issasynchstatus-ole-db.md)  
  
  
