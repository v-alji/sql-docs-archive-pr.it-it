---
title: bcp_init | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_init
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_init function
ms.assetid: 6a25862c-7f31-4873-ab65-30f3abde89d2
author: rothja
ms.author: jroth
ms.openlocfilehash: 72d48b2a07e425e0863084c700c4de93d2776739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626764"
---
# <a name="bcp_init"></a><span data-ttu-id="248d9-102">bcp_init</span><span class="sxs-lookup"><span data-stu-id="248d9-102">bcp_init</span></span>
  <span data-ttu-id="248d9-103">Inizializza l'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="248d9-103">Initializes the bulk copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="248d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="248d9-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_init (  
HDBC   
hdbc  
,  
LPCTSTR   
szTable  
,  
LPCTSTR   
szDataFile  
,  
LPCTSTR   
szErrorFile  
,  
INT   
eDirection  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="248d9-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="248d9-105">Arguments</span></span>  
 <span data-ttu-id="248d9-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="248d9-106">*hdbc*</span></span>  
 <span data-ttu-id="248d9-107">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="248d9-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="248d9-108">*szTable*</span><span class="sxs-lookup"><span data-stu-id="248d9-108">*szTable*</span></span>  
 <span data-ttu-id="248d9-109">Nome della tabella di database per la copia interna o esterna.</span><span class="sxs-lookup"><span data-stu-id="248d9-109">Is the name of the database table to be copied into or out of.</span></span> <span data-ttu-id="248d9-110">Il nome può includere anche il nome del database o del proprietario,</span><span class="sxs-lookup"><span data-stu-id="248d9-110">This name can also include the database name or the owner name.</span></span> <span data-ttu-id="248d9-111">Ad esempio, **pubs. Gracie. titles**, **pubs.. i titoli, i**titoli **Gracie.** **e** i titoli sono tutti nomi di tabella validi.</span><span class="sxs-lookup"><span data-stu-id="248d9-111">For example, **pubs.gracie.titles**, **pubs..titles**, **gracie.titles**, and **titles** are all legal table names.</span></span>  
  
 <span data-ttu-id="248d9-112">Se *eDirection* è DB_OUT, *szTable* può essere anche il nome di una vista di database.</span><span class="sxs-lookup"><span data-stu-id="248d9-112">If *eDirection* is DB_OUT, *szTable* can also be the name of a database view.</span></span>  
  
 <span data-ttu-id="248d9-113">Se *eDirection* è DB_OUT e viene specificata un'istruzione SELECT utilizzando [bcp_control](bcp-control.md) prima che venga chiamato [bcp_exec](bcp-exec.md) , **bcp_init**_szTable_ deve essere impostato su null.</span><span class="sxs-lookup"><span data-stu-id="248d9-113">If *eDirection* is DB_OUT and a SELECT statement is specified using [bcp_control](bcp-control.md) before [bcp_exec](bcp-exec.md) is called, **bcp_init**_szTable_ must be set to NULL.</span></span>  
  
 <span data-ttu-id="248d9-114">*szDataFile*</span><span class="sxs-lookup"><span data-stu-id="248d9-114">*szDataFile*</span></span>  
 <span data-ttu-id="248d9-115">Nome del file utente per la copia interna o esterna.</span><span class="sxs-lookup"><span data-stu-id="248d9-115">Is the name of the user file to be copied into or out of.</span></span> <span data-ttu-id="248d9-116">Se i dati vengono copiati direttamente dalle variabili tramite [bcp_sendrow](bcp-sendrow.md), impostare *szDataFile* su null.</span><span class="sxs-lookup"><span data-stu-id="248d9-116">If data is being copied directly from variables by using [bcp_sendrow](bcp-sendrow.md), set *szDataFile* to NULL.</span></span>  
  
 <span data-ttu-id="248d9-117">*szErrorFile*</span><span class="sxs-lookup"><span data-stu-id="248d9-117">*szErrorFile*</span></span>  
 <span data-ttu-id="248d9-118">Nome del file degli errori in cui inserire messaggi di stato, messaggi di errore e copie delle righe che per qualche motivo non è stato possibile copiare da un file utente in una tabella.</span><span class="sxs-lookup"><span data-stu-id="248d9-118">Is the name of the error file to be filled with progress messages, error messages, and copies of any rows that, for any reason, could not be copied from a user file to a table.</span></span> <span data-ttu-id="248d9-119">Se NULL viene passato come *szErrorFile*, non viene utilizzato alcun file degli errori.</span><span class="sxs-lookup"><span data-stu-id="248d9-119">If NULL is passed as *szErrorFile*, no error file is used.</span></span>  
  
 <span data-ttu-id="248d9-120">*eDirection*</span><span class="sxs-lookup"><span data-stu-id="248d9-120">*eDirection*</span></span>  
 <span data-ttu-id="248d9-121">Direzione della copia, ovvero DB_IN oppure DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="248d9-121">Is the direction of the copy, either DB_IN or DB_OUT.</span></span> <span data-ttu-id="248d9-122">DB_IN indica una copia da variabili di programma o da un file utente a una tabella.</span><span class="sxs-lookup"><span data-stu-id="248d9-122">DB_IN indicates a copy from program variables or a user file to a table.</span></span> <span data-ttu-id="248d9-123">DB_OUT indica una copia da una tabella di database a un file utente.</span><span class="sxs-lookup"><span data-stu-id="248d9-123">DB_OUT indicates a copy from a database table to a user file.</span></span> <span data-ttu-id="248d9-124">È necessario specificare un nome di file utente con DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="248d9-124">You must specify a user file name with DB_OUT.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="248d9-125">Restituisce</span><span class="sxs-lookup"><span data-stu-id="248d9-125">Returns</span></span>  
 <span data-ttu-id="248d9-126">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="248d9-126">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="248d9-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="248d9-127">Remarks</span></span>  
 <span data-ttu-id="248d9-128">Chiamare **bcp_init** prima di chiamare qualsiasi altra funzione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="248d9-128">Call **bcp_init** before calling any other bulk-copy function.</span></span> <span data-ttu-id="248d9-129">**bcp_init** esegue le inizializzazioni necessarie per una copia bulk dei dati tra la workstation e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="248d9-129">**bcp_init** performs the necessary initializations for a bulk copy of data between the workstation and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="248d9-130">La funzione **bcp_init** deve essere fornita con un handle di connessione ODBC abilitato per l'utilizzo con le funzioni di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="248d9-130">The **bcp_init** function must be provided with an ODBC connection handle enabled for use with bulk copy functions.</span></span> <span data-ttu-id="248d9-131">Per abilitare l'handle, utilizzare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_BCP impostato su SQL_BCP_ON per un handle di connessione allocato, ma non connesso.</span><span class="sxs-lookup"><span data-stu-id="248d9-131">To enable the handle, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_BCP set to SQL_BCP_ON on an allocated, but not connected, connection handle.</span></span> <span data-ttu-id="248d9-132">Il tentativo di assegnare l'attributo su un handle collegato comporta un errore.</span><span class="sxs-lookup"><span data-stu-id="248d9-132">Attempting to assign the attribute on a connected handle results in an error.</span></span>  
  
 <span data-ttu-id="248d9-133">Quando viene specificato un file di dati, **bcp_init** esamina la struttura dell'origine del database o della tabella di destinazione, non del file di dati.</span><span class="sxs-lookup"><span data-stu-id="248d9-133">When a data file is specified, **bcp_init** examines the structure of the database source or target table, not the data file.</span></span> <span data-ttu-id="248d9-134">**bcp_init** specifica i valori del formato dati per il file di dati in base a ogni colonna della tabella di database, della vista o del set di risultati SELECT.</span><span class="sxs-lookup"><span data-stu-id="248d9-134">**bcp_init** specifies data format values for the data file based on each column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="248d9-135">Questa specifica include il tipo di dati di ogni colonna, la presenza o meno di un indicatore di lunghezza o Null e di stringhe di byte con carattere di terminazione nei dati e la larghezza dei tipi di dati a lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="248d9-135">This specification includes the data type of each column, the presence or absence of a length or null indicator and terminator byte strings in the data, and the width of fixed-length data types.</span></span> <span data-ttu-id="248d9-136">**bcp_init** imposta questi valori nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="248d9-136">**bcp_init** sets these values as follows:</span></span>  
  
