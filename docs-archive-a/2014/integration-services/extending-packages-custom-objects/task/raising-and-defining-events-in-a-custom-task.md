---
title: Generazione e definizione di eventi in un'attività personalizzata | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SSIS events, custom
- status information [SQL Server], task events
- custom tasks [Integration Services], events
- SSIS custom tasks, events
- IDTSComponentEvents interface
- events [Integration Services], custom
- events [Integration Services], runtime
- custom events [Integration Services]
- SSIS events, runtime
- IDTSEvents interface
ms.assetid: e0898aa1-e90c-4c4e-99d4-708a76efddfd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb41ee60543a05b6cf10b3acda43372e20288d13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635167"
---
# <a name="raising-and-defining-events-in-a-custom-task"></a><span data-ttu-id="2334b-102">Generazione e definizione di eventi in un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="2334b-102">Raising and Defining Events in a Custom Task</span></span>
  <span data-ttu-id="2334b-103">Il motore di runtime di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] include una raccolta di eventi che forniscono lo stato di avanzamento durante la convalida e l'esecuzione di un'attività.</span><span class="sxs-lookup"><span data-stu-id="2334b-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] run-time engine provides a collection of events that provide status on the progress of a task as the task is validated and executed.</span></span> <span data-ttu-id="2334b-104">L'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> definisce questi eventi e viene fornita alle attività come parametro per i metodi <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="2334b-104">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface defines these events, and is provided to tasks as a parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> methods.</span></span>  
  
 <span data-ttu-id="2334b-105">È disponibile un altro set di eventi, definiti nell'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>, che vengono generati per conto dell'attività da <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="2334b-105">There is another set of events, which are defined in the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface, that are raised on behalf of the task by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="2334b-106">L'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> genera gli eventi che si verificano prima e dopo la convalida e l'esecuzione, mentre l'attività genera gli eventi che si verificano durante l'esecuzione e la convalida.</span><span class="sxs-lookup"><span data-stu-id="2334b-106">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> raises events that occur before and after validation and execution, whereas the task raises the events that occur during execution and validation.</span></span>  
  
## <a name="creating-custom-events"></a><span data-ttu-id="2334b-107">Creazione di eventi personalizzati</span><span class="sxs-lookup"><span data-stu-id="2334b-107">Creating Custom Events</span></span>  
 <span data-ttu-id="2334b-108">Gli sviluppatori di attività personalizzate possono definire nuovi eventi personalizzati creando un nuovo oggetto <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> nell'implementazione sottoposta a override del metodo <xref:Microsoft.SqlServer.Dts.Runtime.Task.InitializeTask%2A>.</span><span class="sxs-lookup"><span data-stu-id="2334b-108">Custom task developers can define new, custom events by creating a new <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> in their overridden implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.Task.InitializeTask%2A> method.</span></span> <span data-ttu-id="2334b-109">L'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo>, una volta creato, viene aggiunto alla raccolta `EventInfos` tramite il metodo <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="2334b-109">After the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> is created, it is added to the `EventInfos` collection by using the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A> method.</span></span> <span data-ttu-id="2334b-110">La firma del metodo <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A> è la seguente:</span><span class="sxs-lookup"><span data-stu-id="2334b-110">The method signature of the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A> method is as follows:</span></span>  
  
 `public void Add(string eventName, string description, bool allowEventHandlers, string[] parameterNames, TypeCode[] parameterTypes, string[] parameterDescriptions);`  
  
 <span data-ttu-id="2334b-111">Nell'esempio di codice seguente è illustrato il metodo `InitializeTask` di un'attività personalizzata, in cui vengono creati due eventi e vengono impostate le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="2334b-111">The following code sample shows the `InitializeTask` method of a custom task, where two custom events are created and their properties are set.</span></span> <span data-ttu-id="2334b-112">I nuovi eventi vengono quindi aggiunti alla raccolta <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos>.</span><span class="sxs-lookup"><span data-stu-id="2334b-112">The new events are then added to the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos> collection.</span></span>  
  
 <span data-ttu-id="2334b-113">Il primo evento personalizzato presenta un elemento *eventName* di "**OnBeforeIncrement**" e un elemento *description* di "**Fires after the initial value is updated.** "</span><span class="sxs-lookup"><span data-stu-id="2334b-113">The first custom event has an *eventName* of "**OnBeforeIncrement**" and *description* of "**Fires after the initial value is updated.**"</span></span> <span data-ttu-id="2334b-114">Il parametro successivo, il valore `true`, indica che questo evento deve consentire la creazione di un contenitore del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="2334b-114">The next parameter, the `true` value, indicates that this event should allow an event handler container to be created to handle the event.</span></span> <span data-ttu-id="2334b-115">Il gestore eventi è un contenitore che fornisce la struttura in un pacchetto e servizi alle attività, analogamente ad altri contenitori come Sequence, ForLoop e ForEachLoop.</span><span class="sxs-lookup"><span data-stu-id="2334b-115">The event handler is a container that provides structure in a package and services to tasks, like other containers such as the package, Sequence, ForLoop, and ForEachLoop.</span></span> <span data-ttu-id="2334b-116">Quando il parametro *AllowEventHandlers* è `true` , <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> gli oggetti vengono creati per l'evento.</span><span class="sxs-lookup"><span data-stu-id="2334b-116">When the *allowEventHandlers* parameter is `true`, <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects are created for the event.</span></span> <span data-ttu-id="2334b-117">I parametri definiti per l'evento sono ora disponibili per <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> nella raccolta di variabili di <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="2334b-117">Any parameters that were defined for the event are now available to the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> in the variables collection of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span></span>  
  
