---
title: Sviluppo di tipi specifici di componenti del flusso di dati | Microsoft Docs
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
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: 348e219a-b8ff-425e-b9c6-811880101c54
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e168c866e03bfa5fd1f32127e4bfd6e58a2e8d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721631"
---
# <a name="developing-specific-types-of-data-flow-components"></a><span data-ttu-id="2d082-102">Sviluppo di tipi specifici di componenti del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="2d082-102">Developing Specific Types of Data Flow Components</span></span>
  <span data-ttu-id="2d082-103">In questa sezione vengono descritte le specifiche dello sviluppo di componenti di origine, componenti di trasformazione con output sincroni, componenti di trasformazione con output asincroni e componenti di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2d082-103">This section covers the specifics of developing source components, transformation components with synchronous outputs, transformation components with asynchronous outputs, and destination components.</span></span>  
  
 <span data-ttu-id="2d082-104">Per informazioni sullo sviluppo di componenti flusso dati in generale, vedere [Sviluppo di un componente flusso di dati personalizzato](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="2d082-104">For information about component development in general, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d082-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2d082-105">In This Section</span></span>  
 [<span data-ttu-id="2d082-106">Sviluppo di un componente di origine personalizzato</span><span class="sxs-lookup"><span data-stu-id="2d082-106">Developing a Custom Source Component</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)  
 <span data-ttu-id="2d082-107">Contiene informazioni sullo sviluppo di un componente che accede ai dati da un'origine dati esterna e li fornisce ai componenti a valle nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="2d082-107">Contains information on developing a component that accesses data from an external data source and supplies it to downstream components in the data flow.</span></span>  
  
 [<span data-ttu-id="2d082-108">Sviluppo di un componente di trasformazione personalizzato con output sincroni</span><span class="sxs-lookup"><span data-stu-id="2d082-108">Developing a Custom Transformation Component with Synchronous Outputs</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md)  
 <span data-ttu-id="2d082-109">Contiene informazioni sullo sviluppo di un componente di trasformazione i cui output sono sincroni con gli input.</span><span class="sxs-lookup"><span data-stu-id="2d082-109">Contains information on developing a transformation component whose outputs are synchronous to its inputs.</span></span> <span data-ttu-id="2d082-110">Questi componenti non aggiungono dati al flusso di dati, ma li elaborano mentre passano.</span><span class="sxs-lookup"><span data-stu-id="2d082-110">These components do not add data to the data flow, but process data as it passes through.</span></span>  
  
 [<span data-ttu-id="2d082-111">Sviluppo di un componente di trasformazione personalizzato con output asincroni</span><span class="sxs-lookup"><span data-stu-id="2d082-111">Developing a Custom Transformation Component with Asynchronous Outputs</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md)  
 <span data-ttu-id="2d082-112">Contiene informazioni sullo sviluppo di un componente di trasformazione i cui output non sono sincroni con gli input.</span><span class="sxs-lookup"><span data-stu-id="2d082-112">Contains information on developing a transformation component whose outputs are not synchronous to its inputs.</span></span> <span data-ttu-id="2d082-113">Questi componenti ricevono dati dai componenti a monte, ma aggiungono anche dati al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="2d082-113">These components receive data from upstream components, but also add data to the dataflow.</span></span>  
  
 [<span data-ttu-id="2d082-114">Sviluppo di un componente di destinazione personalizzato</span><span class="sxs-lookup"><span data-stu-id="2d082-114">Developing a Custom Destination Component</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)  
 <span data-ttu-id="2d082-115">Contiene informazioni sullo sviluppo di un componente che riceve righe dai componenti a monte nel flusso di dati e li scrive in un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="2d082-115">Contains information on developing a component that receives rows from upstream components in the data flow and writes them to an external data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2d082-116">Riferimento</span><span class="sxs-lookup"><span data-stu-id="2d082-116">Reference</span></span>  
 <xref:Microsoft.SqlServer.Dts.Pipeline>  
 <span data-ttu-id="2d082-117">Contiene le classi e le interfacce utilizzate per creare componenti del flusso di dati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2d082-117">Contains the classes and interfaces used to create custom data flow components.</span></span>  
  
 <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>  
 <span data-ttu-id="2d082-118">Contiene le classi e le interfacce non gestite dell'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="2d082-118">Contains the unmanaged classes and interfaces of the data flow task.</span></span> <span data-ttu-id="2d082-119">Lo sviluppatore utilizza questi oggetti e lo spazio dei nomi <xref:Microsoft.SqlServer.Dts.Pipeline> gestito quando compila un flusso di dati a livello di programmazione o crea componenti del flusso di dati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2d082-119">The developer uses these, and the managed <xref:Microsoft.SqlServer.Dts.Pipeline> namespace, when building a data flow programmatically or creating custom data flow components.</span></span>  
  
<span data-ttu-id="2d082-120">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2d082-120">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2d082-121">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="2d082-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2d082-122">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="2d082-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2d082-123">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="2d082-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d082-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d082-124">See Also</span></span>  
 <span data-ttu-id="2d082-125">[Confronto tra soluzioni di scripting e oggetti personalizzati](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="2d082-125">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="2d082-126">Sviluppo di tipi specifici di componenti script</span><span class="sxs-lookup"><span data-stu-id="2d082-126">Developing Specific Types of Script Components</span></span>](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md)  
  
  
