---
title: bcp_bind | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_bind
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_bind function
ms.assetid: 6e335a5c-64b2-4bcf-a88f-35dc9393f329
author: rothja
ms.author: jroth
ms.openlocfilehash: db0a58398bf47bd0bb96bd1ef587d41890ed8461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714332"
---
# <a name="bcp_bind"></a><span data-ttu-id="0210c-102">bcp_bind</span><span class="sxs-lookup"><span data-stu-id="0210c-102">bcp_bind</span></span>
  <span data-ttu-id="0210c-103">Vengono associati dati provenienti da una variabile di programma a una colonna di tabella per eseguire la copia bulk in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0210c-103">Binds data from a program variable to a table column for bulk copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0210c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0210c-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_bind (  
HDBC   
hdbc  
,   
LPCBYTE   
pData  
,  
INT   
cbIndicator  
,  
DBINT   
cbData  
,  
LPCBYTE   
pTerm  
,  
INT   
cbTerm  
,  
INT   
eDataType  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="0210c-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0210c-105">Arguments</span></span>  
 <span data-ttu-id="0210c-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="0210c-106">*hdbc*</span></span>  
 <span data-ttu-id="0210c-107">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="0210c-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="0210c-108">*pData*</span><span class="sxs-lookup"><span data-stu-id="0210c-108">*pData*</span></span>  
 <span data-ttu-id="0210c-109">Puntatore ai dati copiati.</span><span class="sxs-lookup"><span data-stu-id="0210c-109">Is a pointer to the data copied.</span></span> <span data-ttu-id="0210c-110">Se *eDataType* è SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SqlBinary, SQLNCHAR o SQLIMAGE, *pData* può essere null.</span><span class="sxs-lookup"><span data-stu-id="0210c-110">If *eDataType* is SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR or SQLIMAGE, *pData* can be NULL.</span></span> <span data-ttu-id="0210c-111">Un valore NULL *pData* indica che i valori di dati Long verranno inviati a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in blocchi utilizzando [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="0210c-111">A NULL *pData* indicates that long data values will be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in chunks using [bcp_moretext](bcp-moretext.md).</span></span> <span data-ttu-id="0210c-112">L'utente deve impostare *pData* su null solo se la colonna corrispondente al campo associato utente è una colonna BLOB, in caso contrario **bcp_bind** avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="0210c-112">The user should only set *pData* to NULL if the column corresponding to the user bound field is a BLOB column otherwise **bcp_bind** will fail.</span></span>  
  
 <span data-ttu-id="0210c-113">Se presenti nei dati, gli indicatori vengono visualizzati in memoria direttamente prima dei dati.</span><span class="sxs-lookup"><span data-stu-id="0210c-113">If indicators are present in the data, they appear in memory directly before the data.</span></span> <span data-ttu-id="0210c-114">Il parametro *pData* punta alla variabile indicatore in questo caso e la larghezza dell'indicatore, il parametro *cbIndicator* , viene utilizzata dalla copia bulk per indirizzare correttamente i dati utente.</span><span class="sxs-lookup"><span data-stu-id="0210c-114">The *pData* parameter points to the indicator variable in this case, and the width of the indicator, the *cbIndicator* parameter, is used by bulk copy to address user data correctly.</span></span>  
  
 <span data-ttu-id="0210c-115">*cbIndicator*</span><span class="sxs-lookup"><span data-stu-id="0210c-115">*cbIndicator*</span></span>  
 <span data-ttu-id="0210c-116">Lunghezza, espressa in byte, di un indicatore di lunghezza o Null per i dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="0210c-116">Is the length, in bytes, of a length or null indicator for the column's data.</span></span> <span data-ttu-id="0210c-117">Valori di lunghezza di indicatore validi sono 0 (nel caso in cui non venga utilizzato un indicatore), 1, 2, 4 o 8.</span><span class="sxs-lookup"><span data-stu-id="0210c-117">Valid indicator length values are 0 (when using no indicator), 1, 2, 4, or 8.</span></span> <span data-ttu-id="0210c-118">Gli indicatori vengono visualizzati in memoria direttamente prima di qualsiasi dato.</span><span class="sxs-lookup"><span data-stu-id="0210c-118">Indicators appear in memory directly before any data.</span></span> <span data-ttu-id="0210c-119">La definizione del tipo di struttura seguente, ad esempio, potrebbe essere utilizzata per inserire valori integer in una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante la copia bulk:</span><span class="sxs-lookup"><span data-stu-id="0210c-119">For example, the following structure type definition could be used to insert integer values into an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table using bulk copy:</span></span>  
  
```  
typedef struct tagBCPBOUNDINT  
    {  
    int iIndicator;  
    int Value;  
    } BCPBOUNDINT;  
```  
  
 <span data-ttu-id="0210c-120">Nel caso di esempio, il parametro *pData* verrebbe impostato sull'indirizzo di un'istanza dichiarata della struttura, ovvero l'indirizzo del membro della struttura BCPBOUNDINT *iIndicator* .</span><span class="sxs-lookup"><span data-stu-id="0210c-120">In the example case, the *pData* parameter would be set to the address of a declared instance of the structure, the address of the BCPBOUNDINT *iIndicator* structure member.</span></span> <span data-ttu-id="0210c-121">Il parametro *cbIndicator* verrà impostato sulla dimensione di un numero intero (sizeof (int)) e il parametro *cbData* verrà nuovamente impostato sulla dimensione di un numero intero (sizeof (int)).</span><span class="sxs-lookup"><span data-stu-id="0210c-121">The *cbIndicator* parameter would be set to the size of an integer (sizeof(int)), and the *cbData* parameter would again be set to the size of an integer (sizeof(int)).</span></span> <span data-ttu-id="0210c-122">Per eseguire una copia bulk di una riga nel server contenente un valore NULL per la colonna associata, il valore del membro *iIndicator* dell'istanza deve essere impostato su SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="0210c-122">To bulk copy a row to the server containing a NULL value for the bound column, the value of the instance's *iIndicator* member should be set to SQL_NULL_DATA.</span></span>  
  
 <span data-ttu-id="0210c-123">*cbData*</span><span class="sxs-lookup"><span data-stu-id="0210c-123">*cbData*</span></span>  
 <span data-ttu-id="0210c-124">Numero di byte dei dati nella variabile di programma che non include la lunghezza di un carattere di terminazione o di un indicatore di lunghezza o Null.</span><span class="sxs-lookup"><span data-stu-id="0210c-124">Is the count of bytes of data in the program variable, not including the length of any length or null indicator or terminator.</span></span>  
  
 <span data-ttu-id="0210c-125">L'impostazione di *cbData* su SQL_NULL_DATA indica che tutte le righe copiate nel server contengono un valore null per la colonna.</span><span class="sxs-lookup"><span data-stu-id="0210c-125">Setting *cbData* to SQL_NULL_DATA signifies that all rows copied to the server contain a NULL value for the column.</span></span>  
  
 <span data-ttu-id="0210c-126">L'impostazione di *cbData* su SQL_VARLEN_DATA indica che il sistema utilizzerà un carattere di terminazione della stringa o un altro metodo per determinare la lunghezza dei dati copiati.</span><span class="sxs-lookup"><span data-stu-id="0210c-126">Setting *cbData* to SQL_VARLEN_DATA indicates that the system will use a string terminator, or other method, to determine the length of data copied.</span></span>  
  
 <span data-ttu-id="0210c-127">Per tipi di dati a lunghezza fissa, ad esempio numeri interi, il tipo di dati indica la lunghezza dei dati al sistema.</span><span class="sxs-lookup"><span data-stu-id="0210c-127">For fixed-length data types, such as integers, the data type indicates the length of the data to the system.</span></span> <span data-ttu-id="0210c-128">Pertanto, per i tipi di dati a lunghezza fissa, *cbData* può essere SQL_VARLEN_DATA o la lunghezza dei dati in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="0210c-128">Therefore, for fixed-length data types, *cbData* can safely be SQL_VARLEN_DATA or the length of the data.</span></span>  
  
 <span data-ttu-id="0210c-129">Per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] i tipi di dati character e binary, *cbData* può essere SQL_VARLEN_DATA, SQL_NULL_DATA, un valore positivo o 0.</span><span class="sxs-lookup"><span data-stu-id="0210c-129">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, *cbData* can be SQL_VARLEN_DATA, SQL_NULL_DATA, some positive value, or 0.</span></span> <span data-ttu-id="0210c-130">Se *cbData* è SQL_VARLEN_DATA, il sistema utilizza un indicatore di lunghezza/null (se presente) o una sequenza di caratteri di terminazione per determinare la lunghezza dei dati.</span><span class="sxs-lookup"><span data-stu-id="0210c-130">If *cbData* is SQL_VARLEN_DATA, the system uses either a length/null indicator (if present) or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="0210c-131">Se vengono forniti entrambi, il sistema utilizza quello che comporta la copia del minori numero di dati.</span><span class="sxs-lookup"><span data-stu-id="0210c-131">If both are supplied, the system uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="0210c-132">Se *cbData* è SQL_VARLEN_DATA, il tipo di dati della colonna è di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo carattere o binario e non viene specificato né un indicatore di lunghezza né una sequenza di caratteri di terminazione, il sistema restituisce un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="0210c-132">If *cbData* is SQL_VARLEN_DATA, the data type of the column is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span>  
  
 <span data-ttu-id="0210c-133">Se *cbData* è 0 o un valore positivo, il sistema utilizza *cbData* come lunghezza dei dati.</span><span class="sxs-lookup"><span data-stu-id="0210c-133">If *cbData* is 0 or a positive value, the system uses *cbData* as the data length.</span></span> <span data-ttu-id="0210c-134">Tuttavia, se, oltre a un valore *cbData* positivo, viene specificato un indicatore di lunghezza o una sequenza di caratteri di terminazione, il sistema determina la lunghezza dei dati utilizzando il metodo che comporta la copia del minor numero di dati.</span><span class="sxs-lookup"><span data-stu-id="0210c-134">However, if, in addition to a positive *cbData* value, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="0210c-135">Il valore del parametro *cbData* rappresenta il numero di byte di dati.</span><span class="sxs-lookup"><span data-stu-id="0210c-135">The *cbData* parameter value represents the count of bytes of data.</span></span> <span data-ttu-id="0210c-136">Se i dati di tipo carattere sono rappresentati da caratteri wide Unicode, un valore positivo per il parametro *cbData* rappresenta il numero di caratteri moltiplicato per la dimensione in byte di ogni carattere.</span><span class="sxs-lookup"><span data-stu-id="0210c-136">If character data is represented by Unicode wide characters, then a positive *cbData* parameter value represents the number of characters multiplied by the size in bytes of each character.</span></span>  
  
 <span data-ttu-id="0210c-137">*pTerm*</span><span class="sxs-lookup"><span data-stu-id="0210c-137">*pTerm*</span></span>  
 <span data-ttu-id="0210c-138">Puntatore al modello di byte, se presente, che contrassegna la fine di questa variabile di programma.</span><span class="sxs-lookup"><span data-stu-id="0210c-138">Is a pointer to the byte pattern, if any, that marks the end of this program variable.</span></span> <span data-ttu-id="0210c-139">Le stringhe ANSI e MBCS C, ad esempio, presentano generalmente un carattere di terminazione di 1 byte (\0).</span><span class="sxs-lookup"><span data-stu-id="0210c-139">For example, ANSI and MBCS C strings usually have a 1-byte terminator (\0).</span></span>  
  
 <span data-ttu-id="0210c-140">Se non è presente alcun carattere di terminazione per la variabile, impostare *pTerm* su null.</span><span class="sxs-lookup"><span data-stu-id="0210c-140">If there is no terminator for the variable, set *pTerm* to NULL.</span></span>  
  
 <span data-ttu-id="0210c-141">È possibile utilizzare una stringa vuota ("") per definire il carattere di terminazione Null C come carattere di terminazione della variabile di programma.</span><span class="sxs-lookup"><span data-stu-id="0210c-141">You can use an empty string ("") to designate the C null terminator as the program-variable terminator.</span></span> <span data-ttu-id="0210c-142">Poiché la stringa vuota con terminazione null costituisce un singolo byte (byte del carattere di terminazione), impostare *cbTerm* su 1.</span><span class="sxs-lookup"><span data-stu-id="0210c-142">Because the null-terminated empty string constitutes a single byte (the terminator byte itself), set *cbTerm* to 1.</span></span> <span data-ttu-id="0210c-143">Per indicare, ad esempio, che la stringa in *szName* è con terminazione null e che il carattere di terminazione deve essere usato per indicare la lunghezza:</span><span class="sxs-lookup"><span data-stu-id="0210c-143">For example, to indicate that the string in *szName* is null-terminated and that the terminator should be used to indicate the length:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0,  
   SQL_VARLEN_DATA, "", 1,  
   SQLCHARACTER, 2)  
