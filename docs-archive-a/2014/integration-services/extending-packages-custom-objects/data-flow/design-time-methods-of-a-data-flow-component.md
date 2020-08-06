---
title: Metodi della fase di progettazione di un componente flusso di dati | Microsoft Docs
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
- custom data flow components [Integration Services], method execution sequence
- ProcessInput method
- method execution sequence [Integration Services]
- PrimeOutput method
- data flow components [Integration Services], method execution sequence
ms.assetid: b5a121a1-b87c-441b-a42c-2cec628dc81c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e33fc4eb5805318dac217d2c5cbaedfd4bca70fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635173"
---
# <a name="design-time-methods-of-a-data-flow-component"></a><span data-ttu-id="cf0dc-102">Metodi della fase di progettazione di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="cf0dc-102">Design-time Methods of a Data Flow Component</span></span>
  <span data-ttu-id="cf0dc-103">Prima dell'esecuzione, l'attività Flusso di dati si trova nel cosiddetto stato della fase di progettazione, quando viene sottoposta a modifiche incrementali.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-103">Before execution, the data flow task is said to be in a design-time state, as it undergoes incremental changes.</span></span> <span data-ttu-id="cf0dc-104">Tali modifiche possono includere l'aggiunta o la rimozione di componenti, l'aggiunta o la rimozione degli oggetti percorso che connettono i componenti e modifiche ai metadati dei componenti.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-104">Changes may include the addition or removal of components, the addition or removal of the path objects that connect components, and changes to the metadata of the components.</span></span> <span data-ttu-id="cf0dc-105">Quando si verificano modifiche ai metadati, il componente può monitorarle e rispondere.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-105">When metadata changes occur, the component can monitor and react to the changes.</span></span> <span data-ttu-id="cf0dc-106">Ad esempio, un componente può impedire determinate modifiche o aggiungerne altre in risposta a una modifica.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-106">For example, a component can disallow certain changes or make additional changes in response to a change.</span></span> <span data-ttu-id="cf0dc-107">In fase di progettazione la finestra di progettazione interagisce con un componente tramite l'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> della fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-107">At design time, the designer interacts with a component through the design-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>

## <a name="design-time-implementation"></a><span data-ttu-id="cf0dc-108">Implementazione della fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="cf0dc-108">Design-Time Implementation</span></span>
 <span data-ttu-id="cf0dc-109">L'interfaccia della fase di progettazione di un componente viene descritta dall'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-109">The design-time interface of a component is described by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span> <span data-ttu-id="cf0dc-110">Anche se questa interfaccia non viene implementata in modo esplicito, una maggiore familiarità con i metodi definiti al suo interno consente di identificare i metodi della classe di base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> che corrispondono all'istanza della fase di progettazione di un componente.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-110">Although you do not explicitly implement this interface, a familiarity with the methods defined in this interface will help you understand which methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class correspond to the design-time instance of a component.</span></span>

 <span data-ttu-id="cf0dc-111">Quando un componente viene caricato in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], viene creata un'istanza dell'istanza della fase di progettazione del componente e vengono chiamati i metodi dell'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> quando il componente viene modificato.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-111">When a component is loaded in the [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], the design-time instance of the component is instantiated and the methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface are called as the component is edited.</span></span> <span data-ttu-id="cf0dc-112">L'implementazione della classe di base consente di eseguire l'override solo dei metodi richiesti dal componente.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-112">The implementation of the base class lets you override only those methods that your component requires.</span></span> <span data-ttu-id="cf0dc-113">In molti casi, è possibile eseguire l'override di tali metodi per evitare modifiche non corrette a un componente.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-113">In many cases, you may override these methods to prevent inappropriate edits to a component.</span></span> <span data-ttu-id="cf0dc-114">Ad esempio, per impedire agli utenti di aggiungere un output a un componente, eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.InsertOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-114">For example, to prevent users from adding an output to a component, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.InsertOutput%2A> method.</span></span> <span data-ttu-id="cf0dc-115">In caso contrario, quando la classe di base chiama l'implementazione di questo metodo, viene aggiunto un output al componente.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-115">Otherwise, when the implementation of this method by the base class is called, it adds an output to the component.</span></span>

 <span data-ttu-id="cf0dc-116">Indipendentemente dallo scopo o dalla funzionalità del componente, è necessario eseguire l'override dei metodi <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-116">Regardless of the purpose or functionality of your component, you should override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> methods.</span></span> <span data-ttu-id="cf0dc-117">Per altre informazioni su <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>, vedere [Convalida di un componente del flusso di dati](validating-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="cf0dc-117">For more information about <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>, see [Validating a Data Flow Component](validating-a-data-flow-component.md).</span></span>

