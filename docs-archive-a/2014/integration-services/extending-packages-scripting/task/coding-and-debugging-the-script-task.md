---
title: Codifica e debug dell'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], debugging
- SSIS Script task, development environment
- SSIS Script task, debugging
- Script task [Integration Services], development environment
- Script task [Integration Services], coding
- debugging [Integration Services], scripts
- VSTA
- SSIS Script task, coding
ms.assetid: 687c262f-fcab-42e8-92ae-e956f3d92d69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0f4383469368ac1fe3c70ff82f8c8bb2cf755838
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712175"
---
# <a name="coding-and-debugging-the-script-task"></a><span data-ttu-id="546d5-102">Scrittura di codice e debug dell'attività Script</span><span class="sxs-lookup"><span data-stu-id="546d5-102">Coding and Debugging the Script Task</span></span>
  <span data-ttu-id="546d5-103">Dopo avere configurato l'attività Script in **Editor attività Script**, scrivere il codice personalizzato nell'ambiente di sviluppo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="546d5-103">After configuring the Script task in the **Script Task Editor**, you write your custom code in the Script task development environment.</span></span>

## <a name="script-task-development-environment"></a><span data-ttu-id="546d5-104">Ambiente di sviluppo dell'attività Script</span><span class="sxs-lookup"><span data-stu-id="546d5-104">Script Task Development Environment</span></span>
 <span data-ttu-id="546d5-105">Per l'attività Script viene usato [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) come ambiente di sviluppo per lo script stesso.</span><span class="sxs-lookup"><span data-stu-id="546d5-105">The Script task uses [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) as the development environment for the script itself.</span></span>

 <span data-ttu-id="546d5-106">Il codice di script viene scritto in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="546d5-106">Script code is written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="546d5-107">Specificare il linguaggio di script impostando la proprietà **ScriptLanguage** in **Editor attività Script**.</span><span class="sxs-lookup"><span data-stu-id="546d5-107">You specify the script language by setting the **ScriptLanguage** property in the **Script Task Editor**.</span></span> <span data-ttu-id="546d5-108">Se si preferisce utilizzare un altro linguaggio di programmazione, è possibile sviluppare un assembly personalizzato nel linguaggio desiderato e chiamarne la funzionalità dal codice nell'attività Script.</span><span class="sxs-lookup"><span data-stu-id="546d5-108">If you prefer to use another programming language, you can develop a custom assembly in your language of choice and call its functionality from the code in the Script task.</span></span>

 <span data-ttu-id="546d5-109">Lo script creato nell'attività Script viene archiviato nella definizione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="546d5-109">The script that you create in the Script task is stored in the package definition.</span></span> <span data-ttu-id="546d5-110">Non viene creato un file script separato.</span><span class="sxs-lookup"><span data-stu-id="546d5-110">There is no separate script file.</span></span> <span data-ttu-id="546d5-111">Pertanto, l'utilizzo dell'attività Script non ha effetto sulla distribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="546d5-111">Therefore, the use of the Script task does not affect package deployment.</span></span>

> [!NOTE]
>  <span data-ttu-id="546d5-112">Quando si progetta il pacchetto e si esegue il debug dello script, il codice di script viene scritto temporaneamente in un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="546d5-112">When you design the package and debug the script, the script code is temporarily written to a project file.</span></span> <span data-ttu-id="546d5-113">Poiché l'archiviazione di informazioni riservate in un file costituisce un potenziale rischio per la sicurezza, è consigliabile non inserire nel codice di script informazioni di questo tipo, ad esempio le password.</span><span class="sxs-lookup"><span data-stu-id="546d5-113">Because storing sensitive information in a file is a potential security risk, we recommend that you do not include sensitive information such as passwords in the script code.</span></span>

 <span data-ttu-id="546d5-114">Per impostazione predefinita, `Option Strict` è disabilitato nell'IDE.</span><span class="sxs-lookup"><span data-stu-id="546d5-114">By default, `Option Strict` is disabled in the IDE.</span></span>

## <a name="script-task-project-structure"></a><span data-ttu-id="546d5-115">Struttura di progetto dell'attività Script</span><span class="sxs-lookup"><span data-stu-id="546d5-115">Script Task Project Structure</span></span>
 <span data-ttu-id="546d5-116">Quando si crea o si modifica lo script contenuto in un'attività Script, VSTA apre un nuovo progetto vuoto o riapre il progetto esistente.</span><span class="sxs-lookup"><span data-stu-id="546d5-116">When you create or modify the script that is contained in a Script task, VSTA opens an empty new project or reopens the existing project.</span></span> <span data-ttu-id="546d5-117">La creazione di questo progetto VSTA non influisce sulla distribuzione del pacchetto, perché il progetto viene salvato nel file del pacchetto; l'attività Script non crea file aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="546d5-117">The creation of this VSTA project does not affect the deployment of the package, because the project is saved inside the package file; the Script task does not create additional files.</span></span>

