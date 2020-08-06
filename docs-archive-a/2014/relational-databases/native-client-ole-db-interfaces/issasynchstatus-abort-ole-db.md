---
title: ISSAsynchStatus::Abort (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus::Abort (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Abort method
ms.assetid: 2a4bd312-839a-45a8-a299-fc8609be9a2a
author: rothja
ms.author: jroth
ms.openlocfilehash: 0fb352b6541240126dcd4c60521b93d57d6839f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718113"
---
# <a name="issasynchstatusabort-ole-db"></a><span data-ttu-id="1967e-102">ISSAsynchStatus::Abort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="1967e-102">ISSAsynchStatus::Abort (OLE DB)</span></span>
  <span data-ttu-id="1967e-103">Annulla un'operazione di esecuzione asincrona.</span><span class="sxs-lookup"><span data-stu-id="1967e-103">Cancels an asynchronously executing operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1967e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1967e-104">Syntax</span></span>  
  
```  
  
HRESULT Abort(  
  HCHAPTER hChapter,  
  DBASYNCHOP eOperation);  
```  
  
## <a name="arguments"></a><span data-ttu-id="1967e-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1967e-105">Arguments</span></span>  
 <span data-ttu-id="1967e-106">*hChapter*[in]</span><span class="sxs-lookup"><span data-stu-id="1967e-106">*hChapter*[in]</span></span>  
 <span data-ttu-id="1967e-107">Handle del capitolo per il quale interrompere l'operazione.</span><span class="sxs-lookup"><span data-stu-id="1967e-107">The handle of the chapter for which to abort the operation.</span></span> <span data-ttu-id="1967e-108">Se l'oggetto chiamato non è un oggetto set di righe o l'operazione non è valida per un capitolo, il chiamante deve impostare *hChapter* su DB_NULL_HCHAPTER.</span><span class="sxs-lookup"><span data-stu-id="1967e-108">If the object being called is not a rowset object or the operation does not apply to a chapter, the caller must set *hChapter* to DB_NULL_HCHAPTER.</span></span>  
  
 <span data-ttu-id="1967e-109">*eOperation*[in]</span><span class="sxs-lookup"><span data-stu-id="1967e-109">*eOperation*[in]</span></span>  
 <span data-ttu-id="1967e-110">Operazione da interrompere.</span><span class="sxs-lookup"><span data-stu-id="1967e-110">The operation to abort.</span></span> <span data-ttu-id="1967e-111">Deve corrispondere al valore seguente:</span><span class="sxs-lookup"><span data-stu-id="1967e-111">This should be the following value:</span></span>  
  
 <span data-ttu-id="1967e-112">DBASYNCHOP_OPEN: la richiesta di annullamento si applica all'apertura o al popolamento asincrono di un set di righe o all'inizializzazione asincrona di un oggetto origine dati.</span><span class="sxs-lookup"><span data-stu-id="1967e-112">DBASYNCHOP_OPEN-The request to cancel applies to the asynchronous opening or population of a rowset or to the asynchronous initialization of a data source object.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="1967e-113">Valori del codice restituito</span><span class="sxs-lookup"><span data-stu-id="1967e-113">Return Code Values</span></span>  
 <span data-ttu-id="1967e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1967e-114">S_OK</span></span>  
 <span data-ttu-id="1967e-115">La richiesta di annullare l'operazione asincrona è stata elaborata.</span><span class="sxs-lookup"><span data-stu-id="1967e-115">The request to cancel the asynchronous operation was processed.</span></span> <span data-ttu-id="1967e-116">Questo non garantisce che l'operazione stessa sia stata annullata.</span><span class="sxs-lookup"><span data-stu-id="1967e-116">This does not guarantee that the operation itself was canceled.</span></span> <span data-ttu-id="1967e-117">Per determinare se è stata effettivamente annullata, il consumer deve chiamare [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) e verificare DB_E_CANCELED. È tuttavia possibile che non venga restituito nella chiamata successiva.</span><span class="sxs-lookup"><span data-stu-id="1967e-117">To determine whether the operation was canceled, the consumer should call [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) and check for DB_E_CANCELED; however, it might not be returned in the very next call.</span></span>  
  
 <span data-ttu-id="1967e-118">DB_E_CANTCANCEL</span><span class="sxs-lookup"><span data-stu-id="1967e-118">DB_E_CANTCANCEL</span></span>  
 <span data-ttu-id="1967e-119">Non è stato possibile annullare l'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="1967e-119">The asynchronous operation cannot be canceled.</span></span>  
  
 <span data-ttu-id="1967e-120">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="1967e-120">DB_E_CANCELED</span></span>  
 <span data-ttu-id="1967e-121">La richiesta di interrompere l'operazione asincrona è stata annullata durante le notifiche.</span><span class="sxs-lookup"><span data-stu-id="1967e-121">The request to abort the asynchronous operation was canceled during notifications.</span></span> <span data-ttu-id="1967e-122">L'operazione viene ancora eseguita in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="1967e-122">The operation is still being executed asynchronously.</span></span>  
  
 <span data-ttu-id="1967e-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1967e-123">E_FAIL</span></span>  
 <span data-ttu-id="1967e-124">Si è verificato un errore specifico del provider.</span><span class="sxs-lookup"><span data-stu-id="1967e-124">A provider-specific error occurred.</span></span>  
  
 <span data-ttu-id="1967e-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1967e-125">E_INVALIDARG</span></span>  
 <span data-ttu-id="1967e-126">Il parametro *hChapter* non è DB_NULL_HCHAPTER o *eOperation* non è DBASYNCH_OPEN.</span><span class="sxs-lookup"><span data-stu-id="1967e-126">The *hChapter* parameter is not DB_NULL_HCHAPTER or *eOperation* is not DBASYNCH_OPEN.</span></span>  
  
 <span data-ttu-id="1967e-127">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="1967e-127">E_UNEXPECTED</span></span>  
 <span data-ttu-id="1967e-128">**ISSAsynchStatus:: Abort** è stato chiamato su un oggetto origine dati su cui **IDBInitialize:: Initialize** non è stato chiamato oppure non è stato completato.</span><span class="sxs-lookup"><span data-stu-id="1967e-128">**ISSAsynchStatus::Abort** was called on a data source object on which **IDBInitialize::Initialize** has not been called, or has not completed.</span></span>  
  
 <span data-ttu-id="1967e-129">**ISSAsynchStatus:: Abort** è stato chiamato su un oggetto origine dati su cui **IDBInitialize:: Initialize** è stato chiamato ma successivamente annullato prima dell'inizializzazione o si è verificato un timeout. L'oggetto origine dati non è ancora inizializzato.</span><span class="sxs-lookup"><span data-stu-id="1967e-129">**ISSAsynchStatus::Abort** was called on a data source object on which **IDBInitialize::Initialize** was called but subsequently canceled before initialization, or has timed out. The data source object is still uninitialized.</span></span>  
  
 <span data-ttu-id="1967e-130">**ISSAsynchStatus:: Abort** è stato chiamato su un set di righe su cui è stato precedentemente chiamato **ITransaction:: commit** o **ITransaction:: Abort** e il set di righe non è sopravvissuto al commit o all'interruzione ed è in uno stato non valido.</span><span class="sxs-lookup"><span data-stu-id="1967e-130">**ISSAsynchStatus::Abort** was called on a rowset on which **ITransaction::Commit** or **ITransaction::Abort** was previously called, and the rowset did not survive the commit or abort and is in a zombie state.</span></span>  
  
 <span data-ttu-id="1967e-131">**ISSAsynchStatus::Abort** è stato chiamato su un set di righe annullato in modo asincrono nella fase di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="1967e-131">**ISSAsynchStatus::Abort** was called on a rowset that was asynchronously canceled in its initialization phase.</span></span> <span data-ttu-id="1967e-132">Il set di righe si trova in uno stato non valido.</span><span class="sxs-lookup"><span data-stu-id="1967e-132">The rowset is in a zombie state.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1967e-133">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1967e-133">Remarks</span></span>  
 <span data-ttu-id="1967e-134">L'interruzione dell'inizializzazione di un set di righe o di un oggetto origine dati potrebbe lasciare il set di righe o l'oggetto origine dati in uno stato non valido e determinare la restituzione di E_UNEXPECTED da parte di tutti i metodi ad eccezione di **IUnknown**.</span><span class="sxs-lookup"><span data-stu-id="1967e-134">Aborting the initialization of a rowset or data source object might leave the rowset or data source object in a zombie state, such that all methods other than **IUnknown** methods return E_UNEXPECTED.</span></span> <span data-ttu-id="1967e-135">Quando ciò accade, l'unica azione possibile per il consumer consiste nel rilasciare il set di righe o l'oggetto origine dati.</span><span class="sxs-lookup"><span data-stu-id="1967e-135">When this happens, the only possible action for the consumer is to release the rowset or data source object.</span></span>  
  
 <span data-ttu-id="1967e-136">Se si chiama **ISSAsynchStatus::Abort** e si passa un valore per *eOperation* diverso da DBASYNCHOP_OPEN, viene restituito S_OK.</span><span class="sxs-lookup"><span data-stu-id="1967e-136">Calling **ISSAsynchStatus::Abort** and passing a value for *eOperation* other than DBASYNCHOP_OPEN returns S_OK.</span></span> <span data-ttu-id="1967e-137">Questo non implica che l'operazione sia stata completata o annullata.</span><span class="sxs-lookup"><span data-stu-id="1967e-137">This does not imply that the operation completed or was canceled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1967e-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1967e-138">See Also</span></span>  
 [<span data-ttu-id="1967e-139">Esecuzione di operazioni asincrone</span><span class="sxs-lookup"><span data-stu-id="1967e-139">Performing Asynchronous Operations</span></span>](../native-client/features/performing-asynchronous-operations.md)  
  
  
