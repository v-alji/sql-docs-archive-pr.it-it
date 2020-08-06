---
title: Creazione di un componente flusso di dati personalizzato | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- design-time component interface [Integration Services]
- custom data flow components [Integration Services], about data flow components
- custom data flow components [Integration Services]
- data flow components [Integration Services]
- data flow components [Integration Services], developing
ms.assetid: 9d96bcf5-eba8-44bd-b113-ed51ad0d0521
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 110d07ff88707ad1a01f299b6f532df99ce58404
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629935"
---
# <a name="creating-a-custom-data-flow-component"></a><span data-ttu-id="e95af-102">Creazione di un componente flusso di dati personalizzato</span><span class="sxs-lookup"><span data-stu-id="e95af-102">Creating a Custom Data Flow Component</span></span>
  <span data-ttu-id="e95af-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] l'attività Flusso di dati espone un modello a oggetti che consente agli sviluppatori di creare componenti flusso di dati personalizzati, ovvero origini, trasformazioni e destinazioni, usando [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] e codice gestito.</span><span class="sxs-lookup"><span data-stu-id="e95af-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], the data flow task exposes an object model that lets developers create custom data flow components-sources, transformations, and destinations-by using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] and managed code.</span></span>  
  
 <span data-ttu-id="e95af-104">Un'attività Flusso di dati è costituita da componenti che contengono un'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> e una raccolta di oggetti <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> che definiscono lo spostamento di dati tra componenti.</span><span class="sxs-lookup"><span data-stu-id="e95af-104">A data flow task consists of components that contain an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface and a collection of <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> objects that define the movement of data between components.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e95af-105">Quando si crea un provider personalizzato, è necessario aggiornare il file ProviderDescriptors.xml con i valori delle colonne di metadati.</span><span class="sxs-lookup"><span data-stu-id="e95af-105">When you create a custom provider, you need to update the ProviderDescriptors.xml file with the metadata column values.</span></span>  
  
## <a name="design-time-and-run-time"></a><span data-ttu-id="e95af-106">Fase di progettazione e di esecuzione</span><span class="sxs-lookup"><span data-stu-id="e95af-106">Design Time and Run Time</span></span>  
 <span data-ttu-id="e95af-107">Prima dell'esecuzione, l'attività Flusso di dati si trova nel cosiddetto stato della fase di progettazione, quando viene sottoposta a modifiche incrementali.</span><span class="sxs-lookup"><span data-stu-id="e95af-107">Before execution, the data flow task is said to be in a design-time state, as it undergoes incremental changes.</span></span> <span data-ttu-id="e95af-108">Tali modifiche possono includere l'aggiunta o la rimozione di componenti, l'aggiunta o la rimozione degli oggetti percorso che connettono i componenti e modifiche ai metadati dei componenti.</span><span class="sxs-lookup"><span data-stu-id="e95af-108">Changes may include the addition or removal of components, the addition or removal of the path objects that connect components, and changes to the metadata of the components.</span></span> <span data-ttu-id="e95af-109">Quando si verificano modifiche ai metadati, il componente può monitorarle e rispondere.</span><span class="sxs-lookup"><span data-stu-id="e95af-109">When metadata changes occur, the component can monitor and react to the changes.</span></span> <span data-ttu-id="e95af-110">Ad esempio, un componente può impedire determinate modifiche o aggiungerne altre in risposta a una modifica.</span><span class="sxs-lookup"><span data-stu-id="e95af-110">For example, a component can disallow certain changes or to make additional changes in response to a change.</span></span> <span data-ttu-id="e95af-111">In fase di progettazione la finestra di progettazione interagisce con un componente tramite l'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> della fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e95af-111">At design time, the designer interacts with a component through the design-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>  
  
 <span data-ttu-id="e95af-112">In fase di esecuzione l'attività Flusso di dati esamina la sequenza di componenti, prepara un piano di esecuzione e gestisce un pool di thread di lavoro che eseguono il piano di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e95af-112">At execution time, the data flow task examines the sequence of components, prepares an execution plan, and manages a pool of worker threads that execute the work plan.</span></span> <span data-ttu-id="e95af-113">Anche se ogni thread di lavoro esegue alcune operazioni interne all'attività Flusso di dati, la principale attività di questo thread è chiamare i metodi del componente tramite l'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> di runtime.</span><span class="sxs-lookup"><span data-stu-id="e95af-113">Although each worker thread performs some work that is internal to the data flow task, the principal task of the worker thread is to call the methods of the component through the run-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> interface.</span></span>  
  
