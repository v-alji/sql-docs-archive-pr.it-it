---
title: srv_setcoldata (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setcoldata
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setcoldata
ms.assetid: 2e19205a-25ca-4d4a-916b-d591cf2c892b
author: rothja
ms.author: jroth
ms.openlocfilehash: b67aa2f7b5a37057d2ed87846689919d84ec4aaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723887"
---
# <a name="srv_setcoldata-extended-stored-procedure-api"></a><span data-ttu-id="c557c-102">srv_setcoldata (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="c557c-102">srv_setcoldata (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="c557c-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="c557c-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="c557c-104">Specifica l'indirizzo corrente per i dati di una colonna.</span><span class="sxs-lookup"><span data-stu-id="c557c-104">Specifies the current address for a column's data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c557c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c557c-105">Syntax</span></span>  
  
```  
  
int srv_setcoldata (  
SRV_PROC *  
srvproc  
,  
int   
column  
,  
void *  
data   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c557c-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c557c-106">Arguments</span></span>  
 <span data-ttu-id="c557c-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="c557c-107">*srvproc*</span></span>  
 <span data-ttu-id="c557c-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client.</span><span class="sxs-lookup"><span data-stu-id="c557c-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="c557c-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="c557c-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="c557c-110">*column*</span><span class="sxs-lookup"><span data-stu-id="c557c-110">*column*</span></span>  
 <span data-ttu-id="c557c-111">Indica il numero della colonna per il quale viene specificato l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="c557c-111">Indicates the number of the column the address is being specified for.</span></span> <span data-ttu-id="c557c-112">Le colonne sono numerate a partire da 1.</span><span class="sxs-lookup"><span data-stu-id="c557c-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="c557c-113">*data*</span><span class="sxs-lookup"><span data-stu-id="c557c-113">*data*</span></span>  
 <span data-ttu-id="c557c-114">Indicatore di misura per i dati di una colonna.</span><span class="sxs-lookup"><span data-stu-id="c557c-114">Is a pointer for a column's data.</span></span> <span data-ttu-id="c557c-115">La memoria allocata per *data* non deve essere liberata fino a quando i dati della colonna non vengono sostituiti da un'altra chiamata a **srv_setcoldata** o fino alla chiamata a **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="c557c-115">Memory allocated for *data* should not be freed until the column data is replaced by another call to **srv_setcoldata**, or until **srv_senddone** is called.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c557c-116">Restituisce</span><span class="sxs-lookup"><span data-stu-id="c557c-116">Returns</span></span>  
 <span data-ttu-id="c557c-117">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="c557c-117">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c557c-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c557c-118">Remarks</span></span>  
 <span data-ttu-id="c557c-119">Ogni colonna della riga deve essere definita prima con **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="c557c-119">Each column of the row must be defined first with **srv_describe**.</span></span> <span data-ttu-id="c557c-120">Gli indirizzi dei dati della colonna sono impostati inizialmente con **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="c557c-120">Column data addresses are initially set with **srv_describe**.</span></span> <span data-ttu-id="c557c-121">Se l'indirizzo dei dati della colonna cambia, è necessario chiamare **srv_setcoldata** per specificare il nuovo indirizzo dei dati e quindi **srv_setcoldata** separatamente per ogni colonna modificata.</span><span class="sxs-lookup"><span data-stu-id="c557c-121">If the address of the column data changes, **srv_setcoldata** must be called to specify the new address of the data and **srv_setcoldata** must be called separately for each changed column.</span></span>  
  
 <span data-ttu-id="c557c-122">I dati Null vengono rappresentati impostando la lunghezza della colonna su 0 con **srv_setcollen**.</span><span class="sxs-lookup"><span data-stu-id="c557c-122">Null data is represented by setting the column's length to 0 with **srv_setcollen**.</span></span> <span data-ttu-id="c557c-123">L'indirizzo dei dati viene quindi ignorato.</span><span class="sxs-lookup"><span data-stu-id="c557c-123">The data address is then ignored.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c557c-124">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="c557c-124">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="c557c-125">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="c557c-125">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c557c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c557c-126">See Also</span></span>  
 [<span data-ttu-id="c557c-127">srv_describe &#40;API Stored procedure estesa&#41;</span><span class="sxs-lookup"><span data-stu-id="c557c-127">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
