---
title: Creazione di un SQL Server Native Client applicazione driver ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, architecture
- SQL Server Native Client ODBC driver, creating applications
- ODBC function calls
- ODBC, header files
- ODBC applications
- ODBC applications, creating
- SQL Server Native Client ODBC driver, extensions
- applications [SQL Server Native Client]
- SQL Server Native Client ODBC driver, ODBC architecture
- extensions [ODBC]
- ODBC, driver extensions
- function calls [ODBC]
ms.assetid: c83c36e2-734e-4960-bc7e-92235910bc6f
author: rothja
ms.author: jroth
ms.openlocfilehash: c8a1719f8b60885810d9b2f8a1f1023a7ffe6e47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722711"
---
# <a name="creating-a-sql-server-native-client-odbc-driver-application"></a><span data-ttu-id="d3861-102">Creazione di un'applicazione driver ODBC di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d3861-102">Creating a SQL Server Native Client ODBC Driver Application</span></span>
  <span data-ttu-id="d3861-103">L'architettura ODBC include quattro componenti che eseguono le funzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d3861-103">ODBC architecture has four components that perform the following functions.</span></span>  
  
|<span data-ttu-id="d3861-104">Componente</span><span class="sxs-lookup"><span data-stu-id="d3861-104">Component</span></span>|<span data-ttu-id="d3861-105">Funzione</span><span class="sxs-lookup"><span data-stu-id="d3861-105">Function</span></span>|  
|---------------|--------------|  
|<span data-ttu-id="d3861-106">Applicazione</span><span class="sxs-lookup"><span data-stu-id="d3861-106">Application</span></span>|<span data-ttu-id="d3861-107">Chiama funzioni ODBC per comunicare con un'origine dati ODBC, invia istruzioni SQL ed elabora set di risultati.</span><span class="sxs-lookup"><span data-stu-id="d3861-107">Calls ODBC functions to communicate with an ODBC data source, submits SQL statements, and processes result sets.</span></span>|  
|<span data-ttu-id="d3861-108">Gestione driver</span><span class="sxs-lookup"><span data-stu-id="d3861-108">Driver Manager</span></span>|<span data-ttu-id="d3861-109">Gestisce la comunicazione tra un'applicazione e tutti i driver ODBC utilizzati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d3861-109">Manages communication between an application and all ODBC drivers used by the application.</span></span>|  
|<span data-ttu-id="d3861-110">Driver</span><span class="sxs-lookup"><span data-stu-id="d3861-110">Driver</span></span>|<span data-ttu-id="d3861-111">Elabora tutte le chiamate di funzioni ODBC dall'applicazione, si connette a un'origine dati, passa istruzioni SQL dall'applicazione all'origine dati e restituisce risultati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d3861-111">Processes all ODBC function calls from the application, connects to a data source, passes SQL statements from the application to the data source, and returns results to the application.</span></span> <span data-ttu-id="d3861-112">Se necessario, il driver converte dati ODBC SQL dall'applicazione al formato SQL nativo utilizzato dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d3861-112">If necessary, the driver translates ODBC SQL from the application to native SQL used by the data source.</span></span>|  
|<span data-ttu-id="d3861-113">Origine dati</span><span class="sxs-lookup"><span data-stu-id="d3861-113">Data source</span></span>|<span data-ttu-id="d3861-114">Contiene tutte le informazioni di cui necessita un driver per accedere a un'istanza specifica di dati in un DBMS.</span><span class="sxs-lookup"><span data-stu-id="d3861-114">Contains all information a driver needs to access a specific instance of data in a DBMS.</span></span>|  
  
 <span data-ttu-id="d3861-115">Un'applicazione che utilizza il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native Client per comunicare con un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3861-115">An application that uses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver to communicate with an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] performs the following tasks:</span></span>  
  
-   <span data-ttu-id="d3861-116">Si connette a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="d3861-116">Connects with a data source</span></span>  
  