## <a name="creating-a-component"></a><span data-ttu-id="e95af-114">Creazione di un componente</span><span class="sxs-lookup"><span data-stu-id="e95af-114">Creating a Component</span></span>  
 <span data-ttu-id="e95af-115">Per creare un componente flusso di dati, derivare una classe dalla classe di base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>, applicare la classe <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>, quindi eseguire l'override dei metodi appropriati della classe di base.</span><span class="sxs-lookup"><span data-stu-id="e95af-115">To create a data flow component, you derive a class from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class, apply the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> class, and then override the appropriate methods of the base class.</span></span> <span data-ttu-id="e95af-116">L'oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> implementa le interfacce <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> ed espone i relativi metodi da sottoporre a override nel componente.</span><span class="sxs-lookup"><span data-stu-id="e95af-116">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> interfaces, and exposes their methods for you to override in your component.</span></span>  
  
 <span data-ttu-id="e95af-117">A seconda degli oggetti utilizzati dal componente, il progetto richiederà riferimenti ad alcuni o a tutti gli assembly seguenti:</span><span class="sxs-lookup"><span data-stu-id="e95af-117">Depending on the objects used by your component, your project will require references to some or all of the following assemblies:</span></span>  
  
|<span data-ttu-id="e95af-118">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="e95af-118">Feature</span></span>|<span data-ttu-id="e95af-119">Assembly a cui fare riferimento</span><span class="sxs-lookup"><span data-stu-id="e95af-119">Assembly to reference</span></span>|<span data-ttu-id="e95af-120">Spazio dei nomi da importare</span><span class="sxs-lookup"><span data-stu-id="e95af-120">Namespace to import</span></span>|  
|-------------|---------------------------|-------------------------|  
|<span data-ttu-id="e95af-121">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="e95af-121">Data flow</span></span>|<span data-ttu-id="e95af-122">Microsoft.SqlServer.PipelineHost</span><span class="sxs-lookup"><span data-stu-id="e95af-122">Microsoft.SqlServer.PipelineHost</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline>|  
|<span data-ttu-id="e95af-123">Wrapper del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="e95af-123">Data flow wrapper</span></span>|<span data-ttu-id="e95af-124">Microsoft.SqlServer.DTSPipelineWrap</span><span class="sxs-lookup"><span data-stu-id="e95af-124">Microsoft.SqlServer.DTSPipelineWrap</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>|  
|<span data-ttu-id="e95af-125">Runtime</span><span class="sxs-lookup"><span data-stu-id="e95af-125">Runtime</span></span>|<span data-ttu-id="e95af-126">Microsoft.SQLServer.ManagedDTS</span><span class="sxs-lookup"><span data-stu-id="e95af-126">Microsoft.SQLServer.ManagedDTS</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime>|  
|<span data-ttu-id="e95af-127">Wrapper del runtime</span><span class="sxs-lookup"><span data-stu-id="e95af-127">Runtime wrapper</span></span>|<span data-ttu-id="e95af-128">Microsoft.SqlServer.DTSRuntimeWrap</span><span class="sxs-lookup"><span data-stu-id="e95af-128">Microsoft.SqlServer.DTSRuntimeWrap</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Wrapper>|  
  
 <span data-ttu-id="e95af-129">Nell'esempio di codice seguente è illustrato un componente semplice che deriva dalla classe di base e applica <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e95af-129">The following code example shows a simple component that derives from the base class, and applies the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span></span> <span data-ttu-id="e95af-130">È necessario aggiungere un riferimento all'assembly DTSPipelineWrap.</span><span class="sxs-lookup"><span data-stu-id="e95af-130">You need to add a reference to the DTSPipelineWrap assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsPipelineComponent(DisplayName = "SampleComponent", ComponentType = ComponentType.Transform )]  
    public class BasicComponent: PipelineComponent  
    {  
        // TODO: Override the base class methods.  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
<DtsPipelineComponent(DisplayName:="SampleComponent", ComponentType:=ComponentType.Transform)> _  
Public Class BasicComponent  
  
    Inherits PipelineComponent  
  
    ' TODO: Override the base class methods.  
  
End Class  
```  
  
<span data-ttu-id="e95af-131">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e95af-131">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e95af-132">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="e95af-132">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e95af-133">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="e95af-133">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e95af-134">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e95af-134">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e95af-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e95af-135">See Also</span></span>  
 [<span data-ttu-id="e95af-136">Sviluppo di un'interfaccia utente per un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="e95af-136">Developing a User Interface for a Data Flow Component</span></span>](developing-a-user-interface-for-a-data-flow-component.md)  
  
  
