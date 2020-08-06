---
title: Destinazione SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdest.f1
helpviewer_keywords:
- SQL Server destination
- loading data
- destinations [Integration Services], SQL Server
- inserting data
- bulk load [Integration Services]
ms.assetid: a0227cd8-6944-4547-87e8-7b2507e26442
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fcd65007e1e6af36386cb2ceba1f7242305b81a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713352"
---
# <a name="sql-server-destination"></a><span data-ttu-id="fb2ef-102">SQL Server - destinazione</span><span class="sxs-lookup"><span data-stu-id="fb2ef-102">SQL Server Destination</span></span>
  <span data-ttu-id="fb2ef-103">La destinazione SQL Server si connette a un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] locale ed esegue il caricamento bulk dei dati nelle tabelle e nelle viste di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb2ef-103">The SQL Server destination connects to a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and bulk loads data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables and views.</span></span> <span data-ttu-id="fb2ef-104">Non è possibile usare la destinazione SQL Server nei pacchetti che accedono a un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un server remoto.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-104">You cannot use the SQL Server destination in packages that access a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database on a remote server.</span></span> <span data-ttu-id="fb2ef-105">Per tali pacchetti, utilizzare la destinazione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-105">Instead, the packages should use the OLE DB destination.</span></span> <span data-ttu-id="fb2ef-106">Per altre informazioni, vedere [OLE DB Destination](ole-db-destination.md).</span><span class="sxs-lookup"><span data-stu-id="fb2ef-106">For more information, see [OLE DB Destination](ole-db-destination.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="fb2ef-107">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="fb2ef-107">Permissions</span></span>  
 <span data-ttu-id="fb2ef-108">Gli utenti che eseguono pacchetti che includono la destinazione SQL Server devono disporre dell'autorizzazione "Creazione oggetti globali",</span><span class="sxs-lookup"><span data-stu-id="fb2ef-108">Users who execute packages that include the SQL Server destination require the "Create global objects" permission.</span></span> <span data-ttu-id="fb2ef-109">che può essere concessa tramite lo strumento Criteri di sicurezza locali, accessibile dal menu **Strumenti di amministrazione** .</span><span class="sxs-lookup"><span data-stu-id="fb2ef-109">You can grant this permission to users by using the Local Security Policy tool opened from the **Administrative Tools** menu.</span></span> <span data-ttu-id="fb2ef-110">Se durante l'esecuzione di un pacchetto che utilizza la destinazione SQL Server viene visualizzato un messaggio di errore, verificare che l'account utilizzato per eseguire il pacchetto disponga dell'autorizzazione "Creazione oggetti globali".</span><span class="sxs-lookup"><span data-stu-id="fb2ef-110">If you receive an error message when executing a package that uses the SQL Server destination, make sure that the account running the package has the "Create global objects" permission.</span></span>  
  
