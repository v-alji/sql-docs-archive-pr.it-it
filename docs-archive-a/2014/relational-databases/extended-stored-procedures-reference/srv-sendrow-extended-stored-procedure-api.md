---
title: srv_sendrow (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_sendrow
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_sendrow
ms.assetid: a08f608a-10e6-4bff-9b48-0d02e8026cdb
author: rothja
ms.author: jroth
ms.openlocfilehash: df40348b8792a70f84719abfb42152fda9487e6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726912"
---
# <a name="srv_sendrow-extended-stored-procedure-api"></a><span data-ttu-id="3c0b9-102">srv_convert (API delle stored procedure estese)</span><span class="sxs-lookup"><span data-stu-id="3c0b9-102">srv_sendrow (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="3c0b9-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="3c0b9-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="3c0b9-104">Trasmette una riga di dati al client.</span><span class="sxs-lookup"><span data-stu-id="3c0b9-104">Transmits a row of data to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c0b9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c0b9-105">Syntax</span></span>  
  
```  
  
int srv_sendrow ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="3c0b9-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3c0b9-106">Arguments</span></span>  
 <span data-ttu-id="3c0b9-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="3c0b9-107">*srvproc*</span></span>  
 <span data-ttu-id="3c0b9-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client, in questo caso l'handle che ha ricevuto la richiesta del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="3c0b9-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="3c0b9-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="3c0b9-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="3c0b9-110">Restituisce</span><span class="sxs-lookup"><span data-stu-id="3c0b9-110">Returns</span></span>  
 <span data-ttu-id="3c0b9-111">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="3c0b9-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c0b9-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3c0b9-112">Remarks</span></span>  
 <span data-ttu-id="3c0b9-113">La funzione **srv_sendrow** viene chiamata una volta per ogni riga inviata al client.</span><span class="sxs-lookup"><span data-stu-id="3c0b9-113">The **srv_sendrow** function is called once for each row sent to the client.</span></span> <span data-ttu-id="3c0b9-114">Tutte le righe devono essere inviate al client prima che qualsiasi messaggio, valore di stato o stato di completamento venga inviato con **srv_sendmsg**, **srv_status** o **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="3c0b9-114">All rows must be sent to the client before any messages, status values, or completion statuses are sent with **srv_sendmsg**, **srv_status**, or **srv_senddone**.</span></span>  
  
 <span data-ttu-id="3c0b9-115">L'invio di una riga le cui colonne non sono state definite tutte con **srv_describe** fa sì che l'applicazione dell'API Stored procedure estesa generi un messaggio di errore informativo e restituisca FAIL al client.</span><span class="sxs-lookup"><span data-stu-id="3c0b9-115">Sending a row that has not had all its columns defined with **srv_describe** causes the Extended Stored Procedure API application to raise an informational error message and return FAIL to the client.</span></span> <span data-ttu-id="3c0b9-116">In questo caso, la riga non viene inviata.</span><span class="sxs-lookup"><span data-stu-id="3c0b9-116">In this case, the row is not sent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3c0b9-117">L'API delle stored procedure estese non supporta l'invio di righe di calcolo al client.</span><span class="sxs-lookup"><span data-stu-id="3c0b9-117">The Extended Stored Procedure API does not support sending compute rows to the client.</span></span> <span data-ttu-id="3c0b9-118">Se, inoltre, una riga che contiene dati `ntext`, `text` o `image` viene inviata al client, il puntatore di testo e il timestamp di testo non vengono inclusi.</span><span class="sxs-lookup"><span data-stu-id="3c0b9-118">Also, if a row containing `ntext`, `text`, or `image` data is sent to the client, the text pointer and text timestamp are not included.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3c0b9-119">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="3c0b9-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="3c0b9-120">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="3c0b9-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c0b9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c0b9-121">See Also</span></span>  
 [<span data-ttu-id="3c0b9-122">srv_describe &#40;API Stored procedure estesa&#41;</span><span class="sxs-lookup"><span data-stu-id="3c0b9-122">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