```csharp  
public override void InitializeTask(Connections connections,  
   VariableDispenser variables, IDTSInfoEvents events,  
   IDTSLogging log, EventInfos eventInfos,  
   LogEntryInfos logEntryInfos, ObjectReferenceTracker refTracker)  
{  
    this.eventInfos = eventInfos;  
    string[] paramNames = new string[1];  
    TypeCode[] paramTypes = new TypeCode[1]{TypeCode.Int32};  
    string[] paramDescriptions = new string[1];  
  
    paramNames[0] = "InitialValue";  
    paramDescriptions[0] = "The value before it is incremented.";  
  
    this.eventInfos.Add("OnBeforeIncrement",   
      "Fires before the task increments the value.",  
      true,paramNames,paramTypes,paramDescriptions);  
    this.onBeforeIncrement = this.eventInfos["OnBeforeIncrement"];  
  
    paramDescriptions[0] = "The value after it has been incremented.";  
    this.eventInfos.Add("OnAfterIncrement",  
      "Fires after the initial value is updated.",  
      true,paramNames, paramTypes,paramDescriptions);  
    this.onAfterIncrement = this.eventInfos["OnAfterIncrement"];  
}  
```  
  
```vb  
Public Overrides Sub InitializeTask(ByVal connections As Connections, _  
ByVal variables As VariableDispenser, ByVal events As IDTSInfoEvents, _  
ByVal log As IDTSLogging, ByVal eventInfos As EventInfos, _  
ByVal logEntryInfos As LogEntryInfos, ByVal refTracker As ObjectReferenceTracker)   
  
    Dim paramNames(0) As String  
    Dim paramTypes(0) As TypeCode = {TypeCode.Int32}  
    Dim paramDescriptions(0) As String  
  
    Me.eventInfos = eventInfos  
  
    paramNames(0) = "InitialValue"  
    paramDescriptions(0) = "The value before it is incremented."  
  
    Me.eventInfos.Add("OnBeforeIncrement", _  
      "Fires before the task increments the value.", _  
      True, paramNames, paramTypes, paramDescriptions)  
    Me.onBeforeIncrement = Me.eventInfos("OnBeforeIncrement")  
  
    paramDescriptions(0) = "The value after it has been incremented."  
    Me.eventInfos.Add("OnAfterIncrement", _  
      "Fires after the initial value is updated.", True, _  
      paramNames, paramTypes, paramDescriptions)  
    Me.onAfterIncrement = Me.eventInfos("OnAfterIncrement")  
  
End Sub  
```  
  
## <a name="raising-custom-events"></a><span data-ttu-id="2334b-118">Generazione di eventi personalizzati</span><span class="sxs-lookup"><span data-stu-id="2334b-118">Raising Custom Events</span></span>  
 <span data-ttu-id="2334b-119">Gli eventi personalizzati vengono generati con una chiamata al metodo <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="2334b-119">Custom events are raised by calling the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A> method.</span></span> <span data-ttu-id="2334b-120">La riga di codice seguente genera un evento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2334b-120">The following line of code raises a custom event.</span></span>  
  
