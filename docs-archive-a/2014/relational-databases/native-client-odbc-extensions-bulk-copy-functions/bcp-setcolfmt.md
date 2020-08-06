---
title: bcp_setcolfmt | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_setcolfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_setcolfmt function
ms.assetid: afb47987-39e7-4079-ad66-e0abf4d4c72b
author: rothja
ms.author: jroth
ms.openlocfilehash: bb3b1da62ab4e98ed4497dd11fcc20163025058b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629805"
---
# <a name="bcp_setcolfmt"></a><span data-ttu-id="49421-102">bcp_setcolfmt</span><span class="sxs-lookup"><span data-stu-id="49421-102">bcp_setcolfmt</span></span>
  <span data-ttu-id="49421-103">La funzione **bcp_setcolfmt** sostituisce l' [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="49421-103">The **bcp_setcolfmt** function supersedes the [bcp_colfmt](bcp-colfmt.md).</span></span> <span data-ttu-id="49421-104">Quando si specificano le regole di confronto delle colonne, è necessario utilizzare la funzione **bcp_setcolfmt** .</span><span class="sxs-lookup"><span data-stu-id="49421-104">In specifying the column collation, the **bcp_setcolfmt** function must be used.</span></span> <span data-ttu-id="49421-105">[bcp_setbulkmode](bcp-setbulkmode.md) può essere utilizzato per specificare più di un formato di colonna.</span><span class="sxs-lookup"><span data-stu-id="49421-105">[bcp_setbulkmode](bcp-setbulkmode.md) can be used to specify more than one column format.</span></span>  
  
 <span data-ttu-id="49421-106">Questa funzione fornisce un approccio flessibile alla definizione del formato delle colonne in un'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="49421-106">This function provides a flexible approach to specifying the column format in a bulk copy operation.</span></span> <span data-ttu-id="49421-107">La funzione viene utilizzata per impostare singoli attributi di formato di colonna.</span><span class="sxs-lookup"><span data-stu-id="49421-107">It is used to set individual column format attributes.</span></span> <span data-ttu-id="49421-108">Ogni chiamata a **bcp_setcolfmt** imposta un attributo di formato della colonna.</span><span class="sxs-lookup"><span data-stu-id="49421-108">Each call to **bcp_setcolfmt** sets one column format attribute.</span></span>  
  
 <span data-ttu-id="49421-109">La funzione **bcp_setcolfmt** specifica il formato di origine o di destinazione dei dati in un file utente.</span><span class="sxs-lookup"><span data-stu-id="49421-109">The **bcp_setcolfmt** function specifies the source or target format of the data in a user file.</span></span> <span data-ttu-id="49421-110">Se utilizzato come formato di origine, **bcp_setcolfmt** specifica il formato di un file di dati esistente utilizzato come origine dati di dati in una copia bulk in una tabella in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49421-110">When used as a source format, **bcp_setcolfmt** specifies the format of an existing data file used as a data source of data in a bulk copy to a table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="49421-111">Quando viene utilizzato come formato di destinazione, il file di dati viene creato utilizzando i formati di colonna specificati con **bcp_setcolfmt**.</span><span class="sxs-lookup"><span data-stu-id="49421-111">When used as a target format, the data file is created using the column formats specified with **bcp_setcolfmt**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49421-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49421-112">Syntax</span></span>  
  
