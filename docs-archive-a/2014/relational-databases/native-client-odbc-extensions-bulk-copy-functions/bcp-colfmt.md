---
title: bcp_colfmt | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_colfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_colfmt function
ms.assetid: 5c3b6299-80c7-4e84-8e69-4ff33009548e
author: rothja
ms.author: jroth
ms.openlocfilehash: f646f3aaf9a8f640d829020bd6762c07c406b61f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725696"
---
# <a name="bcp_colfmt"></a><span data-ttu-id="81a80-102">bcp_colfmt</span><span class="sxs-lookup"><span data-stu-id="81a80-102">bcp_colfmt</span></span>
  <span data-ttu-id="81a80-103">Specifica il formato di origine o di destinazione dei dati in un file utente.</span><span class="sxs-lookup"><span data-stu-id="81a80-103">Specifies the source or target format of the data in a user file.</span></span> <span data-ttu-id="81a80-104">Quando viene utilizzato come formato di origine, **bcp_colfmt** specifica il formato di un file di dati esistente utilizzato come origine dei dati in una copia bulk in una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabella.</span><span class="sxs-lookup"><span data-stu-id="81a80-104">When used as a source format, **bcp_colfmt** specifies the format of an existing data file used as the source of data in a bulk copy to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="81a80-105">Quando viene utilizzato come formato di destinazione, il file di dati viene creato utilizzando i formati di colonna specificati con **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="81a80-105">When used as a target format, the data file is created using the column formats specified with **bcp_colfmt**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81a80-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81a80-106">Syntax</span></span>  
  
