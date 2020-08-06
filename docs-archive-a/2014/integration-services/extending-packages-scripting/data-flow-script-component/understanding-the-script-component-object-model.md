---
title: Informazioni sul modello a oggetti del componente script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], object model
ms.assetid: 2a0aae82-39cc-4423-b09a-72d2f61033bd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a11556b00efc5749e8ddb895712d6c61f2459d8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627897"
---
# <a name="understanding-the-script-component-object-model"></a><span data-ttu-id="58ce1-102">Informazioni sul modello a oggetti del componente script</span><span class="sxs-lookup"><span data-stu-id="58ce1-102">Understanding the Script Component Object Model</span></span>
  <span data-ttu-id="58ce1-103">Come descritto in [codifica e debug del componente script] (.. /Extending-Packages-scripting/Data-Flow-Script-Component/Coding-and-Debugging-the-script-component.MD, il progetto del componente script contiene tre elementi del progetto:</span><span class="sxs-lookup"><span data-stu-id="58ce1-103">As discussed in [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md, the Script component project contains three project items:</span></span>

1.  <span data-ttu-id="58ce1-104">L'elemento `ScriptMain`, che contiene la classe `ScriptMain` in cui si scrive il codice.</span><span class="sxs-lookup"><span data-stu-id="58ce1-104">The `ScriptMain` item, which contains the `ScriptMain` class in which you write your code.</span></span> <span data-ttu-id="58ce1-105">La classe `ScriptMain` eredita dalla classe `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-105">The `ScriptMain` class inherits from the `UserComponent` class.</span></span>

2.  <span data-ttu-id="58ce1-106">L'elemento `ComponentWrapper`, che contiene la classe `UserComponent`, un'istanza di <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> che contiene i metodi e le proprietà da utilizzare per elaborare i dati e per interagire con il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="58ce1-106">The `ComponentWrapper` item, which contains the `UserComponent` class, an instance of <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> that contains the methods and properties that you will use to process data and to interact with the package.</span></span> <span data-ttu-id="58ce1-107">L'elemento `ComponentWrapper` contiene anche le classi di raccolte `Connections` e `Variables`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-107">The `ComponentWrapper` item also contains `Connections` and `Variables` collection classes.</span></span>

3.  <span data-ttu-id="58ce1-108">L'elemento `BufferWrapper`, che contiene le classi che ereditano da <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> per ogni input e output, nonché le proprietà tipizzate per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="58ce1-108">The `BufferWrapper` item, which contains classes that inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> for each input and output, and typed properties for each column.</span></span>

 <span data-ttu-id="58ce1-109">Quando si scrive codice nell'elemento `ScriptMain`, si utilizzeranno gli oggetti, i metodi e le proprietà descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="58ce1-109">As you write your code in the `ScriptMain` item, you will use the objects, methods, and properties discussed in this topic.</span></span> <span data-ttu-id="58ce1-110">Ogni componente non utilizzerà tutti i metodi elencati, ma se li utilizza la sequenza sarà quella illustrata.</span><span class="sxs-lookup"><span data-stu-id="58ce1-110">Each component will not use all the methods listed here; however, when used, they are used in the sequence shown.</span></span>

 <span data-ttu-id="58ce1-111">La classe di base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> non contiene codice di implementazione per i metodi descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="58ce1-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class does not contain any implementation code for the methods discussed in this topic.</span></span> <span data-ttu-id="58ce1-112">Pertanto, non è necessario aggiungere una chiamata all'implementazione della classe di base nell'implementazione del metodo, anche se questa operazione non genera errori.</span><span class="sxs-lookup"><span data-stu-id="58ce1-112">Therefore it is unnecessary, but harmless, to add a call to the base class implementation to your own implementation of the method.</span></span>

 <span data-ttu-id="58ce1-113">Per informazioni su come usare i metodi e le proprietà di queste classi in un tipo di componente script specifico, vedere la sezione [Ulteriori esempi di componente script](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="58ce1-113">For information about how to use the methods and properties of these classes in a particular type of Script component, see the section [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span> <span data-ttu-id="58ce1-114">Negli argomenti di esempio vengono inoltre presentati esempi di codice completi.</span><span class="sxs-lookup"><span data-stu-id="58ce1-114">The example topics also contain complete code samples.</span></span>

## <a name="acquireconnections-method"></a><span data-ttu-id="58ce1-115">Metodo AcquireConnections</span><span class="sxs-lookup"><span data-stu-id="58ce1-115">AcquireConnections Method</span></span>
 <span data-ttu-id="58ce1-116">Le origini e le destinazioni devono in genere connettersi a un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="58ce1-116">Sources and destinations generally must connect to an external data source.</span></span> <span data-ttu-id="58ce1-117">Eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> della classe di base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> per recuperare la connessione o le informazioni di connessione dalla gestione connessione appropriata.</span><span class="sxs-lookup"><span data-stu-id="58ce1-117">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class to retrieve the connection or the connection information from the appropriate connection manager.</span></span>

 <span data-ttu-id="58ce1-118">Nell'esempio seguente viene restituito `System.Data.SqlClient.SqlConnection` da una gestione connessione ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="58ce1-118">The following example returns a `System.Data.SqlClient.SqlConnection` from an ADO.NET connection manager.</span></span>

```vb
Dim connMgr As IDTSConnectionManager100
Dim sqlConn As SqlConnection

Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

    connMgr = Me.Connections.MyADONETConnection
    sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

End Sub
```

 <span data-ttu-id="58ce1-119">Nell'esempio seguente vengono restituiti un percorso completo e un nome file da una gestione connessione file flat, quindi il file viene aperto tramite `System.IO.StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-119">The following example returns a complete path and file name from a Flat File Connection Manager, and then opens the file by using a `System.IO.StreamReader`.</span></span>

```vb
Private textReader As StreamReader
Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

    Dim connMgr As IDTSConnectionManager100 = _
        Me.Connections.MyFlatFileSrcConnectionManager
    Dim exportedAddressFile As String = _
        CType(connMgr.AcquireConnection(Nothing), String)
    textReader = New StreamReader(exportedAddressFile)

End Sub
```

## <a name="preexecute-method"></a><span data-ttu-id="58ce1-120">Metodo PreExecute</span><span class="sxs-lookup"><span data-stu-id="58ce1-120">PreExecute Method</span></span>
 <span data-ttu-id="58ce1-121">Eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PreExecute%2A> della classe di base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> quando è necessario eseguire un'elaborazione una volta solo prima di avviare l'elaborazione delle righe di dati.</span><span class="sxs-lookup"><span data-stu-id="58ce1-121">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PreExecute%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class whenever you have processing that you must perform one time only before you start processing rows of data.</span></span> <span data-ttu-id="58ce1-122">In una destinazione, ad esempio, è possibile configurare il comando con parametri che verrà utilizzato dalla destinazione stessa per inserire ogni riga di dati nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="58ce1-122">For example, in a destination, you may want to configure the parameterized command that the destination will use to insert each row of data into the data source.</span></span>

```vb
    Dim sqlConn As SqlConnection
    Dim sqlCmd As SqlCommand
    Dim sqlParam As SqlParameter
...
    Public Overrides Sub PreExecute()

        sqlCmd = New SqlCommand("INSERT INTO Person.Address2(AddressID, City) " & _
            "VALUES(@addressid, @city)", sqlConn)
        sqlParam = New SqlParameter("@addressid", SqlDbType.Int)
        sqlCmd.Parameters.Add(sqlParam)
        sqlParam = New SqlParameter("@city", SqlDbType.NVarChar, 30)
        sqlCmd.Parameters.Add(sqlParam)

    End Sub
```

```csharp
SqlConnection sqlConn; 
SqlCommand sqlCmd; 
SqlParameter sqlParam; 

public override void PreExecute() 
{ 

    sqlCmd = new SqlCommand("INSERT INTO Person.Address2(AddressID, City) " + "VALUES(@addressid, @city)", sqlConn); 
    sqlParam = new SqlParameter("@addressid", SqlDbType.Int); 
    sqlCmd.Parameters.Add(sqlParam); 
    sqlParam = new SqlParameter("@city", SqlDbType.NVarChar, 30); 
    sqlCmd.Parameters.Add(sqlParam); 

}
```

## <a name="processing-inputs-and-outputs"></a><span data-ttu-id="58ce1-123">Elaborazione di input e output</span><span class="sxs-lookup"><span data-stu-id="58ce1-123">Processing Inputs and Outputs</span></span>

### <a name="processing-inputs"></a><span data-ttu-id="58ce1-124">Elaborazione di input</span><span class="sxs-lookup"><span data-stu-id="58ce1-124">Processing Inputs</span></span>
 <span data-ttu-id="58ce1-125">I componenti script configurati come trasformazioni o destinazioni prevedono un unico input.</span><span class="sxs-lookup"><span data-stu-id="58ce1-125">Script components that are configured as transformations or destinations have one input.</span></span>

#### <a name="what-the-bufferwrapper-project-item-provides"></a><span data-ttu-id="58ce1-126">Contenuto dell'elemento di progetto BufferWrapper</span><span class="sxs-lookup"><span data-stu-id="58ce1-126">What the BufferWrapper Project Item Provides</span></span>
 <span data-ttu-id="58ce1-127">Per ogni input configurato, l'elemento di progetto `BufferWrapper` contiene una classe che deriva da <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> e ha lo stesso nome dell'input.</span><span class="sxs-lookup"><span data-stu-id="58ce1-127">For each input that you have configured, the `BufferWrapper` project item contains a class that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> and has the same name as the input.</span></span> <span data-ttu-id="58ce1-128">Ogni classe del buffer di input contiene le proprietà, le funzioni e i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="58ce1-128">Each input buffer class contains the following properties, functions, and methods:</span></span>

-   <span data-ttu-id="58ce1-129">Proprietà delle funzioni di accesso denominate e tipizzate per ogni colonna di input selezionata.</span><span class="sxs-lookup"><span data-stu-id="58ce1-129">Named, typed accessor properties for each selected input column.</span></span> <span data-ttu-id="58ce1-130">Queste proprietà sono di sola lettura o di lettura/scrittura a seconda del **Tipo di utilizzo** specificato per la colonna nella pagina **Colonne di input** di **Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="58ce1-130">These properties are read-only or read/write depending on the **Usage Type** specified for the column on the **Input Columns** page of the **Script Transformation Editor**.</span></span>

-   <span data-ttu-id="58ce1-131">Una proprietà **\<column>_IsNull** per ogni colonna di input selezionata.</span><span class="sxs-lookup"><span data-stu-id="58ce1-131">A **\<column>_IsNull** property for each selected input column.</span></span> <span data-ttu-id="58ce1-132">Anche questa proprietà è di sola lettura o di lettura/scrittura a seconda del **Tipo di utilizzo** specificato per la colonna.</span><span class="sxs-lookup"><span data-stu-id="58ce1-132">This property is also read-only or read/write depending on the **Usage Type** specified for the column.</span></span>

-   <span data-ttu-id="58ce1-133">Metodo **DirectRowTo\<outputbuffer>** per ogni output configurato.</span><span class="sxs-lookup"><span data-stu-id="58ce1-133">A **DirectRowTo\<outputbuffer>** method for each configured output.</span></span> <span data-ttu-id="58ce1-134">Questi metodi verranno utilizzati per il filtro delle righe in uno degli output dello stesso oggetto `ExclusionGroup`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-134">You will use these methods when filtering rows to one of several outputs in the same `ExclusionGroup`.</span></span>

-   <span data-ttu-id="58ce1-135">Funzione `NextRow` per ottenere la riga di input successiva e funzione `EndOfRowset` per determinare se è stato elaborato l'ultimo buffer di dati.</span><span class="sxs-lookup"><span data-stu-id="58ce1-135">A `NextRow` function to get the next input row, and an `EndOfRowset` function to determine whether the last buffer of data has been processed.</span></span> <span data-ttu-id="58ce1-136">Queste funzioni non sono in genere necessarie quando si utilizzano i metodi di elaborazione dell'input implementati nella classe di base `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-136">You typically do not need these functions when you use the input processing methods implemented in the `UserComponent` base class.</span></span> <span data-ttu-id="58ce1-137">Nella sezione seguente vengono fornite ulteriori informazioni sulla classe di base `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-137">The next section provides more information about the `UserComponent` base class.</span></span>

#### <a name="what-the-componentwrapper-project-item-provides"></a><span data-ttu-id="58ce1-138">Contenuto dell'elemento di progetto ComponentWrapper</span><span class="sxs-lookup"><span data-stu-id="58ce1-138">What the ComponentWrapper Project Item Provides</span></span>
 <span data-ttu-id="58ce1-139">L'elemento di progetto ComponentWrapper contiene una classe denominata `UserComponent` che deriva da <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="58ce1-139">The ComponentWrapper project item contains a class named `UserComponent` that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span></span> <span data-ttu-id="58ce1-140">La classe `ScriptMain` in cui si scrive il codice personalizzato deriva a sua volta da `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-140">The `ScriptMain` class in which you write your custom code derives in turn from `UserComponent`.</span></span> <span data-ttu-id="58ce1-141">La classe `UserComponent` contiene i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="58ce1-141">The `UserComponent` class contains the following methods:</span></span>

-   <span data-ttu-id="58ce1-142">Un'implementazione sottoposta a override del metodo `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-142">An overridden implementation of the `ProcessInput` method.</span></span> <span data-ttu-id="58ce1-143">Si tratta del metodo chiamato dal motore flusso di dati in fase di esecuzione dopo il metodo `PreExecute` e può essere chiamato più volte.</span><span class="sxs-lookup"><span data-stu-id="58ce1-143">This is the method that the data flow engine calls next at run time after the `PreExecute` method, and it may be called multiple times.</span></span> <span data-ttu-id="58ce1-144">`ProcessInput`passa l'elaborazione al metodo \*\* \<inputbuffer> _ProcessInput\*\* .</span><span class="sxs-lookup"><span data-stu-id="58ce1-144">`ProcessInput` hands off processing to the **\<inputbuffer>_ProcessInput** method.</span></span> <span data-ttu-id="58ce1-145">Quindi, il metodo `ProcessInput` verifica se è stata raggiunta la fine del buffer di input e, in caso affermativo, chiama il metodo `FinishOutputs` sottoponibile a override e il metodo privato `MarkOutputsAsFinished`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-145">Then the `ProcessInput` method checks for the end of the input buffer and, if the end of the buffer has been reached, calls the overridable `FinishOutputs` method and the private `MarkOutputsAsFinished` method.</span></span> <span data-ttu-id="58ce1-146">Il metodo `MarkOutputsAsFinished` chiama infine `SetEndOfRowset` sull'ultimo buffer di output.</span><span class="sxs-lookup"><span data-stu-id="58ce1-146">The `MarkOutputsAsFinished` method then calls `SetEndOfRowset` on the last output buffer.</span></span>

-   <span data-ttu-id="58ce1-147">Un'implementazione sovrascrivibile del metodo **\<inputbuffer>_ProcessInput**.</span><span class="sxs-lookup"><span data-stu-id="58ce1-147">An overridable implementation of the **\<inputbuffer>_ProcessInput** method.</span></span> <span data-ttu-id="58ce1-148">Questa implementazione predefinita esegue il ciclo di ogni riga di input e chiama **\<inputbuffer>_ProcessInputRow**.</span><span class="sxs-lookup"><span data-stu-id="58ce1-148">This default implementation simply loops through each input row and calls **\<inputbuffer>_ProcessInputRow**.</span></span>

-   <span data-ttu-id="58ce1-149">Un'implementazione sovrascrivibile del metodo **\<inputbuffer>_ProcessInputRow**.</span><span class="sxs-lookup"><span data-stu-id="58ce1-149">An overridable implementation of the **\<inputbuffer>_ProcessInputRow** method.</span></span> <span data-ttu-id="58ce1-150">L'implementazione predefinita è vuota.</span><span class="sxs-lookup"><span data-stu-id="58ce1-150">The default implementation is empty.</span></span> <span data-ttu-id="58ce1-151">Si tratta del metodo di cui in genere si esegue l'override per scrivere il codice personalizzato di elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="58ce1-151">This is the method that you will normally override to write your custom data processing code.</span></span>

#### <a name="what-your-custom-code-should-do"></a><span data-ttu-id="58ce1-152">Funzione del codice personalizzato</span><span class="sxs-lookup"><span data-stu-id="58ce1-152">What Your Custom Code Should Do</span></span>
 <span data-ttu-id="58ce1-153">È possibile utilizzare i metodi seguenti per elaborare l'input nella classe `ScriptMain`:</span><span class="sxs-lookup"><span data-stu-id="58ce1-153">You can use the following methods to process input in the `ScriptMain` class:</span></span>

-   <span data-ttu-id="58ce1-154">Eseguire l'override di **\<inputbuffer>_ProcessInputRow** per elaborare i dati in ogni riga di input non appena vengono passati.</span><span class="sxs-lookup"><span data-stu-id="58ce1-154">Override **\<inputbuffer>_ProcessInputRow** to process the data in each input row as it passes through.</span></span>

-   <span data-ttu-id="58ce1-155">Eseguire l'override di **\<inputbuffer>_ProcessInput** solo se è necessario eseguire operazioni aggiuntive mentre si esegue il ciclo delle righe di input,</span><span class="sxs-lookup"><span data-stu-id="58ce1-155">Override **\<inputbuffer>_ProcessInput** only if you have to do something additional while looping through input rows.</span></span> <span data-ttu-id="58ce1-156">È ad esempio necessario testare per `EndOfRowset` eseguire altre operazioni dopo l'elaborazione di tutte le righe. Chiamare \*\* \<inputbuffer> _ProcessInputRow\*\* per eseguire l'elaborazione delle righe.</span><span class="sxs-lookup"><span data-stu-id="58ce1-156">(For example, you have to test for `EndOfRowset` to take some other action after all rows have been processed.) Call **\<inputbuffer>_ProcessInputRow** to perform the row processing.</span></span>

-   <span data-ttu-id="58ce1-157">Eseguire l'override di `FinishOutputs` se è necessario eseguire operazioni sugli output prima che vengano chiusi.</span><span class="sxs-lookup"><span data-stu-id="58ce1-157">Override `FinishOutputs` if you have to do something to the outputs before they are closed.</span></span>

 <span data-ttu-id="58ce1-158">Il metodo `ProcessInput` assicura che questi metodi vengano chiamati nel momento appropriato.</span><span class="sxs-lookup"><span data-stu-id="58ce1-158">The `ProcessInput` method ensures that these methods are called at the appropriate times.</span></span>

### <a name="processing-outputs"></a><span data-ttu-id="58ce1-159">Elaborazione degli output</span><span class="sxs-lookup"><span data-stu-id="58ce1-159">Processing Outputs</span></span>
 <span data-ttu-id="58ce1-160">I componenti script configurati come origini o trasformazioni includono uno o più output.</span><span class="sxs-lookup"><span data-stu-id="58ce1-160">Script components configured as sources or transformations have one or more outputs.</span></span>

#### <a name="what-the-bufferwrapper-project-item-provides"></a><span data-ttu-id="58ce1-161">Contenuto dell'elemento di progetto BufferWrapper</span><span class="sxs-lookup"><span data-stu-id="58ce1-161">What the BufferWrapper Project Item Provides</span></span>
 <span data-ttu-id="58ce1-162">Per ogni output configurato, l'elemento di progetto BufferWrapper contiene una classe che deriva da <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> e ha lo stesso nome dell'output.</span><span class="sxs-lookup"><span data-stu-id="58ce1-162">For each output that you have configured, the BufferWrapper project item contains a class that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> and has the same name as the output.</span></span> <span data-ttu-id="58ce1-163">Ogni classe del buffer di input contiene le proprietà e i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="58ce1-163">Each input buffer class contains the following properties and methods:</span></span>

-   <span data-ttu-id="58ce1-164">Proprietà delle funzioni di accesso di sola scrittura, denominate e tipizzate per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="58ce1-164">Named, typed, write-only accessor properties for each output column.</span></span>

-   <span data-ttu-id="58ce1-165">Proprietà di \*\* \<column> _IsNull\*\* di sola scrittura per ogni colonna di output selezionata che è possibile utilizzare per impostare il valore della colonna su `null` .</span><span class="sxs-lookup"><span data-stu-id="58ce1-165">A write-only **\<column>_IsNull** property for each selected output column that you can use to set the column value to `null`.</span></span>

-   <span data-ttu-id="58ce1-166">Un metodo `AddRow` per aggiungere una nuova riga vuota nel buffer di output.</span><span class="sxs-lookup"><span data-stu-id="58ce1-166">An `AddRow` method to add an empty new row to the output buffer.</span></span>

-   <span data-ttu-id="58ce1-167">Un metodo `SetEndOfRowset` per indicare al motore flusso di dati che non sono previsti altri buffer di dati.</span><span class="sxs-lookup"><span data-stu-id="58ce1-167">A `SetEndOfRowset` method to let the data flow engine know that no more buffers of data are expected.</span></span> <span data-ttu-id="58ce1-168">È inoltre disponibile una funzione `EndOfRowset` per determinare se il buffer corrente è l'ultimo buffer di dati.</span><span class="sxs-lookup"><span data-stu-id="58ce1-168">There is also an `EndOfRowset` function to determine whether the current buffer is the last buffer of data.</span></span> <span data-ttu-id="58ce1-169">Queste funzioni non sono in genere necessarie quando si utilizzano i metodi di elaborazione dell'input implementati nella classe di base `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-169">You generally do not need these functions when you use the input processing methods implemented in the `UserComponent` base class.</span></span>

#### <a name="what-the-componentwrapper-project-item-provides"></a><span data-ttu-id="58ce1-170">Contenuto dell'elemento di progetto ComponentWrapper</span><span class="sxs-lookup"><span data-stu-id="58ce1-170">What the ComponentWrapper Project Item Provides</span></span>
 <span data-ttu-id="58ce1-171">L'elemento di progetto ComponentWrapper contiene una classe denominata `UserComponent` che deriva da <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="58ce1-171">The ComponentWrapper project item contains a class named `UserComponent` that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span></span> <span data-ttu-id="58ce1-172">La classe `ScriptMain` in cui si scrive il codice personalizzato deriva a sua volta da `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-172">The `ScriptMain` class in which you write your custom code derives in turn from `UserComponent`.</span></span> <span data-ttu-id="58ce1-173">La classe `UserComponent` contiene i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="58ce1-173">The `UserComponent` class contains the following methods:</span></span>

-   <span data-ttu-id="58ce1-174">Un'implementazione sottoposta a override del metodo `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-174">An overridden implementation of the `PrimeOutput` method.</span></span> <span data-ttu-id="58ce1-175">Il motore flusso di dati chiama questo metodo prima di `ProcessInput` in fase di esecuzione e viene chiamato solo una volta.</span><span class="sxs-lookup"><span data-stu-id="58ce1-175">The data flow engine calls this method before `ProcessInput` at run time, and it is only called one time.</span></span> <span data-ttu-id="58ce1-176">`PrimeOutput` trasferisce l'elaborazione al metodo `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-176">`PrimeOutput` hands off processing to the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="58ce1-177">Quindi, se il componente è un'origine (ovvero non include input), `PrimeOutput` chiama il metodo `FinishOutputs` sottoponibile a override e il metodo privato `MarkOutputsAsFinished`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-177">Then, if the component is a source (that is, the component has no inputs), `PrimeOutput` calls the overridable `FinishOutputs` method and the private `MarkOutputsAsFinished` method.</span></span> <span data-ttu-id="58ce1-178">Il metodo `MarkOutputsAsFinished` chiama `SetEndOfRowset` sull'ultimo buffer di output.</span><span class="sxs-lookup"><span data-stu-id="58ce1-178">The `MarkOutputsAsFinished` method calls `SetEndOfRowset` on the last output buffer.</span></span>

-   <span data-ttu-id="58ce1-179">Un'implementazione sottoponibile a override del metodo `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-179">An overridable implementation of the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="58ce1-180">L'implementazione predefinita è vuota.</span><span class="sxs-lookup"><span data-stu-id="58ce1-180">The default implementation is empty.</span></span> <span data-ttu-id="58ce1-181">Si tratta del metodo di cui in genere si esegue l'override per scrivere il codice personalizzato di elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="58ce1-181">This is the method that you will normally override to write your custom data processing code.</span></span>

#### <a name="what-your-custom-code-should-do"></a><span data-ttu-id="58ce1-182">Funzione del codice personalizzato</span><span class="sxs-lookup"><span data-stu-id="58ce1-182">What Your Custom Code Should Do</span></span>
 <span data-ttu-id="58ce1-183">È possibile utilizzare i metodi seguenti per elaborare gli output nella classe `ScriptMain`:</span><span class="sxs-lookup"><span data-stu-id="58ce1-183">You can use the following methods to process outputs in the `ScriptMain` class:</span></span>

-   <span data-ttu-id="58ce1-184">Eseguire l'override di `CreateNewOutputRows` solo quando è possibile aggiungere e popolare righe di output prima dell'elaborazione delle righe di input.</span><span class="sxs-lookup"><span data-stu-id="58ce1-184">Override `CreateNewOutputRows` only when you can add and populate output rows before processing input rows.</span></span> <span data-ttu-id="58ce1-185">Ad esempio, è possibile utilizzare `CreateNewOutputRows` in un'origine, ma in una trasformazione con output asincroni è necessario chiamare `AddRow` durante o dopo l'elaborazione dei dati di input.</span><span class="sxs-lookup"><span data-stu-id="58ce1-185">For example, you can use `CreateNewOutputRows` in a source, but in a transformation with asynchronous outputs, you should call `AddRow` during or after the processing of input data.</span></span>

-   <span data-ttu-id="58ce1-186">Eseguire l'override di `FinishOutputs` se è necessario eseguire operazioni sugli output prima che vengano chiusi.</span><span class="sxs-lookup"><span data-stu-id="58ce1-186">Override `FinishOutputs` if you have to do something to the outputs before they are closed.</span></span>

 <span data-ttu-id="58ce1-187">Il metodo `PrimeOutput` assicura che questi metodi vengano chiamati nel momento appropriato.</span><span class="sxs-lookup"><span data-stu-id="58ce1-187">The `PrimeOutput` method ensures that these methods are called at the appropriate times.</span></span>

## <a name="postexecute-method"></a><span data-ttu-id="58ce1-188">Metodo PostExecute</span><span class="sxs-lookup"><span data-stu-id="58ce1-188">PostExecute Method</span></span>
 <span data-ttu-id="58ce1-189">Eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PostExecute%2A> della classe di base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> quando è necessario eseguire un'elaborazione un'unica volta solo dopo aver elaborato le righe di dati.</span><span class="sxs-lookup"><span data-stu-id="58ce1-189">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PostExecute%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class whenever you have processing that you must perform one time only after you have processed the rows of data.</span></span> <span data-ttu-id="58ce1-190">Ad esempio, in un'origine può essere necessario chiudere l'oggetto `System.Data.SqlClient.SqlDataReader` utilizzato per caricare dati nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="58ce1-190">For example, in a source, you may want to close the `System.Data.SqlClient.SqlDataReader` that you have used to load data into the data flow.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="58ce1-191">La raccolta di `ReadWriteVariables` è disponibile solo nel metodo `PostExecute`.</span><span class="sxs-lookup"><span data-stu-id="58ce1-191">The collection of `ReadWriteVariables` is available only in the `PostExecute` method.</span></span> <span data-ttu-id="58ce1-192">Pertanto, non è possibile incrementare direttamente il valore di una variabile del pacchetto durante l'elaborazione di ogni riga di dati.</span><span class="sxs-lookup"><span data-stu-id="58ce1-192">Therefore you cannot directly increment the value of a package variable as you process each row of data.</span></span> <span data-ttu-id="58ce1-193">Al contrario, incrementare il valore di una variabile locale e impostare il valore della variabile del pacchetto sul valore della variabile locale nel metodo `PostExecute` dopo l'elaborazione di tutti i dati.</span><span class="sxs-lookup"><span data-stu-id="58ce1-193">Instead, increment the value of a local variable, and set the value of the package variable to the value of the local variable in the `PostExecute` method after all data has been processed.</span></span>

## <a name="releaseconnections-method"></a><span data-ttu-id="58ce1-194">Metodo ReleaseConnections</span><span class="sxs-lookup"><span data-stu-id="58ce1-194">ReleaseConnections Method</span></span>
 <span data-ttu-id="58ce1-195">Le origini e le destinazioni devono in genere connettersi a un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="58ce1-195">Sources and destinations typically must connect to an external data source.</span></span> <span data-ttu-id="58ce1-196">Eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ReleaseConnections%2A> della classe di base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> per chiudere e rilasciare la connessione aperta in precedenza nel metodo <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="58ce1-196">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ReleaseConnections%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class to close and release the connection that you have opened previously in the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> method.</span></span>

```vb
    Dim connMgr As IDTSConnectionManager100
...
    Public Overrides Sub ReleaseConnections()

        connMgr.ReleaseConnection(sqlConn)

    End Sub
```

```csharp
IDTSConnectionManager100 connMgr;

public override void ReleaseConnections()
{

    connMgr.ReleaseConnection(sqlConn);

}
```

<span data-ttu-id="58ce1-197">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="58ce1-197">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="58ce1-198">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="58ce1-198">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="58ce1-199">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="58ce1-199">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="58ce1-200">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="58ce1-200">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="58ce1-201">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58ce1-201">See Also</span></span>
 <span data-ttu-id="58ce1-202">[Configurazione del componente script nell'editor del componente script](configuring-the-script-component-in-the-script-component-editor.md) [codifica e debug del componente script] (.. /extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md</span><span class="sxs-lookup"><span data-stu-id="58ce1-202">[Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md) [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md</span></span>


