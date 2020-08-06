---
title: srv_rpcdb (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcdb
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcdb
ms.assetid: d52bfd22-7a7c-4ab0-af65-df96ff359e6f
author: rothja
ms.author: jroth
ms.openlocfilehash: c951a4a821bbd49748182d9ddf5df017344a174d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723888"
---
# <a name="srv_rpcdb-extended-stored-procedure-api"></a><span data-ttu-id="6beba-102">srv_rpcdb (API delle stored procedure estese)</span><span class="sxs-lookup"><span data-stu-id="6beba-102">srv_rpcdb (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="6beba-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="6beba-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="6beba-104">Restituisce il componente del nome del database per la stored procedure remota corrente.</span><span class="sxs-lookup"><span data-stu-id="6beba-104">Returns the database name component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6beba-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6beba-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcdb (  
SRV_PROC * srvproc,int *len );  
```  
  
## <a name="arguments"></a><span data-ttu-id="6beba-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6beba-106">Arguments</span></span>  
 <span data-ttu-id="6beba-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="6beba-107">*srvproc*</span></span>  
 <span data-ttu-id="6beba-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client.</span><span class="sxs-lookup"><span data-stu-id="6beba-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="6beba-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="6beba-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="6beba-110">*Len*</span><span class="sxs-lookup"><span data-stu-id="6beba-110">*len*</span></span>  
 <span data-ttu-id="6beba-111">Puntatore a una variabile `int` che riceve la lunghezza del nome del database.</span><span class="sxs-lookup"><span data-stu-id="6beba-111">Is a pointer to an `int` variable that receives the length of the database name.</span></span> <span data-ttu-id="6beba-112">Se *len* è NULL, la lunghezza del nome del database non viene restituita.</span><span class="sxs-lookup"><span data-stu-id="6beba-112">If *len* is NULL, the length of the database name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="6beba-113">Restituisce</span><span class="sxs-lookup"><span data-stu-id="6beba-113">Returns</span></span>  
 <span data-ttu-id="6beba-114">Puntatore DBCHAR alla stringa con terminazione Null per la parte del nome del database della stored procedure remota corrente.</span><span class="sxs-lookup"><span data-stu-id="6beba-114">A DBCHAR pointer to the null-terminated string for the database name part of the current remote stored procedure.</span></span> <span data-ttu-id="6beba-115">Se non è presente alcuna stored procedure remota corrente, viene restituito NULL e il parametro *len* viene impostato su -1.</span><span class="sxs-lookup"><span data-stu-id="6beba-115">If there is no current remote stored procedure, NULL is returned and the *len* parameter is set to - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6beba-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6beba-116">Remarks</span></span>  
 <span data-ttu-id="6beba-117">Questa funzione restituisce solo il componente del database del nome dell'oggetto stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="6beba-117">This function returns only the database component of the remote stored procedure object name.</span></span> <span data-ttu-id="6beba-118">Non include gli identificatori facoltativi per il proprietario, il nome della stored procedure remota e il numero della stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="6beba-118">It does not include the optional specifiers for owner, remote stored procedure name, and remote stored procedure number.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6beba-119">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="6beba-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="6beba-120">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="6beba-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
