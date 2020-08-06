---
title: Scrittura del codice di un'attività personalizzata | Microsoft Docs
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
- Validate method
- custom tasks [Integration Services], validating
- validation [Integration Services], design-time tasks
- SSIS custom tasks, validating
ms.assetid: dc224f4f-b339-4eb6-a008-1b4fe0ea4fd2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c369f4a7e8352be7ddde9e2e3938b47b0bcc1349
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629930"
---
# <a name="coding-a-custom-task"></a><span data-ttu-id="a4b71-102">Scrittura del codice di un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="a4b71-102">Coding a Custom Task</span></span>
  <span data-ttu-id="a4b71-103">Dopo avere creato una classe che eredita dalla classe di base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) e avere applicato l'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> alla classe, è necessario eseguire l'override dell'implementazione delle proprietà e dei metodi della classe di base per specificare la funzionalità personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a4b71-103">After you have created a class that inherits from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>

## <a name="configuring-the-task"></a><span data-ttu-id="a4b71-104">Configurazione dell'attività</span><span class="sxs-lookup"><span data-stu-id="a4b71-104">Configuring the Task</span></span>

### <a name="validating-the-task"></a><span data-ttu-id="a4b71-105">Convalida dell'attività</span><span class="sxs-lookup"><span data-stu-id="a4b71-105">Validating the Task</span></span>
 <span data-ttu-id="a4b71-106">Quando si progetta un pacchetto di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], è possibile utilizzare la convalida per verificare le impostazioni per ogni attività, in modo da rilevare impostazioni non corrette o non appropriate non appena vengono specificate, anziché trovare tutti gli errori solo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a4b71-106">When you are designing an [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] package, you can use validation to verify settings on each task, so that you can catch incorrect or inappropriate settings as soon as they are set, instead of finding all errors at run-time only.</span></span> <span data-ttu-id="a4b71-107">Scopo della convalida è determinare se l'attività contiene impostazioni o connessioni non valide che ne impediranno la corretta esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a4b71-107">The purpose of validation is to determine whether the task contains invalid settings or connections that will prevent it from running successfully.</span></span> <span data-ttu-id="a4b71-108">In questo modo è possibile assicurarsi che il pacchetto contenga attività che con buone probabilità verranno eseguite al primo tentativo.</span><span class="sxs-lookup"><span data-stu-id="a4b71-108">This makes sure that the package contains tasks that have a good chance of running on their first run.</span></span>

 <span data-ttu-id="a4b71-109">È possibile implementare la convalida utilizzando il metodo `Validate` nel codice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="a4b71-109">You can implement validation by using the `Validate` method in custom code.</span></span> <span data-ttu-id="a4b71-110">Il motore di runtime convalida un'attività chiamando il metodo `Validate` sull'attività.</span><span class="sxs-lookup"><span data-stu-id="a4b71-110">The run-time engine validates a task by calling the `Validate` method on the task.</span></span> <span data-ttu-id="a4b71-111">È responsabilità dello sviluppatore dell'attività definire i criteri che determinano l'esito positivo o negativo della convalida dell'attività e notificare al motore di runtime il risultato di questa valutazione.</span><span class="sxs-lookup"><span data-stu-id="a4b71-111">It is the responsibility of the task developer to define the criteria that give you a successful or failed task validation, and to notify the run-time engine of the result of this evaluation.</span></span>

#### <a name="task-abstract-base-class"></a><span data-ttu-id="a4b71-112">Classe di base astratta Task</span><span class="sxs-lookup"><span data-stu-id="a4b71-112">Task Abstract Base Class</span></span>
 <span data-ttu-id="a4b71-113">La classe base astratta [Microsoft. SqlServer. Dts. Runtime. Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) fornisce il `Validate` metodo di cui ogni attività esegue l'override per definire i criteri di convalida.</span><span class="sxs-lookup"><span data-stu-id="a4b71-113">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) abstract base class provides the `Validate` method that each task overrides to define its validation criteria.</span></span> <span data-ttu-id="a4b71-114">Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] chiama automaticamente il metodo `Validate` più volte durante la progettazione del pacchetto e fornisce indicatori visivi all'utente quando si verificano avvisi o errori per consentire di identificare i problemi con la configurazione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="a4b71-114">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer automatically calls the `Validate` method multiple times during package design, and provides visual cues to the user when warnings or errors occur to help identify problems with the configuration of the task.</span></span> <span data-ttu-id="a4b71-115">Le attività forniscono i risultati della convalida restituendo un valore dall'enumerazione <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> e generando eventi di avviso e di errore.</span><span class="sxs-lookup"><span data-stu-id="a4b71-115">Tasks provide validation results by returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration, and by raising warning and error events.</span></span> <span data-ttu-id="a4b71-116">Questi eventi contengono informazioni visualizzate all'utente in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4b71-116">These events contain information that is displayed to the user in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>

 <span data-ttu-id="a4b71-117">Di seguito sono riportati alcuni esempi di convalida:</span><span class="sxs-lookup"><span data-stu-id="a4b71-117">Some examples for validation follow:</span></span>

