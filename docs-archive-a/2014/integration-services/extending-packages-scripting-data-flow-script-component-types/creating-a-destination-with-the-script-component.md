---
title: Creazione di una destinazione con il componente script | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], destination components
- destinations [Integration Services], components
- input columns [Integration Services]
ms.assetid: 214e22e8-7e7d-4876-b690-c138e5721b81
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1245dde111b24d1c37e2c5550d236c97126ee725
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635169"
---
# <a name="creating-a-destination-with-the-script-component"></a><span data-ttu-id="e46a6-102">Creazione di una destinazione con il componente script</span><span class="sxs-lookup"><span data-stu-id="e46a6-102">Creating a Destination with the Script Component</span></span>
  <span data-ttu-id="e46a6-103">Utilizzare un componente di destinazione nel flusso di dati di un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per salvare in un'origine dati i dati ricevuti dalle origini e dalle trasformazioni upstream.</span><span class="sxs-lookup"><span data-stu-id="e46a6-103">You use a destination component in the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package to save data received from upstream sources and transformations to a data source.</span></span> <span data-ttu-id="e46a6-104">Normalmente, il componente di destinazione si connette all'origine dati tramite una gestione connessione esistente.</span><span class="sxs-lookup"><span data-stu-id="e46a6-104">Ordinarily the destination component connects to the data source through an existing connection manager.</span></span>

 <span data-ttu-id="e46a6-105">Per una panoramica del componente script, vedere [estensione del flusso di dati con il componente script] (.. /extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="e46a6-105">For an overview of the Script component, see [Extending the Data Flow with the Script Component](../extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span></span>

 <span data-ttu-id="e46a6-106">Il componente script e il codice dell'infrastruttura che genera semplificano in modo significativo il processo di sviluppo di un componente del flusso di dati personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e46a6-106">The Script component and the infrastructure code that it generates for you simplify significantly the process of developing a custom data flow component.</span></span> <span data-ttu-id="e46a6-107">Tuttavia, per comprendere il funzionamento del componente script, può risultare utile leggere informazioni sui passaggi necessari per lo sviluppo di un componente del flusso di dati personalizzato nella sezione [Sviluppo di un componente del flusso di dati personalizzato](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md), in particolare [Sviluppo di un componente di destinazione personalizzato](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md).</span><span class="sxs-lookup"><span data-stu-id="e46a6-107">However, to understand how the Script component works, you may find it useful to read through the steps for developing a custom data flow components in the [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) section, and especially [Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md).</span></span>

## <a name="getting-started-with-a-destination-component"></a><span data-ttu-id="e46a6-108">Introduzione ai componenti di destinazione</span><span class="sxs-lookup"><span data-stu-id="e46a6-108">Getting Started with a Destination Component</span></span>
 <span data-ttu-id="e46a6-109">Quando si aggiunge un componente script nella scheda Flusso di dati di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)], viene visualizzata la finestra di dialogo **Seleziona tipo componente script** in cui si richiede di selezionare uno script **Origine**, **Destinazione** o **Trasformazione**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-109">When you add a Script component to the Data Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the **Select Script Component Type** dialog box opens and prompts you to select a **Source**, **Destination**, or **Transformation** script.</span></span> <span data-ttu-id="e46a6-110">In questa finestra di dialogo selezionare **Destinazione**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-110">In this dialog box, select **Destination**.</span></span>

 <span data-ttu-id="e46a6-111">Connettere quindi l'output di una trasformazione al componente di destinazione in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e46a6-111">Next, connect the output of a transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e46a6-112">A scopo di test, è possibile connettere direttamente un'origine a una destinazione senza alcuna trasformazione.</span><span class="sxs-lookup"><span data-stu-id="e46a6-112">For testing, you can connect a source directly to a destination without any transformations.</span></span>

