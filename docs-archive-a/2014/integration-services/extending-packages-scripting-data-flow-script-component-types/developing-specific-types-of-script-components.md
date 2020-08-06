---
title: Sviluppo di tipi specifici di componenti script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], examples
ms.assetid: dfbbe959-6b4e-4b47-b9dd-bcc31929482d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 114c9ddca90ea02a8e1847444b28b9d5876650a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629481"
---
# <a name="developing-specific-types-of-script-components"></a><span data-ttu-id="f1d9c-102">Sviluppo di tipi specifici di componenti script</span><span class="sxs-lookup"><span data-stu-id="f1d9c-102">Developing Specific Types of Script Components</span></span>
  <span data-ttu-id="f1d9c-103">Il componente script è uno strumento configurabile che è possibile utilizzare nel flusso di dati di un pacchetto per rispondere ai requisiti non soddisfatti dalle origini, dalle trasformazioni e dalle destinazioni incluse in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1d9c-103">The Script component is a configurable tool that you can use in the data flow of a package to fill almost any requirement that is not met by the sources, transformations, and destinations that are included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="f1d9c-104">Questa sezione contiene esempi di codice del componente script che dimostrano le quattro opzioni disponibili per la configurazione di questo componente.</span><span class="sxs-lookup"><span data-stu-id="f1d9c-104">This section contains Script component code samples that demonstrate the four options for configuring the Script component:</span></span>  
  
-   <span data-ttu-id="f1d9c-105">Come origine.</span><span class="sxs-lookup"><span data-stu-id="f1d9c-105">As a source.</span></span>  
  
-   <span data-ttu-id="f1d9c-106">Come trasformazione con output sincroni.</span><span class="sxs-lookup"><span data-stu-id="f1d9c-106">As a transformation with synchronous outputs.</span></span>  
  
-   <span data-ttu-id="f1d9c-107">Come trasformazione con output asincroni.</span><span class="sxs-lookup"><span data-stu-id="f1d9c-107">As a transformation with asynchronous outputs.</span></span>  
  
-   <span data-ttu-id="f1d9c-108">Come destinazione.</span><span class="sxs-lookup"><span data-stu-id="f1d9c-108">As a destination.</span></span>  
  
 <span data-ttu-id="f1d9c-109">Per altri esempi del componente script, vedere [Ulteriori esempi di componente script](../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="f1d9c-109">For additional examples of the Script component, see [Additional Script Component Examples](../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1d9c-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f1d9c-110">In This Section</span></span>  
 [<span data-ttu-id="f1d9c-111">Creazione di un'origine con il componente script</span><span class="sxs-lookup"><span data-stu-id="f1d9c-111">Creating a Source with the Script Component</span></span>](creating-a-source-with-the-script-component.md)  
 <span data-ttu-id="f1d9c-112">Viene descritto e illustrato come creare un'origine del flusso di dati tramite il componente script.</span><span class="sxs-lookup"><span data-stu-id="f1d9c-112">Explains and demonstrates how to create a data flow source by using the Script component.</span></span>  
  
 [<span data-ttu-id="f1d9c-113">Creazione di una trasformazione sincrona con il componente script</span><span class="sxs-lookup"><span data-stu-id="f1d9c-113">Creating a Synchronous Transformation with the Script Component</span></span>](creating-a-synchronous-transformation-with-the-script-component.md)  
 <span data-ttu-id="f1d9c-114">Viene descritto e illustrato come creare una trasformazione del flusso di dati con output sincroni tramite il componente script.</span><span class="sxs-lookup"><span data-stu-id="f1d9c-114">Explains and demonstrates how to create a data flow transformation with synchronous outputs by using the Script component.</span></span> <span data-ttu-id="f1d9c-115">Questo tipo di trasformazione modifica righe di dati sul posto non appena attraversano il componente.</span><span class="sxs-lookup"><span data-stu-id="f1d9c-115">This kind of transformation modifies rows of data in place as they pass through the component.</span></span>  
  
 [<span data-ttu-id="f1d9c-116">Creazione di una trasformazione asincrona con il componente script</span><span class="sxs-lookup"><span data-stu-id="f1d9c-116">Creating an Asynchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)  
 <span data-ttu-id="f1d9c-117">Viene descritto e illustrato come creare una trasformazione del flusso di dati con output asincroni tramite il componente script.</span><span class="sxs-lookup"><span data-stu-id="f1d9c-117">Explains and demonstrates how to create a data flow transformation with asynchronous outputs by using the Script component.</span></span> <span data-ttu-id="f1d9c-118">Questo tipo di trasformazione deve leggere tutte le righe di dati prima di poter aggiungere ulteriori informazioni, ad esempio aggregazioni calcolate, ai dati che attraversano il componente.</span><span class="sxs-lookup"><span data-stu-id="f1d9c-118">This kind of transformation has to read all rows of data before it can add more information, such as calculated aggregates, to the data that passes through the component.</span></span>  
  
 [<span data-ttu-id="f1d9c-119">Creazione di una destinazione con il componente script</span><span class="sxs-lookup"><span data-stu-id="f1d9c-119">Creating a Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)  
 <span data-ttu-id="f1d9c-120">Viene descritto e illustrato come creare una destinazione del flusso di dati tramite il componente script.</span><span class="sxs-lookup"><span data-stu-id="f1d9c-120">Explains and demonstrates how to create a data flow destination by using the Script component.</span></span>  
  
<span data-ttu-id="f1d9c-121">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f1d9c-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f1d9c-122">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="f1d9c-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f1d9c-123">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="f1d9c-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f1d9c-124">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="f1d9c-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d9c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1d9c-125">See Also</span></span>  
 <span data-ttu-id="f1d9c-126">[Confronto tra soluzioni di scripting e oggetti personalizzati](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="f1d9c-126">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="f1d9c-127">Sviluppo di tipi specifici di componenti del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="f1d9c-127">Developing Specific Types of Data Flow Components</span></span>](../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md)  
  
  
