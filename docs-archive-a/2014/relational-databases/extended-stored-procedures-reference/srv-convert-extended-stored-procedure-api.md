---
title: srv_convert (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_convert
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_convert
ms.assetid: 216b4a31-786e-4361-8a33-e5f6e9790f90
author: rothja
ms.author: jroth
ms.openlocfilehash: 30a0ea356f017ed3d1b3ecc85cf483b4553e120a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637322"
---
# <a name="srv_convert-extended-stored-procedure-api"></a><span data-ttu-id="42709-102">srv_convert (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="42709-102">srv_convert (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="42709-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="42709-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="42709-104">Consente di modificare i dati da un tipo all'altro.</span><span class="sxs-lookup"><span data-stu-id="42709-104">Changes data from one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42709-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42709-105">Syntax</span></span>  
  
```  
  
int srv_convert (  
SRV_PROC *  
srvproc  
,  
int  
srctype  
,  
void *  
src  
,  
DBINT  
srclen  
,  
int  
desttype  
,  
void *  
dest  
,  
DBINT  
destlen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="42709-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="42709-106">Arguments</span></span>  
 <span data-ttu-id="42709-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="42709-107">*srvproc*</span></span>  
 <span data-ttu-id="42709-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client.</span><span class="sxs-lookup"><span data-stu-id="42709-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="42709-109">La struttura contiene tutte le informazioni di controllo utilizzate dall'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="42709-109">The structure contains all the control information that the Extended Stored Procedure API uses to manage communications and data between the application and the client.</span></span> <span data-ttu-id="42709-110">Se specificato, l'handle *srvproc* viene passato alla funzione di gestione degli errori dell'API Stored procedure estesa quando si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="42709-110">If the *srvproc* handle is supplied, it is passed to the Extended Stored Procedure API error handler function when an error occurs.</span></span>  
  
 <span data-ttu-id="42709-111">*srctype*</span><span class="sxs-lookup"><span data-stu-id="42709-111">*srctype*</span></span>  
 <span data-ttu-id="42709-112">Indica il tipo a cui appartengono i dati da convertire.</span><span class="sxs-lookup"><span data-stu-id="42709-112">Specifies the data type of the data to be converted.</span></span> <span data-ttu-id="42709-113">Questo parametro può appartenere a qualsiasi tipo di dati dell'API Stored procedure estesa.</span><span class="sxs-lookup"><span data-stu-id="42709-113">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="42709-114">*src*</span><span class="sxs-lookup"><span data-stu-id="42709-114">*src*</span></span>  
 <span data-ttu-id="42709-115">Puntatore ai dati da convertire.</span><span class="sxs-lookup"><span data-stu-id="42709-115">Is a pointer to the data to be converted.</span></span> <span data-ttu-id="42709-116">Questo parametro può appartenere a qualsiasi tipo di dati dell'API Stored procedure estesa.</span><span class="sxs-lookup"><span data-stu-id="42709-116">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="42709-117">*srclen*</span><span class="sxs-lookup"><span data-stu-id="42709-117">*srclen*</span></span>  
 <span data-ttu-id="42709-118">Specifica la lunghezza, espressa in byte, dei dati da convertire.</span><span class="sxs-lookup"><span data-stu-id="42709-118">Specifies the length, in bytes, of the data to be converted.</span></span> <span data-ttu-id="42709-119">Se *srclen* è 0, **srv_convert** inserisce un valore Null nella variabile di destinazione.</span><span class="sxs-lookup"><span data-stu-id="42709-119">If *srclen* is 0, **srv_convert** places a null value in the destination variable.</span></span> <span data-ttu-id="42709-120">A meno che non sia 0, questo parametro viene ignorato per i tipi di dati a lunghezza fissa e in tal caso si presuppone che i dati di origine siano NULL.</span><span class="sxs-lookup"><span data-stu-id="42709-120">Unless it is 0, this parameter is ignored for fixed-length data types, in which case the source data is assumed to be NULL.</span></span> <span data-ttu-id="42709-121">Per i dati appartenenti al tipo SRVCHAR, una lunghezza di -1 indica che la stringa ha una terminazione Null.</span><span class="sxs-lookup"><span data-stu-id="42709-121">For data of the SRVCHAR data type, a length of -1 indicates the string is null-terminated.</span></span>  
  
 <span data-ttu-id="42709-122">*desttype*</span><span class="sxs-lookup"><span data-stu-id="42709-122">*desttype*</span></span>  
 <span data-ttu-id="42709-123">Indica il tipo di dati in cui convertire l'origine.</span><span class="sxs-lookup"><span data-stu-id="42709-123">Specifies the data type to convert the source to.</span></span> <span data-ttu-id="42709-124">Questo parametro può appartenere a qualsiasi tipo di dati dell'API Stored procedure estesa.</span><span class="sxs-lookup"><span data-stu-id="42709-124">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="42709-125">*dest*</span><span class="sxs-lookup"><span data-stu-id="42709-125">*dest*</span></span>  
 <span data-ttu-id="42709-126">Puntatore alla variabile di destinazione che riceve i dati convertiti.</span><span class="sxs-lookup"><span data-stu-id="42709-126">Is a pointer to the destination variable that receives converted data.</span></span> <span data-ttu-id="42709-127">Se questo puntatore è NULL, **srv_convert** chiama il gestore degli errori specificato dall'utente, se disponibile, e restituisce -1.</span><span class="sxs-lookup"><span data-stu-id="42709-127">If this pointer is NULL, **srv_convert** calls the user-supplied error handler ,if any, and returns -1.</span></span>  
  
 <span data-ttu-id="42709-128">Se *desttype* è SRVDECIMAL o SRVNUMERIC, il parametro *dest* deve essere un puntatore a una struttura DBNUMERIC o DBDECIMAL con i campi della precisione e della scala della struttura già impostati sui valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="42709-128">If *desttype* is SRVDECIMAL or SRVNUMERIC, the *dest* parameter must be a pointer to a DBNUMERIC or DBDECIMAL structure with the precision and scale fields of the structure already set to the desired values.</span></span> <span data-ttu-id="42709-129">È possibile utilizzare DEFAULTPRECISION per specificare una precisione predefinita e DEFAULTSCALE per specificare una scala predefinita.</span><span class="sxs-lookup"><span data-stu-id="42709-129">You can use DEFAULTPRECISION to specify a default precision, and DEFAULTSCALE to specify a default scale.</span></span>  
  
 <span data-ttu-id="42709-130">*destlen*</span><span class="sxs-lookup"><span data-stu-id="42709-130">*destlen*</span></span>  
 <span data-ttu-id="42709-131">Specifica la lunghezza, espressa in byte, della variabile di destinazione.</span><span class="sxs-lookup"><span data-stu-id="42709-131">Specifies the length, in bytes, of the destination variable.</span></span> <span data-ttu-id="42709-132">Questo parametro viene ignorato per i tipi di dati a lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="42709-132">This parameter is ignored for fixed-length data types.</span></span> <span data-ttu-id="42709-133">Per una variabile di destinazione di tipo SRVCHAR, il valore di *destlen* deve essere la lunghezza totale dello spazio del buffer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="42709-133">For a destination variable of type SRVCHAR, the value of *destlen* must be the total length of the destination buffer space.</span></span> <span data-ttu-id="42709-134">Una lunghezza di -1 per una variabile di destinazione di tipo SRVCHAR o SRVBINARY indica che lo spazio disponibile è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="42709-134">A length of -1 for a destination variable of type SRVCHAR or SRVBINARY indicates there is sufficient space available.</span></span> <span data-ttu-id="42709-135">Per una variabile di destinazione di tipo *srvchar*, se la lunghezza è pari a -1 la stringa di caratteri include una terminazione Null.</span><span class="sxs-lookup"><span data-stu-id="42709-135">For a destination variable of type *srvchar*, a length of -1 causes the character string to be null-terminated.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="42709-136">Restituisce</span><span class="sxs-lookup"><span data-stu-id="42709-136">Returns</span></span>  
 <span data-ttu-id="42709-137">La lunghezza dei dati convertiti, espressa in byte, se la conversione del tipo di dati viene eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="42709-137">The length of the converted data, in bytes, if the data type conversion succeeds.</span></span> <span data-ttu-id="42709-138">Quando **srv_convert** rileva una richiesta di conversione non supportata, chiama il gestore degli errori specificato dallo sviluppatore, se disponibile, imposta un numero di errore globale e restituisce -1.</span><span class="sxs-lookup"><span data-stu-id="42709-138">When **srv_convert** encounters a request for a conversion it does not support, it calls the developer-supplied error handler, if any, sets a global error number, and returns -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42709-139">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="42709-139">Remarks</span></span>  
 <span data-ttu-id="42709-140">La funzione **srv_willconvert** determina se una specifica conversione è consentita.</span><span class="sxs-lookup"><span data-stu-id="42709-140">The **srv_willconvert** function determines whether a particular conversion is allowed.</span></span>  
  
 <span data-ttu-id="42709-141">La conversione in tipi di dati numerici approssimati SRVFLT4 o SRVFLT8 può causare una perdita di precisione.</span><span class="sxs-lookup"><span data-stu-id="42709-141">Converting to the approximate numeric data types SRVFLT4 or SRVFLT8 can result in some loss of precision.</span></span> <span data-ttu-id="42709-142">Lo stesso problema può verificarsi durante la conversione da tipi di dati numerici approssimati SRVFLT4 o SRVFLT8 in SRVCHAR o SRVTEXT.</span><span class="sxs-lookup"><span data-stu-id="42709-142">Converting from the approximate numeric data types SRVFLT4 or SRVFLT8 to SRVCHAR or SRVTEXT can also result in some loss of precision.</span></span>  
  
 <span data-ttu-id="42709-143">La conversione in SRVFLT*x*, SRVINT*x*, SRVMONEY, SRVMONEY4, SRVDECIMAL o SRVNUMERIC può causare un overflow se il numero è maggiore del valore massimo della destinazione o un underflow se il numero è minore del valore minimo della destinazione.</span><span class="sxs-lookup"><span data-stu-id="42709-143">Converting to SRVFLT*x*, SRVINT*x*, SRVMONEY, SRVMONEY4, SRVDECIMAL, or SRVNUMERIC can result in overflow if the number is larger than the maximum value of the destination, or in underflow if the number is smaller than the minimum value of the destination.</span></span> <span data-ttu-id="42709-144">Se l'overflow si verifica durante la conversione in SRVCHAR o SRVTEXT, il primo carattere del valore risultante contiene un asterisco (\*) per indicare l'errore.</span><span class="sxs-lookup"><span data-stu-id="42709-144">If overflow occurs when converting to SRVCHAR or SRVTEXT, the first character of the resulting value contains an asterisk (\*) to indicate the error.</span></span>  
  
 <span data-ttu-id="42709-145">Durante la conversione di SRVCHAR in SRVBINARY, **srv_convert** interpreta SRVCHAR come stringa esadecimale, indipendentemente dalla presenza di uno 0 (zero) iniziale nella stringa.</span><span class="sxs-lookup"><span data-stu-id="42709-145">When converting SRVCHAR to SRVBINARY, **srv_convert** interprets SRVCHAR as hexadecimal, whether or not the string contains a leading 0.</span></span> <span data-ttu-id="42709-146">Durante la conversione di SRVBINARY in SRVCHAR, **srv_convert** crea una stringa esadecimale senza uno 0 (zero) iniziale.</span><span class="sxs-lookup"><span data-stu-id="42709-146">When converting SRVBINARY to SRVCHAR, **srv_convert** creates a hexadecimal string without a leading 0.</span></span> <span data-ttu-id="42709-147">In tutti gli altri casi, una conversione verso o dal tipo di dati SRVBINARY è una copia di bit diretta.</span><span class="sxs-lookup"><span data-stu-id="42709-147">In all other cases, a conversion to or from the SRVBINARY data type is a straight bit-copy.</span></span>  
  
 <span data-ttu-id="42709-148">In determinati casi, può essere utile convertire un tipo di dati in se stesso.</span><span class="sxs-lookup"><span data-stu-id="42709-148">In certain cases, it can be useful to convert a data type to itself.</span></span> <span data-ttu-id="42709-149">La conversione di SRVCHAR in SRVCHAR con un valore di *destlen* pari a -1, ad esempio, aggiunge un carattere di terminazione Null a una stringa.</span><span class="sxs-lookup"><span data-stu-id="42709-149">For example, converting SRVCHAR to SRVCHAR with a *destlen* of -1 adds a null terminator to a string.</span></span>  
  
 <span data-ttu-id="42709-150">Per una descrizione dei tipi di dati e delle conversioni dei tipi di dati dell'API Stored procedure estesa, vedere [Tipi di dati &#40;API Stored procedure estesa&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="42709-150">For a description of data types and Extended Store Procedure API data type conversions, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="42709-151">Di seguito sono riportati i motivi per cui la funzione **srv_convert** potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="42709-151">The **srv_convert** function can fail for several reasons:</span></span>  
  
-   <span data-ttu-id="42709-152">La conversione richiesta non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="42709-152">The requested conversion is not available.</span></span>  
  
-   <span data-ttu-id="42709-153">La conversione ha causato un troncamento, un overflow o una perdita di precisione nella variabile di destinazione.</span><span class="sxs-lookup"><span data-stu-id="42709-153">The conversion resulted in truncation, overflow, or loss of precision in the destination variable.</span></span>  
  
-   <span data-ttu-id="42709-154">Si è verificato un errore di sintassi durante la conversione di una stringa di caratteri in un tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="42709-154">A syntax error occurred while converting a character string to a numeric data type.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="42709-155">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="42709-155">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="42709-156">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="42709-156">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42709-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42709-157">See Also</span></span>  
 <span data-ttu-id="42709-158">[srv_setutype &#40;API stored procedure estesa&#41;](srv-setutype-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="42709-158">[srv_setutype &#40;Extended Stored Procedure API&#41;](srv-setutype-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="42709-159">srv_willconvert &#40;API Stored procedure estesa&#41;</span><span class="sxs-lookup"><span data-stu-id="42709-159">srv_willconvert &#40;Extended Stored Procedure API&#41;</span></span>](srv-willconvert-extended-stored-procedure-api.md)  
  
  
