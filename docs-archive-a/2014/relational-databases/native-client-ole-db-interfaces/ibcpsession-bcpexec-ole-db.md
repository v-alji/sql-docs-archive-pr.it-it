---
title: IBCPSession::BCPExec (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPExec (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPExec method
ms.assetid: 0f4ebb63-cf03-4e53-846e-6c3021cde007
author: rothja
ms.author: jroth
ms.openlocfilehash: 1452888e046b6223c64a6cdf6fe09b074b815702
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713120"
---
# <a name="ibcpsessionbcpexec-ole-db"></a><span data-ttu-id="be435-102">IBCPSession::BCPExec (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="be435-102">IBCPSession::BCPExec (OLE DB)</span></span>
  <span data-ttu-id="be435-103">Esegue l'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="be435-103">Performs the bulk copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be435-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be435-104">Syntax</span></span>  
  
```  
  
HRESULT BCPExec(   
DBROWCOUNT *pRowsCopied);  
```  
  
## <a name="remarks"></a><span data-ttu-id="be435-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="be435-105">Remarks</span></span>  
 <span data-ttu-id="be435-106">Il metodo **BCPExec** copia i dati da un file utente a una tabella di database o viceversa, a seconda del valore del parametro *eDirection* usato con il metodo [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="be435-106">The **BCPExec** method copies data from a user file to a database table or vice versa, depending on the value of the *eDirection* parameter used with the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="be435-107">Prima di chiamare **BCPExec**, chiamare il metodo **BCPInit** con un nome di file utente valido.</span><span class="sxs-lookup"><span data-stu-id="be435-107">Before calling **BCPExec**, call the **BCPInit** method with a valid user file name.</span></span> <span data-ttu-id="be435-108">In caso contrario, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="be435-108">Failure to do so results in an error.</span></span> <span data-ttu-id="be435-109">L'unica eccezione riguarda le query da utilizzare per operazioni di copia bulk per l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="be435-109">The only exception is if a query is to be used for a bulk copy out operation.</span></span> <span data-ttu-id="be435-110">In un caso di questo tipo, specificare NULL per il nome di tabella nel metodo **BCPInit** e quindi specificare la query usando l'opzione BCP_OPTION_HINTS.</span><span class="sxs-lookup"><span data-stu-id="be435-110">In that case specify NULL for the table name in the **BCPInit** method and then specify the query using the BCP_OPTION_HINTS option.</span></span>  
  
 <span data-ttu-id="be435-111">Il metodo **BCPExec** è l'unico metodo di copia bulk che potrebbe rimanere in attesa per un certo periodo di tempo,</span><span class="sxs-lookup"><span data-stu-id="be435-111">The **BCPExec** method is the only bulk copy method that is likely to be outstanding for any length of time.</span></span> <span data-ttu-id="be435-112">pertanto è l'unico metodo di copia bulk che supporta la modalità asincrona.</span><span class="sxs-lookup"><span data-stu-id="be435-112">It is therefore the only bulk copy method that supports asynchronous mode.</span></span> <span data-ttu-id="be435-113">Per usare la modalità asincrona, impostare la proprietà della sessione specifica del provider SSPROP_ASYNCH_BULKCOPY su VARIANT_TRUE prima di chiamare il metodo **BCPExec** .</span><span class="sxs-lookup"><span data-stu-id="be435-113">To use asynchronous mode, set the provider specific session property SSPROP_ASYNCH_BULKCOPY to VARIANT_TRUE before calling the **BCPExec** method.</span></span> <span data-ttu-id="be435-114">Questa proprietà è disponibile nel set di proprietà DBPROPSET_SQLSERVERSESSION.</span><span class="sxs-lookup"><span data-stu-id="be435-114">This property is available in the DBPROPSET_SQLSERVERSESSION property set.</span></span> <span data-ttu-id="be435-115">Per verificare che l'operazione sia stata completata, chiamare il metodo **BCPExec** con gli stessi parametri.</span><span class="sxs-lookup"><span data-stu-id="be435-115">To test for completion, call the **BCPExec** method with the same parameters.</span></span> <span data-ttu-id="be435-116">Se la copia bulk non è stata ancora completata, il metodo **BCPExec** restituisce DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="be435-116">If the bulk copy has not yet completed, the **BCPExec** method returns DB_S_ASYNCHRONOUS.</span></span> <span data-ttu-id="be435-117">Nell'argomento *pRowsCopied* restituisce anche un conteggio dello stato del numero di righe inviate al server o ricevute dal server.</span><span class="sxs-lookup"><span data-stu-id="be435-117">It also returns in the *pRowsCopied* argument a status count of the number of rows that have been sent to or received from the server.</span></span> <span data-ttu-id="be435-118">Il commit delle righe inviate al server non viene eseguito fino a quando non viene raggiunta la fine di un batch.</span><span class="sxs-lookup"><span data-stu-id="be435-118">Rows sent to the server are not committed until the end of a batch has been reached.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="be435-119">Argomenti</span><span class="sxs-lookup"><span data-stu-id="be435-119">Arguments</span></span>  
 <span data-ttu-id="be435-120">*pRowsCopied*[out]</span><span class="sxs-lookup"><span data-stu-id="be435-120">*pRowsCopied*[out]</span></span>  
 <span data-ttu-id="be435-121">Puntatore a DWORD.</span><span class="sxs-lookup"><span data-stu-id="be435-121">A pointer to a DWORD.</span></span> <span data-ttu-id="be435-122">Il metodo **BCPExec** inserisce in DWORD il numero di righe copiate correttamente.</span><span class="sxs-lookup"><span data-stu-id="be435-122">The **BCPExec** method fills the DWORD with the number of rows successfully copied.</span></span> <span data-ttu-id="be435-123">Se l'argomento *pRowsCopied* è impostato su NULL, viene ignorato dal metodo **BCPExec**.</span><span class="sxs-lookup"><span data-stu-id="be435-123">If the *pRowsCopied* argument is set to NULL, it is ignored by the **BCPExec** method.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="be435-124">Valori del codice restituito</span><span class="sxs-lookup"><span data-stu-id="be435-124">Return Code Values</span></span>  
 <span data-ttu-id="be435-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="be435-125">S_OK</span></span>  
 <span data-ttu-id="be435-126">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="be435-126">The method succeeded.</span></span>  
  
 <span data-ttu-id="be435-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="be435-127">E_FAIL</span></span>  
 <span data-ttu-id="be435-128">Si è verificato un errore specifico del provider. per informazioni dettagliate, usare l'interfaccia [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="be435-128">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="be435-129">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="be435-129">E_UNEXPECTED</span></span>  
 <span data-ttu-id="be435-130">La chiamata al metodo non era prevista.</span><span class="sxs-lookup"><span data-stu-id="be435-130">The call to the method was unexpected.</span></span> <span data-ttu-id="be435-131">Non è stato ad esempio chiamato il metodo **BCPInit** prima della chiamata a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="be435-131">For example, the **BCPInit** method was not called before calling this method.</span></span> <span data-ttu-id="be435-132">Si verifica anche se l'operazione è stata interrotta tramite l'opzione BCP_OPTION_ABORT e successivamente è stato chiamato il metodo **BCPExec**.</span><span class="sxs-lookup"><span data-stu-id="be435-132">Also occurs if the operation has been aborted through using the BCP_OPTION_ABORT option, and the **BCPExec** method was called afterwards.</span></span>  
  
 <span data-ttu-id="be435-133">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="be435-133">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="be435-134">Errore di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="be435-134">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="be435-135">DB_S_ENDOFROWSET</span><span class="sxs-lookup"><span data-stu-id="be435-135">DB_S_ENDOFROWSET</span></span>  
 <span data-ttu-id="be435-136">L'operazione di copia bulk è terminata e il trasferimento dei dati è stato completato.</span><span class="sxs-lookup"><span data-stu-id="be435-136">The bulk copy operation finished, and all the data transfer was completed.</span></span>  
  
 <span data-ttu-id="be435-137">DB_S_ASYNCHRONOUS</span><span class="sxs-lookup"><span data-stu-id="be435-137">DB_S_ASYNCHRONOUS</span></span>  
 <span data-ttu-id="be435-138">Il batch corrente di righe è stato copiato.</span><span class="sxs-lookup"><span data-stu-id="be435-138">The current batch of rows has been copied.</span></span> <span data-ttu-id="be435-139">Chiamare di nuovo il metodo **BCPExec** per trasferire il batch successivo.</span><span class="sxs-lookup"><span data-stu-id="be435-139">Call the **BCPExec** method again to transfer the next batch.</span></span>  
  
 <span data-ttu-id="be435-140">DB_S_ERRORSOCCURRED</span><span class="sxs-lookup"><span data-stu-id="be435-140">DB_S_ERRORSOCCURRED</span></span>  
 <span data-ttu-id="be435-141">Si sono verificati errori durante l'operazione di copia bulk ed è possibile che alcune righe non siano state copiate.</span><span class="sxs-lookup"><span data-stu-id="be435-141">Errors occurred during the bulk copy operation, and some rows might not have been copied.</span></span> <span data-ttu-id="be435-142">Il numero di errori è ancora al di sotto del numero massimo di errori consentiti.</span><span class="sxs-lookup"><span data-stu-id="be435-142">The number of errors is still less than the maximum errors allowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be435-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be435-143">See Also</span></span>  
 <span data-ttu-id="be435-144">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="be435-144">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="be435-145">Esecuzione di operazioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="be435-145">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
