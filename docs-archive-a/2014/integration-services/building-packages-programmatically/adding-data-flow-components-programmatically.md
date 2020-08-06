---
title: Aggiunta di componenti flusso di dati a livello di programmazione | Microsoft Docs
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
- data flow task [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: c06065cf-43e5-4b6b-9824-7309d7f5e35e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 807e758e42b738c4b0bf64b1d6f48bc29649ae6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627357"
---
# <a name="adding-data-flow-components-programmatically"></a><span data-ttu-id="9208e-102">Aggiunta di componenti del flusso di dati a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="9208e-102">Adding Data Flow Components Programmatically</span></span>
  <span data-ttu-id="9208e-103">Il primo passaggio per la compilazione di un flusso di dati consiste nell'aggiunta di componenti.</span><span class="sxs-lookup"><span data-stu-id="9208e-103">When you build a data flow, you start by adding components.</span></span> <span data-ttu-id="9208e-104">È quindi necessario configurarli e connetterli per stabilire il flusso di dati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9208e-104">Then you configure those components and connect them together to establish the flow of data at run time.</span></span> <span data-ttu-id="9208e-105">In questa sezione vengono descritti i passaggi per aggiungere un componente all'attività Flusso di dati, creare la relativa istanza della fase di progettazione e quindi configurarlo.</span><span class="sxs-lookup"><span data-stu-id="9208e-105">This section describes adding a component to the data flow task, creating the design-time instance of the component, and then configuring the component.</span></span> <span data-ttu-id="9208e-106">Per informazioni su come connettere i componenti, vedere [Connessione di componenti flusso di dati a livello di programmazione](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="9208e-106">For information about how to connect components, see [Connecting Data Flow Components Programmatically](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
## <a name="adding-a-component"></a><span data-ttu-id="9208e-107">Aggiunta di un componente</span><span class="sxs-lookup"><span data-stu-id="9208e-107">Adding a Component</span></span>  
 <span data-ttu-id="9208e-108">Chiamare il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaDataCollection100.New%2A> della raccolta <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.ComponentMetaDataCollection%2A> per creare un nuovo componente e aggiungerlo all'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="9208e-108">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaDataCollection100.New%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.ComponentMetaDataCollection%2A> collection to create a new component and add it to the data flow task.</span></span> <span data-ttu-id="9208e-109">Questo metodo restituisce l'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> del componente.</span><span class="sxs-lookup"><span data-stu-id="9208e-109">This method returns the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface of the component.</span></span> <span data-ttu-id="9208e-110">Tuttavia, a questo punto, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> non contiene informazioni specifiche di un determinato componente.</span><span class="sxs-lookup"><span data-stu-id="9208e-110">However, at this point, the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> does not contain information specific to any one component.</span></span> <span data-ttu-id="9208e-111">Impostare la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> per identificare il tipo di componente.</span><span class="sxs-lookup"><span data-stu-id="9208e-111">Set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property to identify the type of component.</span></span> <span data-ttu-id="9208e-112">L'attività Flusso di dati utilizza il valore di questa proprietà per creare un'istanza del componente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9208e-112">The data flow task uses the value of this property to create an instance of the component at run time.</span></span>  
  
 <span data-ttu-id="9208e-113">Il valore specificato nella proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> può essere il CLSID, il PROGID o la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> del componente.</span><span class="sxs-lookup"><span data-stu-id="9208e-113">The value specified in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property can be the CLSID, PROGID, or <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> property of the component.</span></span> <span data-ttu-id="9208e-114">Il CLSID viene in genere visualizzato nella finestra delle proprietà come valore della proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> del componente.</span><span class="sxs-lookup"><span data-stu-id="9208e-114">The CLSID is normally displayed in the Properties window as the value of the component's <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property.</span></span> <span data-ttu-id="9208e-115">Per informazioni su come ottenere questa e altre proprietà dei componenti disponibili, vedere [Individuazione dei componenti del flusso di dati a livello di programmazione](../building-packages-programmatically/discovering-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="9208e-115">For information about obtaining this property and other properties of available components, see [Discovering Data Flow Components Programmatically](../building-packages-programmatically/discovering-data-flow-components-programmatically.md).</span></span>  
  
## <a name="adding-a-managed-component"></a><span data-ttu-id="9208e-116">Aggiunta di un componente gestito</span><span class="sxs-lookup"><span data-stu-id="9208e-116">Adding a Managed Component</span></span>  
 <span data-ttu-id="9208e-117">Non è possibile utilizzare il CLSID o il PROGID per aggiungere uno dei componenti gestiti al flusso di dati, perché questi valori puntano a un wrapper e non al componente stesso.</span><span class="sxs-lookup"><span data-stu-id="9208e-117">You cannot use the CLSID or PROGID to add one the managed data flow components to the data flow, because these values point to a wrapper and not to the component itself.</span></span> <span data-ttu-id="9208e-118">In alternativa, è possibile utilizzare la proprietà `CreationName` o `AssemblyQualifiedName`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9208e-118">Instead you can use the `CreationName` property or the `AssemblyQualifiedName` property as shown in the following sample.</span></span>  
  
 <span data-ttu-id="9208e-119">Se si intende utilizzare la proprietà `AssemblyQualifiedName`, è necessario aggiungere un riferimento nel progetto di [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] all'assembly che contiene il componente gestito.</span><span class="sxs-lookup"><span data-stu-id="9208e-119">If you intend to use the `AssemblyQualifiedName` property, then you must add a reference in your [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] project to the assembly that contains the managed component.</span></span> <span data-ttu-id="9208e-120">Questi assembly non sono visualizzati nella scheda .NET della finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="9208e-120">These assemblies are not listed on the .NET tab of the **Add Reference** dialog box.</span></span> <span data-ttu-id="9208e-121">Normalmente occorre cercare l'assembly nella cartella **C:\Programmi\Microsoft SQL Server\100\DTS\PipelineComponents**.</span><span class="sxs-lookup"><span data-stu-id="9208e-121">Normally you must browse to locate the assembly in the **C:\Program Files\Microsoft SQL Server\100\DTS\PipelineComponents** folder.</span></span>  
  
 <span data-ttu-id="9208e-122">I componenti del flusso di dati gestiti predefiniti includono:</span><span class="sxs-lookup"><span data-stu-id="9208e-122">The built-in managed data flow components include:</span></span>  
  
-   <span data-ttu-id="9208e-123">Origine [!INCLUDE[vstecado](../../includes/vstecado-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9208e-123">[!INCLUDE[vstecado](../../includes/vstecado-md.md)] Source</span></span>  
  
-   <span data-ttu-id="9208e-124">Origine XML</span><span class="sxs-lookup"><span data-stu-id="9208e-124">XML Source</span></span>  
  
-   <span data-ttu-id="9208e-125">DataReader - destinazione</span><span class="sxs-lookup"><span data-stu-id="9208e-125">DataReader Destination</span></span>  
  
-   <span data-ttu-id="9208e-126">Destinazione[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact</span><span class="sxs-lookup"><span data-stu-id="9208e-126">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact Destination</span></span>  
  
-   <span data-ttu-id="9208e-127">Componente script</span><span class="sxs-lookup"><span data-stu-id="9208e-127">Script Component</span></span>  
  
 <span data-ttu-id="9208e-128">Nell'esempio di codice seguente sono illustrate entrambe le modalità di aggiunta di componenti gestiti al flusso di dati:</span><span class="sxs-lookup"><span data-stu-id="9208e-128">The following code sample shows both ways of adding a managed component to the data flow:</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Microsoft.SqlServer.Dts.Runtime.Package package = new Microsoft.SqlServer.Dts.Runtime.Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      Microsoft.SqlServer.Dts.Runtime.TaskHost thMainPipe = (Microsoft.SqlServer.Dts.Runtime.TaskHost)e;  
      MainPipe dataFlowTask = (MainPipe)thMainPipe.InnerObject;  
  
      // The Application object will be used to obtain the CreationName  
      //  of a PipelineComponentInfo from its PipelineComponentInfos collection.  
      Application app = new Application();  
  
      // Add a first ADO NET source to the data flow.  
      //  The CreationName property requires an Application instance.  
      IDTSComponentMetaData100 component1 = dataFlowTask.ComponentMetaDataCollection.New();  
      component1.Name = "DataReader Source";  
      component1.ComponentClassID = app.PipelineComponentInfos["DataReader Source"].CreationName;  
  
      // Add a second ADO NET source to the data flow.  
      //  The AssemblyQualifiedName property requires a reference to the assembly.  
      IDTSComponentMetaData100 component2 = dataFlowTask.ComponentMetaDataCollection.New();  
      component2.Name = "DataReader Source";  
      component2.ComponentClassID = typeof(Microsoft.SqlServer.Dts.Pipeline.DataReaderSourceAdapter).AssemblyQualifiedName;  
    }  
  }  
}  
  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' The Application object will be used to obtain the CreationName  
    '  of a PipelineComponentInfo from its PipelineComponentInfos collection.  
    Dim app As New Application()  
  
    ' Add a first ADO NET source to the data flow.  
    '  The CreationName property requires an Application instance.  
    Dim component1 As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component1.Name = "DataReader Source"  
    component1.ComponentClassID = app.PipelineComponentInfos("DataReader Source").CreationName  
  
    ' Add a second ADO NET source to the data flow.  
    '  The AssemblyQualifiedName property requires a reference to the assembly.  
    Dim component2 As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component2.Name = "DataReader Source"  
    component2.ComponentClassID = _  
      GetType(Microsoft.SqlServer.Dts.Pipeline.DataReaderSourceAdapter).AssemblyQualifiedName  
  
  End Sub  
  
End Module  
```  
  
## <a name="creating-the-design-time-instance-of-the-component"></a><span data-ttu-id="9208e-129">Creazione dell'istanza della fase di progettazione del componente</span><span class="sxs-lookup"><span data-stu-id="9208e-129">Creating the Design-time Instance of the Component</span></span>  
 <span data-ttu-id="9208e-130">Chiamare il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> per creare l'istanza della fase di progettazione del componente identificato dalla proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A>.</span><span class="sxs-lookup"><span data-stu-id="9208e-130">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> method to create the design time instance of the component identified by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property.</span></span> <span data-ttu-id="9208e-131">Questo metodo restituisce l'oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper>, che corrisponde al wrapper gestito per l'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>.</span><span class="sxs-lookup"><span data-stu-id="9208e-131">This method returns the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> object, which is the managed wrapper for the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>  
  
 <span data-ttu-id="9208e-132">Se possibile, modificare un componente utilizzando i metodi dell'istanza della fase di progettazione anziché modificando direttamente i relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="9208e-132">Whenever possible, you should modify a component by using the methods of the design-time instance instead of by modifying the component metadata directly.</span></span> <span data-ttu-id="9208e-133">Anche se alcuni elementi dei metadati devono essere impostati direttamente, ad esempio le connessioni, in genere non è consigliabile eseguire questa operazione perché in questo modo il componente non è più in grado di monitorare e convalidare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="9208e-133">Although there are items in the metadata that you must set directly, such as connections, generally it is inadvisable to modify the metadata directly because you bypass the ability of the component to monitor and validate changes.</span></span>  
  
## <a name="assigning-connections"></a><span data-ttu-id="9208e-134">Assegnazione di connessioni</span><span class="sxs-lookup"><span data-stu-id="9208e-134">Assigning Connections</span></span>  
 <span data-ttu-id="9208e-135">Alcuni componenti, ad esempio il componente Origine OLE DB, richiedono una connessione a dati esterni e utilizzano un oggetto <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> esistente nel pacchetto a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="9208e-135">Some components, such as the OLE DB Source component, require a connection to external data and use an existing <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object in the package for this purpose.</span></span> <span data-ttu-id="9208e-136">La proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnectionCollection100.Count%2A> della raccolta <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> indica il numero di oggetti <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> di runtime richiesti dal componente.</span><span class="sxs-lookup"><span data-stu-id="9208e-136">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnectionCollection100.Count%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection indicates the number of run-time <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects required by the component.</span></span> <span data-ttu-id="9208e-137">Se il conteggio è maggiore di zero, il componente richiede una connessione.</span><span class="sxs-lookup"><span data-stu-id="9208e-137">If the count is greater than zero, the component requires a connection.</span></span> <span data-ttu-id="9208e-138">Assegnare una gestione connessione dal pacchetto al componente specificando le proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.ConnectionManager%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.Name%2A> della prima connessione in <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="9208e-138">Assign a connection manager from the package to the component by specifying the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.ConnectionManager%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.Name%2A> properties of the first connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span> <span data-ttu-id="9208e-139">Si noti che il nome della gestione connessione nella raccolta di connessioni di runtime deve corrispondere al nome della gestione connessione a cui fa riferimento il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9208e-139">Note that the name of the connection manager in the run-time connection collection must match the name of the connection managerreferenced from the package.</span></span>  
  
## <a name="setting-the-values-of-custom-properties"></a><span data-ttu-id="9208e-140">Impostazione dei valori delle proprietà personalizzate</span><span class="sxs-lookup"><span data-stu-id="9208e-140">Setting the Values of Custom Properties</span></span>  
 <span data-ttu-id="9208e-141">Dopo aver creato l'istanza della fase di progettazione del componente, chiamare il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="9208e-141">After creating the design-time instance of the component, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="9208e-142">Questo metodo è simile a un costruttore, in quanto inizializza un componente appena creato definendone le proprietà personalizzate e gli oggetti di input e output.</span><span class="sxs-lookup"><span data-stu-id="9208e-142">This method is similar to a constructor because it initializes a newly created component by creating its custom properties and its input and output objects.</span></span> <span data-ttu-id="9208e-143">Non chiamare <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> più di una volta su un componente, perché il componente potrebbe reimpostarsi e perdere le modifiche apportate in precedenza ai propri metadati.</span><span class="sxs-lookup"><span data-stu-id="9208e-143">Do not call <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> more than one time on a component, because the component may reset itself and lose any modifications previously made to its metadata.</span></span>  
  
 <span data-ttu-id="9208e-144">L'oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.CustomPropertyCollection%2A> del componente contiene una raccolta di oggetti <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> specifici del componente.</span><span class="sxs-lookup"><span data-stu-id="9208e-144">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.CustomPropertyCollection%2A> of the component contains a collection of <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> objects specific to the component.</span></span> <span data-ttu-id="9208e-145">A differenza di altri modelli di programmazione, in cui le proprietà di un oggetto sono sempre visibili sullo stesso, i componenti popolano le loro raccolte di proprietà personalizzate solo quando viene chiamato il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="9208e-145">Unlike other programming models, where the properties of an object are always visible on the object, components only populate their custom property collections when you call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="9208e-146">Dopo aver chiamato il metodo, utilizzare il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.SetComponentProperty%2A> dell'istanza della fase di progettazione del componente per assegnare valori alle relative proprietà personalizzate.</span><span class="sxs-lookup"><span data-stu-id="9208e-146">After you call method, use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.SetComponentProperty%2A> method of the design-time instance of the component to assign values to its custom properties.</span></span> <span data-ttu-id="9208e-147">Questo metodo accetta una coppia nome/valore che identifica la proprietà personalizzata e fornisce il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="9208e-147">This method accepts a name/value pair that identifies the custom property and provides its new value.</span></span>  
  
## <a name="initializing-output-columns"></a><span data-ttu-id="9208e-148">Inizializzazione di colonne di output</span><span class="sxs-lookup"><span data-stu-id="9208e-148">Initializing Output Columns</span></span>  
 <span data-ttu-id="9208e-149">Dopo aver aggiunto un componente all'attività e dopo averlo configurato, inizializzare la raccolta di colonne in <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9208e-149">After you add a component to the task and configure it, initialize the collection of columns in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the object.</span></span> <span data-ttu-id="9208e-150">Questo passaggio è particolarmente importante per i componenti di origine, ma è possibile che non inizializzi le colonne per i componenti di trasformazione e destinazione, in quanto in genere dipendono dalle colonne che ricevono dai componenti a monte.</span><span class="sxs-lookup"><span data-stu-id="9208e-150">This step is especially relevant for source components, but may not initialize the columns for transformation and destination components because they generally depend on the columns that they receive from upstream components.</span></span>  
  
 <span data-ttu-id="9208e-151">Chiamare il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> per inizializzare le colonne negli output di un componente di origine.</span><span class="sxs-lookup"><span data-stu-id="9208e-151">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> method to initialize the columns in the outputs of a source component.</span></span> <span data-ttu-id="9208e-152">Poiché i componenti non si connettono automaticamente alle origini dati esterne, chiamare il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.AcquireConnections%2A> prima di chiamare <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> per fornire al componente l'accesso all'origine dati esterna e la possibilità di popolare le proprie colonne di metadati.</span><span class="sxs-lookup"><span data-stu-id="9208e-152">Because components do not automatically connect to external data sources, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.AcquireConnections%2A> method before calling <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> to provide the component access to its external data source and the ability to populate its column metadata.</span></span> <span data-ttu-id="9208e-153">Infine, chiamare il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReleaseConnections%2A> per rilasciare la connessione.</span><span class="sxs-lookup"><span data-stu-id="9208e-153">Finally, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReleaseConnections%2A> method to release the connection.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="9208e-154">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="9208e-154">Next Step</span></span>  
 <span data-ttu-id="9208e-155">Dopo l'aggiunta e la configurazione del componente, il passaggio successivo consiste nella creazione di percorsi tra componenti, come descritto nell'argomento [Creazione di un percorso tra due componenti](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="9208e-155">After adding and configuring the component, the next step is to create paths between components, which is discussed in the topic, [Creating a Path Between Two Components](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="9208e-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="9208e-156">Sample</span></span>  
 <span data-ttu-id="9208e-157">Nell'esempio di codice seguente viene aggiunto il componente Origine OLE DB all'attività Flusso di dati, viene creata un'istanza della fase di progettazione del componente e vengono configurate le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="9208e-157">The following code sample adds the OLE DB Source component to a data flow task, creates a design-time instance of the component, and configures the component's properties.</span></span> <span data-ttu-id="9208e-158">Per questo esempio è richiesto un riferimento aggiuntivo all'assembly Microsoft.SqlServer.DTSRuntimeWrap.</span><span class="sxs-lookup"><span data-stu-id="9208e-158">This example requires an additional reference to the assembly Microsoft.SqlServer.DTSRuntimeWrap.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Runtime.Wrapper;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Runtime.Package package = new Runtime.Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      Runtime.TaskHost thMainPipe = e as Runtime.TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;  
  
      // Add an OLEDB connection manager to the package.  
      ConnectionManager cm = package.Connections.Add("OLEDB");  
      cm.Name = "OLEDB ConnectionManager";  
      cm.ConnectionString = "Data Source=(local);" +   
        "Initial Catalog=AdventureWorks;Provider=SQLOLEDB.1;" +   
        "Integrated Security=SSPI;"  
  
      // Add an OLE DB source to the data flow.  
      IDTSComponentMetaData100 component =   
        dataFlowTask.ComponentMetaDataCollection.New();  
      component.Name = "OLEDBSource";  
      component.ComponentClassID = "DTSAdapter.OleDbSource.1";  
      // You can also use the CLSID of the component instead of the PROGID.  
      //component.ComponentClassID = "{2C0A8BE5-1EDC-4353-A0EF-B778599C65A0}";  
  
      // Get the design time instance of the component.  
      CManagedComponentWrapper instance = component.Instantiate();  
  
      // Initialize the component  
      instance.ProvideComponentProperties();  
  
      // Specify the connection manager.  
      if (component.RuntimeConnectionCollection.Count > 0)  
      {  
        component.RuntimeConnectionCollection[0].ConnectionManager =   
          DtsConvert.GetExtendedInterface(package.Connections[0]);  
        component.RuntimeConnectionCollection[0].ConnectionManagerID =   
          package.Connections[0].ID;      }  
  
      // Set the custom properties.  
      instance.SetComponentProperty("AccessMode", 2);  
      instance.SetComponentProperty("SqlCommand",   
        "Select * from Production.Product");  
  
      // Reinitialize the metadata.  
      instance.AcquireConnections(null);  
      instance.ReinitializeMetaData();  
      instance.ReleaseConnections();  
  
      // Add other components to the data flow and connect them.  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' Add an OLEDB connection manager to the package.  
    Dim cm As ConnectionManager = package.Connections.Add("OLEDB")  
    cm.Name = "OLEDB ConnectionManager"  
    cm.ConnectionString = "Data Source=(local);" & _  
      "Initial Catalog=AdventureWorks;Provider=SQLOLEDB.1;" & _  
      "Integrated Security=SSPI;"  
  
    ' Add an OLE DB source to the data flow.  
    Dim component As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component.Name = "OLEDBSource"  
    component.ComponentClassID = "DTSAdapter.OleDbSource.1"  
    ' You can also use the CLSID of the component instead of the PROGID.  
    'component.ComponentClassID = "{2C0A8BE5-1EDC-4353-A0EF-B778599C65A0}";  
  
    ' Get the design time instance of the component.  
    Dim instance As CManagedComponentWrapper = component.Instantiate()  
  
    ' Initialize the component.  
    instance.ProvideComponentProperties()  
  
    ' Specify the connection manager.  
    If component.RuntimeConnectionCollection.Count > 0 Then  
      component.RuntimeConnectionCollection(0).ConnectionManager = _  
        DtsConvert.GetExtendedInterface(package.Connections(0))  
      component.RuntimeConnectionCollection(0).ConnectionManagerID = _  
        package.Connections(0).ID  
    End If  
  
    ' Set the custom properties.  
    instance.SetComponentProperty("AccessMode", 2)  
    instance.SetComponentProperty("SqlCommand", _  
      "Select * from Production.Product")  
  
    ' Reinitialize the metadata.  
    instance.AcquireConnections(vbNull)  
    instance.ReinitializeMetaData()  
    instance.ReleaseConnections()  
  
    ' Add other components to the data flow and connect them.  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="9208e-159">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="9208e-159">External Resources</span></span>  
 <span data-ttu-id="9208e-160">Intervento nel blog sull'[aggiornamento di EzAPI per SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223) sul sito Web blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="9208e-160">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="9208e-161">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="9208e-161">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="9208e-162">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="9208e-162">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="9208e-163">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="9208e-163">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="9208e-164">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="9208e-164">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9208e-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9208e-165">See Also</span></span>  
 [<span data-ttu-id="9208e-166">Connessione dei componenti del flusso di dati a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="9208e-166">Connecting Data Flow Components Programmatically</span></span>](../building-packages-programmatically/connecting-data-flow-components-programmatically.md)  
  
  
