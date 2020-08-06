---
title: Sviluppo di un componente di trasformazione personalizzato con output sincroni | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom data flow components [Integration Services], transformation components
- ProcessInput method
- buffer allocations [Integration Services]
- synchronous outputs [Integration Services]
- transformation components [Integration Services]
- output columns [Integration Services]
- data flow components [Integration Services], transformation components
ms.assetid: b694d21f-9919-402d-9192-666c6449b0b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 94d78872570103d3df7e1cb96aecb144fafe4257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721639"
---
# <a name="developing-a-custom-transformation-component-with-synchronous-outputs"></a><span data-ttu-id="e6471-102">Sviluppo di un componente di trasformazione personalizzato con output sincroni</span><span class="sxs-lookup"><span data-stu-id="e6471-102">Developing a Custom Transformation Component with Synchronous Outputs</span></span>
  <span data-ttu-id="e6471-103">I componenti di trasformazione con output sincroni ricevono righe dai componenti a monte, quindi leggono o modificano i valori nelle colonne di queste righe mentre le passano ai componenti a valle.</span><span class="sxs-lookup"><span data-stu-id="e6471-103">Transformation components with synchronous outputs receive rows from upstream components, and read or modify the values in the columns of these rows as they pass the rows to downstream components.</span></span> <span data-ttu-id="e6471-104">Possono anche definire colonne di output aggiuntive derivate dalle colonne fornite dai componenti a monte, ma non aggiungono righe al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="e6471-104">They may also define additional output columns that are derived from the columns provided by upstream components, but they do not add rows to the data flow.</span></span> <span data-ttu-id="e6471-105">Per altre informazioni sulla differenza tra componenti sincroni e asincroni, vedere [Informazioni sulle trasformazioni sincrone e asincrone](../understanding-synchronous-and-asynchronous-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="e6471-105">For more information about the difference between synchronous and asynchronous components, see [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md).</span></span>  
  
 <span data-ttu-id="e6471-106">Questo tipo di componente è indicato per attività in cui i dati vengono modificati in linea quando vengono forniti al componente e in cui il componente non deve necessariamente vedere tutte le righe prima di elaborarle.</span><span class="sxs-lookup"><span data-stu-id="e6471-106">This kind of component is suited for tasks where the data is modified inline as it is provided to the component and where the component does not have to see all the rows before processing them.</span></span> <span data-ttu-id="e6471-107">Si tratta del componente più facile da sviluppare, perché le trasformazioni con output sincroni solitamente non si connettono a origini dati esterne, non gestiscono colonne di metadati esterne né aggiungono righe ai buffer di output.</span><span class="sxs-lookup"><span data-stu-id="e6471-107">It is the easiest component to develop because transformations with synchronous outputs typically do not connect to external data sources, manage external metadata columns, or add rows to output buffers.</span></span>  
  
 <span data-ttu-id="e6471-108">La creazione di un componente di trasformazione con output sincroni richiede l'aggiunta di un oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> che conterrà le colonne a monte selezionate per il componente e di un oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> che può contenere colonne derivate create dal componente.</span><span class="sxs-lookup"><span data-stu-id="e6471-108">Creating a transformation component with synchronous outputs involves adding an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> that will contain the upstream columns selected for the component, and a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object that may contain derived columns created by the component.</span></span> <span data-ttu-id="e6471-109">Include anche l'implementazione dei metodi della fase di progettazione e la specifica di codice che legge o modifica le colonne nelle righe del buffer in ingresso durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e6471-109">It also includes implementing the design-time methods, and providing code that reads or modifies the columns in the incoming buffer rows during execution.</span></span>  
  
 <span data-ttu-id="e6471-110">In questa sezione vengono fornite le informazioni necessarie per implementare un componente di trasformazione personalizzato, con esempi di codice che consentono di comprenderne meglio i concetti.</span><span class="sxs-lookup"><span data-stu-id="e6471-110">This section provides the information that is required to implement a custom transformation component, and provides code examples to help you better understand the concepts.</span></span>  
  
## <a name="design-time"></a><span data-ttu-id="e6471-111">Fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="e6471-111">Design Time</span></span>  
 <span data-ttu-id="e6471-112">Il codice della fase di progettazione per questo componente richiede la creazione degli input e degli output, l'aggiunta di eventuali colonne di output aggiuntive generate dal componente e la convalida della configurazione del componente.</span><span class="sxs-lookup"><span data-stu-id="e6471-112">The design-time code for this component involves creating the inputs and outputs, adding any additional output columns that the component generates, and validating the configuration of the component.</span></span>  
  
### <a name="creating-the-component"></a><span data-ttu-id="e6471-113">Creazione del componente</span><span class="sxs-lookup"><span data-stu-id="e6471-113">Creating the Component</span></span>  
 <span data-ttu-id="e6471-114">Gli input, gli output e le proprietà personalizzate del componente vengono in genere creati durante il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="e6471-114">The inputs, outputs, and custom properties of the component are typically created during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="e6471-115">Sono disponibili due modi per aggiungere l'input e l'output di un componente di trasformazione con output sincroni.</span><span class="sxs-lookup"><span data-stu-id="e6471-115">There are two ways that you can add the input and the output of a transformation component with synchronous outputs.</span></span> <span data-ttu-id="e6471-116">È possibile utilizzare l'implementazione della classe di base del metodo e quindi modificare l'input e output predefiniti creati oppure aggiungere manualmente l'input e l'output in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="e6471-116">You can use the base class implementation of the method and then modify the default input and output that it creates, or you can explicitly add the input and output yourself.</span></span>  
  
 <span data-ttu-id="e6471-117">Nell'esempio di codice seguente è illustrata un'implementazione di <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> che aggiunge in modo esplicito gli oggetti di input e di output.</span><span class="sxs-lookup"><span data-stu-id="e6471-117">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that explicitly adds the input and output objects.</span></span> <span data-ttu-id="e6471-118">In un commento è inclusa la chiamata alla classe di base che consente di ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="e6471-118">The call to the base class that would accomplish the same thing is included in a comment.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsPipelineComponent(DisplayName = "SynchronousComponent", ComponentType = ComponentType.Transform)]  
    public class SyncComponent : PipelineComponent  
    {  
  
        public override void ProvideComponentProperties()  
        {  
            // Add the input.  
            IDTSInput100 input = ComponentMetaData.InputCollection.New();  
            input.Name = "Input";  
  
            // Add the output.  
            IDTSOutput100 output = ComponentMetaData.OutputCollection.New();  
            output.Name = "Output";  
            output.SynchronousInputID = input.ID;  
  
            // Alternatively, you can let the base class add the input and output  
            // and set the SynchronousInputID of the output to the ID of the input.  
            // base.ProvideComponentProperties();  
        }  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsPipelineComponent(DisplayName:="SynchronousComponent", ComponentType:=ComponentType.Transform)> _  
Public Class SyncComponent  
    Inherits PipelineComponent  
  
    Public Overrides Sub ProvideComponentProperties()  
  
        ' Add the input.  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New()  
        input.Name = "Input"  
  
        ' Add the output.  
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New()  
        output.Name = "Output"  
        output.SynchronousInputID = Input.ID  
  
        ' Alternatively, you can let the base class add the input and output  
        ' and set the SynchronousInputID of the output to the ID of the input.  
        ' base.ProvideComponentProperties();  
  
    End Sub  
  
End Class  
```  
  
### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="e6471-119">Creazione e configurazione di colonne di output</span><span class="sxs-lookup"><span data-stu-id="e6471-119">Creating and Configuring Output Columns</span></span>  
 <span data-ttu-id="e6471-120">Anche se i componenti di trasformazione con output sincroni non aggiungono righe ai buffer, possono aggiungere colonne di output aggiuntive all'output.</span><span class="sxs-lookup"><span data-stu-id="e6471-120">Although transformation components with synchronous outputs do not add rows to buffers, they may add extra output columns to their output.</span></span> <span data-ttu-id="e6471-121">In genere, quando un componente aggiunge una colonna di output, i relativi valori vengono derivati in fase di esecuzione dai dati contenuti in una o più colonne fornite al componente da un componente a monte.</span><span class="sxs-lookup"><span data-stu-id="e6471-121">Typically, when a component adds an output column, the values for the new output column are derived at run time from the data that is contained in one or more of the columns provided to the component by an upstream component.</span></span>  
  
 <span data-ttu-id="e6471-122">Dopo la creazione di una colonna di output, è necessario impostare le relative proprietà del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e6471-122">After an output column has been created, its data type properties must be set.</span></span> <span data-ttu-id="e6471-123">L'impostazione delle proprietà del tipo di dati di una colonna di output richiede una gestione speciale e viene eseguita chiamando il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="e6471-123">Setting the data type properties of an output column requires special handling and is performed by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A> method.</span></span> <span data-ttu-id="e6471-124">Questo metodo è necessario perché le proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> sono singolarmente di sola lettura, in quanto ognuna dipende dalle impostazioni dell'altra.</span><span class="sxs-lookup"><span data-stu-id="e6471-124">This method is required because the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> properties are individually read-only, because each depends on the settings of the other.</span></span> <span data-ttu-id="e6471-125">Questo metodo garantisce che i valori delle proprietà siano impostati in modo coerente e l'attività Flusso di dati verifica se sono stati impostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="e6471-125">This method guarantees that the values of the properties are set consistently, and the data flow task validates that they are set correctly.</span></span>  
  
 <span data-ttu-id="e6471-126">L'oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> della colonna determina i valori impostati per le altre proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6471-126">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> of the column determines the values that are set for the other properties.</span></span> <span data-ttu-id="e6471-127">Nella tabella seguente sono illustrati i requisiti delle proprietà dipendenti per ogni oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="e6471-127">The following table shows the requirements on the dependent properties for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span></span> <span data-ttu-id="e6471-128">Le proprietà dipendenti dei tipi di dati non elencati sono impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="e6471-128">The data types not listed have their dependent properties set to zero.</span></span>  
  
|<span data-ttu-id="e6471-129">DataType</span><span class="sxs-lookup"><span data-stu-id="e6471-129">DataType</span></span>|<span data-ttu-id="e6471-130">Length</span><span class="sxs-lookup"><span data-stu-id="e6471-130">Length</span></span>|<span data-ttu-id="e6471-131">Scalabilità</span><span class="sxs-lookup"><span data-stu-id="e6471-131">Scale</span></span>|<span data-ttu-id="e6471-132">Precision</span><span class="sxs-lookup"><span data-stu-id="e6471-132">Precision</span></span>|<span data-ttu-id="e6471-133">CodePage</span><span class="sxs-lookup"><span data-stu-id="e6471-133">CodePage</span></span>|  
|--------------|------------|-----------|---------------|--------------|  
|<span data-ttu-id="e6471-134">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="e6471-134">DT_DECIMAL</span></span>|<span data-ttu-id="e6471-135">0</span><span class="sxs-lookup"><span data-stu-id="e6471-135">0</span></span>|<span data-ttu-id="e6471-136">Maggiore di 0 e minore o uguale a 28.</span><span class="sxs-lookup"><span data-stu-id="e6471-136">Greater than 0 and less than or equal to 28.</span></span>|<span data-ttu-id="e6471-137">0</span><span class="sxs-lookup"><span data-stu-id="e6471-137">0</span></span>|<span data-ttu-id="e6471-138">0</span><span class="sxs-lookup"><span data-stu-id="e6471-138">0</span></span>|  
|<span data-ttu-id="e6471-139">DT_CY</span><span class="sxs-lookup"><span data-stu-id="e6471-139">DT_CY</span></span>|<span data-ttu-id="e6471-140">0</span><span class="sxs-lookup"><span data-stu-id="e6471-140">0</span></span>|<span data-ttu-id="e6471-141">0</span><span class="sxs-lookup"><span data-stu-id="e6471-141">0</span></span>|<span data-ttu-id="e6471-142">0</span><span class="sxs-lookup"><span data-stu-id="e6471-142">0</span></span>|<span data-ttu-id="e6471-143">0</span><span class="sxs-lookup"><span data-stu-id="e6471-143">0</span></span>|  
|<span data-ttu-id="e6471-144">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="e6471-144">DT_NUMERIC</span></span>|<span data-ttu-id="e6471-145">0</span><span class="sxs-lookup"><span data-stu-id="e6471-145">0</span></span>|<span data-ttu-id="e6471-146">Maggiore di 0 e minore o uguale a 28, nonché minore di Precision.</span><span class="sxs-lookup"><span data-stu-id="e6471-146">Greater than 0 and less than or equal to 28, and less than Precision.</span></span>|<span data-ttu-id="e6471-147">Maggiore o uguale a 1 e minore o uguale a 38.</span><span class="sxs-lookup"><span data-stu-id="e6471-147">Greater than or equal to 1 and less than or equal to 38.</span></span>|<span data-ttu-id="e6471-148">0</span><span class="sxs-lookup"><span data-stu-id="e6471-148">0</span></span>|  
|<span data-ttu-id="e6471-149">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="e6471-149">DT_BYTES</span></span>|<span data-ttu-id="e6471-150">Maggiore di 0.</span><span class="sxs-lookup"><span data-stu-id="e6471-150">Greater than 0.</span></span>|<span data-ttu-id="e6471-151">0</span><span class="sxs-lookup"><span data-stu-id="e6471-151">0</span></span>|<span data-ttu-id="e6471-152">0</span><span class="sxs-lookup"><span data-stu-id="e6471-152">0</span></span>|<span data-ttu-id="e6471-153">0</span><span class="sxs-lookup"><span data-stu-id="e6471-153">0</span></span>|  
|<span data-ttu-id="e6471-154">DT_STR</span><span class="sxs-lookup"><span data-stu-id="e6471-154">DT_STR</span></span>|<span data-ttu-id="e6471-155">Maggiore di 0 e minore di 8000.</span><span class="sxs-lookup"><span data-stu-id="e6471-155">Greater than 0 and less than 8000.</span></span>|<span data-ttu-id="e6471-156">0</span><span class="sxs-lookup"><span data-stu-id="e6471-156">0</span></span>|<span data-ttu-id="e6471-157">0</span><span class="sxs-lookup"><span data-stu-id="e6471-157">0</span></span>|<span data-ttu-id="e6471-158">Diverso da 0 e tabella codici valida.</span><span class="sxs-lookup"><span data-stu-id="e6471-158">Not 0, and a valid code page.</span></span>|  
|<span data-ttu-id="e6471-159">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="e6471-159">DT_WSTR</span></span>|<span data-ttu-id="e6471-160">Maggiore di 0 e minore di 4000.</span><span class="sxs-lookup"><span data-stu-id="e6471-160">Greater than 0 and less than 4000.</span></span>|<span data-ttu-id="e6471-161">0</span><span class="sxs-lookup"><span data-stu-id="e6471-161">0</span></span>|<span data-ttu-id="e6471-162">0</span><span class="sxs-lookup"><span data-stu-id="e6471-162">0</span></span>|<span data-ttu-id="e6471-163">0</span><span class="sxs-lookup"><span data-stu-id="e6471-163">0</span></span>|  
  
 <span data-ttu-id="e6471-164">Poiché le restrizioni sulle proprietà del tipo di dati sono basate sul tipo di dati della colonna di output, è necessario scegliere il tipo di dati di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] corretto quando si utilizzano tipi gestiti.</span><span class="sxs-lookup"><span data-stu-id="e6471-164">Because the restrictions on the data type properties are based on the data type of the output column, you must choose the correct [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type when you work with managed types.</span></span> <span data-ttu-id="e6471-165">La classe di base fornisce tre metodi di supporto, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, per assistere gli sviluppatori di componenti gestiti nella selezione di un tipo di dati di [!INCLUDE[ssIS](../../includes/ssis-md.md)] dato un tipo gestito.</span><span class="sxs-lookup"><span data-stu-id="e6471-165">The base class provides three helper methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A> that assist managed component developers in selecting an [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type given a managed type.</span></span> <span data-ttu-id="e6471-166">Questi metodi convertono i tipi di dati gestiti nei tipi di dati di [!INCLUDE[ssIS](../../includes/ssis-md.md)] e viceversa.</span><span class="sxs-lookup"><span data-stu-id="e6471-166">These methods convert managed data types to [!INCLUDE[ssIS](../../includes/ssis-md.md)] data types, and vice versa.</span></span>  
  
## <a name="run-time"></a><span data-ttu-id="e6471-167">Fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="e6471-167">Run Time</span></span>  
 <span data-ttu-id="e6471-168">Generalmente, l'implementazione della parte runtime del componente è suddivisa in due attività: individuazione delle colonne di input e output del componente nel buffer e lettura o scrittura dei valori di tali colonne nelle righe del buffer in ingresso.</span><span class="sxs-lookup"><span data-stu-id="e6471-168">Generally, the implementation of the run-time part of the component is categorized into two tasks-locating the input and output columns of the component in the buffer, and reading or writing the values of these columns in the incoming buffer rows.</span></span>  
  
### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="e6471-169">Individuazione di colonne nel buffer</span><span class="sxs-lookup"><span data-stu-id="e6471-169">Locating Columns in the Buffer</span></span>  
 <span data-ttu-id="e6471-170">Il numero di colonne nei buffer forniti a un componente durante l'esecuzione supera in genere il numero di colonne presenti nelle raccolte di input o output del componente,</span><span class="sxs-lookup"><span data-stu-id="e6471-170">The number of columns in the buffers that are provided to a component during execution will likely exceed the number of columns in the input or output collections of the component.</span></span> <span data-ttu-id="e6471-171">perché ogni buffer contiene tutte le colonne di output definite nei componenti in un flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="e6471-171">This is because each buffer contains all the output columns defined in the components in a data flow.</span></span> <span data-ttu-id="e6471-172">Per assicurarsi che le colonne del buffer corrispondano correttamente alle colonne dell'input o dell'output, gli sviluppatori di componenti devono utilizzare il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> di <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="e6471-172">To ensure that the buffer columns are correctly matched to the columns of the input or output, component developers must use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="e6471-173">Questo metodo individua una colonna nel buffer specificato in base al relativo ID di derivazione.</span><span class="sxs-lookup"><span data-stu-id="e6471-173">This method locates a column in the specified buffer by its lineage ID.</span></span> <span data-ttu-id="e6471-174">In genere, le colonne vengono individuate durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> perché si tratta del primo metodo di runtime in cui la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="e6471-174">Typically columns are located during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> because this is the first run-time method where the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property becomes available.</span></span>  
  
 <span data-ttu-id="e6471-175">Nell'esempio di codice seguente è illustrato un componente che individua gli indici delle colonne nella propria raccolta di colonne di input e output durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="e6471-175">The following code example shows a component that locates indexes of the columns in its input and output column collection during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span></span> <span data-ttu-id="e6471-176">Gli indici delle colonne vengono archiviati in una matrice di valori integer e il componente può accedervi durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="e6471-176">The column indexes are stored in an integer array, and can be accessed by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
```csharp  
int []inputColumns;  
int []outputColumns;  
  
public override void PreExecute()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];  
  
    inputColumns = new int[input.InputColumnCollection.Count];  
    outputColumns = new int[output.OutputColumnCollection.Count];  
  
    for(int col=0; col < input.InputColumnCollection.Count; col++)  
    {  
        IDTSInputColumn100 inputColumn = input.InputColumnCollection[col];  
        inputColumns[col] = BufferManager.FindColumnByLineageID(input.Buffer, inputColumn.LineageID);  
    }  
  
    for(int col=0; col < output.OutputColumnCollection.Count; col++)  
    {  
        IDTSOutputColumn100 outputColumn = output.OutputColumnCollection[col];  
        outputColumns[col] = BufferManager.FindColumnByLineageID(input.Buffer, outputColumn.LineageID);  
    }  
  
}  
```  
  
```vb  
Public Overrides Sub PreExecute()  
  
    Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)  
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)  
  
    ReDim inputColumns(input.InputColumnCollection.Count)  
    ReDim outputColumns(output.OutputColumnCollection.Count)  
  
    For col As Integer = 0 To input.InputColumnCollection.Count  
  
        Dim inputColumn As IDTSInputColumn100 = input.InputColumnCollection(col)  
        inputColumns(col) = BufferManager.FindColumnByLineageID(input.Buffer, inputColumn.LineageID)  
    Next  
  
    For col As Integer = 0 To output.OutputColumnCollection.Count  
  
        Dim outputColumn As IDTSOutputColumn100 = output.OutputColumnCollection(col)  
        outputColumns(col) = BufferManager.FindColumnByLineageID(input.Buffer, outputColumn.LineageID)  
    Next  
  
