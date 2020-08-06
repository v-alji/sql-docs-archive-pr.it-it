---
title: Conversione dalla copia bulk DB-Library a ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- converting DB-Library to ODBC bulk copy
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], DB-Library bulk copy
- ODBC, bulk copy operations
- DB-Library bulk copy
ms.assetid: 0bc15bdb-f19f-4537-ac6c-f249f42cf07f
author: rothja
ms.author: jroth
ms.openlocfilehash: 866900606e582f08695fd4695a1098f34fb2b426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635559"
---
# <a name="converting-from-db-library-to-odbc-bulk-copy"></a><span data-ttu-id="09f30-102">Conversione della copia bulk da DB-Library a ODBC</span><span class="sxs-lookup"><span data-stu-id="09f30-102">Converting from DB-Library to ODBC Bulk Copy</span></span>
  <span data-ttu-id="09f30-103">La conversione di un programma di copia bulk DB-Library in ODBC è semplice perché le funzioni di copia bulk supportate dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client sono simili alle funzioni di copia bulk DB-Library, con le eccezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="09f30-103">Converting a DB-Library bulk copy program to ODBC is easy because the bulk copy functions supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver are similar to the DB-Library bulk copy functions, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="09f30-104">Nelle applicazioni DB-Library un puntatore a una struttura DBPROCESS viene passato come primo parametro delle funzioni di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="09f30-104">DB-Library applications pass a pointer to a DBPROCESS structure as the first parameter of bulk copy functions.</span></span> <span data-ttu-id="09f30-105">Nelle applicazioni ODBC il puntatore DBPROCESS viene sostituito da un handle di connessione ODBC.</span><span class="sxs-lookup"><span data-stu-id="09f30-105">In ODBC applications, the DBPROCESS pointer is replaced with an ODBC connection handle.</span></span>  
  
-   <span data-ttu-id="09f30-106">Le applicazioni DB-Library chiamano **BCP_SETL** prima della connessione per abilitare le operazioni di copia bulk in un DBPROCESS.</span><span class="sxs-lookup"><span data-stu-id="09f30-106">DB-Library applications call **BCP_SETL** before connecting to enable bulk copy operations on a DBPROCESS.</span></span> <span data-ttu-id="09f30-107">Le applicazioni ODBC chiamano invece [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) prima della connessione per abilitare le operazioni bulk su un handle di connessione:</span><span class="sxs-lookup"><span data-stu-id="09f30-107">ODBC applications instead call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) before connecting to enable bulk operations on a connection handle:</span></span>  
  
    ```  
    SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP,  
        (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
    ```  
  
-   <span data-ttu-id="09f30-108">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client non supporta i gestori di messaggi e di errori DB-Library. è necessario chiamare **SQLGetDiagRec** per ottenere gli errori e i messaggi generati dalle funzioni di copia bulk ODBC.</span><span class="sxs-lookup"><span data-stu-id="09f30-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support DB-Library message and error handlers; you must call **SQLGetDiagRec** to get errors and messages raised by the ODBC bulk copy functions.</span></span> <span data-ttu-id="09f30-109">Le versioni ODBC delle funzioni di copia bulk restituiscono i codici restituiti standard di copia bulk SUCCEED o FAILED, non codici restituiti di tipo ODBC, come SQL_SUCCESS o SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="09f30-109">The ODBC versions of bulk copy functions return the standard bulk copy return codes of SUCCEED or FAILED, not ODBC-style return codes, such as SQL_SUCCESS or SQL_ERROR.</span></span>  
  
