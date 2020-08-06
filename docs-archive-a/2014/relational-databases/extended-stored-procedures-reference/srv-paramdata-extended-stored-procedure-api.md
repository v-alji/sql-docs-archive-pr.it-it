---
title: srv_paramdata (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramdata
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramdata
ms.assetid: 3104514d-b404-47c9-b6d7-928106384874
author: rothja
ms.author: jroth
ms.openlocfilehash: 092ca5b811a12c3e6b199a6041ce6e4f8e02f4b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635602"
---
# <a name="srv_paramdata-extended-stored-procedure-api"></a><span data-ttu-id="8e46c-102">srv_paramdata (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="8e46c-102">srv_paramdata (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="8e46c-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="8e46c-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="8e46c-104">Restituisce il valore di un parametro di chiamata a una stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="8e46c-104">Returns the value of a remote stored procedure call parameter.</span></span> <span data-ttu-id="8e46c-105">Questa funzione è stata sostituita dalla funzione **srv_paraminfo**.</span><span class="sxs-lookup"><span data-stu-id="8e46c-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e46c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e46c-106">Syntax</span></span>  
  
```  
  
void * srv_paramdata (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="8e46c-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8e46c-107">Arguments</span></span>  
 <span data-ttu-id="8e46c-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="8e46c-108">*srvproc*</span></span>  
 <span data-ttu-id="8e46c-109">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client. In questo caso, l'handle che ha ricevuto la chiamata alla stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="8e46c-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="8e46c-110">La struttura contiene informazioni utilizzate dalla libreria delle stored procedure estese per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="8e46c-110">The structure contains information the Extended Stored Procedure library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="8e46c-111">*n*</span><span class="sxs-lookup"><span data-stu-id="8e46c-111">*n*</span></span>  
 <span data-ttu-id="8e46c-112">Indica il numero del parametro.</span><span class="sxs-lookup"><span data-stu-id="8e46c-112">Is the number of the parameter.</span></span> <span data-ttu-id="8e46c-113">Il primo parametro è 1.</span><span class="sxs-lookup"><span data-stu-id="8e46c-113">The first parameter is number 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="8e46c-114">Restituisce</span><span class="sxs-lookup"><span data-stu-id="8e46c-114">Returns</span></span>  
 <span data-ttu-id="8e46c-115">Puntatore al valore di parametro.</span><span class="sxs-lookup"><span data-stu-id="8e46c-115">A pointer to the parameter value.</span></span> <span data-ttu-id="8e46c-116">Se il parametro *n* è NULL o se non è presente nessun parametro *n* o nessuna stored procedure remota, restituisce NULL.</span><span class="sxs-lookup"><span data-stu-id="8e46c-116">If the *n*th parameter is NULL, there is no *n*th parameter, or there is no remote stored procedure, returns NULL.</span></span> <span data-ttu-id="8e46c-117">Se il valore del parametro è una stringa, potrebbe non essere con terminazione Null.</span><span class="sxs-lookup"><span data-stu-id="8e46c-117">If the parameter value is a string, it might not be null-terminated.</span></span> <span data-ttu-id="8e46c-118">Usare **srv_paramlen** per determinare la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="8e46c-118">Use **srv_paramlen** to determine the length of the string.</span></span>  
  
 <span data-ttu-id="8e46c-119">Questa funzione restituisce i valori seguenti, se il parametro è uno dei [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="8e46c-119">This function returns the following values, if the parameter is one of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="8e46c-120">I dati puntatore indicano anche se il puntatore per il tipo di dati è valido (VP), NULL o non applicabile (N/A) e il contenuto dei dati a cui punta.</span><span class="sxs-lookup"><span data-stu-id="8e46c-120">Pointer data includes whether the pointer for the data type is valid (VP), NULL, or not applicable (N/A), and the contents of the data pointed to.</span></span>  
  
|<span data-ttu-id="8e46c-121">Nuovi tipi di dati</span><span class="sxs-lookup"><span data-stu-id="8e46c-121">New data types</span></span>|<span data-ttu-id="8e46c-122">Lunghezza dei dati di input</span><span class="sxs-lookup"><span data-stu-id="8e46c-122">Input data length</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="8e46c-123">BITN</span><span class="sxs-lookup"><span data-stu-id="8e46c-123">BITN</span></span>|<span data-ttu-id="8e46c-124">**NULL:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="8e46c-124">**NULL:** VP, NULL</span></span><br /><br /> <span data-ttu-id="8e46c-125">**ZERO:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="8e46c-125">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="8e46c-126">**>=255:** N/D</span><span class="sxs-lookup"><span data-stu-id="8e46c-126">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="8e46c-127">**<255:** N/A</span><span class="sxs-lookup"><span data-stu-id="8e46c-127">**<255:** N/A</span></span>|  
|<span data-ttu-id="8e46c-128">BIGVARCHAR</span><span class="sxs-lookup"><span data-stu-id="8e46c-128">BIGVARCHAR</span></span>|<span data-ttu-id="8e46c-129">**NULL:** NULL, N/D</span><span class="sxs-lookup"><span data-stu-id="8e46c-129">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="8e46c-130">**ZERO:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="8e46c-130">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="8e46c-131">**>=255:** VP, 255 caratteri</span><span class="sxs-lookup"><span data-stu-id="8e46c-131">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="8e46c-132">**<255:** VP, dati effettivi</span><span class="sxs-lookup"><span data-stu-id="8e46c-132">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="8e46c-133">BIGCHAR</span><span class="sxs-lookup"><span data-stu-id="8e46c-133">BIGCHAR</span></span>|<span data-ttu-id="8e46c-134">**NULL:** NULL, N/D</span><span class="sxs-lookup"><span data-stu-id="8e46c-134">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="8e46c-135">**ZERO:** VP, 255 spazi</span><span class="sxs-lookup"><span data-stu-id="8e46c-135">**ZERO:** VP, 255 spaces</span></span><br /><br /> <span data-ttu-id="8e46c-136">**>=255:** VP, 255 caratteri</span><span class="sxs-lookup"><span data-stu-id="8e46c-136">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="8e46c-137">**<255:** VP, dati effettivi + riempimento (fino a 255)</span><span class="sxs-lookup"><span data-stu-id="8e46c-137">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="8e46c-138">BIGBINARY</span><span class="sxs-lookup"><span data-stu-id="8e46c-138">BIGBINARY</span></span>|<span data-ttu-id="8e46c-139">**NULL:** NULL, N/D</span><span class="sxs-lookup"><span data-stu-id="8e46c-139">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="8e46c-140">**ZERO:** VP, 255 0x00</span><span class="sxs-lookup"><span data-stu-id="8e46c-140">**ZERO:** VP, 255 0x00</span></span><br /><br /> <span data-ttu-id="8e46c-141">**>=255:** VP, 255 byte</span><span class="sxs-lookup"><span data-stu-id="8e46c-141">**>=255:** VP, 255 bytes</span></span><br /><br /> <span data-ttu-id="8e46c-142">**<255:** VP, dati effettivi + riempimento (fino a 255)</span><span class="sxs-lookup"><span data-stu-id="8e46c-142">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="8e46c-143">BIGVARBINARY</span><span class="sxs-lookup"><span data-stu-id="8e46c-143">BIGVARBINARY</span></span>|<span data-ttu-id="8e46c-144">**NULL:** NULL, N/D</span><span class="sxs-lookup"><span data-stu-id="8e46c-144">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="8e46c-145">**ZERO:** VP, 0x00</span><span class="sxs-lookup"><span data-stu-id="8e46c-145">**ZERO:** VP, 0x00</span></span><br /><br /> <span data-ttu-id="8e46c-146">**>=255:** VP, 255 byte</span><span class="sxs-lookup"><span data-stu-id="8e46c-146">**>=255:** VP, 255 bytes</span></span><br /><br /> <span data-ttu-id="8e46c-147">**<255:** VP, dati effettivi</span><span class="sxs-lookup"><span data-stu-id="8e46c-147">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="8e46c-148">NCHAR</span><span class="sxs-lookup"><span data-stu-id="8e46c-148">NCHAR</span></span>|<span data-ttu-id="8e46c-149">**NULL:** NULL, N/D</span><span class="sxs-lookup"><span data-stu-id="8e46c-149">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="8e46c-150">**ZERO:** VP, 255 spazi</span><span class="sxs-lookup"><span data-stu-id="8e46c-150">**ZERO:** VP, 255 spaces</span></span><br /><br /> <span data-ttu-id="8e46c-151">**>=255:** VP, 255 caratteri</span><span class="sxs-lookup"><span data-stu-id="8e46c-151">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="8e46c-152">**<255:** VP, dati effettivi + riempimento (fino a 255)</span><span class="sxs-lookup"><span data-stu-id="8e46c-152">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="8e46c-153">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="8e46c-153">NVARCHAR</span></span>|<span data-ttu-id="8e46c-154">**NULL:** NULL, N/D</span><span class="sxs-lookup"><span data-stu-id="8e46c-154">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="8e46c-155">**ZERO:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="8e46c-155">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="8e46c-156">**>=255:** VP, 255 caratteri</span><span class="sxs-lookup"><span data-stu-id="8e46c-156">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="8e46c-157">**<255:** VP, dati effettivi</span><span class="sxs-lookup"><span data-stu-id="8e46c-157">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="8e46c-158">NTEXT</span><span class="sxs-lookup"><span data-stu-id="8e46c-158">NTEXT</span></span>|<span data-ttu-id="8e46c-159">**NULL:** N/D</span><span class="sxs-lookup"><span data-stu-id="8e46c-159">**NULL:** N/A</span></span><br /><br /> <span data-ttu-id="8e46c-160">**ZERO:** N/D</span><span class="sxs-lookup"><span data-stu-id="8e46c-160">**ZERO:** N/A</span></span><br /><br /> <span data-ttu-id="8e46c-161">**>=255:** N/D</span><span class="sxs-lookup"><span data-stu-id="8e46c-161">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="8e46c-162">\*\* \< 255:\*\* N/A</span><span class="sxs-lookup"><span data-stu-id="8e46c-162">**\<255:** N/A</span></span>|  
  
 <span data-ttu-id="8e46c-163">\*   i dati non sono con terminazione Null e non viene generato alcun avviso di troncamento per i dati >255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="8e46c-163">\*   data is not null-terminated; no warning is issued on truncation for data >255 characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e46c-164">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8e46c-164">Remarks</span></span>  
 <span data-ttu-id="8e46c-165">Se si conosce il nome del parametro, è possibile usare **srv_paramnumber** per ottenerne il numero.</span><span class="sxs-lookup"><span data-stu-id="8e46c-165">If you know the parameter name, you can use **srv_paramnumber** to get the parameter number.</span></span> <span data-ttu-id="8e46c-166">Per determinare se un parametro è NULL, usare **srv_paramlen**.</span><span class="sxs-lookup"><span data-stu-id="8e46c-166">To determine whether a parameter is NULL, use **srv_paramlen**.</span></span>  
  
 <span data-ttu-id="8e46c-167">Quando una chiamata alla stored procedure remota viene effettuata con i parametri, tali parametri possono essere passati per nome o per posizione (senza nome).</span><span class="sxs-lookup"><span data-stu-id="8e46c-167">When a remote stored procedure call is made with parameters, the parameters can be passed by name or by position (unnamed).</span></span> <span data-ttu-id="8e46c-168">Se invece viene effettuata con alcuni parametri passati per nome e altri passati per posizione, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="8e46c-168">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="8e46c-169">Se si verifica un errore, il gestore SRV_RPC viene chiamato comunque ma risulta che non sono presenti parametri e **srv_rpcparams** restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="8e46c-169">If an error occurs, the SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8e46c-170">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="8e46c-170">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="8e46c-171">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="8e46c-171">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e46c-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e46c-172">See Also</span></span>  
 [<span data-ttu-id="8e46c-173">srv_rpcparams &#40;API delle stored procedure estese&#41;</span><span class="sxs-lookup"><span data-stu-id="8e46c-173">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
