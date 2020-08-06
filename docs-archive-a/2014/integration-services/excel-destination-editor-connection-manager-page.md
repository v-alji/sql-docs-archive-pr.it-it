---
title: Editor destinazione Excel (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldestadapter.connection.f1
helpviewer_keywords:
- Excel Destination Editor
ms.assetid: fc13f725-963c-488e-91e2-20627133e842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1556bf713c49aac31f1cc1cd624336f10dbf832f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629517"
---
# <a name="excel-destination-editor-connection-manager-page"></a><span data-ttu-id="38c06-102">Editor destinazione Excel (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="38c06-102">Excel Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="38c06-103">Utilizzare la pagina **Gestione connessione** della finestra di dialogo **Editor destinazione Excel** per specificare le informazioni sull'origine dei dati e visualizzare un'anteprima dei risultati.</span><span class="sxs-lookup"><span data-stu-id="38c06-103">Use the **Connection Manager** page of the **Excel Destination Editor** dialog box to specify data source information, and to preview the results.</span></span> <span data-ttu-id="38c06-104">La destinazione Excel carica i dati in un foglio di lavoro oppure in un intervallo denominato in una cartella di lavoro di [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38c06-104">The Excel destination loads data into a worksheet or a named range in a [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38c06-105">La `CommandTimeout` proprietà della destinazione Excel non è disponibile nell' **Editor destinazione Excel**, ma può essere impostata tramite il **Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="38c06-105">The `CommandTimeout` property of the Excel destination is not available in the **Excel Destination Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="38c06-106">Inoltre, alcune opzioni di caricamento rapido sono disponibili solo nella **Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="38c06-106">In addition, certain Fast Load options are available only in the **Advanced Editor**.</span></span> <span data-ttu-id="38c06-107">Per ulteriori informazioni su questa proprietà, vedere la sezione relativa alla destinazione Excel in [Excel Custom Properties](data-flow/excel-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="38c06-107">For more information on these properties, see the Excel Destination section of [Excel Custom Properties](data-flow/excel-custom-properties.md).</span></span>  
  
 <span data-ttu-id="38c06-108">Per ulteriori informazioni sulla destinazione Excel, vedere [Excel Destination](data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="38c06-108">To learn more about the Excel destination, see [Excel Destination](data-flow/excel-destination.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="38c06-109">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="38c06-109">Static Options</span></span>  
 <span data-ttu-id="38c06-110">**Gestione connessione Excel**</span><span class="sxs-lookup"><span data-stu-id="38c06-110">**Excel connection manager**</span></span>  
 <span data-ttu-id="38c06-111">Consente di selezionare una gestione connessione Excel esistente dall'elenco o di creare una nuova connessione facendo clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="38c06-111">Select an existing Excel connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="38c06-112">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="38c06-112">**New**</span></span>  
 <span data-ttu-id="38c06-113">Consente di creare una nuova gestione connessione nella finestra di dialogo **Gestione connessione Excel** .</span><span class="sxs-lookup"><span data-stu-id="38c06-113">Create a new connection manager by using the **Excel Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="38c06-114">**Modalità di accesso ai dati**</span><span class="sxs-lookup"><span data-stu-id="38c06-114">**Data access mode**</span></span>  
 <span data-ttu-id="38c06-115">Consente di specificare il metodo per la selezione dei dati dall'origine.</span><span class="sxs-lookup"><span data-stu-id="38c06-115">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="38c06-116">Opzione</span><span class="sxs-lookup"><span data-stu-id="38c06-116">Option</span></span>|<span data-ttu-id="38c06-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38c06-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="38c06-118">Tabella o vista</span><span class="sxs-lookup"><span data-stu-id="38c06-118">Table or view</span></span>|<span data-ttu-id="38c06-119">Carica i dati in un foglio di lavoro o in un intervallo denominato nell'origine dei dati di Excel.</span><span class="sxs-lookup"><span data-stu-id="38c06-119">Loads data into a worksheet or named range in the Excel data source.</span></span>|  
|<span data-ttu-id="38c06-120">Variabile nome vista o nome tabella</span><span class="sxs-lookup"><span data-stu-id="38c06-120">Table name or view name variable</span></span>|<span data-ttu-id="38c06-121">Consente di specificare il foglio di lavoro o il nome dell'intervallo in una variabile.</span><span class="sxs-lookup"><span data-stu-id="38c06-121">Specify the worksheet or range name in a variable.</span></span><br /><br /> <span data-ttu-id="38c06-122">**Informazioni correlate**: [Uso di variabili nei pacchetti](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="38c06-122">**Related information**: [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="38c06-123">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="38c06-123">SQL command</span></span>|<span data-ttu-id="38c06-124">Consente di caricare i dati nella destinazione Excel mediante una query SQL.</span><span class="sxs-lookup"><span data-stu-id="38c06-124">Load data into the Excel destination by using an SQL query.</span></span>|  
  
 <span data-ttu-id="38c06-125">**Nome del foglio di Excel**</span><span class="sxs-lookup"><span data-stu-id="38c06-125">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="38c06-126">Selezionare la destinazione Excel dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="38c06-126">Select the excel destination from the drop-down list.</span></span> <span data-ttu-id="38c06-127">Se l'elenco è vuoto, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="38c06-127">If the list is empty, click **New**.</span></span>  
  
 <span data-ttu-id="38c06-128">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="38c06-128">**New**</span></span>  
 <span data-ttu-id="38c06-129">Fare clic su **Nuova** per avviare la finestra di dialogo **Crea tabella** .</span><span class="sxs-lookup"><span data-stu-id="38c06-129">Click **New** to launch the **Create Table** dialog box.</span></span> <span data-ttu-id="38c06-130">Quando si fa clic su **OK**viene creato il file di Excel a cui fa riferimento **Gestione connessione Excel** .</span><span class="sxs-lookup"><span data-stu-id="38c06-130">When you click **OK**, the dialog box creates the excel file that the **Excel Connection Manager** points to.</span></span>  
  
 <span data-ttu-id="38c06-131">**Visualizza dati esistenti**</span><span class="sxs-lookup"><span data-stu-id="38c06-131">**View Existing Data**</span></span>  
 <span data-ttu-id="38c06-132">Consente di visualizzare in anteprima i risultati nella finestra di dialogo **Anteprima risultati query** .</span><span class="sxs-lookup"><span data-stu-id="38c06-132">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="38c06-133">L'anteprima supporta la visualizzazione di un massimo di 200 righe.</span><span class="sxs-lookup"><span data-stu-id="38c06-133">Preview can display up to 200 rows.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="38c06-134"> Se la **gestione connessione Excel** selezionata fa riferimento a un file di Excel che non esiste, viene visualizzato un messaggio di errore quando si fa clic su questo pulsante.</span><span class="sxs-lookup"><span data-stu-id="38c06-134">If the **Excel connection manager** you selected points to an excel file that does not exist, you will see an error message when you click this button.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="38c06-135">Opzioni dinamiche relative alla modalità di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="38c06-135">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="38c06-136">Modalità di accesso ai dati = Tabella o vista</span><span class="sxs-lookup"><span data-stu-id="38c06-136">Data access mode = Table or view</span></span>  
 <span data-ttu-id="38c06-137">**Nome del foglio di Excel**</span><span class="sxs-lookup"><span data-stu-id="38c06-137">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="38c06-138">Consente di selezionare il foglio di lavoro o l'intervallo denominato nell'elenco di quelli disponibili nell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="38c06-138">Select the name of the worksheet or named range from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="38c06-139">Modalità di accesso ai dati = Variabile nome vista o nome tabella</span><span class="sxs-lookup"><span data-stu-id="38c06-139">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="38c06-140">**Nome variabile**</span><span class="sxs-lookup"><span data-stu-id="38c06-140">**Variable name**</span></span>  
 <span data-ttu-id="38c06-141">Consente di selezionare la variabile contenente il nome del foglio di lavoro o dell'intervallo denominato.</span><span class="sxs-lookup"><span data-stu-id="38c06-141">Select the variable that contains the name of the worksheet or named range.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="38c06-142">Modalità di accesso ai dati = Comando SQL</span><span class="sxs-lookup"><span data-stu-id="38c06-142">Data access mode = SQL command</span></span>  
 <span data-ttu-id="38c06-143">**Testo comando SQL**</span><span class="sxs-lookup"><span data-stu-id="38c06-143">**SQL command text**</span></span>  
 <span data-ttu-id="38c06-144">Digitare il testo di una query SQL, fare clic su **Compila query**per compilare la query oppure scegliere **Sfoglia**per selezionare il file contenente il testo della query.</span><span class="sxs-lookup"><span data-stu-id="38c06-144">Enter the text of an SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="38c06-145">**Compila query**</span><span class="sxs-lookup"><span data-stu-id="38c06-145">**Build Query**</span></span>  
 <span data-ttu-id="38c06-146">Usare la finestra di dialogo **Generatore query** per creare la query SQL con strumenti grafici visuali.</span><span class="sxs-lookup"><span data-stu-id="38c06-146">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="38c06-147">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="38c06-147">**Browse**</span></span>  
 <span data-ttu-id="38c06-148">Usare la finestra di dialogo **Apri** per individuare il file contenente il testo della query SQL.</span><span class="sxs-lookup"><span data-stu-id="38c06-148">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="38c06-149">**Analizza query**</span><span class="sxs-lookup"><span data-stu-id="38c06-149">**Parse Query**</span></span>  
 <span data-ttu-id="38c06-150">Consente di verificare la sintassi del testo della query.</span><span class="sxs-lookup"><span data-stu-id="38c06-150">Verify the syntax of the query text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c06-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38c06-151">See Also</span></span>  
 <span data-ttu-id="38c06-152">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="38c06-152">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="38c06-153">[Editor destinazione Excel &#40;pagina mapping&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="38c06-153">[Excel Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="38c06-154">[Editor destinazione Excel &#40;pagina output degli errori&#41;](../../2014/integration-services/excel-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="38c06-154">[Excel Destination Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-destination-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="38c06-155">Esecuzione di un ciclo su file e tabelle di Excel usando un contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="38c06-155">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