-   <span data-ttu-id="248d9-137">Il tipo di dati specificato è quello della colonna della vista o della tabella di database oppure del set di risultati SELECT.</span><span class="sxs-lookup"><span data-stu-id="248d9-137">The data type specified is the data type of the column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="248d9-138">Il tipo di dati viene enumerato in base ai tipi di dati nativi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specificati in sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="248d9-138">The data type is enumerated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types specified in sqlncli.h.</span></span> <span data-ttu-id="248d9-139">I dati vengono rappresentati nel relativo formato elettronico,</span><span class="sxs-lookup"><span data-stu-id="248d9-139">Data itself is represented in its computer form.</span></span> <span data-ttu-id="248d9-140">Ovvero i dati di una colonna con tipo di dati **Integer** sono rappresentati da una sequenza a quattro byte che è di tipo Big o little-endian in base al computer in cui è stato creato il file di dati.</span><span class="sxs-lookup"><span data-stu-id="248d9-140">That is, data from a column of **integer** data type is represented by a four-byte sequence that is big-or little-endian based on the computer that created the data file.</span></span>  
  
-   <span data-ttu-id="248d9-141">Se un tipo di dati del database ha una lunghezza fissa, anche i dati del file di dati presenteranno una lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="248d9-141">If a database data type is fixed in length, the data file data is also fixed in length.</span></span> <span data-ttu-id="248d9-142">Le funzioni di copia bulk che elaborano dati, ad esempio [bcp_exec](bcp-exec.md), analizzano le righe di dati che prevedono che la lunghezza dei dati nel file di dati sia identica alla lunghezza dei dati specificata nella tabella di database, nella vista o nell'elenco di colonne SELECT.</span><span class="sxs-lookup"><span data-stu-id="248d9-142">Bulk-copy functions that process data (for example, [bcp_exec](bcp-exec.md)) parse data rows expecting the length of the data in the data file to be identical to the length of the data specified in the database table, view, or SELECT column list.</span></span> <span data-ttu-id="248d9-143">Ad esempio, i dati per una colonna del database definita come **char (13)** devono essere rappresentati da 13 caratteri per ogni riga di dati nel file.</span><span class="sxs-lookup"><span data-stu-id="248d9-143">For example, data for a database column defined as **char(13)** must be represented by 13 characters for each row of data in the file.</span></span> <span data-ttu-id="248d9-144">I dati a lunghezza fissa possono essere preceduti da un indicatore Null se la colonna del database consente valori Null.</span><span class="sxs-lookup"><span data-stu-id="248d9-144">Fixed-length data can be prefixed with a null indicator if the database column allows null values.</span></span>  
  
