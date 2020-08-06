---
title: srv_paraminfo (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paraminfo
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paraminfo
ms.assetid: ee2afd4e-0d91-462b-9403-98d481546330
author: rothja
ms.author: jroth
ms.openlocfilehash: cc3d51acc2ca560246c46267840db72934223999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725819"
---
# <a name="srv_paraminfo-extended-stored-procedure-api"></a><span data-ttu-id="646f1-102">srv_paraminfo (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="646f1-102">srv_paraminfo (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="646f1-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="646f1-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="646f1-104">Restituisce informazioni su un parametro.</span><span class="sxs-lookup"><span data-stu-id="646f1-104">Returns information about a parameter.</span></span> <span data-ttu-id="646f1-105">Questa funzione sostituisce le funzioni seguenti: [srv_paramtype](srv-paramtype-extended-stored-procedure-api.md), [srv_paramlen](srv-paramlen-extended-stored-procedure-api.md), [srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md) e [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="646f1-105">This function supersedes the following functions: [srv_paramtype](srv-paramtype-extended-stored-procedure-api.md), [srv_paramlen](srv-paramlen-extended-stored-procedure-api.md), [srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md), and [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md).</span></span> <span data-ttu-id="646f1-106">**srv_paraminfo** supporta i tipi di dati in [Tipi di dati](data-types-extended-stored-procedure-api.md) e i dati di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="646f1-106">**srv_paraminfo** supports the data types in [Data Types](data-types-extended-stored-procedure-api.md) and zero-length data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="646f1-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="646f1-107">Syntax</span></span>  
  
```  
  
int srv_paraminfo (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbType  
,  
ULONG *  
pcbMaxLen  
,  
ULONG *  
pcbActualLen  
,  
BYTE *  
pbData  
,  
BOOL *  
pfNull  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="646f1-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="646f1-108">Arguments</span></span>  
 <span data-ttu-id="646f1-109">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="646f1-109">*srvproc*</span></span>  
 <span data-ttu-id="646f1-110">Handle per una connessione client.</span><span class="sxs-lookup"><span data-stu-id="646f1-110">A handle for a client connection.</span></span>  
  
 <span data-ttu-id="646f1-111">*n*</span><span class="sxs-lookup"><span data-stu-id="646f1-111">*n*</span></span>  
 <span data-ttu-id="646f1-112">Numero ordinale del parametro da impostare.</span><span class="sxs-lookup"><span data-stu-id="646f1-112">The ordinal number of the parameter to be set.</span></span> <span data-ttu-id="646f1-113">Il primo parametro è 1.</span><span class="sxs-lookup"><span data-stu-id="646f1-113">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="646f1-114">*pbType*</span><span class="sxs-lookup"><span data-stu-id="646f1-114">*pbType*</span></span>  
 <span data-ttu-id="646f1-115">Tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="646f1-115">The data type of the parameter.</span></span>  
  
 <span data-ttu-id="646f1-116">*pcbMaxLen*</span><span class="sxs-lookup"><span data-stu-id="646f1-116">*pcbMaxLen*</span></span>  
 <span data-ttu-id="646f1-117">Indicatore di misura relativo alla lunghezza massima del parametro.</span><span class="sxs-lookup"><span data-stu-id="646f1-117">Pointer to the maximum length of the parameter.</span></span>  
  
 <span data-ttu-id="646f1-118">*pcbActualLen*</span><span class="sxs-lookup"><span data-stu-id="646f1-118">*pcbActualLen*</span></span>  
 <span data-ttu-id="646f1-119">Indicatore di misura relativo alla lunghezza effettiva del parametro.</span><span class="sxs-lookup"><span data-stu-id="646f1-119">Pointer to the actual length of the parameter.</span></span> <span data-ttu-id="646f1-120">Il valore 0 (\**pcbActualLen* == 0) indica dati di lunghezza zero se \**pfNull* è impostato su FALSE.</span><span class="sxs-lookup"><span data-stu-id="646f1-120">A value of 0 (\**pcbActualLen* == 0) signifies zero-length data if \**pfNull* is set to FALSE.</span></span>  
  
 <span data-ttu-id="646f1-121">*pbData*</span><span class="sxs-lookup"><span data-stu-id="646f1-121">*pbData*</span></span>  
 <span data-ttu-id="646f1-122">Puntatore al buffer per i dati di parametro.</span><span class="sxs-lookup"><span data-stu-id="646f1-122">Pointer to the buffer for parameter data.</span></span> <span data-ttu-id="646f1-123">Se *pbData* non è NULL, l'API Stored procedure estesa scrive \**pcbActualLen* byte di dati in \**pbData*.</span><span class="sxs-lookup"><span data-stu-id="646f1-123">If *pbData* is not NULL, the Extended Store Procedure API writes \**pcbActualLen* bytes of data to \**pbData*.</span></span> <span data-ttu-id="646f1-124">Se *pbData* è NULL, non viene scritto alcun dato in \**pbData* ma la funzione restituisce \**pbType*, \**pcbMaxLen*, \**pcbActualLen* e \**pfNull*.</span><span class="sxs-lookup"><span data-stu-id="646f1-124">If *pbData* is NULL, no data is written to \**pbData* but the function returns \**pbType*, \**pcbMaxLen*, \**pcbActualLen*, and \**pfNull*.</span></span> <span data-ttu-id="646f1-125">La memoria per questo buffer deve essere gestita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="646f1-125">The memory for this buffer must be managed by the application.</span></span>  
  
 <span data-ttu-id="646f1-126">*pfNull*</span><span class="sxs-lookup"><span data-stu-id="646f1-126">*pfNull*</span></span>  
 <span data-ttu-id="646f1-127">Puntatore a un flag null.</span><span class="sxs-lookup"><span data-stu-id="646f1-127">Pointer to a null flag.</span></span><span data-ttu-id="646f1-128">\ **pfNull* viene impostato su TRUE se il valore del parametro è NULL.</span><span class="sxs-lookup"><span data-stu-id="646f1-128">\ **pfNull* is set to TRUE if the value of the parameter is NULL.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="646f1-129">Restituisce</span><span class="sxs-lookup"><span data-stu-id="646f1-129">Returns</span></span>  
 <span data-ttu-id="646f1-130">Se le informazioni sul parametro vengono ottenute correttamente, viene restituito SUCCEED; in caso contrario, FAIL.</span><span class="sxs-lookup"><span data-stu-id="646f1-130">If the parameter information was successfully obtained, SUCCEED is returned; otherwise, FAIL.</span></span> <span data-ttu-id="646f1-131">Restituisce FAIL se non esiste una stored procedure remota corrente o se non è presente nessun parametro *n* della stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="646f1-131">FAIL is returned when there is no current remote stored procedure and when there is no *n*th remote stored procedure parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="646f1-132">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="646f1-132">Remarks</span></span>  
 <span data-ttu-id="646f1-133">**Nota sulla sicurezza** È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="646f1-133">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="646f1-134">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="646f1-134">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="646f1-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="646f1-135">See Also</span></span>  
 [<span data-ttu-id="646f1-136">Guida di riferimento per i programmatori delle stored procedure estese</span><span class="sxs-lookup"><span data-stu-id="646f1-136">Extended Stored Procedures Programmer's Reference</span></span>](database-engine-extended-stored-procedures-reference.md)  
  
  
