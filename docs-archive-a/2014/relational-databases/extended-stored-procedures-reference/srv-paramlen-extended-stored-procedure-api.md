---
title: srv_paramlen (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramlen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramlen
ms.assetid: d1fe92ff-cad6-4396-8216-125e5642e81e
author: rothja
ms.author: jroth
ms.openlocfilehash: fc2a0fa7f8409767a2afaa9c4c621ea72732b701
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725811"
---
# <a name="srv_paramlen-extended-stored-procedure-api"></a><span data-ttu-id="00ece-102">srv_paramlen (API delle stored procedure estese)</span><span class="sxs-lookup"><span data-stu-id="00ece-102">srv_paramlen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="00ece-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="00ece-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="00ece-104">Restituisce la lunghezza dei dati di un parametro di chiamata a una stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="00ece-104">Returns the data length of a remote stored procedure call parameter.</span></span> <span data-ttu-id="00ece-105">Questa funzione è stata sostituita dalla funzione **srv_paraminfo**.</span><span class="sxs-lookup"><span data-stu-id="00ece-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00ece-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00ece-106">Syntax</span></span>  
  
```  
  
int srv_paramlen (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="00ece-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="00ece-107">Arguments</span></span>  
 <span data-ttu-id="00ece-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="00ece-108">*srvproc*</span></span>  
 <span data-ttu-id="00ece-109">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client. In questo caso, l'handle che ha ricevuto la chiamata alla stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="00ece-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="00ece-110">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="00ece-110">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="00ece-111">*n*</span><span class="sxs-lookup"><span data-stu-id="00ece-111">*n*</span></span>  
 <span data-ttu-id="00ece-112">Indica il numero del parametro.</span><span class="sxs-lookup"><span data-stu-id="00ece-112">Indicates the number of the parameter.</span></span> <span data-ttu-id="00ece-113">Il primo parametro è 1.</span><span class="sxs-lookup"><span data-stu-id="00ece-113">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="00ece-114">Restituisce</span><span class="sxs-lookup"><span data-stu-id="00ece-114">Returns</span></span>  
 <span data-ttu-id="00ece-115">Lunghezza effettiva in byte dei dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="00ece-115">The actual length, in bytes, of the parameter data.</span></span> <span data-ttu-id="00ece-116">Se non è presente nessun parametro *n* o nessuna stored procedure remota, restituisce -1.</span><span class="sxs-lookup"><span data-stu-id="00ece-116">If there is no *n*th parameter or there is no remote stored procedure, it returns -1.</span></span> <span data-ttu-id="00ece-117">Se il parametro *n* è NULL, restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="00ece-117">If the *n*th parameter is NULL, it returns 0.</span></span>  
  
 <span data-ttu-id="00ece-118">Questa funzione restituisce i valori seguenti, se il parametro è uno dei tipi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] dati di sistema seguenti.</span><span class="sxs-lookup"><span data-stu-id="00ece-118">This function returns the following values, if the parameter is one of the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] system data types.</span></span>  
  
|<span data-ttu-id="00ece-119">Nuovi tipi di dati</span><span class="sxs-lookup"><span data-stu-id="00ece-119">New data types</span></span>|<span data-ttu-id="00ece-120">Lunghezza dei dati di input</span><span class="sxs-lookup"><span data-stu-id="00ece-120">Input data length</span></span>|  
|--------------------|-----------------------|  
|`BITN`|<span data-ttu-id="00ece-121">**NULL:** 1</span><span class="sxs-lookup"><span data-stu-id="00ece-121">**NULL:** 1</span></span><br /><br /> <span data-ttu-id="00ece-122">**Zero:** 1</span><span class="sxs-lookup"><span data-stu-id="00ece-122">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="00ece-123">**>=255:** N/D</span><span class="sxs-lookup"><span data-stu-id="00ece-123">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="00ece-124">**<255:** N/A</span><span class="sxs-lookup"><span data-stu-id="00ece-124">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="00ece-125">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="00ece-125">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="00ece-126">**Zero:** 1</span><span class="sxs-lookup"><span data-stu-id="00ece-126">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="00ece-127">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="00ece-127">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="00ece-128">**<255:** valore *len* effettivo</span><span class="sxs-lookup"><span data-stu-id="00ece-128">**<255:** actual *len*</span></span>|  
|`BIGCHAR`|<span data-ttu-id="00ece-129">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="00ece-129">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="00ece-130">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="00ece-130">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="00ece-131">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="00ece-131">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="00ece-132">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="00ece-132">**<255:** 255</span></span>|  
|`BIGBINARY`|<span data-ttu-id="00ece-133">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="00ece-133">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="00ece-134">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="00ece-134">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="00ece-135">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="00ece-135">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="00ece-136">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="00ece-136">**<255:** 255</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="00ece-137">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="00ece-137">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="00ece-138">**Zero:** 1</span><span class="sxs-lookup"><span data-stu-id="00ece-138">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="00ece-139">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="00ece-139">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="00ece-140">**<255:** valore *len* effettivo</span><span class="sxs-lookup"><span data-stu-id="00ece-140">**<255:** actual *len*</span></span>|  
|`NCHAR`|<span data-ttu-id="00ece-141">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="00ece-141">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="00ece-142">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="00ece-142">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="00ece-143">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="00ece-143">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="00ece-144">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="00ece-144">**<255:** 255</span></span>|  
|`NVARCHAR`|<span data-ttu-id="00ece-145">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="00ece-145">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="00ece-146">**Zero:** 1</span><span class="sxs-lookup"><span data-stu-id="00ece-146">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="00ece-147">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="00ece-147">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="00ece-148">**<255:** valore *len* effettivo</span><span class="sxs-lookup"><span data-stu-id="00ece-148">**<255:** actual *len*</span></span>|  
|`NTEXT`|<span data-ttu-id="00ece-149">**Null:** -1</span><span class="sxs-lookup"><span data-stu-id="00ece-149">**NULL:** -1</span></span><br /><br /> <span data-ttu-id="00ece-150">**ZERO:** -1</span><span class="sxs-lookup"><span data-stu-id="00ece-150">**ZERO:** -1</span></span><br /><br /> <span data-ttu-id="00ece-151">**>=255:** -1</span><span class="sxs-lookup"><span data-stu-id="00ece-151">**>=255:** -1</span></span><br /><br /> <span data-ttu-id="00ece-152">**<255:** -1</span><span class="sxs-lookup"><span data-stu-id="00ece-152">**<255:** -1</span></span>|  
  
 <span data-ttu-id="00ece-153">\*   Valore *len* effettivo = Lunghezza della stringa di carattere multibyte (cch)</span><span class="sxs-lookup"><span data-stu-id="00ece-153">\*   actual *len* = Length of multibyte character string (cch)</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00ece-154">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="00ece-154">Remarks</span></span>  
 <span data-ttu-id="00ece-155">Ogni parametro di stored procedure remota ha una lunghezza massima e una lunghezza effettiva dei dati.</span><span class="sxs-lookup"><span data-stu-id="00ece-155">Each remote stored procedure parameter has an actual and a maximum data length.</span></span> <span data-ttu-id="00ece-156">Per i tipi di dati a lunghezza fissa standard che non consentono valori Null, le due lunghezze coincidono.</span><span class="sxs-lookup"><span data-stu-id="00ece-156">For standard fixed-length data types that do not allow null values, the actual and maximum lengths are the same.</span></span> <span data-ttu-id="00ece-157">Per i tipi di dati a lunghezza variabile, le lunghezze possono essere diverse.</span><span class="sxs-lookup"><span data-stu-id="00ece-157">For variable-length data types, the lengths can vary.</span></span> <span data-ttu-id="00ece-158">Un parametro dichiarato come `varchar(30)`, ad esempio, può includere dati con lunghezza pari solo a 10 byte.</span><span class="sxs-lookup"><span data-stu-id="00ece-158">For example, a parameter declared as `varchar(30)` can have data that is only 10 bytes long.</span></span> <span data-ttu-id="00ece-159">La lunghezza effettiva del parametro è 10, mentre la lunghezza massima è 30.</span><span class="sxs-lookup"><span data-stu-id="00ece-159">The parameter's actual length is 10 and its maximum length is 30.</span></span> <span data-ttu-id="00ece-160">La funzione **srv_paramlen** ottiene la lunghezza effettiva dei dati in byte di una stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="00ece-160">The **srv_paramlen** function gets the actual data length, in bytes, of a remote stored procedure.</span></span> <span data-ttu-id="00ece-161">Per ottenere la lunghezza massima dei dati di un parametro, usare **srv_parammaxlen**.</span><span class="sxs-lookup"><span data-stu-id="00ece-161">To obtain the maximum data length of a parameter, use **srv_parammaxlen**.</span></span>  
  
 <span data-ttu-id="00ece-162">Quando viene effettuata una chiamata a una stored procedure remota con parametri, tali parametri possono essere passati per nome o per posizione (senza nome).</span><span class="sxs-lookup"><span data-stu-id="00ece-162">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="00ece-163">Se invece viene effettuata con alcuni parametri passati per nome e altri passati per posizione, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="00ece-163">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="00ece-164">Il gestore SRV_RPC viene ancora chiamato, ma sembra che non siano presenti parametri e **srv_rpcparams** restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="00ece-164">The SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="00ece-165">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="00ece-165">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="00ece-166">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="00ece-166">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ece-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00ece-167">See Also</span></span>  
 <span data-ttu-id="00ece-168">[srv_paraminfo &#40;API stored procedure estesa&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="00ece-168">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="00ece-169">srv_rpcparams &#40;API delle stored procedure estese&#41;</span><span class="sxs-lookup"><span data-stu-id="00ece-169">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
