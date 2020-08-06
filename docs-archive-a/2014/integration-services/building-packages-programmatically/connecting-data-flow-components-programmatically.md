---
title: Connessione dei componenti del flusso di dati a livello di programmazione | Microsoft Docs
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
- data flow task [Integration Services], components
- paths [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: 404ecab7-7698-447b-93d6-dd256beb11ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39494fee5314f309b79abfd30303fdd607fd3c50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627350"
---
# <a name="connecting-data-flow-components-programmatically"></a><span data-ttu-id="0f034-102">Connessione dei componenti del flusso di dati a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="0f034-102">Connecting Data Flow Components Programmatically</span></span>
  <span data-ttu-id="0f034-103">Dopo avere aggiunto componenti all'attività Flusso di dati, connetterli per creare un albero di esecuzione che rappresenti il flusso di dati dalle origini attraverso le trasformazioni alle destinazioni.</span><span class="sxs-lookup"><span data-stu-id="0f034-103">After you have added components to the data flow task, you connect them to create an execution tree that represents the flow of data from sources through transformations to destinations.</span></span> <span data-ttu-id="0f034-104">Utilizzare oggetti <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> per connettere i componenti nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="0f034-104">You use <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> objects to connect the components in the data flow.</span></span>  
  
## <a name="creating-a-path"></a><span data-ttu-id="0f034-105">Creazione di un percorso</span><span class="sxs-lookup"><span data-stu-id="0f034-105">Creating a Path</span></span>  
 <span data-ttu-id="0f034-106">Chiamare il metodo New della proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.PathCollection%2A> dell'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipe> per creare un nuovo percorso e aggiungerlo alla raccolta di percorsi nell'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="0f034-106">Call the New method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.PathCollection%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipe> interface to create a new path and add it to the collection of paths in the data flow task.</span></span> <span data-ttu-id="0f034-107">Questo metodo restituisce un nuovo oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> disconnesso, che verrà quindi utilizzato per connettere due componenti.</span><span class="sxs-lookup"><span data-stu-id="0f034-107">This method returns a new, disconnected <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object, which you then use to connect two components.</span></span>  
  
 <span data-ttu-id="0f034-108">Chiamare il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100.AttachPathAndPropagateNotifications%2A> per connettere il percorso e notificare ai componenti partecipanti nel percorso che sono stati connessi.</span><span class="sxs-lookup"><span data-stu-id="0f034-108">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100.AttachPathAndPropagateNotifications%2A> method to connect the path and to notify the components participating in the path that they have been connected.</span></span> <span data-ttu-id="0f034-109">Questo metodo accetta <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> del componente a monte e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> del componente a valle come parametri.</span><span class="sxs-lookup"><span data-stu-id="0f034-109">This method accepts an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the upstream component and an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> of the downstream component as parameters.</span></span> <span data-ttu-id="0f034-110">Per impostazione predefinita, la chiamata al metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> del componente crea un singolo input per i componenti che includono input e un singolo output per i componenti che includono output.</span><span class="sxs-lookup"><span data-stu-id="0f034-110">By default, the call to the component's <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method creates a single input for components that have inputs, and a single output for components that have outputs.</span></span> <span data-ttu-id="0f034-111">Nell'esempio seguente vengono utilizzati l'output predefinito dell'origine e l'input predefinito della destinazione.</span><span class="sxs-lookup"><span data-stu-id="0f034-111">The following example uses this default output of the source and input of the destination.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="0f034-112">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="0f034-112">Next Step</span></span>  
 <span data-ttu-id="0f034-113">Dopo aver stabilito un percorso tra due componenti, il passaggio successivo consiste nell'eseguire il mapping delle colonne di input nel componente a valle, descritto nell'argomento successivo [Selezione delle colonne di input a livello di programmazione](../building-packages-programmatically/selecting-input-columns-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="0f034-113">After you establish a path between two components, the next step is to map input columns in the downstream component, which is discussed in the next topic, [Selecting Input Columns Programmatically](../building-packages-programmatically/selecting-input-columns-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="0f034-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f034-114">Sample</span></span>  
 <span data-ttu-id="0f034-115">Nell'esempio di codice seguente è illustrato come stabilire un percorso tra due componenti.</span><span class="sxs-lookup"><span data-stu-id="0f034-115">The following code sample shows how to establish a path between two components.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package = new Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;  
  
      // Create the source component.    
      IDTSComponentMetaData100 source =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      source.ComponentClassID = "DTSAdapter.OleDbSource";  
      CManagedComponentWrapper srcDesignTime = source.Instantiate();  
      srcDesignTime.ProvideComponentProperties();  
  
      // Create the destination component.  
      IDTSComponentMetaData100 destination =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      destination.ComponentClassID = "DTSAdapter.OleDbDestination";  
      CManagedComponentWrapper destDesignTime = destination.Instantiate();  
      destDesignTime.ProvideComponentProperties();  
  
      // Create the path.  
      IDTSPath100 path = dataFlowTask.PathCollection.New();  
      path.AttachPathAndPropagateNotifications(source.OutputCollection[0],  
        destination.InputCollection[0]);  
    }  
  }  
```  
  
 <span data-ttu-id="0f034-116">}</span><span class="sxs-lookup"><span data-stu-id="0f034-116">}</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' Create the source component.    
    Dim source As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    source.ComponentClassID = "DTSAdapter.OleDbSource"  
    Dim srcDesignTime As CManagedComponentWrapper = source.Instantiate()  
    srcDesignTime.ProvideComponentProperties()  
  
    ' Create the destination component.  
    Dim destination As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    destination.ComponentClassID = "DTSAdapter.OleDbDestination"  
    Dim destDesignTime As CManagedComponentWrapper = destination.Instantiate()  
    destDesignTime.ProvideComponentProperties()  
  
    ' Create the path.  
    Dim path As IDTSPath100 = dataFlowTask.PathCollection.New()  
    path.AttachPathAndPropagateNotifications(source.OutputCollection(0), _  
      destination.InputCollection(0))  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="0f034-117">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="0f034-117">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="0f034-118">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="0f034-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="0f034-119">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="0f034-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="0f034-120">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="0f034-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f034-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f034-121">See Also</span></span>  
 [<span data-ttu-id="0f034-122">Selezione delle colonne di input a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="0f034-122">Selecting Input Columns Programmatically</span></span>](../building-packages-programmatically/selecting-input-columns-programmatically.md)  
  
  
