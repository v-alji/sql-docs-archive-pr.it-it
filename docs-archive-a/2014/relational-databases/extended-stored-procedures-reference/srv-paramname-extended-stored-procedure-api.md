---
title: srv_paramname (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramname
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramname
ms.assetid: 1a53d707-7b06-49cc-a0df-ac727cfe953f
author: rothja
ms.author: jroth
ms.openlocfilehash: 2227ac3d46efe7d09abc05964248229f3533d42d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725804"
---
# <a name="srv_paramname-extended-stored-procedure-api"></a><span data-ttu-id="af80a-102">srv_paramname (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="af80a-102">srv_paramname (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="af80a-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="af80a-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="af80a-104">Restituisce il nome di un parametro di chiamata a una stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="af80a-104">Returns the name of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af80a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af80a-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_paramname (  
SRV_PROC * srvproc,intn, int *len );  
```  
  
## <a name="arguments"></a><span data-ttu-id="af80a-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="af80a-106">Arguments</span></span>  
 <span data-ttu-id="af80a-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="af80a-107">*srvproc*</span></span>  
 <span data-ttu-id="af80a-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client. In questo caso, l'handle che ha ricevuto la chiamata alla stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="af80a-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="af80a-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="af80a-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="af80a-110">*n*</span><span class="sxs-lookup"><span data-stu-id="af80a-110">*n*</span></span>  
 <span data-ttu-id="af80a-111">Indica il numero del parametro.</span><span class="sxs-lookup"><span data-stu-id="af80a-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="af80a-112">Il primo parametro è 1.</span><span class="sxs-lookup"><span data-stu-id="af80a-112">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="af80a-113">*Len*</span><span class="sxs-lookup"><span data-stu-id="af80a-113">*len*</span></span>  
 <span data-ttu-id="af80a-114">Fornisce un puntatore a una variabile `int` che contiene la lunghezza, espressa in byte, del nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="af80a-114">Provides a pointer to an `int` variable that contains the length, in bytes, of the parameter name.</span></span> <span data-ttu-id="af80a-115">Se *len* è NULL, la lunghezza del nome del parametro della stored procedure remota non viene restituita.</span><span class="sxs-lookup"><span data-stu-id="af80a-115">If *len* is NULL, the length of the remote stored procedure parameter name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="af80a-116">Restituisce</span><span class="sxs-lookup"><span data-stu-id="af80a-116">Returns</span></span>  
 <span data-ttu-id="af80a-117">Puntatore a una stringa di caratteri con terminazione di tipo Null che contiene il nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="af80a-117">A pointer to a null-terminated character string that contains the parameter name.</span></span> <span data-ttu-id="af80a-118">La lunghezza del nome del parametro viene archiviata in *len*.</span><span class="sxs-lookup"><span data-stu-id="af80a-118">The length of the parameter name is stored in *len*.</span></span> <span data-ttu-id="af80a-119">Se non è presente nessun parametro *n* o nessuna stored procedure remota, restituisce NULL, imposta *len* su -1 e invia un messaggio di errore informativo.</span><span class="sxs-lookup"><span data-stu-id="af80a-119">If there is no *n*th parameter or no remote stored procedure, it returns NULL, *len* is set to -1, and an informational error message is sent.</span></span> <span data-ttu-id="af80a-120">Se il nome del parametro è NULL, *len* viene impostato su 0 e viene restituita una stringa vuota con terminazione di tipo Null.</span><span class="sxs-lookup"><span data-stu-id="af80a-120">If the parameter name is NULL, *len* is set to 0 and a null-terminated empty string is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af80a-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="af80a-121">Remarks</span></span>  
 <span data-ttu-id="af80a-122">Questa funzione ottiene il nome di un parametro di chiamata alla stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="af80a-122">This function gets the name of a remote stored procedure call parameter.</span></span> <span data-ttu-id="af80a-123">Quando viene effettuata una chiamata a una stored procedure remota con parametri, tali parametri possono essere passati per nome o per posizione (senza nome).</span><span class="sxs-lookup"><span data-stu-id="af80a-123">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="af80a-124">Se invece viene effettuata con alcuni parametri passati per nome e altri passati per posizione, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="af80a-124">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="af80a-125">Il gestore SRV_RPC viene comunque chiamato, ma risulta che non sono presenti parametri e **srv_rpcparams** restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="af80a-125">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="af80a-126">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="af80a-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="af80a-127">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="af80a-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af80a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af80a-128">See Also</span></span>  
 [<span data-ttu-id="af80a-129">srv_rpcparams &#40;API delle stored procedure estese&#41;</span><span class="sxs-lookup"><span data-stu-id="af80a-129">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
