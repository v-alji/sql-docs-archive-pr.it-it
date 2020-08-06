---
title: srv_rpcname (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcname
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcname
ms.assetid: 0a1424e4-3319-4836-b8d8-5e0344cc683f
author: rothja
ms.author: jroth
ms.openlocfilehash: 21530b3e7b8aaa8c5a3f8770762cde7e258e3a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725796"
---
# <a name="srv_rpcname-extended-stored-procedure-api"></a><span data-ttu-id="43c6f-102">srv_rpcname (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="43c6f-102">srv_rpcname (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="43c6f-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="43c6f-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="43c6f-104">Restituisce il componente del nome della procedura per la stored procedure remota corrente.</span><span class="sxs-lookup"><span data-stu-id="43c6f-104">Returns the procedure name component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c6f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43c6f-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcname (  
SRV_PROC *  
srvproc  
,  
int *  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="43c6f-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="43c6f-106">Arguments</span></span>  
 <span data-ttu-id="43c6f-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="43c6f-107">*srvproc*</span></span>  
 <span data-ttu-id="43c6f-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client. In questo caso, l'handle che ha ricevuto la stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="43c6f-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="43c6f-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="43c6f-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="43c6f-110">*Len*</span><span class="sxs-lookup"><span data-stu-id="43c6f-110">*len*</span></span>  
 <span data-ttu-id="43c6f-111">Puntatore a una variabile di tipo integer che riceve la lunghezza del nome del database.</span><span class="sxs-lookup"><span data-stu-id="43c6f-111">Is a pointer to an integer variable that receives the length of the database name.</span></span> <span data-ttu-id="43c6f-112">Se *len* è NULL, la lunghezza del nome della stored procedure remota non viene restituita.</span><span class="sxs-lookup"><span data-stu-id="43c6f-112">If *len* is NULL, the length of the remote stored procedure name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="43c6f-113">Restituisce</span><span class="sxs-lookup"><span data-stu-id="43c6f-113">Returns</span></span>  
 <span data-ttu-id="43c6f-114">Puntatore DBCHAR alla stringa con terminazione Null per il componente del nome della stored procedure remota della stored procedure remota corrente.</span><span class="sxs-lookup"><span data-stu-id="43c6f-114">A DBCHAR pointer to the null-terminated string for the remote stored procedure name component of the current remote stored procedure.</span></span> <span data-ttu-id="43c6f-115">Se non è presente alcuna stored procedure remota corrente, viene restituito NULL e *len* viene impostato su -1.</span><span class="sxs-lookup"><span data-stu-id="43c6f-115">If there is not a current remote stored procedure, NULL is returned and *len* is set to -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43c6f-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="43c6f-116">Remarks</span></span>  
 <span data-ttu-id="43c6f-117">Questa funzione restituisce solo il nome della stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="43c6f-117">This function returns only the name of the remote stored procedure.</span></span> <span data-ttu-id="43c6f-118">Non include gli identificatori facoltativi per il proprietario, il nome del database e il numero della stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="43c6f-118">It does not include the optional specifiers for owner, database name, and remote stored procedure number.</span></span>  
  
 <span data-ttu-id="43c6f-119">Poiché è possibile chiamare **srv_rpcname** in assenza di stored procedure remote (non viene visualizzato alcun errore informativo), questa funzione offre un metodo per la verifica dell'eventuale presenza di una stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="43c6f-119">Because it is valid to call **srv_rpcname** when there is not a remote stored procedure (no informational error occurs), this function provides a method for determining whether a remote stored procedure exists.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="43c6f-120">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="43c6f-120">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="43c6f-121">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="43c6f-121">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
