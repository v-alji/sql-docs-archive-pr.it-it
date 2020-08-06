---
title: Editor XML
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.editorxml.f1
- sql12.swb.xmleditor.f1
- vs.xmleditor
- sql12.swb.editor.xml.f1
helpviewer_keywords:
- XML Designer [SQL Server Management Studio]
ms.assetid: 0824a5ce-e67b-4b53-98d9-d371faf2d23c
author: rothja
ms.author: jroth
ms.openlocfilehash: b7c3bbbda4f5a31c4d83b559c1aa623ca2aff89f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636661"
---
# <a name="xml-editor-sql-server-management-studio"></a><span data-ttu-id="a318d-102">Editor XML (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a318d-102">XML Editor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="a318d-103">Offre una serie di strumenti visivi per utilizzare gli XML Schema, i set di dati ADO.NET e i documenti XML.</span><span class="sxs-lookup"><span data-stu-id="a318d-103">Provides a set of visual tools for working with XML Schemas, ADO.NET datasets, and XML documents.</span></span> <span data-ttu-id="a318d-104">Progettazione XML supporta il linguaggio XML Schema Definition (XSD) definito dal World Wide Web Consortium (WC3).</span><span class="sxs-lookup"><span data-stu-id="a318d-104">The XML Designer supports the XML Schema Definition (XSD) language defined by the World Wide Web Consortium (WC3).</span></span> <span data-ttu-id="a318d-105">Lo strumento di progettazione non supporta le definizioni DTD (Document Type Definitions) o altri linguaggi XML Schema, ad esempio XDR (XML-Data Reduced).</span><span class="sxs-lookup"><span data-stu-id="a318d-105">The designer does not support DTDs (document type definitions) or other XML schema languages, such as XDR (XML-Data Reduced).</span></span>  
  
 <span data-ttu-id="a318d-106">Per visualizzare Progettazione XML, aggiungere un set di dati, un XML Schema o un file XML a un progetto o aprire uno dei tipi di file descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a318d-106">To display the designer, add a dataset, XML Schema, or XML file to your project or open any of the file types listed in the table below.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="a318d-107">Il comando **Annulla** non è disponibile nella visualizzazione schema.</span><span class="sxs-lookup"><span data-stu-id="a318d-107">There is no **Undo** command when working in Schema view.</span></span> <span data-ttu-id="a318d-108">Pianificare quindi accuratamente il lavoro e salvare spesso i file.</span><span class="sxs-lookup"><span data-stu-id="a318d-108">Plan your work carefully and save your files often.</span></span>  
  
 <span data-ttu-id="a318d-109">Per consentire di lavorare sui file XML, sugli XML Schema e sui set di dati, Progettazione XML dispone delle tre visualizzazioni (o modalità) seguenti:</span><span class="sxs-lookup"><span data-stu-id="a318d-109">The designer provides the following three views (or modes) to work on XML files, XML Schemas, and datasets:</span></span>  
  
|<span data-ttu-id="a318d-110">Visualizza</span><span class="sxs-lookup"><span data-stu-id="a318d-110">View</span></span>|<span data-ttu-id="a318d-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a318d-111">Description</span></span>|<span data-ttu-id="a318d-112">Tipi di file supportati</span><span class="sxs-lookup"><span data-stu-id="a318d-112">File types supported</span></span>|  
|----------|-----------------|--------------------------|  
|<span data-ttu-id="a318d-113">**Schema**</span><span class="sxs-lookup"><span data-stu-id="a318d-113">**Schema**</span></span>|<span data-ttu-id="a318d-114">Per la creazione e la modifica in modo visivo degli XML Schema e dei set di dati ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="a318d-114">For visually creating and modifying XML Schemas and ADO.NET datasets.</span></span>|<span data-ttu-id="a318d-115">xsd</span><span class="sxs-lookup"><span data-stu-id="a318d-115">.xsd</span></span>|  
|<span data-ttu-id="a318d-116">**Dati**</span><span class="sxs-lookup"><span data-stu-id="a318d-116">**Data**</span></span>|<span data-ttu-id="a318d-117">Per la modifica in modo visivo dei file di dati XML in una griglia dati strutturata.</span><span class="sxs-lookup"><span data-stu-id="a318d-117">For visually modifying XML data files in a structured data grid.</span></span>|<span data-ttu-id="a318d-118">xml</span><span class="sxs-lookup"><span data-stu-id="a318d-118">.xml</span></span>|  
|<span data-ttu-id="a318d-119">**XML**</span><span class="sxs-lookup"><span data-stu-id="a318d-119">**XML**</span></span>|<span data-ttu-id="a318d-120">Per le modifiche XML, l'editor di origine dispone di codifica a colori e di IntelliSense, che include le funzionalità Completa parola ed Elenca membri.</span><span class="sxs-lookup"><span data-stu-id="a318d-120">For editing XML; the source editor provides color-coding and IntelliSense, including Complete Word and List Members.</span></span>|<span data-ttu-id="a318d-121">xml, xsd, xslt, wsdl, web, resx, tdl, wsf, hta, disco, vsdisco e config</span><span class="sxs-lookup"><span data-stu-id="a318d-121">.xml .xsd .xslt .wsdl.web.resx.tdl.wsf.hta.disco.vsdisco.config</span></span>|  
|<span data-ttu-id="a318d-122">**Showplan**</span><span class="sxs-lookup"><span data-stu-id="a318d-122">**ShowPlan**</span></span>|<span data-ttu-id="a318d-123">Consente di visualizzare i piani di query xml creati utilizzando l'opzione SET SHOWPLAN_XML ON.</span><span class="sxs-lookup"><span data-stu-id="a318d-123">Displays xml query plans created using the SET SHOWPLAN_XML ON option.</span></span>|<span data-ttu-id="a318d-124">showplan</span><span class="sxs-lookup"><span data-stu-id="a318d-124">.showplan</span></span>|  
  
