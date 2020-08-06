---
title: Creazione di un'origine con il componente script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], source components
- output columns [Integration Services]
- sources [Integration Services], components
ms.assetid: 547c4179-ea82-4265-8c6f-04a2aa77a3c0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a352348f7f47157c5f2ec6d3ff01cea47de0ffb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629482"
---
# <a name="creating-a-source-with-the-script-component"></a><span data-ttu-id="485b9-102">Creazione di un'origine con il componente script</span><span class="sxs-lookup"><span data-stu-id="485b9-102">Creating a Source with the Script Component</span></span>
  <span data-ttu-id="485b9-103">Utilizzare un componente di origine nel flusso di dati di un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per caricare dati da un'origine dati da passare a trasformazioni e destinazioni a valle.</span><span class="sxs-lookup"><span data-stu-id="485b9-103">You use a source component in the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package to load data from a data source to pass on to downstream transformations and destinations.</span></span> <span data-ttu-id="485b9-104">Normalmente, ci si connette all'origine dati tramite una gestione connessione esistente.</span><span class="sxs-lookup"><span data-stu-id="485b9-104">Ordinarily you connect to the data source through an existing connection manager.</span></span>

 <span data-ttu-id="485b9-105">Per una panoramica del componente script, vedere [estensione del flusso di dati con il componente script] (.. /extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="485b9-105">For an overview of the Script component, see [Extending the Data Flow with the Script Component](../extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span></span>

 <span data-ttu-id="485b9-106">Il componente script e il codice dell'infrastruttura che genera semplificano in modo significativo il processo di sviluppo di un componente del flusso di dati personalizzato.</span><span class="sxs-lookup"><span data-stu-id="485b9-106">The Script component and the infrastructure code that it generates for you simplify significantly the process of developing a custom data flow component.</span></span> <span data-ttu-id="485b9-107">Tuttavia, per comprendere il funzionamento del componente script, può risultare utile leggere informazioni sui passaggi necessari per lo sviluppo di un componente del flusso di dati personalizzato.</span><span class="sxs-lookup"><span data-stu-id="485b9-107">However, to understand how the Script component works, you may find it useful to read through the steps that are involved in developing a custom data flow component.</span></span> <span data-ttu-id="485b9-108">Vedere la sezione [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) (Sviluppo di un componente del flusso di dati personalizzato) e in particolare l'argomento [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) (Sviluppo di un componente di origine personalizzato).</span><span class="sxs-lookup"><span data-stu-id="485b9-108">See the section [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md), especially the topic [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span></span>

## <a name="getting-started-with-a-source-component"></a><span data-ttu-id="485b9-109">Introduzione ai componenti di origine</span><span class="sxs-lookup"><span data-stu-id="485b9-109">Getting Started with a Source Component</span></span>
 <span data-ttu-id="485b9-110">Quando si aggiunge un componente script nel riquadro Flusso di dati di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] viene visualizzata la finestra di dialogo **Seleziona tipo componente script** in cui si richiede di selezionare uno script Origine, Destinazione o Trasformazione.</span><span class="sxs-lookup"><span data-stu-id="485b9-110">When you add a Script component to the Data Flow pane of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the **Select Script Component Type** dialog box opens and prompts you to select a Source, Destination, or Transformation script.</span></span> <span data-ttu-id="485b9-111">In questa finestra di dialogo selezionare **Origine**.</span><span class="sxs-lookup"><span data-stu-id="485b9-111">In this dialog box, select **Source**.</span></span>

## <a name="configuring-a-source-component-in-metadata-design-mode"></a><span data-ttu-id="485b9-112">Configurazione di un componente di origine in modalità di progettazione metadati</span><span class="sxs-lookup"><span data-stu-id="485b9-112">Configuring a Source Component in Metadata-Design Mode</span></span>
 <span data-ttu-id="485b9-113">Dopo aver selezionato la creazione di un componente di origine, configurare il componente tramite **Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="485b9-113">After selecting to create a source component, you configure the component by using the **Script Transformation Editor**.</span></span> <span data-ttu-id="485b9-114">Per altre informazioni, vedere [Configurazione del componente script nell'editor corrispondente](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="485b9-114">For more information, see [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span>

 <span data-ttu-id="485b9-115">Un componente di origine del flusso di dati non include input e supporta uno o più output.</span><span class="sxs-lookup"><span data-stu-id="485b9-115">A data flow source component has no inputs and supports one or more outputs.</span></span> <span data-ttu-id="485b9-116">La configurazione degli output per il componente è uno dei passaggi che vanno completati in modalità di progettazione metadati tramite **Editor trasformazione Script** prima di creare lo script personalizzato.</span><span class="sxs-lookup"><span data-stu-id="485b9-116">Configuring the outputs for the component is one of the steps that you must complete in metadata design mode, by using the **Script Transformation Editor**, before you write your custom script.</span></span>

 <span data-ttu-id="485b9-117">È anche possibile specificare il linguaggio di scripting mediante l'impostazione della proprietà **ScriptLanguage** nella pagina **Script** di **Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="485b9-117">You can also specify the script language by setting the **ScriptLanguage** property on the **Script** page of the **Script Transformation Editor**.</span></span>

> [!NOTE]
>  <span data-ttu-id="485b9-118">Per impostare il linguaggio di scripting predefinito per componenti Script e attività Script, usare l'opzione **Linguaggio di scripting** nella pagina **Generale** della finestra di dialogo **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="485b9-118">To set the default script language for Script components and Script Tasks, use the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="485b9-119">Per ulteriori informazioni, vedere [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="485b9-119">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>

### <a name="adding-connection-managers"></a><span data-ttu-id="485b9-120">Aggiunta di gestioni connessioni</span><span class="sxs-lookup"><span data-stu-id="485b9-120">Adding Connection Managers</span></span>
 <span data-ttu-id="485b9-121">Normalmente, un componente di origine utilizza una gestione connessione esistente per connettersi all'origine dati da cui carica dati nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="485b9-121">Ordinarily a source component uses an existing connection manager to connect to the data source from which it loads data into the data flow.</span></span> <span data-ttu-id="485b9-122">Nella pagina **Gestioni connessioni** di **Editor trasformazione Script** fare clic su **Aggiungi** per aggiungere la gestione connessione appropriata.</span><span class="sxs-lookup"><span data-stu-id="485b9-122">On the **Connection Managers** page of the **Script Transformation Editor**, click **Add** to add the appropriate connection manager.</span></span>

 <span data-ttu-id="485b9-123">Tuttavia, una gestione connessione è solo un'unità pratica che incapsula e archivia le informazioni necessarie per la connessione a un'origine dati di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="485b9-123">However, a connection manager is only a convenient unit that encapsulates and stores the information that it must have to connect to a data source of a particular type.</span></span> <span data-ttu-id="485b9-124">È necessario scrivere codice personalizzato per caricare o salvare i dati e possibilmente anche per aprire e chiudere la connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="485b9-124">You must write your own custom code to load or save your data, and possibly to open and close the connection to the data source also.</span></span>

 <span data-ttu-id="485b9-125">Per informazioni generali sull'uso delle gestioni connessioni con il componente Script, vedere [Connessione a origini dati nel componente Script](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="485b9-125">For general information about how to use connection managers with the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span></span>

 <span data-ttu-id="485b9-126">Per altre informazioni sulla pagina **Gestioni connessioni** di **Editor trasformazione Script**, vedere [Editor trasformazione Script &#40;pagina Gestioni connessioni&#41;](../script-transformation-editor-connection-managers-page.md).</span><span class="sxs-lookup"><span data-stu-id="485b9-126">For more information about the **Connection Managers** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md).</span></span>

### <a name="configuring-outputs-and-output-columns"></a><span data-ttu-id="485b9-127">Configurazione di output e colonne di output</span><span class="sxs-lookup"><span data-stu-id="485b9-127">Configuring Outputs and Output Columns</span></span>
 <span data-ttu-id="485b9-128">Un componente di origine non include input e supporta uno o più output.</span><span class="sxs-lookup"><span data-stu-id="485b9-128">A source component has no inputs and supports one or more outputs.</span></span> <span data-ttu-id="485b9-129">Nella pagina **Input e output** di **Editor trasformazione Script** è stato creato un singolo output per impostazione predefinita, ma non sono state create colonne di output.</span><span class="sxs-lookup"><span data-stu-id="485b9-129">On the **Inputs and Outputs** page of the **Script Transformation Editor**, a single output has been created by default, but no output columns have been created.</span></span> <span data-ttu-id="485b9-130">In questa pagina dell'editor può essere necessario o consigliabile configurare gli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="485b9-130">On this page of the editor, you may need or want to configure the following items.</span></span>

-   <span data-ttu-id="485b9-131">È necessario aggiungere e configurare manualmente le colonne di output per ogni output.</span><span class="sxs-lookup"><span data-stu-id="485b9-131">You must add and configure output columns manually for each output.</span></span> <span data-ttu-id="485b9-132">Selezionare la cartella Colonne di output per ogni output, quindi usare i pulsanti **Aggiungi colonna** e **Rimuovi colonna** per gestire le colonne di output per ogni output del componente di origine.</span><span class="sxs-lookup"><span data-stu-id="485b9-132">Select the Output Columns folder for each output, and then use the **Add Column** and **Remove Column** buttons to manage the output columns for each output of the source component.</span></span> <span data-ttu-id="485b9-133">In seguito, si farà riferimento alle colonne di output nello script in base ai nomi assegnati in questo passaggio, utilizzando le proprietà delle funzioni di accesso tipizzate create nel codice generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="485b9-133">Later, you will refer to the output columns in your script by the names that you assign here, by using the typed accessor properties created for you in the auto-generated code.</span></span>

-   <span data-ttu-id="485b9-134">È possibile creare uno o più output aggiuntivi, ad esempio un output degli errori simulati per le righe che contengono valori imprevisti.</span><span class="sxs-lookup"><span data-stu-id="485b9-134">You may want to create one or more additional outputs, such as a simulated error output for rows that contain unexpected values.</span></span> <span data-ttu-id="485b9-135">Usare i pulsanti **Aggiungi output** e **Rimuovi output** per gestire gli output del componente di origine.</span><span class="sxs-lookup"><span data-stu-id="485b9-135">Use the **Add Output** and **Remove Output** buttons to manage the outputs of the source component.</span></span> <span data-ttu-id="485b9-136">Tutte le righe di input vengono indirizzate a tutti gli output disponibili, a meno che non venga anche specificato un valore identico diverso da zero per la proprietà `ExclusionGroup` di tali output nei casi in cui si intenda indirizzare ogni riga a uno solo degli output che condividono lo stesso valore di `ExclusionGroup`.</span><span class="sxs-lookup"><span data-stu-id="485b9-136">All input rows are directed to all available outputs unless you also specify an identical non-zero value for the `ExclusionGroup` property of those outputs where you intend to direct each row to only one of the outputs that share the same `ExclusionGroup` value.</span></span> <span data-ttu-id="485b9-137">Il valore intero specifico selezionato per identificare `ExclusionGroup` non è significativo.</span><span class="sxs-lookup"><span data-stu-id="485b9-137">The particular integer value selected to identify the `ExclusionGroup` is not significant.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="485b9-138">È anche possibile utilizzare un valore diverso da zero per la proprietà `ExclusionGroup` con un singolo output quando non si desidera restituire tutte le righe come output.</span><span class="sxs-lookup"><span data-stu-id="485b9-138">You can also use a non-zero `ExclusionGroup` property value with a single output when you do not want to output all rows.</span></span> <span data-ttu-id="485b9-139">In questo caso, tuttavia, è necessario chiamare in modo esplicito il metodo **DirectRowTo\<outputbuffer>** per ogni riga che si vuole inviare all'output.</span><span class="sxs-lookup"><span data-stu-id="485b9-139">In this case, however, you must explicitly call the **DirectRowTo\<outputbuffer>** method for each row that you want to send to the output.</span></span>

-   <span data-ttu-id="485b9-140">È necessario assegnare un nome descrittivo agli output.</span><span class="sxs-lookup"><span data-stu-id="485b9-140">You may want to assign a friendly name to the outputs.</span></span> <span data-ttu-id="485b9-141">In seguito, si farà riferimento agli output in base ai nomi presenti nello script, utilizzando le proprietà delle funzioni di accesso tipizzate create nel codice generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="485b9-141">Later, you will refer to the outputs by their names in your script, by using the typed accessor properties created for you in the auto-generated code.</span></span>

-   <span data-ttu-id="485b9-142">Normalmente, più output nello stesso oggetto `ExclusionGroup` dispongono delle stesse colonne di output.</span><span class="sxs-lookup"><span data-stu-id="485b9-142">Ordinarily multiple outputs in the same `ExclusionGroup` have the same output columns.</span></span> <span data-ttu-id="485b9-143">Tuttavia, se si crea un output degli errori simulati, è possibile aggiungere più colonne per archiviare le informazioni sugli errori.</span><span class="sxs-lookup"><span data-stu-id="485b9-143">However, if you are creating a simulated error output, you may want to add more columns to store error information.</span></span> <span data-ttu-id="485b9-144">Per informazioni su come il motore flusso di dati elabora le righe di errore, vedere [Uso degli output degli errori in un componente del flusso di dati](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="485b9-144">For information about how the data flow engine processes error rows, see [Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md).</span></span> <span data-ttu-id="485b9-145">Nel componente script, tuttavia, è necessario scrivere codice personalizzato per inserire le informazioni appropriate sugli errori nelle colonne aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="485b9-145">In the Script component, however, you must write your own code to fill the additional columns with appropriate error information.</span></span> <span data-ttu-id="485b9-146">Per altre informazioni, vedere [Simulazione di un output degli errori per il componente script](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="485b9-146">For more information, see [Simulating an Error Output for the Script Component](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md).</span></span>

 <span data-ttu-id="485b9-147">Per altre informazioni sulla pagina **Input e output** di **Editor trasformazione Script**, vedere [Editor trasformazione Script &#40;pagina Input e output&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span><span class="sxs-lookup"><span data-stu-id="485b9-147">For more information about the **Inputs and Outputs** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span></span>

### <a name="adding-variables"></a><span data-ttu-id="485b9-148">Aggiunta di variabili</span><span class="sxs-lookup"><span data-stu-id="485b9-148">Adding Variables</span></span>
 <span data-ttu-id="485b9-149">Se sono presenti variabili esistenti i cui valori si desidera usare nello script, è possibile aggiungerli nei `ReadOnlyVariables` campi delle proprietà e nella `ReadWriteVariables` pagina **script** di **Editor trasformazione script**.</span><span class="sxs-lookup"><span data-stu-id="485b9-149">If there are any existing variables whose values you want to use in your script, you can add them in the `ReadOnlyVariables` and `ReadWriteVariables` property fields on the **Script** page of the **Script Transformation Editor**.</span></span>

 <span data-ttu-id="485b9-150">Quando si immettono più variabili nei campi delle proprietà, separare i relativi nomi con virgole.</span><span class="sxs-lookup"><span data-stu-id="485b9-150">When you enter multiple variables in the property fields, separate the variable names by commas.</span></span> <span data-ttu-id="485b9-151">È anche possibile immettere più variabili facendo clic sul pulsante con i puntini di sospensione (**...**) accanto ai `ReadOnlyVariables` campi delle `ReadWriteVariables` proprietà e e selezionando variabili nella finestra di dialogo **Seleziona variabili** .</span><span class="sxs-lookup"><span data-stu-id="485b9-151">You can also enter multiple variables by clicking the ellipsis (**...**) button next to the `ReadOnlyVariables` and `ReadWriteVariables` property fields and selecting variables in the **Select variables** dialog box.</span></span>

 <span data-ttu-id="485b9-152">Per informazioni generali sull'uso delle variabili con il componente script, vedere [Uso di variabili nel componente script](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="485b9-152">For general information about how to use variables with the Script component, see [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span></span>

 <span data-ttu-id="485b9-153">Per altre informazioni sulla pagina **Script** di **Editor trasformazione Script**, vedere [Editor trasformazione Script &#40;pagina Script&#41;](../script-transformation-editor-script-page.md).</span><span class="sxs-lookup"><span data-stu-id="485b9-153">For more information about the **Script** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md).</span></span>

## <a name="scripting-a-source-component-in-code-design-mode"></a><span data-ttu-id="485b9-154">Generazione di script per un componente di origine in modalità di progettazione codice</span><span class="sxs-lookup"><span data-stu-id="485b9-154">Scripting a Source Component in Code-Design Mode</span></span>
 <span data-ttu-id="485b9-155">Dopo aver configurato i metadati per il componente, aprire l'IDE di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) per scrivere il codice dello script personalizzato.</span><span class="sxs-lookup"><span data-stu-id="485b9-155">After you have configured the metadata for your component, open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE to code your custom script.</span></span> <span data-ttu-id="485b9-156">Per aprire VSTA fare clic su **Modifica script** nella pagina **Script** di **Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="485b9-156">To open VSTA, click **Edit Script** on the **Script** page of the **Script Transformation Editor**.</span></span> <span data-ttu-id="485b9-157">È possibile creare lo script usando [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#, a seconda del linguaggio di scripting selezionato per la proprietà **ScriptLanguage**.</span><span class="sxs-lookup"><span data-stu-id="485b9-157">You can write your script by using either [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#, depending on the script language selected for the **ScriptLanguage** property.</span></span>

 <span data-ttu-id="485b9-158">Per importanti informazioni applicabili a tutti i tipi di componenti creati tramite il componente script, vedere [Codifica e debug del componente script](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="485b9-158">For important information that applies to all kinds of components created by using the Script component, see [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>

### <a name="understanding-the-auto-generated-code"></a><span data-ttu-id="485b9-159">Informazioni sul codice generato automaticamente</span><span class="sxs-lookup"><span data-stu-id="485b9-159">Understanding the Auto-generated Code</span></span>
 <span data-ttu-id="485b9-160">Quando si apre l'IDE di VSTA dopo la creazione e la configurazione di un componente di origine, la classe `ScriptMain` modificabile viene visualizzata nell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="485b9-160">When you open the VSTA IDE after creating and configuring a source component, the editable `ScriptMain` class appears in the code editor.</span></span> <span data-ttu-id="485b9-161">Scrivere il codice personalizzato nella classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="485b9-161">You write your custom code in the `ScriptMain` class.</span></span>

 <span data-ttu-id="485b9-162">La classe `ScriptMain` include uno stub per il metodo `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="485b9-162">The `ScriptMain` class includes a stub for the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="485b9-163">`CreateNewOutputRows` è il metodo più importante di un componente di origine.</span><span class="sxs-lookup"><span data-stu-id="485b9-163">The `CreateNewOutputRows` is the most important method in a source component.</span></span>

 <span data-ttu-id="485b9-164">Se si apre la finestra **Esplora progetti** in VSTA, è possibile osservare che il componente script ha generato anche gli elementi di `BufferWrapper` progetto e di sola lettura `ComponentWrapper` .</span><span class="sxs-lookup"><span data-stu-id="485b9-164">If you open the **Project Explorer** window in VSTA, you can see that the Script component has also generated read-only `BufferWrapper` and `ComponentWrapper` project items.</span></span> <span data-ttu-id="485b9-165">La classe `ScriptMain` eredita dalla classe `UserComponent` nell'elemento di progetto `ComponentWrapper`.</span><span class="sxs-lookup"><span data-stu-id="485b9-165">The `ScriptMain` class inherits from `UserComponent` class in the `ComponentWrapper` project item.</span></span>

 <span data-ttu-id="485b9-166">In fase di esecuzione il motore flusso di dati richiama il metodo `PrimeOutput` nella classe `UserComponent`, che esegue l'override del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponentHost.PrimeOutput%2A> della classe padre <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="485b9-166">At run time, the data flow engine invokes the `PrimeOutput` method in the `UserComponent` class, which overrides the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponentHost.PrimeOutput%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> parent class.</span></span> <span data-ttu-id="485b9-167">Il metodo `PrimeOutput` chiama a sua volta i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="485b9-167">The `PrimeOutput` method in turn calls the following methods:</span></span>

1.  <span data-ttu-id="485b9-168">Metodo `CreateNewOutputRows`, di cui si esegue l'override in `ScriptMain` per aggiungere righe dall'origine dati ai buffer di output, che sono inizialmente vuoti.</span><span class="sxs-lookup"><span data-stu-id="485b9-168">The `CreateNewOutputRows` method, which you override in `ScriptMain` to add rows from the data source to the output buffers, which are empty at first.</span></span>

2.  <span data-ttu-id="485b9-169">Metodo `FinishOutputs`, che per impostazione predefinita è vuoto.</span><span class="sxs-lookup"><span data-stu-id="485b9-169">The `FinishOutputs` method, which is empty by default.</span></span> <span data-ttu-id="485b9-170">Eseguire l'override di questo metodo in `ScriptMain` per eseguire l'elaborazione richiesta per completare l'output.</span><span class="sxs-lookup"><span data-stu-id="485b9-170">Override this method in `ScriptMain` to perform any processing that is required to complete the output.</span></span>

3.  <span data-ttu-id="485b9-171">Metodo privato `MarkOutputsAsFinished`, che chiama il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer.SetEndOfRowset%2A> della classe padre <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> per indicare al motore flusso di dati che l'output è completo.</span><span class="sxs-lookup"><span data-stu-id="485b9-171">The private `MarkOutputsAsFinished` method, which calls the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer.SetEndOfRowset%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> parent class to indicate to the data flow engine that the output is finished.</span></span> <span data-ttu-id="485b9-172">Non è necessario chiamare in modo esplicito `SetEndOfRowset` nel codice.</span><span class="sxs-lookup"><span data-stu-id="485b9-172">You do not have to call `SetEndOfRowset` explicitly in your own code.</span></span>

### <a name="writing-your-custom-code"></a><span data-ttu-id="485b9-173">Scrittura di codice personalizzato</span><span class="sxs-lookup"><span data-stu-id="485b9-173">Writing Your Custom Code</span></span>
 <span data-ttu-id="485b9-174">Per completare la creazione di un componente di origine personalizzato, è possibile scrivere script nei metodi seguenti disponibili nella classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="485b9-174">To finish creating a custom source component, you may want to write script in the following methods available in the `ScriptMain` class.</span></span>

1.  <span data-ttu-id="485b9-175">Eseguire l'override del metodo `AcquireConnections` per connettersi all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="485b9-175">Override the `AcquireConnections` method to connect to the external data source.</span></span> <span data-ttu-id="485b9-176">Estrarre l'oggetto connessione o le informazioni di connessione necessarie dalla gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="485b9-176">Extract the connection object, or the required connection information, from the connection manager.</span></span>

2.  <span data-ttu-id="485b9-177">Eseguire l'override del metodo `PreExecute` per caricare dati, se è possibile caricare contemporaneamente tutti i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="485b9-177">Override the `PreExecute` method to load data, if you can load all the source data at the same time.</span></span> <span data-ttu-id="485b9-178">Ad esempio, è possibile eseguire `SqlCommand` su una connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] a un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e caricare contemporaneamente tutti i dati di origine in un oggetto `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="485b9-178">For example, you can execute a `SqlCommand` against an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and load all the source data at the same time into a `SqlDataReader`.</span></span> <span data-ttu-id="485b9-179">Se è necessario caricare i dati di origine una riga alla volta (ad esempio quando si legge un file di testo), è possibile caricare i dati mentre si esegue il ciclo delle righe in `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="485b9-179">If you must load the source data one row at a time (for example, when reading a text file), you can load the data as you loop through rows in `CreateNewOutputRows`.</span></span>

3.  <span data-ttu-id="485b9-180">Utilizzare il metodo `CreateNewOutputRows` sottoposto a override per aggiungere nuove righe ai buffer di output vuoti e per inserire i valori di ogni colonna nelle nuove righe di output.</span><span class="sxs-lookup"><span data-stu-id="485b9-180">Use the overridden `CreateNewOutputRows` method to add new rows to the empty output buffers and to fill in the values of each column in the new output rows.</span></span> <span data-ttu-id="485b9-181">Utilizzare il metodo `AddRow` di ogni buffer di output per aggiungere una nuova riga vuota, quindi impostare i valori di ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="485b9-181">Use the `AddRow` method of each output buffer to add an empty new row, and then set the values of each column.</span></span> <span data-ttu-id="485b9-182">In genere si copiano i valori dalle colonne caricate dall'origine esterna.</span><span class="sxs-lookup"><span data-stu-id="485b9-182">Typically you copy values from the columns loaded from the external source.</span></span>

4.  <span data-ttu-id="485b9-183">Eseguire l'override del metodo `PostExecute` per completare l'elaborazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="485b9-183">Override the `PostExecute` method to finish processing the data.</span></span> <span data-ttu-id="485b9-184">Ad esempio, è possibile chiudere l'oggetto `SqlDataReader` utilizzato per il caricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="485b9-184">For example, you can close the `SqlDataReader` that you used to load data.</span></span>

5.  <span data-ttu-id="485b9-185">Eseguire l'override del metodo `ReleaseConnections` per disconnettersi dall'origine dati esterna, se necessario.</span><span class="sxs-lookup"><span data-stu-id="485b9-185">Override the `ReleaseConnections` method to disconnect from the external data source, if required.</span></span>

## <a name="examples"></a><span data-ttu-id="485b9-186">Esempi</span><span class="sxs-lookup"><span data-stu-id="485b9-186">Examples</span></span>
 <span data-ttu-id="485b9-187">Negli esempi seguenti è illustrato il codice personalizzato necessario nella classe `ScriptMain` per creare un componente di origine.</span><span class="sxs-lookup"><span data-stu-id="485b9-187">The following examples demonstrate the custom code that is required in the `ScriptMain` class to create a source component.</span></span>

> [!NOTE]
>  <span data-ttu-id="485b9-188">In questi esempi viene utilizzata la tabella **Person. Address** nel `AdventureWorks` database di esempio e vengono passate la prima e la quarta colonna, ovvero le colonne **intAddressID** e **nvarchar (30) City** , attraverso il flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="485b9-188">These examples use the **Person.Address** table in the `AdventureWorks` sample database and pass its first and fourth columns, the **intAddressID** and **nvarchar(30)City** columns, through the data flow.</span></span> <span data-ttu-id="485b9-189">Gli stessi dati vengono utilizzati negli esempi relativi a origine, trasformazione e destinazione in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="485b9-189">The same data is used in the source, transformation, and destination samples in this section.</span></span> <span data-ttu-id="485b9-190">Per ogni esempio, sono documentati ulteriori prerequisiti e presupposti.</span><span class="sxs-lookup"><span data-stu-id="485b9-190">Additional prerequisites and assumptions are documented for each example.</span></span>

### <a name="adonet-source-example"></a><span data-ttu-id="485b9-191">Esempio di origine ADO.NET</span><span class="sxs-lookup"><span data-stu-id="485b9-191">ADO.NET Source Example</span></span>
 <span data-ttu-id="485b9-192">In questo esempio è illustrato un componente di origine che usa una gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] esistente per caricare dati da una tabella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="485b9-192">This example demonstrates a source component that uses an existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to load data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into the data flow.</span></span>

 <span data-ttu-id="485b9-193">Se si desidera eseguire questo codice di esempio, è necessario configurare il pacchetto e il componente come segue:</span><span class="sxs-lookup"><span data-stu-id="485b9-193">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="485b9-194">Creare una gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] che utilizza il provider `SqlClient` per connettersi al database `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="485b9-194">Create an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the `SqlClient` provider to connect to the `AdventureWorks` database.</span></span>

2.  <span data-ttu-id="485b9-195">Aggiungere un nuovo componente script all'area di progettazione del flusso di dati e configurarlo come origine.</span><span class="sxs-lookup"><span data-stu-id="485b9-195">Add a new Script component to the Data Flow designer surface and configure it as a source.</span></span>

3.  <span data-ttu-id="485b9-196">Aprire l'**Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="485b9-196">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="485b9-197">Nella pagina **Input e output** rinominare l'output predefinito con un nome più descrittivo, ad esempio **MyAddressOutput**, quindi aggiungere e configurare le due colonne di output, **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="485b9-197">On the **Inputs and Outputs** page, rename the default output with a more descriptive name such as **MyAddressOutput**, and add and configure the two output columns, **AddressID** and **City**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="485b9-198">Assicurarsi di modificare il tipo di dati della colonna di output **City** in DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="485b9-198">Be sure to change the data type of the **City** output column to DT_WSTR.</span></span>

4.  <span data-ttu-id="485b9-199">Nella pagina **Gestioni connessioni** aggiungere o creare la gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] e specificare un nome, ad esempio **MyADONETConnection**.</span><span class="sxs-lookup"><span data-stu-id="485b9-199">On the **Connection Managers** page, add or create the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager and give it a name such as **MyADONETConnection**.</span></span>

5.  <span data-ttu-id="485b9-200">Nella pagina **Script** fare clic su **Modifica script** e immettere lo script seguente.</span><span class="sxs-lookup"><span data-stu-id="485b9-200">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="485b9-201">Chiudere quindi l'ambiente di sviluppo dello script e **Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="485b9-201">Then close the script development environment and the **Script Transformation Editor**.</span></span>

6.  <span data-ttu-id="485b9-202">Creare e configurare un componente di destinazione, ad esempio una destinazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o il componente di destinazione di esempio illustrato in [Creazione di una destinazione con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md), in cui sono previste le colonne **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="485b9-202">Create and configure a destination component, such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, or the sample destination component demonstrated in [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md), that expects the **AddressID** and **City** columns.</span></span> <span data-ttu-id="485b9-203">Quindi, connettere il componente di origine alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="485b9-203">Then connect the source component to the destination.</span></span> <span data-ttu-id="485b9-204">È possibile connettere un'origine direttamente a una destinazione senza alcuna trasformazione. È possibile creare una tabella di destinazione eseguendo il [!INCLUDE[tsql](../../includes/tsql-md.md)] comando seguente nel `AdventureWorks` database:</span><span class="sxs-lookup"><span data-stu-id="485b9-204">(You can connect a source directly to a destination without any transformations.) You can create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

7.  <span data-ttu-id="485b9-205">Eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="485b9-205">Run the sample.</span></span>

    ```vb
    Imports System.Data.SqlClient
    ...
    Public Class ScriptMain
        Inherits UserComponent

        Dim connMgr As IDTSConnectionManager100
        Dim sqlConn As SqlConnection
        Dim sqlReader As SqlDataReader

        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

            connMgr = Me.Connections.MyADONETConnection
            sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

        End Sub

        Public Overrides Sub PreExecute()

            Dim cmd As New SqlCommand("SELECT AddressID, City, StateProvinceID FROM Person.Address", sqlConn)
            sqlReader = cmd.ExecuteReader

        End Sub

        Public Overrides Sub CreateNewOutputRows()

            Do While sqlReader.Read
                With MyAddressOutputBuffer
                    .AddRow()
                    .AddressID = sqlReader.GetInt32(0)
                    .City = sqlReader.GetString(1)
                End With
            Loop

        End Sub

        Public Overrides Sub PostExecute()

            sqlReader.Close()

        End Sub

        Public Overrides Sub ReleaseConnections()

            connMgr.ReleaseConnection(sqlConn)

        End Sub

    End Class
    ```

    ```csharp
    using System.Data.SqlClient;
    public class ScriptMain:
        UserComponent

    {
        IDTSConnectionManager100 connMgr;
        SqlConnection sqlConn;
        SqlDataReader sqlReader;

        public override void AcquireConnections(object Transaction)
        {
            connMgr = this.Connections.MyADONETConnection;
            sqlConn = (SqlConnection)connMgr.AcquireConnection(null);

        }

        public override void PreExecute()
        {

            SqlCommand cmd = new SqlCommand("SELECT AddressID, City, StateProvinceID FROM Person.Address", sqlConn);
            sqlReader = cmd.ExecuteReader();

        }

        public override void CreateNewOutputRows()
        {

            while (sqlReader.Read())
            {
                {
                    MyAddressOutputBuffer.AddRow();
                    MyAddressOutputBuffer.AddressID = sqlReader.GetInt32(0);
                    MyAddressOutputBuffer.City = sqlReader.GetString(1);
                }
            }

        }

        public override void PostExecute()
        {

            sqlReader.Close();

        }

        public override void ReleaseConnections()
        {

            connMgr.ReleaseConnection(sqlConn);

        }

    }
    ```

### <a name="flat-file-source-example"></a><span data-ttu-id="485b9-206">Esempio di origine file flat</span><span class="sxs-lookup"><span data-stu-id="485b9-206">Flat File Source Example</span></span>
 <span data-ttu-id="485b9-207">In questo esempio è illustrato un componente di origine che utilizza una gestione connessione file flat esistente per caricare dati da un file flat nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="485b9-207">This example demonstrates a source component that uses an existing Flat File connection manager to load data from a flat file into the data flow.</span></span> <span data-ttu-id="485b9-208">I dati di origine del file flat vengono creati esportandoli da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="485b9-208">The flat file source data is created by exporting it from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>

 <span data-ttu-id="485b9-209">Se si desidera eseguire questo codice di esempio, è necessario configurare il pacchetto e il componente come segue:</span><span class="sxs-lookup"><span data-stu-id="485b9-209">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="485b9-210">Utilizzare l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] importazione/esportazione guidata per esportare la tabella **Person. Address** dal `AdventureWorks` database di esempio in un file flat delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="485b9-210">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard to export the **Person.Address** table from the `AdventureWorks` sample database to a comma-delimited flat file.</span></span> <span data-ttu-id="485b9-211">In questo esempio viene utilizzato il nome file ExportedAddresses.txt.</span><span class="sxs-lookup"><span data-stu-id="485b9-211">This sample uses the file name ExportedAddresses.txt.</span></span>

2.  <span data-ttu-id="485b9-212">Creare una gestione connessione file flat che si connette al file di dati esportato.</span><span class="sxs-lookup"><span data-stu-id="485b9-212">Create a Flat File connection manager that connects to the exported data file.</span></span>

3.  <span data-ttu-id="485b9-213">Aggiungere un nuovo componente script all'area di progettazione del flusso di dati e configurarlo come origine.</span><span class="sxs-lookup"><span data-stu-id="485b9-213">Add a new Script component to the Data Flow designer surface and configure it as a source.</span></span>

4.  <span data-ttu-id="485b9-214">Aprire l'**Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="485b9-214">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="485b9-215">Nella pagina **Input e output** rinominare l'output predefinito con un nome più descrittivo, ad esempio **MyAddressOutput**.</span><span class="sxs-lookup"><span data-stu-id="485b9-215">On the **Inputs and Outputs** page, rename the default output with a more descriptive name such as **MyAddressOutput**.</span></span> <span data-ttu-id="485b9-216">Aggiungere e configurare le due colonne di output, **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="485b9-216">Add and configure the two output columns, **AddressID** and **City**.</span></span>

5.  <span data-ttu-id="485b9-217">Nella pagina **Gestioni connessioni** aggiungere o creare la gestione connessione file flat usando un nome descrittivo, ad esempio **MyFlatFileSrcConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="485b9-217">On the **Connection Managers** page, add or create the Flat File connection manager, using a descriptive name such as **MyFlatFileSrcConnectionManager**.</span></span>

6.  <span data-ttu-id="485b9-218">Nella pagina **Script** fare clic su **Modifica script** e immettere lo script seguente.</span><span class="sxs-lookup"><span data-stu-id="485b9-218">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="485b9-219">Chiudere quindi l'ambiente di sviluppo dello script e **Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="485b9-219">Then close the script development environment and the **Script Transformation Editor**.</span></span>

7.  <span data-ttu-id="485b9-220">Creare e configurare un componente di destinazione, ad esempio una destinazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o il componente di destinazione di esempio illustrato in [Creazione di una destinazione con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="485b9-220">Create and configure a destination component, such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, or the sample destination component demonstrated in [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span></span> <span data-ttu-id="485b9-221">Quindi, connettere il componente di origine alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="485b9-221">Then connect the source component to the destination.</span></span> <span data-ttu-id="485b9-222">È possibile connettere un'origine direttamente a una destinazione senza alcuna trasformazione. È possibile creare una tabella di destinazione eseguendo il [!INCLUDE[tsql](../../includes/tsql-md.md)] comando seguente nel `AdventureWorks` database:</span><span class="sxs-lookup"><span data-stu-id="485b9-222">(You can connect a source directly to a destination without any transformations.) You can create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

8.  <span data-ttu-id="485b9-223">Eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="485b9-223">Run the sample.</span></span>

    ```vb
    Imports System.IO
    ...
    Public Class ScriptMain
        Inherits UserComponent

        Private textReader As StreamReader
        Private exportedAddressFile As String

        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

            Dim connMgr As IDTSConnectionManager100 = _
                Me.Connections.MyFlatFileSrcConnectionManager
            exportedAddressFile = _
                CType(connMgr.AcquireConnection(Nothing), String)

        End Sub

        Public Overrides Sub PreExecute()
            MyBase.PreExecute()
            textReader = New StreamReader(exportedAddressFile)
        End Sub

        Public Overrides Sub CreateNewOutputRows()

            Dim nextLine As String
            Dim columns As String()

            Dim delimiters As Char()
            delimiters = ",".ToCharArray

            nextLine = textReader.ReadLine
            Do While nextLine IsNot Nothing
                columns = nextLine.Split(delimiters)
                With MyAddressOutputBuffer
                    .AddRow()
                    .AddressID = columns(0)
                    .City = columns(3)
                End With
                nextLine = textReader.ReadLine
            Loop

        End Sub

        Public Overrides Sub PostExecute()
            MyBase.PostExecute()
            textReader.Close()

        End Sub

    End Class
    ```

    ```csharp
    using System.IO;
    public class ScriptMain:
        UserComponent

    {
        private StreamReader textReader;
        private string exportedAddressFile;

        public override void AcquireConnections(object Transaction)
        {

            IDTSConnectionManager100 connMgr = this.Connections.MyFlatFileSrcConnectionManager;
            exportedAddressFile = (string)connMgr.AcquireConnection(null);

        }

        public override void PreExecute()
        {
            base.PreExecute();
            textReader = new StreamReader(exportedAddressFile);
        }

        public override void CreateNewOutputRows()
        {

            string nextLine;
            string[] columns;

            char[] delimiters;
            delimiters = ",".ToCharArray();

            nextLine = textReader.ReadLine();
            while (nextLine != null)
            {
                columns = nextLine.Split(delimiters);
                {
                    MyAddressOutputBuffer.AddRow();
                    MyAddressOutputBuffer.AddressID = columns[0];
                    MyAddressOutputBuffer.City = columns[3];
                }
                nextLine = textReader.ReadLine();
            }

        }

        public override void PostExecute()
        {

            base.PostExecute();
            textReader.Close();

        }

    }
    ```

<span data-ttu-id="485b9-224">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="485b9-224">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="485b9-225">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="485b9-225">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="485b9-226">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="485b9-226">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="485b9-227">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="485b9-227">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="485b9-228">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="485b9-228">See Also</span></span>
 <span data-ttu-id="485b9-229">[Creazione di una destinazione con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) [sviluppo di un componente di origine personalizzato](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)</span><span class="sxs-lookup"><span data-stu-id="485b9-229">[Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)</span></span>