## <a name="bulk-inserts"></a><span data-ttu-id="fb2ef-111">Inserimenti bulk</span><span class="sxs-lookup"><span data-stu-id="fb2ef-111">Bulk Inserts</span></span>  
 <span data-ttu-id="fb2ef-112">Se si tenta di utilizzare la destinazione SQL Server per il caricamento bulk dei dati in un database remoto di SQL Server, potrebbe venire visualizzato un messaggio di errore simile a "È disponibile un record OLE DB.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-112">If you attempt to use the SQL Server destination to bulk load data into a remote SQL Server database, you may see an error message similar to the following: "An OLE DB record is available.</span></span> <span data-ttu-id="fb2ef-113">Origine: "Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client" Hresult: 0x80040E14 Descrizione: "Impossibile eseguire il caricamento bulk perché non è stato possibile aprire l'oggetto di mapping dei file SSIS 'Global\DTSQLIMPORT'.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-113">Source: "Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client" Hresult: 0x80040E14 Description: "Could not bulk load because SSIS file mapping object 'Global\DTSQLIMPORT ' could not be opened.</span></span> <span data-ttu-id="fb2ef-114">Codice di errore del sistema operativo 2 (Impossibile trovare il file specificato).</span><span class="sxs-lookup"><span data-stu-id="fb2ef-114">Operating system error code 2 (The system cannot find the file specified.).</span></span> <span data-ttu-id="fb2ef-115">Verificare che l'accesso venga effettuato a un server locale tramite la sicurezza di Windows.""</span><span class="sxs-lookup"><span data-stu-id="fb2ef-115">Make sure you are accessing a local server via Windows security.""</span></span>  
  
 <span data-ttu-id="fb2ef-116">La destinazione SQL Server offre lo stesso tipo di inserimento dei dati ad alta velocità in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] garantito dall'attività Inserimento bulk. Se si usa la destinazione SQL Server, tuttavia, un pacchetto può applicare le trasformazioni ai dati delle colonne prima che vengano caricati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb2ef-116">The SQL Server destination offers the same high-speed insertion of data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that the Bulk Insert task provides; however, by using the SQL Server destination, a package can apply transformations to column data before the data is loaded into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fb2ef-117">Per il caricamento dei dati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è consigliabile utilizzare la destinazione SQL Server invece della destinazione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-117">For loading data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you should consider using the SQL Server destination instead of the OLE DB destination.</span></span>  
  
### <a name="bulk-insert-options"></a><span data-ttu-id="fb2ef-118">Opzioni per l'inserimento bulk</span><span class="sxs-lookup"><span data-stu-id="fb2ef-118">Bulk Insert Options</span></span>  
 <span data-ttu-id="fb2ef-119">Se la destinazione SQL Server utilizza una modalità di accesso ai dati con caricamento rapido, sarà possibile specificare le opzioni di caricamento rapido seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb2ef-119">If the SQL Server destination uses a fast-load data access mode, you can specify the following fast load options:</span></span>  
  
-   <span data-ttu-id="fb2ef-120">È possibile mantenere i valori Identity del file di dati importato o utilizzare valori univoci assegnati da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb2ef-120">Retain identity values from the imported data file, or use unique values assigned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="fb2ef-121">È possibile mantenere i valori Null durante l'operazione di caricamento bulk.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-121">Retain null values during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="fb2ef-122">È possibile verificare i vincoli sulla tabella o vista di destinazione durante l'operazione di importazione bulk.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-122">Verify constraints on the target table or view during the bulk import operation.</span></span>  
  
-   <span data-ttu-id="fb2ef-123">È possibile acquisire un blocco a livello di tabella per la durata dell'operazione di caricamento bulk.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-123">Acquire a table-level lock for the duration of the bulk load operation.</span></span>  
  
-   <span data-ttu-id="fb2ef-124">È possibile eseguire trigger di inserimento definiti sulla tabella di destinazione durante l'operazione di caricamento bulk.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-124">Execute insert triggers defined on the destination table during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="fb2ef-125">È possibile specificare il numero della prima riga nell'input da caricare durante l'operazione di inserimento bulk.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-125">Specify the number of the first row in the input to load during the bulk insert operation.</span></span>  
  
-   <span data-ttu-id="fb2ef-126">È possibile specificare il numero dell'ultima riga nell'input da caricare durante l'operazione di inserimento bulk.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-126">Specify the number of the last row in the input to load during the bulk insert operation.</span></span>  
  
-   <span data-ttu-id="fb2ef-127">È possibile specificare il numero massimo di errori che si possono verificare prima che l'operazione di caricamento bulk venga annullata.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-127">Specify the maximum number of errors allowed before the bulk load operation is canceled.</span></span> <span data-ttu-id="fb2ef-128">Ogni riga che non può essere importata viene conteggiata come errore.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-128">Each row that cannot be imported is counted as one error.</span></span>  
  
