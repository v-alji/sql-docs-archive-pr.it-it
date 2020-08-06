---
title: srv_pfieldex (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_pfieldex
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_pfieldex
ms.assetid: d4e9a34b-b3a3-434f-8556-768bd20d145a
author: rothja
ms.author: jroth
ms.openlocfilehash: a474eafcb6b6d42161a7e67ce7f93636269c46c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626097"
---
# <a name="srv_pfieldex-extended-stored-procedure-api"></a><span data-ttu-id="28d89-102">srv_pfieldex (API delle stored procedure estese)</span><span class="sxs-lookup"><span data-stu-id="28d89-102">srv_pfieldex (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="28d89-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="28d89-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="28d89-104">Restituisce un puntatore ai dati che contengono il campo SRV_PROC richiesto.</span><span class="sxs-lookup"><span data-stu-id="28d89-104">Returns a pointer to data containing the requested SRV_PROC field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28d89-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28d89-105">Syntax</span></span>  
  
```  
  
void *srv_pfieldex(SRV_PROC *   
srvproc  
, int   
field  
, int *   
len  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="28d89-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="28d89-106">Arguments</span></span>  
 <span data-ttu-id="28d89-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="28d89-107">*srvproc*</span></span>  
 <span data-ttu-id="28d89-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client.</span><span class="sxs-lookup"><span data-stu-id="28d89-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="28d89-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="28d89-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="28d89-110">*campo*</span><span class="sxs-lookup"><span data-stu-id="28d89-110">*field*</span></span>  
 <span data-ttu-id="28d89-111">Specifica il campo *srvproc* da restituire.</span><span class="sxs-lookup"><span data-stu-id="28d89-111">Specifies the *srvproc* field to return.</span></span>  
  
|<span data-ttu-id="28d89-112">Campo</span><span class="sxs-lookup"><span data-stu-id="28d89-112">Field</span></span>|<span data-ttu-id="28d89-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28d89-113">Description</span></span>|<span data-ttu-id="28d89-114">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="28d89-114">Return-type</span></span>|  
|-----------|-----------------|------------------|  
|<span data-ttu-id="28d89-115">SRV_MSGLCID</span><span class="sxs-lookup"><span data-stu-id="28d89-115">SRV_MSGLCID</span></span>|<span data-ttu-id="28d89-116">LCDI di messaggio della sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="28d89-116">Current session message LCID.</span></span>|<span data-ttu-id="28d89-117">ULONG\*</span><span class="sxs-lookup"><span data-stu-id="28d89-117">ULONG\*</span></span>|  
|<span data-ttu-id="28d89-118">SRV_INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="28d89-118">SRV_INSTANCENAME</span></span>|<span data-ttu-id="28d89-119">Nome dell'istanza (se si tratta di un'istanza denominata); in caso contrario, restituisce NULL.</span><span class="sxs-lookup"><span data-stu-id="28d89-119">Instance name (if named); otherwise, returns NULL.</span></span>|<span data-ttu-id="28d89-120">WCHAR\*</span><span class="sxs-lookup"><span data-stu-id="28d89-120">WCHAR\*</span></span>|  
  
 <span data-ttu-id="28d89-121">*Len*</span><span class="sxs-lookup"><span data-stu-id="28d89-121">*len*</span></span>  
 <span data-ttu-id="28d89-122">Puntatore a una variabile **int** che contiene la lunghezza in byte del valore *field* restituito.</span><span class="sxs-lookup"><span data-stu-id="28d89-122">Is a pointer to an **int** variable that contains the length of the returned *field* value in bytes.</span></span> <span data-ttu-id="28d89-123">Se *len* è NULL, la lunghezza non viene restituita.</span><span class="sxs-lookup"><span data-stu-id="28d89-123">If *len* is NULL, the length is not returned.</span></span> <span data-ttu-id="28d89-124">Quando viene restituito NULL, \**len* è impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="28d89-124">When NULL is returned \**len* is set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="28d89-125">Restituisce</span><span class="sxs-lookup"><span data-stu-id="28d89-125">Returns</span></span>  
 <span data-ttu-id="28d89-126">Un puntatore ai dati il cui tipo dipende da *field*.</span><span class="sxs-lookup"><span data-stu-id="28d89-126">A pointer to data whose type depends on *field*.</span></span> <span data-ttu-id="28d89-127">Viene restituito NULL se *len* è NULL o *srvproc* è NULL.</span><span class="sxs-lookup"><span data-stu-id="28d89-127">NULL is returned when *len* is NULL or *srvproc* is NULL.</span></span> <span data-ttu-id="28d89-128">Se *field* non è noto, viene restituito NULL.</span><span class="sxs-lookup"><span data-stu-id="28d89-128">If the *field* is unknown, NULL is returned.</span></span> <span data-ttu-id="28d89-129">Quando viene restituito NULL, \**len* è impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="28d89-129">When NULL is returned \**len* is set to 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="28d89-130">Il buffer restituito dal server deve essere di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="28d89-130">The buffer returned from the server should be read only.</span></span> <span data-ttu-id="28d89-131">In caso contrario, lo stato del server può risultare danneggiato.</span><span class="sxs-lookup"><span data-stu-id="28d89-131">Otherwise, the server state may be corrupted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28d89-132">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="28d89-132">Remarks</span></span>  
 <span data-ttu-id="28d89-133">**Nota sulla sicurezza** È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="28d89-133">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="28d89-134">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="28d89-134">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
