---
title: Azioni nei modelli multidimensionali | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- actions [Analysis Services], creating
- report actions [Analysis Services]
- drillthrough actions [Analysis Services]
- cubes [Analysis Services], actions
ms.assetid: b9fee2b9-05a5-4077-848d-d8457326dc27
author: minewiskan
ms.author: owend
ms.openlocfilehash: ce42907190363be085e8f4d8e9adfbab52a70590
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627465"
---
# <a name="actions-in-multidimensional-models"></a><span data-ttu-id="76e41-102">Azioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="76e41-102">Actions in Multidimensional Models</span></span>
  <span data-ttu-id="76e41-103">Un'azione è un'operazione inizializzata dall'utente finale su un cubo o una parte di un cubo selezionati.</span><span class="sxs-lookup"><span data-stu-id="76e41-103">An action is an end user-initiated operation upon a selected cube or portion of a cube.</span></span> <span data-ttu-id="76e41-104">L'operazione consente di avviare un'applicazione con l'elemento selezionato come parametro oppure di recuperare informazioni sull'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="76e41-104">The operation can start an application with the selected item as a parameter, or it can retrieve information about the selected item.</span></span> <span data-ttu-id="76e41-105">Per altre informazioni sulle azioni, vedere [Azioni &#40;Analysis Services - Dati multidimensionali&41#;](actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="76e41-105">For more information about actions, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](actions-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="76e41-106">Usare la scheda **Azioni** di Progettazione cubi per compilare azioni per un cubo.</span><span class="sxs-lookup"><span data-stu-id="76e41-106">Use the **Actions** tab of Cube Designer to build actions for a cube.</span></span> <span data-ttu-id="76e41-107">Specificare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76e41-107">Specify the following:</span></span>  
  
 <span data-ttu-id="76e41-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="76e41-108">**Name**</span></span>  
 <span data-ttu-id="76e41-109">Selezionare un nome che identifichi l'azione.</span><span class="sxs-lookup"><span data-stu-id="76e41-109">Select a name that identifies the action.</span></span>  
  
 <span data-ttu-id="76e41-110">**Destinazione azione**</span><span class="sxs-lookup"><span data-stu-id="76e41-110">**Action Target**</span></span>  
 <span data-ttu-id="76e41-111">Selezionare l'oggetto a cui è associata l'azione.</span><span class="sxs-lookup"><span data-stu-id="76e41-111">Select the object to which the action is attached.</span></span> <span data-ttu-id="76e41-112">Nelle applicazioni client l'azione viene in genere visualizzata quando gli utenti finali selezionano l'oggetto di destinazione. Tuttavia, è l'applicazione client che determina quale operazione dell'utente finale attiva la visualizzazione delle azioni.</span><span class="sxs-lookup"><span data-stu-id="76e41-112">Generally, in client applications, the action is displayed when end users select the target object; however, the client application determines which end-user operation displays actions.</span></span> <span data-ttu-id="76e41-113">In **Tipo di destinazione**scegliere tra gli oggetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="76e41-113">For **Target type**, select from the following objects:</span></span>  
  
-   <span data-ttu-id="76e41-114">Membri dell'attributo</span><span class="sxs-lookup"><span data-stu-id="76e41-114">Attribute members</span></span>  
  
-   <span data-ttu-id="76e41-115">Celle</span><span class="sxs-lookup"><span data-stu-id="76e41-115">Cells</span></span>  
  
-   <span data-ttu-id="76e41-116">Cubo</span><span class="sxs-lookup"><span data-stu-id="76e41-116">Cube</span></span>  
  
-   <span data-ttu-id="76e41-117">Membri della dimensione</span><span class="sxs-lookup"><span data-stu-id="76e41-117">Dimension members</span></span>  
  
-   <span data-ttu-id="76e41-118">Gerarchia</span><span class="sxs-lookup"><span data-stu-id="76e41-118">Hierarchy</span></span>  
  