-   <span data-ttu-id="fb2ef-129">È possibile specificare le colonne nell'input che contengono dati ordinati.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-129">Specify the columns in the input that contain sorted data.</span></span>  
  
 <span data-ttu-id="fb2ef-130">Per altre informazioni sulle opzioni di caricamento bulk, vedere [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fb2ef-130">For more information about bulk load options, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
#### <a name="performance-improvements"></a><span data-ttu-id="fb2ef-131">Miglioramenti alle prestazioni</span><span class="sxs-lookup"><span data-stu-id="fb2ef-131">Performance Improvements</span></span>  
 <span data-ttu-id="fb2ef-132">Per migliorare le prestazioni dell'inserimento bulk e dell'accesso ai dati delle tabelle durante un'operazione di inserimento bulk, modificare le opzioni predefinite nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="fb2ef-132">To improve the performance of a bulk insert and the access to table data during the bulk insert operation, you should change the default options as follows:</span></span>  
  
-   <span data-ttu-id="fb2ef-133">Non verificare i vincoli sulla tabella o vista di destinazione durante l'operazione di importazione bulk.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-133">Do not verify constraints on the target table or view during the bulk import operation.</span></span>  
  
-   <span data-ttu-id="fb2ef-134">Non eseguire trigger di inserimento definiti sulla tabella di destinazione durante l'operazione di caricamento bulk.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-134">Do not execute insert triggers defined on the destination table during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="fb2ef-135">Non applicare blocchi alla tabella,</span><span class="sxs-lookup"><span data-stu-id="fb2ef-135">Do not apply a lock to the table.</span></span> <span data-ttu-id="fb2ef-136">in modo che rimanga disponibile ad altri utenti e applicazioni durante l'operazione di inserimento bulk.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-136">That way, the table remains available to other users and applications during the bulk insert operation.</span></span>  
  
## <a name="configuration-of-the-sql-server-destination"></a><span data-ttu-id="fb2ef-137">Configurazione della destinazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb2ef-137">Configuration of the SQL Server Destination</span></span>  
 <span data-ttu-id="fb2ef-138">È possibile configurare la destinazione SQL Server nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb2ef-138">You can configure the SQL Server destination in the following ways:</span></span>  
  
-   <span data-ttu-id="fb2ef-139">Specificare la tabella o vista in cui eseguire il caricamento bulk dei dati.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-139">Specify the table or view into which to bulk load the data.</span></span>  
  
-   <span data-ttu-id="fb2ef-140">Personalizzare l'operazione di caricamento bulk specificando opzioni quale il controllo dei vincoli.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-140">Customize the bulk load operation by specifying options such as whether to check constraints.</span></span>  
  
-   <span data-ttu-id="fb2ef-141">Specificare se deve essere eseguito il commit di tutte le righe in un batch oppure impostare il numero massimo di righe di cui eseguire il commit in un batch.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-141">Specify whether all rows commit in one batch or set the maximum number of rows to commit as a batch.</span></span>  
  
-   <span data-ttu-id="fb2ef-142">Specificare un timeout per l'operazione di caricamento bulk.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-142">Specify a time-out for the bulk load operation.</span></span>  
  
 <span data-ttu-id="fb2ef-143">Per connettersi a un'origine dei dati questa destinazione utilizza una gestione connessione OLE DB, che specifica il provider OLE DB da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-143">This destination uses an OLE DB connection manager to connect to a data source, and the connection manager specifies the OLE DB provider to use.</span></span> <span data-ttu-id="fb2ef-144">Per altre informazioni, vedere [Gestione connessione OLE DB](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fb2ef-144">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
 <span data-ttu-id="fb2ef-145">Un progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] fornisce inoltre l'oggetto origine dei dati da cui è possibile creare una gestione connessione OLE DB,</span><span class="sxs-lookup"><span data-stu-id="fb2ef-145">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project also provides the data source object from which you can create an OLE DB connection manager.</span></span> <span data-ttu-id="fb2ef-146">in modo da rendere disponibili le origini dei dati e le viste origine dati alla destinazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-146">This makes data sources and data source views available to the SQL Server destination.</span></span>  
  
 <span data-ttu-id="fb2ef-147">La destinazione SQL Server include un input.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-147">The SQL Server destination has one input.</span></span> <span data-ttu-id="fb2ef-148">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-148">It does not support an error output.</span></span>  
  
 <span data-ttu-id="fb2ef-149">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-149">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="fb2ef-150">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor destinazione SQL Server**, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb2ef-150">For more information about the properties that you can set in the **SQL Server Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fb2ef-151">Editor destinazione SQL &#40;pagina Gestione connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="fb2ef-151">SQL Destination Editor &#40;Connection Manager Page&#41;</span></span>](../sql-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="fb2ef-152">Editor destinazione SQL &#40;pagina Mapping&#41;</span><span class="sxs-lookup"><span data-stu-id="fb2ef-152">SQL Destination Editor &#40;Mappings Page&#41;</span></span>](../sql-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="fb2ef-153">Editor destinazione SQL &#40;pagina Avanzate&#41;</span><span class="sxs-lookup"><span data-stu-id="fb2ef-153">SQL Destination Editor &#40;Advanced Page&#41;</span></span>](../sql-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="fb2ef-154">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-154">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="fb2ef-155">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb2ef-155">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fb2ef-156">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="fb2ef-156">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="fb2ef-157">Proprietà personalizzate della destinazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb2ef-157">SQL Server Destination Custom Properties</span></span>](sql-server-destination-custom-properties.md)  
  
 <span data-ttu-id="fb2ef-158">Per ulteriori informazioni sulle procedure per l'impostazione delle proprietà, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb2ef-158">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fb2ef-159">Caricamento bulk dei dati tramite la destinazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb2ef-159">Bulk Load Data by Using the SQL Server Destination</span></span>](sql-server-destination.md)  
  
