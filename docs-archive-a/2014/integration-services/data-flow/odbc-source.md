---
title: Origine ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.f1
ms.assetid: abcf34eb-9140-4100-82e6-b85bccd22abe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 792557839d60f34bdf944dab150959d4df7cb8cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626187"
---
# <a name="odbc-source"></a><span data-ttu-id="69bff-102">Origine ODBC</span><span class="sxs-lookup"><span data-stu-id="69bff-102">ODBC Source</span></span>
  <span data-ttu-id="69bff-103">Tramite l'origine ODBC vengono estratti dati da un database supportato da ODBC mediante una tabella di database, una vista o un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="69bff-103">The ODBC source extracts data from ODBC-supported database by using a database table, a view, or an SQL statement.</span></span>  
  
 <span data-ttu-id="69bff-104">Per l'origine ODBC sono disponibili le modalità di accesso ai dati seguenti per l'estrazione dei dati:</span><span class="sxs-lookup"><span data-stu-id="69bff-104">The ODBC source has the following data access modes for extracting data:</span></span>  
  
-   <span data-ttu-id="69bff-105">Vista o tabella.</span><span class="sxs-lookup"><span data-stu-id="69bff-105">A table or view.</span></span>  
  
-   <span data-ttu-id="69bff-106">Risultato di un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="69bff-106">The results of an SQL statement.</span></span>  
  
 <span data-ttu-id="69bff-107">L'origine utilizza una gestione connessione ODBC che specifica il provider da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="69bff-107">The source uses an ODBC connection manager, which specifies the provider to use.</span></span>  
  
 <span data-ttu-id="69bff-108">Un'origine ODBC include le colonne di output dei dati di origine.</span><span class="sxs-lookup"><span data-stu-id="69bff-108">An ODBC source includes the source data output columns.</span></span> <span data-ttu-id="69bff-109">Durante il mapping delle colonne di output nella destinazione ODBC alle colonne di destinazione, possono verificarsi errori se non viene eseguito il mapping di alcuna colonna di output alle colonne di destinazione.</span><span class="sxs-lookup"><span data-stu-id="69bff-109">When output columns are mapped in the ODBC destination to the destination columns, errors may occur if no output columns are mapped to the destination columns.</span></span> <span data-ttu-id="69bff-110">È possibile eseguire il mapping di colonne di tipi diversi, ma se i dati di output non sono compatibili per la destinazione, si verifica un errore in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="69bff-110">Columns of different types can be mapped, however if the output data is not compatible for the destination then an error occurs at runtime.</span></span> <span data-ttu-id="69bff-111">A seconda del comportamento in seguito all'errore, l'impostazione dell'errore verrà ignorata, provocherà un problema o la riga verrà inviata all'output degli errori.</span><span class="sxs-lookup"><span data-stu-id="69bff-111">Depending on the error behavior, setting the error will be ignored, cause a failure, or the row is sent to the error output.</span></span>  
  
 <span data-ttu-id="69bff-112">L'origine ODBC include un output regolare e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="69bff-112">The ODBC source has one regular output and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="69bff-113">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="69bff-113">Error Handling</span></span>  
 <span data-ttu-id="69bff-114">L'origine ODBC include un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="69bff-114">The ODBC source has an error output.</span></span> <span data-ttu-id="69bff-115">L'output degli errori del componente include le colonne di output seguenti:</span><span class="sxs-lookup"><span data-stu-id="69bff-115">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="69bff-116">**Error Code**: numero che corrisponde all'errore corrente.</span><span class="sxs-lookup"><span data-stu-id="69bff-116">**Error Code**: The number that corresponds to the current error.</span></span> <span data-ttu-id="69bff-117">Per un elenco degli errori, vedere la documentazione per il database supportato da ODBC in uso.</span><span class="sxs-lookup"><span data-stu-id="69bff-117">See the documentation for the ODBC-supported database you are using for a list of errors.</span></span> <span data-ttu-id="69bff-118">Per un elenco dei codici di errore SSIS, vedere la Guida di riferimento ai messaggi e ai codici di errore SSIS.</span><span class="sxs-lookup"><span data-stu-id="69bff-118">For a list of SSIS error codes, see the SSIS Error Code and Message Reference.</span></span>  
  