-   <span data-ttu-id="d3861-117">Invia istruzioni SQL all'origine dati</span><span class="sxs-lookup"><span data-stu-id="d3861-117">Sends SQL statements to the data source</span></span>  
  
-   <span data-ttu-id="d3861-118">Elabora i risultati delle istruzioni dall'origine dati</span><span class="sxs-lookup"><span data-stu-id="d3861-118">Processes the results of statements from the data source</span></span>  
  
-   <span data-ttu-id="d3861-119">Elabora errori e messaggi</span><span class="sxs-lookup"><span data-stu-id="d3861-119">Processes errors and messages</span></span>  
  
-   <span data-ttu-id="d3861-120">Termina la connessione all'origine dati</span><span class="sxs-lookup"><span data-stu-id="d3861-120">Terminates the connection to the data source</span></span>  
  
 <span data-ttu-id="d3861-121">Un'applicazione più complessa scritta per il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native client potrebbe inoltre eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3861-121">A more complex application written for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver might also perform the following tasks:</span></span>  
  
-   <span data-ttu-id="d3861-122">Utilizzare cursori per controllare la posizione in un set di risultati</span><span class="sxs-lookup"><span data-stu-id="d3861-122">Use cursors to control location in a result set</span></span>  
  
-   <span data-ttu-id="d3861-123">Richiedere operazioni di commit o rollback per il controllo delle transazioni</span><span class="sxs-lookup"><span data-stu-id="d3861-123">Request commit or rollback operations for transaction control</span></span>  
  
-   <span data-ttu-id="d3861-124">Eseguire transazioni distribuite che interessano due o più server</span><span class="sxs-lookup"><span data-stu-id="d3861-124">Perform distributed transactions involving two or more servers</span></span>  
  
-   <span data-ttu-id="d3861-125">Eseguire stored procedure nel server remoto</span><span class="sxs-lookup"><span data-stu-id="d3861-125">Run stored procedures on the remote server</span></span>  
  
-   <span data-ttu-id="d3861-126">Chiamare funzioni di catalogo per richiedere informazioni sugli attributi di un set di risultati</span><span class="sxs-lookup"><span data-stu-id="d3861-126">Call catalog functions to inquire about the attributes of a result set</span></span>  
  
-   <span data-ttu-id="d3861-127">Eseguire operazioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="d3861-127">Perform bulk copy operations</span></span>  
  
-   <span data-ttu-id="d3861-128">Gestire le operazioni di dati di grandi dimensioni (**varchar (max)**, **nvarchar (max)** e **varbinary (max)** )</span><span class="sxs-lookup"><span data-stu-id="d3861-128">Manage large data (**varchar(max)**, **nvarchar(max)**, and **varbinary(max)** columns) operations</span></span>  
  
-   <span data-ttu-id="d3861-129">Utilizzare logica di riconnessione per semplificare il failover quando è configurato il mirroring del database</span><span class="sxs-lookup"><span data-stu-id="d3861-129">Use reconnection logic to facilitate failover when database mirroring is configured</span></span>  
  