End Sub  
```  
  
### <a name="processing-rows"></a><span data-ttu-id="e6471-177">Elaborazione di righe</span><span class="sxs-lookup"><span data-stu-id="e6471-177">Processing Rows</span></span>  
 <span data-ttu-id="e6471-178">I componenti ricevono oggetti <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> che contengono righe e colonne nel metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="e6471-178">Components receive <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects that contain rows and columns in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span> <span data-ttu-id="e6471-179">Durante questo metodo vengono scorse le righe nel buffer e vengono lette e modificate le colonne identificate durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> .</span><span class="sxs-lookup"><span data-stu-id="e6471-179">During this method the rows in the buffer are iterated, and the columns identified during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> are read and modified.</span></span> <span data-ttu-id="e6471-180">Il metodo viene chiamato ripetutamente dall'attività Flusso di dati finché non vengono più fornite righe dal componente a monte.</span><span class="sxs-lookup"><span data-stu-id="e6471-180">The method is called repeatedly by the data flow task until no more rows are provided from the upstream component.</span></span>  
  
 <span data-ttu-id="e6471-181">Una singola colonna nel buffer viene letta o scritta tramite il metodo di accesso dell'indicizzatore di matrici oppure utilizzando uno dei metodi `Get` o `Set`.</span><span class="sxs-lookup"><span data-stu-id="e6471-181">An individual column in the buffer is read or written by using the array indexer access method, or by using one of the `Get` or `Set` methods.</span></span> <span data-ttu-id="e6471-182">I metodi `Get` e `Set` sono più efficienti e devono essere utilizzati quando il tipo di dati della colonna nel buffer è noto.</span><span class="sxs-lookup"><span data-stu-id="e6471-182">The `Get` and `Set` methods are more efficient and should be used when the data type of the column in the buffer is known.</span></span>  
  
 <span data-ttu-id="e6471-183">Nell'esempio di codice seguente è illustrata un'implementazione del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> che elabora le righe in ingresso.</span><span class="sxs-lookup"><span data-stu-id="e6471-183">The following code example shows an implementation of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method that processes incoming rows.</span></span>  
  
```csharp  
public override void ProcessInput( int InputID, PipelineBuffer buffer)  
{  
       while( buffer.NextRow())  
       {  
            for(int x=0; x < inputColumns.Length;x++)  
            {  
                if(!buffer.IsNull(inputColumns[x]))  
                {  
                    object columnData = buffer[inputColumns[x]];  
                    // TODO: Modify the column data.  
                    buffer[inputColumns[x]] = columnData;  
                }  
            }  
  
      }  
}  
```  
  
```vb  
Public Overrides Sub ProcessInput(ByVal InputID As Integer, ByVal buffer As PipelineBuffer)  
  
        While (buffer.NextRow())  
  
            For x As Integer = 0 To inputColumns.Length  
  
                if buffer.IsNull(inputColumns(x)) = false then  
  
                    Dim columnData As Object = buffer(inputColumns(x))  
                    ' TODO: Modify the column data.  
                    buffer(inputColumns(x)) = columnData  
  
                End If  
            Next  
  
        End While  