-   <span data-ttu-id="09f30-110">I valori specificati per il parametro DB-Library [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)*varlen* vengono interpretati in modo diverso rispetto al parametro ODBC **bcp_bind**_cbData_ .</span><span class="sxs-lookup"><span data-stu-id="09f30-110">The values specified for the DB-Library [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)*varlen* parameter are interpreted differently than the ODBC **bcp_bind**_cbData_ parameter.</span></span>  
  
    |<span data-ttu-id="09f30-111">Condizione indicata</span><span class="sxs-lookup"><span data-stu-id="09f30-111">Condition indicated</span></span>|<span data-ttu-id="09f30-112">Valore *VARLEN* DB-Library</span><span class="sxs-lookup"><span data-stu-id="09f30-112">DB-Library *varlen* value</span></span>|<span data-ttu-id="09f30-113">Valore ODBC *cbData*</span><span class="sxs-lookup"><span data-stu-id="09f30-113">ODBC *cbData* value</span></span>|  
    |-------------------------|--------------------------------|-------------------------|  
    |<span data-ttu-id="09f30-114">Valori Null forniti</span><span class="sxs-lookup"><span data-stu-id="09f30-114">Null values supplied</span></span>|<span data-ttu-id="09f30-115">0</span><span class="sxs-lookup"><span data-stu-id="09f30-115">0</span></span>|<span data-ttu-id="09f30-116">-1 (SQL_NULL_DATA)</span><span class="sxs-lookup"><span data-stu-id="09f30-116">-1 (SQL_NULL_DATA)</span></span>|  
    |<span data-ttu-id="09f30-117">Dati variabili forniti</span><span class="sxs-lookup"><span data-stu-id="09f30-117">Variable data supplied</span></span>|<span data-ttu-id="09f30-118">-1</span><span class="sxs-lookup"><span data-stu-id="09f30-118">-1</span></span>|<span data-ttu-id="09f30-119">-10 (SQL_VARLEN_DATA)</span><span class="sxs-lookup"><span data-stu-id="09f30-119">-10 (SQL_VARLEN_DATA)</span></span>|  
    |<span data-ttu-id="09f30-120">Carattere di lunghezza zero o stringa binaria</span><span class="sxs-lookup"><span data-stu-id="09f30-120">Zero length character or binary string</span></span>|<span data-ttu-id="09f30-121">N/D</span><span class="sxs-lookup"><span data-stu-id="09f30-121">NA</span></span>|<span data-ttu-id="09f30-122">0</span><span class="sxs-lookup"><span data-stu-id="09f30-122">0</span></span>|  
  
     <span data-ttu-id="09f30-123">In DB-Library, un valore *varlen* pari a-1 indica che vengono forniti dati a lunghezza variabile, che in ODBC *cbData* viene interpretato per indicare che vengono forniti solo valori null.</span><span class="sxs-lookup"><span data-stu-id="09f30-123">In DB-Library, a *varlen* value of -1 indicates that variable length data is being supplied, which in the ODBC *cbData* is interpreted to mean that only NULL values are being supplied.</span></span> <span data-ttu-id="09f30-124">Modificare le specifiche *VARLEN* DB-Library di-1 in SQL_VARLEN_DATA e tutte le specifiche *varlen* da 0 a SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="09f30-124">Change any DB-Library *varlen* specifications of -1 to SQL_VARLEN_DATA and any *varlen* specifications of 0 to SQL_NULL_DATA.</span></span>  
  
-   <span data-ttu-id="09f30-125">Il file \*\* \_ colfmt bcp\**di DB-Library e ODBC [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md)*cbUserData\* presentano lo stesso problema dei parametri **bcp_bind**_varlen_ e *cbData* indicati in precedenza._ \_ _</span><span class="sxs-lookup"><span data-stu-id="09f30-125">The DB-Library **bcp\_colfmt**_file\_collen_ and the ODBC [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md)*cbUserData* have the same issue as the **bcp_bind**_varlen_ and *cbData* parameters noted above.</span></span> <span data-ttu-id="09f30-126">Modificare le specifiche di *FILE_COLLEN* DB-Library di-1 per SQL_VARLEN_DATA ed eventuali specifiche di *file_collen* da 0 a SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="09f30-126">Change any DB-Library *file_collen* specifications of -1 to SQL_VARLEN_DATA and any *file_collen* specifications of 0 to SQL_NULL_DATA.</span></span>  
  
-   <span data-ttu-id="09f30-127">Il parametro *iValue* della funzione ODBC [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) è un puntatore void.</span><span class="sxs-lookup"><span data-stu-id="09f30-127">The *iValue* parameter of the ODBC [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) function is a void pointer.</span></span> <span data-ttu-id="09f30-128">In DB-Library *iValue* è un numero intero.</span><span class="sxs-lookup"><span data-stu-id="09f30-128">In DB-Library, *iValue* was an integer.</span></span> <span data-ttu-id="09f30-129">Eseguire il cast dei valori per ODBC *iValue* a void \*.</span><span class="sxs-lookup"><span data-stu-id="09f30-129">Cast the values for the ODBC *iValue* to void \*.</span></span>  
  
-   <span data-ttu-id="09f30-130">L'opzione **BCP_CONTROL** BCPMAXERRS specifica il numero di righe singole che possono avere errori prima che un'operazione di copia bulk abbia esito negativo.</span><span class="sxs-lookup"><span data-stu-id="09f30-130">The **bcp_control** option BCPMAXERRS specifies how many individual rows can have errors before a bulk copy operation fails.</span></span> <span data-ttu-id="09f30-131">Il valore predefinito per BCPMAXERRS è 0 (fail al primo errore) nella versione DB-Library di **bcp_control** e 10 nella versione ODBC.</span><span class="sxs-lookup"><span data-stu-id="09f30-131">The default for BCPMAXERRS is 0 (fail on first error) in the DB-Library version of **bcp_control** and 10 in the ODBC version.</span></span> <span data-ttu-id="09f30-132">Le applicazioni DB-Library che dipendono dal valore predefinito 0 per terminare un'operazione di copia bulk devono essere modificate per chiamare il **BCP_CONTROL** ODBC per impostare BCPMAXERRS su 0.</span><span class="sxs-lookup"><span data-stu-id="09f30-132">DB-Library applications that depend on the default of 0 to terminate a bulk copy operation must be changed to call the ODBC **bcp_control** to set BCPMAXERRS to 0.</span></span>  
  