## <a name="schema-view"></a><span data-ttu-id="a318d-125">Visualizzazione schema</span><span class="sxs-lookup"><span data-stu-id="a318d-125">Schema View</span></span>  
 <span data-ttu-id="a318d-126">La visualizzazione schema offre una rappresentazione visiva degli elementi, degli attributi, dei tipi e così via che compongono gli XML Schema e i set di dati ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="a318d-126">Schema view provides a visual representation of the elements, attributes, types, and so on, that make up XML Schemas and ADO.NET datasets.</span></span>  
  
 <span data-ttu-id="a318d-127">Nella visualizzazione schema è possibile creare schemi e set di dati trascinando gli elementi dalla scheda XML Schema della casella degli strumenti o da Esplora server e rilasciandoli sulla superficie di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a318d-127">In Schema view you can construct schemas and datasets by dropping elements on the design surface from either the XML Schema tab of the Toolbox or from Server Explorer.</span></span> <span data-ttu-id="a318d-128">È inoltre possibile aggiungere elementi allo strumento di progettazione facendo clic con il pulsante destro del mouse sulla superficie di progettazione e scegliendo Aggiungi dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="a318d-128">Additionally, you can add elements to the designer by right-clicking the design surface and selecting Add from the shortcut menu.</span></span>  
  
 <span data-ttu-id="a318d-129">Nella visualizzazione schema è possibile:</span><span class="sxs-lookup"><span data-stu-id="a318d-129">In Schema view you can:</span></span>  
  
-   <span data-ttu-id="a318d-130">Creare e modificare XML Schema e set di dati ADO.NET esistenti</span><span class="sxs-lookup"><span data-stu-id="a318d-130">Construct and modify existing XML Schemas and ADO.NET datasets</span></span>  
  
-   <span data-ttu-id="a318d-131">Creare e modificare relazioni tra le tabelle</span><span class="sxs-lookup"><span data-stu-id="a318d-131">Create and edit relationships between tables</span></span>  
  
-   <span data-ttu-id="a318d-132">Creare e modificare le chiavi</span><span class="sxs-lookup"><span data-stu-id="a318d-132">Create and edit keys</span></span>  
  
-   <span data-ttu-id="a318d-133">Generare set di dati ADO.NET da XML Schema</span><span class="sxs-lookup"><span data-stu-id="a318d-133">Generate ADO.NET datasets from XML Schemas</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a318d-134">Il layout degli elementi nella visualizzazione schema viene memorizzato nel file xsx che può essere visualizzato facendo clic su **Mostra tutti i file** sulla barra degli strumenti Esplora soluzioni e quindi espandendo il file xsd.</span><span class="sxs-lookup"><span data-stu-id="a318d-134">The layout of elements in Schema view is stored in the .xsx file, which can be seen by clicking **Show All Files** in the Solution Explorer toolbar, and then expanding the .xsd file.</span></span> <span data-ttu-id="a318d-135">Se non viene visualizzato alcun file xsx, significa che il file xsd non è mai stato aperto in Progettazione XML.</span><span class="sxs-lookup"><span data-stu-id="a318d-135">If there is no .xsx file present, it means the .xsd file has never been opened in the XML Designer.</span></span>  
  