```  
  
 <span data-ttu-id="0210c-144">Un formato senza terminazione di questo esempio potrebbe indicare che i 15 caratteri devono essere copiati dalla variabile *szName* alla seconda colonna della tabella associata:</span><span class="sxs-lookup"><span data-stu-id="0210c-144">A nonterminated form of this example could indicate that 15 characters be copied from the *szName* variable to the second column of the bound table:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0, 15,   
   NULL, 0, SQLCHARACTER, 2)  
```  
  
 <span data-ttu-id="0210c-145">L'API della copia bulk esegue la conversione dei caratteri da Unicode a MBCS in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="0210c-145">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="0210c-146">Verificare che la stringa di byte del carattere di terminazione e la lunghezza della stringa di byte siano impostate correttamente.</span><span class="sxs-lookup"><span data-stu-id="0210c-146">Make sure that both the terminator byte string and the length of the byte string are set correctly.</span></span> <span data-ttu-id="0210c-147">Per indicare, ad esempio, che la stringa in *szName* è una stringa di caratteri wide Unicode, terminata dal valore del terminatore null Unicode:</span><span class="sxs-lookup"><span data-stu-id="0210c-147">For example, to indicate that the string in *szName* is a Unicode wide character string, terminated by the Unicode null terminator value:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0,   
   SQL_VARLEN_DATA, L"",  
   sizeof(WCHAR), SQLNCHAR, 2)  
