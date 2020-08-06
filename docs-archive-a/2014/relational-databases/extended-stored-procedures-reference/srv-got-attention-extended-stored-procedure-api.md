---
title: srv_got_attention (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_got_attention
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_got_attention
ms.assetid: 805e68e1-d17f-41bd-8b9f-a27283bb6fbe
author: rothja
ms.author: jroth
ms.openlocfilehash: bb5432e2f5e259187e506237842fbb9110e27a69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725820"
---
# <a name="srv_got_attention-extended-stored-procedure-api"></a><span data-ttu-id="ab3ae-102">srv_got_attention (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="ab3ae-102">srv_got_attention (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="ab3ae-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="ab3ae-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="ab3ae-104">Controlla se l'attività o la connessione corrente deve essere interrotta e restituisce TRUE se la connessione viene terminata o il batch interrotto</span><span class="sxs-lookup"><span data-stu-id="ab3ae-104">Checks whether the current connection or task needs to be aborted and returns TRUE if the connection is killed or the batch is aborted</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab3ae-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab3ae-105">Syntax</span></span>  
  
```  
  
BOOL srv_got_attention  
(SRV_PROC *  
srvproc  
);  
  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab3ae-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ab3ae-106">Parameters</span></span>  
 <span data-ttu-id="ab3ae-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="ab3ae-107">*srvproc*</span></span>  
 <span data-ttu-id="ab3ae-108">Puntatore che identifica una connessione al database.</span><span class="sxs-lookup"><span data-stu-id="ab3ae-108">Pointer identifying a database connection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab3ae-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ab3ae-109">Return Value</span></span>  
 <span data-ttu-id="ab3ae-110">TRUE se la connessione viene terminata o il batch interrotto.</span><span class="sxs-lookup"><span data-stu-id="ab3ae-110">TRUE if the connection is killed or the batch is aborted.</span></span> <span data-ttu-id="ab3ae-111">FALSE se la connessione o il batch è attivo.</span><span class="sxs-lookup"><span data-stu-id="ab3ae-111">FALSE if the connection or batch is active.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab3ae-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ab3ae-112">Remarks</span></span>  
 <span data-ttu-id="ab3ae-113">Una stored procedure estesa con esecuzione prolungata deve controllare l'attenzione del server chiamando periodicamente **srv_got_attention** in modo che la procedura possa terminare se stessa se la connessione viene terminata o il batch viene interrotto.</span><span class="sxs-lookup"><span data-stu-id="ab3ae-113">A long-running extended stored procedure should check the server attention by calling **srv_got_attention** periodically so that the procedure may terminate itself when the connection is killed or the batch is aborted.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ab3ae-114">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="ab3ae-114">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="ab3ae-115">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="ab3ae-115">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
