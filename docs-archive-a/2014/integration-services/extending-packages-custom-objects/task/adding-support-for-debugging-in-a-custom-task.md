---
title: Aggiunta di supporto per il debug in un'attività personalizzata | Microsoft Docs
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
- BreakpointManager class
- breakpoints [Integration Services]
- custom tasks [Integration Services], debugging
- IDTSSuspend interface
- IDTSBreakpointSite interface
- SSIS custom tasks, debugging
- debugging [Integration Services], custom tasks
ms.assetid: 7f06e49b-0b60-4e81-97da-d32dc248264a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fcc1d0c18cd559b547eadb9c1fa77e8f143389d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629933"
---
# <a name="adding-support-for-debugging-in-a-custom-task"></a><span data-ttu-id="1504a-102">Aggiunta di supporto per il debug in un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="1504a-102">Adding Support for Debugging in a Custom Task</span></span>
  <span data-ttu-id="1504a-103">Il motore di runtime di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] consente la sospensione di pacchetti, attività e altri tipi di contenitori durante l'esecuzione tramite l'utilizzo di punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="1504a-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] run-time engine enables packages, tasks, and other types of containers to be suspended during execution by using breakpoints.</span></span> <span data-ttu-id="1504a-104">L'utilizzo di punti di interruzione consente di rivedere e correggere gli errori che impediscono la corretta esecuzione dell'applicazione o delle attività.</span><span class="sxs-lookup"><span data-stu-id="1504a-104">The use of breakpoints lets you review and correct errors that prevent your application or tasks from running correctly.</span></span> <span data-ttu-id="1504a-105">L'architettura dei punti di interruzione consente al client di valutare il valore di runtime degli oggetti nel pacchetto in determinati punti dell'esecuzione mentre l'elaborazione dell'attività è sospesa.</span><span class="sxs-lookup"><span data-stu-id="1504a-105">The breakpoint architecture enables the client to evaluate the run-time value of objects in the package at defined points of execution while task processing is suspended.</span></span>  
  
 <span data-ttu-id="1504a-106">Gli sviluppatori di attività personalizzate possono utilizzare questa architettura per creare destinazioni di punti di interruzione personalizzati utilizzando l'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> e la relativa interfaccia padre <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span><span class="sxs-lookup"><span data-stu-id="1504a-106">Custom task developers can use this architecture to create custom breakpoint targets by using the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface, and its parent interface, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span></span> <span data-ttu-id="1504a-107">L'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> definisce l'interazione tra il motore di runtime e l'attività per la creazione e la gestione di siti o destinazioni di punti di interruzione personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1504a-107">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface defines the interaction between the run-time engine and the task for creating and managing custom breakpoint sites or targets.</span></span> <span data-ttu-id="1504a-108">L'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> fornisce metodi e proprietà che vengono chiamati dal motore di runtime per notificare all'attività di sospendere o riprendere l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1504a-108">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface provides methods and properties that are called by the run-time engine to notify the task to suspend or resume its execution.</span></span>  
  
 <span data-ttu-id="1504a-109">Un sito o una destinazione di punti di interruzione è un punto nell'esecuzione dell'attività in cui l'elaborazione può essere sospesa.</span><span class="sxs-lookup"><span data-stu-id="1504a-109">A breakpoint site or target is a point in the execution of the task where processing can be suspended.</span></span> <span data-ttu-id="1504a-110">Gli utenti selezionano uno dei siti di punti di interruzione disponibili nella finestra di dialogo **Imposta punti di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="1504a-110">Users select from available breakpoint sites in the **Set Breakpoints** dialog box.</span></span> <span data-ttu-id="1504a-111">Ad esempio, oltre alle opzioni predefinite dei punti di interruzione, il contenitore Ciclo Foreach prevede l'opzione "Interrompi all'inizio di ogni iterazione del ciclo".</span><span class="sxs-lookup"><span data-stu-id="1504a-111">For example, in addition to the default breakpoint options, the Foreach Loop Container offers the "Break at the beginning of every iteration of the loop" option.</span></span>  
  
 <span data-ttu-id="1504a-112">Quando un'attività raggiunge la destinazione di un punto di interruzione durante l'esecuzione, la valuta per determinare se il punto di interruzione è abilitato.</span><span class="sxs-lookup"><span data-stu-id="1504a-112">When a task reaches a breakpoint target during execution, it evaluates the breakpoint target to determine whether a breakpoint is enabled.</span></span> <span data-ttu-id="1504a-113">Ciò indica che l'utente desidera arrestare l'esecuzione in corrispondenza di tale punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="1504a-113">This indicates that the user wants execution to stop at that breakpoint.</span></span> <span data-ttu-id="1504a-114">Se il punto di interruzione è abilitato, l'attività genera l'evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> per il motore di runtime.</span><span class="sxs-lookup"><span data-stu-id="1504a-114">If the breakpoint is enabled, the task raises the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> event to the run-time engine.</span></span> <span data-ttu-id="1504a-115">Il motore di runtime risponde all'evento chiamando il metodo `Suspend` di ogni attività attualmente in esecuzione nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1504a-115">The run-time engine responds to the event by calling the `Suspend` method of each task that is currently running in the package.</span></span> <span data-ttu-id="1504a-116">L'esecuzione dell'attività riprende quando il runtime chiama il metodo `ResumeExecution` dell'attività sospesa.</span><span class="sxs-lookup"><span data-stu-id="1504a-116">Execution of the task resumes when the runtime calls the `ResumeExecution` method of the suspended task.</span></span>  
  
 <span data-ttu-id="1504a-117">Le attività che non utilizzano punti di interruzione devono comunque implementare le interfacce <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> e <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span><span class="sxs-lookup"><span data-stu-id="1504a-117">Tasks that do not use breakpoints should still implement the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interfaces.</span></span> <span data-ttu-id="1504a-118">Ciò assicura che l'attività venga sospesa correttamente quando altri oggetti del pacchetto generano eventi <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>.</span><span class="sxs-lookup"><span data-stu-id="1504a-118">This ensures that the task is suspended correctly when other objects in the package raise <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> events.</span></span>  
  
