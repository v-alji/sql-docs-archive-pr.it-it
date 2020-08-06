---
title: Sviluppo di un'interfaccia utente per un'attività personalizzata | Microsoft Docs
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
- custom user interfaces [Integration Services]
- IDtsTaskUI interface
- DtsTaskAttribute attribute
- custom tasks [Integration Services], user interface
- custom user interface [Integration Services], custom tasks
- user interface [Integration Services]
- SSIS custom tasks, user interface
ms.assetid: 1e940cd1-c5f8-4527-b678-e89ba5dc398a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed96bbc302cba4c207e5ce7b2e4fb4b74fed4ee2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636802"
---
# <a name="developing-a-user-interface-for-a-custom-task"></a><span data-ttu-id="cf564-102">Sviluppo di un'interfaccia utente per un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="cf564-102">Developing a User Interface for a Custom Task</span></span>
  <span data-ttu-id="cf564-103">Il modello a oggetti di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] offre agli sviluppatori di attività la possibilità di creare facilmente un'interfaccia utente personalizzata per un'attività da integrare e visualizzare in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf564-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] object model provides custom task developers the ability to easily create a custom user interface for a task that can then be integrated and displayed in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="cf564-104">L'interfaccia utente può fornire informazioni utili all'utente in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] oltre a indicazioni su come configurare correttamente le proprietà e le impostazioni dell'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="cf564-104">The user interface can provide helpful information to the user in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, and guide users to correctly configure the properties and settings of the custom task.</span></span>  
  
 <span data-ttu-id="cf564-105">Per sviluppare un'interfaccia utente personalizzata per un'attività, è necessario utilizzare due classi importanti,</span><span class="sxs-lookup"><span data-stu-id="cf564-105">Developing a custom user interface for a task involves using two important classes.</span></span> <span data-ttu-id="cf564-106">descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cf564-106">The following table describes those classes.</span></span>  
  
|<span data-ttu-id="cf564-107">Classe</span><span class="sxs-lookup"><span data-stu-id="cf564-107">Class</span></span>|<span data-ttu-id="cf564-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cf564-108">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>|<span data-ttu-id="cf564-109">Attributo che identifica un'attività gestita e fornisce informazioni della fase di progettazione tramite le proprietà per controllare le modalità di visualizzazione e di interazione di Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] con l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="cf564-109">An attribute that identifies a managed task, and supplies design-time information through its properties to control how [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer displays and interacts with the object.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>|<span data-ttu-id="cf564-110">Interfaccia utilizzata dall'attività per associare l'attività alla relativa interfaccia utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="cf564-110">An interface used by the task to associate the task with its custom user interface.</span></span>|  
  
 <span data-ttu-id="cf564-111">In questa sezione viene descritto il ruolo dell'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> e dell'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> durante lo sviluppo di un'interfaccia utente per un'attività personalizzata e vengono fornite informazioni su come creare, integrare, distribuire e sottoporre a debug l'attività all'interno di Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf564-111">This section describes the role of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute and the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface when you are developing a user interface for a custom task, and provides details about how to create, integrate, deploy, and debug the task within [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="cf564-112">Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] fornisce più punti di ingresso all'interfaccia utente dell'attività. L'utente può scegliere **Modifica** dal menu di scelta rapida, fare doppio clic sull'attività o fare clic sul collegamento **Visualizza editor** nella parte inferiore della finestra delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="cf564-112">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer provides multiple entry points to the user interface for the task: the user can select **Edit** on the shortcut menu, double-click the task, or click the **Show Editor** link at the bottom of the property sheet.</span></span> <span data-ttu-id="cf564-113">Quando l'utente accede a uno di questi punti di ingresso, Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] trova e carica l'assembly che contiene l'interfaccia utente per l'attività.</span><span class="sxs-lookup"><span data-stu-id="cf564-113">When the user accesses one of these entry points, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer locates and loads the assembly that contains the user interface for the task.</span></span> <span data-ttu-id="cf564-114">L'interfaccia utente per l'attività è responsabile della creazione della finestra di dialogo delle proprietà che l'utente visualizza in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf564-114">The user interface for the task is responsible for creating the properties dialog box that is displayed to the user in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="cf564-115">L'attività e la relativa interfaccia utente sono entità separate</span><span class="sxs-lookup"><span data-stu-id="cf564-115">A task and its user interface are separate entities.</span></span> <span data-ttu-id="cf564-116">che devono essere implementate in assembly distinti per ridurre gli interventi di localizzazione, distribuzione e manutenzione.</span><span class="sxs-lookup"><span data-stu-id="cf564-116">They should be implemented in separate assemblies to reduce localization, deployment, and maintenance work.</span></span> <span data-ttu-id="cf564-117">La DLL dell'attività non carica, chiama né in genere contiene informazioni sulla relativa interfaccia utente, ad eccezione delle informazioni contenute nei valori dell'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> codificati nell'attività.</span><span class="sxs-lookup"><span data-stu-id="cf564-117">The task DLL does not load, call, or generally contain any knowledge of its user interface, except for the information that is contained in the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute values coded in the task.</span></span> <span data-ttu-id="cf564-118">Questo è l'unico modo in cui un'attività è associata alla propria interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="cf564-118">This is the only way that a task and its user interface are associated.</span></span>  
  
