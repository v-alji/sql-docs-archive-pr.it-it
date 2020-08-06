---
title: Editor attività Elaborazione Analysis Services (pagina Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asprocessingtask.as.f1
helpviewer_keywords:
- Analysis Services Processing Task Editor
ms.assetid: 5612be78-57cf-4e4e-92cf-6bfa9f971040
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aabcfe286b40f58b429227654107d58e8a4ee837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626229"
---
# <a name="analysis-services-processing-task-editor-analysis-services-page"></a><span data-ttu-id="be50c-102">Editor attività Elaborazione Analysis Services (pagina Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="be50c-102">Analysis Services Processing Task Editor (Analysis Services Page)</span></span>
  <span data-ttu-id="be50c-103">Usare la pagina **Analysis Services** della finestra di dialogo **Editor attività Elaborazione Analysis Services** per specificare una gestione connessione Analysis Services, selezionare gli oggetti analitici da elaborare e impostare le opzioni di elaborazione e di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="be50c-103">Use the **Analysis Services** page of the **Analysis Services Processing Task Editor** dialog box to specify an Analysis Services connection manager, select the analytic objects to process, and set processing and error handling options.</span></span>  
  
 <span data-ttu-id="be50c-104">Quando si elaborano modelli tabulari, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="be50c-104">When processing tabular models, keep the following in mind:</span></span>  
  
1.  <span data-ttu-id="be50c-105">Non è possibile effettuare analisi di impatto sui modelli tabulari.</span><span class="sxs-lookup"><span data-stu-id="be50c-105">You cannot perform impact analysis on tabular models.</span></span>  
  
2.  <span data-ttu-id="be50c-106">Alcune opzioni di elaborazione per la modalità tabulare non sono esposte, ad esempio Elaborazione deframmentazione e Elabora ricalcolo.</span><span class="sxs-lookup"><span data-stu-id="be50c-106">Some processing options for tabular mode are not exposed, such as Process Defrag and Process Recalc.</span></span> <span data-ttu-id="be50c-107">È possibile eseguire queste funzioni tramite l'attività Esegui DDL.</span><span class="sxs-lookup"><span data-stu-id="be50c-107">You can perform these functions by using the Execute DDL task.</span></span>  
  
3.  <span data-ttu-id="be50c-108">Alcune opzioni di elaborazione fornite, ad esempio l'elaborazione di indici, non sono appropriate per i modelli tabulari, pertanto non devono essere utilizzate.</span><span class="sxs-lookup"><span data-stu-id="be50c-108">Some processing options provided, such as process indexes, are not appropriate for tabular models and should not be used.</span></span>  
  
4.  <span data-ttu-id="be50c-109">Le impostazioni batch vengono ignorate per i modelli tabulari.</span><span class="sxs-lookup"><span data-stu-id="be50c-109">Batch settings are ignored for tabular models.</span></span>  
  
 <span data-ttu-id="be50c-110">Per altre informazioni su questa attività, vedere [Attività Elaborazione Analysis Services](control-flow/analysis-services-processing-task.md).</span><span class="sxs-lookup"><span data-stu-id="be50c-110">To learn about this task, see [Analysis Services Processing Task](control-flow/analysis-services-processing-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="be50c-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="be50c-111">Options</span></span>  
 <span data-ttu-id="be50c-112">**Gestione connessione Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="be50c-112">**Analysis Services connection manager**</span></span>  
 <span data-ttu-id="be50c-113">Consente di selezionare una gestione connessione Analysis Services esistente nell'elenco o di crearne una nuova usando il pulsante **Nuova** .</span><span class="sxs-lookup"><span data-stu-id="be50c-113">Select an existing Analysis Services connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="be50c-114">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="be50c-114">**New**</span></span>  
 <span data-ttu-id="be50c-115">Consente di creare una nuova gestione connessione Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="be50c-115">Create a new Analysis Services connection manager.</span></span>  
  
 <span data-ttu-id="be50c-116">**Argomenti correlati:** [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md), [Riferimento all'interfaccia utente della finestra di dialogo Aggiungi gestione connessione Analysis Services](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span><span class="sxs-lookup"><span data-stu-id="be50c-116">**Related Topics:** [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md), [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span></span>  
  
 <span data-ttu-id="be50c-117">**Elenco oggetti**</span><span class="sxs-lookup"><span data-stu-id="be50c-117">**Object list**</span></span>  
 |<span data-ttu-id="be50c-118">Proprietà</span><span class="sxs-lookup"><span data-stu-id="be50c-118">Property</span></span>|<span data-ttu-id="be50c-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be50c-119">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="be50c-120">**nome oggetto**</span><span class="sxs-lookup"><span data-stu-id="be50c-120">**Object Name**</span></span>|<span data-ttu-id="be50c-121">Consente di visualizzare i nomi degli oggetti specificati.</span><span class="sxs-lookup"><span data-stu-id="be50c-121">Lists the specified object names.</span></span>|  
|<span data-ttu-id="be50c-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="be50c-122">**Type**</span></span>|<span data-ttu-id="be50c-123">Consente di visualizzare i tipi degli oggetti specificati.</span><span class="sxs-lookup"><span data-stu-id="be50c-123">Lists the types of the specified objects.</span></span>|  
|<span data-ttu-id="be50c-124">**Opzioni elaborazione**</span><span class="sxs-lookup"><span data-stu-id="be50c-124">**Process Options**</span></span>|<span data-ttu-id="be50c-125">Consente di selezionare un'opzione di elaborazione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="be50c-125">Select a processing option in the list.</span></span><br /><br /> <span data-ttu-id="be50c-126">**Argomenti correlati**: [elaborazione di oggetti del modello multidimensionale](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services)</span><span class="sxs-lookup"><span data-stu-id="be50c-126">**Related Topics**: [Multidimensional Model Object Processing](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services)</span></span>|  
|<span data-ttu-id="be50c-127">**Impostazioni**</span><span class="sxs-lookup"><span data-stu-id="be50c-127">**Settings**</span></span>|<span data-ttu-id="be50c-128">Consente di visualizzare le impostazioni di elaborazione per gli oggetti specificati.</span><span class="sxs-lookup"><span data-stu-id="be50c-128">Lists processing settings for the specified objects.</span></span>|  
  
 <span data-ttu-id="be50c-129">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="be50c-129">**Add**</span></span>  
 <span data-ttu-id="be50c-130">Consente di aggiungere un oggetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] all'elenco.</span><span class="sxs-lookup"><span data-stu-id="be50c-130">Add an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object to the list.</span></span>  
  
 <span data-ttu-id="be50c-131">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="be50c-131">**Remove**</span></span>  
 <span data-ttu-id="be50c-132">Selezionare un oggetto, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="be50c-132">Select an object, and then click **Delete**.</span></span>  
  
 <span data-ttu-id="be50c-133">**Analisi di impatto**</span><span class="sxs-lookup"><span data-stu-id="be50c-133">**Impact Analysis**</span></span>  
 <span data-ttu-id="be50c-134">Consente di eseguire un'analisi di impatto sull'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="be50c-134">Perform impact analysis on the selected object.</span></span>  
  
 <span data-ttu-id="be50c-135">**Argomenti correlati:** [Finestra di dialogo Analisi di impatto &#40;Analysis Services - Dati multidimensionali&#41;](../../2014/analysis-services/impact-analysis-dialog-box-analysis-services-multidimensional-data.md)</span><span class="sxs-lookup"><span data-stu-id="be50c-135">**Related Topics:** [Impact Analysis Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/impact-analysis-dialog-box-analysis-services-multidimensional-data.md)</span></span>  
  
 <span data-ttu-id="be50c-136">**Riepilogo impostazioni batch**</span><span class="sxs-lookup"><span data-stu-id="be50c-136">**Batch Settings Summary**</span></span>  
 |<span data-ttu-id="be50c-137">Proprietà</span><span class="sxs-lookup"><span data-stu-id="be50c-137">Property</span></span>|<span data-ttu-id="be50c-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be50c-138">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="be50c-139">**Ordine di elaborazione**</span><span class="sxs-lookup"><span data-stu-id="be50c-139">**Processing order**</span></span>|<span data-ttu-id="be50c-140">Consente di specificare se gli oggetti devono essere elaborati sequenzialmente o in un batch. Se si utilizza l'elaborazione parallela, consente di specificare il numero di oggetti da elaborare simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="be50c-140">Specifies whether objects are processed sequentially or in a batch; if parallel processing is used, specifies the number of objects to process concurrently.</span></span>|  
|<span data-ttu-id="be50c-141">**Modalità transazione**</span><span class="sxs-lookup"><span data-stu-id="be50c-141">**Transaction mode**</span></span>|<span data-ttu-id="be50c-142">Consente di specificare la modalità di transazione per l'elaborazione sequenziale.</span><span class="sxs-lookup"><span data-stu-id="be50c-142">Specifies the transaction mode for sequential processing.</span></span>|  
|<span data-ttu-id="be50c-143">**Errori dimensione**</span><span class="sxs-lookup"><span data-stu-id="be50c-143">**Dimension errors**</span></span>|<span data-ttu-id="be50c-144">Consente di specificare il funzionamento dell'attività quando si verificano errori.</span><span class="sxs-lookup"><span data-stu-id="be50c-144">Specifies the task behavior when errors occur.</span></span>|  
|<span data-ttu-id="be50c-145">**Percorso log degli errori di chiave della dimensione**</span><span class="sxs-lookup"><span data-stu-id="be50c-145">**Dimension key error log path**</span></span>|<span data-ttu-id="be50c-146">Consente di specificare il percorso del file nel quale vengono registrati gli errori.</span><span class="sxs-lookup"><span data-stu-id="be50c-146">Specifies the path of the file to which errors are logged.</span></span>|  
|<span data-ttu-id="be50c-147">**Elabora oggetti interessati**</span><span class="sxs-lookup"><span data-stu-id="be50c-147">**Process affected objects**</span></span>|<span data-ttu-id="be50c-148">Indica se vengono elaborati anche gli oggetti dipendenti o interessati.</span><span class="sxs-lookup"><span data-stu-id="be50c-148">Indicates whether dependent or affected objects are also processed.</span></span>|  
  
 <span data-ttu-id="be50c-149">**Modifica impostazioni**</span><span class="sxs-lookup"><span data-stu-id="be50c-149">**Change Settings**</span></span>  
 <span data-ttu-id="be50c-150">Consente di modificare le opzioni di elaborazione e la gestione degli errori nelle chiavi della dimensione.</span><span class="sxs-lookup"><span data-stu-id="be50c-150">Change the processing options and the handling of errors in dimension keys.</span></span>  
  
 <span data-ttu-id="be50c-151">**Argomenti correlati:** [Finestra di dialogo Cambia impostazioni &#40;Analysis Services - Dati multidimensionali&#41;](../../2014/analysis-services/change-settings-dialog-box-analysis-services-multidimensional-data.md)</span><span class="sxs-lookup"><span data-stu-id="be50c-151">**Related Topics:** [Change Settings Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/change-settings-dialog-box-analysis-services-multidimensional-data.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be50c-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be50c-152">See Also</span></span>  
 <span data-ttu-id="be50c-153">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="be50c-153">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="be50c-154">[Editor attività Elaborazione Analysis Services &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="be50c-154">[Analysis Services Processing Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="be50c-155">Attività Esegui DDL Analysis Services</span><span class="sxs-lookup"><span data-stu-id="be50c-155">Analysis Services Execute DDL Task</span></span>](control-flow/analysis-services-execute-ddl-task.md)  
  
  
