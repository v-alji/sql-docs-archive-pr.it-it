---
title: Sviluppo di un'interfaccia utente per un componente flusso di dati | Microsoft Docs
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
- data flow components [Integration Services], custom editors
- user interfaces [Integration Services]
- custom data flow components [Integration Services], custom editors
- custom component editors [Integration Services]
- IDtsComponentUI interface
- UITypeName property
- custom user interface [Integration Services], custom data flow component
- editors [Integration Services]
ms.assetid: 10b829a1-609b-42e3-9070-cfe5a2bb698c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f97f21ad14a5fa67fb49192931a0cb46d0cb41da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713344"
---
# <a name="developing-a-user-interface-for-a-data-flow-component"></a><span data-ttu-id="e7b53-102">Sviluppo di un'interfaccia utente per un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="e7b53-102">Developing a User Interface for a Data Flow Component</span></span>
  <span data-ttu-id="e7b53-103">Gli sviluppatori di componenti possono fornire un'interfaccia utente personalizzata per un componente, che viene visualizzata in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] quando il componente viene modificato.</span><span class="sxs-lookup"><span data-stu-id="e7b53-103">Component developers can provide a custom user interface for a component, which is displayed in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] when the component is edited.</span></span> <span data-ttu-id="e7b53-104">L'implementazione di un'interfaccia utente personalizzata fornisce notifiche quando il componente viene aggiunto o eliminato da un'attività Flusso di dati e quando per il componente è richiesta la Guida.</span><span class="sxs-lookup"><span data-stu-id="e7b53-104">Implementing a custom user interface provides you with notification when the component is added to or deleted from a data flow task, and when help is requested for the component.</span></span>

 <span data-ttu-id="e7b53-105">Se non si fornisce un'interfaccia utente personalizzata per il componente, gli utenti possono comunque configurare il componente e le relative proprietà personalizzate utilizzando l'editor avanzato.</span><span class="sxs-lookup"><span data-stu-id="e7b53-105">If you do not provide a custom user interface for your component, users can still configure the component and its custom properties by using the Advanced Editor.</span></span> <span data-ttu-id="e7b53-106">È possibile assicurarsi che l'editor avanzato consenta agli utenti di modificare in modo appropriato i valori delle proprietà personalizzate tramite le proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> di <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>, a seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="e7b53-106">You can ensure that the Advanced Editor allows users to edit custom property values appropriately by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> properties of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> when appropriate.</span></span> <span data-ttu-id="e7b53-107">Per altre informazioni, vedere la sezione relativa alla creazione di proprietà personalizzate in [Metodi della fase di progettazione di un componente flusso di dati](design-time-methods-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="e7b53-107">For more information, see "Creating Custom Properties" in [Design-time Methods of a Data Flow Component](design-time-methods-of-a-data-flow-component.md).</span></span>

## <a name="setting-the-uitypename-property"></a><span data-ttu-id="e7b53-108">Impostazione della proprietà UITypeName</span><span class="sxs-lookup"><span data-stu-id="e7b53-108">Setting the UITypeName Property</span></span>
 <span data-ttu-id="e7b53-109">Per fornire un'interfaccia utente personalizzata, lo sviluppatore deve impostare la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> di <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> sul nome di una classe che implementa l'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>.</span><span class="sxs-lookup"><span data-stu-id="e7b53-109">To provide a custom user interface, the developer must set the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> to the name of a class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface.</span></span> <span data-ttu-id="e7b53-110">Quando questa proprietà viene impostata dal componente, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] carica e chiama l'interfaccia utente personalizzata quando il componente viene modificato in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7b53-110">When this property is set by the component, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] loads and calls the custom user interface when the component is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>

 <span data-ttu-id="e7b53-111">La proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> è una stringa delimitata da virgole che identifica il nome completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="e7b53-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property is a comma-delimited string that identifies the fully qualified name of the type.</span></span> <span data-ttu-id="e7b53-112">Nell'elenco seguente sono illustrati, nell'ordine, gli elementi che identificano il tipo:</span><span class="sxs-lookup"><span data-stu-id="e7b53-112">The following list shows, in order, the elements that identify the type:</span></span>

-   <span data-ttu-id="e7b53-113">Nome tipo</span><span class="sxs-lookup"><span data-stu-id="e7b53-113">Type name</span></span>