-   <span data-ttu-id="a4b71-118">Una gestione connessione convalida il nome di file specifico.</span><span class="sxs-lookup"><span data-stu-id="a4b71-118">A connection manager validates the specific file name.</span></span>

-   <span data-ttu-id="a4b71-119">Una gestione connessione convalida che l'input è del tipo previsto, ad esempio un file XML.</span><span class="sxs-lookup"><span data-stu-id="a4b71-119">A connection manager validates that the type of input is the expected type, such as an XML file.</span></span>

-   <span data-ttu-id="a4b71-120">Un'attività che prevede input di database verifica che non è in grado di ricevere dati da una connessione non di database.</span><span class="sxs-lookup"><span data-stu-id="a4b71-120">A task that expects database input verifies that it cannot receive data from a non-database connection.</span></span>

-   <span data-ttu-id="a4b71-121">Un'attività garantisce che nessuna delle proprie proprietà sia in conflitto con altre proprietà impostate per la stessa attività.</span><span class="sxs-lookup"><span data-stu-id="a4b71-121">A task guarantees that none of its properties contradicts other properties set on the same task.</span></span>

-   <span data-ttu-id="a4b71-122">Un'attività garantisce che tutte le risorse richieste utilizzate dall'attività in fase di esecuzione siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="a4b71-122">A task guarantees that all required resources used by the task at execution time are available.</span></span>

 <span data-ttu-id="a4b71-123">Le prestazioni sono un aspetto da considerare quando si determinano gli elementi da convalidare.</span><span class="sxs-lookup"><span data-stu-id="a4b71-123">Performance is something to consider in determining what is validated and what is not.</span></span> <span data-ttu-id="a4b71-124">Ad esempio, l'input di un'attività potrebbe essere una connessione su una rete caratterizzata da una larghezza di banda insufficiente o da un traffico elevato.</span><span class="sxs-lookup"><span data-stu-id="a4b71-124">For example, the input to a task might be a connection over a network that has low bandwidth or heavy traffic.</span></span> <span data-ttu-id="a4b71-125">L'elaborazione della convalida può richiedere diversi secondi se si decide di verificare che la risorsa sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="a4b71-125">The validation may take several seconds to process if you decide to validate that the resource is available.</span></span> <span data-ttu-id="a4b71-126">Un'altra convalida può generare un round trip a un server con un carico elevato, quindi la routine di convalida può essere lenta.</span><span class="sxs-lookup"><span data-stu-id="a4b71-126">Another validation may cause a round-trip to a server that is in high demand, and the validation routine might be slow.</span></span> <span data-ttu-id="a4b71-127">Anche se è possibile convalidare molte proprietà e impostazioni, questa operazione non è sempre necessaria.</span><span class="sxs-lookup"><span data-stu-id="a4b71-127">Although there are many properties and settings that can be validated, not everything should be validated.</span></span>

-   <span data-ttu-id="a4b71-128">Prima dell'esecuzione dell'attività, il codice del metodo `Validate` viene chiamato anche da <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> e <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> annulla l'esecuzione in caso di errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="a4b71-128">The code in the `Validate` method is also called by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> before the task is run, and the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> cancels execution if validation fails.</span></span>

