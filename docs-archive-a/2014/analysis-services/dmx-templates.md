---
title: Modelli DMX | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2a577e52-821d-4bd3-ba35-075a6be285c9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 79c8615933baf4fa3d80974daae91b4d1c7fa101
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636463"
---
# <a name="dmx-templates"></a><span data-ttu-id="3ab21-102">Modelli DMX</span><span class="sxs-lookup"><span data-stu-id="3ab21-102">DMX Templates</span></span>
  <span data-ttu-id="3ab21-103">I modelli di data mining consentono di compilare rapidamente query sofisticate.</span><span class="sxs-lookup"><span data-stu-id="3ab21-103">The data mining templates help you quickly build sophisticated queries.</span></span> <span data-ttu-id="3ab21-104">Sebbene la sintassi generale per le query DMX sia ben documentata, l'utilizzo dei modelli semplifica la compilazione delle query facendo clic e scegliendo gli argomenti e le origini dati.</span><span class="sxs-lookup"><span data-stu-id="3ab21-104">Although the general syntax for DMX queries is well documented, using the templates makes it easier to build queries by clicking and pointing to arguments and data sources.</span></span>  
  
## <a name="using-the-templates"></a><span data-ttu-id="3ab21-105">Utilizzo dei modelli</span><span class="sxs-lookup"><span data-stu-id="3ab21-105">Using the Templates</span></span>  
  
1.  <span data-ttu-id="3ab21-106">Nel client di data mining per Excel fare clic su **query**.</span><span class="sxs-lookup"><span data-stu-id="3ab21-106">In the Data Mining Client for Excel, click **Query**.</span></span>  
  
2.  <span data-ttu-id="3ab21-107">Nella pagina **iniziale** della procedura guidata fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3ab21-107">On the wizard **Start** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="3ab21-108">Nella pagina **selezionare modello**, fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="3ab21-108">On the page, **Select Model**, click **Advanced**.</span></span>  
  
     <span data-ttu-id="3ab21-109">**Suggerimento:** Se si intende creare una query di stima su un modello, è possibile selezionare prima il modello, quindi fare clic su **Avanzate**per popolare il modello con il nome del modello.</span><span class="sxs-lookup"><span data-stu-id="3ab21-109">**Tip:** If you are going to create a prediction query on a model, you can select the model first, and then click **Advanced**, to prepopulate the template with the model name.</span></span>  
  
4.  <span data-ttu-id="3ab21-110">Nell' **Editor avanzato query di data mining**fare clic su **modelli DMX**e selezionare un modello.</span><span class="sxs-lookup"><span data-stu-id="3ab21-110">In the **Data Mining Advanced Query Editor**, click **DMX Templates**, and select a template.</span></span>  
  
5.  <span data-ttu-id="3ab21-111">Premere INVIO per caricare il modello nel riquadro Query DMX.</span><span class="sxs-lookup"><span data-stu-id="3ab21-111">Press ENTER to load the template into the DMX Query pane.</span></span>  
  
6.  <span data-ttu-id="3ab21-112">Continuare a fare clic sui collegamenti nel modello e quando viene visualizzata la finestra di dialogo, selezionare un output, un modello oppure un parametro appropriato.</span><span class="sxs-lookup"><span data-stu-id="3ab21-112">Continue clicking the links in the template, and as the dialog box appears, select an appropriate output, model, or parameter.</span></span>  
  
     <span data-ttu-id="3ab21-113">Per le query di stima, scegliere il set di dati di input e successivamente eseguire il mapping delle colonne.</span><span class="sxs-lookup"><span data-stu-id="3ab21-113">For prediction queries, choose the input dataset first, and then map the columns.</span></span>  
  
7.  <span data-ttu-id="3ab21-114">Fare clic su **modifica query** per passare alla visualizzazione dell'editor di testo e modificare manualmente la query.</span><span class="sxs-lookup"><span data-stu-id="3ab21-114">Click **Edit Query** to switch to text editor view and manually change the query.</span></span>  
  
     <span data-ttu-id="3ab21-115">Si noti tuttavia che se si passa a una nuova vista durante l'utilizzo dell'editor di query, le informazioni presenti nella vista precedente verranno cancellate.</span><span class="sxs-lookup"><span data-stu-id="3ab21-115">Be aware, however, that if you switch views when working in the query editor, any information that you had in the previous view will be cleared.</span></span> <span data-ttu-id="3ab21-116">Prima di cambiare vista, salvare il lavoro svolto copiando e incollando le istruzioni DMX in un file separato.</span><span class="sxs-lookup"><span data-stu-id="3ab21-116">Before changing views, save your work by copying and pasting the DMX statements to a separate file.</span></span>  
  
