---
title: ISSAsynchStatus (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- ISSAsynchStatus interface
ms.assetid: c643f09f-9ccc-4d8b-9243-3cde86c2bd46
author: rothja
ms.author: jroth
ms.openlocfilehash: 4489f9d1ad576d49d885842f6969f9b61065791c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626746"
---
# <a name="issasynchstatus-ole-db"></a><span data-ttu-id="06d79-102">ISSAsynchStatus (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="06d79-102">ISSAsynchStatus (OLE DB)</span></span>
  <span data-ttu-id="06d79-103">**ISSAsynchStatus** espone il supporto per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="06d79-103">**ISSAsynchStatus** exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asynchronous operations.</span></span> <span data-ttu-id="06d79-104">Si tratta di un'interfaccia facoltativa che eredita dall'interfaccia di base OLE DB **IDBAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="06d79-104">This is an optional interface that inherits from the core OLE DB interface **IDBAsynchStatus**.</span></span> <span data-ttu-id="06d79-105">Oltre ai metodi **Abort** e **GetStatus** ereditati da **IDBAsynchStatus**, **ISSAsynchStatus** fornisce un nuovo metodo, utilizzato per attendere il completamento dell'operazione asincrona o il verificarsi di un timeout.</span><span class="sxs-lookup"><span data-stu-id="06d79-105">In addition to the **Abort** and **GetStatus** methods inherited from **IDBAsynchStatus**, **ISSAsynchStatus** provides one new method that is used to wait until an asynchronous operation has completed or a time-out occurs.</span></span>  
  
|<span data-ttu-id="06d79-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="06d79-106">Method</span></span>|<span data-ttu-id="06d79-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06d79-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="06d79-108">ISSAsynchStatus::Abort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="06d79-108">ISSAsynchStatus::Abort &#40;OLE DB&#41;</span></span>](issasynchstatus-abort-ole-db.md)|<span data-ttu-id="06d79-109">Annulla un'operazione di esecuzione asincrona.</span><span class="sxs-lookup"><span data-stu-id="06d79-109">Cancels an asynchronously executing operation.</span></span>|  
|[<span data-ttu-id="06d79-110">ISSAsynchStatus::GetStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="06d79-110">ISSAsynchStatus::GetStatus &#40;OLE DB&#41;</span></span>](issasynchstatus-getstatus-ole-db.md)|<span data-ttu-id="06d79-111">Restituisce lo stato di un'operazione in esecuzione in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="06d79-111">Returns the status of an asynchronously executing operation.</span></span>|  
|[<span data-ttu-id="06d79-112">ISSAsynchStatus::WaitForAsynchCompletion &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="06d79-112">ISSAsynchStatus::WaitForAsynchCompletion &#40;OLE DB&#41;</span></span>](issasynchstatus-waitforasynchcompletion-ole-db.md)|<span data-ttu-id="06d79-113">Resta in attesa fino al completamento dell'operazione di esecuzione asincrona o fino al verificarsi di un timeout.</span><span class="sxs-lookup"><span data-stu-id="06d79-113">Waits until the asynchronously executing operation is complete or a time-out occurs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06d79-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="06d79-114">Remarks</span></span>  
 <span data-ttu-id="06d79-115">L'implementazione **ISSAsynchStatus** del metodo **ISSAsynchStatus::GetStatus** coincide con quella del metodo **IDBAsynchStatus::GetStatus**, ad eccezione del fatto che se l'inizializzazione di un'origine dati viene interrotta, viene restituito E_UNEXPECTED anziché DB_E_CANCELED (benché **ISSAsynchStatus::WaitForAsynchCompletion** restituisca DB_E_CANCELED).</span><span class="sxs-lookup"><span data-stu-id="06d79-115">The **ISSAsynchStatus** implementation of the **ISSAsynchStatus::GetStatus** method is the same as the **IDBAsynchStatus::GetStatus** method except that if the initialization of a data source object is aborted, E_UNEXPECTED is returned rather than DB_E_CANCELED (although **ISSAsynchStatus::WaitForAsynchCompletion** returns DB_E_CANCELED).</span></span> <span data-ttu-id="06d79-116">Ciò è dovuto al fatto che l'oggetto origine dati non viene lasciato nello stato consueto in seguito a un'operazione di interruzione, in modo da consentire ulteriori tentativi di operazioni di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="06d79-116">This is because the data source object is not left in the usual state following an abort operation, so that further initialization operations may be attempted.</span></span>  
  
 <span data-ttu-id="06d79-117">I metodi seguenti supportano l'utilizzo dell'esecuzione asincrona in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="06d79-117">The following methods support the use of asynchronous execution in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="06d79-118">**ICommand::Execute**</span><span class="sxs-lookup"><span data-stu-id="06d79-118">**ICommand::Execute**</span></span>  
  
-   <span data-ttu-id="06d79-119">**IOpenRowset::OpenRowset**</span><span class="sxs-lookup"><span data-stu-id="06d79-119">**IOpenRowset::OpenRowset**</span></span>  
  
-   <span data-ttu-id="06d79-120">**IMultipleResults::GetResult**</span><span class="sxs-lookup"><span data-stu-id="06d79-120">**IMultipleResults::GetResult**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d79-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06d79-121">See Also</span></span>  
 <span data-ttu-id="06d79-122">[Interfacce &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="06d79-122">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 [<span data-ttu-id="06d79-123">Esecuzione di operazioni asincrone</span><span class="sxs-lookup"><span data-stu-id="06d79-123">Performing Asynchronous Operations</span></span>](../native-client/features/performing-asynchronous-operations.md)  
  
  
