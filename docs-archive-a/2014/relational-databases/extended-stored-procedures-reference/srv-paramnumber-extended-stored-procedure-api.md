---
title: srv_paramnumber (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramnumber
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramnumber
ms.assetid: d7a6dbff-71d9-4297-8a4f-bfd2876fe204
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e621101c909ef251c40f38713e438d8e40d08a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635599"
---
# <a name="srv_paramnumber-extended-stored-procedure-api"></a><span data-ttu-id="9516f-102">srv_paramnumber (API delle stored procedure estese)</span><span class="sxs-lookup"><span data-stu-id="9516f-102">srv_paramnumber (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="9516f-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="9516f-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="9516f-104">Restituisce il numero di un parametro di chiamata a una stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="9516f-104">Returns the number of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9516f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9516f-105">Syntax</span></span>  
  
```  
  
int srv_paramnumber (  
SRV_PROC *  
srvproc  
,  
DBCHAR *  
name  
,   
int  
namelen   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="9516f-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9516f-106">Arguments</span></span>  
 <span data-ttu-id="9516f-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="9516f-107">*srvproc*</span></span>  
 <span data-ttu-id="9516f-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client. In questo caso, l'handle che ha ricevuto la chiamata alla stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="9516f-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="9516f-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="9516f-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="9516f-110">*nome*</span><span class="sxs-lookup"><span data-stu-id="9516f-110">*name*</span></span>  
 <span data-ttu-id="9516f-111">Puntatore al parametro *name*.</span><span class="sxs-lookup"><span data-stu-id="9516f-111">Is a pointer to the parameter *name*.</span></span>  
  
 <span data-ttu-id="9516f-112">*namelen*</span><span class="sxs-lookup"><span data-stu-id="9516f-112">*namelen*</span></span>  
 <span data-ttu-id="9516f-113">Lunghezza di *name*.</span><span class="sxs-lookup"><span data-stu-id="9516f-113">Is the length of *name*.</span></span> <span data-ttu-id="9516f-114">Se *name* è con terminazione Null, impostare *namelen* su SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="9516f-114">If *name* is null-terminated, set *namelen* to SRV_NULLTERM.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="9516f-115">Restituisce</span><span class="sxs-lookup"><span data-stu-id="9516f-115">Returns</span></span>  
 <span data-ttu-id="9516f-116">Numero di parametro del parametro denominato.</span><span class="sxs-lookup"><span data-stu-id="9516f-116">The parameter number of the named parameter.</span></span> <span data-ttu-id="9516f-117">Il primo parametro è 1.</span><span class="sxs-lookup"><span data-stu-id="9516f-117">The first parameter is 1.</span></span> <span data-ttu-id="9516f-118">Se non è presente alcun parametro denominato *name* o alcuna stored procedure remota, viene restituito 0 e viene generato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="9516f-118">If there is no parameter named *name* or no remote stored procedure, 0 is returned and a message is generated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9516f-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9516f-119">Remarks</span></span>  
 <span data-ttu-id="9516f-120">Quando viene effettuata una chiamata a una stored procedure remota con parametri, tali parametri possono essere passati per nome o per posizione (senza nome).</span><span class="sxs-lookup"><span data-stu-id="9516f-120">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="9516f-121">Se invece viene effettuata con alcuni parametri passati per nome e altri passati per posizione, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="9516f-121">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="9516f-122">Il gestore SRV_RPC viene comunque chiamato, ma risulta che non sono presenti parametri e **srv_rpcparams** restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="9516f-122">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9516f-123">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="9516f-123">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="9516f-124">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="9516f-124">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9516f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9516f-125">See Also</span></span>  
 [<span data-ttu-id="9516f-126">srv_rpcparams &#40;API delle stored procedure estese&#41;</span><span class="sxs-lookup"><span data-stu-id="9516f-126">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