-   <span data-ttu-id="09f30-133">La funzione ODBC **bcp_control** supporta le seguenti opzioni non supportate dalla versione DB-Library di **bcp_control**:</span><span class="sxs-lookup"><span data-stu-id="09f30-133">The ODBC **bcp_control** function supports the following options not supported by the DB-Library version of **bcp_control**:</span></span>  
  
    -   <span data-ttu-id="09f30-134">BCPODBC</span><span class="sxs-lookup"><span data-stu-id="09f30-134">BCPODBC</span></span>  
  
         <span data-ttu-id="09f30-135">Se impostato su TRUE, specifica che i valori **DateTime** e **smalldatetime** salvati in formato carattere avranno il prefisso e il suffisso della sequenza di escape del timestamp ODBC.</span><span class="sxs-lookup"><span data-stu-id="09f30-135">When set to TRUE, specifies that **datetime** and **smalldatetime** values saved in character format will have the ODBC timestamp escape sequence prefix and suffix.</span></span> <span data-ttu-id="09f30-136">Si applica solo alle operazioni BCP_OUT.</span><span class="sxs-lookup"><span data-stu-id="09f30-136">This only applies to BCP_OUT operations.</span></span>  
  
         <span data-ttu-id="09f30-137">Con BCPODBC impostato su FALSE, un valore **DateTime** convertito in una stringa di caratteri viene restituito come:</span><span class="sxs-lookup"><span data-stu-id="09f30-137">With BCPODBC set to FALSE, a **datetime** value converted to a character string is output as:</span></span>  
  
        ```  
        1997-01-01 00:00:00.000  
        ```  
  
         <span data-ttu-id="09f30-138">Con BCPODBC impostato su TRUE, lo stesso valore **DateTime** viene restituito come:</span><span class="sxs-lookup"><span data-stu-id="09f30-138">With BCPODBC set to TRUE, the same **datetime** value is output as:</span></span>  
  
        ```  
        {ts '1997-01-01 00:00:00.000' }  
        ```  
  
    -   <span data-ttu-id="09f30-139">BCPKEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="09f30-139">BCPKEEPIDENTITY</span></span>  
  
         <span data-ttu-id="09f30-140">Quando è impostato su TRUE, specifica che le funzioni di copia bulk inseriscono i valori dei dati forniti per le colonne con vincoli di identità.</span><span class="sxs-lookup"><span data-stu-id="09f30-140">When set to TRUE, specifies that bulk copy functions insert data values supplied for columns with identity constraints.</span></span> <span data-ttu-id="09f30-141">Se questa impostazione non è disponibile, per le righe inserite vengono generati nuovi valori Identity.</span><span class="sxs-lookup"><span data-stu-id="09f30-141">If this is not set, new identity values are generated for the inserted rows.</span></span>  
  
    -   <span data-ttu-id="09f30-142">BCPHINTS</span><span class="sxs-lookup"><span data-stu-id="09f30-142">BCPHINTS</span></span>  
  
         <span data-ttu-id="09f30-143">Specifica le varie ottimizzazioni della copia bulk.</span><span class="sxs-lookup"><span data-stu-id="09f30-143">Specifies various bulk copy optimizations.</span></span> <span data-ttu-id="09f30-144">Questa opzione non può essere utilizzata nella versione 6.5 o nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09f30-144">This option cannot be used on 6.5 or earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="09f30-145">BCPFILECP</span><span class="sxs-lookup"><span data-stu-id="09f30-145">BCPFILECP</span></span>  
  
         <span data-ttu-id="09f30-146">Specifica la tabella codici del file di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="09f30-146">Specifies the code page of the bulk copy file.</span></span>  
  
    -   <span data-ttu-id="09f30-147">BCPUNICODEFILE</span><span class="sxs-lookup"><span data-stu-id="09f30-147">BCPUNICODEFILE</span></span>  
  
         <span data-ttu-id="09f30-148">Specifica che un file di copia bulk in modalità carattere è un file Unicode.</span><span class="sxs-lookup"><span data-stu-id="09f30-148">Specifies that a character mode bulk copy file is a Unicode file.</span></span>  
  
