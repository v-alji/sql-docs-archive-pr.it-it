---
title: Monitoraggio dei contatori delle prestazioni con l'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- performance counters [Integration Services]
- SSIS Script task, performance counters
- custom performance counters [Integration Services]
- Script task [Integration Services], examples
- Script task [Integration Services], performance counters
- counters [Integration Services]
ms.assetid: 86609bf1-cae6-435e-a58d-41bdfc521e94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 143e11ff966eb11961aa15073a503522c4b9c86b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721611"
---
# <a name="monitoring-performance-counters-with-the-script-task"></a><span data-ttu-id="6c02b-102">Monitoraggio dei contatori delle prestazioni con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="6c02b-102">Monitoring Performance Counters with the Script Task</span></span>
  <span data-ttu-id="6c02b-103">È possibile che gli amministratori abbiano l'esigenza di monitorare le prestazioni dei pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che eseguono trasformazioni complesse su grandi quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="6c02b-103">Administrators may need to monitor the performance of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that perform complex transformations on large amounts of data.</span></span> <span data-ttu-id="6c02b-104">Lo spazio dei nomi **System.Diagnostics** delle classi [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] fornisce le classi per l'uso di contatori delle prestazioni esistenti e per la creazione di contatori delle prestazioni personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6c02b-104">The **System.Diagnostics** namespace of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides classes for using existing performance counters and for creating your own performance counters.</span></span>  
  
 <span data-ttu-id="6c02b-105">I contatori delle prestazioni archiviano informazioni sulle prestazioni dell'applicazione che è possibile utilizzare per analizzare le prestazioni del software nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="6c02b-105">Performance counters store application performance information that you can use to analyze the performance of software over time.</span></span> <span data-ttu-id="6c02b-106">Possono essere monitorati in locale o in remoto tramite lo strumento **Performance Monitor**.</span><span class="sxs-lookup"><span data-stu-id="6c02b-106">Performance counters can be monitored locally or remotely by using the **Performance Monitor** tool.</span></span> <span data-ttu-id="6c02b-107">È possibile archiviare i valori dei contatori delle prestazioni in variabili per una successiva diramazione del flusso di controllo nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6c02b-107">You can store the values of performance counters in variables for later control flow branching in the package.</span></span>  
  
 <span data-ttu-id="6c02b-108">In alternativa all'utilizzo dei contatori delle prestazioni, è possibile generare l'evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> tramite la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> dell'oggetto `Dts`.</span><span class="sxs-lookup"><span data-stu-id="6c02b-108">As an alternative to using performance counters, you can raise the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> event through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property of the `Dts` object.</span></span> <span data-ttu-id="6c02b-109">L'evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> restituisce al runtime di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] informazioni relative sia allo stato incrementale che alla percentuale di completamento.</span><span class="sxs-lookup"><span data-stu-id="6c02b-109">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> event returns both incremental progress and percentage complete information to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] runtime.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c02b-110">Se si desidera creare un'attività da riutilizzare più facilmente con più pacchetti, è possibile utilizzare il codice di questo esempio di attività Script come punto iniziale per un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6c02b-110">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="6c02b-111">Per altre informazioni, vedere [Sviluppo di un'attività personalizzata](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="6c02b-111">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="6c02b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c02b-112">Description</span></span>  
 <span data-ttu-id="6c02b-113">Nell'esempio seguente viene creato un contatore delle prestazioni personalizzato che viene incrementato.</span><span class="sxs-lookup"><span data-stu-id="6c02b-113">The following example creates a custom performance counter and increments the counter.</span></span> <span data-ttu-id="6c02b-114">Viene innanzitutto verificato se il contatore delle prestazioni esiste già.</span><span class="sxs-lookup"><span data-stu-id="6c02b-114">First, the example determines whether the performance counter already exists.</span></span> <span data-ttu-id="6c02b-115">Se non è stato creato, lo script chiama il metodo `Create` dell'oggetto `PerformanceCounterCategory` per crearlo.</span><span class="sxs-lookup"><span data-stu-id="6c02b-115">If the performance counter has not been created, the script calls the `Create` method of the `PerformanceCounterCategory` object to create it.</span></span> <span data-ttu-id="6c02b-116">Dopo la creazione del contatore delle prestazioni, lo script lo incrementa.</span><span class="sxs-lookup"><span data-stu-id="6c02b-116">After the performance counter has been created, the script increments the counter.</span></span> <span data-ttu-id="6c02b-117">Infine, viene seguita la procedura consigliata di chiamare il metodo `Close` sul contatore delle prestazioni quando non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="6c02b-117">Finally, the example follows the best practice of calling the `Close` method on the performance counter when it is no longer needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c02b-118">Per creare una nuova categoria di contatori delle prestazioni e un nuovo contatore delle prestazioni, è necessario disporre di diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="6c02b-118">Creating a new performance counter category and performance counter requires administrative rights.</span></span> <span data-ttu-id="6c02b-119">Inoltre, la nuova categoria e il nuovo contatore diventano persistenti nel computer dopo la creazione.</span><span class="sxs-lookup"><span data-stu-id="6c02b-119">Also, the new category and counter persist on the computer after creation.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="6c02b-120">Per configurare l'esempio di attività Script</span><span class="sxs-lookup"><span data-stu-id="6c02b-120">To configure this Script Task example</span></span>  
  
-   <span data-ttu-id="6c02b-121">Usare un' `Imports` istruzione nel codice per importare lo spazio dei nomi **System. Diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="6c02b-121">Use an `Imports` statement in your code to import the **System.Diagnostics** namespace.</span></span>  
  
### <a name="example-code"></a><span data-ttu-id="6c02b-122">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="6c02b-122">Example Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim myCounter As PerformanceCounter  
  
    Try  
        'Create the performance counter if it does not already exist.  
        If Not _  
        PerformanceCounterCategory.Exists("TaskExample") Then  
            PerformanceCounterCategory.Create("TaskExample", _  
                "Task Performance Counter Example", "Iterations", _  
                "Number of times this task has been called.")  
        End If  
  
        'Initialize the performance counter.  
        myCounter = New PerformanceCounter("TaskExample", _  
            "Iterations", String.Empty, False)  
  
        'Increment the performance counter.  
        myCounter.Increment()  
  
         myCounter.Close()  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, _  
            "Task Performance Counter Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
  
public class ScriptMain  
{  
  
public void Main()  
        {  
  
            PerformanceCounter myCounter;  
  
            try  
            {  
                //Create the performance counter if it does not already exist.  
                if (!PerformanceCounterCategory.Exists("TaskExample"))  
                {  
                    PerformanceCounterCategory.Create("TaskExample", "Task Performance Counter Example", "Iterations", "Number of times this task has been called.");  
                }  
  
                //Initialize the performance counter.  
                myCounter = new PerformanceCounter("TaskExample", "Iterations", String.Empty, false);  
  
                //Increment the performance counter.  
                myCounter.Increment();  
  
                myCounter.Close();  
                Dts.TaskResult = (int)ScriptResults.Success;  
            }  
            catch (Exception ex)  
            {  
                Dts.Events.FireError(0, "Task Performance Counter Example", ex.Message + "\r" + ex.StackTrace, String.Empty, 0);  
                Dts.TaskResult = (int)ScriptResults.Failure;  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
  
```  
  
<span data-ttu-id="6c02b-123">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="6c02b-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6c02b-124">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="6c02b-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6c02b-125">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="6c02b-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6c02b-126">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="6c02b-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