```csharp  
componentEvents.FireCustomEvent(this.onBeforeIncrement.Name,  
   this.onBeforeIncrement.Description, ref arguments,  
   null, ref bFireOnBeforeIncrement);  
```  
  
```vb  
componentEvents.FireCustomEvent(Me.onBeforeIncrement.Name, _  
Me.onBeforeIncrement.Description, arguments, _  
Nothing,  bFireOnBeforeIncrement)  
```  
  
## <a name="sample"></a><span data-ttu-id="2334b-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="2334b-121">Sample</span></span>  
 <span data-ttu-id="2334b-122">Nell'esempio di codice seguente è illustrata un'attività che definisce un evento personalizzato nel metodo`InitializeTask`, aggiunge l'evento personalizzato alla raccolta <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos>, quindi genera l'evento personalizzato durante il relativo metodo `Execute` chiamando il metodo <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="2334b-122">The following example shows a task that defines a custom event in the `InitializeTask` method, adds the custom event to the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos> collection, and then raises the custom event during its `Execute` method by calling the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A> method.</span></span>  
  
```csharp  
[DtsTask(DisplayName = "CustomEventTask")]  
    public class CustomEventTask : Task  
    {  
        public override DTSExecResult Execute(Connections connections,   
          VariableDispenser variableDispenser, IDTSComponentEvents componentEvents,  
           IDTSLogging log, object transaction)  
        {  
            bool fireAgain;  
            object[] args = new object[1] { "The value of the parameter." };  
            componentEvents.FireCustomEvent( "MyCustomEvent",   
              "Firing the custom event.", ref args,  
              "CustomEventTask" , ref fireAgain );  
            return DTSExecResult.Success;  
        }  
  
        public override void InitializeTask(Connections connections,  
          VariableDispenser variableDispenser, IDTSInfoEvents events,  
          IDTSLogging log, EventInfos eventInfos,  
          LogEntryInfos logEntryInfos, ObjectReferenceTracker refTracker)  
        {  
            string[] names = new string[1] {"Parameter1"};  
            TypeCode[] types = new TypeCode[1] {TypeCode.String};  
            string[] descriptions = new string[1] {"Parameter description." };  
  
            eventInfos.Add("MyCustomEvent",  
             "Fires when my interesting event happens.",  
             true, names, types, descriptions);  
  
        }  
   }  
```  
  
```vb  
<DtsTask(DisplayName = "CustomEventTask")> _   
    Public Class CustomEventTask  
     Inherits Task  
        Public Overrides Function Execute(ByVal connections As Connections, _  
          ByVal variableDispenser As VariableDispenser, _  
          ByVal componentEvents As IDTSComponentEvents, _  
          ByVal log As IDTSLogging, ByVal transaction As Object) _  
          As DTSExecResult  
  
            Dim fireAgain As Boolean  
            Dim args() As Object =  New Object(1) {"The value of the parameter."}  
  
            componentEvents.FireCustomEvent("MyCustomEvent", _  
              "Firing the custom event.", args, _  
              "CustomEventTask" ,  fireAgain)  
            Return DTSExecResult.Success  
        End Function  
  
        Public Overrides  Sub InitializeTask(ByVal connections As Connections, _  
          ByVal variableDispenser As VariableDispenser,  
          ByVal events As IDTSInfoEvents,  
          ByVal log As IDTSLogging, ByVal eventInfos As EventInfos, ByVal logEnTryInfos As LogEnTryInfos, ByVal refTracker As ObjectReferenceTracker)  
  
            Dim names() As String =  New String(1) {"Parameter1"}  
            Dim types() As TypeCode =  New TypeCode(1) {TypeCode.String}  
            Dim descriptions() As String =  New String(1) {"Parameter description."}  
  
            eventInfos.Add("MyCustomEvent", _  
              "Fires when my interesting event happens.", _  
              True, names, types, descriptions)  
  
        End Sub  
  
    End Class  
```  
  
<span data-ttu-id="2334b-123">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2334b-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2334b-124">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="2334b-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2334b-125">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="2334b-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2334b-126">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="2334b-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2334b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2334b-127">See Also</span></span>  
 <span data-ttu-id="2334b-128">[Gestori eventi di Integration Services &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="2334b-128">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="2334b-129">Aggiunta di un gestore eventi a un pacchetto</span><span class="sxs-lookup"><span data-stu-id="2334b-129">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