## <a name="idtsbreakpointsite-interface-and-breakpointmanager"></a><span data-ttu-id="1504a-119">Interfaccia IDTSBreakpointSite e BreakpointManager</span><span class="sxs-lookup"><span data-stu-id="1504a-119">IDTSBreakpointSite Interface and BreakpointManager</span></span>  
 <span data-ttu-id="1504a-120">Le attività creano destinazioni di punti di interruzione chiamando il metodo <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.CreateBreakpointTarget%2A> di <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, fornendo un ID integer e una stringa descrittiva come parametri.</span><span class="sxs-lookup"><span data-stu-id="1504a-120">Tasks create breakpoint targets by calling the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.CreateBreakpointTarget%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, providing an integer ID and string description as parameters.</span></span> <span data-ttu-id="1504a-121">Quando l'attività raggiunge il punto del codice che contiene la destinazione del punto di interruzione, la valuta utilizzando il metodo <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.IsBreakpointTargetEnabled%2A> per determinare se tale punto di interruzione è abilitato.</span><span class="sxs-lookup"><span data-stu-id="1504a-121">When the task reaches the point in its code that contains a breakpoint target, it evaluates the breakpoint target by using the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.IsBreakpointTargetEnabled%2A> method to determine whether that breakpoint is enabled.</span></span> <span data-ttu-id="1504a-122">Se `true`, l'attività invia una notifica al motore di runtime generando l'evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>.</span><span class="sxs-lookup"><span data-stu-id="1504a-122">If `true`, the task notifies the run-time engine by raising the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> event.</span></span>  
  
 <span data-ttu-id="1504a-123">L'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> definisce un singolo metodo, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite.AcceptBreakpointManager%2A>, che viene chiamato dal motore di runtime durante la creazione di attività.</span><span class="sxs-lookup"><span data-stu-id="1504a-123">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface defines a single method, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite.AcceptBreakpointManager%2A>, which is called by the run-time engine during task creation.</span></span> <span data-ttu-id="1504a-124">Questo metodo fornisce come parametro l'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, che viene quindi utilizzato dall'attività per creare e gestire i propri punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="1504a-124">This method provides as a parameter the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> object, which is then used by the task to create and manage its breakpoints.</span></span> <span data-ttu-id="1504a-125">Le attività devono archiviare l'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> in locale per utilizzarlo durante i metodi `Validate` e `Execute`.</span><span class="sxs-lookup"><span data-stu-id="1504a-125">Tasks should store the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> locally for use during the `Validate` and `Execute` methods.</span></span>  
  
 <span data-ttu-id="1504a-126">Nell'esempio di codice seguente viene illustrato come creare una destinazione di punti di interruzione tramite <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>.</span><span class="sxs-lookup"><span data-stu-id="1504a-126">The following sample code demonstrates how to create a breakpoint target by using the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>.</span></span> <span data-ttu-id="1504a-127">Viene chiamato il metodo <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> per generare l'evento.</span><span class="sxs-lookup"><span data-stu-id="1504a-127">The sample calls the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> method to raise the event.</span></span>  
  
