---
title: Individuazione dei componenti del flusso di dati a livello di programmazione | Microsoft Docs
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
- PipelineComponentInfos collection
- data flow task [Integration Services], components
- discovering data flow components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: ff92a96a-8af6-4532-82cc-c0bbff92401b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a18102f38f1ad06e918efe2ca529185d40deef9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715652"
---
# <a name="discovering-data-flow-components-programmatically"></a><span data-ttu-id="6c1a4-102">Individuazione dei componenti del flusso di dati a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="6c1a4-102">Discovering Data Flow Components Programmatically</span></span>
  <span data-ttu-id="6c1a4-103">Dopo avere aggiunto un'attività Flusso di dati a un pacchetto, il passaggio successivo consiste nel determinare quali componenti flusso di dati sono disponibili per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="6c1a4-103">After you have added a data flow task to a package, your next step may be to determine what data flow components are available for your use.</span></span> <span data-ttu-id="6c1a4-104">È possibile individuare a livello di programmazione le origini, le trasformazioni e le destinazioni del flusso di dati installate e disponibili nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="6c1a4-104">You can programmatically discover the data flow sources, transformations, and destinations that are installed and available on the local computer.</span></span> <span data-ttu-id="6c1a4-105">Per altre informazioni sull'aggiunta di un'attività Flusso di dati al pacchetto, vedere [Aggiunta dell'attività Flusso di dati a livello di programmazione](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="6c1a4-105">For information about adding a data flow task to the package, see [Adding the Data Flow Task Programmatically](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md).</span></span>  
  
## <a name="discovering-components"></a><span data-ttu-id="6c1a4-106">Individuazione di componenti</span><span class="sxs-lookup"><span data-stu-id="6c1a4-106">Discovering Components</span></span>  
 <span data-ttu-id="6c1a4-107">La classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> fornisce la raccolta <xref:Microsoft.SqlServer.Dts.Runtime.Application.PipelineComponentInfos%2A>, che contiene un oggetto <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> per ogni componente installato correttamente nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="6c1a4-107">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class provides the <xref:Microsoft.SqlServer.Dts.Runtime.Application.PipelineComponentInfos%2A> collection, which contains a <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> object for each component correctly installed on the local computer.</span></span> <span data-ttu-id="6c1a4-108">Ogni oggetto <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> contiene informazioni su un componente, ad esempio il nome, la descrizione e il nome di creazione.</span><span class="sxs-lookup"><span data-stu-id="6c1a4-108">Each <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> contains information about a component such as its name, description, and creation name.</span></span> <span data-ttu-id="6c1a4-109">È possibile utilizzare il valore restituito nella proprietà <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> per impostare la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> di <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> quando si aggiunge un componente a un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6c1a4-109">You can use the value returned in the <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> property to set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> when you add a component to a package.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="6c1a4-110">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6c1a4-110">Next Step</span></span>  
 <span data-ttu-id="6c1a4-111">Dopo aver individuato i componenti disponibili, il passaggio successivo consiste nell'aggiunta e nella configurazione dei componenti, come descritto nell'argomento seguente, [Aggiunta di componenti del flusso di dati a livello di programmazione](../building-packages-programmatically/adding-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="6c1a4-111">After discovering available components, the next step is to add and configure the components, which is discussed in the next topic, [Adding Data Flow Components Programmatically](../building-packages-programmatically/adding-data-flow-components-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="6c1a4-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c1a4-112">Sample</span></span>  
 <span data-ttu-id="6c1a4-113">Nell'esempio di codice seguente è illustrato come enumerare la raccolta <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfos> dell'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.Application> per individuare a livello di programmazione i componenti del flusso di dati disponibili nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="6c1a4-113">The following code sample shows how to enumerate the <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfos> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> object to programmatically discover the data flow components available on the local computer.</span></span> <span data-ttu-id="6c1a4-114">Questo esempio richiede un riferimento all'assembly Microsoft.SqlServer.ManagedDTS.</span><span class="sxs-lookup"><span data-stu-id="6c1a4-114">This sample requires a reference to the Microsoft.SqlServer.ManagedDTS assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Application application = new Application();  
      PipelineComponentInfos componentInfos = application.PipelineComponentInfos;  
  
      foreach (PipelineComponentInfo componentInfo in componentInfos)  
      {  
        Console.WriteLine("Name: " + componentInfo.Name + "\n" +  
          " CreationName: " + componentInfo.CreationName + "\n");  
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
  
    Dim application As Application = New Application()  
  
    Dim componentInfos As PipelineComponentInfos = application.PipelineComponentInfos  
  
    For Each componentInfo As PipelineComponentInfo In componentInfos  
      Console.WriteLine("Name: " & componentInfo.Name & vbCrLf & _  
        " CreationName: " & componentInfo.CreationName & vbCrLf)  
    Next  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="6c1a4-115">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="6c1a4-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6c1a4-116">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="6c1a4-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6c1a4-117">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="6c1a4-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6c1a4-118">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="6c1a4-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c1a4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c1a4-119">See Also</span></span>  
 [<span data-ttu-id="6c1a4-120">Aggiunta di componenti del flusso di dati a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="6c1a4-120">Adding Data Flow Components Programmatically</span></span>](../building-packages-programmatically/adding-data-flow-components-programmatically.md)  
  
  