-   <span data-ttu-id="e7b53-114">Nome assembly</span><span class="sxs-lookup"><span data-stu-id="e7b53-114">Assembly name</span></span>

-   <span data-ttu-id="e7b53-115">Versione file</span><span class="sxs-lookup"><span data-stu-id="e7b53-115">File version</span></span>

-   <span data-ttu-id="e7b53-116">Impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="e7b53-116">Culture</span></span>

-   <span data-ttu-id="e7b53-117">Token di chiave pubblica</span><span class="sxs-lookup"><span data-stu-id="e7b53-117">Public key token</span></span>

 <span data-ttu-id="e7b53-118">Nell'esempio di codice seguente è illustrata una classe che deriva dalla classe di base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> e specifica la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7b53-118">The following code example shows a class that derives from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class and specifies the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property.</span></span>

```csharp
[DtsPipelineComponent(
DisplayName="SampleComponent",
UITypeName="MyNamespace.MyComponentUIClassName,MyAssemblyName,Version=1.0.0.0,Culture=neutral,PublicKeyToken=abcd...",
ComponentType = ComponentType.Transform)]
public class SampleComponent : PipelineComponent
{
//TODO: Implement the component here.
}
```

```vb
<DtsPipelineComponent(DisplayName="SampleComponent", _
UITypeName="MyNamespace.MyComponentUIClassName,MyAssemblyName,Version=1.0.0.0,Culture=neutral,PublicKeyToken=abcd...", ComponentType=ComponentType.Transform)> _ 
Public Class SampleComponent 
 Inherits PipelineComponent 
End Class
```

## <a name="implementing-the-idtscomponentui-interface"></a><span data-ttu-id="e7b53-119">Implementazione dell'interfaccia IDtsComponentUI</span><span class="sxs-lookup"><span data-stu-id="e7b53-119">Implementing the IDtsComponentUI Interface</span></span>
 <span data-ttu-id="e7b53-120">L'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> contiene i metodi chiamati da Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] quando un componente viene aggiunto, eliminato e modificato.</span><span class="sxs-lookup"><span data-stu-id="e7b53-120">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface contains methods that [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls when a component is added, deleted, and edited.</span></span> <span data-ttu-id="e7b53-121">Gli sviluppatori di componenti possono fornire codice nella loro implementazione di questi metodi per interagire con gli utenti del componente.</span><span class="sxs-lookup"><span data-stu-id="e7b53-121">Component developers can provide code in their implementation of these methods to interact with users of the component.</span></span>

 <span data-ttu-id="e7b53-122">Questa classe viene in genere implementata in un assembly distinto dal componente stesso.</span><span class="sxs-lookup"><span data-stu-id="e7b53-122">This class is typically implemented in an assembly separate from the component itself.</span></span> <span data-ttu-id="e7b53-123">Anche se non è obbligatorio utilizzare un assembly distinto, in questo modo lo sviluppatore può compilare e distribuire il componente e l'interfaccia utente indipendentemente l'uno dall'altra e mantenere piccola l'impronta binaria del componente.</span><span class="sxs-lookup"><span data-stu-id="e7b53-123">Although use of a separate assembly is not required, this lets the developer build and deploy the component and the user interface independently of each other, and keeps the binary footprint of the component small.</span></span>

 <span data-ttu-id="e7b53-124">L'implementazione di un'interfaccia utente personalizzata fornisce allo sviluppatore di componenti un maggior controllo sul componente quando viene modificato in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7b53-124">Implementing a custom user interface gives the component developer more control over the component as it is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e7b53-125">Ad esempio, un componente può aggiungere codice al metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A>, che viene chiamato quando il componente viene inizialmente aggiunto a un'attività Flusso di dati, e visualizzare una procedura guidata che consente all'utente di completare la configurazione iniziale del componente.</span><span class="sxs-lookup"><span data-stu-id="e7b53-125">For example, a component can add code to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> method, which is called when a component is initially added to a data flow task, and display a wizard that guides the user through the initial configuration of the component.</span></span>

 <span data-ttu-id="e7b53-126">Dopo aver creato una classe che implementa l'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>, è necessario aggiungere codice per rispondere all'interazione dell'utente con il componente.</span><span class="sxs-lookup"><span data-stu-id="e7b53-126">After you have created a class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface, you must add code to respond to user interaction with the component.</span></span> <span data-ttu-id="e7b53-127">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> fornisce l'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> del componente e viene chiamato prima dei metodi <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7b53-127">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method provides the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface of the component, and is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> methods.</span></span> <span data-ttu-id="e7b53-128">Questo riferimento deve essere archiviato in una variabile membro privata e utilizzato in seguito per modificare i metadati del componente.</span><span class="sxs-lookup"><span data-stu-id="e7b53-128">This reference should be stored in a private member variable and used to modify the component's metadata thereafter.</span></span>

