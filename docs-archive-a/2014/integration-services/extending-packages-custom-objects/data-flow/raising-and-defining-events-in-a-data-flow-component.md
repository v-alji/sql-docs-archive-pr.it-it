---
title: Generazione e definizione di eventi in un componente flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow components [Integration Services], events
- events [Integration Services], custom
- custom events [Integration Services]
- custom data flow components [Integration Services], events
- events [Integration Services], raising
- predefined events [Integration Services]
ms.assetid: 1d8c5358-9384-47a8-b7cb-7b0650384119
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 25f4572f8a8af829145da4e4d685f5dddad4a29a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713323"
---
# <a name="raising-and-defining-events-in-a-data-flow-component"></a><span data-ttu-id="746d4-102">Generazione e definizione di eventi in un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="746d4-102">Raising and Defining Events in a Data Flow Component</span></span>
  <span data-ttu-id="746d4-103">Gli sviluppatori di componenti possono generare un subset degli eventi definiti nell'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> chiamando i metodi esposti sulla proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="746d4-103">Component developers can raise a subset of the events defined in the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface by calling the methods exposed on the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span> <span data-ttu-id="746d4-104">È anche possibile definire eventi personalizzati tramite la raccolta <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> e generarli durante l'esecuzione utilizzando il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="746d4-104">You can also define custom events by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> collection, and raise them during execution by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method.</span></span> <span data-ttu-id="746d4-105">In questa sezione viene descritto come creare e generare un evento e vengono fornite linee guida su quando è necessario generare eventi in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="746d4-105">This section describes how to create and raise an event, and provides guidelines on when you should raise events at design time.</span></span>

## <a name="raising-events"></a><span data-ttu-id="746d4-106">Generazione di eventi</span><span class="sxs-lookup"><span data-stu-id="746d4-106">Raising Events</span></span>
 <span data-ttu-id="746d4-107">I componenti generano eventi usando i metodi **Fire\<X>** dell'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="746d4-107">Components raise events by using the **Fire\<X>** methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="746d4-108">È possibile generare eventi durante la progettazione e l'esecuzione di componenti.</span><span class="sxs-lookup"><span data-stu-id="746d4-108">You can raise events during component design and execution.</span></span> <span data-ttu-id="746d4-109">In genere, durante la progettazione di componenti, i metodi <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A> vengono chiamati durante la convalida.</span><span class="sxs-lookup"><span data-stu-id="746d4-109">Typically, during component design, the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A> methods are called during validation.</span></span> <span data-ttu-id="746d4-110">Questi eventi visualizzano messaggi nel riquadro **Elenco errori** di [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] e forniscono feedback agli utenti di un componente non correttamente configurato.</span><span class="sxs-lookup"><span data-stu-id="746d4-110">These events display messages in the **Error List** pane of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] and provide feedback to users of the component when a component is incorrectly configured.</span></span>

 <span data-ttu-id="746d4-111">I componenti possono inoltre generare eventi in qualsiasi momento durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="746d4-111">Components can also raise events at any point during execution.</span></span> <span data-ttu-id="746d4-112">Gli eventi consentono agli sviluppatori di componenti di fornire feedback agli utenti del componente durante la relativa esecuzione.</span><span class="sxs-lookup"><span data-stu-id="746d4-112">Events allow component developers to provide feedback to users of the component as it executes.</span></span> <span data-ttu-id="746d4-113">Se viene chiamato il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> durante l'esecuzione, è probabile che il pacchetto non riesca.</span><span class="sxs-lookup"><span data-stu-id="746d4-113">Calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> method during execution is likely to fail the package.</span></span>

## <a name="defining-and-raising-custom-events"></a><span data-ttu-id="746d4-114">Definizione e generazione di eventi personalizzati</span><span class="sxs-lookup"><span data-stu-id="746d4-114">Defining and Raising Custom Events</span></span>

### <a name="defining-a-custom-event"></a><span data-ttu-id="746d4-115">Definizione di eventi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="746d4-115">Defining a Custom Event</span></span>
 <span data-ttu-id="746d4-116">Gli eventi personalizzati vengono creati chiamando il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> della raccolta <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A>.</span><span class="sxs-lookup"><span data-stu-id="746d4-116">Custom events are created by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> collection.</span></span> <span data-ttu-id="746d4-117">Questa raccolta viene impostata dall'attività Flusso di dati e viene fornita come proprietà allo sviluppatore di componenti tramite la classe di base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>.</span><span class="sxs-lookup"><span data-stu-id="746d4-117">This collection is set by the data flow task and provided as a property to the component developer through the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class.</span></span> <span data-ttu-id="746d4-118">Questa classe contiene eventi personalizzati definiti dall'attività Flusso di dati ed eventi personalizzati definiti dal componente durante il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A>.</span><span class="sxs-lookup"><span data-stu-id="746d4-118">This class contains custom events defined by the data flow task and custom events defined by the component during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method.</span></span>

 <span data-ttu-id="746d4-119">Gli eventi personalizzati di un componente non sono persistenti nel codice XML del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="746d4-119">The custom events of a component are not persisted in the package XML.</span></span> <span data-ttu-id="746d4-120">Pertanto, il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> viene chiamato sia durante la progettazione che durante l'esecuzione per consentire al componente di definire gli eventi che genera.</span><span class="sxs-lookup"><span data-stu-id="746d4-120">Therefore, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method is called during both design and execution to allow the component to define the events it raises.</span></span>

 <span data-ttu-id="746d4-121">Il parametro *allowEventHandlers* del metodo <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> specifica se il componente consente la creazione di oggetti <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> per l'evento.</span><span class="sxs-lookup"><span data-stu-id="746d4-121">The *allowEventHandlers* parameter of the <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> method specifies whether the component allows <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects to be created for the event.</span></span> <span data-ttu-id="746d4-122">Si noti che <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> sono sincroni.</span><span class="sxs-lookup"><span data-stu-id="746d4-122">Note that <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> are synchronous.</span></span> <span data-ttu-id="746d4-123">Pertanto, il componente riprende l'esecuzione solo al termine dell'esecuzione di un oggetto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> connesso all'evento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="746d4-123">Therefore the component does not resume execution until an <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> attached to the custom event has finished executing.</span></span> <span data-ttu-id="746d4-124">Se il parametro *AllowEventHandlers* è `true` , ogni parametro dell'evento viene automaticamente reso disponibile per tutti <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> gli oggetti tramite variabili create e popolate automaticamente dal [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Runtime.</span><span class="sxs-lookup"><span data-stu-id="746d4-124">If the *allowEventHandlers* parameter is `true`, each parameter of the event is automatically made available to any <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects through variables that are created and populated automatically by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime.</span></span>

