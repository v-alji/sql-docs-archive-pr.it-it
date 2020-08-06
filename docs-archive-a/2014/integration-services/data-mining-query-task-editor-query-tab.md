---
title: Editor attività query di data mining (scheda query) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.query.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 72b1755d-d226-46c5-b862-0c9333196a10
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6005c92d0d48850461c01353ddf94c61140d0f2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722908"
---
# <a name="data-mining-query-task-editor-query-tab"></a><span data-ttu-id="2a71f-102">Editor attività Query di data mining (scheda Query)</span><span class="sxs-lookup"><span data-stu-id="2a71f-102">Data Mining Query Task Editor (Query Tab)</span></span>
  <span data-ttu-id="2a71f-103">Usare la scheda **Query** della finestra di dialogo **Attività Query di data mining** per creare query di stima basate su un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="2a71f-103">Use the **Query** tab of the **Data Mining Query Task** dialog box to create prediction queries based on a mining model.</span></span> <span data-ttu-id="2a71f-104">In questa finestra di dialogo è inoltre possibile associare parametri e set di risultati a variabili.</span><span class="sxs-lookup"><span data-stu-id="2a71f-104">In this dialog box you can also bind parameters and result sets to variables.</span></span>  
  
 <span data-ttu-id="2a71f-105">Per informazioni sull'implementazione di data mining nei pacchetti, vedere [Attività Query di data mining](control-flow/data-mining-query-task.md) e [Soluzioni di data mining](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="2a71f-105">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="2a71f-106">Opzioni generali</span><span class="sxs-lookup"><span data-stu-id="2a71f-106">General Options</span></span>  
 <span data-ttu-id="2a71f-107">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2a71f-107">**Name**</span></span>  
 <span data-ttu-id="2a71f-108">Consente di specificare un nome univoco per l'attività Query di data mining.</span><span class="sxs-lookup"><span data-stu-id="2a71f-108">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="2a71f-109">Tale nome viene utilizzato come etichetta nell'icona dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2a71f-109">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a71f-110">I nomi delle attività devono essere univoci all'interno di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2a71f-110">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="2a71f-111">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2a71f-111">**Description**</span></span>  
 <span data-ttu-id="2a71f-112">Consente di digitare una descrizione dell'attività Query di data mining.</span><span class="sxs-lookup"><span data-stu-id="2a71f-112">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="build-query-tab-options"></a><span data-ttu-id="2a71f-113">Opzioni della scheda Compila query</span><span class="sxs-lookup"><span data-stu-id="2a71f-113">Build Query Tab Options</span></span>  
 <span data-ttu-id="2a71f-114">**Query di data mining**</span><span class="sxs-lookup"><span data-stu-id="2a71f-114">**Data mining query**</span></span>  
 <span data-ttu-id="2a71f-115">Consente di digitare una query di data mining.</span><span class="sxs-lookup"><span data-stu-id="2a71f-115">Type a data mining query.</span></span>  
  
 <span data-ttu-id="2a71f-116">**Argomenti correlati:**  [Guida di riferimento a DMX &#40;Data Mining Extensions&#41;](/sql/dmx/data-mining-extensions-dmx-reference)</span><span class="sxs-lookup"><span data-stu-id="2a71f-116">**Related Topics:**  [Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference)</span></span>  
  
 <span data-ttu-id="2a71f-117">**Compila nuova query**</span><span class="sxs-lookup"><span data-stu-id="2a71f-117">**Build New Query**</span></span>  
 <span data-ttu-id="2a71f-118">Consente di creare una query di data mining utilizzando uno strumento grafico.</span><span class="sxs-lookup"><span data-stu-id="2a71f-118">Create the data mining query using a graphical tool.</span></span>  
  
 <span data-ttu-id="2a71f-119">**Argomenti correlati:** [Data Mining Query](control-flow/data-mining-query.md)</span><span class="sxs-lookup"><span data-stu-id="2a71f-119">**Related Topics:** [Data Mining Query](control-flow/data-mining-query.md)</span></span>  
  
## <a name="parameter-mapping-tab-options"></a><span data-ttu-id="2a71f-120">Opzioni della scheda Mapping parametri</span><span class="sxs-lookup"><span data-stu-id="2a71f-120">Parameter Mapping Tab Options</span></span>  
 <span data-ttu-id="2a71f-121">**Nome parametro**</span><span class="sxs-lookup"><span data-stu-id="2a71f-121">**Parameter Name**</span></span>  
 <span data-ttu-id="2a71f-122">Se lo si desidera, consente di aggiornare il nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="2a71f-122">Optionally, update the parameter name.</span></span> <span data-ttu-id="2a71f-123">Eseguire il mapping del parametro a una variabile selezionando una variabile nell'elenco **Nome variabile** .</span><span class="sxs-lookup"><span data-stu-id="2a71f-123">Map the parameter to a variable by selecting a variable in the **Variable Name** list.</span></span>  
  
 <span data-ttu-id="2a71f-124">**Nome variabile**</span><span class="sxs-lookup"><span data-stu-id="2a71f-124">**Variable Name**</span></span>  
 <span data-ttu-id="2a71f-125">Consente di selezionare una variabile nell'elenco per mapparla al parametro.</span><span class="sxs-lookup"><span data-stu-id="2a71f-125">Select a variable in the list to map it to the parameter.</span></span>  
  
 <span data-ttu-id="2a71f-126">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="2a71f-126">**Add**</span></span>  
 <span data-ttu-id="2a71f-127">Consente di aggiungere un parametro all'elenco.</span><span class="sxs-lookup"><span data-stu-id="2a71f-127">Add to a parameter to the list.</span></span>  
  
 <span data-ttu-id="2a71f-128">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="2a71f-128">**Remove**</span></span>  
 <span data-ttu-id="2a71f-129">Selezionare un parametro e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="2a71f-129">Select a parameter, and then click **Remove**.</span></span>  
  
## <a name="result-set-tab-options"></a><span data-ttu-id="2a71f-130">Opzioni della scheda Set dei risultati</span><span class="sxs-lookup"><span data-stu-id="2a71f-130">Result Set Tab Options</span></span>  
 <span data-ttu-id="2a71f-131">**Nome risultato**</span><span class="sxs-lookup"><span data-stu-id="2a71f-131">**Result Name**</span></span>  
 <span data-ttu-id="2a71f-132">Se lo si desidera, consente di aggiornare il nome del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="2a71f-132">Optionally, update the result set name.</span></span> <span data-ttu-id="2a71f-133">Eseguire il mapping del risultato a una variabile selezionando una variabile nell'elenco **Nome variabile** .</span><span class="sxs-lookup"><span data-stu-id="2a71f-133">Map the result to a variable by selecting a variable in the **Variable Name** list.</span></span>  
  
 <span data-ttu-id="2a71f-134">Dopo aver aggiunto un risultato facendo clic su **Aggiungi**, specificare un nome univoco per il risultato.</span><span class="sxs-lookup"><span data-stu-id="2a71f-134">After you have added a result by clicking **Add**, provide a unique name for the result.</span></span>  
  
 <span data-ttu-id="2a71f-135">**Nome variabile**</span><span class="sxs-lookup"><span data-stu-id="2a71f-135">**Variable Name**</span></span>  
 <span data-ttu-id="2a71f-136">Consente di selezionare una variabile nell'elenco per mapparla al set dei risultati.</span><span class="sxs-lookup"><span data-stu-id="2a71f-136">Select a variable in the list to map it to the result set.</span></span>  
  
 <span data-ttu-id="2a71f-137">**Tipo di risultato**</span><span class="sxs-lookup"><span data-stu-id="2a71f-137">**Result Type**</span></span>  
 <span data-ttu-id="2a71f-138">Consente di indicare se restituire un singola riga o un set di risultati completo.</span><span class="sxs-lookup"><span data-stu-id="2a71f-138">Indicate whether to return a single row or a full result set.</span></span>  
  
 <span data-ttu-id="2a71f-139">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="2a71f-139">**Add**</span></span>  
 <span data-ttu-id="2a71f-140">Consente di aggiungere il set di risultati all'elenco.</span><span class="sxs-lookup"><span data-stu-id="2a71f-140">Add a result set to the list.</span></span>  
  
 <span data-ttu-id="2a71f-141">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="2a71f-141">**Remove**</span></span>  
 <span data-ttu-id="2a71f-142">Selezionare un risultato e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="2a71f-142">Select a result, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a71f-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a71f-143">See Also</span></span>  
 <span data-ttu-id="2a71f-144">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2a71f-144">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2a71f-145">[Editor attività query di data mining &#40;scheda modello di data mining&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span><span class="sxs-lookup"><span data-stu-id="2a71f-145">[Data Mining Query Task Editor &#40;Mining Model Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span></span>  
 <span data-ttu-id="2a71f-146">[Editor attività query di data mining &#40;scheda output&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span><span class="sxs-lookup"><span data-stu-id="2a71f-146">[Data Mining Query Task Editor &#40;Output Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span></span>  
 [<span data-ttu-id="2a71f-147">Data Mining Designer</span><span class="sxs-lookup"><span data-stu-id="2a71f-147">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