### <a name="customizing-schema-view"></a><span data-ttu-id="a318d-136">Personalizzazione della visualizzazione schema</span><span class="sxs-lookup"><span data-stu-id="a318d-136">Customizing Schema View</span></span>  
 <span data-ttu-id="a318d-137">Le caratteristiche seguenti consentono di modificare il layout visivo degli elementi nella visualizzazione schema.</span><span class="sxs-lookup"><span data-stu-id="a318d-137">The following features modify the visual layout of elements in Schema view:</span></span>  
  
-   <span data-ttu-id="a318d-138">Zoom</span><span class="sxs-lookup"><span data-stu-id="a318d-138">Zooming</span></span>  
  
-   <span data-ttu-id="a318d-139">Espansione o compressione degli elementi nidificati</span><span class="sxs-lookup"><span data-stu-id="a318d-139">Expanding or collapsing of nested elements</span></span>  
  
-   <span data-ttu-id="a318d-140">Disposizione automatica del layout degli elementi</span><span class="sxs-lookup"><span data-stu-id="a318d-140">Automatically arranging layout of elements</span></span>  
  
-   <span data-ttu-id="a318d-141">Reimpostazione dello stato predefinito degli elementi compressi</span><span class="sxs-lookup"><span data-stu-id="a318d-141">Resetting default state of collapsed elements</span></span>  
  
##### <a name="to-expand-hidden-nested-elements"></a><span data-ttu-id="a318d-142">Per visualizzare gli elementi nidificati nascosti</span><span class="sxs-lookup"><span data-stu-id="a318d-142">To expand hidden nested elements</span></span>  
  
-   <span data-ttu-id="a318d-143">Fare clic sull'icona con il segno più alla base dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="a318d-143">Click the plus icon on the bottom of the element.</span></span>  
  
##### <a name="to-collapse-nested-elements"></a><span data-ttu-id="a318d-144">Per comprimere gli elementi nidificati</span><span class="sxs-lookup"><span data-stu-id="a318d-144">To collapse nested elements</span></span>  
  
-   <span data-ttu-id="a318d-145">Fare clic sull'icona con il segno meno sull'elemento di livello più basso che si desidera visualizzare in Progettazione XML.</span><span class="sxs-lookup"><span data-stu-id="a318d-145">Click the minus icon on the bottom-most element that you want to appear on the designer.</span></span>  
  
## <a name="data-view"></a><span data-ttu-id="a318d-146">Vista dati</span><span class="sxs-lookup"><span data-stu-id="a318d-146">Data View</span></span>  
 <span data-ttu-id="a318d-147">La visualizzazione dati dispone di una griglia dati che può essere utilizzata per modificare i file xml.</span><span class="sxs-lookup"><span data-stu-id="a318d-147">Data view provides a data grid that can be used to modify .xml files.</span></span> <span data-ttu-id="a318d-148">Nella visualizzazione dati è possibile modificare solo il contenuto di un file XML, ma non i tag e la struttura.</span><span class="sxs-lookup"><span data-stu-id="a318d-148">Only the content (but not the tags and structure) in an XML file can be edited in Data view.</span></span>  
  
 <span data-ttu-id="a318d-149">La visualizzazione dati contiene due aree separate: **Tabelle dati** e **Dati**.</span><span class="sxs-lookup"><span data-stu-id="a318d-149">There are two separate areas in Data view: **Data Tables** and **Data**.</span></span> <span data-ttu-id="a318d-150">L'area **Tabelle dati** è un elenco di relazioni definite nel file XML nello stesso ordine di annidamento (dalla più esterna alla più interna).</span><span class="sxs-lookup"><span data-stu-id="a318d-150">The **Data Tables** area is a list of relations defined in the XML file, in the order of its nesting (from the outermost to the innermost).</span></span> <span data-ttu-id="a318d-151">L'area **Dati** è una griglia dati che visualizza i dati sulla base della selezione eseguita nell'area Tabelle dati.</span><span class="sxs-lookup"><span data-stu-id="a318d-151">The **Data** area is a data grid that displays data based on the selection in the Data Tables area.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a318d-152">I file XML appena creati non contengono alcun dato e quindi non possono essere visualizzati nella visualizzazione dati.</span><span class="sxs-lookup"><span data-stu-id="a318d-152">Newly created XML files contain no data and therefore cannot be displayed in Data view.</span></span> <span data-ttu-id="a318d-153">Esistono inoltre alcuni casi di documenti XML la cui visualizzazione dati non può essere attivata.</span><span class="sxs-lookup"><span data-stu-id="a318d-153">There are also some instances of XML documents where data view cannot be invoked at all.</span></span> <span data-ttu-id="a318d-154">Benché il codice XML possa essere considerato valido, se non è strutturato i dati che cercano di passare alla visualizzazione dati genereranno il messaggio seguente: "Anche se il documento XML ha un formato corretto, contiene una struttura non visualizzabile in Visualizzazione dati".</span><span class="sxs-lookup"><span data-stu-id="a318d-154">Although the XML would be considered well formed, if it is not structured data trying to switch to Data view will generate the following message: "Although this document is well formed, it contains structure that Data View cannot display."</span></span>  
  
 <span data-ttu-id="a318d-155">Nella visualizzazione dati è possibile:</span><span class="sxs-lookup"><span data-stu-id="a318d-155">In Data view you can:</span></span>  
  