-   <span data-ttu-id="09f30-149">La funzione ODBC **bcp_colfmt** non supporta l'indicatore *file_type* di SQLCHAR perché è in conflitto con il typedef ODBC SQLCHAR.</span><span class="sxs-lookup"><span data-stu-id="09f30-149">The ODBC **bcp_colfmt** function does not support the *file_type* indicator of SQLCHAR because it conflicts with the ODBC SQLCHAR typedef.</span></span> <span data-ttu-id="09f30-150">Usare SQLCHARACTER invece per **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="09f30-150">Use SQLCHARACTER instead for **bcp_colfmt**.</span></span>  
  
-   <span data-ttu-id="09f30-151">Nelle versioni ODBC delle funzioni di copia bulk il formato per l'utilizzo dei valori **DateTime** e **smalldatetime** nelle stringhe di caratteri è il formato ODBC aaaa-mm-gg hh: mm: SS. sss; i valori **smalldatetime** utilizzano il formato ODBC yyyy-mm-gg hh: mm: SS.</span><span class="sxs-lookup"><span data-stu-id="09f30-151">In the ODBC versions of bulk copy functions, the format for working with **datetime** and **smalldatetime** values in character strings is the ODBC format of yyyy-mm-dd hh:mm:ss.sss; **smalldatetime** values use the ODBC format of yyyy-mm-dd hh:mm:ss.</span></span>  
  
     <span data-ttu-id="09f30-152">Le versioni DB-Library delle funzioni di copia bulk accettano valori **DateTime** e **smalldatetime** nelle stringhe di caratteri utilizzando diversi formati:</span><span class="sxs-lookup"><span data-stu-id="09f30-152">The DB-Library versions of the bulk copy functions accept **datetime** and **smalldatetime** values in character strings using several formats:</span></span>  
  
    -   <span data-ttu-id="09f30-153">Il formato predefinito è *mmm gg aaaa hh: Mmxx* dove *XX* è AM o PM.</span><span class="sxs-lookup"><span data-stu-id="09f30-153">The default format is *mmm dd yyyy hh:mmxx* where *xx* is either AM or PM.</span></span>  
  
    -   <span data-ttu-id="09f30-154">stringhe di caratteri **DateTime** e **smalldatetime** in qualsiasi formato supportato dalla funzione **DBConvert** di DB-Library.</span><span class="sxs-lookup"><span data-stu-id="09f30-154">**datetime** and **smalldatetime** character strings in any format supported by the DB-Library **dbconvert** function.</span></span>  
  
    -   <span data-ttu-id="09f30-155">Quando la casella **Usa impostazioni internazionali** è selezionata nella scheda **Opzioni** DB-Library dell'utilità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rete client, le funzioni di copia bulk DB-Library accettano anche le date nel formato di data regionale definito per le impostazioni locali del registro di sistema del computer client.</span><span class="sxs-lookup"><span data-stu-id="09f30-155">When the **Use international settings** box is checked on the DB-Library **Options** tab of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Network Utility, the DB-Library bulk copy functions also accept dates in the regional date format defined for the locale setting of the client computer registry.</span></span>  
  
     <span data-ttu-id="09f30-156">Le funzioni di copia bulk DB-Library non accettano i formati ODBC **DateTime** e **smalldatetime** .</span><span class="sxs-lookup"><span data-stu-id="09f30-156">The DB-Library bulk copy functions do not accept the ODBC **datetime** and **smalldatetime** formats.</span></span>  
  
     <span data-ttu-id="09f30-157">Se l'attributo dell'istruzione SQL_SOPT_SS_REGIONALIZE è impostato su SQL_RE_ON, le funzioni di copia bulk ODBC accettano il formato di data locale definito per le impostazioni locali del Registro di sistema del computer client.</span><span class="sxs-lookup"><span data-stu-id="09f30-157">If the SQL_SOPT_SS_REGIONALIZE statement attribute is set to SQL_RE_ON, the ODBC bulk copy functions accept dates in the regional date format defined for the locale setting of the client computer registry.</span></span>  
  
-   <span data-ttu-id="09f30-158">Quando si esegue l'output dei valori **Money** in formato carattere, le funzioni di copia bulk ODBC forniscono quattro cifre di precisione e nessun separatore virgola; Le versioni DB-Library forniscono solo due cifre di precisione e includono i separatori di virgole.</span><span class="sxs-lookup"><span data-stu-id="09f30-158">When outputting **money** values in character format, ODBC bulk copy functions supply four digits of precision and no comma separators; DB-Library versions only supply two digits of precision and include the comma separators.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09f30-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09f30-159">See Also</span></span>  
 <span data-ttu-id="09f30-160">[Esecuzione di operazioni di copia bulk &#40;ODBC&#41;](performing-bulk-copy-operations-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="09f30-160">[Performing Bulk Copy Operations &#40;ODBC&#41;](performing-bulk-copy-operations-odbc.md) </span></span>  
 [<span data-ttu-id="09f30-161">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="09f30-161">Bulk Copy Functions</span></span>](../native-client-odbc-extensions-bulk-copy-functions/sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
