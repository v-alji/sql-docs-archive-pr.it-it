---
title: srv_getbindtoken (API delle stored procedure estese) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_getbindtoken
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_getbindtoken
ms.assetid: c947d011-08ac-4fb8-b925-3da6e0999277
author: rothja
ms.author: jroth
ms.openlocfilehash: d42f95c8a7df87f20ebaa30501b96b5f2a00815a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637320"
---
# <a name="srv_getbindtoken-extended-stored-procedure-api"></a><span data-ttu-id="37819-102">srv_getbindtoken (API delle stored procedure estese)</span><span class="sxs-lookup"><span data-stu-id="37819-102">srv_getbindtoken (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="37819-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="37819-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="37819-104">Ottiene un token di associazione della transazione nella sessione client corrente che richiama la stored procedure estesa.</span><span class="sxs-lookup"><span data-stu-id="37819-104">Obtains a bind token of the transaction in the current client session that invokes the extended stored procedure.</span></span>  
  
 <span data-ttu-id="37819-105">La stored procedure estesa può quindi usare **sp_bindsession** per associare qualsiasi nuova sessione creata sullo stesso server alla transazione esistente in modo che la nuova sessione possa condividere lo stesso spazio di blocco della transazione con la sessione client che ha richiamato la stored procedure estesa.</span><span class="sxs-lookup"><span data-stu-id="37819-105">The extended stored procedure can then use **sp_bindsession** to bind any new session it creates against the same server to the existing transaction so that the new session can share the same transaction lock space with the client session that invoked the extended stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37819-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37819-106">Syntax</span></span>  
  
```  
  
int srv_getbindtoken (  
SRV_PROC*  
srvproc  
,  
char*  
bindtoken  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="37819-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="37819-107">Arguments</span></span>  
 <span data-ttu-id="37819-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="37819-108">*srvproc*</span></span>  
 <span data-ttu-id="37819-109">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client.</span><span class="sxs-lookup"><span data-stu-id="37819-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="37819-110">La struttura contiene tutte le informazioni utilizzate dalla libreria dell'API della stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="37819-110">The structure contains all the information that the Extended Stored Procedure API library uses to manage communications and data between the application and the client.</span></span>  
  
 <span data-ttu-id="37819-111">*bindtoken*</span><span class="sxs-lookup"><span data-stu-id="37819-111">*bindtoken*</span></span>  
 <span data-ttu-id="37819-112">Puntatore a un buffer in cui verrà copiato il token di associazione.</span><span class="sxs-lookup"><span data-stu-id="37819-112">Is a pointer to a buffer where the bind token will be copied.</span></span> <span data-ttu-id="37819-113">Il token di associazione viene rappresentato come stringa con terminazioni Null.</span><span class="sxs-lookup"><span data-stu-id="37819-113">The bind token is represented as a null-terminated string.</span></span> <span data-ttu-id="37819-114">Il buffer specificato deve essere lungo almeno 255 byte.</span><span class="sxs-lookup"><span data-stu-id="37819-114">The buffer you specify should be at least 255 bytes in length.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="37819-115">Restituisce</span><span class="sxs-lookup"><span data-stu-id="37819-115">Returns</span></span>  
 <span data-ttu-id="37819-116">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="37819-116">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37819-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="37819-117">Remarks</span></span>  
  
### <a name="to-bind-an-extended-stored-procedure-session-to-the-client-session-that-called-it-so-they-share-the-same-transaction-lock-space"></a><span data-ttu-id="37819-118">Per associare una sessione della stored procedure estesa alla sessione client che l'ha chiamata perché condividano lo stesso spazio di blocco della transazione</span><span class="sxs-lookup"><span data-stu-id="37819-118">To bind an extended stored procedure session to the client session that called it so they share the same transaction lock space</span></span>  
  
1.  <span data-ttu-id="37819-119">La stored procedure estesa chiama **svr_getbindtoken** per ottenere il token di associazione per la transazione corrente nella sessione.</span><span class="sxs-lookup"><span data-stu-id="37819-119">The extended stored procedure calls **svr_getbindtoken** to get the bind token for the current transaction in the session.</span></span> <span data-ttu-id="37819-120">Il token viene restituito nel parametro *bindtoken* specificato.</span><span class="sxs-lookup"><span data-stu-id="37819-120">The token is returned in the given *bindtoken* parameter.</span></span>  
  
2.  <span data-ttu-id="37819-121">La stored procedure estesa apre nuove sessioni sullo stesso server.</span><span class="sxs-lookup"><span data-stu-id="37819-121">The extended stored procedure opens new session(s) against the same server.</span></span> <span data-ttu-id="37819-122">Nella sessione la stored procedure estesa usa il token di associazione con **sp_bindsession** per associare la nuova sessione alla stessa transazione.</span><span class="sxs-lookup"><span data-stu-id="37819-122">Inside that session, the extended stored procedure uses the bind token with **sp_bindsession** to bind the new session to the same transaction.</span></span> <span data-ttu-id="37819-123">La stored procedure estesa può creare più sessioni e può associare tutte le sessioni alla stessa transazione.</span><span class="sxs-lookup"><span data-stu-id="37819-123">The extended stored procedure can create multiple sessions and bind all the sessions to the same transaction.</span></span>  
  
3.  <span data-ttu-id="37819-124">L'associazione di una sessione viene annullata quando viene restituita la stored procedure esterna o quando **sp_bindsession** viene chiamata con una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="37819-124">A bound session is unbound when the external stored procedure returns or when **sp_bindsession** is called with an empty string.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="37819-125">A una connessione condivisa può accedere solo una sessione associata per volta.</span><span class="sxs-lookup"><span data-stu-id="37819-125">Only one bound session at a time can have access to a shared connection.</span></span> <span data-ttu-id="37819-126">Se una sessione esegue un'istruzione nel server o è in attesa di risultati dal server, nessun'altra sessione che condivide la stessa connessione associata può accedere al server fino a quando la sessione corrente non completa l'esecuzione dell'istruzione corrente.</span><span class="sxs-lookup"><span data-stu-id="37819-126">If one session is currently executing a statement at the server or has results pending from the server, no other sessions sharing the same bound connection can gain access to the server until the current session has finished executing the current statement.</span></span> <span data-ttu-id="37819-127">Se una sessione tenta di accedere alla connessione mentre il server è occupato, nella sessione in conflitto viene restituito un errore che indica che la connessione è in uso e che la sessione dovrà eseguire un nuovo tentativo in seguito.</span><span class="sxs-lookup"><span data-stu-id="37819-127">If a session attempts to gain access to the connection while the server is busy, an error is returned to the conflicting session indicating the connection is in use and the session should retry later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="37819-128">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="37819-128">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="37819-129">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="37819-129">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37819-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37819-130">See Also</span></span>  
 <span data-ttu-id="37819-131">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="37819-131">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span></span>  
 [<span data-ttu-id="37819-132">sp_getbindtoken &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="37819-132">sp_getbindtoken &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql)  
  
  