## <a name="providecomponentproperties-method"></a><span data-ttu-id="cf0dc-118">Metodo ProvideComponentProperties</span><span class="sxs-lookup"><span data-stu-id="cf0dc-118">ProvideComponentProperties Method</span></span>
 <span data-ttu-id="cf0dc-119">L'inizializzazione di un componente si verifica nel metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-119">The initialization of a component occurs in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="cf0dc-120">Questo metodo viene chiamato da Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] quando un componente viene aggiunto all'attività Flusso di dati ed è simile a un costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-120">This method is called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer when a component is added to the data flow task, and is similar to a class constructor.</span></span> <span data-ttu-id="cf0dc-121">Gli sviluppatori di componenti devono creare e inizializzare gli input, gli output e le proprietà personalizzate durante la chiamata a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-121">Component developers should create and initialize their inputs, outputs, and custom properties during this method call.</span></span> <span data-ttu-id="cf0dc-122">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> è diverso da un costruttore perché non viene chiamato ogni volta che viene creata un'istanza dell'istanza della fase di progettazione o dell'istanza di runtime del componente.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method differs from a constructor because it is not called every time that the design-time instance or run-time instance of the component is instantiated.</span></span>

 <span data-ttu-id="cf0dc-123">L'implementazione della classe di base del metodo aggiunge un input e un output al componente e assegna l'ID dell'input alla proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-123">The base class implementation of the method adds an input and an output to the component and assigns the ID of the input to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property.</span></span> <span data-ttu-id="cf0dc-124">Tuttavia, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], gli oggetti input e output aggiunti dalla classe di base non sono denominati.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-124">However, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the input and output objects added by the base class are not named.</span></span> <span data-ttu-id="cf0dc-125">I pacchetti che contengono un componente con oggetti input o output la cui proprietà Name non è impostata non vengono caricati correttamente.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-125">Packages that contain a component with input or output objects whose Name property is not set will not successfully load.</span></span> <span data-ttu-id="cf0dc-126">Pertanto, quando si usa l'implementazione di base, è necessario assegnare in modo esplicito i valori alla proprietà Name dell'input e dell'output predefiniti.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-126">Therefore, when you use the base implementation, you must assign values explicitly to the Name property of the default input and output.</span></span>

```csharp
public override void ProvideComponentProperties()
{
    /// TODO: Reset the component.
    /// TODO: Add custom properties.
    /// TODO: Add input objects.
    /// TODO: Add output objects.
}
```

```vb
Public Overrides Sub ProvideComponentProperties()
    ' TODO: Reset the component.
    ' TODO: Add custom properties.
    ' TODO: Add input objects.
    ' TODO: Add output objects.
End Sub
```

### <a name="creating-custom-properties"></a><span data-ttu-id="cf0dc-127">Creazione di proprietà personalizzate.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-127">Creating Custom Properties</span></span>
 <span data-ttu-id="cf0dc-128">La chiamata al metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> è il punto in cui gli sviluppatori di componenti devono aggiungere proprietà personalizzate (<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>) al componente.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-128">The call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method is where component developers should add custom properties (<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>) to the component.</span></span> <span data-ttu-id="cf0dc-129">Le proprietà personalizzate non includono una proprietà del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-129">Custom properties do not have a data type property.</span></span> <span data-ttu-id="cf0dc-130">Il tipo di dati di una proprietà personalizzata viene impostato dal tipo di dati del valore assegnato alla relativa proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-130">The data type of a custom property is set by the data type of the value that you assign to its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.Value%2A> property.</span></span> <span data-ttu-id="cf0dc-131">Tuttavia, dopo aver assegnato un valore iniziale alla proprietà personalizzata, non è possibile assegnare un valore con un tipo di dati diverso.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-131">However, after you have assigned an initial value to the custom property, you cannot assign a value with a different data type.</span></span>

> [!NOTE]
>  <span data-ttu-id="cf0dc-132">L'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> prevede un supporto limitato per i valori delle proprietà di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-132">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> interface has limited support for property values of type `Object`.</span></span> <span data-ttu-id="cf0dc-133">L'unico oggetto che è possibile archiviare come valore di una proprietà personalizzata è una matrice di tipi semplici come stringhe o numeri interi.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-133">The only object that you can store as the value of a custom property is an array of simple types such as strings or integers.</span></span>

 <span data-ttu-id="cf0dc-134">È possibile indicare che la proprietà personalizzata supporta espressioni di proprietà impostando il valore della proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.ExpressionType%2A> su `CPET_NOTIFY` dall'enumerazione <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSCustomPropertyExpressionType>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-134">You can indicate that your custom property supports property expressions by setting the value of its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.ExpressionType%2A> property to `CPET_NOTIFY` from the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSCustomPropertyExpressionType> enumeration, as shown in the following example.</span></span> <span data-ttu-id="cf0dc-135">Non è necessario aggiungere codice per gestire o convalidare l'espressione di proprietà immessa dall'utente.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-135">You do not have to add any code to handle or to validate the property expression entered by the user.</span></span> <span data-ttu-id="cf0dc-136">È possibile impostare un valore predefinito per la proprietà, convalidarlo, quindi leggerlo e utilizzarlo normalmente.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-136">You can set a default value for the property, validate its value, and read and use its value normally.</span></span>

