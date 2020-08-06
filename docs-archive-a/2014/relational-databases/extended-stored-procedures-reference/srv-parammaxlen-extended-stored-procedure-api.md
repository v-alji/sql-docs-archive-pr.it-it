---
title: srv_parammaxlen (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_parammaxlen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_parammaxlen
ms.assetid: 49bfc29d-f76a-4963-b0e6-b8532dfda850
author: rothja
ms.author: jroth
ms.openlocfilehash: b289743b3de4b115a67a029dcc0261854ee3a40b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725807"
---
# <a name="srv_parammaxlen-extended-stored-procedure-api"></a><span data-ttu-id="7eaa0-102">srv_parammaxlen (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="7eaa0-102">srv_parammaxlen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="7eaa0-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="7eaa0-104">Restituisce la lunghezza massima dei dati di un parametro di chiamata a una stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-104">Returns the maximum data length of a remote stored procedure call parameter.</span></span> <span data-ttu-id="7eaa0-105">Questa funzione è stata sostituita dalla funzione **srv_paraminfo**.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eaa0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7eaa0-106">Syntax</span></span>  
  
```  
  
int srv_parammaxlen (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="7eaa0-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7eaa0-107">Arguments</span></span>  
 <span data-ttu-id="7eaa0-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="7eaa0-108">*srvproc*</span></span>  
 <span data-ttu-id="7eaa0-109">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client. In questo caso, l'handle che ha ricevuto la chiamata alla stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="7eaa0-110">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-110">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="7eaa0-111">*n*</span><span class="sxs-lookup"><span data-stu-id="7eaa0-111">*n*</span></span>  
 <span data-ttu-id="7eaa0-112">Indica il numero del parametro.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-112">Indicates the number of the parameter.</span></span> <span data-ttu-id="7eaa0-113">Il primo parametro è 1.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-113">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="7eaa0-114">Restituisce</span><span class="sxs-lookup"><span data-stu-id="7eaa0-114">Returns</span></span>  
 <span data-ttu-id="7eaa0-115">Lunghezza massima in byte dei dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-115">The maximum length, in bytes, of the parameter data.</span></span> <span data-ttu-id="7eaa0-116">Se non è presente nessun parametro *n* o nessuna stored procedure remota, restituisce -1.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns -1.</span></span>  
  
 <span data-ttu-id="7eaa0-117">Questa funzione restituisce i valori seguenti, se il parametro è uno dei tipi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dati seguenti.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-117">This function returns the following values, if the parameter is one of the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span>  
  
|<span data-ttu-id="7eaa0-118">Nuovi tipi di dati</span><span class="sxs-lookup"><span data-stu-id="7eaa0-118">New data types</span></span>|<span data-ttu-id="7eaa0-119">Lunghezza dei dati di input</span><span class="sxs-lookup"><span data-stu-id="7eaa0-119">Input data length</span></span>|  
|--------------------|-----------------------|  
|`BITN`|<span data-ttu-id="7eaa0-120">**NULL:** 1</span><span class="sxs-lookup"><span data-stu-id="7eaa0-120">**NULL:** 1</span></span><br /><br /> <span data-ttu-id="7eaa0-121">**Zero:** 1</span><span class="sxs-lookup"><span data-stu-id="7eaa0-121">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="7eaa0-122">**>=255:** N/D</span><span class="sxs-lookup"><span data-stu-id="7eaa0-122">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="7eaa0-123">**<255:** N/A</span><span class="sxs-lookup"><span data-stu-id="7eaa0-123">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="7eaa0-124">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-124">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-125">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-125">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-126">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-126">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-127">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-127">**<255:** 255</span></span>|  
|`BIGCHAR`|<span data-ttu-id="7eaa0-128">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-128">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-129">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-129">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-130">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-130">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-131">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-131">**<255:** 255</span></span>|  
|`BIGBINARY`|<span data-ttu-id="7eaa0-132">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-132">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-133">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-133">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-134">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-134">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-135">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-135">**<255:** 255</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="7eaa0-136">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-136">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-137">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-137">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-138">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-138">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-139">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-139">**<255:** 255</span></span>|  
|`NCHAR`|<span data-ttu-id="7eaa0-140">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-140">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-141">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-141">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-142">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-142">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-143">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-143">**<255:** 255</span></span>|  
|`NVARCHAR`|<span data-ttu-id="7eaa0-144">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-144">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-145">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-145">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-146">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-146">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="7eaa0-147">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="7eaa0-147">**<255:** 255</span></span>|  
|`NTEXT`|<span data-ttu-id="7eaa0-148">**Null:** -1</span><span class="sxs-lookup"><span data-stu-id="7eaa0-148">**NULL:** -1</span></span><br /><br /> <span data-ttu-id="7eaa0-149">**ZERO:** -1</span><span class="sxs-lookup"><span data-stu-id="7eaa0-149">**ZERO:** -1</span></span><br /><br /> <span data-ttu-id="7eaa0-150">**>=255:** -1</span><span class="sxs-lookup"><span data-stu-id="7eaa0-150">**>=255:** -1</span></span><br /><br /> <span data-ttu-id="7eaa0-151">\*\* \< 255:\*\* -1</span><span class="sxs-lookup"><span data-stu-id="7eaa0-151">**\<255:** -1</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7eaa0-152">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7eaa0-152">Remarks</span></span>  
 <span data-ttu-id="7eaa0-153">Ogni parametro di stored procedure remota ha una lunghezza massima e una lunghezza effettiva dei dati.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-153">Each remote stored procedure parameter has an actual and a maximum data length.</span></span> <span data-ttu-id="7eaa0-154">Per i tipi di dati a lunghezza fissa standard che non consentono valori Null, le due lunghezze coincidono.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-154">For standard fixed-length data types that do not allow null values, the actual and maximum lengths are the same.</span></span> <span data-ttu-id="7eaa0-155">Per i tipi di dati a lunghezza variabile, le lunghezze possono essere diverse.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-155">For variable-length data types, the lengths can vary.</span></span> <span data-ttu-id="7eaa0-156">Un parametro dichiarato come **varchar(30)** può ad esempio contenere dati con lunghezza pari a 10 byte.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-156">For example, a parameter declared as **varchar(30)** can have data that is only 10 bytes long.</span></span> <span data-ttu-id="7eaa0-157">La lunghezza effettiva del parametro è 10, mentre la lunghezza massima è 30.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-157">The parameter's actual length is 10 and its maximum length is 30.</span></span> <span data-ttu-id="7eaa0-158">La funzione **srv_parammaxlen** ottiene la lunghezza massima dei dati di una stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-158">The **srv_parammaxlen** function gets the maximum data length of a remote stored procedure.</span></span> <span data-ttu-id="7eaa0-159">Per ottenere la lunghezza effettiva di un parametro, usare **srv_paramlen**.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-159">To obtain the actual length of a parameter, use **srv_paramlen**.</span></span>  
  
 <span data-ttu-id="7eaa0-160">Quando viene effettuata una chiamata a una stored procedure remota con parametri, tali parametri possono essere passati per nome o per posizione (senza nome).</span><span class="sxs-lookup"><span data-stu-id="7eaa0-160">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="7eaa0-161">Se invece viene effettuata con alcuni parametri passati per nome e altri passati per posizione, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-161">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="7eaa0-162">Il gestore SRV_RPC viene comunque chiamato, ma risulta che non sono presenti parametri e **srv_rpcparams** restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-162">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7eaa0-163">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-163">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="7eaa0-164">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="7eaa0-164">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eaa0-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7eaa0-165">See Also</span></span>  
 <span data-ttu-id="7eaa0-166">[srv_paraminfo &#40;API stored procedure estesa&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="7eaa0-166">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="7eaa0-167">srv_rpcparams &#40;API delle stored procedure estese&#41;</span><span class="sxs-lookup"><span data-stu-id="7eaa0-167">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
