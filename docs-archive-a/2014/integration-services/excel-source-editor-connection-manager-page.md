---
title: Editor origine Excel (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsourceadapter.connection.f1
helpviewer_keywords:
- Excel Source Editor
ms.assetid: 428e04e0-ad98-45d0-8345-12ec1b67b2eb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3285b5c8b14016b91005af79542e3e2f9b6559b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629501"
---
# <a name="excel-source-editor-connection-manager-page"></a><span data-ttu-id="7a1e6-102">Editor origine Excel (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="7a1e6-102">Excel Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="7a1e6-103">Usare il nodo **Gestione connessione** della finestra di dialogo **Editor origine Excel** per selezionare la cartella di lavoro di [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] da usare come origine.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-103">Use the **Connection Manager** node of the **Excel Source Editor** dialog box to select the [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook for the source to use.</span></span> <span data-ttu-id="7a1e6-104">L'origine Excel legge i dati da un foglio di lavoro o da un intervallo denominato in una cartella di lavoro esistente.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-104">The Excel source reads data from a worksheet or named range in an existing workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a1e6-105">La `CommandTimeout` proprietà dell'origine Excel non è disponibile nell' **Editor origine Excel**, ma può essere impostata tramite il **Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-105">The `CommandTimeout` property of the Excel source is not available in the **Excel Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="7a1e6-106">Per altre informazioni su questa proprietà, vedere la sezione relativa all'origine Excel in [Proprietà personalizzate di Excel](data-flow/excel-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7a1e6-106">For more information on this property, see the Excel Source section of [Excel Custom Properties](data-flow/excel-custom-properties.md).</span></span>  
  
 <span data-ttu-id="7a1e6-107">Per ulteriori informazioni sull'origine Excel, vedere [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="7a1e6-107">To learn more about the Excel source, see [Excel Source](data-flow/excel-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="7a1e6-108">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="7a1e6-108">Static Options</span></span>  
 <span data-ttu-id="7a1e6-109">**Gestione connessione OLE DB**</span><span class="sxs-lookup"><span data-stu-id="7a1e6-109">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="7a1e6-110">Consente di selezionare una gestione connessione Excel esistente dall'elenco o di creare una nuova connessione facendo clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-110">Select an existing Excel connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="7a1e6-111">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="7a1e6-111">**New**</span></span>  
 <span data-ttu-id="7a1e6-112">Consente di creare una nuova gestione connessione nella finestra di dialogo **Gestione connessione Excel** .</span><span class="sxs-lookup"><span data-stu-id="7a1e6-112">Create a new connection manager by using the **Excel Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="7a1e6-113">**Modalità di accesso ai dati**</span><span class="sxs-lookup"><span data-stu-id="7a1e6-113">**Data access mode**</span></span>  
 <span data-ttu-id="7a1e6-114">Consente di specificare il metodo per la selezione dei dati dall'origine.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-114">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="7a1e6-115">Valore</span><span class="sxs-lookup"><span data-stu-id="7a1e6-115">Value</span></span>|<span data-ttu-id="7a1e6-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a1e6-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7a1e6-117">Tabella o vista</span><span class="sxs-lookup"><span data-stu-id="7a1e6-117">Table or view</span></span>|<span data-ttu-id="7a1e6-118">Consente di recuperare dati da un foglio di lavoro o da un intervallo denominato nel file di Excel.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-118">Retrieve data from a worksheet or named range in the Excel file.</span></span>|  
|<span data-ttu-id="7a1e6-119">Variabile nome vista o nome tabella</span><span class="sxs-lookup"><span data-stu-id="7a1e6-119">Table name or view name variable</span></span>|<span data-ttu-id="7a1e6-120">Consente di specificare il foglio di lavoro o il nome dell'intervallo in una variabile.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-120">Specify the worksheet or range name in a variable.</span></span><br /><br /> <span data-ttu-id="7a1e6-121">**Informazioni correlate:** [Uso di variabili nei pacchetti](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="7a1e6-121">**Related information:** [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="7a1e6-122">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="7a1e6-122">SQL command</span></span>|<span data-ttu-id="7a1e6-123">Consente di recuperare dati dal file di Excel utilizzando una query SQL.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-123">Retrieve data from the Excel file by using a SQL query.</span></span> <span data-ttu-id="7a1e6-124">Per informazioni sulla sintassi di query, vedere [Origine Excel](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="7a1e6-124">For information about query syntax, see [Excel Source](data-flow/excel-source.md).</span></span>|  
|<span data-ttu-id="7a1e6-125">Comando SQL da variabile</span><span class="sxs-lookup"><span data-stu-id="7a1e6-125">SQL command from variable</span></span>|<span data-ttu-id="7a1e6-126">Consente di specificare il testo della query SQL in una variabile.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-126">Specify the SQL query text in a variable.</span></span>|  
  
 <span data-ttu-id="7a1e6-127">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="7a1e6-127">**Preview**</span></span>  
 <span data-ttu-id="7a1e6-128">Consente di visualizzare in anteprima i risultati nella finestra di dialogo **Vista dati** .</span><span class="sxs-lookup"><span data-stu-id="7a1e6-128">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="7a1e6-129">L'anteprima supporta la visualizzazione di un massimo di 200 righe.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-129">Preview can display up to 200 rows.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="7a1e6-130">Opzioni dinamiche relative alla modalità di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="7a1e6-130">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="7a1e6-131">Modalità di accesso ai dati = Tabella o vista</span><span class="sxs-lookup"><span data-stu-id="7a1e6-131">Data access mode = Table or view</span></span>  
 <span data-ttu-id="7a1e6-132">**Nome del foglio di Excel**</span><span class="sxs-lookup"><span data-stu-id="7a1e6-132">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="7a1e6-133">Consente di selezionare il nome del foglio di lavoro o dell'intervallo denominato in un elenco di fogli di lavoro o intervalli disponibili nella cartella di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-133">Select the name of the worksheet or named range from a list of those available in the Excel workbook.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="7a1e6-134">Modalità di accesso ai dati = Variabile nome vista o nome tabella</span><span class="sxs-lookup"><span data-stu-id="7a1e6-134">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="7a1e6-135">**Nome variabile**</span><span class="sxs-lookup"><span data-stu-id="7a1e6-135">**Variable name**</span></span>  
 <span data-ttu-id="7a1e6-136">Consente di selezionare la variabile contenente il nome del foglio di lavoro o dell'intervallo denominato.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-136">Select the variable that contains the name of the worksheet or named range.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="7a1e6-137">Modalità di accesso ai dati = Comando SQL</span><span class="sxs-lookup"><span data-stu-id="7a1e6-137">Data access mode = SQL command</span></span>  
 <span data-ttu-id="7a1e6-138">**Testo comando SQL**</span><span class="sxs-lookup"><span data-stu-id="7a1e6-138">**SQL command text**</span></span>  
 <span data-ttu-id="7a1e6-139">È possibile digitare il testo di una query SQL, compilare la query facendo clic su **Compila query**o cercare il file contenente il testo della query facendo clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-139">Enter the text of a SQL query, build the query by clicking **Build Query**, or browse to the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="7a1e6-140">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="7a1e6-140">**Parameters**</span></span>  
 <span data-ttu-id="7a1e6-141">Se è stata immessa una query con parametri utilizzando ?</span><span class="sxs-lookup"><span data-stu-id="7a1e6-141">If you have entered a parameterized query by using ?</span></span> <span data-ttu-id="7a1e6-142">come segnaposto per il parametro nel testo della query, usare la finestra di dialogo **Imposta parametri query** per eseguire il mapping tra i parametri di input della query e le variabili del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-142">as a parameter placeholder in the query text, use the **Set Query Parameters** dialog box to map query input parameters to package variables.</span></span>  
  
 <span data-ttu-id="7a1e6-143">**Compila query**</span><span class="sxs-lookup"><span data-stu-id="7a1e6-143">**Build query**</span></span>  
 <span data-ttu-id="7a1e6-144">Usare la finestra di dialogo **Generatore query** per creare la query SQL con strumenti grafici visuali.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-144">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="7a1e6-145">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="7a1e6-145">**Browse**</span></span>  
 <span data-ttu-id="7a1e6-146">Usare la finestra di dialogo **Apri** per individuare il file contenente il testo della query SQL.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-146">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="7a1e6-147">**Analizza query**</span><span class="sxs-lookup"><span data-stu-id="7a1e6-147">**Parse query**</span></span>  
 <span data-ttu-id="7a1e6-148">Consente di verificare la sintassi del testo della query.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-148">Verify the syntax of the query text.</span></span>  
  
### <a name="data-access-mode--sql-command-from-variable"></a><span data-ttu-id="7a1e6-149">Modalità di accesso ai dati = Comando SQL da variabile</span><span class="sxs-lookup"><span data-stu-id="7a1e6-149">Data access mode = SQL command from variable</span></span>  
 <span data-ttu-id="7a1e6-150">**Nome variabile**</span><span class="sxs-lookup"><span data-stu-id="7a1e6-150">**Variable name**</span></span>  
 <span data-ttu-id="7a1e6-151">Consente di selezionare la variabile contenente il testo della query SQL.</span><span class="sxs-lookup"><span data-stu-id="7a1e6-151">Select the variable that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a1e6-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a1e6-152">See Also</span></span>  
 <span data-ttu-id="7a1e6-153">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7a1e6-153">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="7a1e6-154">[Editor origine Excel &#40;pagina colonne&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="7a1e6-154">[Excel Source Editor &#40;Columns Page&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="7a1e6-155">[Editor origine Excel &#40;pagina output degli errori&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="7a1e6-155">[Excel Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="7a1e6-156">[Gestione connessione Excel](connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="7a1e6-156">[Excel Connection Manager](connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="7a1e6-157">Esecuzione di un ciclo su file e tabelle di Excel usando un contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="7a1e6-157">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
