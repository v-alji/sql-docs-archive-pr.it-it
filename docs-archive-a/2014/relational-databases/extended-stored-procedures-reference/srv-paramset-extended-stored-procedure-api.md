---
title: srv_paramset (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramset
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramset
ms.assetid: 2a509206-a1b8-4b20-b0a2-ef680cef7bd8
author: rothja
ms.author: jroth
ms.openlocfilehash: 9ebe308e5e0c8fc24382582fb71db2f48c77541e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624723"
---
# <a name="srv_paramset-extended-stored-procedure-api"></a><span data-ttu-id="48f95-102">srv_paramset (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="48f95-102">srv_paramset (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="48f95-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="48f95-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="48f95-104">Imposta il valore di un parametro restituito di chiamata a una stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="48f95-104">Sets the value of a remote stored procedure call return parameter.</span></span> <span data-ttu-id="48f95-105">Questa funzione è stata sostituita dalla funzione **srv_paramsetoutput**.</span><span class="sxs-lookup"><span data-stu-id="48f95-105">This function has been superseded by the **srv_paramsetoutput** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48f95-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48f95-106">Syntax</span></span>  
  
```  
  
int srv_paramset (  
SRV_PROC *  
srvproc  
,  
int  
n  
,   
void *  
data  
,  
int  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="48f95-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="48f95-107">Arguments</span></span>  
 <span data-ttu-id="48f95-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="48f95-108">*srvproc*</span></span>  
 <span data-ttu-id="48f95-109">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client. In questo caso, l'handle che ha ricevuto la chiamata alla stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="48f95-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="48f95-110">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="48f95-110">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="48f95-111">*n*</span><span class="sxs-lookup"><span data-stu-id="48f95-111">*n*</span></span>  
 <span data-ttu-id="48f95-112">Indica il numero del parametro da impostare.</span><span class="sxs-lookup"><span data-stu-id="48f95-112">Indicates the number of the parameter to set.</span></span> <span data-ttu-id="48f95-113">Il primo parametro è 1.</span><span class="sxs-lookup"><span data-stu-id="48f95-113">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="48f95-114">*data*</span><span class="sxs-lookup"><span data-stu-id="48f95-114">*data*</span></span>  
 <span data-ttu-id="48f95-115">Puntatore al valore dei dati da inviare di nuovo al client come parametro restituito della stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="48f95-115">Is a pointer to the data value to be sent back to the client as the remote stored procedure return parameter.</span></span>  
  
 <span data-ttu-id="48f95-116">*Len*</span><span class="sxs-lookup"><span data-stu-id="48f95-116">*len*</span></span>  
 <span data-ttu-id="48f95-117">Specifica la lunghezza effettiva dei dati da restituire.</span><span class="sxs-lookup"><span data-stu-id="48f95-117">Specifies the actual length of the data to be returned.</span></span> <span data-ttu-id="48f95-118">Se il tipo di dati del parametro ha una lunghezza costante e non consente valori Null (ad esempio, *srvbit* o *srvint1*), *len* viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="48f95-118">If the data type of the parameter is of a constant length and does not allow null values (for example, *srvbit* or *srvint1*), *len* is ignored.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="48f95-119">Restituisce</span><span class="sxs-lookup"><span data-stu-id="48f95-119">Returns</span></span>  
 <span data-ttu-id="48f95-120">SUCCEED se il valore del parametro è stato impostato correttamente; in caso contrario, FAIL.</span><span class="sxs-lookup"><span data-stu-id="48f95-120">SUCCEED if the parameter value was successfully set; otherwise, FAIL.</span></span> <span data-ttu-id="48f95-121">Restituisce FAIL se non esiste una stored procedure remota corrente, se non è presente il parametro *n* della stored procedure remota, se il parametro non è un parametro restituito o se l'argomento *len* non è valido.</span><span class="sxs-lookup"><span data-stu-id="48f95-121">FAIL is returned when there is no current remote stored procedure, when there is no *n*th remote stored procedure parameter, when the parameter is not a return parameter, and when the *len* argument is not legal.</span></span>  
  
 <span data-ttu-id="48f95-122">Se *len* è 0, restituisce NULL.</span><span class="sxs-lookup"><span data-stu-id="48f95-122">If *len*is 0, it returns NULL.</span></span> <span data-ttu-id="48f95-123">L'impostazione di *len* su 0 è l'unico modo per restituire NULL al client.</span><span class="sxs-lookup"><span data-stu-id="48f95-123">Setting *len* to 0 is the only way to return NULL to the client.</span></span>  
  
 <span data-ttu-id="48f95-124">Questa funzione restituisce i valori seguenti, se il parametro è uno dei [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="48f95-124">This function returns the following values, if the parameter is one of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] data types.</span></span>  
  
|<span data-ttu-id="48f95-125">Nuovi tipi di dati</span><span class="sxs-lookup"><span data-stu-id="48f95-125">New data types</span></span>|<span data-ttu-id="48f95-126">Lunghezza dei dati restituiti</span><span class="sxs-lookup"><span data-stu-id="48f95-126">Return data length</span></span>|  
|--------------------|------------------------|  
|`BITN`|<span data-ttu-id="48f95-127">**NULL:** *len* = 0, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-127">**NULL:** *len* = 0, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-128">**ZERO:** N/D</span><span class="sxs-lookup"><span data-stu-id="48f95-128">**ZERO:** N/A</span></span><br /><br /> <span data-ttu-id="48f95-129">**>=255:** N/D</span><span class="sxs-lookup"><span data-stu-id="48f95-129">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="48f95-130">**<255:** N/A</span><span class="sxs-lookup"><span data-stu-id="48f95-130">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="48f95-131">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="48f95-131">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="48f95-132">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-132">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-133">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-133">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-134">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="48f95-134">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGCHAR`|<span data-ttu-id="48f95-135">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="48f95-135">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="48f95-136">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-136">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-137">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-137">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-138">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="48f95-138">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGBINARY`|<span data-ttu-id="48f95-139">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="48f95-139">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="48f95-140">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-140">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-141">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-141">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-142">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="48f95-142">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="48f95-143">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="48f95-143">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="48f95-144">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-144">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-145">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-145">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-146">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="48f95-146">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|<span data-ttu-id="48f95-147">NCHAR</span><span class="sxs-lookup"><span data-stu-id="48f95-147">NCHAR</span></span>|<span data-ttu-id="48f95-148">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="48f95-148">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="48f95-149">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-149">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-150">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-150">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-151">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="48f95-151">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|<span data-ttu-id="48f95-152">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="48f95-152">NVARCHAR</span></span>|<span data-ttu-id="48f95-153">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="48f95-153">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="48f95-154">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-154">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-155">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-155">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-156">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="48f95-156">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`NTEXT`|<span data-ttu-id="48f95-157">**NULL:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-157">**NULL:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-158">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-158">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-159">**>=255:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-159">**>=255:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="48f95-160">\*\* \< 255:\*\* *Len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="48f95-160">**\<255:** *len* = IG, data = IG, RET = 0</span></span>|  
|<span data-ttu-id="48f95-161">RET = valore restituito di srv_paramset</span><span class="sxs-lookup"><span data-stu-id="48f95-161">RET = Return value of srv_paramset</span></span>||  
|<span data-ttu-id="48f95-162">IG = il valore verrà ignorato</span><span class="sxs-lookup"><span data-stu-id="48f95-162">IG = Value will be ignored</span></span>||  
|<span data-ttu-id="48f95-163">valid = qualsiasi puntatore valido ai dati</span><span class="sxs-lookup"><span data-stu-id="48f95-163">valid = Any valid pointer to data</span></span>||  
  
## <a name="remarks"></a><span data-ttu-id="48f95-164">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="48f95-164">Remarks</span></span>  
 <span data-ttu-id="48f95-165">I parametri contengono i dati passati tra i client e l'applicazione con stored procedure remote.</span><span class="sxs-lookup"><span data-stu-id="48f95-165">Parameters contain data passed between clients and the application with remote stored procedures.</span></span> <span data-ttu-id="48f95-166">Il client può specificare determinati parametri come parametri restituiti.</span><span class="sxs-lookup"><span data-stu-id="48f95-166">The client can specify certain parameters as return parameters.</span></span> <span data-ttu-id="48f95-167">Questi parametri restituiti possono contenere valori che l'applicazione del server Open Data Services passa nuovamente al client.</span><span class="sxs-lookup"><span data-stu-id="48f95-167">These return parameters can contain values that the Open Data Services server application passes back to the client.</span></span> <span data-ttu-id="48f95-168">L'utilizzo di parametri restituiti è analogo al passaggio di parametri per riferimento.</span><span class="sxs-lookup"><span data-stu-id="48f95-168">Using return parameters is analogous to passing parameters by reference.</span></span>  
  
 <span data-ttu-id="48f95-169">Non è possibile impostare il valore restituito per un parametro non richiamato come parametro restituito.</span><span class="sxs-lookup"><span data-stu-id="48f95-169">You cannot set the return value for a parameter that wasn't invoked as a return parameter.</span></span> <span data-ttu-id="48f95-170">È possibile usare **srv_paramstatus** per determinare la modalità di richiamo del parametro.</span><span class="sxs-lookup"><span data-stu-id="48f95-170">You can use **srv_paramstatus** to determine how the parameter was invoked.</span></span>  
  
 <span data-ttu-id="48f95-171">Questa funzione imposta il valore restituito per un parametro ma non lo invia effettivamente al client.</span><span class="sxs-lookup"><span data-stu-id="48f95-171">This function sets the return value for a parameter but it does not actually send the return value to the client.</span></span> <span data-ttu-id="48f95-172">Tutti i parametri restituiti, indipendentemente dal fatto che i relativi valori restituiti siano stati impostati con **srv_paramset**, vengono inviati automaticamente al client quando **srv_senddone** viene chiamato con il flag di stato SRV_DONE_FINAL impostato.</span><span class="sxs-lookup"><span data-stu-id="48f95-172">All return parameters, whether their return values have been set with **srv_paramset** or not, are automatically sent to the client when **srv_senddone** is called with the status flag SRV_DONE_FINAL set.</span></span>  
  
 <span data-ttu-id="48f95-173">Quando viene effettuata una chiamata a una stored procedure remota con parametri, tali parametri possono essere passati per nome o per posizione (senza nome).</span><span class="sxs-lookup"><span data-stu-id="48f95-173">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="48f95-174">Se invece viene effettuata con alcuni parametri passati per nome e altri passati per posizione, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="48f95-174">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="48f95-175">Il gestore SRV_RPC viene comunque chiamato, ma risulta che non sono presenti parametri e **srv_rpcparams** restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="48f95-175">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="48f95-176">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="48f95-176">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="48f95-177">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="48f95-177">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f95-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48f95-178">See Also</span></span>  
 [<span data-ttu-id="48f95-179">srv_paramsetoutput &#40;API Stored procedure estesa&#41;</span><span class="sxs-lookup"><span data-stu-id="48f95-179">srv_paramsetoutput &#40;Extended Stored Procedure API&#41;</span></span>](srv-paramsetoutput-extended-stored-procedure-api.md)  
  
  