```  
  
RETCODE bcp_setcolfmt (  
HDBC   
hdbc  
,  
INT   
field  
,  
INT   
property  
,  
void*   
pValue  
,  
INT   
cbValue  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="49421-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="49421-113">Arguments</span></span>  
 <span data-ttu-id="49421-114">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="49421-114">*hdbc*</span></span>  
 <span data-ttu-id="49421-115">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="49421-115">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="49421-116">*campo*</span><span class="sxs-lookup"><span data-stu-id="49421-116">*field*</span></span>  
 <span data-ttu-id="49421-117">Numero di colonna ordinale per cui viene impostata la proprietà.</span><span class="sxs-lookup"><span data-stu-id="49421-117">Is the ordinal column number for which the property is being set.</span></span>  
  
 <span data-ttu-id="49421-118">*property*</span><span class="sxs-lookup"><span data-stu-id="49421-118">*property*</span></span>  
 <span data-ttu-id="49421-119">Una delle costanti di proprietà.</span><span class="sxs-lookup"><span data-stu-id="49421-119">Is one of the property constants.</span></span> <span data-ttu-id="49421-120">Le costanti della proprietà sono definite nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="49421-120">Property constants are defined in this table.</span></span>  
  
|<span data-ttu-id="49421-121">Proprietà</span><span class="sxs-lookup"><span data-stu-id="49421-121">Property</span></span>|<span data-ttu-id="49421-122">Valore</span><span class="sxs-lookup"><span data-stu-id="49421-122">Value</span></span>|<span data-ttu-id="49421-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49421-123">Description</span></span>|  
|--------------|-----------|-----------------|  
|<span data-ttu-id="49421-124">BCP_FMT_TYPE</span><span class="sxs-lookup"><span data-stu-id="49421-124">BCP_FMT_TYPE</span></span>|<span data-ttu-id="49421-125">BYTE</span><span class="sxs-lookup"><span data-stu-id="49421-125">BYTE</span></span>|<span data-ttu-id="49421-126">Tipo di dati della colonna nel file utente.</span><span class="sxs-lookup"><span data-stu-id="49421-126">Is the data type of this column in the user file.</span></span> <span data-ttu-id="49421-127">Se differisce dal tipo di dati della colonna corrispondente nella tabella del database, la copia bulk converte i dati, se possibile.</span><span class="sxs-lookup"><span data-stu-id="49421-127">If different from the data type of the corresponding column in the database table, bulk copy converts the data if possible.</span></span><br /><br /> <span data-ttu-id="49421-128">Il parametro BCP_FMT_TYPE viene enumerato in base ai token dei tipi di dati in sqlncli.h e non in base agli enumeratori dei tipi di dati C ODBC.</span><span class="sxs-lookup"><span data-stu-id="49421-128">The BCP_FMT_TYPE parameter is enumerated by the SQL Server data type tokens in sqlncli.h, rather than the ODBC C data type enumerators.</span></span> <span data-ttu-id="49421-129">È possibile, ad esempio, specificare una stringa di caratteri SQL_C_CHAR di tipo ODBC utilizzando il tipo SQLCHARACTER specifico di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49421-129">For example, you can specify a character string, ODBC type SQL_C_CHAR, using the SQLCHARACTER type specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="49421-130">Per specificare la rappresentazione predefinita dei dati per il tipo di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], impostare questo parametro su 0.</span><span class="sxs-lookup"><span data-stu-id="49421-130">To specify the default data representation for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, set this parameter to 0.</span></span><br /><br /> <span data-ttu-id="49421-131">Per una copia bulk esterna a SQL Server in un file, quando BCP_FMT_TYPE è SQLDECIMAL o SQLNUMERIC:</span><span class="sxs-lookup"><span data-stu-id="49421-131">For a bulk copy out of SQL Server into a file, when BCP_FMT_TYPE is SQLDECIMAL or SQLNUMERIC:</span></span><br /><br /> <span data-ttu-id="49421-132">-Se la colonna di origine non è **Decimal** o **numeric**, vengono utilizzate la precisione e la scala predefinite.</span><span class="sxs-lookup"><span data-stu-id="49421-132">-   If the source column is not **decimal** or **numeric**, the default precision and scale are used.</span></span><br /><span data-ttu-id="49421-133">-Se la colonna di origine è **Decimal** o **numeric**, vengono utilizzate la precisione e la scala della colonna di origine.</span><span class="sxs-lookup"><span data-stu-id="49421-133">-   If the source column is **decimal** or **numeric**, the precision and scale of the source column are used.</span></span>|  
|<span data-ttu-id="49421-134">BCP_FMT_INDICATOR_LEN</span><span class="sxs-lookup"><span data-stu-id="49421-134">BCP_FMT_INDICATOR_LEN</span></span>|<span data-ttu-id="49421-135">INT</span><span class="sxs-lookup"><span data-stu-id="49421-135">INT</span></span>|<span data-ttu-id="49421-136">Lunghezza in byte dell'indicatore (prefisso).</span><span class="sxs-lookup"><span data-stu-id="49421-136">Is the length in bytes of the indicator (prefix).</span></span><br /><br /> <span data-ttu-id="49421-137">Lunghezza, espressa in byte, di un indicatore di lunghezza o Null nei dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="49421-137">It is the length, in bytes, of a length/null indicator within the column data.</span></span> <span data-ttu-id="49421-138">I valori validi per la lunghezza dell'indicatore sono 0 (quando non si utilizza alcun indicatore), 1, 2 o 4.</span><span class="sxs-lookup"><span data-stu-id="49421-138">Valid indicator length values are 0 (when using no indicator), 1, 2, or 4.</span></span><br /><br /> <span data-ttu-id="49421-139">Per specificare l'utilizzo di un indicatore di copia bulk predefinito, impostare questo parametro su SQL_VARLEN_DATA.</span><span class="sxs-lookup"><span data-stu-id="49421-139">To specify default bulk copy indicator usage, set this parameter to SQL_VARLEN_DATA.</span></span><br /><br /> <span data-ttu-id="49421-140">Gli indicatori vengono visualizzati in memoria direttamente prima dei dati e nel file di dati immediatamente prima dei dati a cui si riferiscono.</span><span class="sxs-lookup"><span data-stu-id="49421-140">Indicators appear in memory directly before any data, and in the data file directly before the data to which they apply.</span></span><br /><br /> <span data-ttu-id="49421-141">Se si utilizzano più modalità per specificare la lunghezza delle colonne del file di dati, ad esempio un indicatore e una lunghezza di colonna massima o un indicatore e una sequenza di caratteri di terminazione, la copia bulk sceglie quella che comporta la copia del minor numero di dati.</span><span class="sxs-lookup"><span data-stu-id="49421-141">If more than one means of specifying a data file column length is used (such as an indicator and a maximum column length, or an indicator and a terminator sequence), bulk copy chooses the one that results in the least amount of data being copied.</span></span><br /><br /> <span data-ttu-id="49421-142">I file di dati generati dalla copia bulk quando il formato dei dati non viene modificato dall'utente contengono indicatori se la lunghezza dei dati di colonna può variare o se la colonna può accettare NULL come valore.</span><span class="sxs-lookup"><span data-stu-id="49421-142">Data files generated by bulk copy when no user intervention adjusts the format of the data contain indicators when the column data can vary in length or the column can accept NULL as a value.</span></span>|  
|<span data-ttu-id="49421-143">BCP_FMT_DATA_LEN</span><span class="sxs-lookup"><span data-stu-id="49421-143">BCP_FMT_DATA_LEN</span></span>|<span data-ttu-id="49421-144">DBINT</span><span class="sxs-lookup"><span data-stu-id="49421-144">DBINT</span></span>|<span data-ttu-id="49421-145">Lunghezza in byte dei dati (lunghezza di colonna)</span><span class="sxs-lookup"><span data-stu-id="49421-145">Is the length in bytes of the data (column length)</span></span><br /><br /> <span data-ttu-id="49421-146">Lunghezza massima, espressa in byte, dei dati della colonna nel file utente, esclusa la lunghezza di eventuali caratteri di terminazione o di indicatori di lunghezza.</span><span class="sxs-lookup"><span data-stu-id="49421-146">It is the maximum length, in bytes, of this column's data in the user file, not including the length of any length indicator or terminator.</span></span><br /><br /> <span data-ttu-id="49421-147">L'impostazione di BCP_FMT_DATA_LEN su SQL_NULL_DATA indica che tutti i valori nella colonna del file di dati sono o devono essere impostati su NULL.</span><span class="sxs-lookup"><span data-stu-id="49421-147">Setting BCP_FMT_DATA_LEN to SQL_NULL_DATA indicates that all values in the data file column are, or should be set to, NULL.</span></span><br /><br /> <span data-ttu-id="49421-148">L'impostazione di BCP_FMT_DATA_LEN su SQL_VARLEN_DATA indica che il sistema deve determinare la lunghezza dei dati in ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="49421-148">Setting BCP_FMT_DATA_LEN to SQL_VARLEN_DATA indicates that the system should determine the length of data in each column.</span></span> <span data-ttu-id="49421-149">Per alcune colonne, ciò può indicare che viene generato un indicatore di lunghezza o Null da anteporre ai dati in una copia da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o che l'indicatore è previsto nei dati copiati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49421-149">For some columns, this could mean that a length/null indicator is generated to precede data on a copy from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or that the indicator is expected in data copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="49421-150">Per i tipi di dati character e binary di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], BCP_FMT_DATA_LEN può essere SQL_VARLEN_DATA, SQL_NULL_DATA, 0 o un valore positivo.</span><span class="sxs-lookup"><span data-stu-id="49421-150">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, BCP_FMT_DATA_LEN can be SQL_VARLEN_DATA, SQL_NULL_DATA, 0, or some positive value.</span></span> <span data-ttu-id="49421-151">Se BCP_FMT_DATA_LEN è SQL_VARLEN_DATA, il sistema utilizza l'indicatore di lunghezza, se disponibile, o una sequenza di caratteri di terminazione per determinare la lunghezza dei dati.</span><span class="sxs-lookup"><span data-stu-id="49421-151">If BCP_FMT_DATA_LEN is SQL_VARLEN_DATA, the system uses either the length indicator, if present, or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="49421-152">Se vengono specificati sia un indicatore di lunghezza che una sequenza di caratteri di terminazione, la copia bulk utilizza la modalità che comporta la copia del minor numero di dati.</span><span class="sxs-lookup"><span data-stu-id="49421-152">If both a length indicator and a terminator sequence are supplied, bulk copy uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="49421-153">Se BCP_FMT_DATA_LEN è SQL_VARLEN_DATA, il tipo di dati è un tipo character o binary di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e non viene specificato né un indicatore di lunghezza né una sequenza di caratteri di terminazione, il sistema restituisce un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="49421-153">If BCP_FMT_DATA_LEN is SQL_VARLEN_DATA, the data type is an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span><br /><br /> <span data-ttu-id="49421-154">Se BCP_FMT_DATA_LEN è 0 o un valore positivo, viene utilizzato come lunghezza massima dei dati.</span><span class="sxs-lookup"><span data-stu-id="49421-154">If BCP_FMT_DATA_LEN is 0 or a positive value, the system uses BCP_FMT_DATA_LEN as the maximum data length.</span></span> <span data-ttu-id="49421-155">Se, tuttavia, oltre a un valore positivo per BCP_FMT_DATA_LEN viene specificato un indicatore di lunghezza o una sequenza di caratteri di terminazione, il sistema determina la lunghezza dei dati utilizzando il metodo che comporta la copia del minor numero di dati.</span><span class="sxs-lookup"><span data-stu-id="49421-155">However, if, in addition to a positive BCP_FMT_DATA_LEN, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span><br /><br /> <span data-ttu-id="49421-156">Il valore di BCP_FMT_DATA_LEN rappresenta il numero di byte dei dati.</span><span class="sxs-lookup"><span data-stu-id="49421-156">The BCP_FMT_DATA_LEN value represents the count of bytes of data.</span></span> <span data-ttu-id="49421-157">Se i dati di tipo carattere vengono rappresentati come caratteri estesi Unicode, un valore positivo per il parametro BCP_FMT_DATA_LEN rappresenta il numero di caratteri moltiplicato per le dimensioni, espresse in byte, di ogni carattere.</span><span class="sxs-lookup"><span data-stu-id="49421-157">If character data is represented by Unicode wide characters, then a positive BCP_FMT_DATA_LEN parameter value represents the number of characters multiplied by the size, in bytes, of each character.</span></span>|  
|<span data-ttu-id="49421-158">BCP_FMT_TERMINATOR</span><span class="sxs-lookup"><span data-stu-id="49421-158">BCP_FMT_TERMINATOR</span></span>|<span data-ttu-id="49421-159">LPCBYTE</span><span class="sxs-lookup"><span data-stu-id="49421-159">LPCBYTE</span></span>|<span data-ttu-id="49421-160">Puntatore alla sequenza di caratteri di terminazione (ANSI o Unicode in base alle esigenze) da utilizzare per la colonna.</span><span class="sxs-lookup"><span data-stu-id="49421-160">Pointer to the terminator sequence (either ANSI or Unicode as appropriate) to be used for this column.</span></span> <span data-ttu-id="49421-161">Questo parametro risulta particolarmente utile per i dati di tipo carattere, in quanto tutti gli altri tipi hanno una lunghezza fissa o, nel caso dei dati binari, richiedono un indicatore di lunghezza per registrare in modo accurato il numero di byte presenti.</span><span class="sxs-lookup"><span data-stu-id="49421-161">This parameter is useful mainly for character data types because all other types are of fixed length or, in the case of binary data, require an indicator of length to accurately record the number of bytes present.</span></span><br /><br /> <span data-ttu-id="49421-162">Per evitare di terminare i dati estratti o per indicare che i dati di un file utente non devono essere terminati, impostare questo parametro su NULL.</span><span class="sxs-lookup"><span data-stu-id="49421-162">To avoid terminating extracted data, or to indicate that data in a user file is not terminated, set this parameter to NULL.</span></span><br /><br /> <span data-ttu-id="49421-163">Se si utilizzano più modalità per definire la lunghezza delle colonne di un file utente, ad esempio un carattere di terminazione e un indicatore di lunghezza o un carattere di terminazione e una lunghezza di colonna massima, la copia bulk sceglierà quella che comporta la copia del minor numero di dati.</span><span class="sxs-lookup"><span data-stu-id="49421-163">If more than one means of specifying a user-file column length is used (such as a terminator and a length indicator, or a terminator and a maximum column length), bulk copy chooses the one that results in the least amount of data being copied.</span></span><br /><br /> <span data-ttu-id="49421-164">L'API della copia bulk esegue la conversione dei caratteri da Unicode a MBCS in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="49421-164">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="49421-165">Verificare attentamente che la stringa di byte del carattere di terminazione e la lunghezza della stringa di byte siano impostate correttamente.</span><span class="sxs-lookup"><span data-stu-id="49421-165">Care must be taken to ensure that both the terminator byte string and the length of the byte string are set correctly.</span></span>|  
|<span data-ttu-id="49421-166">BCP_FMT_SERVER_COL</span><span class="sxs-lookup"><span data-stu-id="49421-166">BCP_FMT_SERVER_COL</span></span>|<span data-ttu-id="49421-167">INT</span><span class="sxs-lookup"><span data-stu-id="49421-167">INT</span></span>|<span data-ttu-id="49421-168">Posizione ordinale della colonna nel database.</span><span class="sxs-lookup"><span data-stu-id="49421-168">Ordinal position of the column in the database</span></span>|  
|<span data-ttu-id="49421-169">BCP_FMT_COLLATION</span><span class="sxs-lookup"><span data-stu-id="49421-169">BCP_FMT_COLLATION</span></span>|<span data-ttu-id="49421-170">LPCSTR</span><span class="sxs-lookup"><span data-stu-id="49421-170">LPCSTR</span></span>|<span data-ttu-id="49421-171">Nome delle regole di confronto.</span><span class="sxs-lookup"><span data-stu-id="49421-171">Collation name.</span></span>|  
  
 <span data-ttu-id="49421-172">*pValue*</span><span class="sxs-lookup"><span data-stu-id="49421-172">*pValue*</span></span>  
 <span data-ttu-id="49421-173">Puntatore al valore da associare alla *Proprietà*.</span><span class="sxs-lookup"><span data-stu-id="49421-173">Is the pointer to the value to associate to the *property*.</span></span> <span data-ttu-id="49421-174">Consente di impostare singolarmente ogni proprietà di formato di colonna.</span><span class="sxs-lookup"><span data-stu-id="49421-174">It allows each column format property to be set individually.</span></span>  
  
 <span data-ttu-id="49421-175">*cbValue*</span><span class="sxs-lookup"><span data-stu-id="49421-175">*cbvalue*</span></span>  
 <span data-ttu-id="49421-176">Lunghezza in byte del buffer delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="49421-176">Is the length of the property buffer in bytes.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="49421-177">Restituisce</span><span class="sxs-lookup"><span data-stu-id="49421-177">Returns</span></span>  
 <span data-ttu-id="49421-178">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="49421-178">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49421-179">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="49421-179">Remarks</span></span>  
 <span data-ttu-id="49421-180">Questa funzione sostituisce la funzione **bcp_colfmt** .</span><span class="sxs-lookup"><span data-stu-id="49421-180">This function supersedes the **bcp_colfmt** function.</span></span> <span data-ttu-id="49421-181">Tutte le funzionalità di **bcp_colfmt** sono disponibili nella **bcp_setcolfmt** funzione.</span><span class="sxs-lookup"><span data-stu-id="49421-181">All the functionality of **bcp_colfmt** is provided in **bcp_setcolfmt** function.</span></span> <span data-ttu-id="49421-182">Sono inoltre supportate le regole di confronto delle colonne.</span><span class="sxs-lookup"><span data-stu-id="49421-182">In addition, support for column collation is also provided.</span></span> <span data-ttu-id="49421-183">È consigliabile impostare gli attributi di formato di colonna seguenti nell'ordine indicato:</span><span class="sxs-lookup"><span data-stu-id="49421-183">It is recommended that the following column format attributes be set in the order given below:</span></span>  
  
 <span data-ttu-id="49421-184">BCP_FMT_SERVER_COL</span><span class="sxs-lookup"><span data-stu-id="49421-184">BCP_FMT_SERVER_COL</span></span>  
  
 <span data-ttu-id="49421-185">BCP_FMT_DATA_LEN</span><span class="sxs-lookup"><span data-stu-id="49421-185">BCP_FMT_DATA_LEN</span></span>  
  
 <span data-ttu-id="49421-186">BCP_FMT_TYPE</span><span class="sxs-lookup"><span data-stu-id="49421-186">BCP_FMT_TYPE</span></span>  
  
 <span data-ttu-id="49421-187">La funzione **bcp_setcolfmt** consente di specificare il formato del file utente per le copie bulk.</span><span class="sxs-lookup"><span data-stu-id="49421-187">The **bcp_setcolfmt** function allows you to specify the user-file format for bulk copies.</span></span> <span data-ttu-id="49421-188">Per la copia bulk, un formato contiene le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="49421-188">For bulk copy, a format contains the following parts:</span></span>  
  
-   <span data-ttu-id="49421-189">Un mapping dalle colonne del file utente alle colonne del database.</span><span class="sxs-lookup"><span data-stu-id="49421-189">A mapping from user-file columns to database columns.</span></span>  
  
-   <span data-ttu-id="49421-190">Il tipo di dati di ogni colonna del file utente.</span><span class="sxs-lookup"><span data-stu-id="49421-190">The data type of each user-file column.</span></span>  
  
-   <span data-ttu-id="49421-191">La lunghezza dell'indicatore facoltativo per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="49421-191">The length of the optional indicator for each column.</span></span>  
  
-   <span data-ttu-id="49421-192">La lunghezza massima dei dati per ogni colonna del file utente.</span><span class="sxs-lookup"><span data-stu-id="49421-192">The maximum length of data per user-file column.</span></span>  
  
-   <span data-ttu-id="49421-193">La sequenza di byte di terminazione facoltativa per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="49421-193">The optional terminating byte sequence for each column.</span></span>  
  
-   <span data-ttu-id="49421-194">La lunghezza della sequenza di byte di terminazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="49421-194">The length of the optional terminating byte sequence.</span></span>  
  
 <span data-ttu-id="49421-195">Ogni chiamata a **bcp_setcolfmt** specifica il formato per una colonna del file utente.</span><span class="sxs-lookup"><span data-stu-id="49421-195">Each call to **bcp_setcolfmt** specifies the format for one user-file column.</span></span> <span data-ttu-id="49421-196">Ad esempio, per modificare le impostazioni predefinite per tre colonne in un file di dati utente a cinque colonne, chiamare prima [bcp_columns](bcp-columns.md)**(5)**, quindi chiamare **bcp_setcolfmt** cinque volte, con tre di queste chiamate che impostano il formato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="49421-196">For example, to change the default settings for three columns in a five-column user data file, first call [bcp_columns](bcp-columns.md)**(5)**, and then call **bcp_setcolfmt** five times, with three of those calls setting your custom format.</span></span> <span data-ttu-id="49421-197">Per le due chiamate rimanenti, impostare BCP_FMT_TYPE su 0 e impostare rispettivamente BCP_FMT_INDICATOR_LENGTH, BCP_FMT_DATA_LEN e *cbValue* su 0, SQL_VARLEN_DATA e 0.</span><span class="sxs-lookup"><span data-stu-id="49421-197">For the remaining two calls, set BCP_FMT_TYPE to 0, and set BCP_FMT_INDICATOR_LENGTH, BCP_FMT_DATA_LEN, and *cbValue* to 0, SQL_VARLEN_DATA, and 0 respectively.</span></span> <span data-ttu-id="49421-198">Questa procedura consente di copiare tutte e cinque le colonne, tre con il formato personalizzato e due con il formato predefinito.</span><span class="sxs-lookup"><span data-stu-id="49421-198">This procedure copies all five columns, three with your customized format and two with the default format.</span></span>  
  
 <span data-ttu-id="49421-199">Prima di chiamare **bcp_setcolfmt**, è necessario chiamare la funzione **bcp_columns** .</span><span class="sxs-lookup"><span data-stu-id="49421-199">The **bcp_columns** function must be called before calling **bcp_setcolfmt**.</span></span>  
  
 <span data-ttu-id="49421-200">È necessario chiamare **bcp_setcolfmt** una volta per ogni proprietà di ogni colonna del file utente.</span><span class="sxs-lookup"><span data-stu-id="49421-200">You must call **bcp_setcolfmt** once for each property of each column in the user file.</span></span>  
  
 <span data-ttu-id="49421-201">Non è necessario copiare tutti i dati di un file utente nella tabella di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="49421-201">You do not need to copy all data in a user file to the SQL Server table.</span></span> <span data-ttu-id="49421-202">Per ignorare una colonna, specificarne il formato dei dati impostando il parametro BCP_FMT_SERVER_COL su 0.</span><span class="sxs-lookup"><span data-stu-id="49421-202">To skip a column, specify the format of the data for the column, setting the BCP_FMT_SERVER_COL parameter to 0.</span></span> <span data-ttu-id="49421-203">Se si desidera ignorare una colonna, è necessario specificarne il tipo.</span><span class="sxs-lookup"><span data-stu-id="49421-203">If you want to skip a column, you must specify its type.</span></span>  
  
 <span data-ttu-id="49421-204">È possibile utilizzare la funzione [bcp_writefmt](bcp-writefmt.md) per salvare in modo permanente la specifica di formato.</span><span class="sxs-lookup"><span data-stu-id="49421-204">The [bcp_writefmt](bcp-writefmt.md) function can be used to persist the format specification.</span></span>  
  
## <a name="bcp_setcolfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="49421-205">Supporto di bcp_setcolfmt per le caratteristiche avanzate di data e ora</span><span class="sxs-lookup"><span data-stu-id="49421-205">bcp_setcolfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="49421-206">I tipi utilizzati con la proprietà BCP_FMT_TYPE per i tipi data/ora sono specificati nelle [modifiche della copia bulk per i tipi di data e ora avanzati &#40;OLE DB e ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="49421-206">The types used with the BCP_FMT_TYPE property for date/time types are as specified in [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="49421-207">Per ulteriori informazioni, vedere [miglioramenti di data e ora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="49421-207">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49421-208">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49421-208">See Also</span></span>  
 [<span data-ttu-id="49421-209">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="49421-209">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  