## <a name="modifying-a-component-and-persisting-changes"></a><span data-ttu-id="e7b53-129">Come effettuare modifiche in un componente e renderle persistenti</span><span class="sxs-lookup"><span data-stu-id="e7b53-129">Modifying a Component and Persisting Changes</span></span>
 <span data-ttu-id="e7b53-130">L'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> viene fornita come parametro al metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7b53-130">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface is provided as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method.</span></span> <span data-ttu-id="e7b53-131">Questo riferimento deve essere memorizzato nella cache in una variabile membro dal codice dell'interfaccia utente e quindi utilizzato per modificare il componente in risposta all'interazione dell'utente con l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="e7b53-131">This reference should be cached in a member variable by the user interface code, and then used to modify the component in response to user interaction with the user interface.</span></span>

 <span data-ttu-id="e7b53-132">Anche se è possibile modificare direttamente il componente tramite l'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, è preferibile creare un'istanza di <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> tramite il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7b53-132">Although you can modify the component directly through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, it is better to create an instance of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> method.</span></span> <span data-ttu-id="e7b53-133">Quando si modifica direttamente il componente tramite l'interfaccia, le misure di sicurezza di convalida del componente vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="e7b53-133">When you edit the component directly by using the interface, you bypass the component's validation safeguards.</span></span> <span data-ttu-id="e7b53-134">Il vantaggio dell'utilizzo dell'istanza della fase di progettazione del componente tramite <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> è che ci si assicura che il componente controlli le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="e7b53-134">The advantage of using the design-time instance of the component through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> is that you ensure that the component has control over the changes made to it.</span></span>

 <span data-ttu-id="e7b53-135">Il valore restituito del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> determina se le modifiche apportate a un componente vengono rese persistenti o annullate.</span><span class="sxs-lookup"><span data-stu-id="e7b53-135">The return value of the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method determines whether changes made to a component are persisted or discarded.</span></span> <span data-ttu-id="e7b53-136">Quando questo metodo restituisce `false`, tutte le modifiche vengono annullate; se restituisce `true`, le modifiche al componente vengono rese persistenti e il pacchetto viene contrassegnato in modo da richiederne il salvataggio.</span><span class="sxs-lookup"><span data-stu-id="e7b53-136">When this method returns `false`, all changes are discarded; `true` persists the changes to the component and marks the package as needing to be saved.</span></span>

### <a name="using-the-services-of-the-ssis-designer"></a><span data-ttu-id="e7b53-137">Utilizzo dei servizi di Progettazione SSIS</span><span class="sxs-lookup"><span data-stu-id="e7b53-137">Using the Services of the SSIS Designer</span></span>
 <span data-ttu-id="e7b53-138">Il parametro `IServiceProvider` del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> fornisce l'accesso ai servizi seguenti di Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e7b53-138">The `IServiceProvider` parameter of the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method provides access to the following services of [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer:</span></span>