### <a name="project-items-and-classes-in-the-script-task-project"></a><span data-ttu-id="546d5-118">Elementi e classi del progetto dell'attività Script</span><span class="sxs-lookup"><span data-stu-id="546d5-118">Project Items and Classes in the Script Task Project</span></span>
 <span data-ttu-id="546d5-119">Per impostazione predefinita, il progetto dell'attività Script visualizzato nella finestra Esplora progetti in VSTA contiene un singolo elemento, `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="546d5-119">By default, the Script task project displayed in the VSTA Project Explorer window contains a single item, `ScriptMain`.</span></span> <span data-ttu-id="546d5-120">L'elemento `ScriptMain` contiene a sua volta una singola classe, anch'essa denominata `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="546d5-120">The `ScriptMain` item, in turn, contains a single class, also named `ScriptMain`.</span></span> <span data-ttu-id="546d5-121">Gli elementi di codice nella classe variano a seconda del linguaggio di programmazione selezionato per l'attività Script:</span><span class="sxs-lookup"><span data-stu-id="546d5-121">The code elements in the class vary depending on the programming language that you selected for the Script task:</span></span>

-   <span data-ttu-id="546d5-122">Quando l'attività script è configurata per il [!INCLUDE[vb_orcas_long](../../../includes/vb-orcas-long-md.md)] linguaggio di programmazione, la `ScriptMain` classe include una subroutine Public, `Main` .</span><span class="sxs-lookup"><span data-stu-id="546d5-122">When the Script task is configured for the [!INCLUDE[vb_orcas_long](../../../includes/vb-orcas-long-md.md)] programming language, the `ScriptMain` class has a public subroutine, `Main`.</span></span> <span data-ttu-id="546d5-123">La subroutine `ScriptMain.Main` è il metodo chiamato dal runtime quando si esegue l'attività Script.</span><span class="sxs-lookup"><span data-stu-id="546d5-123">The `ScriptMain.Main` subroutine is the method that the runtime calls when you run your Script task.</span></span>

     <span data-ttu-id="546d5-124">Per impostazione predefinita, nella subroutine `Main` di un nuovo script è presente solo il codice costituito dalla riga `Dts.TaskResult = ScriptResults.Success`.</span><span class="sxs-lookup"><span data-stu-id="546d5-124">By default, the only code in the `Main` subroutine of a new script is the line `Dts.TaskResult = ScriptResults.Success`.</span></span> <span data-ttu-id="546d5-125">Questa riga indica al runtime che l'operazione dell'attività è riuscita.</span><span class="sxs-lookup"><span data-stu-id="546d5-125">This line informs the runtime that the task was successful in its operation.</span></span> <span data-ttu-id="546d5-126">La `Dts.TaskResult` proprietà viene descritta in [restituzione di risultati dall'attività script](../../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="546d5-126">The `Dts.TaskResult` property is discussed in [Returning Results from the Script Task](../../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span></span>

-   <span data-ttu-id="546d5-127">Se l'attività Script è configurata per il linguaggio di programmazione Visual C#, la classe `ScriptMain` include un metodo pubblico `Main`.</span><span class="sxs-lookup"><span data-stu-id="546d5-127">When the Script task is configured for the Visual C# programming language, the `ScriptMain` class has a public method, `Main`.</span></span> <span data-ttu-id="546d5-128">Il metodo viene chiamato durante l'esecuzione dell'attività Script.</span><span class="sxs-lookup"><span data-stu-id="546d5-128">The method is called when the Script task runs.</span></span>

     <span data-ttu-id="546d5-129">Per impostazione predefinita, il metodo `Main` include la riga `Dts.TaskResult = (int)ScriptResults.Success`.</span><span class="sxs-lookup"><span data-stu-id="546d5-129">By default, the `Main` method includes the line `Dts.TaskResult = (int)ScriptResults.Success`.</span></span> <span data-ttu-id="546d5-130">Questa riga indica al runtime che l'operazione dell'attività è riuscita.</span><span class="sxs-lookup"><span data-stu-id="546d5-130">This line informs the runtime that the task was successful in its operation.</span></span>

 <span data-ttu-id="546d5-131">L'elemento `ScriptMain` può contenere classi diverse dalla classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="546d5-131">The `ScriptMain` item can contain classes other than the `ScriptMain` class.</span></span> <span data-ttu-id="546d5-132">Le classi sono disponibili solo per l'attività Script in cui risiedono.</span><span class="sxs-lookup"><span data-stu-id="546d5-132">Classes are available only to the Script task in which they reside.</span></span>

 <span data-ttu-id="546d5-133">Per impostazione predefinita, nell'elemento di progetto `ScriptMain` è incluso il seguente codice generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="546d5-133">By default, the `ScriptMain` project item contains the following autogenerated code.</span></span> <span data-ttu-id="546d5-134">Nel modello del codice sono inoltre disponibili una panoramica dell'attività Script, nonché informazioni aggiuntive su come recuperare e modificare oggetti SSIS, quali variabili, eventi e connessioni.</span><span class="sxs-lookup"><span data-stu-id="546d5-134">The code template also provides an overview of the Script task, and additional information on how to retrieve and manipulate SSIS objects, such as variables, events, and connections.</span></span>

```vb
' Microsoft SQL Server Integration Services Script Task
' Write scripts using Microsoft Visual Basic 2008.
' The ScriptMain is the entry point class of the script.

Imports System
Imports System.Data
Imports System.Math
Imports Microsoft.SqlServer.Dts.Runtime.VSTAProxy

<System.AddIn.AddIn("ScriptMain", Version:="1.0", Publisher:="", Description:="")> _
Partial Class ScriptMain

Private Sub ScriptMain_Startup(ByVal sender As Object, ByVal e As System.EventArgs) Handles Me.Startup

End Sub

Private Sub ScriptMain_Shutdown(ByVal sender As Object, ByVal e As System.EventArgs) Handles Me.Shutdown
Try
' Unlock variables from the read-only and read-write variable collection properties
If (Dts.Variables.Count <> 0) Then
Dts.Variables.Unlock()
End If
Catch ex As Exception
        End Try
End Sub

Enum ScriptResults
Success = DTSExecResult.Success
Failure = DTSExecResult.Failure
End Enum

' The execution engine calls this method when the task executes.
' To access the object model, use the Dts property. Connections, variables, events,
' and logging features are available as members of the Dts property as shown in the following examples.
'
' To reference a variable, call Dts.Variables("MyCaseSensitiveVariableName").Value
' To post a log entry, call Dts.Log("This is my log text", 999, Nothing)
' To fire an event, call Dts.Events.FireInformation(99, "test", "hit the help message", "", 0, True)
'
' To use the connections collection use something like the following:
' ConnectionManager cm = Dts.Connections.Add("OLEDB")
' cm.ConnectionString = "Data Source=localhost;Initial Catalog=AdventureWorks;Provider=SQLNCLI10;Integrated Security=SSPI;Auto Translate=False;"
'
' Before returning from this method, set the value of Dts.TaskResult to indicate success or failure.
' 
' To open Help, press F1.

Public Sub Main()
'
' Add your code here
'
Dts.TaskResult = ScriptResults.Success
End Sub

End Class
```

```csharp
/*
   Microsoft SQL Server Integration Services Script Task
   Write scripts using Microsoft Visual C# 2008.
   The ScriptMain is the entry point class of the script.
*/

using System;
using System.Data;
using Microsoft.SqlServer.Dts.Runtime.VSTAProxy;
using System.Windows.Forms;

namespace ST_1bcfdbad36d94f8ba9f23a10375abe53.csproj
{
    [System.AddIn.AddIn("ScriptMain", Version = "1.0", Publisher = "", Description = "")]
    public partial class ScriptMain
    {
        private void ScriptMain_Startup(object sender, EventArgs e)
        {

        }

        private void ScriptMain_Shutdown(object sender, EventArgs e)
        {
            try
            {
                // Unlock variables from the read-only and read-write variable collection properties
                if (Dts.Variables.Count != 0)
                {
                    Dts.Variables.Unlock();
                }
            }
            catch
            {
            }
        }

        #region VSTA generated code
        private void InternalStartup()
        {
            this.Startup += new System.EventHandler(ScriptMain_Startup);
            this.Shutdown += new System.EventHandler(ScriptMain_Shutdown);
        }
        enum ScriptResults
        {
            Success = DTSExecResult.Success,
            Failure = DTSExecResult.Failure
        };

        #endregion

        /*
The execution engine calls this method when the task executes.
To access the object model, use the Dts property. Connections, variables, events,
and logging features are available as members of the Dts property as shown in the following examples.

To reference a variable, call Dts.Variables["MyCaseSensitiveVariableName"].Value;
To post a log entry, call Dts.Log("This is my log text", 999, null);
To fire an event, call Dts.Events.FireInformation(99, "test", "hit the help message", "", 0, true);

To use the connections collection use something like the following:
ConnectionManager cm = Dts.Connections.Add("OLEDB");
cm.ConnectionString = "Data Source=localhost;Initial Catalog=AdventureWorks;Provider=SQLNCLI10;Integrated Security=SSPI;Auto Translate=False;";

Before returning from this method, set the value of Dts.TaskResult to indicate success or failure.

To open Help, press F1.
*/

        public void Main()
        {
            // TODO: Add your code here
            Dts.TaskResult = (int)ScriptResults.Success;
        }
    }
```

### <a name="additional-project-items-in-the-script-task-project"></a><span data-ttu-id="546d5-135">Altri elementi di progetto dell'attività Script</span><span class="sxs-lookup"><span data-stu-id="546d5-135">Additional Project Items in the Script Task Project</span></span>
 <span data-ttu-id="546d5-136">Il progetto dell'attività Script può includere elementi diversi dall'elemento `ScriptMain` predefinito.</span><span class="sxs-lookup"><span data-stu-id="546d5-136">The Script task project can include items other than the default `ScriptMain` item.</span></span> <span data-ttu-id="546d5-137">È possibile aggiungere classi, moduli e file di codice al progetto.</span><span class="sxs-lookup"><span data-stu-id="546d5-137">You can add classes, modules, and code files to the project.</span></span> <span data-ttu-id="546d5-138">È anche possibile utilizzare cartelle per organizzare gruppi di elementi.</span><span class="sxs-lookup"><span data-stu-id="546d5-138">You can also use folders to organize groups of items.</span></span> <span data-ttu-id="546d5-139">Tutti gli elementi aggiunti vengono salvati in modo permanente nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="546d5-139">All the items that you add are persisted inside the package.</span></span>

### <a name="references-in-the-script-task-project"></a><span data-ttu-id="546d5-140">Riferimenti nel progetto dell'attività Script</span><span class="sxs-lookup"><span data-stu-id="546d5-140">References in the Script Task Project</span></span>
 <span data-ttu-id="546d5-141">Per aggiungere riferimenti agli assembly gestiti, fare clic con il pulsante destro del mouse sul progetto di attività script in **Esplora progetti** e quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="546d5-141">You can add references to managed assemblies by right-clicking the Script task project in **Project Explorer**, and then clicking **Add Reference**.</span></span> <span data-ttu-id="546d5-142">Per altre informazioni, vedere [Riferimenti ad altri assembly nelle soluzioni di scripting](../referencing-other-assemblies-in-scripting-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="546d5-142">For more information, see [Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="546d5-143">È possibile visualizzare i riferimenti al progetto nell'ambiente IDE di VSTA in **Visualizzazione classi** o in **Esplora progetti**.</span><span class="sxs-lookup"><span data-stu-id="546d5-143">You can view project references in the VSTA IDE in **Class View** or in **Project Explorer**.</span></span> <span data-ttu-id="546d5-144">Queste finestre possono essere aperte dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="546d5-144">You open either of these windows from the **View** menu.</span></span> <span data-ttu-id="546d5-145">È possibile aggiungere un nuovo riferimento dal menu **Progetto**, da **Esplora progetti** o da **Visualizzazione classi**.</span><span class="sxs-lookup"><span data-stu-id="546d5-145">You can add a new reference from the **Project** menu, from **Project Explorer**, or from **Class View**.</span></span>

## <a name="interacting-with-the-package-in-the-script-task"></a><span data-ttu-id="546d5-146">Interazione con il pacchetto nell'attività Script</span><span class="sxs-lookup"><span data-stu-id="546d5-146">Interacting with the Package in the Script Task</span></span>
 <span data-ttu-id="546d5-147">L'attività Script utilizza l'oggetto `Dts` globale, che è un'istanza della classe <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel>, e i relativi membri per interagire con il pacchetto contenitore e con il runtime di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="546d5-147">The Script task uses the global `Dts` object, which is an instance of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class, and its members to interact with the containing package and with the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime.</span></span>

 <span data-ttu-id="546d5-148">Nella tabella seguente sono elencati i principali membri pubblici della classe <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel>, che viene esposta al codice dell'attività Script tramite l'oggetto `Dts` globale.</span><span class="sxs-lookup"><span data-stu-id="546d5-148">The following table lists the principal public members of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class, which is exposed to Script task code through the global `Dts` object.</span></span> <span data-ttu-id="546d5-149">Negli argomenti di questa sezione verrà descritto in maggior dettaglio l'utilizzo di questi membri.</span><span class="sxs-lookup"><span data-stu-id="546d5-149">The topics in this section discuss the use of these members in more detail.</span></span>

|<span data-ttu-id="546d5-150">Membro</span><span class="sxs-lookup"><span data-stu-id="546d5-150">Member</span></span>|<span data-ttu-id="546d5-151">Scopo</span><span class="sxs-lookup"><span data-stu-id="546d5-151">Purpose</span></span>|
|------------|-------------|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A>|<span data-ttu-id="546d5-152">Fornisce accesso alle gestioni connessioni definite nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="546d5-152">Provides access to connection managers defined in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>|<span data-ttu-id="546d5-153">Fornisce un'interfaccia degli eventi per consentire all'attività Script di generare errori, avvisi e messaggi informativi.</span><span class="sxs-lookup"><span data-stu-id="546d5-153">Provides an events interface to let the Script task raise errors, warnings, and informational messages.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A>|<span data-ttu-id="546d5-154">Fornisce un modo semplice per restituire al runtime un singolo oggetto (in aggiunta a `TaskResult`) che può anche essere utilizzato per la diramazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="546d5-154">Provides a simple way to return a single object to the runtime (in addition to the `TaskResult`) that can also be used for workflow branching.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>|<span data-ttu-id="546d5-155">Registra informazioni quali lo stato e i risultati dell'attività nei provider di log abilitati.</span><span class="sxs-lookup"><span data-stu-id="546d5-155">Logs information such as task progress and results to enabled log providers.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A>|<span data-ttu-id="546d5-156">Indica l'esito positivo o negativo dell'attività.</span><span class="sxs-lookup"><span data-stu-id="546d5-156">Reports the success or failure of the task.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Transaction%2A>|<span data-ttu-id="546d5-157">Fornisce la transazione, se presente, in cui è in esecuzione il contenitore dell'attività.</span><span class="sxs-lookup"><span data-stu-id="546d5-157">Provides the transaction, if any, within which the task's container is running.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>|<span data-ttu-id="546d5-158">Fornisce accesso alle variabili elencate nelle proprietà `ReadOnlyVariables` e `ReadWriteVariables` dell'attività per l'utilizzo all'interno dello script.</span><span class="sxs-lookup"><span data-stu-id="546d5-158">Provides access to the variables listed in the `ReadOnlyVariables` and `ReadWriteVariables` task properties for use within the script.</span></span>|

 <span data-ttu-id="546d5-159">La classe <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> contiene anche alcuni membri pubblici che probabilmente non verranno utilizzati.</span><span class="sxs-lookup"><span data-stu-id="546d5-159">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class also contains some public members that you will probably not use.</span></span>

|<span data-ttu-id="546d5-160">Membro</span><span class="sxs-lookup"><span data-stu-id="546d5-160">Member</span></span>|<span data-ttu-id="546d5-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="546d5-161">Description</span></span>|
|------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>|<span data-ttu-id="546d5-162">La proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> fornisce un accesso più semplice alle variabili.</span><span class="sxs-lookup"><span data-stu-id="546d5-162">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property provides more convenient access to variables.</span></span> <span data-ttu-id="546d5-163">Anche se è possibile utilizzare <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, è necessario chiamare in modo esplicito i metodi per bloccare e sbloccare le variabili per la lettura e la scrittura.</span><span class="sxs-lookup"><span data-stu-id="546d5-163">Although you can use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, you must explicitly call methods to lock and unlock variables for reading and writing.</span></span> <span data-ttu-id="546d5-164">L'attività Script gestisce automaticamente la semantica di blocco quando si utilizza la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>.</span><span class="sxs-lookup"><span data-stu-id="546d5-164">The Script task handles locking semantics for you when you use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property.</span></span>|

## <a name="debugging-the-script-task"></a><span data-ttu-id="546d5-165">Debug dell'attività Script</span><span class="sxs-lookup"><span data-stu-id="546d5-165">Debugging the Script Task</span></span>
 <span data-ttu-id="546d5-166">Per eseguire il debug del codice nell'attività Script, impostare almeno un punto di interruzione nel codice, quindi chiudere l'IDE di VSTA per eseguire il pacchetto in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="546d5-166">To debug the code in your Script task, set at least one breakpoint in the code, and then close the VSTA IDE to run the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="546d5-167">Quando l'esecuzione del pacchetto entra nell'attività Script, l'IDE di VSTA viene riaperto e visualizza il codice in modalità di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="546d5-167">When package execution enters the Script task, the VSTA IDE reopens and displays your code in read-only mode.</span></span> <span data-ttu-id="546d5-168">Quando l'esecuzione raggiunge il punto di interruzione, è possibile esaminare i valori delle variabili e scorrere il codice rimanente.</span><span class="sxs-lookup"><span data-stu-id="546d5-168">After execution reaches your breakpoint, you can examine variable values and step through the remaining code.</span></span>

> [!WARNING]
>  <span data-ttu-id="546d5-169">È possibile eseguire il debug dell'attività Script quando si esegue il pacchetto in modalità a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="546d5-169">You can debug the Script task when you run the package in 64-bit mode.</span></span>

> [!NOTE]
>  <span data-ttu-id="546d5-170">È necessario eseguire il pacchetto da sottoporre a debug nell'attività Script.</span><span class="sxs-lookup"><span data-stu-id="546d5-170">You must execute the package to debug into your Script task.</span></span> <span data-ttu-id="546d5-171">Se si esegue solo la singola attività, i punti di interruzione nel codice dell'attività Script vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="546d5-171">If you execute only the individual task, breakpoints in the Script task code are ignored.</span></span>

> [!NOTE]
>  <span data-ttu-id="546d5-172">Non è possibile eseguire il debug di un'attività Script se l'attività viene eseguita nell'ambito di un pacchetto figlio eseguito da un'attività Esegui pacchetto.</span><span class="sxs-lookup"><span data-stu-id="546d5-172">You cannot debug a Script task when you run the Script task as part of a child package that is run from an Execute Package task.</span></span> <span data-ttu-id="546d5-173">In tali circostanze, i punti di interruzione impostati all'interno dell'attività Script del pacchetto figlio verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="546d5-173">Breakpoints that you set in the Script task in the child package are disregarded in these circumstances.</span></span> <span data-ttu-id="546d5-174">È possibile eseguire il debug del pacchetto figlio normalmente eseguendolo separatamente.</span><span class="sxs-lookup"><span data-stu-id="546d5-174">You can debug the child package normally by running it separately.</span></span>

> [!NOTE]
>  <span data-ttu-id="546d5-175">Quando si esegue il debug di un pacchetto che contiene più attività Script, il debugger è in grado di elaborarne solo una.</span><span class="sxs-lookup"><span data-stu-id="546d5-175">When you debug a package that contains multiple Script tasks, the debugger debugs one Script task.</span></span> <span data-ttu-id="546d5-176">Il sistema può eseguire il debug di un'altra attività Script se il debugger termina l'elaborazione, come nel caso di un contenitore Ciclo ForEach o Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="546d5-176">The system can debug another Script task if the debugger completes, as in the case of a Foreach Loop or For Loop container.</span></span>

## <a name="external-resources"></a><span data-ttu-id="546d5-177">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="546d5-177">External Resources</span></span>

-   <span data-ttu-id="546d5-178">Intervento del blog, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661) (Problemi di installazione e configurazione di VSTA per le installazioni SSIS 2008 e R2), in blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="546d5-178">Blog entry, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), on blogs.msdn.com.</span></span>

<span data-ttu-id="546d5-179">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="546d5-179">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="546d5-180">Per i download, gli articoli, gli esempi e i video [!INCLUDE[msCoName](../../../includes/msconame-md.md)] più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] su MSDN:</span><span class="sxs-lookup"><span data-stu-id="546d5-180">For the latest downloads, articles, samples, and videos from [!INCLUDE[msCoName](../../../includes/msconame-md.md)], as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="546d5-181">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="546d5-181">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="546d5-182">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="546d5-182">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="546d5-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="546d5-183">See Also</span></span>
 <span data-ttu-id="546d5-184">[Riferimento ad altri assembly nelle soluzioni di scripting](../referencing-other-assemblies-in-scripting-solutions.md) [configurazione dell'attività script in Editor attività script](configuring-the-script-task-in-the-script-task-editor.md)</span><span class="sxs-lookup"><span data-stu-id="546d5-184">[Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md) [Configuring the Script Task in the Script Task Editor](configuring-the-script-task-in-the-script-task-editor.md)</span></span>


