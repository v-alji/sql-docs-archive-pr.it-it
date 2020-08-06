---
title: srv_rpcowner (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcowner
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcowner
ms.assetid: e81a60e6-14ea-47bc-a11c-3d7635344447
author: rothja
ms.author: jroth
ms.openlocfilehash: f903870d0ee01256addb1557eb7e9123853b39e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726927"
---
# <a name="srv_rpcowner-extended-stored-procedure-api"></a><span data-ttu-id="6977e-102">srv_rpcowner (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="6977e-102">srv_rpcowner (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="6977e-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="6977e-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="6977e-104">Restituisce il componente proprietario per la stored procedure remota corrente.</span><span class="sxs-lookup"><span data-stu-id="6977e-104">Returns the owner component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6977e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6977e-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcowner (  
SRV_PROC *  
srvproc  
,  
int *  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="6977e-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6977e-106">Arguments</span></span>  
 <span data-ttu-id="6977e-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="6977e-107">*srvproc*</span></span>  
 <span data-ttu-id="6977e-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client. In questo caso, l'handle che ha ricevuto la stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="6977e-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="6977e-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="6977e-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="6977e-110">*Len*</span><span class="sxs-lookup"><span data-stu-id="6977e-110">*len*</span></span>  
 <span data-ttu-id="6977e-111">Puntatore a una variabile di tipo integer che riceve la lunghezza del nome del proprietario.</span><span class="sxs-lookup"><span data-stu-id="6977e-111">Is a pointer to an integer variable that receives the length of the owner name.</span></span> <span data-ttu-id="6977e-112">Il parametro *len* può essere NULL. In tal caso, non viene restituita la lunghezza del componente proprietario.</span><span class="sxs-lookup"><span data-stu-id="6977e-112">The parameter *len* can be NULL, in which case the length of the owner component is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="6977e-113">Restituisce</span><span class="sxs-lookup"><span data-stu-id="6977e-113">Returns</span></span>  
 <span data-ttu-id="6977e-114">Puntatore DBCHAR al componente proprietario con terminazione Null per la stored procedure remota corrente.</span><span class="sxs-lookup"><span data-stu-id="6977e-114">A DBCHAR pointer to the null-terminated owner component for the current remote stored procedure.</span></span> <span data-ttu-id="6977e-115">Se non è presente alcuna stored procedure remota corrente, viene restituito NULL e *len* viene impostato su -1.</span><span class="sxs-lookup"><span data-stu-id="6977e-115">If there is no current remote stored procedure, NULL is returned and *len* is set to - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6977e-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6977e-116">Remarks</span></span>  
 <span data-ttu-id="6977e-117">Questa funzione restituisce solo il componente proprietario della stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="6977e-117">This function returns only the owner component of the remote stored procedure.</span></span> <span data-ttu-id="6977e-118">Non include gli identificatori facoltativi per il nome, il nome della stored procedure remota e il numero della stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="6977e-118">It does not include the optional specifiers for name, remote stored procedure name, and remote stored procedure number.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6977e-119">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="6977e-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="6977e-120">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="6977e-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