-   <span data-ttu-id="248d9-145">Quando viene definita la sequenza di byte con caratteri di terminazione, la lunghezza di tale sequenza è impostata su 0.</span><span class="sxs-lookup"><span data-stu-id="248d9-145">When terminator-byte sequence is defined, the length of the terminator-byte sequence is set to 0.</span></span>  
  
-   <span data-ttu-id="248d9-146">Quando si esegue la copia in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il file di dati deve includere dati per ogni colonna della tabella di database.</span><span class="sxs-lookup"><span data-stu-id="248d9-146">When copying to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data file must have data for each column in the database table.</span></span> <span data-ttu-id="248d9-147">Quando si esegue la copia da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], i dati di tutte le colonne della vista o della tabella di database o del set di risultati SELECT vengono copiati nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="248d9-147">When copying from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data from all columns in the database table, view, or SELECT result set are copied to the data file.</span></span>  
  
-   <span data-ttu-id="248d9-148">Quando si esegue la copia dati di in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la posizione ordinale di una colonna nel file di dati deve essere identica alla posizione ordinale della colonna nella tabella di database.</span><span class="sxs-lookup"><span data-stu-id="248d9-148">When copying to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the ordinal position of a column in the data file must be identical to the ordinal position of the column in the database table.</span></span> <span data-ttu-id="248d9-149">Quando si esegue [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] la copia da, **bcp_exec** inserisce i dati in base alla posizione ordinale della colonna nella tabella di database.</span><span class="sxs-lookup"><span data-stu-id="248d9-149">When copying from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp_exec** places data based on the ordinal position of the column in the database table.</span></span>  
  
