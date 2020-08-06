---
title: Destinazione Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldest.f1
helpviewer_keywords:
- destinations [Integration Services], Excel
- Excel [Integration Services]
ms.assetid: 37c07446-1264-4814-b4f5-9c66d333bb24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e959f14e52fc045cb0cbc2ba0255d20bd0356d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726124"
---
# <a name="excel-destination"></a><span data-ttu-id="efbf9-102">Destinazione Excel</span><span class="sxs-lookup"><span data-stu-id="efbf9-102">Excel Destination</span></span>
  <span data-ttu-id="efbf9-103">La destinazione Excel consente di caricare dati in fogli di lavoro o intervalli di una cartella di lavoro di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="efbf9-103">The Excel destination loads data into worksheets or ranges in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel workbooks.</span></span>  
  
## <a name="access-modes"></a><span data-ttu-id="efbf9-104">Modalità di accesso</span><span class="sxs-lookup"><span data-stu-id="efbf9-104">Access Modes</span></span>  
 <span data-ttu-id="efbf9-105">Sono disponibili tre diverse modalità di accesso ai dati per il caricamento dei dati:</span><span class="sxs-lookup"><span data-stu-id="efbf9-105">The Excel destination provides three different data access modes for loading data:</span></span>  
  
-   <span data-ttu-id="efbf9-106">Vista o tabella.</span><span class="sxs-lookup"><span data-stu-id="efbf9-106">A table or view.</span></span>  
  
-   <span data-ttu-id="efbf9-107">Vista o tabella specificata in una variabile.</span><span class="sxs-lookup"><span data-stu-id="efbf9-107">A table or view specified in a variable.</span></span>  
  
-   <span data-ttu-id="efbf9-108">Risultato di un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="efbf9-108">The results of an SQL statement.</span></span> <span data-ttu-id="efbf9-109">La query può essere con parametri.</span><span class="sxs-lookup"><span data-stu-id="efbf9-109">The query can be a parameterized query.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="efbf9-110">In Excel un intervallo o un foglio di lavoro equivale a una vista o tabella.</span><span class="sxs-lookup"><span data-stu-id="efbf9-110">In Excel, a worksheet or range is the equivalent of a table or view.</span></span> <span data-ttu-id="efbf9-111">Nell'elenco delle tabelle disponibili degli editor dell'origine e della destinazione Excel vengono visualizzati solo i fogli di lavoro (riconoscibili dalla presenza del simbolo $ in fondo al nome del foglio di lavoro, ad esempio Sheet1$) e gli intervalli denominati (riconoscibili dall'assenza del simbolo $, ad esempio MyRange) esistenti.</span><span class="sxs-lookup"><span data-stu-id="efbf9-111">The lists of available tables in the Excel Source and Destination editors display only existing worksheets (identified by the $ sign appended to the worksheet name, such as Sheet1$) and named ranges (identified by the absence of the $ sign, such as MyRange).</span></span>  
  
## <a name="usage-considerations"></a><span data-ttu-id="efbf9-112">Considerazioni sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="efbf9-112">Usage Considerations</span></span>  
 <span data-ttu-id="efbf9-113">La gestione connessione Excel usa il provider OLE DB [!INCLUDE[msCoName](../../includes/msconame-md.md)] per Jet 4.0 e il relativo driver ISAM (Indexed Sequential Access Method, metodo di accesso sequenziale indicizzato) di Excel di supporto per stabilire la connessione con le origini dati Excel, quindi leggere e scrivere informazioni.</span><span class="sxs-lookup"><span data-stu-id="efbf9-113">The Excel Connection Manager uses the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 and its supporting Excel ISAM (Indexed Sequential Access Method) driver to connect and read and write data to Excel data sources.</span></span>  
  
 <span data-ttu-id="efbf9-114">Il comportamento di questo provider e del relativo driver è documentato in molti articoli della [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base e, sebbene tali articoli non siano specifici di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] o del suo predecessore, Data Transformation Services, consentono di ottenere informazioni circa i comportamenti che possono produrre risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="efbf9-114">Many existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base articles document the behavior of this provider and driver, and although these articles are not specific to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] or its predecessor Data Transformation Services, you may want to know about certain behaviors that can lead to unexpected results.</span></span> <span data-ttu-id="efbf9-115">Per informazioni generali sull'utilizzo e sul comportamento del driver per Excel, vedere [HOWTO: Utilizzare ADO con dati di Excel da Visual Basic o VBA](https://support.microsoft.com/kb/257819).</span><span class="sxs-lookup"><span data-stu-id="efbf9-115">For general information on the use and behavior of the Excel driver, see [HOWTO: Use ADO with Excel Data from Visual Basic or VBA](https://support.microsoft.com/kb/257819).</span></span>  
  
 <span data-ttu-id="efbf9-116">I seguenti comportamenti del provider Jet incluso nel driver per Excel possono produrre risultati imprevisti durante il salvataggio di dati in una destinazione Excel.</span><span class="sxs-lookup"><span data-stu-id="efbf9-116">The following behaviors of the Jet provider that is included with the Excel driver can lead to unexpected results when saving data to an Excel destination.</span></span>  
  