8.  <span data-ttu-id="3ab21-117">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="3ab21-117">Click **Finish**.</span></span> <span data-ttu-id="3ab21-118">Nella finestra di dialogo **Scegli destinazione** specificare il percorso in cui si desidera salvare il risultato.</span><span class="sxs-lookup"><span data-stu-id="3ab21-118">In the **Choose Destination** dialog  box, specify where you want the result saved.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="3ab21-119">Se un'istruzione è stata eseguita correttamente, l'istruzione DMX inviata al server viene registrata anche nella finestra di **traccia** .</span><span class="sxs-lookup"><span data-stu-id="3ab21-119">If you executed a statement successfully, the DMX statement that you sent to the server is also recorded in the **Trace** window.</span></span> <span data-ttu-id="3ab21-120">Per ulteriori informazioni sull'utilizzo della funzionalità Trace, vedere [trace &#40;client di data mining per&#41;Excel ](trace-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="3ab21-120">For more information about how to use the Trace feature, see [Trace &#40;Data Mining Client for Excel&#41;](trace-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="3ab21-121">Per ulteriori informazioni su come utilizzare l'editor avanzato query di data mining, vedere [Query &#40;SQL Server componenti aggiuntivi Data mining&#41;](query-sql-server-data-mining-add-ins.md) e [Editor avanzato query di data mining](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="3ab21-121">For more information about how to use the Data Mining Advanced Query Editor, see [Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md) and [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
## <a name="list-of-dmx-templates"></a><span data-ttu-id="3ab21-122">Elenco dei modelli DMX</span><span class="sxs-lookup"><span data-stu-id="3ab21-122">List of DMX Templates</span></span>  
 <span data-ttu-id="3ab21-123">I seguenti modelli DMX sono inclusi nel client di data mining per Excel.</span><span class="sxs-lookup"><span data-stu-id="3ab21-123">The following DMX templates are included in the Data Mining Client for Excel.</span></span>  
  
 <span data-ttu-id="3ab21-124">**Stima**</span><span class="sxs-lookup"><span data-stu-id="3ab21-124">**Prediction**</span></span>  
  
 <span data-ttu-id="3ab21-125">Utilizzare tali modelli per creare query di stima avanzate, comprese le query non supportate dalle procedure guidate nei componenti aggiuntivi, ad esempio le query che utilizzano tabelle annidate o origini dati esterne.</span><span class="sxs-lookup"><span data-stu-id="3ab21-125">Use these templates to create advanced prediction queries, including queries not supported by the wizards in the add-ins, such as queries that use nested tables or external data sources.</span></span>  
  
-   <span data-ttu-id="3ab21-126">Stime filtrate</span><span class="sxs-lookup"><span data-stu-id="3ab21-126">Filtered predictions</span></span>  
  
-   <span data-ttu-id="3ab21-127">Stime nidificate filtrate</span><span class="sxs-lookup"><span data-stu-id="3ab21-127">Filtered nested predictions</span></span>  
  
-   <span data-ttu-id="3ab21-128">Stime nidificate</span><span class="sxs-lookup"><span data-stu-id="3ab21-128">Nested predictions</span></span>  
  
-   <span data-ttu-id="3ab21-129">Stime singleton</span><span class="sxs-lookup"><span data-stu-id="3ab21-129">Singleton predictions</span></span>  
  
-   <span data-ttu-id="3ab21-130">Stime standard</span><span class="sxs-lookup"><span data-stu-id="3ab21-130">Standard predictions</span></span>  
  
-   <span data-ttu-id="3ab21-131">Stime basate su serie temporali</span><span class="sxs-lookup"><span data-stu-id="3ab21-131">Time series predictions</span></span>  
  
-   <span data-ttu-id="3ab21-132">Query di stima TOP</span><span class="sxs-lookup"><span data-stu-id="3ab21-132">TOP prediction query</span></span>  
  
-   <span data-ttu-id="3ab21-133">Query di stima TOP sulla tabella nidificata</span><span class="sxs-lookup"><span data-stu-id="3ab21-133">TOP prediction query on nested table</span></span>  
  
 <span data-ttu-id="3ab21-134">**Creare**</span><span class="sxs-lookup"><span data-stu-id="3ab21-134">**Create**</span></span>  
  
 <span data-ttu-id="3ab21-135">Utilizzare tali modelli per compilare modelli o strutture dei dati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3ab21-135">Use these templates to build custom models or data structures.</span></span> <span data-ttu-id="3ab21-136">Non si è limitati ai modelli supportati dalle procedure guidate: è possibile usare qualsiasi algoritmo data mining supportato dall'istanza di a cui [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] si è connessi, inclusi gli algoritmi plug-in.</span><span class="sxs-lookup"><span data-stu-id="3ab21-136">You are not limited to the models supported by the wizards - you can use any data mining algorithm supported by the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you are connected to, including plug-in algorithms.</span></span>  
  
-   <span data-ttu-id="3ab21-137">Modello di data mining</span><span class="sxs-lookup"><span data-stu-id="3ab21-137">Mining model</span></span>  
  
-   <span data-ttu-id="3ab21-138">Struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="3ab21-138">Mining structure</span></span>  
  
-   <span data-ttu-id="3ab21-139">Struttura di data mining con dati di controllo</span><span class="sxs-lookup"><span data-stu-id="3ab21-139">Mining structure with holdout</span></span>  
  
-   <span data-ttu-id="3ab21-140">Modello temporaneo</span><span class="sxs-lookup"><span data-stu-id="3ab21-140">Temporary model</span></span>  
  
-   <span data-ttu-id="3ab21-141">Struttura temporanea</span><span class="sxs-lookup"><span data-stu-id="3ab21-141">Temporary structure</span></span>  
  
 <span data-ttu-id="3ab21-142">**Proprietà modello**</span><span class="sxs-lookup"><span data-stu-id="3ab21-142">**Model Properties**</span></span>  
  
 <span data-ttu-id="3ab21-143">Utilizzare tali modelli per creare query che ottengono i metadati sul modello e il set di training.</span><span class="sxs-lookup"><span data-stu-id="3ab21-143">Use these templates to create queries that get metadata about the model and the training set.</span></span> <span data-ttu-id="3ab21-144">È inoltre possibile recuperare i dettagli dal contenuto del modello o ottenere un profilo statistico dei dati di training.</span><span class="sxs-lookup"><span data-stu-id="3ab21-144">You can also retrieve details from the model content, or get a statistical profile of the training data.</span></span>  
  
-   <span data-ttu-id="3ab21-145">Contenuto di modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="3ab21-145">Mining model content</span></span>  
  
-   <span data-ttu-id="3ab21-146">Valori di colonna minimo e massimo</span><span class="sxs-lookup"><span data-stu-id="3ab21-146">Minimum and maximum column values</span></span>  
  
-   <span data-ttu-id="3ab21-147">Case di testing/training struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="3ab21-147">Mining structure test/training cases</span></span>  
  
-   <span data-ttu-id="3ab21-148">Valori di colonna discreti</span><span class="sxs-lookup"><span data-stu-id="3ab21-148">Discrete column values</span></span>  
  
 <span data-ttu-id="3ab21-149">**Gestione**</span><span class="sxs-lookup"><span data-stu-id="3ab21-149">**Management**</span></span>  
  
 <span data-ttu-id="3ab21-150">Utilizzare tali modelli per eseguire qualsiasi attività di gestione supportata da DMX, tra cui l'importazione e l'esportazione di modelli, l'eliminazione di modelli e la cancellazione di modelli o strutture dei dati.</span><span class="sxs-lookup"><span data-stu-id="3ab21-150">Use these templates to perform any management task supported by DMX, which includes importing and exporting models, deleting models, and clearing models or data structures.</span></span>  
  
-   <span data-ttu-id="3ab21-151">Cancella modello di data mining</span><span class="sxs-lookup"><span data-stu-id="3ab21-151">Clear mining model</span></span>  
  
-   <span data-ttu-id="3ab21-152">Cancella struttura e modelli</span><span class="sxs-lookup"><span data-stu-id="3ab21-152">Clear structure and models</span></span>  
  
-   <span data-ttu-id="3ab21-153">Cancella struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="3ab21-153">Clear mining structure</span></span>  
  
-   <span data-ttu-id="3ab21-154">Elimina modello di data mining</span><span class="sxs-lookup"><span data-stu-id="3ab21-154">Delete mining model</span></span>  
  
-   <span data-ttu-id="3ab21-155">Elimina struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="3ab21-155">Delete mining structure</span></span>  
  
-   <span data-ttu-id="3ab21-156">Rinomina modello di data mining</span><span class="sxs-lookup"><span data-stu-id="3ab21-156">Rename mining model</span></span>  
  
-   <span data-ttu-id="3ab21-157">Rinomina struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="3ab21-157">Rename mining structure</span></span>  
  
-   <span data-ttu-id="3ab21-158">Training modello di data mining</span><span class="sxs-lookup"><span data-stu-id="3ab21-158">Train mining model</span></span>  
  
-   <span data-ttu-id="3ab21-159">Training struttura di data mining nidificata</span><span class="sxs-lookup"><span data-stu-id="3ab21-159">Train nested mining structure</span></span>  
  
-   <span data-ttu-id="3ab21-160">Training struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="3ab21-160">Train mining structure</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="3ab21-161">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ab21-161">Requirements</span></span>  
 <span data-ttu-id="3ab21-162">A seconda del modello utilizzato, potrebbero essere necessarie autorizzazioni amministrative per l'accesso al server [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="3ab21-162">Depending on which template you are using, you might need administrative permissions to access the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server and execute the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab21-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ab21-163">See Also</span></span>  
 [<span data-ttu-id="3ab21-164">Creazione di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="3ab21-164">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
