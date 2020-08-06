---
title: Percorsi in Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- paths [Integration Services], about paths
- data flow [Integration Services], paths
- paths [Integration Services]
- destinations [Integration Services], paths
- sources [Integration Services], paths
ms.assetid: 6c4629a9-2ede-4011-9101-3b342249640e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c52bbd06974311a7fc94b3058309399d70df0034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715635"
---
# <a name="integration-services-paths"></a><span data-ttu-id="846f9-102">Percorsi in Integration Services</span><span class="sxs-lookup"><span data-stu-id="846f9-102">Integration Services Paths</span></span>
  <span data-ttu-id="846f9-103">Un percorso collega due componenti in un flusso di dati connettendo l'output di un componente all'input dell'altro.</span><span class="sxs-lookup"><span data-stu-id="846f9-103">A path connects two components in a data flow by connecting the output of one data flow component to the input of another component.</span></span> <span data-ttu-id="846f9-104">Un percorso ha un'origine e una destinazione.</span><span class="sxs-lookup"><span data-stu-id="846f9-104">A path has a source and a destination.</span></span> <span data-ttu-id="846f9-105">Se un percorso connette, ad esempio, un'origine OLE DB e una trasformazione Ordinamento, l'origine OLE DB costituirà l'origine del percorso e la trasformazione Ordinamento ne costituirà la destinazione.</span><span class="sxs-lookup"><span data-stu-id="846f9-105">For example, if a path connects an OLE DB source and a Sort transformation, the OLE DB source is the source of the path, and the Sort transformation is the destination of the path.</span></span> <span data-ttu-id="846f9-106">L'origine è il componente da cui inizia il percorso, mentre la destinazione è il componente in cui termina.</span><span class="sxs-lookup"><span data-stu-id="846f9-106">The source is the component where the path starts, and the destination is the component where the path ends.</span></span>  
  
 <span data-ttu-id="846f9-107">Se si esegue un pacchetto in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , è possibile visualizzare i dati in un flusso di dati collegando visualizzatori dati a un percorso.</span><span class="sxs-lookup"><span data-stu-id="846f9-107">If you run a package in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, you can view the data in a data flow by attaching data viewers to a path.</span></span> <span data-ttu-id="846f9-108">Un visualizzatore dati può essere configurato in modo da visualizzare i dati in una griglia.</span><span class="sxs-lookup"><span data-stu-id="846f9-108">A data viewer can be configured to display data in a grid.</span></span> <span data-ttu-id="846f9-109">Si tratta di un utile strumento di debug.</span><span class="sxs-lookup"><span data-stu-id="846f9-109">A data viewer is a useful debugging tool.</span></span> <span data-ttu-id="846f9-110">Per altre informazioni, vedere [Debug di un flusso di dati](../troubleshooting/debugging-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="846f9-110">For more information, see [Debugging Data Flow](../troubleshooting/debugging-data-flow.md).</span></span>  
  
## <a name="configuration-of-the-path"></a><span data-ttu-id="846f9-111">Configurazione del percorso</span><span class="sxs-lookup"><span data-stu-id="846f9-111">Configuration of the Path</span></span>  
 <span data-ttu-id="846f9-112">In Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] è disponibile la finestra di dialogo **Editor percorso flusso di dati** che consente di impostare le proprietà di un percorso, visualizzare i metadati delle colonne di dati che passano attraverso il percorso e configurare i visualizzatori dati.</span><span class="sxs-lookup"><span data-stu-id="846f9-112">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides the **Data Flow Path Editor** dialog box for setting path properties, viewing the metadata of the data columns that pass through the path, and configuring data viewers.</span></span>  
  
 <span data-ttu-id="846f9-113">Le proprietà configurabili di un percorso includono nome, descrizione e annotazione.</span><span class="sxs-lookup"><span data-stu-id="846f9-113">The configurable path properties include the name, description, and annotation of the path.</span></span> <span data-ttu-id="846f9-114">È possibile configurare i percorsi anche a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="846f9-114">You can also configure paths programmatically.</span></span> <span data-ttu-id="846f9-115">Per altre informazioni, vedere [Connessione dei componenti del flusso di dati a livello di programmazione](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="846f9-115">For more information, see [Connecting Data Flow Components Programmatically](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
 <span data-ttu-id="846f9-116">L'annotazione di un percorso visualizza il nome dell'origine del percorso o il nome del percorso sull'area di progettazione della scheda **Flusso di dati** in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="846f9-116">A path annotation displays the name of the path source or the path name on the design surface of the **Data Flow** tab in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="846f9-117">Le annotazioni dei percorsi sono simili a quelle che è possibile aggiungere a flussi di dati, flussi di controllo e gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="846f9-117">Path annotations are similar to the annotations you can add to data flows, control flows, and event handlers.</span></span> <span data-ttu-id="846f9-118">L'unica differenza è costituita dal fatto che sono collegate a un percorso, mentre le altre annotazioni vengono visualizzate nelle schede **Flusso di dati**, **Flusso di controllo**e **Gestore evento**di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="846f9-118">The only difference is that a path annotation is attached to a path, whereas other annotations appear on the **Data Flow**, **Control Flow**, and **Event Handle**r tabs of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="846f9-119">I metadati indicano il nome, il tipo di dati, la precisione, la scala, la lunghezza, la tabella codici e il componente di origine di ogni colonna nell'output del componente precedente.</span><span class="sxs-lookup"><span data-stu-id="846f9-119">The metadata shows the name, data type, precision, scale, length, code page, and source component of each column in the output of the previous component.</span></span> <span data-ttu-id="846f9-120">Il componente di origine è il componente del flusso di dati che ha creato la colonna</span><span class="sxs-lookup"><span data-stu-id="846f9-120">The source component is the data flow component that created the column.</span></span> <span data-ttu-id="846f9-121">e può anche non essere il primo componente nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="846f9-121">This may or may not be the first component in the data flow.</span></span> <span data-ttu-id="846f9-122">Le trasformazioni Unione input multipli e Ordinamento, ad esempio, creano proprie colonne e costituiscono pertanto l'origine delle relative colonne di output.</span><span class="sxs-lookup"><span data-stu-id="846f9-122">For example, the Union All and Sort transformations create their own columns, and they are the sources of their output columns.</span></span> <span data-ttu-id="846f9-123">La trasformazione Copia colonna, invece, può passare colonne senza modificarle oppure creare nuove colonne copiando le colonne di input.</span><span class="sxs-lookup"><span data-stu-id="846f9-123">In contrast, a Copy Column transformation can pass through columns without changing them or can create new columns by copying input columns.</span></span> <span data-ttu-id="846f9-124">La trasformazione Copia colonna costituisce il componente di origine solo per le nuove colonne.</span><span class="sxs-lookup"><span data-stu-id="846f9-124">The Copy Column transformation is the source component only of the new columns.</span></span>  
  
 <span data-ttu-id="846f9-125">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="846f9-125">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="846f9-126">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor percorso flusso di dati**, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="846f9-126">For more information about the properties that you can set in the **Data Flow Path Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="846f9-127">Editor percorso flusso di dati &#40;pagina generale&#41;</span><span class="sxs-lookup"><span data-stu-id="846f9-127">Data Flow Path Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="846f9-128">Editor percorso flusso di dati &#40;pagina metadati&#41;</span><span class="sxs-lookup"><span data-stu-id="846f9-128">Data Flow Path Editor &#40;Metadata Page&#41;</span></span>](../data-flow-path-editor-metadata-page.md)  
  
-   [<span data-ttu-id="846f9-129">Editor percorso flusso di dati &#40;pagina visualizzatori dati&#41;</span><span class="sxs-lookup"><span data-stu-id="846f9-129">Data Flow Path Editor &#40;Data Viewers Page&#41;</span></span>](../data-flow-path-editor-data-viewers-page.md)  
  
 <span data-ttu-id="846f9-130">Per altre informazioni sulle proprietà che è possibile impostare a livello di programmazione, vedere [Proprietà del percorso](../path-properties.md).</span><span class="sxs-lookup"><span data-stu-id="846f9-130">For more information about the properties that you can set programmatically, see [Path Properties](../path-properties.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="846f9-131">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="846f9-131">Related Tasks</span></span>  
  
-   [<span data-ttu-id="846f9-132">Visualizzazione dei metadati dei percorsi nell'Editor percorso flusso di dati</span><span class="sxs-lookup"><span data-stu-id="846f9-132">View Path Metadata in the Data Flow Path Editor</span></span>](../view-path-metadata-in-the-data-flow-path-editor.md)  
  
-   [<span data-ttu-id="846f9-133">Connessione di componenti in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="846f9-133">Connect Components in a Data Flow</span></span>](connect-components-in-a-data-flow.md)  
  
## <a name="see-also"></a><span data-ttu-id="846f9-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="846f9-134">See Also</span></span>  
 [<span data-ttu-id="846f9-135">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="846f9-135">Data Flow</span></span>](data-flow.md)  
  
  