```  
  
RETCODE bcp_colfmt (  
HDBC   
hdbc  
,  
INT  
idxUserDataCol  
,  
BYTE   
eUserDataType  
,  
INT   
cbIndicator  
,  
DBINT   
cbUserData  
,  
LPCBYTE   
pUserDataTerm  
,  
INT   
cbUserDataTerm  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="81a80-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="81a80-107">Arguments</span></span>  
 <span data-ttu-id="81a80-108">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="81a80-108">*hdbc*</span></span>  
 <span data-ttu-id="81a80-109">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="81a80-109">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="81a80-110">*idxUserDataCol*</span><span class="sxs-lookup"><span data-stu-id="81a80-110">*idxUserDataCol*</span></span>  
 <span data-ttu-id="81a80-111">Numero ordinale di colonna nel file di dati dell'utente per il quale viene specificato il formato.</span><span class="sxs-lookup"><span data-stu-id="81a80-111">Is the ordinal column number in the user data file for which the format is being specified.</span></span> <span data-ttu-id="81a80-112">La prima colonna è 1.</span><span class="sxs-lookup"><span data-stu-id="81a80-112">The first column is 1.</span></span>  
  
 <span data-ttu-id="81a80-113">*eUserDataType*</span><span class="sxs-lookup"><span data-stu-id="81a80-113">*eUserDataType*</span></span>  
 <span data-ttu-id="81a80-114">Tipo di dati della colonna nel file utente.</span><span class="sxs-lookup"><span data-stu-id="81a80-114">Is the data type of this column in the user file.</span></span> <span data-ttu-id="81a80-115">Se è diverso dal tipo di dati della colonna corrispondente nella tabella di database (*idxServerColumn*), la copia bulk converte i dati, se possibile.</span><span class="sxs-lookup"><span data-stu-id="81a80-115">If different from the data type of the corresponding column in the database table (*idxServerColumn*), bulk copy converts the data if possible.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]<span data-ttu-id="81a80-116">è stato introdotto il supporto per i token del tipo di dati SQLXML e SQLUDT nel parametro *eUserDataType* .</span><span class="sxs-lookup"><span data-stu-id="81a80-116">introduced support for SQLXML and SQLUDT data type tokens in the *eUserDataType* parameter.</span></span>  
  
 <span data-ttu-id="81a80-117">Il parametro *eUserDataType* viene enumerato in base ai [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] token del tipo di dati in sqlncli. h e non negli enumeratori dei tipi di dati ODBC C.</span><span class="sxs-lookup"><span data-stu-id="81a80-117">The *eUserDataType* parameter is enumerated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type tokens in sqlncli.h, not the ODBC C data type enumerators.</span></span> <span data-ttu-id="81a80-118">È ad esempio possibile specificare una stringa di caratteri SQL_C_CHAR di tipo ODBC utilizzando il tipo SQLCHARACTER specifico di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81a80-118">For example, you can specify a character string, ODBC type SQL_C_CHAR, using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific type SQLCHARACTER.</span></span>  
  
 <span data-ttu-id="81a80-119">Per specificare la rappresentazione predefinita dei dati per il tipo di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], impostare questo parametro su 0.</span><span class="sxs-lookup"><span data-stu-id="81a80-119">To specify the default data representation for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, set this parameter to 0.</span></span>  
  
 <span data-ttu-id="81a80-120">Per una copia bulk [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un file, quando *eUserDataType* è SqlDecimal o SQLNUMERIC:</span><span class="sxs-lookup"><span data-stu-id="81a80-120">For a bulk copy out of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] into a file, when *eUserDataType* is SQLDECIMAL or SQLNUMERIC:</span></span>  
  
-   <span data-ttu-id="81a80-121">Se la colonna di origine non è **Decimal** o **numeric**, vengono utilizzate la precisione e la scala predefinite.</span><span class="sxs-lookup"><span data-stu-id="81a80-121">If the source column is not **decimal** or **numeric**, the default precision and scale are used.</span></span>  
  
-   <span data-ttu-id="81a80-122">Se la colonna di origine è **Decimal** o **numeric**, vengono utilizzate la precisione e la scala della colonna di origine.</span><span class="sxs-lookup"><span data-stu-id="81a80-122">If the source column is **decimal** or **numeric**, the precision and scale of the source column are used.</span></span>  
  
 <span data-ttu-id="81a80-123">*cbIndicator*</span><span class="sxs-lookup"><span data-stu-id="81a80-123">*cbIndicator*</span></span>  
 <span data-ttu-id="81a80-124">Lunghezza, espressa in byte, di un indicatore di lunghezza o Null nei dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="81a80-124">Is the length, in bytes, of a length/null indicator within the column data.</span></span> <span data-ttu-id="81a80-125">Valori di lunghezza di indicatore validi sono 0 (nel caso in cui non venga utilizzato un indicatore), 1, 2, 4 o 8.</span><span class="sxs-lookup"><span data-stu-id="81a80-125">Valid indicator length values are 0 (when using no indicator), 1, 2, 4, or 8.</span></span>  
  
 <span data-ttu-id="81a80-126">Per specificare l'utilizzo di un indicatore di copia bulk predefinito, impostare questo parametro su SQL_VARLEN_DATA.</span><span class="sxs-lookup"><span data-stu-id="81a80-126">To specify default bulk copy indicator usage, set this parameter to SQL_VARLEN_DATA.</span></span>  
  
 <span data-ttu-id="81a80-127">Gli indicatori vengono visualizzati in memoria direttamente prima dei dati e nel file di dati immediatamente prima dei dati a cui si riferiscono.</span><span class="sxs-lookup"><span data-stu-id="81a80-127">Indicators appear in memory directly before any data, and in the data file directly before the data to which they apply.</span></span>  
  
 <span data-ttu-id="81a80-128">Se si utilizzano più modalità per specificare la lunghezza delle colonne del file di dati, ad esempio un indicatore e una lunghezza di colonna massima o un indicatore e una sequenza di caratteri di terminazione, la copia bulk sceglie quella che comporta la copia del minor numero di dati.</span><span class="sxs-lookup"><span data-stu-id="81a80-128">If more than one means of specifying a data file column length is used (such as an indicator and a maximum column length, or an indicator and a terminator sequence), bulk copy chooses the one that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="81a80-129">I file di dati generati dalla copia bulk quando il formato dei dati non viene modificato dall'utente contengono indicatori se la lunghezza dei dati di colonna può variare o se la colonna può accettare NULL come valore.</span><span class="sxs-lookup"><span data-stu-id="81a80-129">Data files generated by bulk copy when no user intervention adjusts the format of the data contain indicators when the column data can vary in length or the column can accept NULL as a value.</span></span>  
  
 <span data-ttu-id="81a80-130">*cbUserData*</span><span class="sxs-lookup"><span data-stu-id="81a80-130">*cbUserData*</span></span>  
 <span data-ttu-id="81a80-131">Lunghezza massima, espressa in byte, dei dati della colonna nel file utente, senza includere la lunghezza di un carattere di terminazione o di un indicatore di lunghezza.</span><span class="sxs-lookup"><span data-stu-id="81a80-131">Is the maximum length, in bytes, of this column's data in the user file, not including the length of any length indicator or terminator.</span></span>  
  
 <span data-ttu-id="81a80-132">L'impostazione di *cbUserData* su SQL_NULL_DATA indica che tutti i valori nella colonna del file di dati sono o devono essere impostati su null.</span><span class="sxs-lookup"><span data-stu-id="81a80-132">Setting *cbUserData* to SQL_NULL_DATA indicates that all values in the data file column are, or should be set to NULL.</span></span>  
  
 <span data-ttu-id="81a80-133">L'impostazione di *cbUserData* su SQL_VARLEN_DATA indica che il sistema deve determinare la lunghezza dei dati in ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="81a80-133">Setting *cbUserData* to SQL_VARLEN_DATA indicates that the system should determine the length of data in each column.</span></span> <span data-ttu-id="81a80-134">Per alcune colonne, ciò può indicare che viene generato un indicatore di lunghezza o Null da anteporre ai dati in una copia da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o che l'indicatore è previsto nei dati copiati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81a80-134">For some columns, this could mean that a length/null indicator is generated to precede data on a copy from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or that the indicator is expected in data copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="81a80-135">Per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] i tipi di dati character e binary, *cbUserData* può essere SQL_VARLEN_DATA, SQL_NULL_DATA, 0 o un valore positivo.</span><span class="sxs-lookup"><span data-stu-id="81a80-135">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, *cbUserData* can be SQL_VARLEN_DATA, SQL_NULL_DATA, 0, or some positive value.</span></span> <span data-ttu-id="81a80-136">Se *cbUserData* è SQL_VARLEN_DATA, il sistema utilizza l'indicatore di lunghezza, se presente, o una sequenza di caratteri di terminazione per determinare la lunghezza dei dati.</span><span class="sxs-lookup"><span data-stu-id="81a80-136">If *cbUserData* is SQL_VARLEN_DATA, the system uses either the length indicator, if present, or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="81a80-137">Se vengono specificati sia un indicatore di lunghezza che una sequenza di caratteri di terminazione, la copia bulk utilizza la modalità che comporta la copia del minor numero di dati.</span><span class="sxs-lookup"><span data-stu-id="81a80-137">If both a length indicator and a terminator sequence are supplied, bulk copy uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="81a80-138">Se *cbUserData* è SQL_VARLEN_DATA, il tipo di dati è di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo carattere o binario e non viene specificato né un indicatore di lunghezza né una sequenza di caratteri di terminazione, il sistema restituisce un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="81a80-138">If *cbUserData* is SQL_VARLEN_DATA, the data type is an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span>  
  
 <span data-ttu-id="81a80-139">Se *cbUserData* è 0 o un valore positivo, il sistema usa *cbUserData* come lunghezza massima dei dati.</span><span class="sxs-lookup"><span data-stu-id="81a80-139">If *cbUserData* is 0 or a positive value, the system uses *cbUserData* as the maximum data length.</span></span> <span data-ttu-id="81a80-140">Se, tuttavia, oltre a un *cbUserData* positivo, viene specificato un indicatore di lunghezza o una sequenza di caratteri di terminazione, il sistema determina la lunghezza dei dati usando il metodo che comporta la copia della quantità minima di dati.</span><span class="sxs-lookup"><span data-stu-id="81a80-140">However, if, in addition to a positive *cbUserData*, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="81a80-141">Il valore *cbUserData* rappresenta il numero di byte dei dati.</span><span class="sxs-lookup"><span data-stu-id="81a80-141">The *cbUserData* value represents the count of bytes of data.</span></span> <span data-ttu-id="81a80-142">Se i dati di tipo carattere sono rappresentati da caratteri wide Unicode, un valore positivo per il parametro *cbUserData* rappresenta il numero di caratteri moltiplicato per la dimensione, espressa in byte, di ogni carattere.</span><span class="sxs-lookup"><span data-stu-id="81a80-142">If character data is represented by Unicode wide characters, then a positive *cbUserData* parameter value represents the number of characters multiplied by the size, in bytes, of each character.</span></span>  
  
 <span data-ttu-id="81a80-143">*pUserDataTerm*</span><span class="sxs-lookup"><span data-stu-id="81a80-143">*pUserDataTerm*</span></span>  
 <span data-ttu-id="81a80-144">Sequenza di caratteri di terminazione da utilizzare per la colonna.</span><span class="sxs-lookup"><span data-stu-id="81a80-144">Is the terminator sequence to be used for this column.</span></span> <span data-ttu-id="81a80-145">Questo parametro risulta particolarmente utile per i dati di tipo carattere, in quanto tutti gli altri tipi hanno una lunghezza fissa o, nel caso dei dati binari, richiedono un indicatore di lunghezza per registrare in modo accurato il numero di byte presenti.</span><span class="sxs-lookup"><span data-stu-id="81a80-145">This parameter is useful mainly for character data types because all other types are of fixed length or, in the case of binary data, require an indicator of length to accurately record the number of bytes present.</span></span>  
  
 <span data-ttu-id="81a80-146">Per evitare di terminare i dati estratti o per indicare che i dati di un file utente non devono essere terminati, impostare questo parametro su NULL.</span><span class="sxs-lookup"><span data-stu-id="81a80-146">To avoid terminating extracted data, or to indicate that data in a user file is not terminated, set this parameter to NULL.</span></span>  
  
 <span data-ttu-id="81a80-147">Se si utilizzano più modalità per definire la lunghezza delle colonne di un file utente, ad esempio un carattere di terminazione e un indicatore di lunghezza o un carattere di terminazione e una lunghezza di colonna massima, la copia bulk sceglierà quella che comporta la copia del minor numero di dati.</span><span class="sxs-lookup"><span data-stu-id="81a80-147">If more than one means of specifying a user-file column length is used (such as a terminator and a length indicator, or a terminator and a maximum column length), bulk copy chooses the one that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="81a80-148">L'API della copia bulk esegue la conversione dei caratteri da Unicode a MBCS in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="81a80-148">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="81a80-149">Verificare attentamente che la stringa di byte del carattere di terminazione e la lunghezza della stringa di byte siano impostate correttamente.</span><span class="sxs-lookup"><span data-stu-id="81a80-149">Care must be taken to ensure that both the terminator byte string and the length of the byte string are set correctly.</span></span>  
  
 <span data-ttu-id="81a80-150">*pUserDataTerm*</span><span class="sxs-lookup"><span data-stu-id="81a80-150">*cbUserDataTerm*</span></span>  
 <span data-ttu-id="81a80-151">Lunghezza, espressa in byte, della sequenza di caratteri di terminazione da utilizzare per la colonna.</span><span class="sxs-lookup"><span data-stu-id="81a80-151">Is the length, in bytes, of the terminator sequence to be used for this column.</span></span> <span data-ttu-id="81a80-152">Se non sono presenti caratteri di terminazione nei dati o non si desidera includerli, impostare questo valore su 0.</span><span class="sxs-lookup"><span data-stu-id="81a80-152">If no terminator is present or desired in the data, set this value to 0.</span></span>  
  
 <span data-ttu-id="81a80-153">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="81a80-153">*idxServerCol*</span></span>  
 <span data-ttu-id="81a80-154">Posizione ordinale della colonna nella tabella di database.</span><span class="sxs-lookup"><span data-stu-id="81a80-154">Is the ordinal position of the column in the database table.</span></span> <span data-ttu-id="81a80-155">Il numero della prima colonna è 1.</span><span class="sxs-lookup"><span data-stu-id="81a80-155">The first column number is 1.</span></span> <span data-ttu-id="81a80-156">La posizione ordinale di una colonna viene segnalata da [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="81a80-156">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
 <span data-ttu-id="81a80-157">Se questo valore è 0, la copia bulk ignora la colonna nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="81a80-157">If this value is 0, bulk copy ignores the column in the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="81a80-158">Restituisce</span><span class="sxs-lookup"><span data-stu-id="81a80-158">Returns</span></span>  
 <span data-ttu-id="81a80-159">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="81a80-159">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81a80-160">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="81a80-160">Remarks</span></span>  
 <span data-ttu-id="81a80-161">La funzione **bcp_colfmt** consente di specificare il formato del file utente per le copie bulk.</span><span class="sxs-lookup"><span data-stu-id="81a80-161">The **bcp_colfmt** function allows you to specify the user-file format for bulk copies.</span></span> <span data-ttu-id="81a80-162">Per la copia bulk, un formato contiene le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="81a80-162">For bulk copy, a format contains the following parts:</span></span>  
  
-   <span data-ttu-id="81a80-163">Un mapping dalle colonne del file utente alle colonne del database.</span><span class="sxs-lookup"><span data-stu-id="81a80-163">A mapping from user-file columns to database columns.</span></span>  
  
-   <span data-ttu-id="81a80-164">Il tipo di dati di ogni colonna del file utente.</span><span class="sxs-lookup"><span data-stu-id="81a80-164">The data type of each user-file column.</span></span>  
  
-   <span data-ttu-id="81a80-165">La lunghezza dell'indicatore facoltativo per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="81a80-165">The length of the optional indicator for each column.</span></span>  
  
-   <span data-ttu-id="81a80-166">La lunghezza massima dei dati per ogni colonna del file utente.</span><span class="sxs-lookup"><span data-stu-id="81a80-166">The maximum length of data per user-file column.</span></span>  
  
-   <span data-ttu-id="81a80-167">La sequenza di byte di terminazione facoltativa per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="81a80-167">The optional terminating byte sequence for each column.</span></span>  
  
-   <span data-ttu-id="81a80-168">La lunghezza della sequenza di byte di terminazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="81a80-168">The length of the optional terminating byte sequence.</span></span>  
  
 <span data-ttu-id="81a80-169">Ogni chiamata a **bcp_colfmt** specifica il formato per una colonna del file utente.</span><span class="sxs-lookup"><span data-stu-id="81a80-169">Each call to **bcp_colfmt** specifies the format for one user-file column.</span></span> <span data-ttu-id="81a80-170">Ad esempio, per modificare le impostazioni predefinite per tre colonne in un file di dati utente a cinque colonne, chiamare prima [bcp_columns](bcp-columns.md)**(5)**, quindi chiamare **bcp_colfmt** cinque volte, con tre di queste chiamate che impostano il formato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="81a80-170">For example, to change the default settings for three columns in a five-column user data file, first call [bcp_columns](bcp-columns.md)**(5)**, and then call **bcp_colfmt** five times, with three of those calls setting your custom format.</span></span> <span data-ttu-id="81a80-171">Per le due chiamate rimanenti, impostare *eUserDataType* su 0, quindi impostare *cbIndicator*, *cbUserData*e *cbUserDataTerm* su 0, SQL_VARLEN_DATA e 0 rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="81a80-171">For the remaining two calls, set *eUserDataType* to 0, and set *cbIndicator*, *cbUserData*, and *cbUserDataTerm* to 0, SQL_VARLEN_DATA, and 0 respectively.</span></span> <span data-ttu-id="81a80-172">Questa procedura consente di copiare tutte e cinque le colonne, tre con il formato personalizzato e due con il formato predefinito.</span><span class="sxs-lookup"><span data-stu-id="81a80-172">This procedure copies all five columns, three with your customized format and two with the default format.</span></span>  
  
 <span data-ttu-id="81a80-173">Per *cbIndicator*, un valore pari a 8 per indicare che un tipo di valore di grandi dimensioni è ora valido.</span><span class="sxs-lookup"><span data-stu-id="81a80-173">For *cbIndicator*, a value of 8 to indicate a large value type is now valid.</span></span> <span data-ttu-id="81a80-174">Se si specifica il prefisso per un campo la cui colonna corrispondente è un nuovo tipo max, può essere impostato solo su 8.</span><span class="sxs-lookup"><span data-stu-id="81a80-174">If the prefix is specified for a field whose corresponding column is a new max type, it can only be set to 8.</span></span> <span data-ttu-id="81a80-175">Per informazioni dettagliate, vedere [bcp_bind](bcp-bind.md).</span><span class="sxs-lookup"><span data-stu-id="81a80-175">For details, see [bcp_bind](bcp-bind.md).</span></span>  
  
 <span data-ttu-id="81a80-176">La funzione **bcp_columns** deve essere chiamata prima di qualsiasi chiamata a **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="81a80-176">The **bcp_columns** function must be called before any calls to **bcp_colfmt**.</span></span>  
  
 <span data-ttu-id="81a80-177">È necessario chiamare **bcp_colfmt** una volta per ogni colonna del file utente.</span><span class="sxs-lookup"><span data-stu-id="81a80-177">You must call **bcp_colfmt** once for each column in the user file.</span></span>  
  
 <span data-ttu-id="81a80-178">La chiamata di **bcp_colfmt** più di una volta per ogni colonna del file utente genera un errore.</span><span class="sxs-lookup"><span data-stu-id="81a80-178">Calling **bcp_colfmt** more than once for any user-file column causes an error.</span></span>  
  
 <span data-ttu-id="81a80-179">Non è necessario copiare tutti i dati di un file utente nella tabella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81a80-179">You do not need to copy all data in a user file to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="81a80-180">Per ignorare una colonna, specificare il formato dei dati per la colonna, impostando il parametro *idxServerCol su* su 0.</span><span class="sxs-lookup"><span data-stu-id="81a80-180">To skip a column, specify the format of the data for the column, setting the *idxServerCol* parameter to 0.</span></span> <span data-ttu-id="81a80-181">Se si desidera ignorare una colonna, è necessario specificarne il tipo.</span><span class="sxs-lookup"><span data-stu-id="81a80-181">If you want to skip a column, you must specify its type.</span></span>  
  
 <span data-ttu-id="81a80-182">È possibile utilizzare la funzione [bcp_writefmt](bcp-writefmt.md) per salvare in modo permanente la specifica di formato.</span><span class="sxs-lookup"><span data-stu-id="81a80-182">The [bcp_writefmt](bcp-writefmt.md) function can be used to persist the format specification.</span></span>  
  
## <a name="bcp_colfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="81a80-183">Supporto di bcp_colfmt per le caratteristiche avanzate di data e ora</span><span class="sxs-lookup"><span data-stu-id="81a80-183">bcp_colfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="81a80-184">Per informazioni sui tipi utilizzati con il parametro *eUserDataType* per i tipi data/ora, vedere la pagina relativa alle [modifiche di copia bulk per i tipi di data e ora avanzati &#40;OLE DB e&#41;ODBC ](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="81a80-184">For information aboutt he types used with the *eUserDataType* parameter for date/time types, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="81a80-185">Per ulteriori informazioni, vedere [miglioramenti di data e ora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="81a80-185">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81a80-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81a80-186">See Also</span></span>  
 [<span data-ttu-id="81a80-187">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="81a80-187">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
