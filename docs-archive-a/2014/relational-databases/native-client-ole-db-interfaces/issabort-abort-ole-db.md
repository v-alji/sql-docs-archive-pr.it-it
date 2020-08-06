---
title: ISSAbort::Abort (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAbort::Abort (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Abort method
ms.assetid: a5bca169-694b-4895-84ac-e8fba491e479
author: rothja
ms.author: jroth
ms.openlocfilehash: 3daad53087c876af8dc46bccc9c4bf7952976067
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718119"
---
# <a name="issabortabort-ole-db"></a><span data-ttu-id="7634a-102">ISSAbort::Abort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="7634a-102">ISSAbort::Abort (OLE DB)</span></span>
  <span data-ttu-id="7634a-103">Annulla il set di righe corrente oltre a qualsiasi comando eseguito in batch associato al comando corrente.</span><span class="sxs-lookup"><span data-stu-id="7634a-103">Cancels the current rowset plus any batched commands associated with the current command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7634a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7634a-104">Syntax</span></span>  
  
```  
  
HRESULT Abort(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="7634a-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7634a-105">Remarks</span></span>  
 <span data-ttu-id="7634a-106">Se il comando interrotto è in una stored procedure, l'esecuzione della stored procedure (e di qualsiasi procedura che ha chiamato la procedura) verrà terminata insieme al batch di comandi che contiene la chiamata alla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="7634a-106">If the command being aborted is in a stored procedure, execution of the stored procedure (and any procedures which had called that procedure) will be terminated as well as the command batch which contains the stored procedure call.</span></span> <span data-ttu-id="7634a-107">Se nel server è in corso il trasferimento di un set di risultati al client, questo processo verrà arrestato.</span><span class="sxs-lookup"><span data-stu-id="7634a-107">If the server is in the process of transferring a result set to the client, this will be stopped.</span></span> <span data-ttu-id="7634a-108">Se il client non desidera utilizzare un set di risultati, la chiamata a **ISSAbort::Abort** prima di rilasciare il set di righe accelererà il rilascio del set di righe, ma se è presente una transazione aperta e XACT_ABORT è ON, verrà eseguito il rollback della transazione quando viene chiamato **ISSAbort::Abort**</span><span class="sxs-lookup"><span data-stu-id="7634a-108">If the client does not want to consume a result set, calling **ISSAbort::Abort** before releasing the rowset will speed up the rowset release, but if there is an open transaction and XACT_ABORT is ON, the transaction will be rolled back when **ISSAbort::Abort** is called</span></span>  
  
 <span data-ttu-id="7634a-109">Dopo che il metodo IsDefined **:: Abort** restituisce S_OK, l'interfaccia **IMultipleResults** associata entra in uno stato inutilizzabile e restituisce DB_E_CANCELED a tutte le chiamate ai metodi, ad eccezione dei metodi definiti dall'interfaccia **IUnknown** , fino a quando non viene rilasciata.</span><span class="sxs-lookup"><span data-stu-id="7634a-109">After **ISSAbort::Abort** returns S_OK, the associated **IMultipleResults** interface enters a unusable state and returns DB_E_CANCELED to all method calls (except for methods defined by the **IUnknown** interface) until it is released.</span></span> <span data-ttu-id="7634a-110">Se si ottiene un'interfaccia **IRowset** da **IMultipleResults** prima di una chiamata a **Abort**, anche questa interfaccia passa in uno stato inutilizzabile e restituisce DB_E_CANCELED a tutte le chiamate ai metodi, ad eccezione dei metodi definiti dall'interfaccia **IUnknown** e da **IRowset::ReleaseRows**, fino a quando non viene rilasciata in seguito a una chiamata riuscita a **ISSAbort::Abort**.</span><span class="sxs-lookup"><span data-stu-id="7634a-110">If an **IRowset** had been obtained from **IMultipleResults** prior to a call to **Abort**, it also enters an unusable state and returns DB_E_CANCELED to all method calls (except for methods defined by the **IUnknown** interface and **IRowset::ReleaseRows**) until it is released after a successful call to **ISSAbort::Abort**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7634a-111">A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], se lo stato XACT_ABORT del server è ON, l'esecuzione di **ISSAbort::Abort** terminerà qualsiasi transazione implicita o esplicita e ne eseguirà il rollback durante la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7634a-111">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], if the server XACT_ABORT state is ON, executing **ISSAbort::Abort** will terminate and roll back any current implicit or explicit transaction when connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7634a-112">Nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] la transazione corrente non viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="7634a-112">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not abort the current transaction.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="7634a-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7634a-113">Arguments</span></span>  
 <span data-ttu-id="7634a-114">No.</span><span class="sxs-lookup"><span data-stu-id="7634a-114">None.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="7634a-115">Valori del codice restituito</span><span class="sxs-lookup"><span data-stu-id="7634a-115">Return Code Values</span></span>  
 <span data-ttu-id="7634a-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="7634a-116">S_OK</span></span>  
 <span data-ttu-id="7634a-117">Il metodo **ISSAbort::Abort** restituisce S_OK se il batch è stato annullato e DB_E_CANTCANCEL in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="7634a-117">The **ISSAbort::Abort** method returns S_OK if the batch was canceled and DB_E_CANTCANCEL otherwise.</span></span> <span data-ttu-id="7634a-118">Se il batch è già stato annullato, viene restituito DB_E_CANCELED.</span><span class="sxs-lookup"><span data-stu-id="7634a-118">If the batch has already been canceled, DB_E_CANCELED is returned.</span></span>  
  
 <span data-ttu-id="7634a-119">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="7634a-119">DB_E_CANCELED</span></span>  
 <span data-ttu-id="7634a-120">Il batch è già stato annullato.</span><span class="sxs-lookup"><span data-stu-id="7634a-120">The batch has already been canceled.</span></span>  
  
 <span data-ttu-id="7634a-121">DB_E_CANTCANCEL</span><span class="sxs-lookup"><span data-stu-id="7634a-121">DB_E_CANTCANCEL</span></span>  
 <span data-ttu-id="7634a-122">Il batch non è stato annullato.</span><span class="sxs-lookup"><span data-stu-id="7634a-122">The batch was not canceled.</span></span>  
  
 <span data-ttu-id="7634a-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7634a-123">E_FAIL</span></span>  
 <span data-ttu-id="7634a-124">Si è verificato un errore specifico del provider. per informazioni dettagliate, usare l'interfaccia [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="7634a-124">A provider specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="7634a-125">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="7634a-125">E_UNEXPECTED</span></span>  
 <span data-ttu-id="7634a-126">La chiamata al metodo non era prevista.</span><span class="sxs-lookup"><span data-stu-id="7634a-126">The call to the method was unexpected.</span></span> <span data-ttu-id="7634a-127">Lo stato dell'oggetto, ad esempio, è in dubbio in quanto **ISSAbort::Abort** è già stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="7634a-127">For example, the object is in a zombie state because **ISSAbort::Abort** has already been called.</span></span>  
  
 <span data-ttu-id="7634a-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7634a-128">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="7634a-129">Errore di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="7634a-129">Out of memory error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7634a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7634a-130">See Also</span></span>  
 [<span data-ttu-id="7634a-131">&#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="7634a-131">ISSAbort &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/issabort-ole-db.md)  
  
  
