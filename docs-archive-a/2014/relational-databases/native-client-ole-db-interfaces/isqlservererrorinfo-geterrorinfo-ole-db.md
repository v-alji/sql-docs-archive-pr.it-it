---
title: ISQLServerErrorInfo::GetErrorInfo (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISQLServerErrorInfo::GetErrorInfo (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- GetErrorInfo method
ms.assetid: 83265c9c-eaf9-41f0-9f73-b0ae0972f0d5
author: rothja
ms.author: jroth
ms.openlocfilehash: c3e325cd99276e04a178b89c19b233289edc09fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718131"
---
# <a name="isqlservererrorinfogeterrorinfo-ole-db"></a><span data-ttu-id="4dcac-102">ISQLServerErrorInfo::GetErrorInfo (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="4dcac-102">ISQLServerErrorInfo::GetErrorInfo (OLE DB)</span></span>
  <span data-ttu-id="4dcac-103">Restituisce un puntatore a una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] struttura SSERRORINFO del provider OLE DB di Native Client contenente i [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Dettagli dell'errore.</span><span class="sxs-lookup"><span data-stu-id="4dcac-103">Returns a pointer to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider SSERRORINFO structure containing the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error details.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dcac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4dcac-104">Syntax</span></span>  
  
```  
  
   HRESULT GetErrorInfo(  
SSERRORINFO**ppSSErrorInfo,  
OLECHAR**ppErrorStrings);  
```  
  
## <a name="arguments"></a><span data-ttu-id="4dcac-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4dcac-105">Arguments</span></span>  
 <span data-ttu-id="4dcac-106">*ppSSErrorInfo*[out]</span><span class="sxs-lookup"><span data-stu-id="4dcac-106">*ppSSErrorInfo*[out]</span></span>  
 <span data-ttu-id="4dcac-107">Puntatore a una struttura SSERRORINFO.</span><span class="sxs-lookup"><span data-stu-id="4dcac-107">A pointer to a SSERRORINFO structure.</span></span> <span data-ttu-id="4dcac-108">Se il metodo non riesce o non sono disponibili informazioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associate all'errore, il provider non alloca memoria e verifica che l'argomento *ppSSErrorInfo* sia un puntatore Null nell'output.</span><span class="sxs-lookup"><span data-stu-id="4dcac-108">If the method fails or there is no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information associated with the error, the provider does not allocate any memory, and ensures that the *ppSSErrorInfo* argument is a null pointer on output.</span></span>  
  
 <span data-ttu-id="4dcac-109">*ppErrorStrings*[out]</span><span class="sxs-lookup"><span data-stu-id="4dcac-109">*ppErrorStrings*[out]</span></span>  
 <span data-ttu-id="4dcac-110">Puntatore a un puntatore stringa carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="4dcac-110">A pointer to a Unicode character-string pointer.</span></span> <span data-ttu-id="4dcac-111">Se il metodo non riesce o non sono disponibili informazioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associate a un errore, il provider non alloca memoria e verifica che l'argomento *ppErrorStrings* sia un puntatore Null nell'output.</span><span class="sxs-lookup"><span data-stu-id="4dcac-111">If the method fails or there is no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information associated with an error, the provider does not allocate any memory, and ensures that the *ppErrorStrings* argument is a null pointer on output.</span></span> <span data-ttu-id="4dcac-112">Liberando l'argomento *ppErrorStrings* con il metodo **IMalloc::Free**, vengono liberati i tre singoli membri della stringa della struttura SSERRORINFO restituita, in quanto la memoria è allocata in un blocco.</span><span class="sxs-lookup"><span data-stu-id="4dcac-112">Freeing the *ppErrorStrings* argument with the **IMalloc::Free** method frees the three individual string members of the returned SSERRORINFO structure, as the memory is allocated in a block.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="4dcac-113">Valori del codice restituito</span><span class="sxs-lookup"><span data-stu-id="4dcac-113">Return Code Values</span></span>  
 <span data-ttu-id="4dcac-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="4dcac-114">S_OK</span></span>  
 <span data-ttu-id="4dcac-115">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="4dcac-115">The method succeeded.</span></span>  
  
 <span data-ttu-id="4dcac-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4dcac-116">E_INVALIDARG</span></span>  
 <span data-ttu-id="4dcac-117">L'argomento *ppSSErrorInfo* o *ppErrorStrings* era NULL.</span><span class="sxs-lookup"><span data-stu-id="4dcac-117">Either the *ppSSErrorInfo* or the *ppErrorStrings* argument was NULL.</span></span>  
  
 <span data-ttu-id="4dcac-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4dcac-118">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="4dcac-119">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non è in grado di allocare memoria sufficiente per completare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="4dcac-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider could not allocate sufficient memory to complete the request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4dcac-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4dcac-120">Remarks</span></span>  
 <span data-ttu-id="4dcac-121">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client alloca memoria per le stringhe SSERRORINFO e OLECHAR restituite tramite i puntatori passati dal consumer.</span><span class="sxs-lookup"><span data-stu-id="4dcac-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider allocates memory for the SSERRORINFO and OLECHAR strings returned through the pointers passed by the consumer.</span></span> <span data-ttu-id="4dcac-122">Il consumer deve deallocare questa memoria tramite il metodo **IMalloc::Free** quando l'accesso ai dati dell'errore non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="4dcac-122">The consumer must deallocate this memory by using the **IMalloc::Free** method when it no longer requires access to the error data.</span></span>  
  
 <span data-ttu-id="4dcac-123">La struttura SSERRORINFO viene definita nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="4dcac-123">The SSERRORINFO structure is defined as follows:</span></span>  
  
```  
typedef struct tagSSErrorInfo  
   {  
   LPOLESTR pwszMessage;  
   LPOLESTR pwszServer;  
   LPOLESTR pwszProcedure;  
   LONG lNative;  
   BYTE bState;  
   BYTE bClass;  
   WORD wLineNumber;  
   }  
SSERRORINFO;  
```  
  
|<span data-ttu-id="4dcac-124">Membro</span><span class="sxs-lookup"><span data-stu-id="4dcac-124">Member</span></span>|<span data-ttu-id="4dcac-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4dcac-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4dcac-126">*pwszMessage*</span><span class="sxs-lookup"><span data-stu-id="4dcac-126">*pwszMessage*</span></span>|<span data-ttu-id="4dcac-127">Messaggio di errore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dcac-127">The error message from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4dcac-128">Il messaggio viene restituito attraverso il metodo **IErrorInfo::GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="4dcac-128">The message is returned through the **IErrorInfo::GetDescription** method.</span></span>|  
|<span data-ttu-id="4dcac-129">*pwszServer*</span><span class="sxs-lookup"><span data-stu-id="4dcac-129">*pwszServer*</span></span>|<span data-ttu-id="4dcac-130">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="4dcac-130">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which the error occurred.</span></span>|  
|<span data-ttu-id="4dcac-131">*pwszProcedure*</span><span class="sxs-lookup"><span data-stu-id="4dcac-131">*pwszProcedure*</span></span>|<span data-ttu-id="4dcac-132">Nome della stored procedure che genera l'errore se esso si è verificato all'interno della stessa, in caso contrario, una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="4dcac-132">The name of the stored procedure generating the error if the error occurred in a stored procedure; otherwise, an empty string.</span></span>|  
|<span data-ttu-id="4dcac-133">*lNative*</span><span class="sxs-lookup"><span data-stu-id="4dcac-133">*lNative*</span></span>|<span data-ttu-id="4dcac-134">Numero di errore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dcac-134">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number.</span></span> <span data-ttu-id="4dcac-135">Il numero di errore è identico a quello restituito nel parametro *plNativeError* del metodo **ISQLErrorInfo::GetSQLInfo**.</span><span class="sxs-lookup"><span data-stu-id="4dcac-135">The error number is identical to that returned in the *plNativeError* parameter of the **ISQLErrorInfo::GetSQLInfo** method.</span></span>|  
|<span data-ttu-id="4dcac-136">*bState*</span><span class="sxs-lookup"><span data-stu-id="4dcac-136">*bState*</span></span>|<span data-ttu-id="4dcac-137">Stato dell'errore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dcac-137">The state of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error.</span></span>|  
|<span data-ttu-id="4dcac-138">*bClass*</span><span class="sxs-lookup"><span data-stu-id="4dcac-138">*bClass*</span></span>|<span data-ttu-id="4dcac-139">Gravità dell'errore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dcac-139">The severity of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error.</span></span>|  
|<span data-ttu-id="4dcac-140">*wLineNumber*</span><span class="sxs-lookup"><span data-stu-id="4dcac-140">*wLineNumber*</span></span>|<span data-ttu-id="4dcac-141">Quando applicabile, riga di una stored procedure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che ha generato il messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="4dcac-141">When applicable, the line of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure that generated the error message.</span></span> <span data-ttu-id="4dcac-142">Se non è coinvolta alcuna procedura, il valore predefinito è 1.</span><span class="sxs-lookup"><span data-stu-id="4dcac-142">If no procedure is involved, the default value is 1.</span></span>|  
  
 <span data-ttu-id="4dcac-143">I puntatori nella struttura fanno riferimento agli indirizzi nella stringa restituita nell'argomento *ppErrorStrings*.</span><span class="sxs-lookup"><span data-stu-id="4dcac-143">Pointers in the structure reference addresses in the string returned in the *ppErrorStrings* argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dcac-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dcac-144">See Also</span></span>  
 <span data-ttu-id="4dcac-145">[ISQLServerErrorInfo &#40;OLE DB&#41;](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="4dcac-145">[ISQLServerErrorInfo &#40;OLE DB&#41;](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) </span></span>  
 [<span data-ttu-id="4dcac-146">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4dcac-146">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