```csharp  
public void AcceptBreakpointManager( BreakpointManager breakPointManager )  
{  
   //   Store the breakpoint manager locally.  
   this.bpm  = breakPointManager;  
}  
public override DTSExecResult Execute( Connections connections,  
  Variables variables, IDTSComponentEvents events,  
  IDTSLogging log, DtsTransaction txn)  
{  
   //   Create a breakpoint.  
   this.bpm.CreateBreakPointTarget( 1 , "A sample breakpoint target." );  
...  
   if( this.bpm.IsBreakpointTargetEnabled( 1 ) == true )  
      events.OnBreakpointHit( this.bpm.GetBreakpointTarget( 1 ) );  
}  
```  
  
```vb  
Public Sub AcceptBreakpointManager(ByVal breakPointManager As BreakpointManager)  
  
   ' Store the breakpoint manager locally.  
   Me.bpm  = breakPointManager  
  
End Sub  
  
Public Overrides Function Execute(ByVal connections As Connections, _  
  ByVal variables As Variables, ByVal events As IDTSComponentEvents, _  
  ByVal log As IDTSLogging, ByVal txn As DtsTransaction) As DTSExecResult  
  
   ' Create a breakpoint.  
   Me.bpm.CreateBreakPointTarget(1 , "A sample breakpoint target.")  
  
   If Me.bpm.IsBreakpointTargetEnabled(1) = True Then  
      events.OnBreakpointHit(Me.bpm.GetBreakpointTarget(1))  
   End If  
  
End Function  
```  
  
## <a name="idtssuspend-interface"></a><span data-ttu-id="1504a-128">Interfaccia IDTSSuspend</span><span class="sxs-lookup"><span data-stu-id="1504a-128">IDTSSuspend Interface</span></span>  
 <span data-ttu-id="1504a-129">L'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> definisce i metodi che vengono chiamati dal motore di runtime quando sospende o riprende l'esecuzione di un'attività.</span><span class="sxs-lookup"><span data-stu-id="1504a-129">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface defines the methods that are called by the run-time engine when it pauses or resumes execution of a task.</span></span> <span data-ttu-id="1504a-130">L'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> viene implementata dall'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> e i relativi metodi `Suspend` e `ResumeExecution` vengono in genere sottoposti a override dall'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1504a-130">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface is implemented by the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface, and its `Suspend` and `ResumeExecution` methods are usually overridden by the custom task.</span></span> <span data-ttu-id="1504a-131">Quando il motore di runtime riceve un evento `OnBreakpointHit` da un'attività, chiama il metodo `Suspend` di ogni attività in esecuzione, notificando la pausa alle attività.</span><span class="sxs-lookup"><span data-stu-id="1504a-131">When the run-time engine receives an `OnBreakpointHit` event from a task, it calls the `Suspend` method of each running task, notifying the tasks to pause.</span></span> <span data-ttu-id="1504a-132">Quando il client riprende l'esecuzione, il motore di runtime chiama il metodo `ResumeExecution` delle attività sospese.</span><span class="sxs-lookup"><span data-stu-id="1504a-132">When the client resumes execution, the run-time engine calls the `ResumeExecution` method of the tasks that are suspended.</span></span>  
  
 <span data-ttu-id="1504a-133">La sospensione e la ripresa dell'esecuzione di un'attività implica la sospensione e la ripresa del thread di esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1504a-133">Suspending and resuming task execution involves pausing and resuming the task's execution thread.</span></span> <span data-ttu-id="1504a-134">Nel codice gestito questo risultato si ottiene utilizzando la classe `ManualResetEvent` nello spazio dei nomi `System.Threading` di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1504a-134">In managed code, you do this using the `ManualResetEvent` class in `System.Threading` namespace of the .NET Framework.</span></span>  
  
 <span data-ttu-id="1504a-135">Nell'esempio di codice seguente vengono illustrate la sospensione e la ripresa dell'esecuzione di un'attività.</span><span class="sxs-lookup"><span data-stu-id="1504a-135">The following code sample demonstrates suspension and resumption of task execution.</span></span> <span data-ttu-id="1504a-136">Si noti che il metodo `Execute` è diverso rispetto all'esempio di codice precedente e che il thread di esecuzione è in pausa quando viene attivato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="1504a-136">Notice that the `Execute` method has changed from the previous code sample, and the execution thread is paused when firing the breakpoint.</span></span>  
  
