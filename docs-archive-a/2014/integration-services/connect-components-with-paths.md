---
title: Connettere i componenti con i percorsi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data flow [Integration Services], connections
- components [Integration Services], connections
- connections [Integration Services], data flow components
ms.assetid: 05633e4c-1370-4b05-802b-f36b07dd71c8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e11955601406406abe48b53197e95c8224762fee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722976"
---
# <a name="connect-components-with-paths"></a><span data-ttu-id="18bf7-102">Connessione di componenti con i percorsi</span><span class="sxs-lookup"><span data-stu-id="18bf7-102">Connect Components with Paths</span></span>
  <span data-ttu-id="18bf7-103">Per costruire il flusso di dati in un pacchetto, è possibile usare l'area di progettazione della scheda **Flusso di dati** di Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18bf7-103">You construct the data flow in a package on the design surface of the **Data Flow** tab in the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="18bf7-104">Se un flusso di dati contiene due componenti, sarà possibile connetterli connettendo l'output di un'origine o trasformazione all'input di una trasformazione o destinazione.</span><span class="sxs-lookup"><span data-stu-id="18bf7-104">If a data flow contains two data flow components, you can connect them by connecting the output of a source or transformation to the input of a transformation or destination.</span></span> <span data-ttu-id="18bf7-105">Il connettore tra due componenti del flusso di dati è detto percorso.</span><span class="sxs-lookup"><span data-stu-id="18bf7-105">The connector between two data flow components is called a path.</span></span>

 <span data-ttu-id="18bf7-106">Nella figura seguente viene illustrato un semplice flusso di dati con un componente di origine, due trasformazioni, un componente di destinazione e i percorsi che li connettono.</span><span class="sxs-lookup"><span data-stu-id="18bf7-106">The following diagram shows a simple data flow with a source component, two transformations, a destination component, and the paths that connect them.</span></span>

 <span data-ttu-id="18bf7-107">![Flusso di dati](media/mw-dts-08.gif "Flusso di dati")</span><span class="sxs-lookup"><span data-stu-id="18bf7-107">![Data flow](media/mw-dts-08.gif "Data flow")</span></span>

 <span data-ttu-id="18bf7-108">Dopo aver connesso i due componenti è possibile visualizzare i metadati dei dati che si spostano lungo il percorso e le proprietà del percorso nella finestra **Editor percorso flusso di dati**.</span><span class="sxs-lookup"><span data-stu-id="18bf7-108">After two components are connected, you can view the metadata of the data that moves through the path and the properties of the path in **Data Flow Path Editor**.</span></span> <span data-ttu-id="18bf7-109">Per altre informazioni, vedere [Percorsi in Integration Services](data-flow/integration-services-paths.md).</span><span class="sxs-lookup"><span data-stu-id="18bf7-109">For more information, see [Integration Services Paths](data-flow/integration-services-paths.md).</span></span>

 <span data-ttu-id="18bf7-110">A un percorso è possibile aggiungere anche un visualizzatore dati,</span><span class="sxs-lookup"><span data-stu-id="18bf7-110">You can also add data viewers to paths.</span></span> <span data-ttu-id="18bf7-111">che consente di visualizzare i dati che si spostano tra i componenti del flusso di dati durante l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="18bf7-111">A data viewer makes it possible to view data moving between data flow components when the package is run.</span></span>

### <a name="to-connect-components-in-a-data-flow"></a><span data-ttu-id="18bf7-112">Per connettere componenti in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="18bf7-112">To connect components in a data flow</span></span>

-   [<span data-ttu-id="18bf7-113">Connessione di componenti in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="18bf7-113">Connect Components in a Data Flow</span></span>](data-flow/connect-components-in-a-data-flow.md)

### <a name="to-set-path-properties"></a><span data-ttu-id="18bf7-114">Per impostare le proprietà di un percorso</span><span class="sxs-lookup"><span data-stu-id="18bf7-114">To set path properties</span></span>

-   [<span data-ttu-id="18bf7-115">Impostazione delle proprietà di un percorso tramite l'Editor percorso flusso di dati</span><span class="sxs-lookup"><span data-stu-id="18bf7-115">Set the Properties of a Path by Using the Data Flow Path Editor</span></span>](../../2014/integration-services/set-the-properties-of-a-path-by-using-the-data-flow-path-editor.md)

### <a name="to-view-path-metadata"></a><span data-ttu-id="18bf7-116">Per visualizzare i metadati di un percorso</span><span class="sxs-lookup"><span data-stu-id="18bf7-116">To view path metadata</span></span>

-   [<span data-ttu-id="18bf7-117">Visualizzazione dei metadati dei percorsi nell'Editor percorso flusso di dati</span><span class="sxs-lookup"><span data-stu-id="18bf7-117">View Path Metadata in the Data Flow Path Editor</span></span>](../../2014/integration-services/view-path-metadata-in-the-data-flow-path-editor.md)

### <a name="to-view-path-metadata"></a><span data-ttu-id="18bf7-118">Per visualizzare i metadati di un percorso</span><span class="sxs-lookup"><span data-stu-id="18bf7-118">To view path metadata</span></span>

-   [<span data-ttu-id="18bf7-119">Aggiunta di un visualizzatore dati a un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="18bf7-119">Add a Data Viewer to a Data Flow</span></span>](../../2014/integration-services/add-a-data-viewer-to-a-data-flow.md)

## <a name="see-also"></a><span data-ttu-id="18bf7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18bf7-120">See Also</span></span>
 <span data-ttu-id="18bf7-121">[Flusso](data-flow/data-flow.md) di dati dell' [attività flusso](control-flow/data-flow-task.md) di dati [trasformare i dati con le trasformazioni](data-flow/transformations/transform-data-with-transformations.md) [gestione degli errori nei dati](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="18bf7-121">[Data Flow Task](control-flow/data-flow-task.md) [Data Flow](data-flow/data-flow.md) [Transform Data with Transformations](data-flow/transformations/transform-data-with-transformations.md) [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>


