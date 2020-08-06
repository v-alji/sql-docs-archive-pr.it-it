---
title: Codifica e debug del componente script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SSIS Script task, development environment
- Script component [Integration Services], debugging
- Script component [Integration Services], coding
- SSIS Script component, debugging
- Script component [Integration Services], development environment
- debugging [Integration Services], scripts
- SSIS Script component, coding
- VSTA
ms.assetid: c3913c15-66aa-4b61-89b5-68488fa5f0a4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9363ad447ca3d0031289eafb1d8f616320fca5b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629924"
---
# <a name="coding-and-debugging-the-script-component"></a><span data-ttu-id="59104-102">Codifica e debug del componente script</span><span class="sxs-lookup"><span data-stu-id="59104-102">Coding and Debugging the Script Component</span></span>
  <span data-ttu-id="59104-103">In Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] sono disponibili due modalità per il componente script: progettazione metadati e progettazione codice.</span><span class="sxs-lookup"><span data-stu-id="59104-103">In [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, the Script component has two modes: metadata design mode and code design mode.</span></span> <span data-ttu-id="59104-104">Quando si apre l'**Editor trasformazione Script**, per il componente viene attivata la modalità di progettazione metadati, che consente di configurare i metadati e impostare le proprietà del componente.</span><span class="sxs-lookup"><span data-stu-id="59104-104">When you open the **Script Transformation Editor**, the component enters metadata design mode, in which you configure metadata and set component properties.</span></span> <span data-ttu-id="59104-105">Dopo l'impostazione delle proprietà del componente script e la configurazione di input e output nella modalità di progettazione metadati, è possibile passare alla modalità di progettazione codice per scrivere lo script personalizzato.</span><span class="sxs-lookup"><span data-stu-id="59104-105">After you have set the properties of the Script component and configured the input and outputs in metadata design mode, you can switch to code design mode to write your custom script.</span></span> <span data-ttu-id="59104-106">Per altre informazioni sulla modalità di progettazione metadati e sulla modalità di progettazione codice, vedere [Configurazione del componente script nell'editor corrispondente](configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="59104-106">For more information about metadata design mode and code design mode, see [Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md).</span></span>

## <a name="writing-the-script-in-code-design-mode"></a><span data-ttu-id="59104-107">Scrittura dello script in modalità di progettazione codice</span><span class="sxs-lookup"><span data-stu-id="59104-107">Writing the Script in Code Design Mode</span></span>

### <a name="script-component-development-environment"></a><span data-ttu-id="59104-108">Ambiente di sviluppo del componente script</span><span class="sxs-lookup"><span data-stu-id="59104-108">Script Component Development Environment</span></span>
 <span data-ttu-id="59104-109">Per scrivere lo script, fare clic su **Modifica script** nella pagina **Script** dell'**Editor trasformazione Script** per aprire l'ambiente IDE di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="59104-109">To write your script, click **Edit Script** on the **Script** page of the **Script Transformation Editor** to open the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE.</span></span> <span data-ttu-id="59104-110">L'IDE di VSTA include tutte le funzionalità standard dell'ambiente [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .NET, come l'editor di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] con codifica a colori, la tecnologia IntelliSense e il Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="59104-110">The VSTA IDE includes all the standard features of the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .NET environment, such as the color-coded [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] editor, IntelliSense, and Object Browser.</span></span>

 <span data-ttu-id="59104-111">Il codice di script viene scritto in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="59104-111">Script code is written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="59104-112">Il linguaggio di scripting viene specificato mediante l'impostazione della proprietà **ScriptLanguage** nell'**Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="59104-112">You specify the script language by setting the **ScriptLanguage** property in the **Script Transformation Editor**.</span></span> <span data-ttu-id="59104-113">Per utilizzare un altro linguaggio di programmazione, è possibile sviluppare un assembly personalizzato nel linguaggio desiderato e chiamarne la funzionalità dal codice nel componente script.</span><span class="sxs-lookup"><span data-stu-id="59104-113">If you prefer to use another programming language, you can develop a custom assembly in your language of choice and call its functionality from the code in the Script component.</span></span>

 <span data-ttu-id="59104-114">Lo script creato nel componente script viene archiviato nella definizione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="59104-114">The script that you create in the Script component is stored in the package definition.</span></span> <span data-ttu-id="59104-115">Non viene creato un file script separato.</span><span class="sxs-lookup"><span data-stu-id="59104-115">There is no separate script file.</span></span> <span data-ttu-id="59104-116">Pertanto, l'utilizzo del componente script non ha effetto sulla distribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="59104-116">Therefore, the use of the Script component does not affect package deployment.</span></span>

> [!NOTE]
>  <span data-ttu-id="59104-117">Durante la progettazione del pacchetto, il codice di script viene scritto temporaneamente in un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="59104-117">While you design the package, the script code is temporarily written to a project file.</span></span> <span data-ttu-id="59104-118">Poiché l'archiviazione di informazioni riservate in un file costituisce un potenziale rischio per la sicurezza, è consigliabile non inserire nel codice di script informazioni riservate, ad esempio le password.</span><span class="sxs-lookup"><span data-stu-id="59104-118">Because storing sensitive information in a file is a potential security risk, we recommended that you do not include sensitive information such as passwords in the script code.</span></span>

 <span data-ttu-id="59104-119">Per impostazione predefinita, `Option Strict` è disabilitato nell'IDE.</span><span class="sxs-lookup"><span data-stu-id="59104-119">By default, `Option Strict` is disabled in the IDE.</span></span>

### <a name="script-component-project-structure"></a><span data-ttu-id="59104-120">Struttura di progetto del componente script</span><span class="sxs-lookup"><span data-stu-id="59104-120">Script Component Project Structure</span></span>
 <span data-ttu-id="59104-121">L'efficacia del componente script consiste nella possibilità di generare codice di infrastruttura in grado di ridurre la quantità di codice da scrivere.</span><span class="sxs-lookup"><span data-stu-id="59104-121">The power of the Script component is that it can generate infrastructure code that reduces the amount of code that you must write.</span></span> <span data-ttu-id="59104-122">Questa funzionalità si basa sul fatto che input e output, con le relative colonne e proprietà, sono fissi e noti in anticipo.</span><span class="sxs-lookup"><span data-stu-id="59104-122">This feature relies on the fact that inputs and outputs and their columns and properties are fixed and known in advance.</span></span> <span data-ttu-id="59104-123">Pertanto, qualsiasi modifica successiva apportata ai metadati del componente può invalidare il codice scritto.</span><span class="sxs-lookup"><span data-stu-id="59104-123">Therefore, any subsequent changes that you make to the component's metadata may invalidate the code that you have written.</span></span> <span data-ttu-id="59104-124">Questa condizione è causa di errori di compilazione durante l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="59104-124">This causes compilation errors during execution of the package.</span></span>

#### <a name="project-items-and-classes-in-the-script-component-project"></a><span data-ttu-id="59104-125">Elementi e classi del progetto del componente script</span><span class="sxs-lookup"><span data-stu-id="59104-125">Project Items and Classes in the Script Component Project</span></span>
 <span data-ttu-id="59104-126">Quando si passa alla modalità di progettazione codice, nell'IDE di VSTA viene aperto e visualizzato l'elemento del progetto `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="59104-126">When you switch to code design mode, the VSTA IDE opens and displays the `ScriptMain` project item.</span></span> <span data-ttu-id="59104-127">L'elemento del progetto `ScriptMain` contiene la classe `ScriptMain` modificabile che funge da punto di ingresso per lo script e nella quale viene scritto il codice.</span><span class="sxs-lookup"><span data-stu-id="59104-127">The `ScriptMain` project item contains the editable `ScriptMain` class, which serves as the entry point for the script and which is where you write your code.</span></span> <span data-ttu-id="59104-128">Gli elementi di codice nella classe variano a seconda del linguaggio di programmazione selezionato per l'attività Script.</span><span class="sxs-lookup"><span data-stu-id="59104-128">The code elements in the class vary depending on the programming language that you selected for the Script task.</span></span>

 <span data-ttu-id="59104-129">Il progetto di script contiene due elementi del progetto aggiuntivi di sola lettura generati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="59104-129">The script project contains two additional auto-generated read-only project items:</span></span>

-   <span data-ttu-id="59104-130">L'elemento del progetto `ComponentWrapper` contiene tre classi:</span><span class="sxs-lookup"><span data-stu-id="59104-130">The `ComponentWrapper` project item contains three classes:</span></span>

    -   <span data-ttu-id="59104-131">Classe `UserComponent` che eredita da <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> e contiene i metodi e le proprietà da utilizzare per elaborare i dati e interagire con il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="59104-131">The `UserComponent` class, which inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> and contains the methods and properties that you will use to process data and to interact with the package.</span></span> <span data-ttu-id="59104-132">La classe `ScriptMain` eredita dalla classe `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="59104-132">The `ScriptMain` class inherits from the `UserComponent` class.</span></span>

    -   <span data-ttu-id="59104-133">Classe della raccolta `Connections` che contiene riferimenti alle connessioni selezionate nella pagina Gestione connessione dell'Editor trasformazione Script.</span><span class="sxs-lookup"><span data-stu-id="59104-133">A `Connections` collection class that contains references to the connections selected on the Connection Manager page of the Script Transformation Editor.</span></span>

    -   <span data-ttu-id="59104-134">`Variables`Classe di raccolta che contiene riferimenti alle variabili immesse nelle `ReadOnlyVariable` proprietà e nella `ReadWriteVariables` pagina **script** di **Editor trasformazione script**.</span><span class="sxs-lookup"><span data-stu-id="59104-134">A `Variables` collection class that contains references to the variables entered in the `ReadOnlyVariable` and `ReadWriteVariables` properties on the **Script** page of the **Script Transformation Editor**.</span></span>

-   <span data-ttu-id="59104-135">L' `BufferWrapper` elemento del progetto contiene una classe che eredita da <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> per ogni input e output configurato nella pagina **input e** output di **Editor trasformazione script**.</span><span class="sxs-lookup"><span data-stu-id="59104-135">The `BufferWrapper` project item contains a class that inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> for each input and output configured on the **Inputs and Outputs** page of the **Script Transformation Editor**.</span></span> <span data-ttu-id="59104-136">Ognuna di queste classi contiene proprietà della funzione di accesso tipizzate corrispondenti alle colonne di input e output configurate e i buffer del flusso di dati contenenti le colonne.</span><span class="sxs-lookup"><span data-stu-id="59104-136">Each of these classes contains typed accessor properties that correspond to the configured input and output columns, and the data flow buffers that contain the columns.</span></span>

 <span data-ttu-id="59104-137">Per informazioni su come usare questi oggetti, metodi e proprietà, vedere [Informazioni sul modello a oggetti del componente script](understanding-the-script-component-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="59104-137">For information about how to use these objects, methods, and properties, see [Understanding the Script Component Object Model](understanding-the-script-component-object-model.md).</span></span> <span data-ttu-id="59104-138">Per informazioni su come usare i metodi e le proprietà di queste classi in un tipo di componente script specifico, vedere la sezione [Ulteriori esempi di componente script](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="59104-138">For information about how to use the methods and properties of these classes in a particular type of Script component, see the section [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span> <span data-ttu-id="59104-139">Negli argomenti di esempio vengono inoltre presentati esempi di codice completi.</span><span class="sxs-lookup"><span data-stu-id="59104-139">The example topics also contain complete code samples.</span></span>

 <span data-ttu-id="59104-140">Quando si configura il componente di script come trasformazione, nell'elemento del progetto `ScriptMain` è incluso il seguente codice generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="59104-140">When you configure the Script component as a transformation, the `ScriptMain` project item contains the following autogenerated code.</span></span> <span data-ttu-id="59104-141">Nel modello del codice sono inoltre disponibili una panoramica del componente di script, nonché informazioni aggiuntive su come recuperare e modificare oggetti SSIS, quali variabili, eventi e connessioni.</span><span class="sxs-lookup"><span data-stu-id="59104-141">The code template also provides an overview of the Script component, and additional information on how to retrieve and manipulate SSIS objects, such as variables, events, and connections.</span></span>

```vb
' Microsoft SQL Server Integration Services Script Component
' Write scripts using Microsoft Visual Basic 2008.
' ScriptMain is the entry point class of the script.

Imports System
Imports System.Data
Imports System.Math
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

<Microsoft.SqlServer.Dts.Pipeline.SSISScriptComponentEntryPointAttribute> _
<CLSCompliant(False)> _
Public Class ScriptMain
    Inherits UserComponent

    Public Overrides Sub PreExecute()
        MyBase.PreExecute()
        '
        ' Add your code here for preprocessing or remove if not needed
        '
    End Sub

    Public Overrides Sub PostExecute()
        MyBase.PostExecute()
        '
        ' Add your code here for postprocessing or remove if not needed
        ' You can set read/write variables here, for example:
        ' Me.Variables.MyIntVar = 100
        '
    End Sub

    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)
        '
        ' Add your code here
        '
    End Sub

End Class
```

```csharp
/* Microsoft SQL Server Integration Services user script component
*  Write scripts using Microsoft Visual C# 2008.
*  ScriptMain is the entry point class of the script.*/

using System;
using System.Data;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

[Microsoft.SqlServer.Dts.Pipeline.SSISScriptComponentEntryPointAttribute]
public class ScriptMain : UserComponent
{

    public override void PreExecute()
    {
        base.PreExecute();
        /*
          Add your code here for preprocessing or remove if not needed
        */
    }

    public override void PostExecute()
    {
        base.PostExecute();
        /*
          Add your code here for postprocessing or remove if not needed
          You can set read/write variables here, for example:
          Variables.MyIntVar = 100
        */
    }

    public override void Input0_ProcessInputRow(Input0Buffer Row)
    {
        /*
          Add your code here
        */
    }

}
```

#### <a name="additional-project-items-in-the-script-component-project"></a><span data-ttu-id="59104-142">Altri elementi del progetto del componente script</span><span class="sxs-lookup"><span data-stu-id="59104-142">Additional Project Items in the Script Component Project</span></span>
 <span data-ttu-id="59104-143">Il progetto del componente script può includere elementi diversi dall'elemento `ScriptMain` predefinito.</span><span class="sxs-lookup"><span data-stu-id="59104-143">The Script component project can include items other than the default `ScriptMain` item.</span></span> <span data-ttu-id="59104-144">È possibile aggiungere al progetto classi, moduli, file di codice e cartelle ed è possibile utilizzare le cartelle per organizzare gruppi di elementi.</span><span class="sxs-lookup"><span data-stu-id="59104-144">You can add classes, modules, code files, and folders to the project, and you can use folders to organize groups of items.</span></span>

 <span data-ttu-id="59104-145">Tutti gli elementi aggiunti vengono salvati in modo permanente nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="59104-145">All the items that you add are persisted inside the package.</span></span>

#### <a name="references-in-the-script-component-project"></a><span data-ttu-id="59104-146">Riferimenti nel progetto del componente script</span><span class="sxs-lookup"><span data-stu-id="59104-146">References in the Script Component Project</span></span>
 <span data-ttu-id="59104-147">Per aggiungere riferimenti agli assembly gestiti, fare clic con il pulsante destro del mouse sul progetto di attività script in **Esplora progetti** e quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="59104-147">You can add references to managed assemblies by right-clicking the Script task project in **Project Explorer**, and then clicking **Add Reference**.</span></span> <span data-ttu-id="59104-148">Per altre informazioni, vedere [Riferimenti ad altri assembly nelle soluzioni di scripting](../referencing-other-assemblies-in-scripting-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="59104-148">For more information, see [Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="59104-149">È possibile visualizzare i riferimenti al progetto nell'ambiente IDE di VSTA in **Visualizzazione classi** o in **Esplora progetti**.</span><span class="sxs-lookup"><span data-stu-id="59104-149">You can view project references in the VSTA IDE in **Class View** or in **Project Explorer**.</span></span> <span data-ttu-id="59104-150">Queste finestre possono essere aperte dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="59104-150">You open either of these windows from the **View** menu.</span></span> <span data-ttu-id="59104-151">È possibile aggiungere un nuovo riferimento dal menu **Progetto**, da **Esplora progetti** o da **Visualizzazione classi**.</span><span class="sxs-lookup"><span data-stu-id="59104-151">You can add a new reference from the **Project** menu, from **Project Explorer**, or from **Class View**.</span></span>

## <a name="interacting-with-the-package-in-the-script-component"></a><span data-ttu-id="59104-152">Interazione con il pacchetto nel componente script</span><span class="sxs-lookup"><span data-stu-id="59104-152">Interacting with the Package in the Script Component</span></span>
 <span data-ttu-id="59104-153">Tramite lo script personalizzato scritto nel componente script è possibile accedere e utilizzare variabili e gestioni connessioni del pacchetto contenitore attraverso funzioni di accesso fortemente tipizzate nelle classi di base generate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="59104-153">The custom script that you write in the Script component can access and use variables and connection managers from the containing package through strongly-typed accessors in the auto-generated base classes.</span></span> <span data-ttu-id="59104-154">Tuttavia, è necessario configurare sia le variabili sia le gestioni connessioni prima di passare alla modalità di progettazione codice per renderle disponibili allo script.</span><span class="sxs-lookup"><span data-stu-id="59104-154">However, you must configure both variables and connection managers before entering code-design mode if you want to make them available to your script.</span></span> <span data-ttu-id="59104-155">È inoltre possibile generare eventi ed eseguire registrazioni dal codice del componente script.</span><span class="sxs-lookup"><span data-stu-id="59104-155">You can also raise events and perform logging from your Script component code.</span></span>

 <span data-ttu-id="59104-156">Gli elementi del progetto generati automaticamente nel progetto del componente script forniscono i seguenti oggetti, metodi e proprietà per l'interazione con il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="59104-156">The autogenerated project items in the Script component project provide the following objects, methods, and properties for interacting with the package.</span></span>

|<span data-ttu-id="59104-157">Funzionalità del pacchetto</span><span class="sxs-lookup"><span data-stu-id="59104-157">Package Feature</span></span>|<span data-ttu-id="59104-158">Metodo di accesso</span><span class="sxs-lookup"><span data-stu-id="59104-158">Access Method</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="59104-159">variables</span><span class="sxs-lookup"><span data-stu-id="59104-159">Variables</span></span>|<span data-ttu-id="59104-160">Utilizzare le proprietà delle funzioni di accesso denominate e tipizzate nella classe della raccolta `Variables` nell'elemento del progetto `ComponentWrapper`, esposto tramite la proprietà `Variables` della classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="59104-160">Use the named and typed accessor properties in the `Variables` collection class in the `ComponentWrapper` project item, exposed through the `Variables` property of the `ScriptMain` class.</span></span><br /><br /> <span data-ttu-id="59104-161">Il metodo `PreExecute` può accedere unicamente a variabili di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="59104-161">The `PreExecute` method can access only read-only variables.</span></span> <span data-ttu-id="59104-162">Il metodo `PostExecute` può accedere sia a variabili di sola lettura sia a variabili di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="59104-162">The `PostExecute` method can access both read-only and read/write variables.</span></span>|
|<span data-ttu-id="59104-163">Connessioni</span><span class="sxs-lookup"><span data-stu-id="59104-163">Connections</span></span>|<span data-ttu-id="59104-164">Utilizzare le proprietà delle funzioni di accesso denominate e tipizzate nella classe della raccolta `Connections` nell'elemento del progetto `ComponentWrapper`, esposto tramite la proprietà `Connections` della classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="59104-164">Use the named and typed accessor properties in the `Connections` collection class in the `ComponentWrapper` project item, exposed through the `Connections` property of the `ScriptMain` class.</span></span>|
|<span data-ttu-id="59104-165">Eventi</span><span class="sxs-lookup"><span data-stu-id="59104-165">Events</span></span>|<span data-ttu-id="59104-166">Generare eventi tramite la <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> proprietà della `ScriptMain` classe e i metodi \*\*Fire \<X> \*\* dell' <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="59104-166">Raise events by using the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the `ScriptMain` class and the **Fire\<X>** methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span>|
|<span data-ttu-id="59104-167">Registrazione</span><span class="sxs-lookup"><span data-stu-id="59104-167">Logging</span></span>|<span data-ttu-id="59104-168">Eseguire la registrazione utilizzando il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> della classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="59104-168">Perform logging by using the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method of the `ScriptMain` class.</span></span>|

## <a name="debugging-the-script-component"></a><span data-ttu-id="59104-169">Debug del componente script</span><span class="sxs-lookup"><span data-stu-id="59104-169">Debugging the Script Component</span></span>
 <span data-ttu-id="59104-170">Per eseguire il debug del codice nel componente di script, impostare almeno un punto di interruzione nel codice, quindi chiudere l'IDE di VSTA per eseguire il pacchetto in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59104-170">To debug the code in your Script component, set at least one breakpoint in the code, and then close the VSTA IDE to run the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="59104-171">Quando l'esecuzione del pacchetto entra nel componente di script, l'IDE di VSTA viene riaperto e visualizza il codice in modalità di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="59104-171">When package execution enters the Script component, the VSTA IDE reopens and displays your code in read-only mode.</span></span> <span data-ttu-id="59104-172">Quando l'esecuzione raggiunge il punto di interruzione, è possibile esaminare i valori delle variabili e scorrere il codice rimanente.</span><span class="sxs-lookup"><span data-stu-id="59104-172">After execution reaches your breakpoint, you can examine variable values and step through the remaining code.</span></span>

> [!NOTE]
>  <span data-ttu-id="59104-173">Non è possibile eseguire il debug di un componente di script se l'attività viene eseguita nell'ambito di un pacchetto figlio eseguito da un'attività Esegui pacchetto.</span><span class="sxs-lookup"><span data-stu-id="59104-173">You cannot debug a Script component when you run the Script component as part of a child package that is run from an Execute Package task.</span></span> <span data-ttu-id="59104-174">In tali circostanze, i punti di interruzione impostati all'interno del componente di script del pacchetto figlio verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="59104-174">Breakpoints that you set in the Script component in the child package are disregarded in these circumstances.</span></span> <span data-ttu-id="59104-175">È possibile eseguire il debug del pacchetto figlio normalmente eseguendolo separatamente.</span><span class="sxs-lookup"><span data-stu-id="59104-175">You can debug the child package normally by running it separately.</span></span>

> [!NOTE]
>  <span data-ttu-id="59104-176">Quando si esegue il debug di un pacchetto che contiene più componenti di script, il debugger è in grado di elaborarne solo uno.</span><span class="sxs-lookup"><span data-stu-id="59104-176">When you debug a package that contains multiple Script components, the debugger debugs one Script component.</span></span> <span data-ttu-id="59104-177">Il sistema può eseguire il debug di un altro componente di script se il debugger termina l'elaborazione, come nel caso di un contenitore Ciclo ForEach o Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="59104-177">The system can debug another Script component if the debugger completes, as in the case of a Foreach Loop or For Loop container.</span></span>

 <span data-ttu-id="59104-178">È anche possibile monitorare l'esecuzione del componente di script utilizzando i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="59104-178">You can also monitor the execution of the Script component by using the following methods:</span></span>

-   <span data-ttu-id="59104-179">Interrompere l'esecuzione e visualizzare un messaggio modale usando il `MessageBox.Show` Metodo nello spazio dei nomi **System. Windows. Forms** .</span><span class="sxs-lookup"><span data-stu-id="59104-179">Interrupt execution and display a modal message by using the `MessageBox.Show` method in the **System.Windows.Forms** namespace.</span></span> <span data-ttu-id="59104-180">Rimuovere il codice al termine del processo di debug.</span><span class="sxs-lookup"><span data-stu-id="59104-180">(Remove this code after you complete the debugging process.)</span></span>

-   <span data-ttu-id="59104-181">Generare eventi per messaggi informativi, avvisi ed errori.</span><span class="sxs-lookup"><span data-stu-id="59104-181">Raise events for informational messages, warnings, and errors.</span></span> <span data-ttu-id="59104-182">I metodi FireInformation, FireWarning e FireError visualizzano la descrizione dell'evento nella finestra **Output** di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="59104-182">The FireInformation, FireWarning, and FireError methods display the event description in the Visual Studio **Output** window.</span></span> <span data-ttu-id="59104-183">I metodi FireProgress, Console.Write e Console.WriteLine, tuttavia, non visualizzano alcuna informazione nella finestra **Output**.</span><span class="sxs-lookup"><span data-stu-id="59104-183">However, the FireProgress method, the Console.Write method, and Console.WriteLine method do not display any information in the **Output** window.</span></span> <span data-ttu-id="59104-184">I messaggi dell'evento FireProgress vengono visualizzati nella scheda **Stato** di Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59104-184">Messages from the FireProgress event appear on the **Progress** tab of [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="59104-185">Per altre informazioni, vedere [Generazione di eventi nel componente script](../../data-flow/transformations/script-component.md).</span><span class="sxs-lookup"><span data-stu-id="59104-185">For more information, see [Raising Events in the Script Component](../../data-flow/transformations/script-component.md).</span></span>

-   <span data-ttu-id="59104-186">Registrare eventi o messaggi definiti dall'utente nei provider di log abilitati.</span><span class="sxs-lookup"><span data-stu-id="59104-186">Log events or user-defined messages to enabled logging providers.</span></span> <span data-ttu-id="59104-187">Per altre informazioni, vedere [Registrazione nel componente script](logging-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="59104-187">For more information, see [Logging in the Script Component](logging-in-the-script-component.md).</span></span>

 <span data-ttu-id="59104-188">Se si vuole soltanto esaminare l'output di un componente script configurato come origine o trasformazione, senza salvare i dati in una destinazione, è possibile arrestare il flusso di dati con una [trasformazione Conteggio righe](../../data-flow/transformations/row-count-transformation.md) e collegare un visualizzatore dati all'output del componente script.</span><span class="sxs-lookup"><span data-stu-id="59104-188">If you just want to examine the output of a Script component configured as a source or as a transformation, without saving the data to a destination, you can stop the data flow with a [Row Count Transformation](../../data-flow/transformations/row-count-transformation.md) and attach a data viewer to the output of the Script component.</span></span> <span data-ttu-id="59104-189">Per informazioni sui visualizzatori dati, vedere [Debug di un flusso di dati](../../troubleshooting/debugging-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="59104-189">For information about data viewers, see [Debugging Data Flow](../../troubleshooting/debugging-data-flow.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="59104-190">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="59104-190">In This Section</span></span>
 <span data-ttu-id="59104-191">Per ulteriori informazioni sulla codifica del componente script, vedere gli argomenti seguenti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="59104-191">For more information about coding the Script component, see the following topics in this section.</span></span>

 <span data-ttu-id="59104-192">[Informazioni sullo Script Component Object Model](understanding-the-script-component-object-model.md) Viene illustrato come utilizzare gli oggetti, i metodi e le proprietà disponibili nel componente script.</span><span class="sxs-lookup"><span data-stu-id="59104-192">[Understanding the Script Component Object Model](understanding-the-script-component-object-model.md) Explains how to use the objects, methods, and properties available in the Script component.</span></span>

 <span data-ttu-id="59104-193">[Riferimento ad altri assembly nelle soluzioni di scripting](../referencing-other-assemblies-in-scripting-solutions.md) Viene illustrato come fare riferimento a oggetti dalla [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] libreria di classi nel componente script.</span><span class="sxs-lookup"><span data-stu-id="59104-193">[Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md) Explains how to reference objects from the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library in the Script component.</span></span>

 <span data-ttu-id="59104-194">[Simulazione di un output degli errori per il componente script](../../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md) Viene illustrato come simulare un output degli errori per le righe che generano errori durante l'elaborazione da parte del componente script.</span><span class="sxs-lookup"><span data-stu-id="59104-194">[Simulating an Error Output for the Script Component](../../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md) Explains how to simulate an error output for rows that raise errors during processing by the Script component.</span></span>

## <a name="external-resources"></a><span data-ttu-id="59104-195">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="59104-195">External Resources</span></span>

-   <span data-ttu-id="59104-196">Intervento del blog, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661) (Problemi di installazione e configurazione di VSTA per le installazioni SSIS 2008 e R2), in blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="59104-196">Blog entry, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), on blogs.msdn.com.</span></span>

<span data-ttu-id="59104-197">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="59104-197">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="59104-198">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="59104-198">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="59104-199">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="59104-199">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="59104-200">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="59104-200">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="59104-201">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59104-201">See Also</span></span>
 [<span data-ttu-id="59104-202">Configurazione del componente script nell'editor corrispondente</span><span class="sxs-lookup"><span data-stu-id="59104-202">Configuring the Script Component in the Script Component Editor</span></span>](configuring-the-script-component-in-the-script-component-editor.md)


