---
title: IBCPSession::BCPInit (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPInit (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPInit method
ms.assetid: 583096d7-da34-49be-87fd-31210aac81aa
author: rothja
ms.author: jroth
ms.openlocfilehash: 25a01c71811de9d47ce01714402460bb53d4c70e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714312"
---
# <a name="ibcpsessionbcpinit-ole-db"></a><span data-ttu-id="89dfe-102">IBCPSession::BCPInit (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="89dfe-102">IBCPSession::BCPInit (OLE DB)</span></span>
  <span data-ttu-id="89dfe-103">Inizializza la struttura della copia bulk, esegue alcune operazioni di controllo degli errori, verifica che i dati e i nomi dei file di formato siano corretti, quindi li apre.</span><span class="sxs-lookup"><span data-stu-id="89dfe-103">Initializes the bulk copy structure, performs some error checking, verifies that the data and format file names are correct, and then opens them.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89dfe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89dfe-104">Syntax</span></span>  
  
```  
  
HRESULT BCPInit(   
const wchar_t *pwszTable,  
const wchar_t *pwszDataFile,  
const wchar_t *pwszErrorFile,  
inteDirection);  
```  
  
## <a name="remarks"></a><span data-ttu-id="89dfe-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="89dfe-105">Remarks</span></span>  
 <span data-ttu-id="89dfe-106">Il metodo **BCPInit** deve essere chiamato prima di qualsiasi altro metodo di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="89dfe-106">The **BCPInit** method should be called before any other bulk-copy method.</span></span> <span data-ttu-id="89dfe-107">Il metodo **BCPInit** esegue le inizializzazioni necessarie per una copia bulk dei dati tra la workstation e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89dfe-107">The **BCPInit** method performs the necessary initializations for a bulk copy of data between the workstation and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="89dfe-108">Il metodo **BCPInit** esamina la struttura dell'origine del database o della tabella di destinazione, non il file di dati.</span><span class="sxs-lookup"><span data-stu-id="89dfe-108">The **BCPInit** method examines the structure of the database source or target table, not the data file.</span></span> <span data-ttu-id="89dfe-109">Specifica i valori relativi al formato dei dati per il file di dati in base a ogni colonna nella vista o nella tabella di database o nel set di risultati SELECT.</span><span class="sxs-lookup"><span data-stu-id="89dfe-109">It specifies data format values for the data file based on each column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="89dfe-110">Questa specifica include il tipo di dati di ogni colonna, la presenza o meno di un indicatore di lunghezza o Null e di stringhe di byte con carattere di terminazione nei dati e la larghezza dei tipi di dati a lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="89dfe-110">This specification includes the data type of each column, the presence or absence of a length or null indicator and terminator byte strings in the data, and the width of fixed-length data types.</span></span> <span data-ttu-id="89dfe-111">Il metodo **BCPInit** imposta questi valori nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="89dfe-111">The **BCPInit** method sets these values as follows:</span></span>  
  
-   <span data-ttu-id="89dfe-112">Il tipo di dati specificato è quello della colonna della vista o della tabella di database oppure del set di risultati SELECT.</span><span class="sxs-lookup"><span data-stu-id="89dfe-112">The data type specified is the data type of the column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="89dfe-113">Il tipo di dati viene enumerato [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in base ai tipi di dati nativi specificati nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file di intestazione di Native Client (sqlncli. h).</span><span class="sxs-lookup"><span data-stu-id="89dfe-113">The data type is enumerated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types specified in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client header file (sqlncli.h).</span></span> <span data-ttu-id="89dfe-114">I relativi valori utilizzano il modello BCP_TYPE_XXX.</span><span class="sxs-lookup"><span data-stu-id="89dfe-114">Their values are in the pattern of BCP_TYPE_XXX.</span></span> <span data-ttu-id="89dfe-115">I dati vengono rappresentati nel relativo formato elettronico,</span><span class="sxs-lookup"><span data-stu-id="89dfe-115">The data is represented in its computer form.</span></span> <span data-ttu-id="89dfe-116">ovvero i dati di una colonna di un tipo di dati integer vengono rappresentati da una sequenza a quattro byte, di tipo big o little endian a seconda del computer con il quale è stato creato il file di dati.</span><span class="sxs-lookup"><span data-stu-id="89dfe-116">That is, data from a column of integer data type is represented by a four-byte sequence that is big-or little-endian based on the computer that created the data file.</span></span>  
  
-   <span data-ttu-id="89dfe-117">Se un tipo di dati del database ha una lunghezza fissa, anche i dati del file di dati presenteranno una lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="89dfe-117">If a database data type is fixed in length, the data file data is also fixed in length.</span></span> <span data-ttu-id="89dfe-118">I metodi di copia bulk che elaborano dati, ad esempio [IBCPSession::BCPExec](ibcpsession-bcpexec-ole-db.md), analizzano le righe di dati prevedendo che la lunghezza dei dati nel file sia identica alla lunghezza dei dati specificata nella vista o nella tabella di database o nell'elenco di colonne SELECT.</span><span class="sxs-lookup"><span data-stu-id="89dfe-118">Bulk-copy methods that process data (for example, [IBCPSession::BCPExec](ibcpsession-bcpexec-ole-db.md)) parse data rows expecting the length of the data in the data file to be identical to the length of the data specified in the database table, view, or SELECT column list.</span></span> <span data-ttu-id="89dfe-119">I dati di una colonna del database definiti come `char(13)` devono, ad esempio, essere rappresentati da 13 caratteri per ogni riga di dati nel file.</span><span class="sxs-lookup"><span data-stu-id="89dfe-119">For example, data for a database column defined as `char(13)` must be represented by 13 characters for each row of data in the file.</span></span> <span data-ttu-id="89dfe-120">I dati a lunghezza fissa possono essere preceduti da un indicatore Null se la colonna del database consente valori Null.</span><span class="sxs-lookup"><span data-stu-id="89dfe-120">Fixed-length data can be prefixed with a null indicator if the database column allows null values.</span></span>  
  
-   <span data-ttu-id="89dfe-121">Quando si copiano dati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il file di dati deve includere dati per ogni colonna nella tabella di database.</span><span class="sxs-lookup"><span data-stu-id="89dfe-121">When copying data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data file must have data for each column in the database table.</span></span> <span data-ttu-id="89dfe-122">Quando si copiano dati da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], i dati di tutte le colonne della vista o della tabella di database o del set di risultati SELECT vengono copiati nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="89dfe-122">When copying data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data from all columns in the database table, view, or SELECT result set are copied to the data file.</span></span>  
  
-   <span data-ttu-id="89dfe-123">Quando si copiano dati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la posizione ordinale di una colonna nel file di dati deve essere identica alla posizione ordinale della colonna nella tabella di database.</span><span class="sxs-lookup"><span data-stu-id="89dfe-123">When copying data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the ordinal position of a column in the data file must be identical to the ordinal position of the column in the database table.</span></span> <span data-ttu-id="89dfe-124">Quando si copiano dati da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il metodo **BCPExec** dispone i dati in base alla posizione ordinale della colonna nella tabella di database.</span><span class="sxs-lookup"><span data-stu-id="89dfe-124">When copying data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the **BCPExec** method places data based on the ordinal position of the column in the database table.</span></span>  
  
-   <span data-ttu-id="89dfe-125">Se un tipo di dati del database ha una lunghezza variabile, ad esempio `varbinary(22)`, o se una colonna del database può contenere valori Null, i dati nel file di dati sono preceduti da un indicatore di lunghezza o Null.</span><span class="sxs-lookup"><span data-stu-id="89dfe-125">If a database data type is variable in length (for example, `varbinary(22)`) or if a database column can contain null values, data in the data file is prefixed by a length/null indicator.</span></span> <span data-ttu-id="89dfe-126">La larghezza dell'indicatore varia in base al tipo di dati e alla versione della copia bulk.</span><span class="sxs-lookup"><span data-stu-id="89dfe-126">The width of the indicator varies based on the data type and version of bulk copy.</span></span> <span data-ttu-id="89dfe-127">L'opzione BCP_OPTION_FILEFMT del metodo [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) fornisce compatibilità tra i file di dati di copia bulk precedenti e i server che eseguono versioni successive di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] indicando quando la larghezza degli indicatori nei dati è inferiore a quella prevista.</span><span class="sxs-lookup"><span data-stu-id="89dfe-127">The [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) method option BCP_OPTION_FILEFMT provides compatibility between earlier bulk-copy data files and servers running later versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by indicating when the width of indicators in the data is narrower than expected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89dfe-128">Per modificare i valori relativi al formato dei dati specificati per un file di dati, utilizzare i metodi [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) e [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="89dfe-128">To change the data format values specified for a data file, use the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods.</span></span>  
  
 <span data-ttu-id="89dfe-129">Le copie bulk in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono essere ottimizzate per le tabelle che non contengono indici impostando l'opzione del database **select into/bulkcopy**.</span><span class="sxs-lookup"><span data-stu-id="89dfe-129">Bulk copies to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be optimized for tables that do not contain indexes by setting the database option **select into/bulkcopy**.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="89dfe-130">Argomenti</span><span class="sxs-lookup"><span data-stu-id="89dfe-130">Arguments</span></span>  
 <span data-ttu-id="89dfe-131">*pwszTable*[in]</span><span class="sxs-lookup"><span data-stu-id="89dfe-131">*pwszTable*[in]</span></span>  
 <span data-ttu-id="89dfe-132">Nome della tabella di database per la copia interna o esterna.</span><span class="sxs-lookup"><span data-stu-id="89dfe-132">The name of the database table to be copied into or out of.</span></span> <span data-ttu-id="89dfe-133">Il nome può includere il nome del database o del proprietario,</span><span class="sxs-lookup"><span data-stu-id="89dfe-133">The name can include the database name or the owner name.</span></span> <span data-ttu-id="89dfe-134">ad esempio "pubs.username.titles", "pubs..titles", "username.titles".</span><span class="sxs-lookup"><span data-stu-id="89dfe-134">For example, "pubs.username.titles", "pubs..titles", "username.titles".</span></span>  
  
 <span data-ttu-id="89dfe-135">Se l'argomento eDirection è impostato su BCP_DIRECTION_OUT, l'argomento pwszTable può essere il nome di una vista di database.</span><span class="sxs-lookup"><span data-stu-id="89dfe-135">If the eDirection argument is set to BCP_DIRECTION_OUT, the pwszTable argument can be the name of a database view.</span></span>  
  
 <span data-ttu-id="89dfe-136">Se l'argomento eDirection è impostato su BCP_DIRECTION_OUT e viene specificata un'istruzione SELECT utilizzando il metodo **BCPControl** prima che venga chiamato il metodo **BCPExec**, è necessario impostare l'argomento *pwszTable* su NULL.</span><span class="sxs-lookup"><span data-stu-id="89dfe-136">If the eDirection argument is set to BCP_DIRECTION_OUT and a SELECT statement is specified using the **BCPControl** method before the **BCPExec** method is called, the *pwszTable* argument must be set to NULL.</span></span>  
  
 <span data-ttu-id="89dfe-137">*pwszDataFile*[in]</span><span class="sxs-lookup"><span data-stu-id="89dfe-137">*pwszDataFile*[in]</span></span>  
 <span data-ttu-id="89dfe-138">Nome del file utente per la copia interna o esterna.</span><span class="sxs-lookup"><span data-stu-id="89dfe-138">The name of the user file to be copied into or out of.</span></span>  
  
 <span data-ttu-id="89dfe-139">*pwszErrorFile*[in]</span><span class="sxs-lookup"><span data-stu-id="89dfe-139">*pwszErrorFile*[in]</span></span>  
 <span data-ttu-id="89dfe-140">Nome del file degli errori in cui inserire messaggi di stato, messaggi di errore e copie delle righe che non è stato possibile copiare da un file utente in una tabella.</span><span class="sxs-lookup"><span data-stu-id="89dfe-140">The name of the error file to be filled with progress messages, error messages, and copies of any rows that could not be copied from a user file to a table.</span></span> <span data-ttu-id="89dfe-141">Se l'argomento *pwszErrorFile* è impostato su NULL, non viene usato alcun file degli errori.</span><span class="sxs-lookup"><span data-stu-id="89dfe-141">If the *pwszErrorFile* argument is set to NULL, no error file is used.</span></span>  
  
 <span data-ttu-id="89dfe-142">*eDirection*[in]</span><span class="sxs-lookup"><span data-stu-id="89dfe-142">*eDirection*[in]</span></span>  
 <span data-ttu-id="89dfe-143">Direzione dell'operazione di copia, BCP_DIRECTION_IN o BCP_DIRECTION _OUT.</span><span class="sxs-lookup"><span data-stu-id="89dfe-143">The direction of the copy operation, either BCP_DIRECTION_IN or BCP_DIRECTION _OUT.</span></span> <span data-ttu-id="89dfe-144">BCP_DIRECTION _IN indica una copia da un file utente in una tabella di database e BCP_DIRECTION _OUT indica una copia da una tabella di database in un file utente.</span><span class="sxs-lookup"><span data-stu-id="89dfe-144">BCP_DIRECTION _IN indicates a copy from a user file to a database table; BCP_DIRECTION _OUT indicates a copy from a database table to a user file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="89dfe-145">Valori del codice restituito</span><span class="sxs-lookup"><span data-stu-id="89dfe-145">Return Code Values</span></span>  
 <span data-ttu-id="89dfe-146">S_OK</span><span class="sxs-lookup"><span data-stu-id="89dfe-146">S_OK</span></span>  
 <span data-ttu-id="89dfe-147">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="89dfe-147">The method succeeded.</span></span>  
  
 <span data-ttu-id="89dfe-148">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="89dfe-148">E_FAIL</span></span>  
 <span data-ttu-id="89dfe-149">Si è verificato un errore specifico del provider. per informazioni dettagliate, utilizzare l'interfaccia [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="89dfe-149">A provider specific error occurred' for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="89dfe-150">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="89dfe-150">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="89dfe-151">Errore di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="89dfe-151">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="89dfe-152">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="89dfe-152">E_INVALIDARG</span></span>  
 <span data-ttu-id="89dfe-153">Uno o più argomenti non sono stati specificati correttamente,</span><span class="sxs-lookup"><span data-stu-id="89dfe-153">One or more of the arguments was not correctly specified.</span></span> <span data-ttu-id="89dfe-154">ad esempio è stato immesso un nome file non valido.</span><span class="sxs-lookup"><span data-stu-id="89dfe-154">For example, an invalid file name was given.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89dfe-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89dfe-155">See Also</span></span>  
 <span data-ttu-id="89dfe-156">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="89dfe-156">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="89dfe-157">Esecuzione di operazioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="89dfe-157">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