End Sub  
```  
  
## <a name="sample"></a><span data-ttu-id="e6471-184">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6471-184">Sample</span></span>  
 <span data-ttu-id="e6471-185">Nell'esempio seguente è illustrato un componente di trasformazione semplice con output sincroni che converte i valori di tutte le colonne di tipo stringa in lettere maiuscole.</span><span class="sxs-lookup"><span data-stu-id="e6471-185">The following sample shows a simple transformation component with synchronous outputs that converts the values of all string columns to uppercase.</span></span> <span data-ttu-id="e6471-186">Nell'esempio non vengono dimostrati tutti i metodi e le funzionalità descritti nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="e6471-186">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="e6471-187">Vengono descritti i metodi importanti di cui ogni componente di trasformazione personalizzato con output sincroni deve eseguire l'override, ma non è incluso codice per la convalida in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e6471-187">It demonstrates the important methods that every custom transformation component with synchronous outputs must override, but does not contain code for design-time validation.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
using Microsoft.SqlServer.Dts.Runtime.Wrapper;  
  
namespace Uppercase  
{  
  [DtsPipelineComponent(DisplayName = "Uppercase")]  
  public class Uppercase : PipelineComponent  
  {  
    ArrayList m_ColumnIndexList = new ArrayList();  
  
    public override void ProvideComponentProperties()  
    {  
      base.ProvideComponentProperties();  
      ComponentMetaData.InputCollection[0].Name = "Uppercase Input";  
      ComponentMetaData.OutputCollection[0].Name = "Uppercase Output";  
    }  
  
    public override void PreExecute()  
    {  
      IDTSInput100 input = ComponentMetaData.InputCollection[0];  
      IDTSInputColumnCollection100 inputColumns = input.InputColumnCollection;  
  
      foreach (IDTSInputColumn100 column in inputColumns)  
      {  
        if (column.DataType == DataType.DT_STR || column.DataType == DataType.DT_WSTR)  
        {  
          m_ColumnIndexList.Add((int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID));  
        }  
      }  
    }  
  
    public override void ProcessInput(int inputID, PipelineBuffer buffer)  
    {  
      while (buffer.NextRow())  
      {  
        foreach (int columnIndex in m_ColumnIndexList)  
        {  
          string str = buffer.GetString(columnIndex);  
          buffer.SetString(columnIndex, str.ToUpper());  
        }  
      }  
    }  
  }  
}  
```  
  