-   <span data-ttu-id="69bff-119">**Error Column**(Colonna errore): colonna di origine che provoca l'errore (per gli errori di conversione).</span><span class="sxs-lookup"><span data-stu-id="69bff-119">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="69bff-120">Colonne dei dati di output standard.</span><span class="sxs-lookup"><span data-stu-id="69bff-120">The standard output data columns.</span></span>  
  
 <span data-ttu-id="69bff-121">A seconda dell'impostazione del comportamento in seguito all'errore, l'origine ODBC supporta la restituzione degli errori (conversione dei dati, troncamento) che si verificano durante il processo di estrazione nell'output degli errori.</span><span class="sxs-lookup"><span data-stu-id="69bff-121">Depending on the error behavior setting, the ODBC source supports returning errors (data conversion, truncation) that occur during the extraction process in the error output.</span></span> <span data-ttu-id="69bff-122">Per altre informazioni, vedere [Editor destinazione ODBC &#40;pagina Gestione connessione&#41;](../odbc-destination-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="69bff-122">For more information, see [ODBC Destination Editor &#40;Connection Manager Page&#41;](../odbc-destination-editor-connection-manager-page.md).</span></span>  
  
## <a name="data-type-support"></a><span data-ttu-id="69bff-123">Supporto dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="69bff-123">Data Type Support</span></span>  
 <span data-ttu-id="69bff-124">Per informazioni sui tipi di dati supportati dall'origine ODBC, vedere Connettore per ODBC (Open Database Connectivity) di Attunity.</span><span class="sxs-lookup"><span data-stu-id="69bff-124">For information about the data types supported by the ODBC source, see Connector for Open Database Connectivity (ODBC) by Attunity.</span></span>  
  
## <a name="extract-options"></a><span data-ttu-id="69bff-125">Opzioni di estrazione</span><span class="sxs-lookup"><span data-stu-id="69bff-125">Extract Options</span></span>  
 <span data-ttu-id="69bff-126">L'origine ODBC usa la modalità **Batch** o **Row-by-Row** .</span><span class="sxs-lookup"><span data-stu-id="69bff-126">The ODBC source operates in either **Batch** or **Row-by-Row** mode.</span></span> <span data-ttu-id="69bff-127">La modalità utilizzata è determinata dalla proprietà **FetchMethod** .</span><span class="sxs-lookup"><span data-stu-id="69bff-127">The mode used is determined by the **FetchMethod** property.</span></span> <span data-ttu-id="69bff-128">Nell'elenco seguente vengono descritte le diverse modalità.</span><span class="sxs-lookup"><span data-stu-id="69bff-128">The following list describes the modes.</span></span>  
  
-   <span data-ttu-id="69bff-129">**Batch**: il componente tenta di usare il metodo di recupero più efficiente in base alle funzionalità del provider ODBC rilevate.</span><span class="sxs-lookup"><span data-stu-id="69bff-129">**Batch**: The component attempts to use the most efficient fetch method based on the perceived ODBC provider capabilities.</span></span> <span data-ttu-id="69bff-130">Per la maggior parte degli attuali provider ODBC, tale metodo è SQLFetchScroll con associazione di matrici (in cui le dimensioni delle matrici sono determinate dalla proprietà **BatchSize** ).</span><span class="sxs-lookup"><span data-stu-id="69bff-130">For most modern ODBC providers, this is SQLFetchScroll with array binding (where the array size is determined by the **BatchSize** property).</span></span> <span data-ttu-id="69bff-131">Se si seleziona **Batch** e il provider non supporta questo metodo, la destinazione ODBC passa automaticamente alla modalità **Riga per riga** .</span><span class="sxs-lookup"><span data-stu-id="69bff-131">If you select **Batch** and the provider does not support this method, the ODBC destination automatically switches to the **Row-by-row** mode.</span></span>  
  
-   <span data-ttu-id="69bff-132">**Row-by Row**: il componente usa SQLFetch per recuperare le righe una per volta.</span><span class="sxs-lookup"><span data-stu-id="69bff-132">**Row-by Row**: The component uses SQLFetch to retrieve the rows one at a time.</span></span>  
  
 <span data-ttu-id="69bff-133">Per altre informazioni sulla proprietà **FetchMethod** , vedere [Proprietà personalizzate dell'origine ODBC](odbc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="69bff-133">For more information about the **FetchMethod** property, see [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span></span>  
  
## <a name="parallelism"></a><span data-ttu-id="69bff-134">Parallelismo</span><span class="sxs-lookup"><span data-stu-id="69bff-134">Parallelism</span></span>  
 <span data-ttu-id="69bff-135">Non sussiste alcuna limitazione al numero di componenti dell'origine ODBC che possono essere eseguiti in parallelo rispetto alla stessa tabella o a tabelle diverse, nello stesso computer o in computer diversi, ad eccezione dei normali limiti di sessione globali.</span><span class="sxs-lookup"><span data-stu-id="69bff-135">There is no limitation on the number of ODBC source components that can run in parallel against the same table or different tables, on the same machine or on different machines (other than normal global session limits).</span></span>  
  
 <span data-ttu-id="69bff-136">Alcune limitazioni del provider ODBC utilizzato possono tuttavia ridurre il numero di connessioni simultanee tramite il provider.</span><span class="sxs-lookup"><span data-stu-id="69bff-136">However, limitations of the ODBC provider being used may restrict the number of concurrent connections through the provider.</span></span> <span data-ttu-id="69bff-137">Queste limitazioni riducono il numero di possibili istanze parallele supportate per l'origine ODBC.</span><span class="sxs-lookup"><span data-stu-id="69bff-137">These limitations limit the number of supported parallel instances possible for the ODBC source.</span></span> <span data-ttu-id="69bff-138">Lo sviluppatore di SSIS deve essere a conoscenza delle limitazioni di qualsiasi provider ODBC utilizzato e tenerne conto in caso di compilazione di pacchetti SSIS.</span><span class="sxs-lookup"><span data-stu-id="69bff-138">The SSIS developer must be aware of the limitations of any ODBC provider being used and take them into consideration when building SSIS packages.</span></span>  
  
## <a name="troubleshooting-the-odbc-source"></a><span data-ttu-id="69bff-139">Risoluzione dei problemi relativi all'origine ODBC</span><span class="sxs-lookup"><span data-stu-id="69bff-139">Troubleshooting the ODBC Source</span></span>  
 <span data-ttu-id="69bff-140">È possibile registrare le chiamate eseguite dall'origine ODBC a provider di dati esterni.</span><span class="sxs-lookup"><span data-stu-id="69bff-140">You can log the calls that the ODBC source makes to external data providers.</span></span> <span data-ttu-id="69bff-141">Questa funzionalità di registrazione può essere utilizzata per risolvere i problemi relativi al caricamento di dati da origini dati esterne eseguito dall'origine ODBC.</span><span class="sxs-lookup"><span data-stu-id="69bff-141">You can use this logging capability to troubleshoot the loading of data from external data sources that the ODBC source performs.</span></span> <span data-ttu-id="69bff-142">Per registrare le chiamate eseguite dall'origine ODBC a provider di dati esterni, abilitare la traccia di Gestione driver ODBC.</span><span class="sxs-lookup"><span data-stu-id="69bff-142">To log the calls that the ODBC source makes to external data providers, enable the ODBC driver manager trace.</span></span> <span data-ttu-id="69bff-143">Per altre informazioni, vedere la documentazione di Microsoft su *come generare una traccia ODBC con l'amministratore dell'origine dati ODBC*.</span><span class="sxs-lookup"><span data-stu-id="69bff-143">For more information, see the Microsoft documentation on *How To Generate an ODBC Trace with ODBC the Data Source Administrator.*</span></span>  
  
## <a name="configuring-the-odbc-source"></a><span data-ttu-id="69bff-144">Configurazione dell'origine ODBC</span><span class="sxs-lookup"><span data-stu-id="69bff-144">Configuring the ODBC Source</span></span>  
 <span data-ttu-id="69bff-145">È possibile configurare l'origine ODBC a livello di codice o tramite Progettazione SSIS.</span><span class="sxs-lookup"><span data-stu-id="69bff-145">You can configure the ODBC source programmatically or through the SSIS Designer.</span></span>  
  
 <span data-ttu-id="69bff-146">Per ulteriori informazioni, vedere uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="69bff-146">For more information, see one of the following topics:</span></span>  
  
-   [<span data-ttu-id="69bff-147">Editor origine ODBC &#40;pagina Gestione connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="69bff-147">ODBC Source Editor &#40;Connection Manager Page&#41;</span></span>](../odbc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="69bff-148">Editor origine ODBC &#40;pagina Colonne&#41;</span><span class="sxs-lookup"><span data-stu-id="69bff-148">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../odbc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="69bff-149">Editor origine ODBC &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="69bff-149">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
 <span data-ttu-id="69bff-150">La finestra di dialogo **Editor avanzato** contiene le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="69bff-150">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="69bff-151">Per aprire la finestra di dialogo **Editor avanzato** :</span><span class="sxs-lookup"><span data-stu-id="69bff-151">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="69bff-152">Nella schermata **Flusso di dati** del progetto di [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] fare clic con il pulsante destro del mouse sull'origine ODBC e scegliere **Visualizza editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="69bff-152">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the ODBC source and select **Show Advanced Editor**.</span></span>  
  
 <span data-ttu-id="69bff-153">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo Editor avanzato, vedere [Proprietà personalizzate dell'origine ODBC](odbc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="69bff-153">For more information about the properties that you can set in the Advanced Editor dialog box, see [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69bff-154">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="69bff-154">In This Section</span></span>  
  
-   [<span data-ttu-id="69bff-155">Editor origine ODBC &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="69bff-155">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="69bff-156">Editor origine ODBC &#40;pagina Colonne&#41;</span><span class="sxs-lookup"><span data-stu-id="69bff-156">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../odbc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="69bff-157">Editor origine ODBC &#40;pagina Gestione connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="69bff-157">ODBC Source Editor &#40;Connection Manager Page&#41;</span></span>](../odbc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="69bff-158">Estrarre dati tramite l'origine ODBC</span><span class="sxs-lookup"><span data-stu-id="69bff-158">Extract Data by Using the ODBC Source</span></span>](odbc-source.md)  
  
-   [<span data-ttu-id="69bff-159">Proprietà personalizzate dell'origine ODBC</span><span class="sxs-lookup"><span data-stu-id="69bff-159">ODBC Source Custom Properties</span></span>](odbc-source-custom-properties.md)  
  
  
