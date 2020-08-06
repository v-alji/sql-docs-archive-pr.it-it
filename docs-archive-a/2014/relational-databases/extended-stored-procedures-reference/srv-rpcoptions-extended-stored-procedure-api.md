---
title: srv_rpcoptions (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcoptions
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcoptions
ms.assetid: dbcce5d1-d5a1-4379-9597-04e43af5923d
author: rothja
ms.author: jroth
ms.openlocfilehash: f5ebe4ab48721002e679ce149293b474a934e348
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726928"
---
# <a name="srv_rpcoptions-extended-stored-procedure-api"></a><span data-ttu-id="9181c-102">srv_rpcoptions (API delle stored procedure estese)</span><span class="sxs-lookup"><span data-stu-id="9181c-102">srv_rpcoptions (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="9181c-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="9181c-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="9181c-104">Restituisce le opzioni di runtime per la stored procedure remota corrente.</span><span class="sxs-lookup"><span data-stu-id="9181c-104">Returns run-time options for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9181c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9181c-105">Syntax</span></span>  
  
```  
  
DBUSMALLINT srv_rpcoptions ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="9181c-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9181c-106">Arguments</span></span>  
 <span data-ttu-id="9181c-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="9181c-107">*srvproc*</span></span>  
 <span data-ttu-id="9181c-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client. In questo caso, l'handle che ha ricevuto la stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="9181c-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="9181c-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="9181c-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="9181c-110">Restituisce</span><span class="sxs-lookup"><span data-stu-id="9181c-110">Returns</span></span>  
 <span data-ttu-id="9181c-111">Una bitmap che contiene i flag di esecuzione uniti in un'operazione con OR logico per la stored procedure remota corrente.</span><span class="sxs-lookup"><span data-stu-id="9181c-111">A bitmap that contains the run-time flags joined in a logical OR for the current remote stored procedure.</span></span> <span data-ttu-id="9181c-112">Se non è presente alcuna stored procedure remota corrente, viene restituito 0 e viene generato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="9181c-112">If there is not a current remote stored procedure, 0 is returned and a message is generated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9181c-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9181c-113">Remarks</span></span>  
 <span data-ttu-id="9181c-114">Nella tabella seguente viene descritto ciascun flag di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9181c-114">The following table describes each run-time flag.</span></span>  
  
|<span data-ttu-id="9181c-115">Flag di esecuzione</span><span class="sxs-lookup"><span data-stu-id="9181c-115">Run-time flag</span></span>|<span data-ttu-id="9181c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9181c-116">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="9181c-117">SRV_NOMETADATA</span><span class="sxs-lookup"><span data-stu-id="9181c-117">SRV_NOMETADATA</span></span>|<span data-ttu-id="9181c-118">Il client ha richiesto risultati senza informazioni sui metadati.</span><span class="sxs-lookup"><span data-stu-id="9181c-118">The client has requested results without metadata information.</span></span> <span data-ttu-id="9181c-119">Questo flag viene utilizzato solo quando il client comunica con un'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9181c-119">This flag is only used when the client is communicating with an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9181c-120">Un'applicazione API delle stored procedure estese non può omettere le informazioni sui metadati.</span><span class="sxs-lookup"><span data-stu-id="9181c-120">An Extended Stored Procedure API application cannot omit metadata information.</span></span>|  
|<span data-ttu-id="9181c-121">SRV_RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="9181c-121">SRV_RECOMPILE</span></span>|<span data-ttu-id="9181c-122">Il client ha richiesto di ricompilare la stored procedure remota prima di eseguirla.</span><span class="sxs-lookup"><span data-stu-id="9181c-122">The client has requested to recompile the remote stored procedure before executing it.</span></span> <span data-ttu-id="9181c-123">Questo flag non può essere applicato a un'applicazione API delle stored procedure estese.</span><span class="sxs-lookup"><span data-stu-id="9181c-123">This flag may not apply to an Extended Stored Procedure API application.</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9181c-124">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="9181c-124">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="9181c-125">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="9181c-125">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