```csharp  
private ManualResetEvent m_suspended = new ManualResetEvent( true );  
private ManualResetEvent m_canExecute = new ManualResetEvent( true );  
private int   m_suspendRequired = 0;  
private int   m_debugMode = 0;  
  
public override DTSExecResult Execute( Connections connections, Variables variables, IDTSComponentEvents events, IDTSLogging log, DtsTransaction txn)  
{  
   // While a task is not executing, it is suspended.    
   // Now that we are executing,  
   // change to not suspended.  
   ChangeEvent(m_suspended, false);  
  
   // Check for a suspend before doing any work,   
   // in case the suspend and execute calls  
   // were initiated at virtually the same time.  
   CheckAndSuspend();  
   CheckAndFireBreakpoint( componentEvents, 1);  
}  
private void CheckAndSuspend()  
{  
   // Loop until we can execute.    
   // The loop is required rather than a simple If  
   // because there is a time between the return from WaitOne and the  
   // reset that we might receive another Suspend call.    
   // Suspend() will see that we are suspended  
   // and return.  So we need to rewait.  
   while (!m_canExecute.WaitOne(0, false))  
   {  
      ChangeEvent(m_suspended, true);  
      m_canExecute.WaitOne();  
      ChangeEvent(m_suspended, false);  
   }  
}  
private void CheckAndFireBreakpoint(IDTSComponentEvents events, int breakpointID)  
{  
   // If the breakpoint is enabled, fire it.  
   if (m_debugMode != 0 &&    this.bpm.IsBreakpointTargetEnabled(breakpointID))  
   {  
      //   Enter a suspend mode before firing the breakpoint.    
      //   Firing the breakpoint will cause the runtime   
      //   to call Suspend on this task.    
      //   Because we are blocked on the breakpoint,   
      //   we are suspended.  
      ChangeEvent(m_suspended, true);  
      events.OnBreakpointHit(this.bpm.GetBreakpointTarget(breakpointID));  
      ChangeEvent(m_suspended, false);  
   }  
   // Check for a suspension for two reasons:   
   //   1. If we are at a point where we could fire a breakpoint,   
   //      we are at a valid suspend point.  Even if we didn't hit a  
   //      breakpoint, the runtime may have called suspend,   
   //      so check for it.       
   //   2. Between the return from OnBreakpointHit   
   //      and the reset of the event, it is possible to have  
   //      received a suspend call from which we returned because   
   //      we were already suspended.  We need to be sure it is okay  
   //      to continue executing now.  
   CheckAndSuspend();  
}  
static void ChangeEvent(ManualResetEvent e, bool shouldSet)  
{  
   bool succeeded;  
   if (shouldSet)  
      succeeded = e.Set();  
   else  
      succeeded = e.Reset();  
  
   if (!succeeded)  
      throw new Exception("Synchronization object failed.");  
  
}  
public bool SuspendRequired  
{  
   get   {return m_suspendRequired != 0;}  
   set  
   {  
      // This lock is also taken by Suspend().    
      // Because it is possible for the package to be  
      // suspended and resumed in quick succession,   
      // this property might be set before  
      // the actual Suspend() call.    
      // Without the lock, the Suspend() might reset the canExecute  
      // event after we set it to abort the suspension.  
      lock (this)  
      {  
         Interlocked.Exchange(ref m_suspendRequired, value ? 1 : 0);  
         if (!value)  
            ResumeExecution();  
      }  
   }  
}  
public void ResumeExecution()  
{  
   ChangeEvent( m_canExecute,true );  
}  
public void Suspend()  
{  
   // This lock is also taken by the set SuspendRequired method.    
   // It prevents this call from overriding an   
   // aborted suspension.  See comments in set SuspendRequired.  
   lock (this)  
   {  
      // If a Suspend is required, do it.  
      if (m_suspendRequired != 0)  
         ChangeEvent(m_canExecute, false);  
   }  
   // We can't return from Suspend until the task is "suspended".  
   // This can happen one of two ways:   
   // the m_suspended event occurs, indicating that the execute thread  
   // has suspended, or the canExecute flag is set,   
   // indicating that a suspend is no longer required.  
   WaitHandle [] suspendOperationComplete = {m_suspended, m_canExecute};  
   WaitHandle.WaitAny(suspendOperationComplete);  
}  
```  
  