-   <span data-ttu-id="76e41-119">Membri della gerarchia</span><span class="sxs-lookup"><span data-stu-id="76e41-119">Hierarchy members</span></span>  
  
-   <span data-ttu-id="76e41-120">Level</span><span class="sxs-lookup"><span data-stu-id="76e41-120">Level</span></span>  
  
-   <span data-ttu-id="76e41-121">Membri del livello</span><span class="sxs-lookup"><span data-stu-id="76e41-121">Level members</span></span>  
  
 <span data-ttu-id="76e41-122">Dopo aver selezionato il tipo di oggetto di destinazione, in **Oggetto di destinazione**selezionare l'oggetto del cubo del tipo definito.</span><span class="sxs-lookup"><span data-stu-id="76e41-122">After you select the target object type, under **Target object**, select the cube object of the designated type.</span></span>  
  
 <span data-ttu-id="76e41-123">**Condizione (facoltativa)**</span><span class="sxs-lookup"><span data-stu-id="76e41-123">**Condition (Optional)**</span></span>  
 <span data-ttu-id="76e41-124">Specificare un'espressione MDX (Multidimensional Expressions) facoltativa che restituisca un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="76e41-124">Specify an optional Multidimensional Expressions (MDX) expression that resolves to a Boolean value.</span></span> <span data-ttu-id="76e41-125">Se il valore è `True`, l'azione viene eseguita sulla destinazione specificata.</span><span class="sxs-lookup"><span data-stu-id="76e41-125">If the value is `True`, the action is performed on the specified target.</span></span> <span data-ttu-id="76e41-126">Se invece il valore è `False`, l'azione non viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="76e41-126">If the value is `False`, the action is not performed.</span></span>  
  
 <span data-ttu-id="76e41-127">**Contenuto azione**</span><span class="sxs-lookup"><span data-stu-id="76e41-127">**Action Content**</span></span>  
 <span data-ttu-id="76e41-128">Selezionare il tipo di azione.</span><span class="sxs-lookup"><span data-stu-id="76e41-128">Select the type of action.</span></span> <span data-ttu-id="76e41-129">Nella tabella seguente vengono riepilogati i tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="76e41-129">The following table summarizes the available types.</span></span>  
  
