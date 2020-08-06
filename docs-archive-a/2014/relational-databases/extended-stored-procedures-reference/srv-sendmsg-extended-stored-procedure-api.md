---
title: srv_sendmsg (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_sendmsg
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_sendmsg
ms.assetid: efcb50b9-f8ff-4121-bf67-05830171b928
author: rothja
ms.author: jroth
ms.openlocfilehash: 0821ad88f48313cfadea634a489def9b242a49f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726915"
---
# <a name="srv_sendmsg-extended-stored-procedure-api"></a><span data-ttu-id="0b9ca-102">srv_sendmsg (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="0b9ca-102">srv_sendmsg (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="0b9ca-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="0b9ca-104">Invia un messaggio al client.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-104">Sends a message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b9ca-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b9ca-105">Syntax</span></span>  
  
```  
  
int srv_sendmsg (  
SRV_PROC *  
srvproc  
,  
int  
msgtype  
,  
DBINT  
msgnum  
,  
DBTINYINT  
class  
,   
DBTINYINT  
state  
,  
DBCHAR *  
rpcname  
,  
int   
rpcnamelen  
,  
DBUSMALLINT  
linenum  
,  
DBCHAR *  
message  
,  
int  
msglen   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="0b9ca-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0b9ca-106">Arguments</span></span>  
 <span data-ttu-id="0b9ca-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="0b9ca-107">*srvproc*</span></span>  
 <span data-ttu-id="0b9ca-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client, in questo caso l'handle che ha ricevuto la richiesta del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="0b9ca-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="0b9ca-110">*msgtype*</span><span class="sxs-lookup"><span data-stu-id="0b9ca-110">*msgtype*</span></span>  
 <span data-ttu-id="0b9ca-111">SRV_MSG_INFO o SRV_MSG_ERROR, a seconda che il server invii un messaggio informativo o un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-111">Is either SRV_MSG_INFO or SRV_MSG_ERROR, depending on whether the server is sending an informational or error message.</span></span>  
  
 <span data-ttu-id="0b9ca-112">*msgnum*</span><span class="sxs-lookup"><span data-stu-id="0b9ca-112">*msgnum*</span></span>  
 <span data-ttu-id="0b9ca-113">Numero di messaggio a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-113">Is a 4-byte message number.</span></span>  
  
 <span data-ttu-id="0b9ca-114">*class*</span><span class="sxs-lookup"><span data-stu-id="0b9ca-114">*class*</span></span>  
 <span data-ttu-id="0b9ca-115">Specifica la gravità dell'errore.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-115">Specifies the error severity.</span></span> <span data-ttu-id="0b9ca-116">Un livello di gravità minore o uguale a 10 è considerato un messaggio informativo.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-116">A severity less than or equal to 10 is considered an informational message.</span></span>  
  
 <span data-ttu-id="0b9ca-117">*state*</span><span class="sxs-lookup"><span data-stu-id="0b9ca-117">*state*</span></span>  
 <span data-ttu-id="0b9ca-118">Fornisce il numero di contesto dell'errore per il messaggio corrente.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-118">Provides the error state number for the current message.</span></span> <span data-ttu-id="0b9ca-119">Il numero di contesto dell'errore fornisce informazioni sul contesto dell'errore.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-119">The error state number provides information about the context of the error.</span></span> <span data-ttu-id="0b9ca-120">I numeri di contesto validi sono compresi tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-120">Valid state numbers are from 0 through 255.</span></span>  
  
 <span data-ttu-id="0b9ca-121">*rpcname*</span><span class="sxs-lookup"><span data-stu-id="0b9ca-121">*rpcname*</span></span>  
 <span data-ttu-id="0b9ca-122">Attualmente non supportato.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-122">Is currently not supported.</span></span>  
  
 <span data-ttu-id="0b9ca-123">*rpcnamelen*</span><span class="sxs-lookup"><span data-stu-id="0b9ca-123">*rpcnamelen*</span></span>  
 <span data-ttu-id="0b9ca-124">Attualmente non supportato.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-124">Is currently not supported.</span></span>  
  
 <span data-ttu-id="0b9ca-125">*linenum*</span><span class="sxs-lookup"><span data-stu-id="0b9ca-125">*linenum*</span></span>  
 <span data-ttu-id="0b9ca-126">Numero di riga nel batch di comandi del linguaggio a cui è applicato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-126">Is the line number in the language command batch where the message applies.</span></span> <span data-ttu-id="0b9ca-127">I numeri di riga partono da 1.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-127">Line numbers start at 1.</span></span> <span data-ttu-id="0b9ca-128">Se *linenum* non si applica al messaggio, viene impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-128">If *linenum* does not apply to the message, set to 0.</span></span>  
  
 <span data-ttu-id="0b9ca-129">*message*</span><span class="sxs-lookup"><span data-stu-id="0b9ca-129">*message*</span></span>  
 <span data-ttu-id="0b9ca-130">Puntatore alla stringa di caratteri da inviare al client.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-130">Is a pointer to the character string to be sent to the client.</span></span>  
  
 <span data-ttu-id="0b9ca-131">*msglen*</span><span class="sxs-lookup"><span data-stu-id="0b9ca-131">*msglen*</span></span>  
 <span data-ttu-id="0b9ca-132">Specifica la lunghezza, espressa in byte, di *message*.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-132">Specifies the length, in bytes, of *message*.</span></span> <span data-ttu-id="0b9ca-133">Se *message* è con terminazione Null, impostare *msglen* su SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-133">If *message* is null-terminated, set *msglen* to SRV_NULLTERM.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="0b9ca-134">Restituisce</span><span class="sxs-lookup"><span data-stu-id="0b9ca-134">Returns</span></span>  
 <span data-ttu-id="0b9ca-135">SUCCEED o FAIL</span><span class="sxs-lookup"><span data-stu-id="0b9ca-135">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b9ca-136">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0b9ca-136">Remarks</span></span>  
 <span data-ttu-id="0b9ca-137">Questa funzione invia messaggi informativi o di errore al client.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-137">This function sends error or informational messages to the client.</span></span> <span data-ttu-id="0b9ca-138">Viene chiamata una volta per ogni messaggio da inviare.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-138">It is called once for each message to be sent.</span></span>  
  
 <span data-ttu-id="0b9ca-139">I messaggi possono essere inviati al client con **srv_sendmsg** in qualsiasi ordine prima o dopo l'invio di tutte le righe, se presenti, con **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-139">Messages can be sent to the client with **srv_sendmsg** in any order before or after all rows (if any) have been sent with **srv_sendrow**.</span></span> <span data-ttu-id="0b9ca-140">Tutti i messaggi, se presenti, devono essere inviati al client prima dell'invio dello stato di completamento con **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-140">All messages, if any, must be sent to the client before the completion status is sent with **srv_senddone**.</span></span>  
  
 <span data-ttu-id="0b9ca-141">Per inviare i messaggi in Unicode, usare **srv_wsendmsg** anziché **srv_sendmsg**.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-141">To send messages in Unicode, use **srv_wsendmsg** rather than **srv_sendmsg**.</span></span>  
  
 <span data-ttu-id="0b9ca-142">Per altre informazioni, vedere [Dati Unicode e tabelle codici del server](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="0b9ca-142">For more information see [Unicode Data and Server Code Pages](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0b9ca-143">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="0b9ca-143">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="0b9ca-144">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="0b9ca-144">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