-   [<span data-ttu-id="fb2ef-160">Impostazione delle proprietà di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="fb2ef-160">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="fb2ef-161">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="fb2ef-161">Related Tasks</span></span>  
  
-   [<span data-ttu-id="fb2ef-162">Caricamento bulk dei dati tramite la destinazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb2ef-162">Bulk Load Data by Using the SQL Server Destination</span></span>](sql-server-destination.md)  
  
-   [<span data-ttu-id="fb2ef-163">Impostazione delle proprietà di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="fb2ef-163">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-content"></a><span data-ttu-id="fb2ef-164">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="fb2ef-164">Related Content</span></span>  
  
-   <span data-ttu-id="fb2ef-165">Articolo tecnico relativo alla possibile [visualizzazione dell'errore "Impossibile preparare l'attività Inserimento bulk SSIS per l'inserimento dei dati" nei sistemi con Controllo dell'account utente abilitato](https://go.microsoft.com/fwlink/?LinkId=199482)sul sito support.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-165">Technical article, [You may get "Unable to prepare the SSIS bulk insert for data insertion" error on UAC enabled systems](https://go.microsoft.com/fwlink/?LinkId=199482), on support.microsoft.com.</span></span>  
  
-   <span data-ttu-id="fb2ef-166">Articolo tecnico relativo alla [guida alle prestazioni del caricamento dati](https://go.microsoft.com/fwlink/?LinkId=233700)sul sito msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-166">Technical article, [The Data Loading Performance Guide](https://go.microsoft.com/fwlink/?LinkId=233700), on msdn.microsoft.com.</span></span>  
  
-   <span data-ttu-id="fb2ef-167">Articolo tecnico relativo all' [utilizzo di SQL Server Integration Services per il caricamento bulk dei dati](https://go.microsoft.com/fwlink/?LinkId=233701)sul sito Web simple-talk.com.</span><span class="sxs-lookup"><span data-stu-id="fb2ef-167">Technical article, [Using SQL Server Integration Services to Bulk Load Data](https://go.microsoft.com/fwlink/?LinkId=233701), on simple-talk.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2ef-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb2ef-168">See Also</span></span>  
 [<span data-ttu-id="fb2ef-169">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="fb2ef-169">Data Flow</span></span>](data-flow.md)  
  
  