```vb  
Imports System   
Imports System.Collections   
Imports Microsoft.SqlServer.Dts.Pipeline   
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper   
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper   
Namespace Uppercase   
  
 <DtsPipelineComponent(DisplayName="Uppercase")> _   
 Public Class Uppercase   
 Inherits PipelineComponent   
   Private m_ColumnIndexList As ArrayList = New ArrayList   
  
   Public  Overrides Sub ProvideComponentProperties()   
     MyBase.ProvideComponentProperties   
     ComponentMetaData.InputCollection(0).Name = "Uppercase Input"   
     ComponentMetaData.OutputCollection(0).Name = "Uppercase Output"   
   End Sub   
  
   Public  Overrides Sub PreExecute()   
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)   
     Dim inputColumns As IDTSInputColumnCollection100 = input.InputColumnCollection   
     For Each column As IDTSInputColumn100 In inputColumns   
       If column.DataType = DataType.DT_STR OrElse column.DataType = DataType.DT_WSTR Then   
         m_ColumnIndexList.Add(CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer))   
       End If   
     Next   
   End Sub   
  
   Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)   
     While buffer.NextRow   
       For Each columnIndex As Integer In m_ColumnIndexList   
         Dim str As String = buffer.GetString(columnIndex)   
         buffer.SetString(columnIndex, str.ToUpper)   
       Next   
     End While   
   End Sub   
 End Class   
End Namespace  
```  
  
<span data-ttu-id="e6471-188">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e6471-188">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e6471-189">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="e6471-189">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e6471-190">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="e6471-190">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e6471-191">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e6471-191">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6471-192">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6471-192">See Also</span></span>  
 <span data-ttu-id="e6471-193">[Sviluppo di un componente di trasformazione personalizzato con output asincroni](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md) </span><span class="sxs-lookup"><span data-stu-id="e6471-193">[Developing a Custom Transformation Component with Asynchronous Outputs](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md) </span></span>  
 <span data-ttu-id="e6471-194">[Informazioni sulle trasformazioni sincrone e asincrone](../understanding-synchronous-and-asynchronous-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="e6471-194">[Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md) </span></span>  
 [<span data-ttu-id="e6471-195">Creazione di una trasformazione sincrona con il componente script</span><span class="sxs-lookup"><span data-stu-id="e6471-195">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
