---
title: srv_describe (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_describe
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_describe
ms.assetid: 2115600e-5ce7-4be0-9cd3-a1dd1fab0729
author: rothja
ms.author: jroth
ms.openlocfilehash: 52a397b79f4fcecaa2ccacde7500cb852ae793fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637321"
---
# <a name="srv_describe-extended-stored-procedure-api"></a><span data-ttu-id="ab5f3-102">srv_describe (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="ab5f3-102">srv_describe (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="ab5f3-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="ab5f3-104">Definisce il nome della colonna e i tipi di dati di origine e di destinazione per una colonna specifica in una riga.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-104">Defines the column name and source and destination data types for a specific column in a row.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab5f3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab5f3-105">Syntax</span></span>  
  
```  
  
int srv_describe (  
SRV_PROC *  
srvproc  
,  
int  
colnumber  
,  
DBCHAR *  
column_name  
,  
int  
namelen  
,  
DBINT  
desttype  
,  
DBINT  
destlen  
,  
DBINT  
srctype  
,  
DBINT  
srclen  
,  
void *  
srcdata  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="ab5f3-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ab5f3-106">Arguments</span></span>  
 <span data-ttu-id="ab5f3-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="ab5f3-107">*srvproc*</span></span>  
 <span data-ttu-id="ab5f3-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client, in questo caso il client che invia la riga.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the client sending the row).</span></span> <span data-ttu-id="ab5f3-109">La struttura contiene tutte le informazioni utilizzate dalla libreria dell'API della stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-109">The structure contains all the information that the Extended Stored Procedure API library uses to manage communications and data between the application and the client.</span></span>  
  
 <span data-ttu-id="ab5f3-110">*colnumber*</span><span class="sxs-lookup"><span data-stu-id="ab5f3-110">*colnumber*</span></span>  
 <span data-ttu-id="ab5f3-111">Attualmente non supportato.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-111">Is currently not supported.</span></span> <span data-ttu-id="ab5f3-112">Le colonne devono essere descritte in ordine.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-112">Columns must be described in order.</span></span> <span data-ttu-id="ab5f3-113">Tutte le colonne devono essere descritte prima che venga chiamata **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-113">All columns must be described before **srv_sendrow** is called.</span></span>  
  
 <span data-ttu-id="ab5f3-114">*column_name*</span><span class="sxs-lookup"><span data-stu-id="ab5f3-114">*column_name*</span></span>  
 <span data-ttu-id="ab5f3-115">Specifica il nome della colonna a cui appartengono i dati.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-115">Specifies the name of the column to which the data belongs.</span></span> <span data-ttu-id="ab5f3-116">Questo parametro può essere NULL in quanto una colonna non deve necessariamente avere un nome.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-116">This parameter can be NULL because a column is not required to have a name.</span></span>  
  
 <span data-ttu-id="ab5f3-117">*namelen*</span><span class="sxs-lookup"><span data-stu-id="ab5f3-117">*namelen*</span></span>  
 <span data-ttu-id="ab5f3-118">Specifica la lunghezza, espressa in byte, di *column_name*.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-118">Specifies the length, in bytes, of *column_name*.</span></span> <span data-ttu-id="ab5f3-119">Se *namelen* è SRV_NULLTERM, *column_name* deve essere con terminazione Null.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-119">If *namelen* is SRV_NULLTERM, then *column_name* must be null-terminated.</span></span>  
  
 <span data-ttu-id="ab5f3-120">*desttype*</span><span class="sxs-lookup"><span data-stu-id="ab5f3-120">*desttype*</span></span>  
 <span data-ttu-id="ab5f3-121">Specifica il tipo di dati della colonna della riga di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-121">Specifies the data type of the destination row column.</span></span> <span data-ttu-id="ab5f3-122">Si tratta del tipo di dati inviato al client.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-122">This is the data type sent to the client.</span></span> <span data-ttu-id="ab5f3-123">È necessario specificarlo anche se i dati sono NULL. Per altre informazioni, vedere [Tipi di dati &#40;API Stored procedure estesa&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="ab5f3-123">The data type must be specified even if the data is NULL, for more information, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="ab5f3-124">*destlen*</span><span class="sxs-lookup"><span data-stu-id="ab5f3-124">*destlen*</span></span>  
 <span data-ttu-id="ab5f3-125">Specifica la lunghezza, espressa in byte, dei dati da inviare al client.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-125">Specifies the length, in bytes, of the data to be sent to the client.</span></span> <span data-ttu-id="ab5f3-126">Per tipi di dati a lunghezza fissa che non consentono i valori Null, *destlen* viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-126">For fixed-length data types that do not allow null values, *destlen* is ignored.</span></span> <span data-ttu-id="ab5f3-127">Per tipi di dati a lunghezza variabile e a lunghezza fissa che consentono i valori Null, *destlen* specifica la lunghezza massima dei dati di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-127">For variable-length data types and fixed-length data types that allow null values, *destlen* specifies the maximum length the destination data can be.</span></span>  
  
 <span data-ttu-id="ab5f3-128">*srctype*</span><span class="sxs-lookup"><span data-stu-id="ab5f3-128">*srctype*</span></span>  
 <span data-ttu-id="ab5f3-129">Specifica il tipo di dati dei dati di origine.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-129">Specifies the data type of the source data.</span></span>  
  
 <span data-ttu-id="ab5f3-130">*srclen*</span><span class="sxs-lookup"><span data-stu-id="ab5f3-130">*srclen*</span></span>  
 <span data-ttu-id="ab5f3-131">Specifica la lunghezza, espressa in byte, dei dati di origine.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-131">Specifies the length, in bytes, of the source data.</span></span> <span data-ttu-id="ab5f3-132">Questo valore viene ignorato per i tipi di dati a lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-132">This value is ignored for fixed-length data types.</span></span>  
  
 <span data-ttu-id="ab5f3-133">*srcdata*</span><span class="sxs-lookup"><span data-stu-id="ab5f3-133">*srcdata*</span></span>  
 <span data-ttu-id="ab5f3-134">Fornisce l'indirizzo dei dati di origine per una determinata colonna.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-134">Provides the source data address for a particular column.</span></span> <span data-ttu-id="ab5f3-135">Dopo essere stata chiamata, **srv_sendrow** cerca i dati di *colnumber* in *srcdata*.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-135">When **srv_sendrow** is called, it looks for the data for *colnumber* at *srcdata*.</span></span> <span data-ttu-id="ab5f3-136">È necessario quindi non liberarlo prima di una chiamata a **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-136">Therefore it should not be freed before a call to **srv_sendrow**.</span></span> <span data-ttu-id="ab5f3-137">L'indirizzo dei dati di origine può essere modificato tra una chiamata e l'altra a **srv_sendrow** usando **srv_setcoldata**.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-137">The source data address can be changed between calls to **srv_sendrow** by using **srv_setcoldata**.</span></span> <span data-ttu-id="ab5f3-138">La memoria allocata per *srcdata* non deve essere liberata fino a quando i dati della colonna non vengono sostituiti da un'altra chiamata a **srv_setcoldata** o fino alla chiamata a **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-138">Memory allocated for *srcdata* should not be freed until the column data is replaced by another call to **srv_setcoldata**, or until **srv_senddone** is called.</span></span>  
  
 <span data-ttu-id="ab5f3-139">Se *desttype* è SRVDECIMAL o SRVNUMERIC, il parametro *srcdata* deve essere un puntatore a una struttura DBNUMERIC o DBDECIMAL con i campi della precisione e della scala della struttura già impostati sui valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-139">If *desttype* is SRVDECIMAL or SRVNUMERIC, the *srcdata* parameter must be a pointer to a DBNUMERIC or DBDECIMAL structure with the precision and scale fields of the structure already set to the values you want.</span></span> <span data-ttu-id="ab5f3-140">È possibile utilizzare DEFAULTPRECISION per specificare una precisione predefinita e DEFAULTSCALE per specificare una scala predefinita.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-140">You can use DEFAULTPRECISION to specify a default precision, and DEFAULTSCALE to specify a default scale.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="ab5f3-141">Restituisce</span><span class="sxs-lookup"><span data-stu-id="ab5f3-141">Returns</span></span>  
 <span data-ttu-id="ab5f3-142">Il numero della colonna descritta.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-142">The number of the column described.</span></span> <span data-ttu-id="ab5f3-143">La prima colonna è la colonna 1.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-143">The first column is column 1.</span></span> <span data-ttu-id="ab5f3-144">Se si verifica un errore, viene restituito 0.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-144">If an error occurs, returns 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab5f3-145">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ab5f3-145">Remarks</span></span>  
 <span data-ttu-id="ab5f3-146">La funzione **srv_describe** deve essere chiamata una volta per ogni colonna nella riga prima della prima chiamata a **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-146">The **srv_describe** function must be called once for each column in the row before the first call to **srv_sendrow**.</span></span> <span data-ttu-id="ab5f3-147">Le colonne di una riga possono essere descritte in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-147">The columns of a row can be described in any order.</span></span>  
  
 <span data-ttu-id="ab5f3-148">Per modificare il percorso e lunghezza dei dati di origine nelle righe della colonna prima dell'invio del set di risultati completo, usare rispettivamente **srv_setcoldata** e **srv_setcollen**.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-148">To change the location and length of the source data in column rows before the complete result set has been sent, use **srv_setcoldata** and **srv_setcollen**, respectively.</span></span>  
  
 <span data-ttu-id="ab5f3-149">Per una descrizione dei tipi di dati e delle conversioni dei tipi di dati dell'API Stored procedure estesa, vedere [Tipi di dati &#40;API Stored procedure estesa&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="ab5f3-149">For a description of data types and Extended Store Procedure API data type conversions, see[Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="ab5f3-150">Se il nome della colonna nell'applicazione è in Unicode, è necessario convertirlo nella tabella codici multibyte del server prima di chiamare **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-150">If the column name in your application is in Unicode, you need to convert it to the multibyte code page of the server before calling **srv_describe**.</span></span> <span data-ttu-id="ab5f3-151">Per ulteriori informazioni, vedere [dati Unicode e tabelle codici del server](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="ab5f3-151">For more information, see [Unicode Data and Server Code Pages](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ab5f3-152">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="ab5f3-152">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="ab5f3-153">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="ab5f3-153">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab5f3-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab5f3-154">See Also</span></span>  
 <span data-ttu-id="ab5f3-155">[srv_sendrow &#40;API stored procedure estesa&#41;](srv-sendrow-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="ab5f3-155">[srv_sendrow &#40;Extended Stored Procedure API&#41;](srv-sendrow-extended-stored-procedure-api.md) </span></span>  
 <span data-ttu-id="ab5f3-156">[srv_setutype &#40;API stored procedure estesa&#41;](srv-setutype-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="ab5f3-156">[srv_setutype &#40;Extended Stored Procedure API&#41;](srv-setutype-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="ab5f3-157">srv_setcoldata &#40;API Stored procedure estesa&#41;</span><span class="sxs-lookup"><span data-stu-id="ab5f3-157">srv_setcoldata &#40;Extended Stored Procedure API&#41;</span></span>](srv-setcoldata-extended-stored-procedure-api.md)  
  
  