## <a name="the-dtstask-attribute"></a><span data-ttu-id="cf564-119">Attributo DtsTask</span><span class="sxs-lookup"><span data-stu-id="cf564-119">The DtsTask Attribute</span></span>  
 <span data-ttu-id="cf564-120">L'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> è incluso nel codice della classe dell'attività per associare un'attività alla relativa interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="cf564-120">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute is included in the task class code to associate a task with its user interface.</span></span> <span data-ttu-id="cf564-121">Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] utilizza le proprietà dell'attributo per determinare la modalità di visualizzazione dell'attività nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="cf564-121">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the properties of the attribute to determine how to display the task in the designer.</span></span> <span data-ttu-id="cf564-122">Queste proprietà includono il nome da visualizzare e l'icona, se presente.</span><span class="sxs-lookup"><span data-stu-id="cf564-122">These properties include the name to display and the icon, if any.</span></span>  
  
 <span data-ttu-id="cf564-123">Nella tabella seguente sono descritte le proprietà dell'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cf564-123">The following table describes the properties of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute.</span></span>  
  
|<span data-ttu-id="cf564-124">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cf564-124">Property</span></span>|<span data-ttu-id="cf564-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cf564-125">Description</span></span>|  
|--------------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>|<span data-ttu-id="cf564-126">Visualizza il nome dell'attività nella casella degli strumenti del Flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="cf564-126">Displays the task name in the Control Flow toolbox.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A>|<span data-ttu-id="cf564-127">Descrizione dell'attività (ereditata da <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute>).</span><span class="sxs-lookup"><span data-stu-id="cf564-127">The task description (inherited from <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute>).</span></span> <span data-ttu-id="cf564-128">Questa proprietà è visualizzata nelle descrizioni comandi.</span><span class="sxs-lookup"><span data-stu-id="cf564-128">This property is shown in ToolTips.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A>|<span data-ttu-id="cf564-129">Icona visualizzata in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf564-129">The icon displayed in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.RequiredProductLevel%2A>|<span data-ttu-id="cf564-130">Se utilizzata, impostarla su uno dei valori dell'enumerazione <xref:Microsoft.SqlServer.Dts.Runtime.DTSProductLevel>.</span><span class="sxs-lookup"><span data-stu-id="cf564-130">If used, set it to one of the values in the <xref:Microsoft.SqlServer.Dts.Runtime.DTSProductLevel> enumeration.</span></span> <span data-ttu-id="cf564-131">Ad esempio: `RequiredProductLevel = DTSProductLevel.None`.</span><span class="sxs-lookup"><span data-stu-id="cf564-131">For example, `RequiredProductLevel = DTSProductLevel.None`.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.TaskContact%2A>|<span data-ttu-id="cf564-132">Contiene informazioni di contatto per i casi in cui l'attività richiede supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="cf564-132">Holds contact information for occasions when the task requires technical support.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.TaskType%2A>|<span data-ttu-id="cf564-133">Assegna un tipo all'attività.</span><span class="sxs-lookup"><span data-stu-id="cf564-133">Assigns a type to the task.</span></span>|  
|<span data-ttu-id="cf564-134">Attribute.TypeId</span><span class="sxs-lookup"><span data-stu-id="cf564-134">Attribute.TypeId</span></span>|<span data-ttu-id="cf564-135">Se implementata in una classe derivata, ottiene un identificatore univoco per questo attributo.</span><span class="sxs-lookup"><span data-stu-id="cf564-135">When implemented in a derived class, gets a unique identifier for this Attribute.</span></span> <span data-ttu-id="cf564-136">Per ulteriori informazioni, vedere la proprietà `Attribute.TypeID` nella libreria di classi di Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf564-136">For more information, see `Attribute.TypeID` property in the .NET Framework Class Library.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A>|<span data-ttu-id="cf564-137">Nome di tipo dell'assembly utilizzato da Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] per caricare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="cf564-137">The type name of the assembly that is used by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to load the assembly.</span></span> <span data-ttu-id="cf564-138">Questa proprietà viene utilizzata per trovare l'assembly dell'interfaccia utente per l'attività.</span><span class="sxs-lookup"><span data-stu-id="cf564-138">This property is used to find the user interface assembly for the task.</span></span>|  
  
 <span data-ttu-id="cf564-139">Nell'esempio di codice seguente è illustrato l'aspetto di <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> codificato sopra la definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="cf564-139">The following code example shows the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> as it would look, coded above the class definition.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.SSIS.Samples  
{  
  [DtsTask  
  (  
   DisplayName = "MyTask",  
   IconResource = "MyTask.MyTaskIcon.ico",  
   UITypeName = "My Custom Task," +  
   "Version=1.0.0.0," +  
   "Culture = Neutral," +  
   "PublicKeyToken = 12345abc6789de01",  
   TaskType = "PackageMaintenance",  
   TaskContact = "MyTask; company name; any other information",  
   RequiredProductLevel = DTSProductLevel.None  
   )]  
  public class MyTask : Task  
  {  
    // Your code here.  
  }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsTask(DisplayName:="MyTask", _  
 IconResource:="MyTask.MyTaskIcon.ico", _  
 UITypeName:="My Custom Task," & _  
 "Version=1.0.0.0,Culture=Neutral," & _  
 "PublicKeyToken=12345abc6789de01", _  
 TaskType:="PackageMaintenance", _  
 TaskContact:="MyTask; company name; any other information", _  
 RequiredProductLevel:=DTSProductLevel.None)> _  
Public Class MyTask  
  Inherits Task  
  
  ' Your code here.  
  
End Class 'MyTask  
```  
  
 <span data-ttu-id="cf564-140">Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] utilizza la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> dell'attributo che include il nome dell'assembly, il nome del tipo, la versione, la lingua e il token di chiave pubblica per individuare l'assembly nella Global Assembly Cache (GAC) e caricarlo per l'utilizzo nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="cf564-140">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> property of the attribute that includes the assembly name, type name, version, culture, and public key token, to locate the assembly in the Global Assembly Cache (GAC) and load it for use by the designer.</span></span>  
  
 <span data-ttu-id="cf564-141">Dopo l'individuazione dell'assembly, Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] utilizza le altre proprietà dell'attributo per visualizzare informazioni aggiuntive sull'attività in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)], ad esempio il nome, l'icona e la descrizione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="cf564-141">After the assembly has been located, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the other properties in the attribute to display additional information about the task in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, such as the name, icon, and description of the task.</span></span>  
  
 <span data-ttu-id="cf564-142">Le proprietà <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> specificano la modalità con cui l'attività viene presentata all'utente.</span><span class="sxs-lookup"><span data-stu-id="cf564-142">The <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> properties specify how the task is presented to the user.</span></span> <span data-ttu-id="cf564-143">La proprietà <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> contiene l'ID di risorsa dell'icona incorporata nell'assembly dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="cf564-143">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> property contains the resource ID of the icon embedded in the user interface assembly.</span></span> <span data-ttu-id="cf564-144">La finestra di progettazione carica la risorsa dell'icona in base all'ID dall'assembly e la visualizza accanto al nome dell'attività nella casella degli strumenti e nell'area di progettazione quando l'attività viene aggiunta al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cf564-144">The designer loads the icon resource by ID from the assembly, and displays it next to the task name in the toolbox and on the designer surface when the task is added to a package.</span></span> <span data-ttu-id="cf564-145">Se un'attività non prevede una risorsa di icona, la finestra di progettazione utilizza un'icona predefinita per l'attività.</span><span class="sxs-lookup"><span data-stu-id="cf564-145">If a task does not provide an icon resource, the designer uses a default icon for the task.</span></span>  
  
## <a name="the-idtstaskui-interface"></a><span data-ttu-id="cf564-146">Interfaccia IDTSTaskUI</span><span class="sxs-lookup"><span data-stu-id="cf564-146">The IDTSTaskUI Interface</span></span>  
 <span data-ttu-id="cf564-147">L'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> definisce la raccolta di metodi e proprietà chiamati da Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] per inizializzare e visualizzare l'interfaccia utente associata all'attività.</span><span class="sxs-lookup"><span data-stu-id="cf564-147">The <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface defines the collection of methods and properties called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to initialize and display the user interface associated with the task.</span></span> <span data-ttu-id="cf564-148">Quando viene richiamata l'interfaccia utente per un'attività, la finestra di progettazione chiama il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.Initialize%2A>, implementato dall'interfaccia utente dell'attività quando è stata scritta, quindi fornisce le raccolte <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> e <xref:Microsoft.SqlServer.Dts.Runtime.Connections> rispettivamente dell'attività e del pacchetto come parametri.</span><span class="sxs-lookup"><span data-stu-id="cf564-148">When the user interface for a task is invoked, the designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.Initialize%2A> method, implemented by the task user interface when you wrote it, and then provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> and <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collections of the task and package, respectively, as parameters.</span></span> <span data-ttu-id="cf564-149">Queste raccolte vengono archiviate in locale e utilizzate successivamente nel metodo <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf564-149">These collections are stored locally, and used subsequently in the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method.</span></span>  
  
 <span data-ttu-id="cf564-150">La finestra di progettazione chiama il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> per richiedere la finestra visualizzata in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf564-150">The designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method to request the window that is displayed in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="cf564-151">L'attività crea un'istanza della finestra che contiene l'interfaccia utente per l'attività e restituisce l'interfaccia utente alla finestra di progettazione per la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf564-151">The task creates an instance of the window that contains the user interface for the task, and returns the user interface to the designer for display.</span></span> <span data-ttu-id="cf564-152">In genere, gli oggetti <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> e <xref:Microsoft.SqlServer.Dts.Runtime.Connections> vengono forniti alla finestra tramite un costruttore di overload, in modo che possano essere utilizzati per configurare l'attività.</span><span class="sxs-lookup"><span data-stu-id="cf564-152">Typically, the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> and <xref:Microsoft.SqlServer.Dts.Runtime.Connections> objects are provided to the window through an overloaded constructor so they can be used to configure the task.</span></span>  
  
 <span data-ttu-id="cf564-153">Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] chiama il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> dell'interfaccia utente dell'attività per visualizzare l'interfaccia utente per l'attività.</span><span class="sxs-lookup"><span data-stu-id="cf564-153">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method of the task UI to display the user interface for the task.</span></span> <span data-ttu-id="cf564-154">L'interfaccia utente dell'attività restituisce il Windows Form da questo metodo e Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] visualizza questo form come finestra di dialogo modale.</span><span class="sxs-lookup"><span data-stu-id="cf564-154">The task user interface returns the Windows form from this method, and [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer shows this form as a modal dialog box.</span></span> <span data-ttu-id="cf564-155">Quando il form viene chiuso, Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] esamina il valore della proprietà `DialogResult` del form per determinare se l'attività è stata modificata e se queste modifiche devono essere salvate.</span><span class="sxs-lookup"><span data-stu-id="cf564-155">When the form is closed, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer examines the value of the `DialogResult` property of the form to determine whether the task has been modified and if these modifications should be saved.</span></span> <span data-ttu-id="cf564-156">Se il valore della proprietà `DialogResult` è `OK`, Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] chiama i metodi di persistenza dell'attività per salvare le modifiche; in caso contrario, le modifiche vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="cf564-156">If the value of the `DialogResult` property is `OK`, the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls the persistence methods of the task to save the changes; otherwise, the changes are discarded.</span></span>  
  
 <span data-ttu-id="cf564-157">Nell'esempio di codice seguente viene implementata l'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> e si presuppone l'esistenza di una classe di Windows Form denominata SampleTaskForm.</span><span class="sxs-lookup"><span data-stu-id="cf564-157">The following code sample implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface, and assumes the existence of a Windows form class named SampleTaskForm.</span></span>  
  
```csharp  
using System;  
using System.Windows.Forms;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Runtime.Design;  
  
namespace Sample  
{  
   public class HelloWorldTaskUI : IDtsTaskUI  
   {  
      TaskHost   taskHost;  
      Connections connections;  
      public void Initialize(TaskHost taskHost, IServiceProvider serviceProvider)  
      {  
         this.taskHost = taskHost;  
         IDtsConnectionService cs = serviceProvider.GetService  
         ( typeof( IDtsConnectionService ) ) as   IDtsConnectionService;   
         this.connections = cs.GetConnections();  
      }  
      public ContainerControl GetView()  
      {  
        return new HelloWorldTaskForm(this.taskHost, this.connections);  
      }  
     public void Delete(IWin32Window parentWindow)  
     {  
     }  
     public void New(IWin32Window parentWindow)  
     {  
     }  
   }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Runtime.Design  
Imports System.Windows.Forms  
  
Public Class HelloWorldTaskUI  
  Implements IDtsTaskUI  
  
  Dim taskHost As TaskHost  
  Dim connections As Connections  
  
  Public Sub Initialize(ByVal taskHost As TaskHost, ByVal serviceProvider As IServiceProvider) _  
    Implements IDtsTaskUI.Initialize  
  
    Dim cs As IDtsConnectionService  
  
    Me.taskHost = taskHost  
    cs = DirectCast(serviceProvider.GetService(GetType(IDtsConnectionService)), IDtsConnectionService)  
    Me.connections = cs.GetConnections()  
  
  End Sub  
  
  Public Function GetView() As ContainerControl _  
    Implements IDtsTaskUI.GetView  
  
    Return New HelloWorldTaskForm(Me.taskHost, Me.connections)  
  
  End Function  
  
  Public Sub Delete(ByVal parentWindow As IWin32Window) _  
    Implements IDtsTaskUI.Delete  
  
  End Sub  
  
  Public Sub [New](ByVal parentWindow As IWin32Window) _  
    Implements IDtsTaskUI.[New]  
  
  End Sub  
  
End Class  
```  
  
<span data-ttu-id="cf564-158">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="cf564-158">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="cf564-159">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="cf564-159">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="cf564-160">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="cf564-160">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="cf564-161">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="cf564-161">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf564-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf564-162">See Also</span></span>  
 <span data-ttu-id="cf564-163">[Creazione di un'attività personalizzata](creating-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="cf564-163">[Creating a Custom Task](creating-a-custom-task.md) </span></span>  
 <span data-ttu-id="cf564-164">[Scrittura del codice di un'attività personalizzata](coding-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="cf564-164">[Coding a Custom Task](coding-a-custom-task.md) </span></span>  
 [<span data-ttu-id="cf564-165">Sviluppo di un'interfaccia utente per un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="cf564-165">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
  
  
