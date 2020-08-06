---
title: Trasformare dati con le trasformazioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data flow [Integration Services], transformations
- transformations [Integration Services], about transformations
- transforming data [Integration Services]
ms.assetid: e1340b6f-ef75-4b14-af6f-823586eff0ed
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 952d8ea4eeea2dd8010a17a2b3deba41447b6231
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637442"
---
# <a name="transform-data-with-transformations"></a><span data-ttu-id="c7ba6-102">Trasformazione di dati con le trasformazioni</span><span class="sxs-lookup"><span data-stu-id="c7ba6-102">Transform Data with Transformations</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="c7ba6-103">sono disponibili tre tipi di componenti flusso di dati: origini, trasformazioni e destinazioni.</span><span class="sxs-lookup"><span data-stu-id="c7ba6-103">includes three types of data flow components: sources, transformations, and destinations.</span></span>  
  
 <span data-ttu-id="c7ba6-104">Nella figura seguente viene illustrato un semplice flusso di dati con un'origine, due trasformazioni e una destinazione.</span><span class="sxs-lookup"><span data-stu-id="c7ba6-104">The following diagram shows a simple data flow that has a source, two transformations, and a destination.</span></span>  
  
 <span data-ttu-id="c7ba6-105">![Flusso di dati](../../media/mw-dts-08.gif "Flusso di dati")</span><span class="sxs-lookup"><span data-stu-id="c7ba6-105">![Data flow](../../media/mw-dts-08.gif "Data flow")</span></span>  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="c7ba6-106">Le trasformazioni offrono le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7ba6-106">transformations provide the following functionality:</span></span>  
  
-   <span data-ttu-id="c7ba6-107">Divisione, copia e unione dei set di righe ed esecuzione di operazioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c7ba6-107">Splitting, copying, and merging rowsets and performing lookup operations.</span></span>  
  
-   <span data-ttu-id="c7ba6-108">Aggiornamento dei valori delle colonne e creazione di nuove colonne tramite l'applicazione di trasformazioni, quale quella per la conversione dei caratteri da minuscolo a maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="c7ba6-108">Updating column values and creating new columns by applying transformations such as changing lowercase to uppercase.</span></span>  
  
-   <span data-ttu-id="c7ba6-109">Esecuzione di operazioni di Business Intelligence quali la pulitura dei dati, il text mining e l'esecuzione di query di stima basate su algoritmi di data mining.</span><span class="sxs-lookup"><span data-stu-id="c7ba6-109">Performing business intelligence operations such as cleaning data, mining text, or running data mining prediction queries.</span></span>  
  
-   <span data-ttu-id="c7ba6-110">Creazione di nuovi set di righe costituiti da valori ordinati o di aggregazione, dati campione o trasformati tramite Pivot o UnPivot.</span><span class="sxs-lookup"><span data-stu-id="c7ba6-110">Creating new rowsets that consist of aggregate or sorted values, sample data, or pivoted and unpivoted data.</span></span>  
  
-   <span data-ttu-id="c7ba6-111">Esecuzione di attività quali quelle per l'esportazione e l'importazione di dati, la generazione di informazioni di controllo e l'utilizzo di dimensioni a modifica lenta.</span><span class="sxs-lookup"><span data-stu-id="c7ba6-111">Performing tasks such as exporting and importing data, providing audit information, and working with slowly changing dimensions.</span></span>  
  
 <span data-ttu-id="c7ba6-112">Per altre informazioni, vedere [Trasformazioni di Integration Services](integration-services-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="c7ba6-112">For more information, see [Integration Services Transformations](integration-services-transformations.md).</span></span>  
  
 <span data-ttu-id="c7ba6-113">È inoltre possibile creare trasformazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="c7ba6-113">You can also write custom transformations.</span></span> <span data-ttu-id="c7ba6-114">Per altre informazioni, vedere [Sviluppo di un componente del flusso di dati personalizzato](../../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) e [Sviluppo di tipi specifici di componenti del flusso di dati](../../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md).</span><span class="sxs-lookup"><span data-stu-id="c7ba6-114">For more information, see [Developing a Custom Data Flow Component](../../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) and [Developing Specific Types of Data Flow Components](../../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md).</span></span>  
  
 <span data-ttu-id="c7ba6-115">Dopo l'aggiunta della trasformazione alla finestra di progettazione del flusso di dati, ma prima della sua configurazione, è possibile connettere la trasformazione al flusso di dati connettendo l'output di un'altra trasformazione o di un'altra origine nel flusso di dati all'input della nuova trasformazione.</span><span class="sxs-lookup"><span data-stu-id="c7ba6-115">After you add the transformation to the data flow designer, but before you configure the transformation, you connect the transformation to the data flow by connecting the output of another transformation or source in the data flow to the input of this transformation.</span></span> <span data-ttu-id="c7ba6-116">Il connettore tra due componenti del flusso di dati è detto percorso.</span><span class="sxs-lookup"><span data-stu-id="c7ba6-116">The connector between two data flow components is called a path.</span></span> <span data-ttu-id="c7ba6-117">Per altre informazioni sulla connessione di componenti e l'uso dei percorsi, vedere [Connessione di componenti con i percorsi](../../connect-components-with-paths.md).</span><span class="sxs-lookup"><span data-stu-id="c7ba6-117">For more information about connecting components and working with paths, see [Connect Components with Paths](../../connect-components-with-paths.md).</span></span>  
  
### <a name="to-add-a-transformation-to-a-data-flow"></a><span data-ttu-id="c7ba6-118">Per aggiungere una trasformazione a un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="c7ba6-118">To add a transformation to a data flow</span></span>  
  
-   [<span data-ttu-id="c7ba6-119">Aggiunta o eliminazione di un componente in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="c7ba6-119">Add or Delete a Component in a Data Flow</span></span>](../add-or-delete-a-component-in-a-data-flow.md)  
  
### <a name="to-connect-a-transformation-to-a-data-flow"></a><span data-ttu-id="c7ba6-120">Per connettere una trasformazione a un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="c7ba6-120">To connect a transformation to a data flow</span></span>  
  
-   [<span data-ttu-id="c7ba6-121">Connettere componenti in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="c7ba6-121">Connect Components in a Data Flow</span></span>](../connect-components-in-a-data-flow.md)  
  
### <a name="to-set-the-properties-of-a-transformation"></a><span data-ttu-id="c7ba6-122">Per impostare le proprietà di una trasformazione</span><span class="sxs-lookup"><span data-stu-id="c7ba6-122">To set the properties of a transformation</span></span>  
  
-   [<span data-ttu-id="c7ba6-123">Impostazione delle proprietà di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="c7ba6-123">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="c7ba6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7ba6-124">See Also</span></span>  
 <span data-ttu-id="c7ba6-125">[Attività Flusso di dati](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="c7ba6-125">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 <span data-ttu-id="c7ba6-126">[Flusso di dati](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="c7ba6-126">[Data Flow](../data-flow.md) </span></span>  
 <span data-ttu-id="c7ba6-127">[Connessione di componenti con i percorsi](../../connect-components-with-paths.md) </span><span class="sxs-lookup"><span data-stu-id="c7ba6-127">[Connect Components with Paths](../../connect-components-with-paths.md) </span></span>  
 <span data-ttu-id="c7ba6-128">[Gestione degli errori nei dati](../error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="c7ba6-128">[Error Handling in Data](../error-handling-in-data.md) </span></span>  
 [<span data-ttu-id="c7ba6-129">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="c7ba6-129">Data Flow</span></span>](../data-flow.md)  
  
  
