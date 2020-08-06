---
title: Uso di variabili a livello di programmazione | Microsoft Docs
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
- System namespace
- scope [Integration Services]
- variables [Integration Services], programmatically
- configuration files [Integration Services]
- Variables collection
- User namespace
- custom variables [Integration Services]
- variables [Integration Services], customizing
ms.assetid: c4b76a3d-94ca-4a8e-bb45-cb8bd0ea3ec1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2c903ee6adb8989eaeb93efbe943eca93c73eae4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723016"
---
# <a name="working-with-variables-programmatically"></a><span data-ttu-id="040bd-102">Utilizzo delle variabili a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="040bd-102">Working with Variables Programmatically</span></span>
  <span data-ttu-id="040bd-103">Le variabili consentono di impostare valori in modo dinamico e di controllare i processi in pacchetti, contenitori, attività e gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="040bd-103">Variables are a way to dynamically set values and control processes in packages, containers, tasks, and event handlers.</span></span> <span data-ttu-id="040bd-104">Possono inoltre essere utilizzate dai vincoli di precedenza per controllare la direzione del flusso di dati verso attività diverse.</span><span class="sxs-lookup"><span data-stu-id="040bd-104">Variables can also be used by precedence constraints to control the direction of the flow of data to different tasks.</span></span> <span data-ttu-id="040bd-105">Le variabili possono essere utilizzate per effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="040bd-105">Variables have a variety of uses:</span></span>

-   <span data-ttu-id="040bd-106">Aggiornare le proprietà di un pacchetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="040bd-106">Update properties of a package at run time.</span></span>

-   <span data-ttu-id="040bd-107">Popolare i valori dei parametri per le istruzioni Transact-SQL in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="040bd-107">Populate parameter values for Transact-SQL statements at run time.</span></span>

