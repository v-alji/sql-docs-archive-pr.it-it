---
title: srv_rpcparams (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcparams
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcparams
ms.assetid: 96a5e6f6-d320-4623-b96e-0a856e3abebb
author: rothja
ms.author: jroth
ms.openlocfilehash: 443b9ea8a67341afdb92f0c384148c8b1b42f752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726920"
---
# <a name="srv_rpcparams-extended-stored-procedure-api"></a><span data-ttu-id="082ee-102">srv_rpcparams (API delle stored procedure estese)</span><span class="sxs-lookup"><span data-stu-id="082ee-102">srv_rpcparams (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="082ee-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="082ee-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="082ee-104">Restituisce il numero di parametri per la chiamata alla stored procedure remota corrente.</span><span class="sxs-lookup"><span data-stu-id="082ee-104">Returns the number of parameters for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="082ee-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="082ee-105">Syntax</span></span>  
  
```  
  
int srv_rpcparams ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="082ee-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="082ee-106">Arguments</span></span>  
 <span data-ttu-id="082ee-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="082ee-107">*srvproc*</span></span>  
 <span data-ttu-id="082ee-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client. In questo caso, l'handle che ha ricevuto la stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="082ee-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="082ee-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="082ee-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="082ee-110">Restituisce</span><span class="sxs-lookup"><span data-stu-id="082ee-110">Returns</span></span>  
 <span data-ttu-id="082ee-111">Numero di parametri nella stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="082ee-111">The number of parameters in the remote stored procedure.</span></span> <span data-ttu-id="082ee-112">Se nella stored procedure remota non sono inclusi parametri o se non è presente una stored procedure remota corrente, viene restituito -1 e viene generato un messaggio di errore informativo.</span><span class="sxs-lookup"><span data-stu-id="082ee-112">If there are no parameters in the remote stored procedure or if there is not a current remote stored procedure, -1 is returned and an information error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="082ee-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="082ee-113">Remarks</span></span>  
 <span data-ttu-id="082ee-114">Questa funzione restituisce il numero di parametri nella stored procedure remota corrente.</span><span class="sxs-lookup"><span data-stu-id="082ee-114">This function returns the number of parameters in the current remote stored procedure.</span></span> <span data-ttu-id="082ee-115">La funzione viene in genere chiamata dalla stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="082ee-115">It is usually called from the remote stored procedure.</span></span>  
  
 <span data-ttu-id="082ee-116">Quando viene effettuata una chiamata a una stored procedure remota con parametri, tali parametri possono essere passati per nome o per posizione (senza nome).</span><span class="sxs-lookup"><span data-stu-id="082ee-116">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="082ee-117">Se la chiamata alla stored procedure è stata eseguita con alcuni parametri passati per nome e alcuni passati per posizione, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="082ee-117">If the remote stored procedure call was made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="082ee-118">Quando si verifica questo errore, viene chiamato il gestore delle stored procedure remote, ma non vengono ricevuti i parametri e **srv_rpcparams** restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="082ee-118">When this error occurs, the remote stored procedure handler is called, but it does not receive the parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="082ee-119">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="082ee-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="082ee-120">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="082ee-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