```csharp
IDTSCustomProperty100 myCustomProperty;
...
myCustomProperty.ExpressionType = DTSCustomPropertyExpressionType.CPET_NOTIFY;
```

```vb
Dim myCustomProperty As IDTSCustomProperty100
...
myCustomProperty.ExpressionType = DTSCustomPropertyExpressionType.CPET_NOTIFY
```

 <span data-ttu-id="cf0dc-137">È possibile limitare gli utenti alla selezione di un valore di proprietà personalizzato da un'enumerazione usando la <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> proprietà, come illustrato nell'esempio seguente, in cui si presuppone che sia stata definita un'enumerazione pubblica denominata `MyValidValues` .</span><span class="sxs-lookup"><span data-stu-id="cf0dc-137">You can limit users to selecting a custom property value from an enumeration by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> property, as shown in the following example, which assumes that you have defined a public enumeration named `MyValidValues`.</span></span>

```csharp
IDTSCustomProperty100 customProperty = outputColumn.CustomPropertyCollection.New();
customProperty.Name = "My Custom Property";
// This line associates the type with the custom property.
customProperty.TypeConverter = typeof(MyValidValues).AssemblyQualifiedName;
// Now you can use the enumeration values directly.
customProperty.Value = MyValidValues.ValueOne;  
```

```vb
Dim customProperty As IDTSCustomProperty100 = outputColumn.CustomPropertyCollection.New 
customProperty.Name = "My Custom Property" 
' This line associates the type with the custom property.
customProperty.TypeConverter = GetType(MyValidValues).AssemblyQualifiedName 
' Now you can use the enumeration values directly.
customProperty.Value = MyValidValues.ValueOne
```

 <span data-ttu-id="cf0dc-138">Per altre informazioni, vedere gli argomenti relativi alla conversione di tipi generalizzata e all'implementazione del convertitore di tipi in [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span><span class="sxs-lookup"><span data-stu-id="cf0dc-138">For more information, see "Generalized Type Conversion" and "Implementing a Type Converter" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span></span>

 <span data-ttu-id="cf0dc-139">È possibile specificare una finestra di dialogo dell'editor personalizzata per il valore della proprietà personalizzata tramite la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-139">You can specify a custom editor dialog box for the value of your custom property by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> property, as shown in the following example.</span></span> <span data-ttu-id="cf0dc-140">Creare innanzitutto un editor di tipo personalizzato che eredita da `System.Drawing.Design.UITypeEditor`, se non è possibile individuare una classe di editor di tipo dell'interfaccia utente che soddisfa le esigenze specifiche.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-140">First, you must create a custom type editor that inherits from `System.Drawing.Design.UITypeEditor`, if you cannot locate an existing UI type editor class that fits your needs.</span></span>

```csharp
public class MyCustomTypeEditor : UITypeEditor
{
...
}
```

```vb
Public Class MyCustomTypeEditor
  Inherits UITypeEditor 
  ...
End Class
```

 <span data-ttu-id="cf0dc-141">Specificare questa classe come valore della proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> della proprietà personalizzata.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-141">Next, specify this class as the value of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> property of your custom property.</span></span>

```csharp
IDTSCustomProperty100 customProperty = outputColumn.CustomPropertyCollection.New();
customProperty.Name = "My Custom Property";
// This line associates the editor with the custom property.
customProperty.UITypeEditor = typeof(MyCustomTypeEditor).AssemblyQualifiedName;
```

```vb
Dim customProperty As IDTSCustomProperty100 = outputColumn.CustomPropertyCollection.New 
customProperty.Name = "My Custom Property" 
' This line associates the editor with the custom property.
customProperty.UITypeEditor = GetType(MyCustomTypeEditor).AssemblyQualifiedName
```

 <span data-ttu-id="cf0dc-142">Per altre informazioni, vedere "implementazione di un editor di tipi con interfaccia utente" in [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span><span class="sxs-lookup"><span data-stu-id="cf0dc-142">For more information, see "Implementing a UI Type Editor" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span></span>

<span data-ttu-id="cf0dc-143">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="cf0dc-143">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="cf0dc-144">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="cf0dc-144">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="cf0dc-145">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="cf0dc-145">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="cf0dc-146">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-146">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf0dc-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf0dc-147">See Also</span></span>
 [<span data-ttu-id="cf0dc-148">Metodi di runtime di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="cf0dc-148">Run-time Methods of a Data Flow Component</span></span>](run-time-methods-of-a-data-flow-component.md)