-   <span data-ttu-id="040bd-108">Controllare il flusso di un ciclo Foreach.</span><span class="sxs-lookup"><span data-stu-id="040bd-108">Control the flow of a Foreach loop.</span></span> <span data-ttu-id="040bd-109">Per altre informazioni, vedere [Aggiungere un'enumerazione a un flusso di controllo](../control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="040bd-109">For more information, see [Add Enumeration to a Control Flow](../control-flow/control-flow.md).</span></span>

-   <span data-ttu-id="040bd-110">Controllare un vincolo di precedenza in base al relativo utilizzo in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="040bd-110">Control a precedence constraint by its use in an expression.</span></span> <span data-ttu-id="040bd-111">Un vincolo di precedenza può includere variabili nella definizione del vincolo.</span><span class="sxs-lookup"><span data-stu-id="040bd-111">A precedence constraint can include variables in the constraint definition.</span></span> <span data-ttu-id="040bd-112">Per altre informazioni, vedere [Aggiunta di espressioni ai vincoli di precedenza](../control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="040bd-112">For more information, see [Add Expressions to Precedence Constraints](../control-flow/precedence-constraints.md).</span></span>

-   <span data-ttu-id="040bd-113">Controllare la ripetizione condizionale di un contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="040bd-113">Control the conditional repeat of a For Loop container.</span></span> <span data-ttu-id="040bd-114">Per altre informazioni, vedere [Aggiungere un'enumerazione a un flusso di controllo](../add-iteration-to-a-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="040bd-114">For more information, see [Add Iteration to a Control Flow](../add-iteration-to-a-control-flow.md).</span></span>

-   <span data-ttu-id="040bd-115">Compilare espressioni che includono valori di variabili.</span><span class="sxs-lookup"><span data-stu-id="040bd-115">Build expressions that include variable values.</span></span>

-   <span data-ttu-id="040bd-116">È possibile creare variabili personalizzate per tutti i tipi di contenitori, ovvero pacchetti, contenitori **Ciclo Foreach**, contenitori **Ciclo For**, contenitori **Sequenza**, TaskHost e gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="040bd-116">You can create custom variables for all container types: packages, **Foreach Loop** containers, **For Loop** containers, **Sequence** containers, TaskHosts, and event handlers.</span></span> <span data-ttu-id="040bd-117">Per altre informazioni, vedere [Variabili di Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) e [Utilizzo di variabili nei pacchetti](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="040bd-117">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>

## <a name="scope"></a><span data-ttu-id="040bd-118">Scope</span><span class="sxs-lookup"><span data-stu-id="040bd-118">Scope</span></span>
 <span data-ttu-id="040bd-119">Ogni contenitore dispone di una propria raccolta <xref:Microsoft.SqlServer.Dts.Runtime.Variables>.</span><span class="sxs-lookup"><span data-stu-id="040bd-119">Each container has its own <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection.</span></span> <span data-ttu-id="040bd-120">Ogni nuova variabile creata si trova nell'ambito del relativo contenitore padre.</span><span class="sxs-lookup"><span data-stu-id="040bd-120">When a new variable is created, it is within the scope of its parent container.</span></span> <span data-ttu-id="040bd-121">Poiché il contenitore del pacchetto costituisce il livello principale della gerarchia dei contenitori, le variabili con ambito pacchetto sono variabili globali e sono visibili a tutti i contenitori del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="040bd-121">Because the package container is at the top of the container hierarchy, variables with package scope function like global variables, and are visible to all containers within the package.</span></span> <span data-ttu-id="040bd-122">Alla raccolta di variabili per il contenitore possono accedere anche gli elementi figlio del contenitore tramite la raccolta <xref:Microsoft.SqlServer.Dts.Runtime.Variables>, utilizzando il nome della variabile o il relativo indice nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="040bd-122">The collection of variables for the container can also be accessed by the children of the container through the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection, by using either the variable name or the variable's index in the collection.</span></span>

 <span data-ttu-id="040bd-123">Poiché la visibilità di una variabile ha un ambito dall'alto in basso, le variabili dichiarate a livello di pacchetto sono visibili a tutti i contenitori nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="040bd-123">Because the visibility of a variable is scoped from the top down, variables declared at the package level are visible to all the containers in the package.</span></span> <span data-ttu-id="040bd-124">Pertanto, la raccolta <xref:Microsoft.SqlServer.Dts.Runtime.Variables> in un contenitore include tutte le variabili che appartengono al relativo oggetto padre in aggiunta alle proprie variabili.</span><span class="sxs-lookup"><span data-stu-id="040bd-124">Therefore, the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection on a container includes all the variables that belong to its parent in addition to its own variables</span></span>

 <span data-ttu-id="040bd-125">Viceversa, le variabili contenute in un'attività sono limitate in termini di ambito e visibilità e sono visibili solo all'attività.</span><span class="sxs-lookup"><span data-stu-id="040bd-125">Conversely, the variables that are contained in a task are limited in scope and visibility, and are only visible to the task.</span></span>

 <span data-ttu-id="040bd-126">Se un pacchetto esegue altri pacchetti, le variabili definite nell'ambito del pacchetto chiamante sono disponibili per il pacchetto chiamato.</span><span class="sxs-lookup"><span data-stu-id="040bd-126">If a package runs other packages, the variables defined in the scope of the calling package are available to the called package.</span></span> <span data-ttu-id="040bd-127">L'unica eccezione si verifica quando nel pacchetto chiamato esiste una variabile con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="040bd-127">The only exception occurs when a same-named variable exists in the called package.</span></span> <span data-ttu-id="040bd-128">Quando si verifica questa collisione, il valore della variabile nel pacchetto chiamato sostituisce il valore del pacchetto chiamante.</span><span class="sxs-lookup"><span data-stu-id="040bd-128">When this collision occurs, the variable value in the called package overrides the value from the calling package.</span></span> <span data-ttu-id="040bd-129">Le variabili definite nell'ambito del pacchetto chiamato non sono mai nuovamente disponibili per il pacchetto chiamante.</span><span class="sxs-lookup"><span data-stu-id="040bd-129">Variables defined in the scope of the called package are never available back to the calling package.</span></span>

 <span data-ttu-id="040bd-130">Nell'esempio di codice seguente viene creata una variabile a livello di programmazione, `myCustomVar`, nell'ambito del pacchetto, quindi vengono scorse tutte le variabili visibili al pacchetto e ne vengono stampati il nome, il tipo di dati e il valore.</span><span class="sxs-lookup"><span data-stu-id="040bd-130">The following code example programmatically creates a variable, `myCustomVar`, at the package scope, and then iterates through all the variables visible to the package, printing their name, data type, and value.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Application app = new Application();
      // Load a sample package that contains a variable that sets the file name.
      Package pkg = app.LoadPackage(
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +
        @"\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx",
        null);
      Variables pkgVars = pkg.Variables;
      Variable myVar = pkg.Variables.Add("myCustomVar", false, "User", "3");
      foreach (Variable pkgVar in pkgVars)
      {
        Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name,
          pkgVar.DataType, pkgVar.Value.ToString());
      }
      Console.Read();
    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim app As Application = New Application()
    ' Load a sample package that contains a variable that sets the file name.
    Dim pkg As Package = app.LoadPackage( _
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _
      "\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx", _
      Nothing)
    Dim pkgVars As Variables = pkg.Variables
    Dim myVar As Variable = pkg.Variables.Add("myCustomVar", False, "User", "3")
    Dim pkgVar As Variable
    For Each pkgVar In pkgVars
      Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name, _
        pkgVar.DataType, pkgVar.Value.ToString())
    Next
    Console.Read()

  End Sub

End Module
```

 <span data-ttu-id="040bd-131">**Esempio di output**</span><span class="sxs-lookup"><span data-stu-id="040bd-131">**Sample Output:**</span></span>

 `Variable: CancelEvent, Int32, 0`

 `Variable: CreationDate, DateTime, 4/18/2003 11:57:00 AM`

 `Variable: CreatorComputerName, String,`

 `Variable: CreatorName, String,`

 `Variable: ExecutionInstanceGUID, String, {237AB5A4-7E59-4FC9-8D61-E8F20363DF25}`

 `Variable: FileName, String, Junk`

 `Variable: InteractiveMode, Boolean, False`

 `Variable: LocaleID, Int32, 1033`

 `Variable: MachineName, String, MYCOMPUTERNAME`

 `Variable: myCustomVar, String, 3`

 `Variable: OfflineMode, Boolean, False`

 `Variable: PackageID, String, {F0D2E396-A6A5-42AE-9467-04CE946A810C}`

 `Variable: PackageName, String, DTSPackage1`

 `Variable: StartTime, DateTime, 1/28/2005 7:55:39 AM`

 `Variable: UserName, String, <domain>\<userid>`

 `Variable: VersionBuild, Int32, 198`

 `Variable: VersionComments, String,`

 `Variable: VersionGUID, String, {90E105B4-B4AF-4263-9CBD-C2050C2D6148}`

 `Variable: VersionMajor, Int32, 1`

 `Variable: VersionMinor, Int32, 0`

 <span data-ttu-id="040bd-132">Si noti che tutte le variabili che hanno come ambito lo spazio dei nomi **System** sono disponibili per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="040bd-132">Notice that all the variables scoped in the **System** namespace are available to the package.</span></span> <span data-ttu-id="040bd-133">Per altre informazioni, vedere [Variabili di sistema](../system-variables.md).</span><span class="sxs-lookup"><span data-stu-id="040bd-133">For more information, see [System Variables](../system-variables.md).</span></span>

## <a name="namespaces"></a><span data-ttu-id="040bd-134">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="040bd-134">Namespaces</span></span>
 <span data-ttu-id="040bd-135">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) sono disponibili due spazi dei nomi predefiniti in cui risiedono le variabili, ovvero gli spazi dei nomi **User** e **System**.</span><span class="sxs-lookup"><span data-stu-id="040bd-135">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) provides two default namespaces where variables reside; **User** and **System** namespaces.</span></span> <span data-ttu-id="040bd-136">Per impostazione predefinita, tutte le variabili personalizzate create dallo sviluppatore vengono aggiunte allo spazio dei nomi **User**.</span><span class="sxs-lookup"><span data-stu-id="040bd-136">By default, any custom variable created by the developer is added to the **User** namespace.</span></span> <span data-ttu-id="040bd-137">Le variabili di sistema risiedono nello spazio dei nomi **System**.</span><span class="sxs-lookup"><span data-stu-id="040bd-137">System variables reside in the **System** namespace.</span></span> <span data-ttu-id="040bd-138">È possibile creare altri spazi dei nomi diversi da **User** in cui includere variabili personalizzate, nonché modificare il nome dello spazio dei nomi **User**, ma non è possibile aggiungere o modificare variabili nello spazio dei nomi **System**, né assegnare variabili di sistema a uno spazio dei nomi diverso.</span><span class="sxs-lookup"><span data-stu-id="040bd-138">You can create additional namespaces other than the **User** namespace to hold custom variables, and you can change the name of the **User** namespace, but you cannot add or modify variables in the **System** namespace, or assign system variables to a different namespace.</span></span>

 <span data-ttu-id="040bd-139">Le variabili di sistema disponibili variano a seconda del tipo di contenitore.</span><span class="sxs-lookup"><span data-stu-id="040bd-139">The system variables that are available differ depending on the container type.</span></span> <span data-ttu-id="040bd-140">Per un elenco delle variabili di sistema disponibili per pacchetti, contenitori, attività e gestori di eventi, vedere [Variabili di sistema](../system-variables.md).</span><span class="sxs-lookup"><span data-stu-id="040bd-140">For a list of the system variables available to packages, containers, tasks, and event handlers, see [System Variables](../system-variables.md).</span></span>

## <a name="value"></a><span data-ttu-id="040bd-141">valore</span><span class="sxs-lookup"><span data-stu-id="040bd-141">Value</span></span>
 <span data-ttu-id="040bd-142">Il valore di una variabile personalizzata può essere un valore letterale o un'espressione:</span><span class="sxs-lookup"><span data-stu-id="040bd-142">The value of a custom variable can be a literal or an expression:</span></span>

-   <span data-ttu-id="040bd-143">Se si desidera che la variabile contenga un valore letterale, impostare il valore della relativa proprietà <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="040bd-143">If you want the variable to contain a literal value, set the value of its <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property.</span></span>

-   <span data-ttu-id="040bd-144">Se si desidera che la variabile contenga un'espressione, in modo che sia possibile utilizzare i risultati dell'espressione come valore, impostare la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> della variabile su `true` e specificare un'espressione nella proprietà <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="040bd-144">If you want the variable to contain an expression, so that you can use the results of the expression as its value, set the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> property of the variable to `true`, and provide an expression in the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Expression%2A> property.</span></span> <span data-ttu-id="040bd-145">In fase di esecuzione l'espressione verrà valutata e il relativo risultato verrà utilizzato come valore della variabile.</span><span class="sxs-lookup"><span data-stu-id="040bd-145">At run time, the expression is evaluated, and the result of the expression is used as the value of the variable.</span></span> <span data-ttu-id="040bd-146">Se ad esempio la proprietà Expression di una variabile è `"100 * 2""100 * 2"`, la variabile restituirà il valore 200.</span><span class="sxs-lookup"><span data-stu-id="040bd-146">For example, if the expression property of a variable is `"100 * 2""100 * 2"`, the variable evaluates to a value of 200.</span></span>

 <span data-ttu-id="040bd-147">Non è possibile impostare in modo esplicito il valore <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> di una variabile.</span><span class="sxs-lookup"><span data-stu-id="040bd-147">For a variable, you cannot explicitly set the value of its <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A>.</span></span> <span data-ttu-id="040bd-148">Il valore <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> è derivato dal valore iniziale assegnato alla variabile e non può essere modificato in seguito.</span><span class="sxs-lookup"><span data-stu-id="040bd-148">The <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> value is inferred from the initial value assigned to the variable, and cannot be changed afterward.</span></span> <span data-ttu-id="040bd-149">Per altre informazioni sui tipi di dati della variabile, vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="040bd-149">For more information about variable data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

 <span data-ttu-id="040bd-150">Nell'esempio di codice seguente viene creata una nuova variabile, la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> viene impostata su `true`, viene assegnata l'espressione `"100 * 2"` alla proprietà Expression della variabile, quindi viene restituito il valore della variabile.</span><span class="sxs-lookup"><span data-stu-id="040bd-150">The following code example creates a new variable, sets <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> to `true`, assigns the expression `"100 * 2"` to the expression property of the variable, and then outputs the value of the variable.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Package pkg = new Package();
      Variable v100 = pkg.Variables.Add("myVar", false, "", 1);
      v100.EvaluateAsExpression = true;
      v100.Expression = "100 * 2";
      Console.WriteLine("Expression for myVar: {0}", 
        v100.Properties["Expression"].GetValue(v100));
      Console.WriteLine("Value of myVar: {0}", v100.Value.ToString());
      Console.Read();
    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim pkg As Package = New Package
    Dim v100 As Variable = pkg.Variables.Add("myVar", False, "", 1)
    v100.EvaluateAsExpression = True
    v100.Expression = "100 * 2"
    Console.WriteLine("Expression for myVar: {0}", _
      v100.Properties("Expression").GetValue(v100))
    Console.WriteLine("Value of myVar: {0}", v100.Value.ToString)
    Console.Read()

  End Sub

End Module
```

 <span data-ttu-id="040bd-151">**Esempio di output**</span><span class="sxs-lookup"><span data-stu-id="040bd-151">**Sample Output:**</span></span>

 `Expression for myVar: 100 * 2`

 `Value of myVar: 200`

 <span data-ttu-id="040bd-152">È necessario utilizzare un'espressione valida che utilizza la sintassi delle espressioni di [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="040bd-152">The expression must be a valid expression that uses the [!INCLUDE[ssIS](../../includes/ssis-md.md)] expression syntax.</span></span> <span data-ttu-id="040bd-153">I valori letterali sono consentiti nelle espressioni delle variabili, in aggiunta agli operatori e alle funzioni disponibili nella sintassi delle espressioni, ma le espressioni non possono fare riferimento ad altre variabili o colonne.</span><span class="sxs-lookup"><span data-stu-id="040bd-153">Literals are permitted in variable expressions, in addition to the operators and functions that the expression syntax provides, but expressions cannot reference other variables or columns.</span></span> <span data-ttu-id="040bd-154">Per altre informazioni, vedere [Espressioni di Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="040bd-154">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="040bd-155">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="040bd-155">Configuration Files</span></span>
 <span data-ttu-id="040bd-156">Se un file di configurazione include una variabile personalizzata, la variabile può essere aggiornata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="040bd-156">If a configuration file includes a custom variable, the variable can be updated at run time.</span></span> <span data-ttu-id="040bd-157">Questo significa che quando il pacchetto viene eseguito, il valore della variabile che si trovava originariamente nel pacchetto viene sostituito con un nuovo valore del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="040bd-157">What this means is that when the package runs, the value of the variable originally in the package is replaced with a new value from the configuration file.</span></span> <span data-ttu-id="040bd-158">Questa tecnica di sostituzione risulta utile quando un pacchetto viene distribuito in più server che richiedono valori di variabili diversi.</span><span class="sxs-lookup"><span data-stu-id="040bd-158">This replacement technique is useful when a package is deployed to multiple servers that require different variable values.</span></span> <span data-ttu-id="040bd-159">Ad esempio, una variabile può specificare il numero di volte in cui un contenitore **Ciclo Foreach** ripete il flusso di lavoro o elencare i destinatari a cui un gestore di eventi invia un messaggio di posta elettronica quando viene generato un errore oppure modificare il numero di errori che possono verificarsi prima che l'esecuzione del pacchetto abbia esito negativo.</span><span class="sxs-lookup"><span data-stu-id="040bd-159">For example, a variable can specify the number of times a **Foreach Loop** container repeats its workflow, or list the recipients that an event handler sends e-mail to when an error is raised, or change the number of errors that can occur before the package fails.</span></span> <span data-ttu-id="040bd-160">Queste variabili vengono fornite dinamicamente nei file di configurazione per ogni ambiente.</span><span class="sxs-lookup"><span data-stu-id="040bd-160">These variables are dynamically provided in configuration files for each environment.</span></span> <span data-ttu-id="040bd-161">Pertanto, nei file di configurazione sono consentite solo variabili di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="040bd-161">Therefore, only variables that are read/write are allowed in configuration files.</span></span> <span data-ttu-id="040bd-162">Per altre informazioni, vedere [Creazione di configurazioni dei pacchetti](../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="040bd-162">For more information, see [Create Package Configurations](../create-package-configurations.md).</span></span>

<span data-ttu-id="040bd-163">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="040bd-163">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="040bd-164">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="040bd-164">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="040bd-165">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="040bd-165">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="040bd-166">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="040bd-166">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="040bd-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="040bd-167">See Also</span></span>
 <span data-ttu-id="040bd-168">[Integration Services &#40;variabili di&#41; SSIS](../integration-services-ssis-variables.md) [utilizzano variabili nei pacchetti](../use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="040bd-168">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) [Use Variables in Packages](../use-variables-in-packages.md)</span></span>