## <a name="configuring-a-destination-component-in-metadata-design-mode"></a><span data-ttu-id="e46a6-113">Configurazione di un componente di destinazione in modalità di progettazione metadati</span><span class="sxs-lookup"><span data-stu-id="e46a6-113">Configuring a Destination Component in Metadata-Design Mode</span></span>
 <span data-ttu-id="e46a6-114">Dopo aver selezionato l'opzione per creare un componente di destinazione, configurare il componente usando **Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-114">After you select the option to create a destination component, you configure the component by using the **Script Transformation Editor**.</span></span> <span data-ttu-id="e46a6-115">Per altre informazioni, vedere [Configurazione del componente script nell'editor corrispondente](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="e46a6-115">For more information, see [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span>

 <span data-ttu-id="e46a6-116">Per selezionare il linguaggio di scripting che verrà usato dal componente script di destinazione, impostare la proprietà **ScriptLanguage** nella pagina **Script** della finestra di dialogo **Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-116">To select the script language that the Script destination will use, you set the **ScriptLanguage** property on the **Script** page of the **Script Transformation Editor** dialog box.</span></span>

> [!NOTE]
>  <span data-ttu-id="e46a6-117">Per impostare il linguaggio di scripting predefinito per il componente script, usare l'opzione **Linguaggio di scripting** nella pagina **Generale** della finestra di dialogo **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-117">To set the default scripting language for the Script component, use the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="e46a6-118">Per ulteriori informazioni, vedere [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="e46a6-118">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>

 <span data-ttu-id="e46a6-119">Un componente di destinazione del flusso di dati include un input e nessun output.</span><span class="sxs-lookup"><span data-stu-id="e46a6-119">A data flow destination component has one input and no outputs.</span></span> <span data-ttu-id="e46a6-120">La configurazione dell'input per il componente è uno dei passaggi che vanno completati in modalità di progettazione metadati tramite **Editor trasformazione Script** prima di scrivere lo script personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e46a6-120">Configuring the input for the component is one of the steps that you must complete in metadata design mode, by using the **Script Transformation Editor**, before you write your custom script.</span></span>

### <a name="adding-connection-managers"></a><span data-ttu-id="e46a6-121">Aggiunta di gestioni connessioni</span><span class="sxs-lookup"><span data-stu-id="e46a6-121">Adding Connection Managers</span></span>
 <span data-ttu-id="e46a6-122">Normalmente, un componente di destinazione utilizza una gestione connessione esistente per connettersi all'origine dati in cui salva i dati dal flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="e46a6-122">Ordinarily a destination component uses an existing connection manager to connect to the data source to which it saves data from the data flow.</span></span> <span data-ttu-id="e46a6-123">Nella pagina **Gestioni connessioni** di **Editor trasformazione Script** fare clic su **Aggiungi** per aggiungere la gestione connessione appropriata.</span><span class="sxs-lookup"><span data-stu-id="e46a6-123">On the **Connection Managers** page of the **Script Transformation Editor**, click **Add** to add the appropriate connection manager.</span></span>

 <span data-ttu-id="e46a6-124">Tuttavia, una gestione connessione è solo un'unità pratica che incapsula e archivia le informazioni necessarie per la connessione a un'origine dati di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="e46a6-124">However, a connection manager is just a convenient unit that encapsulates and stores the information that is required to connect to a data source of a particular type.</span></span> <span data-ttu-id="e46a6-125">È necessario scrivere codice personalizzato per caricare o salvare i dati e possibilmente per aprire e chiudere la connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e46a6-125">You must write your own custom code to load or save your data, and possibly to open and close the connection to the data source.</span></span>

 <span data-ttu-id="e46a6-126">Per informazioni generali sull'uso delle gestioni connessioni con il componente Script, vedere [Connessione a origini dati nel componente Script](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="e46a6-126">For general information about how to use connection managers with the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span></span>

 <span data-ttu-id="e46a6-127">Per altre informazioni sulla pagina **Gestioni connessioni** di **Editor trasformazione Script**, vedere [Editor trasformazione Script &#40;pagina Gestioni connessioni&#41;](../script-transformation-editor-connection-managers-page.md).</span><span class="sxs-lookup"><span data-stu-id="e46a6-127">For more information about the **Connection Managers** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md).</span></span>

### <a name="configuring-inputs-and-input-columns"></a><span data-ttu-id="e46a6-128">Configurazione di input e colonne di input</span><span class="sxs-lookup"><span data-stu-id="e46a6-128">Configuring Inputs and Input Columns</span></span>
 <span data-ttu-id="e46a6-129">Un componente di destinazione include un input e nessun output.</span><span class="sxs-lookup"><span data-stu-id="e46a6-129">A destination component has one input and no outputs.</span></span>

 <span data-ttu-id="e46a6-130">Nella pagina **Colonne di input** di **Editor trasformazione Script** l'elenco di colonne contiene le colonne disponibili dell'output del componente a monte nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="e46a6-130">On the **Input Columns** page of the **Script Transformation Editor**, the column list shows the available columns from the output of the upstream component in the data flow.</span></span> <span data-ttu-id="e46a6-131">Selezionare le colonne da salvare.</span><span class="sxs-lookup"><span data-stu-id="e46a6-131">Select the columns that you want to save.</span></span>

 <span data-ttu-id="e46a6-132">Per altre informazioni sulla pagina **Colonne di input** di **Editor trasformazione Script**, vedere [Editor trasformazione Script &#40;pagina Colonne di input&#41;](../script-transformation-editor-input-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="e46a6-132">For more information about the **Input Columns** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Input Columns Page&#41;](../script-transformation-editor-input-columns-page.md).</span></span>

 <span data-ttu-id="e46a6-133">La pagina **Input e output** di **Editor trasformazione Script** contiene un unico input, che è possibile rinominare.</span><span class="sxs-lookup"><span data-stu-id="e46a6-133">The **Inputs and Outputs** page of the **Script Transformation Editor** shows a single input, which you can rename.</span></span> <span data-ttu-id="e46a6-134">Si farà riferimento all'input in base al relativo nome nello script utilizzando la proprietà della funzione di accesso creata nel codice generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e46a6-134">You will refer to the input by its name in your script by using the accessor property created in the auto-generated code.</span></span>

 <span data-ttu-id="e46a6-135">Per altre informazioni sulla pagina **Input e output** di **Editor trasformazione Script**, vedere [Editor trasformazione Script &#40;pagina Input e output&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span><span class="sxs-lookup"><span data-stu-id="e46a6-135">For more information about the **Inputs and Outputs** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span></span>

### <a name="adding-variables"></a><span data-ttu-id="e46a6-136">Aggiunta di variabili</span><span class="sxs-lookup"><span data-stu-id="e46a6-136">Adding Variables</span></span>
 <span data-ttu-id="e46a6-137">Se si desidera utilizzare le variabili esistenti nello script, è possibile aggiungerle nei campi delle `ReadOnlyVariables` proprietà e nella `ReadWriteVariables` pagina **script** di **Editor trasformazione script**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-137">If you want to use existing variables in your script, you can add them in the `ReadOnlyVariables` and `ReadWriteVariables` property fields on the **Script** page of the **Script Transformation Editor**.</span></span>

 <span data-ttu-id="e46a6-138">Quando si aggiungono più variabili nei campi delle proprietà, separare i relativi nomi con virgole.</span><span class="sxs-lookup"><span data-stu-id="e46a6-138">When you add multiple variables in the property fields, separate the variable names by commas.</span></span> <span data-ttu-id="e46a6-139">È anche possibile selezionare più variabili facendo clic sul pulsante con i puntini di sospensione (**...**) accanto ai `ReadOnlyVariables` campi delle `ReadWriteVariables` proprietà e e quindi selezionando le variabili nella finestra di dialogo **Seleziona variabili** .</span><span class="sxs-lookup"><span data-stu-id="e46a6-139">You can also select multiple variables by clicking the ellipsis (**...**) button next to the `ReadOnlyVariables` and `ReadWriteVariables` property fields, and then selecting the variables in the **Select variables** dialog box.</span></span>

 <span data-ttu-id="e46a6-140">Per informazioni generali sull'uso delle variabili con il componente script, vedere [Uso di variabili nel componente script](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="e46a6-140">For general information about how to use variables with the Script component, see [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span></span>

 <span data-ttu-id="e46a6-141">Per altre informazioni sulla pagina **Script** di **Editor trasformazione Script**, vedere [Editor trasformazione Script &#40;pagina Script&#41;](../script-transformation-editor-script-page.md).</span><span class="sxs-lookup"><span data-stu-id="e46a6-141">For more information about the **Script** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md).</span></span>

## <a name="scripting-a-destination-component-in-code-design-mode"></a><span data-ttu-id="e46a6-142">Generazione di script per un componente di destinazione in modalità di progettazione codice</span><span class="sxs-lookup"><span data-stu-id="e46a6-142">Scripting a Destination Component in Code-Design Mode</span></span>
 <span data-ttu-id="e46a6-143">Dopo aver configurato i metadati per il componente, è possibile scrivere lo script personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e46a6-143">After you have configured the metadata for your component, you can write your custom script.</span></span> <span data-ttu-id="e46a6-144">Nella pagina **Script** di **Editor trasformazione Script** fare clic su **Modifica script** per aprire l'IDE di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA), in cui è possibile aggiungere lo script personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e46a6-144">In the **Script Transformation Editor**, on the **Script** page, click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE where you can add your custom script.</span></span> <span data-ttu-id="e46a6-145">Il linguaggio di scripting che si usa varia a seconda che sia stato selezionato [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# come linguaggio di scripting per la proprietà **ScriptLanguage** nella pagina **Script**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-145">The scripting language that you use depends on whether you selected [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# as the script language for the **ScriptLanguage** property on the **Script** page.</span></span>

 <span data-ttu-id="e46a6-146">Per importanti informazioni applicabili a tutti i tipi di componenti creati tramite il componente script, vedere [Codifica e debug del componente script](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="e46a6-146">For important information that applies to all kinds of components created by using the Script component, see [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>

### <a name="understanding-the-auto-generated-code"></a><span data-ttu-id="e46a6-147">Informazioni sul codice generato automaticamente</span><span class="sxs-lookup"><span data-stu-id="e46a6-147">Understanding the Auto-generated Code</span></span>
 <span data-ttu-id="e46a6-148">Quando si apre l'IDE di VSTA dopo la creazione e la configurazione di un componente di destinazione, la classe `ScriptMain` modificabile viene visualizzata nell'editor del codice con uno stub per il metodo `ProcessInputRow`.</span><span class="sxs-lookup"><span data-stu-id="e46a6-148">When you open the VSTA IDE after you create and configuring a destination component, the editable `ScriptMain` class appears in the code editor with a stub for the `ProcessInputRow` method.</span></span> <span data-ttu-id="e46a6-149">La classe `ScriptMain` è quella in cui si scriverà il codice personalizzato, mentre `ProcessInputRow` è il metodo più importante in un componente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e46a6-149">The `ScriptMain` class is where you will write your custom code, and `ProcessInputRow` is the most important method in a destination component.</span></span>

 <span data-ttu-id="e46a6-150">Se si apre la finestra **Esplora progetti** in VSTA, è possibile osservare che il componente script ha generato anche gli elementi di `BufferWrapper` progetto e di sola lettura `ComponentWrapper` .</span><span class="sxs-lookup"><span data-stu-id="e46a6-150">If you open the **Project Explorer** window in VSTA, you can see that the Script component has also generated read-only `BufferWrapper` and `ComponentWrapper` project items.</span></span> <span data-ttu-id="e46a6-151">La classe `ScriptMain` eredita dalla classe `UserComponent` nell'elemento di progetto `ComponentWrapper`.</span><span class="sxs-lookup"><span data-stu-id="e46a6-151">The `ScriptMain` class inherits from `UserComponent` class in the `ComponentWrapper` project item.</span></span>

 <span data-ttu-id="e46a6-152">In fase di esecuzione il motore flusso di dati richiama il metodo `ProcessInput` nella classe `UserComponent`, che esegue l'override del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ProcessInput%2A> della classe padre <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="e46a6-152">At run time, the data flow engine invokes the `ProcessInput` method in the `UserComponent` class, which overrides the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ProcessInput%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> parent class.</span></span> <span data-ttu-id="e46a6-153">Il metodo `ProcessInput` a sua volta esegue il ciclo delle righe nel buffer di input e chiama il metodo `ProcessInputRow` una volta per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="e46a6-153">The `ProcessInput` method in turn loops through the rows in the input buffer and calls the `ProcessInputRow` method one time for each row.</span></span>

### <a name="writing-your-custom-code"></a><span data-ttu-id="e46a6-154">Scrittura di codice personalizzato</span><span class="sxs-lookup"><span data-stu-id="e46a6-154">Writing Your Custom Code</span></span>
 <span data-ttu-id="e46a6-155">Per completare la creazione di un componente di destinazione personalizzato, è possibile scrivere script nei metodi seguenti disponibili nella classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="e46a6-155">To finish creating a custom destination component, you may want to write script in the following methods available in the `ScriptMain` class.</span></span>

1.  <span data-ttu-id="e46a6-156">Eseguire l'override del metodo `AcquireConnections` per connettersi all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="e46a6-156">Override the `AcquireConnections` method to connect to the external data source.</span></span> <span data-ttu-id="e46a6-157">Estrarre l'oggetto connessione o le informazioni di connessione necessarie dalla gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="e46a6-157">Extract the connection object, or the required connection information, from the connection manager.</span></span>

2.  <span data-ttu-id="e46a6-158">Eseguire l'override del metodo `PreExecute` per prepararsi al salvataggio dei dati.</span><span class="sxs-lookup"><span data-stu-id="e46a6-158">Override the `PreExecute` method to prepare to save the data.</span></span> <span data-ttu-id="e46a6-159">Ad esempio, è possibile creare e configurare un oggetto `SqlCommand` e i relativi parametri in questo metodo.</span><span class="sxs-lookup"><span data-stu-id="e46a6-159">For example, you may want to create and configure a `SqlCommand` and its parameters in this method.</span></span>

3.  <span data-ttu-id="e46a6-160">Utilizzare il metodo `ProcessInputRow` sottoposto a override per copiare ogni riga di input nell'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="e46a6-160">Use the overridden `ProcessInputRow` method to copy each input row to the external data source.</span></span> <span data-ttu-id="e46a6-161">Ad esempio, per una destinazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è possibile copiare i valori delle colonne nei parametri di un oggetto `SqlCommand` ed eseguire il comando una volta per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="e46a6-161">For example, for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, you can copy the column values into the parameters of a `SqlCommand` and execute the command one time for each row.</span></span> <span data-ttu-id="e46a6-162">Per una destinazione file flat, è possibile scrivere i valori per ogni colonna in un oggetto `StreamWriter`, separandoli con il delimitatore di colonna.</span><span class="sxs-lookup"><span data-stu-id="e46a6-162">For a flat file destination, you can write the values for each column to a `StreamWriter`, separating the values by the column delimiter.</span></span>

4.  <span data-ttu-id="e46a6-163">Eseguire l'override del metodo `PostExecute` per disconnettersi dall'origine dati esterna, se necessario, e per eseguire eventuali altre operazioni di pulizia richieste.</span><span class="sxs-lookup"><span data-stu-id="e46a6-163">Override the `PostExecute` method to disconnect from the external data source, if required, and to perform any other required cleanup.</span></span>

## <a name="examples"></a><span data-ttu-id="e46a6-164">Esempi</span><span class="sxs-lookup"><span data-stu-id="e46a6-164">Examples</span></span>
 <span data-ttu-id="e46a6-165">Negli esempi seguenti è illustrato il codice necessario nella classe `ScriptMain` per creare un componente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e46a6-165">The examples that follow demonstrate code that is required in the `ScriptMain` class to create a destination component.</span></span>

> [!NOTE]
>  <span data-ttu-id="e46a6-166">In questi esempi viene utilizzata la tabella **Person. Address** nel `AdventureWorks` database di esempio e vengono passate la prima e la quarta colonna, ovvero le colonne **int \* AddressID**\* e **nvarchar (30) City** , attraverso il flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="e46a6-166">These examples use the **Person.Address** table in the `AdventureWorks` sample database and pass its first and fourth columns, the **int\*AddressID**\* and **nvarchar(30)City** columns, through the data flow.</span></span> <span data-ttu-id="e46a6-167">Gli stessi dati vengono utilizzati negli esempi relativi a origine, trasformazione e destinazione in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="e46a6-167">The same data is used in the source, transformation, and destination samples in this section.</span></span> <span data-ttu-id="e46a6-168">Per ogni esempio, sono documentati ulteriori prerequisiti e presupposti.</span><span class="sxs-lookup"><span data-stu-id="e46a6-168">Additional prerequisites and assumptions are documented for each example.</span></span>

### <a name="adonet-destination-example"></a><span data-ttu-id="e46a6-169">Esempio di destinazione ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e46a6-169">ADO.NET Destination Example</span></span>
 <span data-ttu-id="e46a6-170">In questo esempio è illustrato un componente di destinazione che usa una gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] esistente per salvare i dati del flusso di dati in una tabella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e46a6-170">This example demonstrates a destination component that uses an existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to save data from the data flow into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>

 <span data-ttu-id="e46a6-171">Se si desidera eseguire questo codice di esempio, è necessario configurare il pacchetto e il componente come segue:</span><span class="sxs-lookup"><span data-stu-id="e46a6-171">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="e46a6-172">Creare una gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] che utilizza il provider `SqlClient` per connettersi al database `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="e46a6-172">Create an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the `SqlClient` provider to connect to the `AdventureWorks` database.</span></span>

2.  <span data-ttu-id="e46a6-173">Creare una tabella di destinazione eseguendo il comando [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente nel database `AdventureWorks`:</span><span class="sxs-lookup"><span data-stu-id="e46a6-173">Create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

3.  <span data-ttu-id="e46a6-174">Aggiungere un nuovo componente script all'area di progettazione del flusso di dati e configurarlo come destinazione.</span><span class="sxs-lookup"><span data-stu-id="e46a6-174">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>

4.  <span data-ttu-id="e46a6-175">Connettere l'output di un'origine o di una trasformazione a monte al componente di destinazione in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e46a6-175">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e46a6-176">È possibile connettere un'origine direttamente a una destinazione senza alcuna trasformazione. Questo output deve fornire i dati della tabella **Person. Address** del `AdventureWorks` database di esempio che contiene almeno le colonne **AddressID** e **City** .</span><span class="sxs-lookup"><span data-stu-id="e46a6-176">(You can connect a source directly to a destination without any transformations.) This output should provide data from the **Person.Address** table of the `AdventureWorks` sample database that contains at least the **AddressID** and **City** columns.</span></span>

5.  <span data-ttu-id="e46a6-177">Aprire l'**Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-177">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="e46a6-178">Nella pagina **Colonne di input** selezionare le colonne di input **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-178">On the **Input Columns** page, select the **AddressID** and **City** input columns.</span></span>

6.  <span data-ttu-id="e46a6-179">Nella pagina **Input e output** rinominare l'input con un nome più descrittivo, ad esempio **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-179">On the **Inputs and Outputs** page, rename the input with a more descriptive name such as **MyAddressInput**.</span></span>

7.  <span data-ttu-id="e46a6-180">Nella pagina **Gestioni connessioni** aggiungere o creare la gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] e specificare un nome, ad esempio **MyADONETConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-180">On the **Connection Managers** page, add or create the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager with a name such as **MyADONETConnectionManager**.</span></span>

8.  <span data-ttu-id="e46a6-181">Nella pagina **Script** fare clic su **Modifica script** e immettere lo script seguente.</span><span class="sxs-lookup"><span data-stu-id="e46a6-181">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="e46a6-182">Quindi, chiudere l'ambiente di sviluppo dello script.</span><span class="sxs-lookup"><span data-stu-id="e46a6-182">Then close the script development environment.</span></span>

9. <span data-ttu-id="e46a6-183">Chiudere **Editor trasformazione Script** ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="e46a6-183">Close the **Script Transformation Editor** and run the sample.</span></span>

```vb
Imports System.Data.SqlClient
...
Public Class ScriptMain
    Inherits UserComponent

    Dim connMgr As IDTSConnectionManager100
    Dim sqlConn As SqlConnection
    Dim sqlCmd As SqlCommand
    Dim sqlParam As SqlParameter

    Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

        connMgr = Me.Connections.MyADONETConnectionManager
        sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

    End Sub

    Public Overrides Sub PreExecute()

        sqlCmd = New SqlCommand("INSERT INTO Person.Address2(AddressID, City) " & _
            "VALUES(@addressid, @city)", sqlConn)
        sqlParam = New SqlParameter("@addressid", SqlDbType.Int)
        sqlCmd.Parameters.Add(sqlParam)
        sqlParam = New SqlParameter("@city", SqlDbType.NVarChar, 30)
        sqlCmd.Parameters.Add(sqlParam)

    End Sub

    Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)
        With sqlCmd
            .Parameters("@addressid").Value = Row.AddressID
            .Parameters("@city").Value = Row.City
            .ExecuteNonQuery()
        End With
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
    SqlCommand sqlCmd;
    SqlParameter sqlParam;

    public override void AcquireConnections(object Transaction)
    {

        connMgr = this.Connections.MyADONETConnectionManager;
        sqlConn = (SqlConnection)connMgr.AcquireConnection(null);

    }

    public override void PreExecute()
    {

        sqlCmd = new SqlCommand("INSERT INTO Person.Address2(AddressID, City) " +
            "VALUES(@addressid, @city)", sqlConn);
        sqlParam = new SqlParameter("@addressid", SqlDbType.Int);
        sqlCmd.Parameters.Add(sqlParam);
        sqlParam = new SqlParameter("@city", SqlDbType.NVarChar, 30);
        sqlCmd.Parameters.Add(sqlParam);

    }

    public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)
    {
        {
            sqlCmd.Parameters["@addressid"].Value = Row.AddressID;
            sqlCmd.Parameters["@city"].Value = Row.City;
            sqlCmd.ExecuteNonQuery();
        }
    }

    public override void ReleaseConnections()
    {

        connMgr.ReleaseConnection(sqlConn);

    }

}
```

### <a name="flat-file-destination-example"></a><span data-ttu-id="e46a6-184">Esempio di destinazione file flat</span><span class="sxs-lookup"><span data-stu-id="e46a6-184">Flat File Destination Example</span></span>
 <span data-ttu-id="e46a6-185">In questo esempio è illustrato un componente di destinazione che utilizza una gestione connessione file flat esistente per salvare i dati del flusso di dati in un file flat.</span><span class="sxs-lookup"><span data-stu-id="e46a6-185">This example demonstrates a destination component that uses an existing Flat File connection manager to save data from the data flow to a flat file.</span></span>

 <span data-ttu-id="e46a6-186">Se si desidera eseguire questo codice di esempio, è necessario configurare il pacchetto e il componente come segue:</span><span class="sxs-lookup"><span data-stu-id="e46a6-186">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="e46a6-187">Creare una gestione connessione file flat che si connette a un file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e46a6-187">Create a Flat File connection manager that connects to a destination file.</span></span> <span data-ttu-id="e46a6-188">Il file non deve necessariamente esistere, in quanto verrà creato dal componente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e46a6-188">The file does not have to exist; the destination component will create it.</span></span> <span data-ttu-id="e46a6-189">Configurare il file di destinazione come file delimitato da virgole che contiene le colonne **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-189">Configure the destination file as a comma-delimited file that contains the **AddressID** and **City** columns.</span></span>

2.  <span data-ttu-id="e46a6-190">Aggiungere un nuovo componente script all'area di progettazione del flusso di dati e configurarlo come destinazione.</span><span class="sxs-lookup"><span data-stu-id="e46a6-190">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>

3.  <span data-ttu-id="e46a6-191">Connettere l'output di un'origine o di una trasformazione a monte al componente di destinazione in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e46a6-191">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e46a6-192">È possibile connettere un'origine direttamente a una destinazione senza alcuna trasformazione. Questo output deve fornire i dati della tabella **Person. Address** del `AdventureWorks` database di esempio e deve contenere almeno le colonne **AddressID** e **City** .</span><span class="sxs-lookup"><span data-stu-id="e46a6-192">(You can connect a source directly to a destination without any transformations.) This output should provide data from the **Person.Address** table of the `AdventureWorks` sample database, and should contain at least the **AddressID** and **City** columns.</span></span>

4.  <span data-ttu-id="e46a6-193">Aprire l'**Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-193">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="e46a6-194">Nella pagina **Colonne di input** selezionare le colonne **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-194">On the **Input Columns** page, select the **AddressID** and **City** columns.</span></span>

5.  <span data-ttu-id="e46a6-195">Nella pagina **Input e output** rinominare l'input con un nome più descrittivo, ad esempio **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-195">On the **Inputs and Outputs** page, rename the input with a more descriptive name, such as **MyAddressInput**.</span></span>

6.  <span data-ttu-id="e46a6-196">Nella pagina **Gestioni connessioni** aggiungere o creare la gestione connessione file flat usando un nome descrittivo, ad esempio **MyFlatFileDestConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="e46a6-196">On the **Connection Managers** page, add or create the Flat File connection manager with a descriptive name such as **MyFlatFileDestConnectionManager**.</span></span>

7.  <span data-ttu-id="e46a6-197">Nella pagina **Script** fare clic su **Modifica script** e immettere lo script seguente.</span><span class="sxs-lookup"><span data-stu-id="e46a6-197">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="e46a6-198">Quindi, chiudere l'ambiente di sviluppo dello script.</span><span class="sxs-lookup"><span data-stu-id="e46a6-198">Then close the script development environment.</span></span>

8.  <span data-ttu-id="e46a6-199">Chiudere **Editor trasformazione Script** ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="e46a6-199">Close the **Script Transformation Editor** and run the sample.</span></span>

```vb
Imports System.IO
...
Public Class ScriptMain
    Inherits UserComponent

    Dim copiedAddressFile As String
    Private textWriter As StreamWriter
    Private columnDelimiter As String = ","

    Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

        Dim connMgr As IDTSConnectionManager100 = _
            Me.Connections.MyFlatFileDestConnectionManager
        copiedAddressFile = CType(connMgr.AcquireConnection(Nothing), String)

    End Sub

    Public Overrides Sub PreExecute()

        textWriter = New StreamWriter(copiedAddressFile, False)

    End Sub

    Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)

        With textWriter
            If Not Row.AddressID_IsNull Then
                .Write(Row.AddressID)
            End If
            .Write(columnDelimiter)
            If Not Row.City_IsNull Then
                .Write(Row.City)
            End If
            .WriteLine()
        End With

    End Sub

    Public Overrides Sub PostExecute()

        textWriter.Close()

    End Sub

End Class
```

```csharp
using System.IO;
public class ScriptMain:
    UserComponent

{
    string copiedAddressFile;
    private StreamWriter textWriter;
    private string columnDelimiter = ",";

    public override void AcquireConnections(object Transaction)
    {

        IDTSConnectionManager100 connMgr = this.Connections.MyFlatFileDestConnectionManager;
        copiedAddressFile = (string) connMgr.AcquireConnection(null);

    }

    public override void PreExecute()
    {

        textWriter = new StreamWriter(copiedAddressFile, false);

    }

    public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)
    {

        {
            if (!Row.AddressID_IsNull)
            {
                textWriter.Write(Row.AddressID);
            }
            textWriter.Write(columnDelimiter);
            if (!Row.City_IsNull)
            {
                textWriter.Write(Row.City);
            }
            textWriter.WriteLine();
        }

    }

    public override void PostExecute()
    {

        textWriter.Close();

    }

}
```

<span data-ttu-id="e46a6-200">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e46a6-200">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e46a6-201">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="e46a6-201">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e46a6-202">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="e46a6-202">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e46a6-203">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e46a6-203">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="e46a6-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e46a6-204">See Also</span></span>
 <span data-ttu-id="e46a6-205">[Creazione di un'origine con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md) [sviluppo di un componente di destinazione personalizzato](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)</span><span class="sxs-lookup"><span data-stu-id="e46a6-205">[Creating a Source with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md) [Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)</span></span>