|<span data-ttu-id="e7b53-139">Service</span><span class="sxs-lookup"><span data-stu-id="e7b53-139">Service</span></span>|<span data-ttu-id="e7b53-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7b53-140">Description</span></span>|
|-------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Design.IDtsClipboardService>|<span data-ttu-id="e7b53-141">Viene utilizzato per determinare se il componente è stato generato come parte di un'operazione Copia/Incolla o Taglia/Incolla.</span><span class="sxs-lookup"><span data-stu-id="e7b53-141">Used to determine whether the component was generated as part of a copy/paste or cut/paste operation.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionService>|<span data-ttu-id="e7b53-142">Viene utilizzato per accedere alle connessioni esistenti o per creare nuove connessioni nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e7b53-142">Used to access existing connections or to create new connections in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Design.IErrorCollectionService>|<span data-ttu-id="e7b53-143">Viene utilizzato per acquisire eventi dai componenti del flusso di dati quando è necessario acquisire tutti gli errori e gli avvisi generati dal componente anziché ricevere solo quelli più recenti.</span><span class="sxs-lookup"><span data-stu-id="e7b53-143">Used to capture events from data flow components when you need to capture all the errors and warnings raised by the component instead of receiving only the last error or warning.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsVariableService>|<span data-ttu-id="e7b53-144">Viene utilizzato per accedere alle variabili esistenti o per creare nuove variabili nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e7b53-144">Used to access existing variables or to create new variables in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Design.IDtsPipelineEnvironmentService>|<span data-ttu-id="e7b53-145">Viene utilizzato dai componenti del flusso di dati per accedere all'attività Flusso di dati padre e ad altri componenti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="e7b53-145">Used by data flow components to access the parent Data Flow task and other components in the data flow.</span></span> <span data-ttu-id="e7b53-146">Questa caratteristica può essere utilizzata per sviluppare un componente come la Creazione guidata dimensioni a modifica lenta, che crea e connette componenti del flusso di dati aggiuntivi se necessario.</span><span class="sxs-lookup"><span data-stu-id="e7b53-146">This feature could be used to develop a component like the Slowly Changing Dimension Wizard that creates and connects additional data flow components as needed.</span></span>|

 <span data-ttu-id="e7b53-147">Questi servizi offrono agli sviluppatori di componenti la possibilità di accedere e creare oggetti nel pacchetto in cui viene caricato il componente.</span><span class="sxs-lookup"><span data-stu-id="e7b53-147">These services provide component developers the ability to access and create objects in the package in which the component is loaded.</span></span>

## <a name="sample"></a><span data-ttu-id="e7b53-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7b53-148">Sample</span></span>
 <span data-ttu-id="e7b53-149">Nell'esempio di codice seguente è illustrata l'integrazione di una classe di interfaccia utente personalizzata che implementa l'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> e un Windows Form che funge da editor per un componente.</span><span class="sxs-lookup"><span data-stu-id="e7b53-149">The following code example shows the integration of a custom user interface class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface, and a Windows form that serves as the editor for a component.</span></span>

### <a name="custom-user-interface-class"></a><span data-ttu-id="e7b53-150">Classe dell'interfaccia utente personalizzata</span><span class="sxs-lookup"><span data-stu-id="e7b53-150">Custom User Interface Class</span></span>
 <span data-ttu-id="e7b53-151">Nell'esempio di codice seguente è illustrata la classe che implementa l'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>.</span><span class="sxs-lookup"><span data-stu-id="e7b53-151">The following code shows the class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface.</span></span> <span data-ttu-id="e7b53-152">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> crea l'editor del componente, quindi visualizza il form.</span><span class="sxs-lookup"><span data-stu-id="e7b53-152">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method creates the component editor and then displays the form.</span></span> <span data-ttu-id="e7b53-153">Il valore restituito del form determina se le modifiche apportate al componente sono persistenti.</span><span class="sxs-lookup"><span data-stu-id="e7b53-153">The return value of the form determines whether changes to the component are persisted.</span></span>

```csharp
using System;
using System.Windows.Forms;
using Microsoft.SqlServer.Dts.Runtime;
using Microsoft.SqlServer.Dts.Pipeline.Design;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
    public class SampleComponentUI : IDtsComponentUI
    {
        IDTSComponentMetaData100 md;
        IServiceProvider sp;

        public void Help(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public void New(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public void Delete(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public bool Edit(System.Windows.Forms.IWin32Window parentWindow, Variables vars, Connections cons)
        {
            // Create and display the form for the user interface.
            SampleComponentUIForm componentEditor = new SampleComponentUIForm(cons, vars, md);

            DialogResult result  = componentEditor.ShowDialog(parentWindow);

            if (result == DialogResult.OK)
                return true;

            return false;
        }
        public void Initialize(IDTSComponentMetaData100 dtsComponentMetadata, IServiceProvider serviceProvider)
        {
            // Store the component metadata.
            this.md = dtsComponentMetadata;
        }
    }
}
```