-   <span data-ttu-id="d3861-130">Registrare dati relativi alle prestazioni e query con esecuzione prolungata</span><span class="sxs-lookup"><span data-stu-id="d3861-130">Log performance data and long-running queries</span></span>  
  
 <span data-ttu-id="d3861-131">Per eseguire chiamate di funzioni ODBC, un'applicazione C o C++ deve includere i file di intestazione sql.h, sqlext.h e sqltypes.h.</span><span class="sxs-lookup"><span data-stu-id="d3861-131">To make ODBC function calls, a C or C++ application must include the sql.h, sqlext.h, and sqltypes.h header files.</span></span> <span data-ttu-id="d3861-132">Per eseguire chiamate alle funzioni API del programma di installazione ODBC, un'applicazione deve includere il file di intestazione odbcinst.h.</span><span class="sxs-lookup"><span data-stu-id="d3861-132">To make calls to the ODBC installer API functions, an application must include the odbcinst.h header file.</span></span> <span data-ttu-id="d3861-133">Un'applicazione ODBC Unicode deve includere il file di intestazione sqlucode.h.</span><span class="sxs-lookup"><span data-stu-id="d3861-133">A Unicode ODBC application must include the sqlucode.h header file.</span></span> <span data-ttu-id="d3861-134">Le applicazioni ODBC devono essere collegate con il file odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="d3861-134">ODBC applications must be linked with the odbc32.lib file.</span></span> <span data-ttu-id="d3861-135">Le applicazioni ODBC che chiamano funzioni API del programma di installazione ODBC devono essere collegate con il file odbccp32.lib.</span><span class="sxs-lookup"><span data-stu-id="d3861-135">ODBC applications that call the ODBC installer API functions must be linked with the odbccp32.lib file.</span></span> <span data-ttu-id="d3861-136">Tali file sono inclusi in Windows Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="d3861-136">These files are included in the Windows Platform SDK.</span></span>  
  
 <span data-ttu-id="d3861-137">Molti driver ODBC, incluso il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native client, offrono estensioni ODBC specifiche del driver.</span><span class="sxs-lookup"><span data-stu-id="d3861-137">Many ODBC drivers, including the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver, offer driver-specific ODBC extensions.</span></span> <span data-ttu-id="d3861-138">Per sfruttare i vantaggi delle [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] estensioni specifiche del driver ODBC di Native client, un'applicazione deve includere il file di intestazione sqlncli. h.</span><span class="sxs-lookup"><span data-stu-id="d3861-138">To take advantage of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver-specific extensions, an application should include the sqlncli.h header file.</span></span> <span data-ttu-id="d3861-139">Questo file di intestazione contiene gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3861-139">This header file contains:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="d3861-140">Attributi di connessione specifici del driver ODBC di Native Client.</span><span class="sxs-lookup"><span data-stu-id="d3861-140">Native Client ODBC driver-specific connection attributes.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="d3861-141">Attributi di istruzione specifici del driver ODBC di Native Client.</span><span class="sxs-lookup"><span data-stu-id="d3861-141">Native Client ODBC driver-specific statement attributes.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="d3861-142">Attributi di colonna specifici del driver ODBC di Native Client.</span><span class="sxs-lookup"><span data-stu-id="d3861-142">Native Client ODBC driver-specific column attributes.</span></span>  
  
-   <span data-ttu-id="d3861-143">Tipi di dati specifici di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3861-143">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific data types.</span></span>  
  
-   <span data-ttu-id="d3861-144">Tipi di dati definiti dall'utente specifici di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3861-144">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific user-defined data types.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="d3861-145">Tipi di [SQLGetInfo](../../native-client-odbc-api/sqlgetinfo.md) specifici del driver ODBC di Native Client.</span><span class="sxs-lookup"><span data-stu-id="d3861-145">Native Client ODBC driver-specific [SQLGetInfo](../../native-client-odbc-api/sqlgetinfo.md) types.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="d3861-146">Campi di diagnostica del driver ODBC di Native Client.</span><span class="sxs-lookup"><span data-stu-id="d3861-146">Native Client ODBC driver diagnostics fields.</span></span>  
  
-   <span data-ttu-id="d3861-147">Codici di funzioni dinamiche di diagnostica specifiche di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3861-147">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific diagnostic dynamic function codes.</span></span>  
  
-   <span data-ttu-id="d3861-148">Definizioni di tipi C/C++ per tipi di dati C nativi specifici di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (restituite quando le colonne sono associate al tipo di dati C SQL_C_BINARY).</span><span class="sxs-lookup"><span data-stu-id="d3861-148">C/C++ type definitions for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific native C data types (returned when columns bound to C data type SQL_C_BINARY).</span></span>  
  
-   <span data-ttu-id="d3861-149">Definizione del tipo per la struttura di dati SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="d3861-149">Type definition for the SQLPERF data structure.</span></span>  
  