-   <span data-ttu-id="a318d-156">Popolare manualmente le tabelle di dati</span><span class="sxs-lookup"><span data-stu-id="a318d-156">Manually populate data tables</span></span>  
  
-   <span data-ttu-id="a318d-157">Modificare le tabelle di dati esistenti</span><span class="sxs-lookup"><span data-stu-id="a318d-157">Edit existing data tables</span></span>  
  
-   <span data-ttu-id="a318d-158">Generare un XML Schema da un documento XML</span><span class="sxs-lookup"><span data-stu-id="a318d-158">Generate an XML Schema from an XML document</span></span>  
  
## <a name="xml-view"></a><span data-ttu-id="a318d-159">Visualizzazione XML</span><span class="sxs-lookup"><span data-stu-id="a318d-159">XML View</span></span>  
 <span data-ttu-id="a318d-160">La visualizzazione XML dispone di un editor per modificare il codice XML non formattato e dispone inoltre di IntelliSense e della codifica a colori.</span><span class="sxs-lookup"><span data-stu-id="a318d-160">XML view provides an editor for editing raw XML and provides IntelliSense and color coding.</span></span> <span data-ttu-id="a318d-161">Quando si lavora su file xsd e xml associati a uno schema è disponibile il completamento delle istruzioni.</span><span class="sxs-lookup"><span data-stu-id="a318d-161">Statement completion is available when working on .xsd files and .xml files that have an associated schema.</span></span> <span data-ttu-id="a318d-162">Digitare \< per avviare un tag e verrà visualizzato un elenco di elementi validi in tale posizione.</span><span class="sxs-lookup"><span data-stu-id="a318d-162">Type \< to initiate a tag and you will be presented with a list of elements that are valid at that location.</span></span> <span data-ttu-id="a318d-163">Dopo avere digitato il nome dell'elemento e premuto la barra spaziatrice verrà visualizzato un elenco di attributi supportati dall'elemento.</span><span class="sxs-lookup"><span data-stu-id="a318d-163">After you type the element name and press the SPACEBAR, you will be presented with a list of attributes that the element supports.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="a318d-164">IntelliSense non sono disponibili sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="a318d-164">IntelliSense options are not available on the toolbar.</span></span> <span data-ttu-id="a318d-165">Per accedere alle opzioni, nell'editor XML scegliere **IntelliSense** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a318d-165">When in the XML Editor, to access the options, on the **Edit** menu, click **IntelliSense**.</span></span>  
  
## <a name="showplan-view"></a><span data-ttu-id="a318d-166">Visualizzazione SHOWPLAN</span><span class="sxs-lookup"><span data-stu-id="a318d-166">SHOWPLAN view</span></span>  
 <span data-ttu-id="a318d-167">I piani di query possono essere salvati in formato XML quando vengono creati con l'opzione SET SHOWPLAN_XML ON.</span><span class="sxs-lookup"><span data-stu-id="a318d-167">Query plans can be saved in XML format when created using SET SHOWPLAN_XML ON option.</span></span> <span data-ttu-id="a318d-168">Per aprire il piano di query, fare doppio clic su un file con estensione showplan.</span><span class="sxs-lookup"><span data-stu-id="a318d-168">Double-click a file with the .showplan extension to open the query plan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a318d-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a318d-169">See Also</span></span>  
 [<span data-ttu-id="a318d-170">Salvare un piano di esecuzione in formato XML</span><span class="sxs-lookup"><span data-stu-id="a318d-170">Save an Execution Plan in XML Format</span></span>](../performance/save-an-execution-plan-in-xml-format.md)  
  
  
