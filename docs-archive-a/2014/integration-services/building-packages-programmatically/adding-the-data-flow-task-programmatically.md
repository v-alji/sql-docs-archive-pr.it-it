---
title: Aggiunta dell'attività Flusso di dati a livello di programmazione | Microsoft Docs
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
- adding Data Flow task
- SSIS data flow
- data flow task [Integration Services], adding
- MainPipe object
ms.assetid: 0ca03712-a82e-4aa7-949b-f869a8936ddf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f7e699cc8e88bafb2a4508fdac8560fa73befe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627354"
---
# <a name="adding-the-data-flow-task-programmatically"></a><span data-ttu-id="e7c4d-102">Aggiunta dell'attività Flusso di dati a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="e7c4d-102">Adding the Data Flow Task Programmatically</span></span>
  <span data-ttu-id="e7c4d-103">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] è inclusa l'attività Flusso di dati, rappresentata dallo spazio dei nomi <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper> del modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-103">[!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] includes a task called the Data Flow task, which is represented by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper> namespace in the object model.</span></span> <span data-ttu-id="e7c4d-104">Flusso di dati è un'attività speciale, a elevate prestazioni, dedicata alla trasformazione e allo spostamento dei dati durante l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-104">The Data Flow task is a specialized, high-performance task, dedicated to transforming and moving data during package execution.</span></span> <span data-ttu-id="e7c4d-105">Analogamente ad altre attività, Flusso di dati è inclusa nell'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> e dal punto di vista del motore di run-time è solo un'altra attività del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-105">Like other tasks, the Data Flow task is wrapped by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object, and from the perspective of the run-time engine, this task is just another task in the package.</span></span> <span data-ttu-id="e7c4d-106">Tuttavia, il flusso di dati contiene oggetti aggiuntivi denominati componenti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-106">However, the data flow contains additional objects called data flow components.</span></span> <span data-ttu-id="e7c4d-107">Si tratta dei componenti che consentono lo spostamento dei dati da un'origine a una destinazione, a volte tramite una trasformazione.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-107">These components are the components that make data move from a source to a destination, sometimes through a transformation.</span></span> <span data-ttu-id="e7c4d-108">Tali componenti definiscono sia la direzione dello spostamento che la modalità di trasformazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-108">The components define both the direction of movement and how data is transformed.</span></span> <span data-ttu-id="e7c4d-109">La configurazione dell'attività Flusso di dati implica l'aggiunta di componenti e quindi la relativa connessione per stabilire il flusso dei dati e ottenere la trasformazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-109">Configuring the Data Flow task involves adding components to the task, and then connecting them to establish the flow of data and achieve the intended transformation.</span></span>  
  
 <span data-ttu-id="e7c4d-110">Un'attività Flusso di dati include tre tipi di componenti: **Origini flusso di dati**, **Trasformazioni flusso di dati** e **Destinazioni flusso di dati**, visualizzati in questo ordine nella casella degli strumenti di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7c4d-110">There are three types of components within a Data Flow task: **Data Flow Sources**, **Data Flow Transformations**, and **Data Flow Destinations**, shown in that order within the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer toolbox.</span></span> <span data-ttu-id="e7c4d-111">Questi tipi vengono anche definiti più semplicemente come origini, trasformazioni o destinazioni.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-111">These types are also referred to more simply as sources, transformations, or destinations.</span></span> <span data-ttu-id="e7c4d-112">Come implicano i nomi, i dati vengono spostati da un'origine a una trasformazione e quindi a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-112">As implied by the names, data flows from a source to a transformation, and then to a destination.</span></span> <span data-ttu-id="e7c4d-113">Si tratta di una descrizione semplicistica del flusso di dati per illustrare il concetto, ma l'attività Flusso di dati è sufficientemente flessibile e potente da gestire più origini e da connettere molte trasformazioni che inviano l'output a molte destinazioni.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-113">This is a simplistic description of the data flow to illustrate the concept, but the Data Flow task is flexible and powerful enough to handle multiple sources, and to connect together many transformations that send output to multiple destinations.</span></span>  
  
 <span data-ttu-id="e7c4d-114">L'attività Flusso di dati viene aggiunta in un pacchetto allo stesso modo delle altre attività.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-114">The Data Flow task is added to a package the same way other tasks are added.</span></span> <span data-ttu-id="e7c4d-115">Una volta aggiunta, l'attività viene configurata con l'aggiunta, la configurazione e la connessione dei relativi componenti.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-115">After the task has been added, it is configured by adding components to the data flow task, and configuring and connecting components in the task.</span></span>  
  
## <a name="sample"></a><span data-ttu-id="e7c4d-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7c4d-116">Sample</span></span>  
 <span data-ttu-id="e7c4d-117">Nell'esempio di codice seguente viene illustrato come aggiungere un'attività Flusso di dati in un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-117">The following code sample shows how to add a Data Flow task to a package.</span></span> <span data-ttu-id="e7c4d-118">L'esempio richiede un riferimento agli assembly Microsoft.SqlServer.PipelineHost, Microsoft.SqlServer.DTSPipelineWrap e Microsoft.SqlServer.ManagedDTS.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-118">This example requires a reference to the assemblies Microsoft.SqlServer.PipelineHost, Microsoft.SqlServer.DTSPipelineWrap, and Microsoft.SqlServer.ManagedDTS.</span></span>  
  
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
      Package p = new Package();  
      Executable e = p.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;   
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim e As Executable = p.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As TaskHost = CType(e, TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="e7c4d-119">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="e7c4d-119">External Resources</span></span>  
 <span data-ttu-id="e7c4d-120">Intervento nel blog sull'[aggiornamento di EzAPI per SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223) sul sito Web blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-120">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="e7c4d-121">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e7c4d-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e7c4d-122">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="e7c4d-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e7c4d-123">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="e7c4d-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e7c4d-124">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e7c4d-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7c4d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7c4d-125">See Also</span></span>  
 [<span data-ttu-id="e7c4d-126">Individuazione dei componenti del flusso di dati a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="e7c4d-126">Discovering Data Flow Components Programmatically</span></span>](../building-packages-programmatically/discovering-data-flow-components-programmatically.md)  
  
  