```  
  
 <span data-ttu-id="0210c-148">Se la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] colonna associata è un carattere wide, non viene eseguita alcuna conversione su [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="0210c-148">If the bound [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column is wide character, no conversion is performed on [bcp_sendrow](bcp-sendrow.md).</span></span> <span data-ttu-id="0210c-149">Se la colonna di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è un tipo di carattere MBCS, la conversione da carattere wide a carattere multibyte viene eseguita quando i dati vengono inviati a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0210c-149">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column is an MBCS character type, wide character to multibyte character conversion is performed as the data is sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0210c-150">*cbTerm*</span><span class="sxs-lookup"><span data-stu-id="0210c-150">*cbTerm*</span></span>  
 <span data-ttu-id="0210c-151">Numero dei byte presenti nel carattere di terminazione per la variabile di programma, se presente.</span><span class="sxs-lookup"><span data-stu-id="0210c-151">Is the count of bytes present in the terminator for the program variable, if any.</span></span> <span data-ttu-id="0210c-152">Se non è presente alcun carattere di terminazione per la variabile, impostare *cbTerm* su 0.</span><span class="sxs-lookup"><span data-stu-id="0210c-152">If there is no terminator for the variable, set *cbTerm* to 0.</span></span>  
  
 <span data-ttu-id="0210c-153">*eDataType*</span><span class="sxs-lookup"><span data-stu-id="0210c-153">*eDataType*</span></span>  
 <span data-ttu-id="0210c-154">Tipo di dati C della variabile di programma.</span><span class="sxs-lookup"><span data-stu-id="0210c-154">Is the C data type of the program variable.</span></span> <span data-ttu-id="0210c-155">I dati della variabile di programma vengono convertiti nel tipo della colonna di database.</span><span class="sxs-lookup"><span data-stu-id="0210c-155">The data in the program variable is converted to the type of the database column.</span></span> <span data-ttu-id="0210c-156">Se questo parametro è 0, non viene eseguita alcuna conversione.</span><span class="sxs-lookup"><span data-stu-id="0210c-156">If this parameter is 0, no conversion is performed.</span></span>  
  
 <span data-ttu-id="0210c-157">Il parametro *eDataType* viene enumerato in base ai [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] token del tipo di dati in sqlncli. h e non negli enumeratori dei tipi di dati ODBC C.</span><span class="sxs-lookup"><span data-stu-id="0210c-157">The *eDataType* parameter is enumerated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type tokens in sqlncli.h, not the ODBC C data type enumerators.</span></span> <span data-ttu-id="0210c-158">È ad esempio possibile specificare un numero intero a due byte, SQL_C_SHORT di tipo ODBC, utilizzando il tipo specifico di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQLINT2.</span><span class="sxs-lookup"><span data-stu-id="0210c-158">For example, you can specify a two-byte integer, ODBC type SQL_C_SHORT, using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific type SQLINT2.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]<span data-ttu-id="0210c-159">è stato introdotto il supporto per i token del tipo di dati SQLXML e SQLUDT nel *`eDataType`* paramentor.</span><span class="sxs-lookup"><span data-stu-id="0210c-159">introduced support for SQLXML and SQLUDT data type tokens in the *`eDataType`* paramenter.</span></span>  
  
 <span data-ttu-id="0210c-160">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="0210c-160">*idxServerCol*</span></span>  
 <span data-ttu-id="0210c-161">Posizione ordinale della colonna nella tabella di database in cui vengono copiati i dati.</span><span class="sxs-lookup"><span data-stu-id="0210c-161">Is the ordinal position of the column in the database table to which the data is copied.</span></span> <span data-ttu-id="0210c-162">La prima colonna di una tabella è la colonna 1.</span><span class="sxs-lookup"><span data-stu-id="0210c-162">The first column in a table is column 1.</span></span> <span data-ttu-id="0210c-163">La posizione ordinale di una colonna viene segnalata da [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="0210c-163">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="0210c-164">Restituisce</span><span class="sxs-lookup"><span data-stu-id="0210c-164">Returns</span></span>  
 <span data-ttu-id="0210c-165">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="0210c-165">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0210c-166">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0210c-166">Remarks</span></span>  
 <span data-ttu-id="0210c-167">Utilizzare **bcp_bind** per un modo rapido ed efficiente per copiare dati da una variabile di programma in una tabella in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0210c-167">Use **bcp_bind** for a fast, efficient way to copy data from a program variable into a table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0210c-168">Chiamare [bcp_init](bcp-init.md) prima di chiamare questa o qualsiasi altra funzione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="0210c-168">Call [bcp_init](bcp-init.md) before calling this or any other bulk-copy function.</span></span> <span data-ttu-id="0210c-169">La chiamata di **bcp_init** imposta la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabella di destinazione per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="0210c-169">Calling **bcp_init** sets the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] target table for bulk copy.</span></span> <span data-ttu-id="0210c-170">Quando si chiama **bcp_init** per l'uso con **bcp_bind** e [bcp_sendrow](bcp-sendrow.md), il **bcp_init** parametro _szDataFile_ , che indica il file di dati, è impostato su null. il **bcp_init**parametro_eDirection_ è impostato su DB_IN.</span><span class="sxs-lookup"><span data-stu-id="0210c-170">When calling **bcp_init** for use with **bcp_bind** and [bcp_sendrow](bcp-sendrow.md), the **bcp_init** _szDataFile_ parameter, indicating the data file, is set to NULL; the **bcp_init**_eDirection_ parameter is set to DB_IN.</span></span>  
  
 <span data-ttu-id="0210c-171">Eseguire una chiamata di **bcp_bind** separata per ogni colonna della [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabella in cui si desidera copiare.</span><span class="sxs-lookup"><span data-stu-id="0210c-171">Make a separate **bcp_bind** call for every column in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into which you want to copy.</span></span> <span data-ttu-id="0210c-172">Una volta effettuate le chiamate **bcp_bind** necessarie, chiamare **bcp_sendrow** per inviare una riga di dati dalle variabili di programma a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0210c-172">After the necessary **bcp_bind** calls have been made, then call **bcp_sendrow** to send a row of data from your program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0210c-173">La riassociazione della colonna non è supportata.</span><span class="sxs-lookup"><span data-stu-id="0210c-173">Rebinding a column is not supported.</span></span>  
  
 <span data-ttu-id="0210c-174">Quando si desidera [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eseguire il commit delle righe già ricevute, chiamare [bcp_batch](bcp-batch.md).</span><span class="sxs-lookup"><span data-stu-id="0210c-174">Whenever you want [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to commit the rows already received, call [bcp_batch](bcp-batch.md).</span></span> <span data-ttu-id="0210c-175">Ad esempio, chiamare **bcp_batch** una volta per ogni 1000 righe inserite o in qualsiasi altro intervallo.</span><span class="sxs-lookup"><span data-stu-id="0210c-175">For example, call **bcp_batch** once for every 1000 rows inserted or at any other interval.</span></span>  
  
 <span data-ttu-id="0210c-176">Quando non sono presenti altre righe da inserire, chiamare [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="0210c-176">When there are no more rows to be inserted, call [bcp_done](bcp-done.md).</span></span> <span data-ttu-id="0210c-177">In caso contrario, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="0210c-177">Failure to do so results in an error.</span></span>  
  
 <span data-ttu-id="0210c-178">Le impostazioni dei parametri di controllo, specificate con [bcp_control](bcp-control.md), non hanno alcun effetto sui trasferimenti **bcp_bind** righe.</span><span class="sxs-lookup"><span data-stu-id="0210c-178">Control parameter settings, specified with [bcp_control](bcp-control.md), have no effect on **bcp_bind** row transfers.</span></span>  
  
 <span data-ttu-id="0210c-179">Se *pData* per una colonna è impostato su null perché il relativo valore verrà fornito dalle chiamate a [bcp_moretext](bcp-moretext.md), anche tutte le colonne successive con *eDataType* impostato su SQLtext, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SqlBinary, SQLNCHAR o SQLIMAGE devono essere associate con *pData* impostato su null e anche i rispettivi valori devono essere forniti dalle chiamate a `bcp_moretext` .</span><span class="sxs-lookup"><span data-stu-id="0210c-179">If *pData* for a column is set to NULL because its value will be supplied by calls to [bcp_moretext](bcp-moretext.md), any subsequent columns with *eDataType* set to SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR, or SQLIMAGE must also be bound with *pData* set to NULL, and their values must also be supplied by calls to `bcp_moretext`.</span></span>  
  
 <span data-ttu-id="0210c-180">Per i nuovi tipi di valore di grandi dimensioni, ad esempio `varchar(max)` , `varbinary(max)` o `nvarchar(max)` , è possibile utilizzare SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SqlBinary e SQLNCHAR come indicatori di tipo nel parametro *eDataType* .</span><span class="sxs-lookup"><span data-stu-id="0210c-180">For new large value types, such as `varchar(max)`, `varbinary(max)`, or `nvarchar(max)`, you can use SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, and SQLNCHAR as type indicators in the *eDataType* parameter.</span></span>  
  
 <span data-ttu-id="0210c-181">Se *cbTerm* è diverso da 0, qualsiasi valore (1, 2, 4 o 8) è valido per il prefisso (*cbIndicator*).</span><span class="sxs-lookup"><span data-stu-id="0210c-181">If *cbTerm* is not 0, any value (1, 2, 4, or 8) is valid for the prefix (*cbIndicator*).</span></span> <span data-ttu-id="0210c-182">In questa situazione, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native client verrà cercata la terminazione, il calcolo della lunghezza dei dati rispetto al carattere di terminazione (*i*) e l'impostazione di *cbData* sul valore minore di i e sul valore di prefix.</span><span class="sxs-lookup"><span data-stu-id="0210c-182">In this situation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will search for the terminator, calculate data length with respect to the terminator (*i*), and set the *cbData* to the smaller value of i and the value of prefix.</span></span>  
  
 <span data-ttu-id="0210c-183">Se *cbTerm* è 0 e *cbIndicator* (il prefisso) non è 0, *cbIndicator* deve essere 8.</span><span class="sxs-lookup"><span data-stu-id="0210c-183">If *cbTerm* is 0 and *cbIndicator* (the prefix) is not 0, *cbIndicator* must be 8.</span></span> <span data-ttu-id="0210c-184">Al prefisso a 8 byte possono essere assegnati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0210c-184">The 8 byte prefix can take the following values:</span></span>  
  
-   <span data-ttu-id="0210c-185">0xFFFFFFFFFFFFFFFF indica un valore Null per il campo</span><span class="sxs-lookup"><span data-stu-id="0210c-185">0xFFFFFFFFFFFFFFFF means a null value for the field</span></span>  
  
-   <span data-ttu-id="0210c-186">0xFFFFFFFFFFFFFFFE viene trattato come valore di prefisso speciale utilizzato per inviare dati in blocchi al server in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="0210c-186">0xFFFFFFFFFFFFFFFE is treated as a special prefix value which is used for efficiently sending data in chunks to the server.</span></span> <span data-ttu-id="0210c-187">Il formato dei dati con questo prefisso speciale è:</span><span class="sxs-lookup"><span data-stu-id="0210c-187">The format of data with this special prefix is:</span></span>  
  
-   <span data-ttu-id="0210c-188"><SPECIAL_PREFIX> \<0 or more  DATA CHUNKS> <ZERO_CHUNK> dove:</span><span class="sxs-lookup"><span data-stu-id="0210c-188"><SPECIAL_PREFIX> \<0 or more  DATA CHUNKS> <ZERO_CHUNK> where:</span></span>  
  
-   <span data-ttu-id="0210c-189">SPECIAL_PREFIX è 0xFFFFFFFFFFFFFFFE</span><span class="sxs-lookup"><span data-stu-id="0210c-189">SPECIAL_PREFIX is 0xFFFFFFFFFFFFFFFE</span></span>  
  
-   <span data-ttu-id="0210c-190">DATA_CHUNK è un prefisso a 4 byte che contiene la lunghezza del blocco, seguita dai dati effettivi la cui lunghezza viene specificata nel prefisso a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="0210c-190">DATA_CHUNK is a 4 byte prefix containing length of the chunk,followed by the actual data whose length is specified in the 4 byte prefix.</span></span>  
  
-   <span data-ttu-id="0210c-191">ZERO_CHUNK è un valore a 4 byte che contiene tutti zeri (00000000) che indicano la fine dei dati.</span><span class="sxs-lookup"><span data-stu-id="0210c-191">ZERO_CHUNK is a 4 byte value containing all zeros (00000000) indicating the end of data.</span></span>  
  
-   <span data-ttu-id="0210c-192">Qualsiasi altra lunghezza a 8 byte valida viene trattata come una lunghezza dei dati normale.</span><span class="sxs-lookup"><span data-stu-id="0210c-192">Any other valid 8 byte length is treated as a regular data length.</span></span>  
  
 <span data-ttu-id="0210c-193">La chiamata di [bcp_columns](bcp-columns.md) quando si utilizza **bcp_bind** genera un errore.</span><span class="sxs-lookup"><span data-stu-id="0210c-193">Calling [bcp_columns](bcp-columns.md) when using **bcp_bind** results in an error.</span></span>  
  
## <a name="bcp_bind-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="0210c-194">Supporto di bcp_bind per le caratteristiche avanzate di data e ora</span><span class="sxs-lookup"><span data-stu-id="0210c-194">bcp_bind Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="0210c-195">Per informazioni sui tipi utilizzati con il parametro *eDataType* per i tipi data/ora, vedere la pagina relativa alle [modifiche di copia bulk per i tipi di data e ora avanzati &#40;OLE DB e&#41;ODBC ](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="0210c-195">For information about the types used with the *eDataType* parameter for date/time types, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="0210c-196">Per ulteriori informazioni, vedere [miglioramenti di data e ora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="0210c-196">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0210c-197">Esempio</span><span class="sxs-lookup"><span data-stu-id="0210c-197">Example</span></span>  
  
```  
#include sql.h  
#include sqlext.h  
#include odbcss.h  
// Variables like henv not specified.  
HDBC      hdbc;  
char         szCompanyName[MAXNAME];  
DBINT      idCompany;  
DBINT      nRowsProcessed;  
DBBOOL      bMoreData;  
char*      pTerm = "\t\t";  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source; return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bcp.   
if (bcp_init(hdbc, "comdb..accounts_info", NULL, NULL  
   DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Bind program variables to table columns.   
if (bcp_bind(hdbc, (LPCBYTE) &idCompany, 0, sizeof(DBINT), NULL, 0,  
   SQLINT4, 1)    == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_bind(hdbc, (LPCBYTE) szCompanyName, 0, SQL_VARLEN_DATA,  
   (LPCBYTE) pTerm, strnlen(pTerm, sizeof(pTerm)), SQLCHARACTER, 2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
while (TRUE)  
   {  
   // Retrieve and process program data.   
   if ((bMoreData = getdata(&idCompany, szCompanyName)) == TRUE)  
      {  
      // Send the data.   
      if (bcp_sendrow(hdbc) == FAIL)  
         {  
         // Raise error and return.  
         return;  
         }  
      }  
   else  
      {  
      // Break out of loop.  
      break;  
      }  
   }  
  
// Terminate the bulk copy operation.  
if ((nRowsProcessed = bcp_done(hdbc)) == -1)  
   {  
   printf_s("Bulk-copy unsuccessful.\n");  
   return;  
   }  
  
printf_s("%ld rows copied.\n", nRowsProcessed);  
```  
  
## <a name="see-also"></a><span data-ttu-id="0210c-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0210c-198">See Also</span></span>  
 [<span data-ttu-id="0210c-199">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="0210c-199">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