|<span data-ttu-id="76e41-130">Type</span><span class="sxs-lookup"><span data-stu-id="76e41-130">Type</span></span>|<span data-ttu-id="76e41-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76e41-131">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="76e41-132">Set di dati</span><span class="sxs-lookup"><span data-stu-id="76e41-132">Data Set</span></span>|<span data-ttu-id="76e41-133">Consente di recuperare un set di dati.</span><span class="sxs-lookup"><span data-stu-id="76e41-133">Retrieves a dataset.</span></span>|  
|<span data-ttu-id="76e41-134">Proprietario</span><span class="sxs-lookup"><span data-stu-id="76e41-134">Proprietary</span></span>|<span data-ttu-id="76e41-135">Esegue un'operazione utilizzando un'interfaccia diversa da quelle elencate in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="76e41-135">Performs an operation by using an interface other than those listed in this table.</span></span>|  
|<span data-ttu-id="76e41-136">Set di righe</span><span class="sxs-lookup"><span data-stu-id="76e41-136">Row Set</span></span>|<span data-ttu-id="76e41-137">Consente di recuperare un set di righe.</span><span class="sxs-lookup"><span data-stu-id="76e41-137">Retrieves a rowset.</span></span>|  
|<span data-ttu-id="76e41-138">Istruzione</span><span class="sxs-lookup"><span data-stu-id="76e41-138">Statement</span></span>|<span data-ttu-id="76e41-139">Esegue un comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="76e41-139">Runs an OLE DB command.</span></span>|  
|<span data-ttu-id="76e41-140">URL</span><span class="sxs-lookup"><span data-stu-id="76e41-140">URL</span></span>|<span data-ttu-id="76e41-141">Visualizza una pagina variabile in un browser Internet.</span><span class="sxs-lookup"><span data-stu-id="76e41-141">Displays a variable page in an Internet browser.</span></span>|  
  
 <span data-ttu-id="76e41-142">In **Espressione azione**specificare i parametri passati durante l'esecuzione dell'azione.</span><span class="sxs-lookup"><span data-stu-id="76e41-142">For **Action Expression**, specify the parameters that are passed when the action is run.</span></span> <span data-ttu-id="76e41-143">Il risultato della valutazione della sintassi deve essere una stringa ed è necessario includere un'espressione MDX.</span><span class="sxs-lookup"><span data-stu-id="76e41-143">The syntax must evaluate to a string, and you must include an expression written in MDX.</span></span> <span data-ttu-id="76e41-144">Ad esempio, l'espressione MDX può indicare una parte del cubo inclusa nella sintassi.</span><span class="sxs-lookup"><span data-stu-id="76e41-144">For example, your MDX expression can indicate a part of the cube that is included in the syntax.</span></span> <span data-ttu-id="76e41-145">Le espressioni MDX vengono valutate prima del passaggio dei parametri.</span><span class="sxs-lookup"><span data-stu-id="76e41-145">MDX expressions are evaluated before the parameters are passed.</span></span> <span data-ttu-id="76e41-146">È inoltre disponibile Generatore MDX, che consente di compilare espressioni MDX in modo semplificato.</span><span class="sxs-lookup"><span data-stu-id="76e41-146">Also, MDX Builder is available to help you build MDX expressions.</span></span>  
  
 <span data-ttu-id="76e41-147">**Proprietà aggiuntive**</span><span class="sxs-lookup"><span data-stu-id="76e41-147">**Additional Properties**</span></span>  
 <span data-ttu-id="76e41-148">Selezionare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="76e41-148">Select the property.</span></span> <span data-ttu-id="76e41-149">Nella tabella seguente vengono riepilogate le proprietà disponibili.</span><span class="sxs-lookup"><span data-stu-id="76e41-149">The following table summarizes the available properties.</span></span>  
  
