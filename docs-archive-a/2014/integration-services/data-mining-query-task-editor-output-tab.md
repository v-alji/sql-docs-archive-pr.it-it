---
title: Editor attività query di data mining (scheda output) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.output.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 62f9e015-6fe0-4396-ad90-3ad51bf00025
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1508972b0487daa90f52af723d58185944a19a58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722912"
---
# <a name="data-mining-query-task-editor-output-tab"></a><span data-ttu-id="472cd-102">Editor attività Query di data mining (Scheda Output)</span><span class="sxs-lookup"><span data-stu-id="472cd-102">Data Mining Query Task Editor (Output Tab)</span></span>
  <span data-ttu-id="472cd-103">Utilizzare la scheda **Output** della finestra di dialogo **Editor attività Query di data mining** per specificare la destinazione della query di stima.</span><span class="sxs-lookup"><span data-stu-id="472cd-103">Use the **Output** tab of the **Data Mining Query Task Editor** dialog box to specify the destination of the prediction query.</span></span>  
  
 <span data-ttu-id="472cd-104">Per informazioni sull'implementazione di data mining nei pacchetti, vedere [Attività Query di data mining](control-flow/data-mining-query-task.md) e [Soluzioni di data mining](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="472cd-104">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="472cd-105">Opzioni generali</span><span class="sxs-lookup"><span data-stu-id="472cd-105">General Options</span></span>  
 <span data-ttu-id="472cd-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="472cd-106">**Name**</span></span>  
 <span data-ttu-id="472cd-107">Consente di specificare un nome univoco per l'attività Query di data mining.</span><span class="sxs-lookup"><span data-stu-id="472cd-107">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="472cd-108">Tale nome viene utilizzato come etichetta nell'icona dell'attività.</span><span class="sxs-lookup"><span data-stu-id="472cd-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="472cd-109">I nomi delle attività devono essere univoci all'interno di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="472cd-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="472cd-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="472cd-110">**Description**</span></span>  
 <span data-ttu-id="472cd-111">Consente di digitare una descrizione dell'attività Query di data mining.</span><span class="sxs-lookup"><span data-stu-id="472cd-111">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="output-tab-options"></a><span data-ttu-id="472cd-112">Opzioni della scheda Output</span><span class="sxs-lookup"><span data-stu-id="472cd-112">Output Tab Options</span></span>  
 <span data-ttu-id="472cd-113">**Connection**</span><span class="sxs-lookup"><span data-stu-id="472cd-113">**Connection**</span></span>  
 <span data-ttu-id="472cd-114">Selezionare una gestione connessione nell'elenco oppure fare clic su **Nuova** per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="472cd-114">Select a connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="472cd-115">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="472cd-115">**New**</span></span>  
 <span data-ttu-id="472cd-116">Consente di creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="472cd-116">Create a new connection manager.</span></span> <span data-ttu-id="472cd-117">È possibile utilizzare solo i tipi di gestione connessione ADO.NET e OLE DB.</span><span class="sxs-lookup"><span data-stu-id="472cd-117">Only the ADO.NET and OLE DB connection manager types can be used.</span></span>  
  
 <span data-ttu-id="472cd-118">**Tabella di output**</span><span class="sxs-lookup"><span data-stu-id="472cd-118">**Output table**</span></span>  
 <span data-ttu-id="472cd-119">Consente di specificare la tabella in cui la query di stima scrive i risultati.</span><span class="sxs-lookup"><span data-stu-id="472cd-119">Specify the table to which the prediction query writes its results.</span></span>  
  
 <span data-ttu-id="472cd-120">**Elimina e ricrea tabella di output**</span><span class="sxs-lookup"><span data-stu-id="472cd-120">**Drop and re-create the output table**</span></span>  
 <span data-ttu-id="472cd-121">Consente di indicare se la query di stima deve sovrascrivere il contenuto nella tabella di destinazione, eliminando e quindi creando di nuovo la tabella.</span><span class="sxs-lookup"><span data-stu-id="472cd-121">Indicate whether the prediction query should overwrite content in the destination table by dropping and then re-creating the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="472cd-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="472cd-122">See Also</span></span>  
 <span data-ttu-id="472cd-123">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="472cd-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="472cd-124">[Editor attività query di data mining &#40;scheda modello di data mining&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span><span class="sxs-lookup"><span data-stu-id="472cd-124">[Data Mining Query Task Editor &#40;Mining Model Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span></span>  
 <span data-ttu-id="472cd-125">[Editor attività query di data mining &#40;scheda query&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span><span class="sxs-lookup"><span data-stu-id="472cd-125">[Data Mining Query Task Editor &#40;Query Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span></span>  
 [<span data-ttu-id="472cd-126">Data Mining Designer</span><span class="sxs-lookup"><span data-stu-id="472cd-126">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