```vb  
Private m_suspended As ManualResetEvent = New ManualResetEvent(True)  
Private m_canExecute As ManualResetEvent = New ManualResetEvent(True)  
Private m_suspendRequired As Integer = 0  
Private m_debugMode As Integer = 0  
  
Public Overrides Function Execute(ByVal connections As Connections, _  
ByVal variables As Variables, ByVal events As IDTSComponentEvents, _  
ByVal log As IDTSLogging, ByVal txn As DtsTransaction) As DTSExecResult  
  
   ' While a task is not executing it is suspended.    
   ' Now that we are executing,  
   ' change to not suspended.  
   ChangeEvent(m_suspended, False)  
  
   ' Check for a suspend before doing any work,   
   ' in case the suspend and execute calls  
   ' were initiated at virtually the same time.  
   CheckAndSuspend()  
   CheckAndFireBreakpoint(componentEvents, 1)  
  
End Function  
  
Private Sub CheckAndSuspend()  
  
   ' Loop until we can execute.    
   ' The loop is required rather than a simple if  
   ' because there is a time between the return from WaitOne and the  
   ' reset that we might receive another Suspend call.    
   ' Suspend() will see that we are suspended  
   ' and return.  So we need to rewait.  
   Do While Not m_canExecute.WaitOne(0, False)  
              ChangeEvent(m_suspended, True)  
              m_canExecute.WaitOne()  
              ChangeEvent(m_suspended, False)  
   Loop  
  
End Sub  
  
Private Sub CheckAndFireBreakpoint(ByVal events As IDTSComponentEvents, _  
ByVal breakpointID As Integer)  
  
   ' If the breakpoint is enabled, fire it.  
   If m_debugMode <> 0 AndAlso Me.bpm.IsBreakpointTargetEnabled(breakpointID) Then  
              '   Enter a suspend mode before firing the breakpoint.    
              '   Firing the breakpoint will cause the runtime   
              '   to call Suspend on this task.    
              '   Because we are blocked on the breakpoint,   
              '   we are suspended.  
              ChangeEvent(m_suspended, True)  
              events.OnBreakpointHit(Me.bpm.GetBreakpointTarget(breakpointID))  
              ChangeEvent(m_suspended, False)  
   End If  
  
   ' Check for a suspension for two reasons:   
   '   1. If we are at a point where we could fire a breakpoint,   
   '         we are at a valid suspend point.  Even if we didn't hit a  
   '         breakpoint, the runtime may have called suspend,   
   '         so check for it.     
   '   2. Between the return from OnBreakpointHit   
   '         and the reset of the event, it is possible to have  
   '         received a suspend call from which we returned because   
   '         we were already suspended.  We need to be sure it is okay  
   '         to continue executing now.  
   CheckAndSuspend()  
  
End Sub  
  
Shared Sub ChangeEvent(ByVal e As ManualResetEvent, ByVal shouldSet As Boolean)  
  
   Dim succeeded As Boolean  
   If shouldSet Then  
              succeeded = e.Set()  
   Else  
              succeeded = e.Reset()  
   End If  
  
   If (Not succeeded) Then  
              Throw New Exception("Synchronization object failed.")  
   End If  
  
End Sub  
  
Public Property SuspendRequired() As Boolean  
   Get  
               Return m_suspendRequired <> 0  
  End Get  
  Set  
    ' This lock is also taken by Suspend().    
     '   Because it is possible for the package to be  
     '   suspended and resumed in quick succession,   
     '   this property might be set before  
     '   the actual Suspend() call.    
     '   Without the lock, the Suspend() might reset the canExecute  
     '   event after we set it to abort the suspension.  
              SyncLock Me  
                         Interlocked.Exchange(m_suspendRequired,IIf(Value, 1, 0))  
                         If (Not Value) Then  
                                    ResumeExecution()  
                         End If  
              End SyncLock  
   End Set  
End Property  
  
Public Sub ResumeExecution()  
   ChangeEvent(m_canExecute,True)  
End Sub  
  
Public Sub Suspend()  
  
   ' This lock is also taken by the set SuspendRequired method.    
   ' It prevents this call from overriding an   
   ' aborted suspension.  See comments in set SuspendRequired.  
   SyncLock Me  
   ' If a Suspend is required, do it.  
              If m_suspendRequired <> 0 Then  
                         ChangeEvent(m_canExecute, False)  
              End If  
   End SyncLock  
   ' We can't return from Suspend until the task is "suspended".  
   ' This can happen one of two ways:   
   ' the m_suspended event occurs, indicating that the execute thread  
   ' has suspended, or the canExecute flag is set,   
   ' indicating that a suspend is no longer required.  
   Dim suspendOperationComplete As WaitHandle() = {m_suspended, m_canExecute}  
   WaitHandle.WaitAny(suspendOperationComplete)  
  
End Sub  
```  
  
<span data-ttu-id="1504a-137">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="1504a-137">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="1504a-138">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="1504a-138">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="1504a-139">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="1504a-139">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="1504a-140">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="1504a-140">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1504a-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1504a-141">See Also</span></span>  
 [<span data-ttu-id="1504a-142">Debug del flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="1504a-142">Debugging Control Flow</span></span>](../../troubleshooting/debugging-control-flow.md)  
  
  