#### <a name="user-interface-considerations-during-validation"></a><span data-ttu-id="a4b71-129">Considerazioni sull'interfaccia utente durante la convalida</span><span class="sxs-lookup"><span data-stu-id="a4b71-129">User Interface Considerations during Validation</span></span>
 <span data-ttu-id="a4b71-130">[Microsoft. SqlServer. Dts. Runtime. Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) include un' <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interfaccia come parametro per il `Validate` metodo.</span><span class="sxs-lookup"><span data-stu-id="a4b71-130">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) includes an <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface as a parameter to the `Validate` method.</span></span> <span data-ttu-id="a4b71-131">L'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> contiene i metodi chiamati dall'attività per generare eventi nel motore di runtime.</span><span class="sxs-lookup"><span data-stu-id="a4b71-131">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface contains the methods that are called by the task in order to raise events to the run-time engine.</span></span> <span data-ttu-id="a4b71-132">I metodi <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> vengono chiamati quando si verifica una condizione di avviso o di errore durante la convalida.</span><span class="sxs-lookup"><span data-stu-id="a4b71-132">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods are called when a warning or error condition occurs during validation.</span></span> <span data-ttu-id="a4b71-133">Entrambi i metodi di avviso richiedono gli stessi parametri, che includono un codice di errore, un componente di origine, una descrizione, un file della Guida e informazioni di contesto della Guida.</span><span class="sxs-lookup"><span data-stu-id="a4b71-133">Both warning methods require the same parameters, which include an error code, source component, description, Help file, and Help context information.</span></span> <span data-ttu-id="a4b71-134">Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] utilizza queste informazioni per visualizzare indicatori visivi nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a4b71-134">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses this information to display visual cues on the design surface.</span></span> <span data-ttu-id="a4b71-135">Gli indicatori visivi forniti dalla finestra di progettazione includono l'icona di un punto esclamativo visualizzata accanto all'attività nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a4b71-135">The visual cues that are provided by the designer include an exclamation icon that appears next to the task on the designer surface.</span></span> <span data-ttu-id="a4b71-136">Tale icona indica all'utente che l'attività richiede procedure aggiuntive di configurazione prima che l'esecuzione possa continuare.</span><span class="sxs-lookup"><span data-stu-id="a4b71-136">This visual cue signals to the user that the task requires additional configuration before execution can continue.</span></span>

 <span data-ttu-id="a4b71-137">L'icona del punto esclamativo visualizza inoltre una descrizione comando contenente un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="a4b71-137">The exclamation icon also displays a ToolTip that contains an error message.</span></span> <span data-ttu-id="a4b71-138">Il messaggio di errore viene fornito dall'attività nel parametro di descrizione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a4b71-138">The error message is provided by the task in the description parameter of the event.</span></span> <span data-ttu-id="a4b71-139">I messaggi di errore vengono anche visualizzati nel riquadro **Elenco attività** di [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], che offre all'utente una posizione centrale da cui visualizzare tutti gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="a4b71-139">Error messages are also displayed in the **Task List** pane of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], providing the user with a central location for viewing all validation errors.</span></span>

#### <a name="validation-example"></a><span data-ttu-id="a4b71-140">Esempio di convalida</span><span class="sxs-lookup"><span data-stu-id="a4b71-140">Validation Example</span></span>
 <span data-ttu-id="a4b71-141">Nell'esempio di codice riportato di seguito è illustrata un'attività con una proprietà `UserName`.</span><span class="sxs-lookup"><span data-stu-id="a4b71-141">The following code example shows a task with a `UserName` property.</span></span> <span data-ttu-id="a4b71-142">Questa proprietà è stata specificata come richiesto per l'esito positivo della convalida.</span><span class="sxs-lookup"><span data-stu-id="a4b71-142">This property has been specified as required for validation to succeed.</span></span> <span data-ttu-id="a4b71-143">Se la proprietà non viene impostata, l'attività genera un errore e restituisce <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Failure> dall'enumerazione <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>.</span><span class="sxs-lookup"><span data-stu-id="a4b71-143">If the property is not set, the task posts an error, and returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Failure> from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration.</span></span> <span data-ttu-id="a4b71-144">Il metodo `Validate` è incluso in un blocco try/catch e genera errori di convalida se si verifica un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a4b71-144">The `Validate` method is wrapped in a try/catch block, and fails validation if an exception occurs.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

public class SampleTask : Task
{
  private string userName = "";

