---
title: srv_rpcnumber (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcnumber
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcnumber
ms.assetid: 3094085e-fe9e-423d-bf87-7852352c2d26
author: rothja
ms.author: jroth
ms.openlocfilehash: 25f30f8288125cf64d6b10a867d6af03c0f8ee91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725795"
---
# <a name="srv_rpcnumber-extended-stored-procedure-api"></a><span data-ttu-id="eb7b4-102">srv_rpcnumber (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="eb7b4-102">srv_rpcnumber (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="eb7b4-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="eb7b4-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="eb7b4-104">Restituisce il componente numerico per la chiamata alla stored procedure remota corrente.</span><span class="sxs-lookup"><span data-stu-id="eb7b4-104">Returns the number component for the current remote stored procedure call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb7b4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb7b4-105">Syntax</span></span>  
  
```  
  
int srv_rpcnumber ( SRV_PROC *  
srvproc   
)  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="eb7b4-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="eb7b4-106">Arguments</span></span>  
 <span data-ttu-id="eb7b4-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="eb7b4-107">*srvproc*</span></span>  
 <span data-ttu-id="eb7b4-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client. In questo caso, l'handle che ha ricevuto la stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="eb7b4-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="eb7b4-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="eb7b4-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="eb7b4-110">Restituisce</span><span class="sxs-lookup"><span data-stu-id="eb7b4-110">Returns</span></span>  
 <span data-ttu-id="eb7b4-111">Il componente numerico per la stored procedure remota corrente.</span><span class="sxs-lookup"><span data-stu-id="eb7b4-111">The number component for the current remote stored procedure.</span></span> <span data-ttu-id="eb7b4-112">Se il client non utilizza un componente numerico durante l'esecuzione della stored procedure remota o se non è presente una stored procedure remota corrente, restituisce - 1.</span><span class="sxs-lookup"><span data-stu-id="eb7b4-112">If the client does not use a number component when running the remote stored procedure or if there is no current remote stored procedure, it returns - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb7b4-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="eb7b4-113">Remarks</span></span>  
 <span data-ttu-id="eb7b4-114">Questa funzione restituisce solo il componente numerico della stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="eb7b4-114">This function returns only the number component of the remote stored procedure.</span></span> <span data-ttu-id="eb7b4-115">Non include gli identificatori facoltativi per il proprietario, il nome della stored procedure remota e il nome del database.</span><span class="sxs-lookup"><span data-stu-id="eb7b4-115">It does not include the optional specifiers for owner, remote stored procedure name, and database name.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="eb7b4-116">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="eb7b4-116">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="eb7b4-117">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="eb7b4-117">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