-   <span data-ttu-id="efbf9-117">**Salvataggio di dati di testo**.</span><span class="sxs-lookup"><span data-stu-id="efbf9-117">**Saving text data**.</span></span> <span data-ttu-id="efbf9-118">Quando salva dati di testo in una destinazione Excel, il driver per Excel antepone una virgoletta singola (') al testo in ogni cella, per garantire che i valori salvati verranno interpretati come testo.</span><span class="sxs-lookup"><span data-stu-id="efbf9-118">When the Excel driver saves text data values to an Excel destination, the driver precedes the text in each cell with the single quote character (') to ensure that the saved values will be interpreted as text values.</span></span> <span data-ttu-id="efbf9-119">Se si usano o si sviluppano altre applicazioni che leggono o elaborano i dati salvati, può essere necessario includere istruzioni specifiche per la gestione della virgoletta singola (') che precede ogni valore di testo.</span><span class="sxs-lookup"><span data-stu-id="efbf9-119">If you have or develop other applications that read or process the saved data, you may need to include special handling for the single quote character that precedes each text value.</span></span>  
  
     <span data-ttu-id="efbf9-120">Per informazioni su come evitare di includere la virgoletta singola, vedere il post di blog seguente relativo all' [aggiunta della virgoletta singola a tutte le stringhe quando i dati sono trasformati in Excel tramite il componente per flusso di dati di destinazione di Excel in un pacchetto SSIS](https://go.microsoft.com/fwlink/?LinkId=400876), su msdn.com.</span><span class="sxs-lookup"><span data-stu-id="efbf9-120">For information on how to avoid including the single quote, see this blog post, [Single quote is appended to all strings when data is transformed to excel when using Excel destination data flow component in SSIS package](https://go.microsoft.com/fwlink/?LinkId=400876), on msdn.com.</span></span>  
  
-   <span data-ttu-id="efbf9-121">**Salvataggio di dati memo (ntext)**.</span><span class="sxs-lookup"><span data-stu-id="efbf9-121">**Saving memo (ntext) da**ta.</span></span> <span data-ttu-id="efbf9-122">Per poter salvare correttamente stringhe di oltre 255 caratteri in una colonna Excel, il driver deve riconoscere il tipo di dati della colonna di destinazione come **memo** invece di **string**.</span><span class="sxs-lookup"><span data-stu-id="efbf9-122">Before you can successfully save strings longer than 255 characters to an Excel column, the driver must recognize the data type of the destination column as **memo** and not **string**.</span></span> <span data-ttu-id="efbf9-123">Se la tabella di destinazione contiene già righe di dati, le prime righe campionate dal driver devono contenere almeno un'istanza di un valore composto da più di 255 caratteri nella colonna con tipo di dati memo.</span><span class="sxs-lookup"><span data-stu-id="efbf9-123">If the destination table already contains rows of data, then the first few rows that are sampled by the driver must contain at least one instance of a value longer than 255 characters in the memo column.</span></span> <span data-ttu-id="efbf9-124">Se la tabella di destinazione viene creata durante la progettazione del pacchetto o in fase di esecuzione, l'istruzione CREATE TABLE deve utilizzare LONGTEXT (o uno dei sinonimi) come tipo di dati della colonna di tipo Memo.</span><span class="sxs-lookup"><span data-stu-id="efbf9-124">If the destination table is created during package design or at run time, then the CREATE TABLE statement must use LONGTEXT (or one of its synonyms) as the data type of the memo column.</span></span>  
  
-   <span data-ttu-id="efbf9-125">**Tipi di dati**.</span><span class="sxs-lookup"><span data-stu-id="efbf9-125">**Data types**.</span></span> <span data-ttu-id="efbf9-126">Il driver per Excel riconosce solo un set limitato di tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="efbf9-126">The Excel driver recognizes only a limited set of data types.</span></span> <span data-ttu-id="efbf9-127">Tutte le colonne numeriche vengono interpretate come valori double (DT_R8) e tutte le colonne di tipo stringa (con tipo di dati diverso da memo) vengono interpretate come stringhe Unicode di 255 caratteri (DT_WSTR).</span><span class="sxs-lookup"><span data-stu-id="efbf9-127">For example, all numeric columns are interpreted as doubles (DT_R8), and all string columns (other than memo columns) are interpreted as 255-character Unicode strings (DT_WSTR).</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="efbf9-128">esegue il mapping dei tipi di dati di Excel nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="efbf9-128">maps the Excel data types as follows:</span></span>  
  
    -   <span data-ttu-id="efbf9-129">Numero    Numero a virgola mobile e precisione doppia (DT_R8)</span><span class="sxs-lookup"><span data-stu-id="efbf9-129">Numeric    double-precision float (DT_R8)</span></span>  
  
    -   <span data-ttu-id="efbf9-130">Valuta     Valuta (DT_CY)</span><span class="sxs-lookup"><span data-stu-id="efbf9-130">Currency     currency (DT_CY)</span></span>  
  
    -   <span data-ttu-id="efbf9-131">Valore booleano     Valore booleano (DT_BOOL)</span><span class="sxs-lookup"><span data-stu-id="efbf9-131">Boolean     Boolean (DT_BOOL)</span></span>  
  
    -   <span data-ttu-id="efbf9-132">Data/ora `datetime` (DT_DATE)</span><span class="sxs-lookup"><span data-stu-id="efbf9-132">Date/time     `datetime` (DT_DATE)</span></span>  
  
    -   <span data-ttu-id="efbf9-133">Stringa     Stringa Unicode di 255 caratteri (DT_WSTR)</span><span class="sxs-lookup"><span data-stu-id="efbf9-133">String     Unicode string, length 255 (DT_WSTR)</span></span>  
  
    -   <span data-ttu-id="efbf9-134">Memo     Flusso di testo Unicode (DT_NTEXT)</span><span class="sxs-lookup"><span data-stu-id="efbf9-134">Memo     Unicode text stream (DT_NTEXT)</span></span>  
  
-   <span data-ttu-id="efbf9-135">**Conversione di tipi di dati e lunghezze**.</span><span class="sxs-lookup"><span data-stu-id="efbf9-135">**Data type and length conversions**.</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="efbf9-136">non viene eseguita la conversione implicita dei tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="efbf9-136">does not implicitly convert data types.</span></span> <span data-ttu-id="efbf9-137">Può essere pertanto necessario usare le trasformazioni Colonna derivata o Conversione dati per convertire i dati di Excel in modo esplicito prima di caricarli in una destinazione diversa da Excel oppure per convertire dati non di Excel prima di caricarli in una destinazione Excel.</span><span class="sxs-lookup"><span data-stu-id="efbf9-137">As a result, you may need to use the Derived Column or Data Conversion transformations to convert Excel data explicitly before loading it into a non-Excel destination, or to convert non-Excel data before loading it into an Excel destination.</span></span> <span data-ttu-id="efbf9-138">In questo caso può essere conveniente creare il pacchetto iniziale usando Importazione/Esportazione guidata SQL Server, che configura automaticamente le conversioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="efbf9-138">In this case, it may be useful to create the initial package by using the Import and Export Wizard, which configures the necessary conversions for you.</span></span> <span data-ttu-id="efbf9-139">Di seguito sono riportati alcuni esempi di tali conversioni:</span><span class="sxs-lookup"><span data-stu-id="efbf9-139">Some examples of the conversions that may be required include the following:</span></span>  
  
    -   <span data-ttu-id="efbf9-140">Conversione tra colonne di Excel di tipo stringa Unicode e colonne di tipo stringa non Unicode con tabelle codici specifiche</span><span class="sxs-lookup"><span data-stu-id="efbf9-140">Conversion between Unicode Excel string columns and non-Unicode string columns with specific codepages.</span></span>  
  
    -   <span data-ttu-id="efbf9-141">Conversione tra colonne di Excel di tipo stringa di 255 caratteri e colonne di tipo stringa di lunghezze diverse</span><span class="sxs-lookup"><span data-stu-id="efbf9-141">Conversion between 255-character Excel string columns and string columns of different lengths.</span></span>  
  
    -   <span data-ttu-id="efbf9-142">Conversione tra colonne di Excel di tipo numerico a precisione doppia e colonne numeriche di altro tipo</span><span class="sxs-lookup"><span data-stu-id="efbf9-142">Conversion between double-precision Excel numeric columns and numeric columns of other types.</span></span>  
  
## <a name="configuration-of-the-excel-destination"></a><span data-ttu-id="efbf9-143">Configurazione della destinazione Excel</span><span class="sxs-lookup"><span data-stu-id="efbf9-143">Configuration of the Excel Destination</span></span>  
 <span data-ttu-id="efbf9-144">Per connettersi a un'origine dei dati, la destinazione Excel usa una gestione connessione Excel che specifica il file di cartella di lavoro da usare.</span><span class="sxs-lookup"><span data-stu-id="efbf9-144">The Excel destination uses an Excel connection manager to connect to a data source, and the connection manager specifies the workbook file to use.</span></span> <span data-ttu-id="efbf9-145">Per altre informazioni, vedere [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="efbf9-145">For more information, see [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span></span>  
  
 <span data-ttu-id="efbf9-146">La destinazione Excel include un input regolare e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="efbf9-146">The Excel destination has one regular input and one error output.</span></span>  
  
 <span data-ttu-id="efbf9-147">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="efbf9-147">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="efbf9-148">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor destinazione Excel** , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="efbf9-148">For more information about the properties that you can set in the **Excel Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="efbf9-149">Editor destinazione Excel &#40;pagina Gestione connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="efbf9-149">Excel Destination Editor &#40;Connection Manager Page&#41;</span></span>](../excel-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="efbf9-150">Editor destinazione Excel &#40;pagina Mapping&#41;</span><span class="sxs-lookup"><span data-stu-id="efbf9-150">Excel Destination Editor &#40;Mappings Page&#41;</span></span>](../excel-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="efbf9-151">Editor destinazione Excel &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="efbf9-151">Excel Destination Editor &#40;Error Output Page&#41;</span></span>](../excel-destination-editor-error-output-page.md)  
  
 <span data-ttu-id="efbf9-152">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="efbf9-152">The **Advanced Editor** dialog box reflects all the properties that can be set programmatically.</span></span> <span data-ttu-id="efbf9-153">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="efbf9-153">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="efbf9-154">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="efbf9-154">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="efbf9-155">Proprietà personalizzate di Excel</span><span class="sxs-lookup"><span data-stu-id="efbf9-155">Excel Custom Properties</span></span>](excel-custom-properties.md)  
  
 <span data-ttu-id="efbf9-156">Per altre informazioni su come impostare le proprietà, vedere [Impostazione delle proprietà di un componente del flusso di dati](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="efbf9-156">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="efbf9-157">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="efbf9-157">Related Tasks</span></span>  
  
-   [<span data-ttu-id="efbf9-158">Caricare dati da o in Excel con SQL Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="efbf9-158">Import data from Excel or export data to Excel with SQL Server Integration Services (SSIS)</span></span>](../load-data-to-from-excel-with-ssis.md)  
  
-   [<span data-ttu-id="efbf9-159">Esecuzione di un ciclo su file e tabelle di Excel usando un contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="efbf9-159">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
-   [<span data-ttu-id="efbf9-160">Impostazione delle proprietà di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="efbf9-160">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="efbf9-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efbf9-161">See Also</span></span>  
 <span data-ttu-id="efbf9-162">[Origine Excel](excel-source.md) </span><span class="sxs-lookup"><span data-stu-id="efbf9-162">[Excel Source](excel-source.md) </span></span>  
 <span data-ttu-id="efbf9-163">[Variabili di Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="efbf9-163">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="efbf9-164">[Flusso di dati](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="efbf9-164">[Data Flow](data-flow.md) </span></span>  
 [<span data-ttu-id="efbf9-165">Utilizzo di file di Excel con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="efbf9-165">Working with Excel Files with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-excel-files-with-the-script-task.md)  
  
  
