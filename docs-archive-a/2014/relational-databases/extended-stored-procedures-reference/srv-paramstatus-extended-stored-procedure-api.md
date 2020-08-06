---
title: srv_paramstatus (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramstatus
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramstatus
ms.assetid: 86cecd45-0b09-42e9-8152-32a12a1c2b7a
author: rothja
ms.author: jroth
ms.openlocfilehash: d89d4ccbb6a97ff47669ad4ed9c0b4c22ac934eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711920"
---
# <a name="srv_paramstatus-extended-stored-procedure-api"></a><span data-ttu-id="5c6a8-102">srv_paramstatus (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="5c6a8-102">srv_paramstatus (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="5c6a8-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="5c6a8-104">Restituisce lo stato di un determinato parametro di chiamata a una stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-104">Returns the status of a particular remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c6a8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c6a8-105">Syntax</span></span>  
  
```  
  
int srv_paramstatus (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="5c6a8-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5c6a8-106">Arguments</span></span>  
 <span data-ttu-id="5c6a8-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="5c6a8-107">*srvproc*</span></span>  
 <span data-ttu-id="5c6a8-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client. In questo caso, l'handle che ha ricevuto la chiamata alla stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="5c6a8-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="5c6a8-110">*n*</span><span class="sxs-lookup"><span data-stu-id="5c6a8-110">*n*</span></span>  
 <span data-ttu-id="5c6a8-111">Indica il numero del parametro.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="5c6a8-112">Il primo parametro è 1.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-112">The first parameter is number 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="5c6a8-113">Restituisce</span><span class="sxs-lookup"><span data-stu-id="5c6a8-113">Returns</span></span>  
 <span data-ttu-id="5c6a8-114">`int` contenente flag di stato per il parametro.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-114">An `int` that contains status flags for the parameter.</span></span> <span data-ttu-id="5c6a8-115">Attualmente è disponibile un solo flag: se il bit 0 è impostato su 1, il parametro è un parametro restituito.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-115">Currently, there is only one flag: If bit 0 is set to 1, the parameter is a return parameter.</span></span> <span data-ttu-id="5c6a8-116">Se non è presente nessun parametro *n* o nessuna stored procedure remota, restituisce -1.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c6a8-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5c6a8-117">Remarks</span></span>  
 <span data-ttu-id="5c6a8-118">Questa routine restituisce i flag di stato per un determinato parametro di chiamata a una stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-118">This routine returns the status flags for a remote stored procedure call parameter.</span></span>  
  
 <span data-ttu-id="5c6a8-119">I parametri contengono i dati passati tra i client e l'applicazione con stored procedure remote.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-119">Parameters contain data passed between clients and the application with remote stored procedures.</span></span> <span data-ttu-id="5c6a8-120">Il client può specificare determinati parametri come parametri restituiti.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-120">The client can specify certain parameters as return parameters.</span></span> <span data-ttu-id="5c6a8-121">Questi parametri restituiti possono contenere valori che l'applicazione passa nuovamente al client.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-121">These return parameters can contain values that the application passes back to the client.</span></span>  
  
 <span data-ttu-id="5c6a8-122">Attualmente l'unico flag di stato è quello che indica se il parametro è un parametro restituito.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-122">Currently, the only status flag is one that indicates whether the parameter is a return parameter.</span></span>  
  
 <span data-ttu-id="5c6a8-123">Quando viene effettuata una chiamata a una stored procedure remota con parametri, tali parametri possono essere passati per nome o per posizione (senza nome).</span><span class="sxs-lookup"><span data-stu-id="5c6a8-123">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="5c6a8-124">Se invece viene effettuata con alcuni parametri passati per nome e altri passati per posizione, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-124">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="5c6a8-125">Se si verifica un errore, il gestore SRV_RPC viene ancora chiamato, ma viene visualizzato come se non fossero presenti parametri e **srv_rpcparams** restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-125">If an error occurs, the SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5c6a8-126">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="5c6a8-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="5c6a8-127">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="5c6a8-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c6a8-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c6a8-128">See Also</span></span>  
 [<span data-ttu-id="5c6a8-129">srv_rpcparams &#40;API delle stored procedure estese&#41;</span><span class="sxs-lookup"><span data-stu-id="5c6a8-129">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