|<span data-ttu-id="76e41-150">Proprietà</span><span class="sxs-lookup"><span data-stu-id="76e41-150">Property</span></span>|<span data-ttu-id="76e41-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76e41-151">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="76e41-152">**Chiamata**</span><span class="sxs-lookup"><span data-stu-id="76e41-152">**Invocation**</span></span>|<span data-ttu-id="76e41-153">Specifica la modalità di esecuzione dell'azione.</span><span class="sxs-lookup"><span data-stu-id="76e41-153">Specifies how the action is run.</span></span> <span data-ttu-id="76e41-154">L'impostazione predefinita Interattiva specifica che l'azione viene eseguita quando un utente accede a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="76e41-154">Interactive, the default, specifies that the action is run when a user accesses an object.</span></span> <span data-ttu-id="76e41-155">Le impostazioni possibili sono:</span><span class="sxs-lookup"><span data-stu-id="76e41-155">The possible settings are:</span></span><br /><br /> <span data-ttu-id="76e41-156">Batch</span><span class="sxs-lookup"><span data-stu-id="76e41-156">Batch</span></span><br /><br /> <span data-ttu-id="76e41-157">Interattività</span><span class="sxs-lookup"><span data-stu-id="76e41-157">Interactive</span></span><br /><br /> <span data-ttu-id="76e41-158">Su apertura</span><span class="sxs-lookup"><span data-stu-id="76e41-158">On Open</span></span>|  
|<span data-ttu-id="76e41-159">**Applicazione**</span><span class="sxs-lookup"><span data-stu-id="76e41-159">**Application**</span></span>|<span data-ttu-id="76e41-160">Descrive l'applicazione dell'azione.</span><span class="sxs-lookup"><span data-stu-id="76e41-160">Describes the application of the action.</span></span>|  
|<span data-ttu-id="76e41-161">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="76e41-161">**Description**</span></span>|<span data-ttu-id="76e41-162">Descrive l'azione.</span><span class="sxs-lookup"><span data-stu-id="76e41-162">Describes the action.</span></span>|  
|<span data-ttu-id="76e41-163">**Sottotitolo**</span><span class="sxs-lookup"><span data-stu-id="76e41-163">**Caption**</span></span>|<span data-ttu-id="76e41-164">Visualizza una didascalia da associare all'azione.</span><span class="sxs-lookup"><span data-stu-id="76e41-164">Provides a caption that is displayed for the action.</span></span> <span data-ttu-id="76e41-165">Se la didascalia è MDX, specificare `True` per la **Didascalia MDX**.</span><span class="sxs-lookup"><span data-stu-id="76e41-165">If the caption is MDX, specify `True` for **Caption is MDX**.</span></span>|  
|<span data-ttu-id="76e41-166">**Didascalia MDX**</span><span class="sxs-lookup"><span data-stu-id="76e41-166">**Caption is MDX**</span></span>|<span data-ttu-id="76e41-167">Specificare `True` se la didascalia è MDX, in caso contrario specificare `False`.</span><span class="sxs-lookup"><span data-stu-id="76e41-167">Specify `True` if the caption is MDX or `False` if it is not.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="76e41-168">Per definire i tipi di azione HTML e Riga di comando, è necessario utilizzare Analysis Services Scripting Language (ASSL) o la libreria AMO (Analysis Management Objects).</span><span class="sxs-lookup"><span data-stu-id="76e41-168">You must use Analysis Services Scripting Language (ASSL) or Analysis Management Objects (AMO) to define HTML and Command Line action types.</span></span> <span data-ttu-id="76e41-169">Per altre informazioni, vedere [Elemento Action &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/objects/action-element-assl), [Elemento Type &#40;Action&#41; &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/type-element-action-assl) e [Programmazione di oggetti avanzati OLAP in AMO](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-advanced-objects).</span><span class="sxs-lookup"><span data-stu-id="76e41-169">For more information, see [Action Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/objects/action-element-assl), [Type Element &#40;Action&#41; &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/type-element-action-assl), and [Programming AMO OLAP Advanced Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-advanced-objects).</span></span>  
  
## <a name="creating-a-reporting-action"></a><span data-ttu-id="76e41-170">Creazione di un'azione report</span><span class="sxs-lookup"><span data-stu-id="76e41-170">Creating a Reporting Action</span></span>  
 <span data-ttu-id="76e41-171">Il server di report risponde alle richieste basate su URL relative ai report.</span><span class="sxs-lookup"><span data-stu-id="76e41-171">The report server responds to URL-based requests for reports.</span></span> <span data-ttu-id="76e41-172">Per creare un'azione report scegliere **Nuova azione report** dal menu **Cubo**.</span><span class="sxs-lookup"><span data-stu-id="76e41-172">To create a reporting action, on the **Cube** menu, click **New Reporting Action**.</span></span> <span data-ttu-id="76e41-173">Le opzioni seguenti sono specifiche di un'azione report.</span><span class="sxs-lookup"><span data-stu-id="76e41-173">The following options are specific to a reporting action.</span></span>  
  
 <span data-ttu-id="76e41-174">**Server di report**</span><span class="sxs-lookup"><span data-stu-id="76e41-174">**Report Server**</span></span>  
 <span data-ttu-id="76e41-175">Le proprietà descritte nella tabella seguente sono specifiche del server di report.</span><span class="sxs-lookup"><span data-stu-id="76e41-175">The properties described in the following table are specified for the report server.</span></span>  
  
|<span data-ttu-id="76e41-176">Proprietà</span><span class="sxs-lookup"><span data-stu-id="76e41-176">Property</span></span>|<span data-ttu-id="76e41-177">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76e41-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="76e41-178">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="76e41-178">**Server name**</span></span>|<span data-ttu-id="76e41-179">Nome del computer in cui il server di report è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="76e41-179">The name of the computer running report server.</span></span>|  
|<span data-ttu-id="76e41-180">**Percorso server**</span><span class="sxs-lookup"><span data-stu-id="76e41-180">**Server path**</span></span>|<span data-ttu-id="76e41-181">Percorso esposto dal server di report.</span><span class="sxs-lookup"><span data-stu-id="76e41-181">The path exposed by report server.</span></span>|  
|<span data-ttu-id="76e41-182">**Formato report**</span><span class="sxs-lookup"><span data-stu-id="76e41-182">**Report format**</span></span>|<span data-ttu-id="76e41-183">HTML5, HTML3, Excel o PDF.</span><span class="sxs-lookup"><span data-stu-id="76e41-183">HTML5, HTML3, Excel, or PDF.</span></span>|  
  
 <span data-ttu-id="76e41-184">**Parametri (facoltativi)**</span><span class="sxs-lookup"><span data-stu-id="76e41-184">**Parameters (Optional)**</span></span>  
 <span data-ttu-id="76e41-185">I parametri vengono inviati al server come parte della stringa dell'URL quando viene creata l'azione.</span><span class="sxs-lookup"><span data-stu-id="76e41-185">The parameters are sent to the server as part of the URL string when the action is created.</span></span> <span data-ttu-id="76e41-186">Includono **Nome parametro** e **Valore parametro**, che è un'espressione MDX.</span><span class="sxs-lookup"><span data-stu-id="76e41-186">They include **Parameter Name** and **Parameter Value**, which is an MDX expression.</span></span>  
  
 <span data-ttu-id="76e41-187">L'URL del server di report viene creato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="76e41-187">The report server URL is constructed as follows:</span></span>  
  
```  
  
http://  
host  
/  
virtualdirectory  
/Path&  
parametername1  
=  
parametervalue1  
& ...  
```  
  
 <span data-ttu-id="76e41-188">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="76e41-188">For example:</span></span>  
  
```  
http://localhost/ReportServer/Sales/YearlySalesByCategory?rs:Command=Render&Region=West  
```  
  
## <a name="creating-a-drillthrough-action"></a><span data-ttu-id="76e41-189">Creazione di un'azione drill-through</span><span class="sxs-lookup"><span data-stu-id="76e41-189">Creating a Drillthrough Action</span></span>  
 <span data-ttu-id="76e41-190">Un'azione drill-through viene definita da un'azione set di righe, che a sua volta viene restituita all'applicazione client come istruzione drill-through.</span><span class="sxs-lookup"><span data-stu-id="76e41-190">A drillthrough action is defined by a rowset action, which is returned to the client application as a drillthrough statement.</span></span> <span data-ttu-id="76e41-191">La destinazione dell'azione è membro di un gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="76e41-191">The action target is a member of a measure group.</span></span> <span data-ttu-id="76e41-192">Per creare una nuova azione drill-through, scegliere **Nuova azione drill-through** dal menu **Cubo**.</span><span class="sxs-lookup"><span data-stu-id="76e41-192">To create a new drillthrough action, on the **Cube** menu, click **New Drillthrough Action**.</span></span> <span data-ttu-id="76e41-193">Le opzioni seguenti sono specifiche di un'azione drill-through.</span><span class="sxs-lookup"><span data-stu-id="76e41-193">The following options are specific to a drillthrough action:</span></span>  
  
 <span data-ttu-id="76e41-194">**Colonne drill-through**</span><span class="sxs-lookup"><span data-stu-id="76e41-194">**Drillthrough Columns**</span></span>  
 <span data-ttu-id="76e41-195">Selezionare una o più dimensioni e per ogni dimensione selezionare le colonne drill-through restituite all'applicazione client dall'azione.</span><span class="sxs-lookup"><span data-stu-id="76e41-195">Select one or more dimensions and, for each dimension, the drillthrough columns returned to the client application by the action.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e41-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76e41-196">See Also</span></span>  
 [<span data-ttu-id="76e41-197">Cubi nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="76e41-197">Cubes in Multidimensional Models</span></span>](cubes-in-multidimensional-models.md)  
  
  