```vb
Imports System 
Imports System.Windows.Forms 
Imports Microsoft.SqlServer.Dts.Runtime 
Imports Microsoft.SqlServer.Dts.Pipeline.Design 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 

Namespace Microsoft.Samples.SqlServer.Dts 

 Public Class SampleComponentUI 
 Implements IDtsComponentUI 
   Private md As IDTSComponentMetaData100 
   Private sp As IServiceProvider 

   Public Sub Help(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Sub New(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Sub Delete(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Function Edit(ByVal parentWindow As System.Windows.Forms.IWin32Window, ByVal vars As Variables, ByVal cons As Connections) As Boolean 
     ' Create and display the form for the user interface.
     Dim componentEditor As SampleComponentUIForm = New SampleComponentUIForm(cons, vars, md) 
     Dim result As DialogResult = componentEditor.ShowDialog(parentWindow) 
     If result = DialogResult.OK Then 
       Return True 
     End If 
     Return False 
   End Function 

   Public Sub Initialize(ByVal dtsComponentMetadata As IDTSComponentMetaData100, ByVal serviceProvider As IServiceProvider) 
     Me.md = dtsComponentMetadata 
   End Sub 
 End Class 

End Namespace
```

### <a name="custom-editor"></a><span data-ttu-id="e7b53-154">Editor personalizzato</span><span class="sxs-lookup"><span data-stu-id="e7b53-154">Custom Editor</span></span>
 <span data-ttu-id="e7b53-155">Nel codice seguente è illustrata l'implementazione del Windows Form visualizzato durante la chiamata al metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7b53-155">The following code shows the implementation of the Windows form that is shown during the call to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method.</span></span>

```csharp
using System;
using System.Drawing;
using System.Collections;
using System.ComponentModel;
using System.Windows.Forms;
using System.Data;

using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    public partial class SampleComponentUIForm : System.Windows.Forms.Form
    {
        private Connections connections;
        private Variables variables;
        private IDTSComponentMetaData100 metaData;
        private CManagedComponentWrapper designTimeInstance;
        private System.ComponentModel.IContainer components = null;

        public SampleComponentUIForm( Connections cons, Variables vars, IDTSComponentMetaData100 md)
        {
            variables = vars;
            connections = cons;
            metaData = md;
        }

        private void btnOk_Click(object sender, System.EventArgs e)
        {
            if (designTimeInstance == null)
                designTimeInstance = metaData.Instantiate();

            designTimeInstance.SetComponentProperty( "CustomProperty", txtCustomPropertyValue.Text);

            this.Close();
        }

        private void btnCancel_Click(object sender, System.EventArgs e)
        {
            this.Close();
        }
    }
}
```

```vb
Imports System 
Imports System.Drawing 
Imports System.Collections 
Imports System.ComponentModel 
Imports System.Windows.Forms 
Imports System.Data 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Imports Microsoft.SqlServer.Dts.Runtime 

Namespace Microsoft.Samples.SqlServer.Dts 

 Public Partial Class SampleComponentUIForm 
  Inherits System.Windows.Forms.Form 
   Private connections As Connections 
   Private variables As Variables 
   Private metaData As IDTSComponentMetaData100 
   Private designTimeInstance As CManagedComponentWrapper 
   Private components As System.ComponentModel.IContainer = Nothing 

   Public Sub New(ByVal cons As Connections, ByVal vars As Variables, ByVal md As IDTSComponentMetaData100) 
     variables = vars 
     connections = cons 
     metaData = md 
   End Sub 

   Private Sub btnOk_Click(ByVal sender As Object, ByVal e As System.EventArgs) 
     If designTimeInstance Is Nothing Then 
       designTimeInstance = metaData.Instantiate 
     End If 
     designTimeInstance.SetComponentProperty("CustomProperty", txtCustomPropertyValue.Text) 
     Me.Close 
   End Sub 

   Private Sub btnCancel_Click(ByVal sender As Object, ByVal e As System.EventArgs) 
     Me.Close 
   End Sub 
 End Class 

End Namespace
```

<span data-ttu-id="e7b53-156">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e7b53-156">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e7b53-157">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="e7b53-157">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e7b53-158">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="e7b53-158">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e7b53-159">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e7b53-159">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7b53-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7b53-160">See Also</span></span>
 [<span data-ttu-id="e7b53-161">Creazione di un componente flusso di dati personalizzato</span><span class="sxs-lookup"><span data-stu-id="e7b53-161">Creating a Custom Data Flow Component</span></span>](creating-a-custom-data-flow-component.md)