  public override DTSExecResult Validate(Connections connections,
     VariableDispenser variableDispenser, IDTSComponentEvents events,
     IDTSLogging log)
  {
    try
    {
      if (this.userName == "")
      {
        //   Raise an OnError event.
        events.FireError(0, "SampleTask", "The UserName property must be configured.", "", 0);
        //   Fail validation.
        return DTSExecResult.Failure;
      }
      //   Return success.
      return DTSExecResult.Success;
    }
    catch (System.Exception exception)
    {
      //   Capture exceptions, post an error, and fail validation.
      events.FireError(0, "Sampletask", exception.Message, "", 0);
      return DTSExecResult.Failure;
    }
  }
  public string UserName
  {
    get
    {
      return this.userName;
    }
    set
    {
      this.userName = value;
    }
  }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Runtime

Public Class SampleTask
  Inherits Task

  Private _userName As String = ""

  Public Overrides Function Validate(ByVal connections As Connections, _
     ByVal variableDispenser As VariableDispenser, _
     ByVal events As IDTSComponentEvents, _
     ByVal log As IDTSLogging) As DTSExecResult

    Try
      If Me._userName = "" Then
        '   Raise an OnError event.
        events.FireError(0, "SampleTask", "The UserName property must be configured.", "", 0)
        '   Fail validation.
        Return DTSExecResult.Failure
      End If
      '   Return success.
      Return DTSExecResult.Success
    Catch exception As System.Exception
      '   Capture exceptions, post an error, and fail validation.
      events.FireError(0, "Sampletask", exception.Message, "", 0)
      Return DTSExecResult.Failure
    End Try

  End Function

