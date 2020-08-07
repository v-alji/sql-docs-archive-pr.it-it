---
title: bcp_control | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_control
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_control function
ms.assetid: 32187282-1385-4c52-9134-09f061eb44f5
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ea5d60da8069707a53f3bdf2de53345cd11090f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623241"
---
# <a name="bcp_control"></a><span data-ttu-id="2f019-102">bcp_control</span><span class="sxs-lookup"><span data-stu-id="2f019-102">bcp_control</span></span>
  <span data-ttu-id="2f019-103">Modifica le impostazioni predefinite per vari parametri di controllo per una copia bulk tra un file e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f019-103">Changes the default settings for various control parameters for a bulk copy between a file and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f019-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f019-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_control (  
HDBC   
hdbc  
,  
INT   
eOption  
,  
void*   
iValue  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f019-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2f019-105">Arguments</span></span>  
 <span data-ttu-id="2f019-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="2f019-106">*hdbc*</span></span>  
 <span data-ttu-id="2f019-107">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="2f019-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="2f019-108">*eOption*</span><span class="sxs-lookup"><span data-stu-id="2f019-108">*eOption*</span></span>  
 <span data-ttu-id="2f019-109">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f019-109">Is one of the following:</span></span>  
  
 <span data-ttu-id="2f019-110">BCPABORT</span><span class="sxs-lookup"><span data-stu-id="2f019-110">BCPABORT</span></span>  
 <span data-ttu-id="2f019-111">Arresta un'operazione di copia bulk già in corso.</span><span class="sxs-lookup"><span data-stu-id="2f019-111">Stops a bulk-copy operation that is already in progress.</span></span> <span data-ttu-id="2f019-112">Chiamare **bcp_control** con un *eOption* di BCPABORT da un altro thread per arrestare un'operazione di copia bulk in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2f019-112">Call **bcp_control** with an *eOption* of BCPABORT from another thread to stop a running bulk copy operation.</span></span> <span data-ttu-id="2f019-113">Il parametro *iValue* viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="2f019-113">The *iValue* parameter is ignored.</span></span>  
  
 <span data-ttu-id="2f019-114">BCPBATCH</span><span class="sxs-lookup"><span data-stu-id="2f019-114">BCPBATCH</span></span>  
 <span data-ttu-id="2f019-115">Indica il numero di righe per batch.</span><span class="sxs-lookup"><span data-stu-id="2f019-115">Is the number of rows per batch.</span></span> <span data-ttu-id="2f019-116">L'impostazione predefinita è 0 e indica tutte le righe di una tabella, quando i dati vengono estratti, o tutte le righe nel file di dati dell'utente, quando i dati vengono copiati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f019-116">The default is 0, which indicates either all rows in a table, when data is being extracted, or all rows in the user data file, when data is being copied to an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2f019-117">Un valore inferiore a 1 comporta la reimpostazione di BCPBATCH sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="2f019-117">A value less than 1 resets BCPBATCH to the default.</span></span>  
  
 <span data-ttu-id="2f019-118">BCPDELAYREADFMT</span><span class="sxs-lookup"><span data-stu-id="2f019-118">BCPDELAYREADFMT</span></span>  
 <span data-ttu-id="2f019-119">Un valore booleano, se impostato su true, causerà la lettura [bcp_readfmt](bcp-readfmt.md) in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2f019-119">A Boolean, if set to true, will cause [bcp_readfmt](bcp-readfmt.md) to read at execution.</span></span> <span data-ttu-id="2f019-120">Se false (impostazione predefinita), bcp_readfmt leggerà immediatamente il file di formato.</span><span class="sxs-lookup"><span data-stu-id="2f019-120">If false (the default), bcp_readfmt will immediately read the format file.</span></span> <span data-ttu-id="2f019-121">Si verificherà un errore di sequenza se BCPDELAYREADFMT è true e si chiama bcp_columns o bcp_setcolfmt.</span><span class="sxs-lookup"><span data-stu-id="2f019-121">A sequence error will occur if BCPDELAYREADFMT is true and you call bcp_columns or bcp_setcolfmt.</span></span>  
  
 <span data-ttu-id="2f019-122">Si verificherà un errore di sequenza anche se si chiama `bcp_control(hdbc,` BCPDELAYREADFMT `, (void *)FALSE)` dopo avere chiamato `bcp_control(hdbc,` BCPDELAYREADFMT `, (void *)TRUE)` e bcp_writefmt.</span><span class="sxs-lookup"><span data-stu-id="2f019-122">A sequence error will also occur if you call `bcp_control(hdbc,` BCPDELAYREADFMT`, (void *)FALSE)` after calling `bcp_control(hdbc,` BCPDELAYREADFMT`, (void *)TRUE)` and bcp_writefmt.</span></span>  
  
 <span data-ttu-id="2f019-123">Per altre informazioni, vedere [Metadata Discovery](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="2f019-123">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
 <span data-ttu-id="2f019-124">BCPFILECP</span><span class="sxs-lookup"><span data-stu-id="2f019-124">BCPFILECP</span></span>  
 <span data-ttu-id="2f019-125">*iValue* contiene il numero della tabella codici per il file di dati.</span><span class="sxs-lookup"><span data-stu-id="2f019-125">*iValue* contains the number of the code page for the data file.</span></span> <span data-ttu-id="2f019-126">È possibile specificare il numero della tabella codici, ad esempio 1252 o 850, o uno dei valori indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="2f019-126">You can specify the number of the code page, such as 1252 or 850, or one of these values:</span></span>  
  
 <span data-ttu-id="2f019-127">BCPFILE_ACP: i dati nel file si trova in Microsoft Windows?</span><span class="sxs-lookup"><span data-stu-id="2f019-127">BCPFILE_ACP: data in the file is in the Microsoft Windows??</span></span> <span data-ttu-id="2f019-128">tabella codici del client.</span><span class="sxs-lookup"><span data-stu-id="2f019-128">code page of the client.</span></span>  
  
 <span data-ttu-id="2f019-129">BCPFILE_OEMCP: i dati contenuti nel file utilizzano la tabella codici OEM del client (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="2f019-129">BCPFILE_OEMCP: data in the file is in the OEM code page of the client (default).</span></span>  
  
 <span data-ttu-id="2f019-130">BCPFILE_RAW: i dati contenuti nel file utilizzano la tabella codici di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f019-130">BCPFILE_RAW: data in the file is in the code page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2f019-131">BCPFILEFMT</span><span class="sxs-lookup"><span data-stu-id="2f019-131">BCPFILEFMT</span></span>  
 <span data-ttu-id="2f019-132">Numero di versione del formato del file di dati.</span><span class="sxs-lookup"><span data-stu-id="2f019-132">The version number of the data file format.</span></span> <span data-ttu-id="2f019-133">Il valore può essere 80 ([!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]), 90 ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]), 100 ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] o [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]), 110 ([!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]) o 120 ([!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="2f019-133">This can be 80 ([!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]), 90 ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]), 100 ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]), 110 ([!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]), or 120 ([!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="2f019-134">120 è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="2f019-134">120 is the default.</span></span> <span data-ttu-id="2f019-135">Questo valore è utile per l'esportazione e l'importazione di dati in formati supportati da una versione precedente del server.</span><span class="sxs-lookup"><span data-stu-id="2f019-135">This is useful for exporting and importing data in formats that were supported by earlier version of the server.</span></span> <span data-ttu-id="2f019-136">Ad esempio, per importare i dati ottenuti da una colonna di testo di un [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server in una colonna **varchar (max)** di un [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Server o versione successiva, è necessario specificare 80.</span><span class="sxs-lookup"><span data-stu-id="2f019-136">For example, to import data that was obtained from a text column in a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server into a **varchar(max)** column in a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later server, you should specify 80.</span></span> <span data-ttu-id="2f019-137">Analogamente, se si specifica 80 quando si esportano dati da una colonna **varchar (max)** , questo verrà salvato esattamente come le colonne di testo vengono salvate nel [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] formato e possono essere importate in una colonna di testo di un [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] Server.</span><span class="sxs-lookup"><span data-stu-id="2f019-137">Similarly, if you specify 80 when exporting data from a **varchar(max)** column, it will be saved just like text columns are saved in the [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] format, and can be imported into a text column of a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server.</span></span>  
  
 <span data-ttu-id="2f019-138">BCPFIRST</span><span class="sxs-lookup"><span data-stu-id="2f019-138">BCPFIRST</span></span>  
 <span data-ttu-id="2f019-139">Indica la prima riga di dati del file o della tabella da copiare.</span><span class="sxs-lookup"><span data-stu-id="2f019-139">Is the first row of data to file or table to copy.</span></span> <span data-ttu-id="2f019-140">Il valore predefinito è 1. Un valore minore di 1 reimposta l'opzione sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="2f019-140">The default is 1; a value less than 1 resets this option to its default.</span></span>  
  
 <span data-ttu-id="2f019-141">BCPFIRSTEX</span><span class="sxs-lookup"><span data-stu-id="2f019-141">BCPFIRSTEX</span></span>  
 <span data-ttu-id="2f019-142">Per le operazioni BCP out, specifica la prima riga della tabella di database da copiare nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="2f019-142">For BCP out operations, specifies the first row of the database table to copy into the data file.</span></span>  
  
 <span data-ttu-id="2f019-143">Per le operazioni BCP in, specifica la prima riga del file di dati da copiare nella tabella di database.</span><span class="sxs-lookup"><span data-stu-id="2f019-143">For BCP in operations, specifies the first row of the data file to copy into the database table.</span></span>  
  
 <span data-ttu-id="2f019-144">È previsto che il parametro *iValue* sia l'indirizzo di un intero con segno a 64 bit contenente il valore.</span><span class="sxs-lookup"><span data-stu-id="2f019-144">The *iValue* parameter is expected to be the address of a signed 64-bit integer containing the value.</span></span> <span data-ttu-id="2f019-145">Il valore massimo che è possibile passare a BCPFIRSTEX è 2^63-1.</span><span class="sxs-lookup"><span data-stu-id="2f019-145">The maximum value that can be passed to BCPFIRSTEX is 2^63-1.</span></span>  
  
 <span data-ttu-id="2f019-146">BCPFMTXML</span><span class="sxs-lookup"><span data-stu-id="2f019-146">BCPFMTXML</span></span>  
 <span data-ttu-id="2f019-147">Specifica che il file di formato generato deve essere in formato XML.</span><span class="sxs-lookup"><span data-stu-id="2f019-147">Specifies that the format file generated should be in XML format.</span></span> <span data-ttu-id="2f019-148">Per impostazione predefinita è disattivato.</span><span class="sxs-lookup"><span data-stu-id="2f019-148">It is off by default.</span></span>  
  
 <span data-ttu-id="2f019-149">I file in formato XML offrono una maggiore flessibilità sebbene con alcuni vincoli aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="2f019-149">XML format files provide greater flexibility but with some added constraints.</span></span> <span data-ttu-id="2f019-150">Diversamente dai file nei formati precedenti, non è ad esempio possibile specificare contemporaneamente il prefisso e il carattere di terminazione per un campo.</span><span class="sxs-lookup"><span data-stu-id="2f019-150">For example, you can not specify the prefix and terminator for a field simultaneously, which was possible in older format files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f019-151">I file in formato XML sono supportati solo quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene installato insieme a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="2f019-151">XML format files are only supported when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed along with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="2f019-152">BCPHINTS</span><span class="sxs-lookup"><span data-stu-id="2f019-152">BCPHINTS</span></span>  
 <span data-ttu-id="2f019-153">*iValue* contiene un puntatore alla stringa di caratteri SQLTCHAR.</span><span class="sxs-lookup"><span data-stu-id="2f019-153">*iValue* contains an SQLTCHAR character string pointer.</span></span> <span data-ttu-id="2f019-154">Tale stringa specifica hint di elaborazione della copia bulk di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o un'istruzione Transact-SQL che restituisce un set di risultati.</span><span class="sxs-lookup"><span data-stu-id="2f019-154">The string addressed specifies either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk-copy processing hints or a Transact-SQL statement that returns a result set.</span></span> <span data-ttu-id="2f019-155">Se viene specificata un'istruzione Transact-SQL che restituisce più set di risultati, vengono ignorati tutti i set di risultati successivi al primo.</span><span class="sxs-lookup"><span data-stu-id="2f019-155">If a Transact-SQL statement is specified that returns more than one result set, all result sets after the first are ignored.</span></span> <span data-ttu-id="2f019-156">Per ulteriori informazioni sugli hint di elaborazione per la copia bulk, vedere [utilità bcp](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="2f019-156">For more information about bulk-copy processing hints, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
 <span data-ttu-id="2f019-157">BCPKEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="2f019-157">BCPKEEPIDENTITY</span></span>  
 <span data-ttu-id="2f019-158">Quando *iValue* è true, specifica che le funzioni di copia bulk inseriscono i valori dei dati forniti per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] le colonne definite con un vincolo Identity.</span><span class="sxs-lookup"><span data-stu-id="2f019-158">When *iValue* is TRUE, specifies that bulk copy functions insert data values supplied for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] columns defined with an identity constraint.</span></span> <span data-ttu-id="2f019-159">Il file di input deve fornire valori per le colonne di identità.</span><span class="sxs-lookup"><span data-stu-id="2f019-159">The input file must supply values for the identity columns.</span></span> <span data-ttu-id="2f019-160">Se questa impostazione non è disponibile, per le righe inserite vengono generati nuovi valori Identity.</span><span class="sxs-lookup"><span data-stu-id="2f019-160">If this is not set, new identity values are generated for the inserted rows.</span></span> <span data-ttu-id="2f019-161">Eventuali dati presenti nel file per le colonne di identità vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="2f019-161">Any data present in the file for the identity columns is ignored.</span></span>  
  
 <span data-ttu-id="2f019-162">BCPKEEPNULLS</span><span class="sxs-lookup"><span data-stu-id="2f019-162">BCPKEEPNULLS</span></span>  
 <span data-ttu-id="2f019-163">Specifica se i valori di dati vuoti nel file verranno convertiti in valori NULL nella tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f019-163">Specifies whether empty data values in the file will be converted to NULL values in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="2f019-164">Quando *iValue* è true, i valori vuoti verranno convertiti in valori null nella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabella.</span><span class="sxs-lookup"><span data-stu-id="2f019-164">When *iValue* is TRUE, empty values will be converted to NULL in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="2f019-165">L'impostazione predefinita prevede che i valori vuoti vengano convertiti in un valore predefinito, se presente, per la colonna nella tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f019-165">The default is for empty values to be converted to a default value for the column in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table if a default exists.</span></span>  
  
 <span data-ttu-id="2f019-166">BCPLAST</span><span class="sxs-lookup"><span data-stu-id="2f019-166">BCPLAST</span></span>  
 <span data-ttu-id="2f019-167">Indica l'ultima riga da copiare.</span><span class="sxs-lookup"><span data-stu-id="2f019-167">Is the last row to copy.</span></span> <span data-ttu-id="2f019-168">Il valore predefinito prevede che vengano copiate tutte le righe. Un valore inferiore a 1 reimposta l'opzione sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="2f019-168">The default is to copy all rows; a value less than 1 resets this option to its default.</span></span>  
  
 <span data-ttu-id="2f019-169">BCPLASTEX</span><span class="sxs-lookup"><span data-stu-id="2f019-169">BCPLASTEX</span></span>  
 <span data-ttu-id="2f019-170">Per le operazioni BCP out, specifica l'ultima riga della tabella di database da copiare nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="2f019-170">For BCP out operations, specifies the last row of the database table to copy into the data file.</span></span>  
  
 <span data-ttu-id="2f019-171">Per le operazioni BCP in, specifica l'ultima riga del file di dati da copiare nella tabella di database.</span><span class="sxs-lookup"><span data-stu-id="2f019-171">For BCP in operations, specifies the last row of the data file to copy into the database table.</span></span>  
  
 <span data-ttu-id="2f019-172">È previsto che il parametro *iValue* sia l'indirizzo di un intero con segno a 64 bit contenente il valore.</span><span class="sxs-lookup"><span data-stu-id="2f019-172">The *iValue* parameter is expected to be the address of a signed 64-bit integer containing the value.</span></span> <span data-ttu-id="2f019-173">Il valore massimo che è possibile passare a BCPLASTEX è 2^63-1.</span><span class="sxs-lookup"><span data-stu-id="2f019-173">The maximum value that can be passed to BCPLASTEX is 2^63-1.</span></span>  
  
 <span data-ttu-id="2f019-174">BCPMAXERRS</span><span class="sxs-lookup"><span data-stu-id="2f019-174">BCPMAXERRS</span></span>  
 <span data-ttu-id="2f019-175">Indica il numero massimo di errori che si possono verificare prima che l'operazione di copia bulk venga annullata.</span><span class="sxs-lookup"><span data-stu-id="2f019-175">Is the number of errors allowed before the bulk copy operation fails.</span></span> <span data-ttu-id="2f019-176">Il valore predefinito è 10. un valore minore di 1 Reimposta questa opzione sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="2f019-176">The default is 10; a value less than 1 resets this option to its default.</span></span> <span data-ttu-id="2f019-177">La copia bulk impone un massimo di 65.535 errori.</span><span class="sxs-lookup"><span data-stu-id="2f019-177">Bulk copy imposes a maximum of 65,535 errors.</span></span> <span data-ttu-id="2f019-178">Il tentativo di impostare questa opzione su un valore maggiore di 65.535 comporta l'impostazione dell'opzione su 65.535.</span><span class="sxs-lookup"><span data-stu-id="2f019-178">An attempt to set this option to a value larger than 65,535 results in the option being set to 65,535.</span></span>  
  
 <span data-ttu-id="2f019-179">BCPODBC</span><span class="sxs-lookup"><span data-stu-id="2f019-179">BCPODBC</span></span>  
 <span data-ttu-id="2f019-180">Se è TRUE, specifica che i valori **DateTime** e **smalldatetime** salvati in formato carattere utilizzeranno il prefisso e il suffisso della sequenza di escape del timestamp ODBC.</span><span class="sxs-lookup"><span data-stu-id="2f019-180">When TRUE, specifies that **datetime** and **smalldatetime** values saved in character format will use the ODBC timestamp escape sequence prefix and suffix.</span></span> <span data-ttu-id="2f019-181">L'opzione BCPODBC è applicabile solo a BCP_OUT.</span><span class="sxs-lookup"><span data-stu-id="2f019-181">The BCPODBC option only applies to BCP_OUT.</span></span>  
  
 <span data-ttu-id="2f019-182">Se è FALSE, un valore **DateTime** che rappresenta il 1 ° gennaio 1997 viene convertito nella stringa di caratteri: 1997-01-01 00:00:00.000.</span><span class="sxs-lookup"><span data-stu-id="2f019-182">When FALSE, a **datetime** value representing January 1, 1997 is converted to the character string: 1997-01-01 00:00:00.000.</span></span> <span data-ttu-id="2f019-183">Se è TRUE, lo stesso valore **DateTime** viene rappresentato come: {ts ' 1997-01-01 00:00:00.000'}.</span><span class="sxs-lookup"><span data-stu-id="2f019-183">When TRUE, the same **datetime** value is represented as: {ts '1997-01-01 00:00:00.000'}.</span></span>  
  
 <span data-ttu-id="2f019-184">BCPROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="2f019-184">BCPROWCOUNT</span></span>  
 <span data-ttu-id="2f019-185">Restituisce il numero di righe interessate dall'ultima operazione BCP o da quella corrente.</span><span class="sxs-lookup"><span data-stu-id="2f019-185">Returns the number of rows affected by the current (or last) BCP operation.</span></span>  
  
 <span data-ttu-id="2f019-186">BCPTEXTFILE</span><span class="sxs-lookup"><span data-stu-id="2f019-186">BCPTEXTFILE</span></span>  
 <span data-ttu-id="2f019-187">Quando è impostato su TRUE, specifica che il file di dati è un file di testo, anziché un file binario.</span><span class="sxs-lookup"><span data-stu-id="2f019-187">When TRUE, specifies that the data file is a text file, rather than a binary file.</span></span> <span data-ttu-id="2f019-188">Se il file è un file di testo, BCP determina se è Unicode controllando il marcatore di byte Unicode nei primi due byte del file di dati.</span><span class="sxs-lookup"><span data-stu-id="2f019-188">If the file is a text file, BCP determines whether or not it is Unicode by checking the Unicode byte marker in the first two bytes of the data file.</span></span>  
  
 <span data-ttu-id="2f019-189">BCPUNICODEFILE</span><span class="sxs-lookup"><span data-stu-id="2f019-189">BCPUNICODEFILE</span></span>  
 <span data-ttu-id="2f019-190">Quando è impostato su TRUE, specifica che il file di input è un file Unicode.</span><span class="sxs-lookup"><span data-stu-id="2f019-190">When TRUE, specifies the input file is a Unicode file.</span></span>  
  
 <span data-ttu-id="2f019-191">*iValue*</span><span class="sxs-lookup"><span data-stu-id="2f019-191">*iValue*</span></span>  
 <span data-ttu-id="2f019-192">Valore per l'oggetto *eOption*specificato.</span><span class="sxs-lookup"><span data-stu-id="2f019-192">Is the value for the specified *eOption*.</span></span> <span data-ttu-id="2f019-193">*iValue* è un valore integer (LONGLONG) di cui viene eseguito il cast a un puntatore void per consentire l'espansione futura a valori di bit 64.</span><span class="sxs-lookup"><span data-stu-id="2f019-193">*iValue* is an integer (LONGLONG) value cast to a void pointer to allow for future expansion to 64 bit values.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="2f019-194">Restituisce</span><span class="sxs-lookup"><span data-stu-id="2f019-194">Returns</span></span>  
 <span data-ttu-id="2f019-195">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="2f019-195">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f019-196">Commenti</span><span class="sxs-lookup"><span data-stu-id="2f019-196">Remarks</span></span>  
 <span data-ttu-id="2f019-197">Questa funzione imposta vari parametri di controllo per le operazioni di copia bulk, inclusi il numero di errori consentito prima dell'annullamento di una copia bulk, i numeri della prima e dell'ultima riga da copiare da un file di dati e le dimensioni del batch.</span><span class="sxs-lookup"><span data-stu-id="2f019-197">This function sets various control parameters for bulk-copy operations, including the number of errors allowed before canceling a bulk copy, the numbers of the first and last rows to copy from a data file, and the batch size.</span></span>  
  
 <span data-ttu-id="2f019-198">Questa funzione viene utilizzata anche per specificare l'istruzione SELECT quando si esegue una copia bulk del set di risultati di un'istruzione SELECT da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f019-198">This function is also used to specify the SELECT statement when bulk copying out from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] the result set of a SELECT.</span></span> <span data-ttu-id="2f019-199">Impostare *eOption* su BCPHINTS e impostare *iValue* su un puntatore a una stringa SQLTCHAR che contiene l'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="2f019-199">Set *eOption* to BCPHINTS and set *iValue* to have a pointer to an SQLTCHAR string containing the SELECT statement.</span></span>  
  
 <span data-ttu-id="2f019-200">Questi parametri di controllo sono significativi solo in caso di copia tra un file utente e una tabella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f019-200">These control parameters are only meaningful when copying between a user file and an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="2f019-201">Le impostazioni dei parametri di controllo non hanno effetto sulle righe copiate in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="2f019-201">Control parameter settings have no effect on rows copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f019-202">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f019-202">Example</span></span>  
  
```  
// Variables like henv not specified.  
SQLHDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("address"), _T("address.add"), _T("addr.err"),  
   DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set the number of rows per batch.   
if (bcp_control(hdbc, BCPBATCH, (void*) 1000) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set file column count.   
if (bcp_columns(hdbc, 1) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set the file format.   
if (bcp_colfmt(hdbc, 1, 0, 0, SQL_VARLEN_DATA, '\n', 1, 1)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
printf_s("%ld rows processed by bulk copy.", nRowsProcessed);  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f019-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f019-203">See Also</span></span>  
 [<span data-ttu-id="2f019-204">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="2f019-204">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
