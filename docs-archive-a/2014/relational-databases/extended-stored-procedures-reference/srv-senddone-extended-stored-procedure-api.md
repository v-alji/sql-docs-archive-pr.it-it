---
title: srv_senddone (API Stored Procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_senddone
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_senddone
ms.assetid: 1fc4f1d5-56d4-43f6-b5e4-0c0cc295cba3
author: rothja
ms.author: jroth
ms.openlocfilehash: 877acdc1b666c7f4cbaab737590a1c55e474eb05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726919"
---
# <a name="srv_senddone-extended-stored-procedure-api"></a><span data-ttu-id="090d1-102">srv_senddone (API delle stored procedure estese)</span><span class="sxs-lookup"><span data-stu-id="090d1-102">srv_senddone (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="090d1-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="090d1-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="090d1-104">Invia messaggio di completamento dei risultati al client.</span><span class="sxs-lookup"><span data-stu-id="090d1-104">Sends a result completion message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="090d1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="090d1-105">Syntax</span></span>  
  
```  
  
int srv_senddone (  
SRV_PROC *  
srvproc  
,  
DBUSMALLINT   
status  
,  
DBUSMALLINT  
info  
,  
DBINT  
count   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="090d1-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="090d1-106">Arguments</span></span>  
 <span data-ttu-id="090d1-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="090d1-107">*srvproc*</span></span>  
 <span data-ttu-id="090d1-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client, in questo caso l'handle che ha ricevuto la richiesta del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="090d1-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="090d1-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="090d1-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="090d1-110">*Stato*</span><span class="sxs-lookup"><span data-stu-id="090d1-110">*status*</span></span>  
 <span data-ttu-id="090d1-111">Campo a 2 byte per vari flag di *status*.</span><span class="sxs-lookup"><span data-stu-id="090d1-111">Is a 2-byte field for various *status* flags.</span></span> <span data-ttu-id="090d1-112">È possibile impostare più flag usando gli operatori logici AND e OR con i valori dei flag di *status*.</span><span class="sxs-lookup"><span data-stu-id="090d1-112">Multiple flags can be set by using the AND and OR logical operators with *status* flag values.</span></span> <span data-ttu-id="090d1-113">Nella tabella seguente sono elencati i possibili flag di *status*.</span><span class="sxs-lookup"><span data-stu-id="090d1-113">The following table lists possible *status* flags.</span></span>  
  
|<span data-ttu-id="090d1-114">Flag di stato</span><span class="sxs-lookup"><span data-stu-id="090d1-114">Status flag</span></span>|<span data-ttu-id="090d1-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="090d1-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="090d1-116">SRV_DONE_COUNT</span><span class="sxs-lookup"><span data-stu-id="090d1-116">SRV_DONE_COUNT</span></span>|<span data-ttu-id="090d1-117">Il parametro *count* contiene un conteggio valido.</span><span class="sxs-lookup"><span data-stu-id="090d1-117">The *count* parameter contains a valid count.</span></span>|  
|<span data-ttu-id="090d1-118">SRV_DONE_ERROR</span><span class="sxs-lookup"><span data-stu-id="090d1-118">SRV_DONE_ERROR</span></span>|<span data-ttu-id="090d1-119">Il comando client corrente ha ricevuto un errore.</span><span class="sxs-lookup"><span data-stu-id="090d1-119">The current client command received an error.</span></span>|  
  
 <span data-ttu-id="090d1-120">*info*</span><span class="sxs-lookup"><span data-stu-id="090d1-120">*info*</span></span>  
 <span data-ttu-id="090d1-121">Campo a 2 byte riservato.</span><span class="sxs-lookup"><span data-stu-id="090d1-121">Is a reserved, 2-byte field.</span></span> <span data-ttu-id="090d1-122">Impostare questo valore su 0.</span><span class="sxs-lookup"><span data-stu-id="090d1-122">Set this value to 0.</span></span>  
  
 <span data-ttu-id="090d1-123">*count*</span><span class="sxs-lookup"><span data-stu-id="090d1-123">*count*</span></span>  
 <span data-ttu-id="090d1-124">Campo a 4 byte utilizzato per indicare un conteggio per il set di risultati corrente.</span><span class="sxs-lookup"><span data-stu-id="090d1-124">Is a 4-byte field used to indicate a count for the current result set.</span></span> <span data-ttu-id="090d1-125">Se il flag SRV_DONE_COUNT è impostato nel campo *status*, *count* include un conteggio valido.</span><span class="sxs-lookup"><span data-stu-id="090d1-125">If the SRV_DONE_COUNT flag is set in the *status* field, *count* holds a valid count.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="090d1-126">Restituisce</span><span class="sxs-lookup"><span data-stu-id="090d1-126">Returns</span></span>  
 <span data-ttu-id="090d1-127">SUCCEED o FAIL</span><span class="sxs-lookup"><span data-stu-id="090d1-127">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="090d1-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="090d1-128">Remarks</span></span>  
 <span data-ttu-id="090d1-129">Una richiesta del client può provocare l'esecuzione da parte del server di alcuni comandi e la restituzione di alcuni set di risultati.</span><span class="sxs-lookup"><span data-stu-id="090d1-129">A client request can cause the server to execute a number of commands and to return a number of result sets.</span></span> <span data-ttu-id="090d1-130">Per ogni set di risultati, **srv_senddone** deve restituire un messaggio di completamento dei risultati al client.</span><span class="sxs-lookup"><span data-stu-id="090d1-130">For each result set, **srv_senddone** must return a result completion message to the client.</span></span>  
  
 <span data-ttu-id="090d1-131">Il campo *count* indica il numero di righe interessate da un comando.</span><span class="sxs-lookup"><span data-stu-id="090d1-131">The *count* field indicates the number of rows affected by a command.</span></span> <span data-ttu-id="090d1-132">Se il campo *count* contiene un conteggio, il flag SRV_DONE_COUNT deve essere impostato nel campo *status*.</span><span class="sxs-lookup"><span data-stu-id="090d1-132">If the *count* field contains a count, the SRV_DONE_COUNT flag should be set in the *status* field.</span></span> <span data-ttu-id="090d1-133">Questa impostazione consente al client di distinguere tra un valore di *count* pari a 0 e un campo *count* inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="090d1-133">This setting allows the client to distinguish between a *count* value of 0 and an unused *count* field.</span></span>  
  
 <span data-ttu-id="090d1-134">Non chiamare **srv_senddone** dal gestore SRV_CONNECT.</span><span class="sxs-lookup"><span data-stu-id="090d1-134">Do not call **srv_senddone** from the SRV_CONNECT handler.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="090d1-135">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="090d1-135">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="090d1-136">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="090d1-136">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
