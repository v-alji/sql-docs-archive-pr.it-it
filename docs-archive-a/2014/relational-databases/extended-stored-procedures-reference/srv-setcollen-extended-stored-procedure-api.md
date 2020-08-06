---
title: srv_setcollen (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setcollen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setcollen
ms.assetid: 3c60f1c3-4562-463a-a259-12df172788bd
author: rothja
ms.author: jroth
ms.openlocfilehash: 8e3023e2ac239e074656329da7d8af3aba3afa88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714364"
---
# <a name="srv_setcollen-extended-stored-procedure-api"></a><span data-ttu-id="07ae2-102">srv_setcollen (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="07ae2-102">srv_setcollen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="07ae2-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="07ae2-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="07ae2-104">Specifica la lunghezza in byte della data corrente di una colonna a lunghezza variabile o di una colonna che consente valori Null.</span><span class="sxs-lookup"><span data-stu-id="07ae2-104">Specifies the current data length in bytes of a variable-length column or a column that allows NULL values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07ae2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07ae2-105">Syntax</span></span>  
  
```  
  
int srv_setcollen (  
SRV_PROC *  
srvproc  
,  
int   
column  
,  
int  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="07ae2-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="07ae2-106">Arguments</span></span>  
 <span data-ttu-id="07ae2-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="07ae2-107">*srvproc*</span></span>  
 <span data-ttu-id="07ae2-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client.</span><span class="sxs-lookup"><span data-stu-id="07ae2-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="07ae2-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="07ae2-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="07ae2-110">*column*</span><span class="sxs-lookup"><span data-stu-id="07ae2-110">*column*</span></span>  
 <span data-ttu-id="07ae2-111">Indica il numero della colonna per la quale viene specificata la lunghezza dei dati.</span><span class="sxs-lookup"><span data-stu-id="07ae2-111">Indicates the number of the column for which the data length is being specified.</span></span> <span data-ttu-id="07ae2-112">Le colonne sono numerate a partire da 1.</span><span class="sxs-lookup"><span data-stu-id="07ae2-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="07ae2-113">*Len*</span><span class="sxs-lookup"><span data-stu-id="07ae2-113">*len*</span></span>  
 <span data-ttu-id="07ae2-114">Indica la lunghezza in byte dei dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="07ae2-114">Indicates the length, in bytes, of the column data.</span></span> <span data-ttu-id="07ae2-115">Alla lunghezza 0 corrisponde un valore Null per i dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="07ae2-115">A length of 0 means the column data value is null.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="07ae2-116">Restituisce</span><span class="sxs-lookup"><span data-stu-id="07ae2-116">Returns</span></span>  
 <span data-ttu-id="07ae2-117">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="07ae2-117">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07ae2-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="07ae2-118">Remarks</span></span>  
 <span data-ttu-id="07ae2-119">Ogni colonna della riga deve essere definita prima con **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="07ae2-119">Each column of the row must first be defined with **srv_describe**.</span></span> <span data-ttu-id="07ae2-120">La lunghezza della colonna dei dati viene impostata dall'ultima chiamata a **srv_describe** o **srv_setcollen**.</span><span class="sxs-lookup"><span data-stu-id="07ae2-120">The column data length is set by the last call to **srv_describe** or **srv_setcollen**.</span></span> <span data-ttu-id="07ae2-121">Se viene modificata una riga dei dati a lunghezza variabile (dati con terminazione null), è necessario usare **srv_setcollen** per impostarli sulla nuova lunghezza prima di chiamare **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="07ae2-121">If variable-length data (null-terminated data) changes for a row, **srv_setcollen** must be used to set it to the new length before calling **srv_sendrow**.</span></span> <span data-ttu-id="07ae2-122">Per una colonna che consente valori Null è necessario che sia stato chiamato **srv_describe** con *desttype* impostato su un tipo di dati che consente valori Null (ad esempio SRVINTN) e che i dati Null siano stati specificati chiamando **srv_setcollen** con *len* impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="07ae2-122">For a column that allows null values, **srv_describe** must have been called with *desttype* set to a data type that allows nulls (like SRVINTN) and null data is specified by calling **srv_setcollen** with *len* set to 0.</span></span> <span data-ttu-id="07ae2-123">Quando si utilizza l'API Stored procedure estesa, non è possibile specificare dati di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="07ae2-123">Zero length data cannot be specified using the Extended Stored Procedure API.</span></span>  
  
 <span data-ttu-id="07ae2-124">Quando il tipo di dati della colonna è a lunghezza variabile, *len* non viene controllato.</span><span class="sxs-lookup"><span data-stu-id="07ae2-124">Note that when the data type of the column is variable-length, *len* is not checked.</span></span> <span data-ttu-id="07ae2-125">Questa funzione restituisce FAIL se chiamata per una colonna a lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="07ae2-125">This function returns FAIL if called for a fixed-length column.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="07ae2-126">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="07ae2-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="07ae2-127">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="07ae2-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ae2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07ae2-128">See Also</span></span>  
 [<span data-ttu-id="07ae2-129">srv_describe &#40;API Stored procedure estesa&#41;</span><span class="sxs-lookup"><span data-stu-id="07ae2-129">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