  Public Property UserName() As String
    Get
      Return Me._userName
    End Get
    Set(ByVal Value As String)
      Me._userName = Value
    End Set
  End Property

End Class
```

### <a name="persisting-the-task"></a><span data-ttu-id="a4b71-145">Persistenza dell'attività</span><span class="sxs-lookup"><span data-stu-id="a4b71-145">Persisting the Task</span></span>
 <span data-ttu-id="a4b71-146">In genere non è necessario implementare la persistenza personalizzata per un'attività.</span><span class="sxs-lookup"><span data-stu-id="a4b71-146">Ordinarily you do not have to implement custom persistence for a task.</span></span> <span data-ttu-id="a4b71-147">La persistenza personalizzata è richiesta solo quando le proprietà di un oggetto utilizzano tipi di dati complessi.</span><span class="sxs-lookup"><span data-stu-id="a4b71-147">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="a4b71-148">Per altre informazioni, vedere [Sviluppo di oggetti personalizzati per Integration Services](../developing-custom-objects-for-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="a4b71-148">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>

## <a name="executing-the-task"></a><span data-ttu-id="a4b71-149">Esecuzione dell'attività</span><span class="sxs-lookup"><span data-stu-id="a4b71-149">Executing the Task</span></span>
 <span data-ttu-id="a4b71-150">In questa sezione viene descritto come utilizzare il metodo `Execute` ereditato e sottoposto a override dalle attività.</span><span class="sxs-lookup"><span data-stu-id="a4b71-150">This section describes how to use the `Execute` method that is inherited and overridden by tasks.</span></span> <span data-ttu-id="a4b71-151">Vengono inoltre illustrate varie modalità con cui fornire informazioni sui risultati dell'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="a4b71-151">This section also explains various ways of providing information about the results of task execution.</span></span>

### <a name="execute-method"></a><span data-ttu-id="a4b71-152">Metodo Execute</span><span class="sxs-lookup"><span data-stu-id="a4b71-152">Execute Method</span></span>
 <span data-ttu-id="a4b71-153">Le attività contenute in un pacchetto vengono eseguite quando il runtime di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] chiama il relativo metodo `Execute`.</span><span class="sxs-lookup"><span data-stu-id="a4b71-153">Tasks that are contained in a package run when the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime calls their `Execute` method.</span></span> <span data-ttu-id="a4b71-154">Le attività implementano la logica di business e le funzionalità principali in questo metodo e forniscono i risultati dell'esecuzione inviando messaggi, restituendo un valore dall'enumerazione <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> ed eseguendo l'override della proprietà `get` della proprietà `ExecutionValue`.</span><span class="sxs-lookup"><span data-stu-id="a4b71-154">Tasks implement their core business logic and functionality in this method, and provide the results of execution by posting messages, returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration, and overriding the property `get` of the `ExecutionValue` property.</span></span>

 <span data-ttu-id="a4b71-155">La classe di base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) specifica un'implementazione predefinita del metodo <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4b71-155">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class provides a default implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span> <span data-ttu-id="a4b71-156">Le attività personalizzate eseguono l'override di questo metodo per definire le funzionalità di runtime.</span><span class="sxs-lookup"><span data-stu-id="a4b71-156">The custom tasks override this method to define their run-time functionality.</span></span> <span data-ttu-id="a4b71-157">L'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> esegue il wrapping dell'attività, isolandola dal motore di runtime e dagli altri oggetti nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a4b71-157">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object wraps the task, isolating it from the run-time engine and the other objects in the package.</span></span> <span data-ttu-id="a4b71-158">A causa di questo isolamento, l'ordine di esecuzione dell'attività è indipendente dalla relativa posizione nel pacchetto e l'attività viene eseguita solo quando viene chiamata dal runtime.</span><span class="sxs-lookup"><span data-stu-id="a4b71-158">Because of this isolation, the task is unaware of its location in the package with regard to its execution order, and runs only when it is called by the runtime.</span></span> <span data-ttu-id="a4b71-159">Questa architettura consente di evitare i problemi che possono verificarsi quando le attività modificano il pacchetto durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a4b71-159">This architecture prevents problems that can occur when tasks modify the package during execution.</span></span> <span data-ttu-id="a4b71-160">L'attività dispone di accesso agli altri oggetti del pacchetto solo tramite gli oggetti forniti come parametri nel metodo <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4b71-160">The task is provided access to the other objects in the package only through the objects supplied to it as parameters in the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span> <span data-ttu-id="a4b71-161">Questi parametri consentono alle attività di generare eventi, scrivere voci nel log eventi, accedere alla raccolta di variabili e integrare le connessioni a origini dati nelle transazioni, mantenendo allo stesso tempo l'isolamento necessario per garantire la stabilità e l'affidabilità del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a4b71-161">These parameters let tasks raise events, write entries to the event log, access the variables collection, and enlist connections to data sources in transactions, while still maintaining the isolation that is necessary to guarantee the stability and reliability of the package.</span></span>

 <span data-ttu-id="a4b71-162">Nella tabella seguente sono riportati i parametri forniti all'attività nel metodo <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4b71-162">The following table lists the parameters provided to the task in the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span>

|<span data-ttu-id="a4b71-163">Parametro</span><span class="sxs-lookup"><span data-stu-id="a4b71-163">Parameter</span></span>|<span data-ttu-id="a4b71-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4b71-164">Description</span></span>|
|---------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Runtime.Connections>|<span data-ttu-id="a4b71-165">Contiene una raccolta di oggetti <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> disponibili per l'attività.</span><span class="sxs-lookup"><span data-stu-id="a4b71-165">Contains a collection of <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects available to the task.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.VariableDispenser>|<span data-ttu-id="a4b71-166">Contiene le variabili disponibili per l'attività.</span><span class="sxs-lookup"><span data-stu-id="a4b71-166">Contains the variables available to the task.</span></span> <span data-ttu-id="a4b71-167">Le attività utilizzano le variabili tramite VariableDispenser, non direttamente.</span><span class="sxs-lookup"><span data-stu-id="a4b71-167">The tasks use variables through the VariableDispenser; the tasks do not use variables directly.</span></span> <span data-ttu-id="a4b71-168">VariableDispenser blocca e sblocca le variabili e impedisce il verificarsi di deadlock o sovrascritture.</span><span class="sxs-lookup"><span data-stu-id="a4b71-168">The variable dispenser locks and unlocks variables, and prevents deadlocks or overwrites.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents>|<span data-ttu-id="a4b71-169">Contiene i metodi chiamati dall'attività per generare eventi nel motore di runtime.</span><span class="sxs-lookup"><span data-stu-id="a4b71-169">Contains the methods called by the task to raise events to the run-time engine.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSLogging>|<span data-ttu-id="a4b71-170">Contiene i metodi e le proprietà utilizzati dall'attività per scrivere voci nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="a4b71-170">Contains methods and properties used by the task to write entries to the event log.</span></span>|
|<span data-ttu-id="a4b71-171">Oggetto</span><span class="sxs-lookup"><span data-stu-id="a4b71-171">Object</span></span>|<span data-ttu-id="a4b71-172">Contiene l'oggetto transazione di cui fa parte il contenitore, se presente.</span><span class="sxs-lookup"><span data-stu-id="a4b71-172">Contains the transaction object that the container is a part of, if any.</span></span> <span data-ttu-id="a4b71-173">Questo valore viene passato come parametro al metodo <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> di un oggetto <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="a4b71-173">This value is passed as a parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object.</span></span>|

### <a name="providing-execution-feedback"></a><span data-ttu-id="a4b71-174">Feedback dell'esecuzione</span><span class="sxs-lookup"><span data-stu-id="a4b71-174">Providing Execution Feedback</span></span>
 <span data-ttu-id="a4b71-175">Le attività includono il codice in blocchi `try/catch` per evitare che vengano generate eccezioni nel motore di runtime.</span><span class="sxs-lookup"><span data-stu-id="a4b71-175">Tasks wrap their code in `try/catch` blocks to prevent exceptions from being raised to the run-time engine.</span></span> <span data-ttu-id="a4b71-176">In questo modo l'esecuzione del pacchetto viene completata senza arresti imprevisti.</span><span class="sxs-lookup"><span data-stu-id="a4b71-176">This ensures that the package finishes execution and does not stop unexpectedly.</span></span> <span data-ttu-id="a4b71-177">Tuttavia, il motore di runtime prevede altri meccanismi per la gestione delle condizioni di errore che possono verificarsi durante l'esecuzione di un'attività,</span><span class="sxs-lookup"><span data-stu-id="a4b71-177">However, the run-time engine provides other mechanisms for handling error conditions that can occur during the execution of a task.</span></span> <span data-ttu-id="a4b71-178">tra cui l'invio di messaggi di errore e di avviso, la restituzione di un valore dalla struttura <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>, l'invio di messaggi, la restituzione del valore <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> e la diffusione di informazioni sui risultati dell'esecuzione dell'attività tramite la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.Task.ExecutionValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4b71-178">These include posting error and warning messages, returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> structure, posting messages, returning the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value, and disclosing information about the results of task execution through the <xref:Microsoft.SqlServer.Dts.Runtime.Task.ExecutionValue%2A> property.</span></span>

 <span data-ttu-id="a4b71-179">L'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> contiene i metodi <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>, che possono essere chiamati dall'attività per inviare messaggi di errore e di avviso al motore di runtime.</span><span class="sxs-lookup"><span data-stu-id="a4b71-179">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface contains the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods, which can be called by the task to post error and warning messages to the run-time engine.</span></span> <span data-ttu-id="a4b71-180">Entrambi i metodi richiedono parametri quali il codice di errore, il componente di origine, il file della Guida e informazioni di contesto della Guida.</span><span class="sxs-lookup"><span data-stu-id="a4b71-180">Both methods require parameters such as the error code, source component, description, Help file, and help context information.</span></span> <span data-ttu-id="a4b71-181">A seconda della configurazione dell'attività, il runtime risponde a questi messaggi generando eventi e punti di interruzione oppure scrivendo informazioni nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="a4b71-181">Depending on the configuration of the task, the runtime responds to these messages by raising events and breakpoints, or by writing information to the event log.</span></span>

 <span data-ttu-id="a4b71-182"><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> fornisce anche la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A>, che può essere utilizzata per fornire informazioni aggiuntive sui risultati dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a4b71-182">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> also provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property that can be used to provide additional information about the results of execution.</span></span> <span data-ttu-id="a4b71-183">Se ad esempio un'attività elimina righe da una tabella come parte del metodo `Execute`, potrebbe restituire il numero di righe eliminate come valore della proprietà <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4b71-183">For example, if a task deletes rows from a table as part of its `Execute` method, it might return the number of rows deleted as the value of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property.</span></span> <span data-ttu-id="a4b71-184">Inoltre, <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> fornisce la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecValueVariable%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4b71-184">In addition, the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecValueVariable%2A> property.</span></span> <span data-ttu-id="a4b71-185">Questa proprietà consente all'utente di eseguire il mapping dell'oggetto<xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> restituito dall'attività con qualsiasi variabile visibile all'attività.</span><span class="sxs-lookup"><span data-stu-id="a4b71-185">This property lets the user map the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> returned from the task to any variable visible to the task.</span></span> <span data-ttu-id="a4b71-186">La variabile specificata può quindi essere utilizzata per stabilire vincoli di precedenza tra attività.</span><span class="sxs-lookup"><span data-stu-id="a4b71-186">The specified variable can then be used to establish precedence constraints between tasks.</span></span>

### <a name="execution-example"></a><span data-ttu-id="a4b71-187">Esempio di esecuzione</span><span class="sxs-lookup"><span data-stu-id="a4b71-187">Execution Example</span></span>
 <span data-ttu-id="a4b71-188">Nell'esempio di codice seguente è illustrata un'implementazione del metodo `Execute` e viene mostrata una proprietà `ExecutionValue` sottoposta a override.</span><span class="sxs-lookup"><span data-stu-id="a4b71-188">The following code example demonstrates an implementation of the `Execute` method, and shows an overridden `ExecutionValue` property.</span></span> <span data-ttu-id="a4b71-189">L'attività elimina il file specificato dalla proprietà `fileName` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="a4b71-189">The task deletes the file that is specified by the `fileName` property of the task.</span></span> <span data-ttu-id="a4b71-190">L'attività invia un avviso se il file non esiste o se la proprietà `fileName` è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="a4b71-190">The task posts a warning if the file does not exist, or if the `fileName` property is an empty string.</span></span> <span data-ttu-id="a4b71-191">L'attività restituisce un valore `Boolean` nella proprietà <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> per indicare se il file è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="a4b71-191">The task returns a `Boolean` value in the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property to indicate whether the file was deleted.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

public class SampleTask : Task
{
  private string fileName = "";
  private bool fileDeleted = false;

  public override DTSExecResult Execute(Connections cons,
     VariableDispenser vars, IDTSComponentEvents events,
     IDTSLogging log, Object txn)
  {
    try
    {
      if (this.fileName == "")
      {
        events.FireWarning(0, "SampleTask", "No file specified.", "", 0);
        this.fileDeleted = false;
      }
      else
      {
        if (System.IO.File.Exists(this.fileName))
        {
          System.IO.File.Delete(this.fileName);
          this.fileDeleted = true;
        }
        else
          this.fileDeleted = false;
      }
      return DTSExecResult.Success;
    }
    catch (System.Exception exception)
    {
      //   Capture the exception and post an error.
      events.FireError(0, "Sampletask", exception.Message, "", 0);
      return DTSExecResult.Failure;
    }
  }
  public string FileName
  {
    get { return this.fileName; }
    set { this.fileName = value; }
  }
  public override object ExecutionValue
  {
    get { return this.fileDeleted; }
  }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Runtime

Public Class SampleTask
  Inherits Task

  Private _fileName As String = ""
  Private _fileDeleted As Boolean = False

  Public Overrides Function Execute(ByVal cons As Connections, _
     ByVal vars As VariableDispenser, ByVal events As IDTSComponentEvents, _
     ByVal log As IDTSLogging, ByVal txn As Object) As DTSExecResult

    Try
      If Me._fileName = "" Then
        events.FireWarning(0, "SampleTask", "No file specified.", "", 0)
        Me._fileDeleted = False
      Else
        If System.IO.File.Exists(Me._fileName) Then
          System.IO.File.Delete(Me._fileName)
          Me._fileDeleted = True
        Else
          Me._fileDeleted = False
        End If
      End If
      Return DTSExecResult.Success
    Catch exception As System.Exception
      '   Capture the exception and post an error.
      events.FireError(0, "Sampletask", exception.Message, "", 0)
      Return DTSExecResult.Failure
    End Try

  End Function

  Public Property FileName() As String
    Get
      Return Me._fileName
    End Get
    Set(ByVal Value As String)
      Me._fileName = Value
    End Set
  End Property

  Public Overrides ReadOnly Property ExecutionValue() As Object
    Get
      Return Me._fileDeleted
    End Get
  End Property

End Class
```

<span data-ttu-id="a4b71-192">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a4b71-192">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a4b71-193">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="a4b71-193">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a4b71-194">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="a4b71-194">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a4b71-195">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="a4b71-195">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4b71-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4b71-196">See Also</span></span>
 <span data-ttu-id="a4b71-197">[Creazione di un'attività personalizzata](creating-a-custom-task.md) che [codifica un'attività](coding-a-custom-task.md) personalizzata [sviluppo di un'interfaccia utente per un'attività personalizzata](developing-a-user-interface-for-a-custom-task.md)</span><span class="sxs-lookup"><span data-stu-id="a4b71-197">[Creating a Custom Task](creating-a-custom-task.md) [Coding a Custom Task](coding-a-custom-task.md) [Developing a User Interface for a Custom Task](developing-a-user-interface-for-a-custom-task.md)</span></span>


