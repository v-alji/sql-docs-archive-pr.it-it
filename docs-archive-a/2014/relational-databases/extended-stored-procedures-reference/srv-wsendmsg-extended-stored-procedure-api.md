---
title: srv_wsendmsg (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_wsendmsg
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_wsendmsg
ms.assetid: f2153076-32c9-4a52-8e1b-fc9618153543
author: rothja
ms.author: jroth
ms.openlocfilehash: 4cc915cce0befccb5c5af58e703c11b750af855b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725787"
---
# <a name="srv_wsendmsg-extended-stored-procedure-api"></a><span data-ttu-id="077c9-102">srv_wsendmsg (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="077c9-102">srv_wsendmsg (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="077c9-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="077c9-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="077c9-104">Invia un messaggio Unicode al client.</span><span class="sxs-lookup"><span data-stu-id="077c9-104">Sends a Unicode message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="077c9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="077c9-105">Syntax</span></span>  
  
```  
  
int srv_wsendmsg(SRV_PROC *   
srvproc  
, int   
msgnum  
, int   
severity  
, WCHAR *   
message  
, int   
msglen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="077c9-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="077c9-106">Arguments</span></span>  
 <span data-ttu-id="077c9-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="077c9-107">*srvproc*</span></span>  
 <span data-ttu-id="077c9-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client.</span><span class="sxs-lookup"><span data-stu-id="077c9-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="077c9-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="077c9-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="077c9-110">*Msgnum*</span><span class="sxs-lookup"><span data-stu-id="077c9-110">*Msgnum*</span></span>  
 <span data-ttu-id="077c9-111">Numero di messaggio a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="077c9-111">Is a 4-byte message number.</span></span>  
  
 <span data-ttu-id="077c9-112">*Gravità*</span><span class="sxs-lookup"><span data-stu-id="077c9-112">*Severity*</span></span>  
 <span data-ttu-id="077c9-113">Specifica la gravità dell'errore.</span><span class="sxs-lookup"><span data-stu-id="077c9-113">Specifies the severity of the error.</span></span> <span data-ttu-id="077c9-114">Un livello di gravità minore o uguale a 10 è considerato un messaggio informativo; in caso contrario, è un errore.</span><span class="sxs-lookup"><span data-stu-id="077c9-114">A severity less than or equal to 10 is considered an informational message; otherwise, it is an error.</span></span>  
  
 <span data-ttu-id="077c9-115">*message*</span><span class="sxs-lookup"><span data-stu-id="077c9-115">*message*</span></span>  
 <span data-ttu-id="077c9-116">Puntatore alla stringa Unicode da inviare al client.</span><span class="sxs-lookup"><span data-stu-id="077c9-116">Is a pointer to a Unicode string to be sent to the client.</span></span>  
  
 <span data-ttu-id="077c9-117">*msglen*</span><span class="sxs-lookup"><span data-stu-id="077c9-117">*msglen*</span></span>  
 <span data-ttu-id="077c9-118">Specifica la lunghezza, espressa in caratteri, di *message*.</span><span class="sxs-lookup"><span data-stu-id="077c9-118">Specifies the length, in characters, of *message*.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="077c9-119">Restituisce</span><span class="sxs-lookup"><span data-stu-id="077c9-119">Returns</span></span>  
 <span data-ttu-id="077c9-120">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="077c9-120">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="077c9-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="077c9-121">Remarks</span></span>  
 <span data-ttu-id="077c9-122">Utilizzare questa funzione per inviare messaggi in Unicode.</span><span class="sxs-lookup"><span data-stu-id="077c9-122">Use this function to send messages in Unicode.</span></span> <span data-ttu-id="077c9-123">È simile a **srv_sendmsg**, ma il messaggio che invia è una stringa WCHAR anziché una stringa di tipo DBCHAR.</span><span class="sxs-lookup"><span data-stu-id="077c9-123">It is similar to **srv_sendmsg**, but the message it sends is a WCHAR string rather than type DBCHAR string.</span></span> <span data-ttu-id="077c9-124">Notare che la lunghezza del messaggio viene riportata in caratteri anziché in byte e che *msglen* non sarà mai uguale a SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="077c9-124">Note that message length is reported in characters rather than bytes, and *msglen* will never be equal to SRV_NULLTERM.</span></span>  
  
 <span data-ttu-id="077c9-125">La funzione restituisce FAIL quando:</span><span class="sxs-lookup"><span data-stu-id="077c9-125">The function returns FAIL when</span></span>  
  
-   <span data-ttu-id="077c9-126">Il valore *msglen* specificato non è incluso nell'intervallo 0-32242.</span><span class="sxs-lookup"><span data-stu-id="077c9-126">The *msglen* given is not in the range of 0-32242.</span></span>  
  
-   <span data-ttu-id="077c9-127">Il valore *msglen* specificato è 0 ma il puntatore del messaggio è NULL.</span><span class="sxs-lookup"><span data-stu-id="077c9-127">The *msglen* given is 0 but the message pointer is NULL.</span></span>  
  
-   <span data-ttu-id="077c9-128">Si verifica un errore durante l'invio del messaggio di errore tramite rete.</span><span class="sxs-lookup"><span data-stu-id="077c9-128">There is error when sending the error message through network.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="077c9-129">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="077c9-129">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="077c9-130">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="077c9-130">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="077c9-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="077c9-131">See Also</span></span>  
 [<span data-ttu-id="077c9-132">srv_sendmsg &#40;API Stored procedure estesa&#41;</span><span class="sxs-lookup"><span data-stu-id="077c9-132">srv_sendmsg &#40;Extended Stored Procedure API&#41;</span></span>](srv-sendmsg-extended-stored-procedure-api.md)  
  
  