-   <span data-ttu-id="d3861-150">Macro e prototipi di copia bulk per supportare l'utilizzo di API per la copia bulk tramite una connessione ODBC.</span><span class="sxs-lookup"><span data-stu-id="d3861-150">Bulk copy macros and prototypes to support bulk copy API usage through an ODBC connection.</span></span>  
  
-   <span data-ttu-id="d3861-151">Chiamata delle funzioni API dei metadati delle query distribuite per ottenere elenchi di server collegati e dei relativi cataloghi.</span><span class="sxs-lookup"><span data-stu-id="d3861-151">Call the distributed query metadata API functions for lists of linked servers and their catalogs.</span></span>  
  
 <span data-ttu-id="d3861-152">Qualsiasi applicazione ODBC C o C++ che utilizza la funzionalità di copia bulk del [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native client deve essere collegata con il file sqlncli11. lib.</span><span class="sxs-lookup"><span data-stu-id="d3861-152">Any C or C++ ODBC application that uses the bulk copy feature of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver must be linked with the sqlncli11.lib file.</span></span> <span data-ttu-id="d3861-153">Le applicazioni che chiamano le funzioni API dei metadati delle query distribuite devono anch'esse essere collegate con sqlncli11.lib.</span><span class="sxs-lookup"><span data-stu-id="d3861-153">Applications calling the distributed query metadata API functions must also be linked with sqlncli11.lib.</span></span> <span data-ttu-id="d3861-154">I file sqlncli. h e sqlncli11. lib vengono distribuiti come parte degli [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] strumenti di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="d3861-154">The sqlncli.h and sqlncli11.lib files are distributed as part of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] developer's tools.</span></span> <span data-ttu-id="d3861-155">Le directory Include e Lib di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] devono essere incluse nei percorsi INCLUDE e LIB del compilatore, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d3861-155">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Include and Lib directories should be in the compiler's INCLUDE and LIB paths as in the following:</span></span>  
  
```  
LIB=c:\Program Files\Microsoft Data Access SDK 2.8\Libs\x86\lib;C:\Program Files\Microsoft SQL Server\100\Tools\SDK\Lib;  
INCLUDE=c:\Program Files\Microsoft Data Access SDK 2.8\inc;C:\Program Files\Microsoft SQL Server\100\Tools\SDK\Include;  
```  
  
 <span data-ttu-id="d3861-156">Una decisione di progettazione da adottare nelle fasi iniziali del processo di compilazione di un'applicazione consiste nello stabilire se l'applicazione debba supportare più chiamate ODBC in sospeso simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="d3861-156">One design decision made early in the process of building an application is whether the application needs to have multiple ODBC calls outstanding at the same time.</span></span> <span data-ttu-id="d3861-157">Per supportare più chiamate ODBC simultanee, sono disponibili due metodi, descritti più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d3861-157">There are two methods for supporting multiple concurrent ODBC calls, which are described in the remaining topics in this section.</span></span> <span data-ttu-id="d3861-158">Per ulteriori informazioni, vedere [ODBC Programmer ' s Reference](https://go.microsoft.com/fwlink/?LinkId=45250).</span><span class="sxs-lookup"><span data-stu-id="d3861-158">For more information, see the [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3861-159">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d3861-159">In This Section</span></span>  
  
-   [<span data-ttu-id="d3861-160">Modalità asincrona e SQLCancel</span><span class="sxs-lookup"><span data-stu-id="d3861-160">Asynchronous Mode and SQLCancel</span></span>](../../native-client-odbc-api/sqlcancel.md)  
  
-   [<span data-ttu-id="d3861-161">Applicazioni a thread multipli</span><span class="sxs-lookup"><span data-stu-id="d3861-161">Multithreaded Applications</span></span>](creating-a-driver-application-multithreaded-applications.md)  
  
## <a name="see-also"></a><span data-ttu-id="d3861-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3861-162">See Also</span></span>  
 [<span data-ttu-id="d3861-163">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="d3861-163">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