### <a name="raising-a-custom-event"></a><span data-ttu-id="746d4-125">Generazione di eventi personalizzati</span><span class="sxs-lookup"><span data-stu-id="746d4-125">Raising a Custom Event</span></span>
 <span data-ttu-id="746d4-126">I componenti generano eventi personalizzati chiamando il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> e fornendo il nome, il testo e i parametri dell'evento.</span><span class="sxs-lookup"><span data-stu-id="746d4-126">Components raise custom events by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method, and providing the name, text, and parameters of the event.</span></span> <span data-ttu-id="746d4-127">Se il parametro *AllowEventHandlers* è `true` , <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> gli eventuali creati per l'evento personalizzato vengono eseguiti dal motore di [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Run-Time.</span><span class="sxs-lookup"><span data-stu-id="746d4-127">If the *allowEventHandlers* parameter is `true`, any <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> that are created for the custom event are executed by the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] run-time engine.</span></span>

### <a name="custom-event-sample"></a><span data-ttu-id="746d4-128">Esempio di evento personalizzato</span><span class="sxs-lookup"><span data-stu-id="746d4-128">Custom Event Sample</span></span>
 <span data-ttu-id="746d4-129">Nell'esempio di codice seguente è illustrato un componente che definisce un evento personalizzato durante il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A>, quindi genera l'evento in fase di esecuzione chiamando il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="746d4-129">The following code example shows a component that defines a custom event during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method, and then raises the event at run time by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method.</span></span>

```csharp
public override void RegisterEvents()
{
    string [] parameterNames = new string[2]{"RowCount", "StartTime"};
    ushort [] parameterTypes = new ushort[2]{ DtsConvert.VarTypeFromTypeCode(TypeCode.Int32), DtsConvert.VarTypeFromTypeCode(TypeCode.DateTime)};
    string [] parameterDescriptions = new string[2]{"The number of rows to sort.", "The start time of the Sort operation."};
    EventInfos.Add("StartingSort","Fires when the component begins sorting the rows.",false,ref parameterNames, ref parameterTypes, ref parameterDescriptions);
}
public override void ProcessInput(int inputID, PipelineBuffer buffer)
{
    while (buffer.NextRow())
    {
       // Process buffer rows.
    }

    IDTSEventInfo100 eventInfo = EventInfos["StartingSort"];
    object []arguments = new object[2]{buffer.RowCount, DateTime.Now };
    ComponentMetaData.FireCustomEvent("StartingSort", "Beginning sort operation.", ref arguments, ComponentMetaData.Name, ref FireSortEventAgain);
}
```

```vb
Public  Overrides Sub RegisterEvents() 
  Dim parameterNames As String() = New String(2) {"RowCount", "StartTime"} 
  Dim parameterTypes As System.UInt16() = New System.UInt16(2) {DtsConvert.VarTypeFromTypeCode(TypeCode.Int32), DtsConvert.VarTypeFromTypeCode(TypeCode.DateTime)} 
  Dim parameterDescriptions As String() = New String(2) {"The number of rows to sort.", "The start time of the Sort operation."} 
  EventInfos.Add("StartingSort", "Fires when the component begins sorting the rows.", False, parameterNames, parameterTypes, parameterDescriptions) 
End Sub 

Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer) 
  While buffer.NextRow 
  End While 
  Dim eventInfo As IDTSEventInfo100 = EventInfos("StartingSort") 
  Dim arguments As Object() = New Object(2) {buffer.RowCount, DateTime.Now} 
  ComponentMetaData.FireCustomEvent("StartingSort", _
    "Beginning sort operation.", arguments, _
    ComponentMetaData.Name, FireSortEventAgain) 
End Sub
```

<span data-ttu-id="746d4-130">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="746d4-130">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="746d4-131">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="746d4-131">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="746d4-132">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="746d4-132">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="746d4-133">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="746d4-133">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="746d4-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="746d4-134">See Also</span></span>
 <span data-ttu-id="746d4-135">[Integration Services &#40;i gestori eventi&#41; SSIS](../../integration-services-ssis-event-handlers.md) [aggiungono un gestore eventi a un pacchetto](../../add-an-event-handler-to-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="746d4-135">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) [Add an Event Handler to a Package](../../add-an-event-handler-to-a-package.md)</span></span>


