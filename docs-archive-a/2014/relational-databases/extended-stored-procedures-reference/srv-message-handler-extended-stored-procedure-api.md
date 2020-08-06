---
title: srv_message_handler (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_message_handler
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_message_handler
ms.assetid: 41bcd057-436f-4fa8-8293-fc8057a30877
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e7b6472ed4fabb6dc2d545eb51a1e026635ce19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626101"
---
# <a name="srv_message_handler-extended-stored-procedure-api"></a><span data-ttu-id="d37f2-102">srv_message_handler (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="d37f2-102">srv_message_handler (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="d37f2-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="d37f2-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="d37f2-104">Chiama il gestore dei messaggi dell'API Stored procedure estesa installato.</span><span class="sxs-lookup"><span data-stu-id="d37f2-104">Calls the installed Extended Stored Procedure API message handler.</span></span> <span data-ttu-id="d37f2-105">Questa funzione viene in genere utilizzata per chiamare [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da un stored procedure esteso per registrare un errore (definito dalla stored procedure estesa) nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file di log degli errori o nel [!INCLUDE[msCoName](../../includes/msconame-md.md)] registro applicazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="d37f2-105">This function is usually used to call [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from an extended stored procedure to log an error (defined by the extended stored procedure) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log file or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d37f2-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d37f2-106">Syntax</span></span>  
  
```  
  
int srv_message_handler (  
SRV_PROC *  
srvproc  
,  
int  
errornum  
,  
BYTE   
severity  
,  
BYTE  
state  
,  
int  
oserrnum  
,  
char *  
errtext  
,  
int  
errtextlen  
,  
char *  
oserrtext  
,  
int  
oserrtextlen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d37f2-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d37f2-107">Arguments</span></span>  
 <span data-ttu-id="d37f2-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="d37f2-108">*srvproc*</span></span>  
 <span data-ttu-id="d37f2-109">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client.</span><span class="sxs-lookup"><span data-stu-id="d37f2-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="d37f2-110">Il parametro *srvproc* contiene informazioni usate per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="d37f2-110">The *srvproc* parameter contains information that is used to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="d37f2-111">*errornum*</span><span class="sxs-lookup"><span data-stu-id="d37f2-111">*errornum*</span></span>  
 <span data-ttu-id="d37f2-112">Numero dell'errore definito dalla stored procedure estesa.</span><span class="sxs-lookup"><span data-stu-id="d37f2-112">Is an error number defined by the extended stored procedure.</span></span> <span data-ttu-id="d37f2-113">Questo numero deve essere compreso tra 50.001 e 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="d37f2-113">This number must be from 50,001 through 2,147,483,647.</span></span>  
  
 <span data-ttu-id="d37f2-114">*severity*</span><span class="sxs-lookup"><span data-stu-id="d37f2-114">*severity*</span></span>  
 <span data-ttu-id="d37f2-115">Valore di gravità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] standard per l'errore.</span><span class="sxs-lookup"><span data-stu-id="d37f2-115">Is a standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] severity value for the error.</span></span> <span data-ttu-id="d37f2-116">Questo numero deve essere compreso tra 0 e 24.</span><span class="sxs-lookup"><span data-stu-id="d37f2-116">This number must be from 0 through 24.</span></span>  
  
 <span data-ttu-id="d37f2-117">*state*</span><span class="sxs-lookup"><span data-stu-id="d37f2-117">*state*</span></span>  
 <span data-ttu-id="d37f2-118">Valore di stato di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per l'errore.</span><span class="sxs-lookup"><span data-stu-id="d37f2-118">Is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] state value for the error.</span></span>  
  
 <span data-ttu-id="d37f2-119">*oserrnum*</span><span class="sxs-lookup"><span data-stu-id="d37f2-119">*oserrnum*</span></span>  
 <span data-ttu-id="d37f2-120">Numero dell'errore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d37f2-120">Is the operating-system error number.</span></span> <span data-ttu-id="d37f2-121">Questo argomento viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="d37f2-121">This argument is ignored.</span></span>  
  
 <span data-ttu-id="d37f2-122">*errtext*</span><span class="sxs-lookup"><span data-stu-id="d37f2-122">*errtext*</span></span>  
 <span data-ttu-id="d37f2-123">Descrizione dell'errore della stored procedure estesa *errornum*.</span><span class="sxs-lookup"><span data-stu-id="d37f2-123">Is the description of the extended stored procedure error *errornum*.</span></span>  
  
 <span data-ttu-id="d37f2-124">*errtextlen*</span><span class="sxs-lookup"><span data-stu-id="d37f2-124">*errtextlen*</span></span>  
 <span data-ttu-id="d37f2-125">Lunghezza della stringa dell'errore della stored procedure estesa *errtext*.</span><span class="sxs-lookup"><span data-stu-id="d37f2-125">Is the length of the extended stored procedure error string *errtext*.</span></span>  
  
 <span data-ttu-id="d37f2-126">*oserrtext*</span><span class="sxs-lookup"><span data-stu-id="d37f2-126">*oserrtext*</span></span>  
 <span data-ttu-id="d37f2-127">Descrizione dell'errore del sistema operativo *oserrnum*.</span><span class="sxs-lookup"><span data-stu-id="d37f2-127">Is the description of the operating-system error *oserrnum*.</span></span> <span data-ttu-id="d37f2-128">Questo argomento viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="d37f2-128">This argument is ignored.</span></span>  
  
 <span data-ttu-id="d37f2-129">*oserrtextlen*</span><span class="sxs-lookup"><span data-stu-id="d37f2-129">*oserrtextlen*</span></span>  
 <span data-ttu-id="d37f2-130">Lunghezza della stringa dell'errore del sistema operativo *oserrtext*.</span><span class="sxs-lookup"><span data-stu-id="d37f2-130">Is the length of the operating-system error string *oserrtext*.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d37f2-131">Restituisce</span><span class="sxs-lookup"><span data-stu-id="d37f2-131">Returns</span></span>  
 <span data-ttu-id="d37f2-132">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="d37f2-132">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d37f2-133">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d37f2-133">Remarks</span></span>  
 <span data-ttu-id="d37f2-134">La funzione **srv_message_handler** consente a una stored procedure estesa di integrarsi con le funzioni centralizzate di registrazione e report errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d37f2-134">The **srv_message_handler** function enables an extended stored procedure to integrate with the centralized error logging and reporting features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d37f2-135">Gli avvisi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono essere stabiliti per gli eventi dalle stored procedure estese e SQL Server Agent monitorerà queste condizioni di avviso.</span><span class="sxs-lookup"><span data-stu-id="d37f2-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerts can be established for events from extended stored procedures, and SQL Server Agent will monitor for these alert conditions.</span></span>  
  
 <span data-ttu-id="d37f2-136">Se il messaggio di errore è più lungo, viene troncato a 412 byte.</span><span class="sxs-lookup"><span data-stu-id="d37f2-136">If the error message is longer, it is truncated to 412 bytes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d37f2-137">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="d37f2-137">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="d37f2-138">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="d37f2-138">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