-   <span data-ttu-id="248d9-150">Se un tipo di dati del database è di lunghezza variabile (ad esempio, **varbinary (22)**) o se una colonna del database può contenere valori null, i dati nel file di dati sono preceduti da un indicatore di lunghezza o null.</span><span class="sxs-lookup"><span data-stu-id="248d9-150">If a database data type is variable in length (for example, **varbinary(22)**) or if a database column can contain null values, data in the data file is prefixed by a length/null indicator.</span></span> <span data-ttu-id="248d9-151">La larghezza dell'indicatore varia in base al tipo di dati e alla versione della copia bulk.</span><span class="sxs-lookup"><span data-stu-id="248d9-151">The width of the indicator varies based on the data type and version of bulk copy.</span></span>  
  
 <span data-ttu-id="248d9-152">Per modificare i valori del formato dati specificati per un file di dati, chiamare [bcp_columns](bcp-columns.md) e [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="248d9-152">To change data format values specified for a data file, call [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md).</span></span>  
  
 <span data-ttu-id="248d9-153">Le copie bulk eseguite in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono essere ottimizzate per le tabelle che non contengono indici impostando il modello di recupero del database su SIMPLE o BULK_LOGGED.</span><span class="sxs-lookup"><span data-stu-id="248d9-153">Bulk copies to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be optimized for tables that do not contain indexes by setting the database recovery model to SIMPLE or BULK_LOGGED.</span></span> <span data-ttu-id="248d9-154">Per ulteriori informazioni, vedere [prerequisiti per la registrazione minima nell'importazione bulk](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md) e [ALTER database](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="248d9-154">For more information, see [Prerequisites for Minimal Logging in Bulk Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md) and [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
 <span data-ttu-id="248d9-155">Se non viene utilizzato alcun file di dati, è necessario chiamare [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) per specificare il formato e la posizione in memoria dei dati per ogni colonna, quindi copiare le righe di dati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="248d9-155">If no data file is used, you must call [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) to specify the format and location in memory of the data fsor each column, then copy data rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="248d9-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="248d9-156">Example</span></span>  
 <span data-ttu-id="248d9-157">In questo esempio viene illustrato come utilizzare la funzione ODBC bcp_init con un file di formato.</span><span class="sxs-lookup"><span data-stu-id="248d9-157">This sample shows how to use the ODBC bcp_init function with a format file.</span></span>  
  
 <span data-ttu-id="248d9-158">Prima di compilare ed esegue il codice C++, è necessario effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="248d9-158">Before you compile and run the C++ code, you need to do the following:</span></span>  
  
-   <span data-ttu-id="248d9-159">Creare un'origine dati ODBC denominata Test.</span><span class="sxs-lookup"><span data-stu-id="248d9-159">Create an ODBC data source called Test.</span></span> <span data-ttu-id="248d9-160">È possibile associare questa origine dati a qualsiasi database.</span><span class="sxs-lookup"><span data-stu-id="248d9-160">You can associate this data source with any database.</span></span>  
  
-   <span data-ttu-id="248d9-161">Eseguire sul database l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="248d9-161">Run the following [!INCLUDE[tsql](../../includes/tsql-md.md)] on the database:</span></span>  
  
    ```  
    CREATE TABLE BCPDate (cola int, colb datetime);  
    ```  
  
-   <span data-ttu-id="248d9-162">Nella directory in cui verrà eseguita l'applicazione aggiungere un file denominato Bcpfmt.fmt e aggiungervi il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="248d9-162">In the directory where you will run the application, add a file called Bcpfmt.fmt, and add this to the file:</span></span>  
  
    ```  
    8.0  
    2  
    1SQLCHAR04"\t"1colaSQL_Latin1_General_Cp437_Bin  
    2SQLCHAR08"\r\n"2colbSQL_Latin1_General_Cp437_Bin  
    ```  
  
-   <span data-ttu-id="248d9-163">Nella directory in cui verrà eseguita l'applicazione aggiungere un file denominato Bcpodbc.bcp e aggiungervi il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="248d9-163">In the directory where you will run the application, add a file called Bcpodbc.bcp, and add this to the file:</span></span>  
  
    ```  
    1  
    2  
    ```  
  
 <span data-ttu-id="248d9-164">A questo punto è possibile compilare ed eseguire il codice C++.</span><span class="sxs-lookup"><span data-stu-id="248d9-164">Now you are ready to compile and run the C++ code.</span></span>  
  
```  
// compile with: odbc32.lib sqlncli11.lib  
#include <stdio.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC;   
  
void Cleanup() {  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
   SDWORD cRows;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle, set BCP mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetConnectAttr(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security. Create SQL Server DSN using Windows NT authentication.  
   retcode = SQLConnect(hdbc1, (UCHAR*)"Test", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_IN);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Read the format file.  
   retcode = bcp_readfmt(hdbc1, "BCPFMT.fmt");  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_readfmt(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_exec(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied in = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="248d9-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="248d9-165">See Also</span></span>  
 [<span data-ttu-id="248d9-166">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="248d9-166">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
