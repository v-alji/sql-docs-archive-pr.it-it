---
title: 'Passaggio 2: Aggiunta e configurazione di funzionalità di registrazione | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 56105f3f-e500-4669-8c8e-acf434527727
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0f2cdce6f34a19e22830d357d20f5d99cff8c14f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715563"
---
# <a name="step-2-adding-and-configuring-logging"></a><span data-ttu-id="e5010-102">Passaggio 2: Aggiunta e configurazione di funzionalità di registrazione</span><span class="sxs-lookup"><span data-stu-id="e5010-102">Step 2: Adding and Configuring Logging</span></span>
  <span data-ttu-id="e5010-103">In questa attività verrà abilitata la registrazione per il flusso di dati del pacchetto Lesson 3.dtsx.</span><span class="sxs-lookup"><span data-stu-id="e5010-103">In this task, you will enable logging for the data flow in the Lesson 3.dtsx package.</span></span> <span data-ttu-id="e5010-104">Successivamente un provider di log per file di testo verrà configurato in modo da registrare gli eventi PipelineExecutionPlan e PipelineExecuteTrees.</span><span class="sxs-lookup"><span data-stu-id="e5010-104">Then, you will configure a Text File log provider to log the PipelineExecutionPlan and PipelineExecuteTrees events.</span></span> <span data-ttu-id="e5010-105">Il provider di log per file di testo crea log facili da visualizzare e da spostare.</span><span class="sxs-lookup"><span data-stu-id="e5010-105">The Text Files log provider creates logs that are easy to view and easily transportable.</span></span> <span data-ttu-id="e5010-106">La semplicità di questi file di log li rende particolarmente utili nella fase di test di base di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e5010-106">The simplicity of these log files makes these files especially useful during the basic testing phase of a package.</span></span> <span data-ttu-id="e5010-107">Le voci di log possono essere visualizzate anche nella finestra Registra eventi di Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5010-107">You can also view the log entries in the Log Events window of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
### <a name="to-add-logging-to-the-package"></a><span data-ttu-id="e5010-108">Per aggiungere le funzionalità di registrazione al pacchetto</span><span class="sxs-lookup"><span data-stu-id="e5010-108">To add logging to the package</span></span>  
  
1.  <span data-ttu-id="e5010-109">Scegliere **Registrazione** dal menu **SSIS**.</span><span class="sxs-lookup"><span data-stu-id="e5010-109">On the **SSIS** menu, click **Logging**.</span></span>  
  
2.  <span data-ttu-id="e5010-110">Nel riquadro **Contenitori** della finestra di dialogo **Configura log SSIS** verificare che sia selezionato l'oggetto in prima posizione, che rappresenta il pacchetto della lezione 3.</span><span class="sxs-lookup"><span data-stu-id="e5010-110">In the **Configure SSIS Logs** dialog box, in the **Containers** pane, make sure that the topmost object, which represents the Lesson 3 package, is selected.</span></span>  
  
3.  <span data-ttu-id="e5010-111">Nella casella **Tipo provider** della scheda **Provider e log** selezionare **Provider di log SSIS per file di testo**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e5010-111">On the **Providers and Logs** tab, in the **Provider type** box, select **SSIS log provider for Text files**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="e5010-112">Integration Services aggiunge un nuovo provider di log file di testo al pacchetto con il nome predefinito **provider di log SSIS per file di testo**.</span><span class="sxs-lookup"><span data-stu-id="e5010-112">Integration Services adds a new Text File log provider to the package with the default name **SSIS log provider for text files**.</span></span> <span data-ttu-id="e5010-113">È ora possibile configurare il nuovo provider di log.</span><span class="sxs-lookup"><span data-stu-id="e5010-113">You can now configure the new log provider.</span></span>  
  
4.  <span data-ttu-id="e5010-114">Nella colonna **nome** Digitare `Lesson 3 Log File` .</span><span class="sxs-lookup"><span data-stu-id="e5010-114">In the **Name** column, type `Lesson 3 Log File`.</span></span>  
  
5.  <span data-ttu-id="e5010-115">Facoltativamente, modificare la **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="e5010-115">Optionally, modify the **Description**.</span></span>  
  
6.  <span data-ttu-id="e5010-116">Nella colonna **Configurazione** fare clic su **\<New Connection>** per specificare la destinazione nella quale verranno scritte le informazioni sulla registrazione.</span><span class="sxs-lookup"><span data-stu-id="e5010-116">In the **Configuration** column, click **\<New Connection>** to specify the destination to which the log information is written.</span></span>  
  
     <span data-ttu-id="e5010-117">Nella finestra di dialogo **Editor gestione connessione file** per **Tipo di utilizzo**selezionare **Crea file**e quindi fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="e5010-117">In the **File Connection Manager Editor** dialog box, for **Usage type**, select **Create file**, and then click **Browse**.</span></span> <span data-ttu-id="e5010-118">Per impostazione predefinita, la finestra di dialogo **Seleziona file** apre la cartella di progetto; tuttavia è possibile salvare le informazioni sulla registrazione in qualsiasi posizione.</span><span class="sxs-lookup"><span data-stu-id="e5010-118">By default, the **Select File** dialog box opens the project folder, but you can save log information to any location.</span></span>  
  
7.  <span data-ttu-id="e5010-119">Nella finestra di dialogo **Seleziona file** Digitare, nella casella **nome file** `TutorialLog.log` , quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="e5010-119">In the **Select File** dialog box, in the **File name** box type `TutorialLog.log`, and click **Open**.</span></span>  
  
8.  <span data-ttu-id="e5010-120">Fare clic su **OK** per chiudere la finestra di dialogo **Editor gestione connessione file** .</span><span class="sxs-lookup"><span data-stu-id="e5010-120">Click **OK** to close the **File Connection Manager Editor** dialog box.</span></span>  
  
9. <span data-ttu-id="e5010-121">Nel riquadro **Contenitori** espandere tutti i nodi della gerarchia del contenitore del pacchetto e quindi deselezionare tutte le caselle di controllo, compresa **Extract Sample Currency Data** .</span><span class="sxs-lookup"><span data-stu-id="e5010-121">In the **Containers** pane, expand all nodes of the package container hierarchy, and then clear all check boxes, including the **Extract Sample Currency Data** check box.</span></span> <span data-ttu-id="e5010-122">Selezionare quindi la casella di controllo **Extract Sample Currency Data** per ottenere solo gli eventi relativi a tale nodo.</span><span class="sxs-lookup"><span data-stu-id="e5010-122">Now select the check box for **Extract Sample Currency Data** to get only the events for this node.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e5010-123"> Se la casella di controllo **Extract Sample Currency Data** risulta non disponibile anziché selezionata, l'attività utilizza le impostazioni del log del contenitore padre e non è possibile attivare gli eventi di log specifici dell'attività.</span><span class="sxs-lookup"><span data-stu-id="e5010-123">If the state of the **Extract Sample Currency Data** check box is dimmed instead of selected, the task uses the log settings of the parent container and you cannot enable the log events that are specific to the task.</span></span>  
  
10. <span data-ttu-id="e5010-124">Nella colonna **Eventi** della scheda **Dettagli** selezionare gli eventi **PipelineExecutionPlan** e **PipelineExecutionTrees** .</span><span class="sxs-lookup"><span data-stu-id="e5010-124">On the **Details** tab, in the **Events** column, select the **PipelineExecutionPlan** and **PipelineExecutionTrees** events.</span></span>  
  
11. <span data-ttu-id="e5010-125">Fare clic su **Avanzate** per controllare i dettagli che verranno scritti nel log per ogni evento.</span><span class="sxs-lookup"><span data-stu-id="e5010-125">Click **Advanced** to review the details that the log provider will write to the log for each event.</span></span> <span data-ttu-id="e5010-126">Per impostazione predefinita, tutte le categorie delle informazioni vengono automaticamente selezionate per gli eventi specificati.</span><span class="sxs-lookup"><span data-stu-id="e5010-126">By default, all information categories are automatically selected for the events you specify.</span></span>  
  
12. <span data-ttu-id="e5010-127">Fare clic su **Standard** per nascondere le categorie delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="e5010-127">Click **Basic** to hide the information categories.</span></span>  
  
13. <span data-ttu-id="e5010-128">Nella colonna **nome** della scheda **provider e log** selezionare `Lesson 3 Log File` .</span><span class="sxs-lookup"><span data-stu-id="e5010-128">On the **Provider and Logs** tab, in the **Name** column, select `Lesson 3 Log File`.</span></span> <span data-ttu-id="e5010-129">Dopo aver creato un provider di log per il pacchetto, è possibile disabilitare temporaneamente la registrazione senza la necessità di eliminarlo e ricrearlo.</span><span class="sxs-lookup"><span data-stu-id="e5010-129">Once you have created a log provider for your package, you can optionally deselect it to temporarily turn off logging, without having to delete and re-create a log provider.</span></span>  
  
14. <span data-ttu-id="e5010-130">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5010-130">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e5010-131">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e5010-131">Next Steps</span></span>  
 [<span data-ttu-id="e5010-132">Passaggio 3: Test del pacchetto creato nella lezione 3 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="e5010-132">Step 3: Testing the Lesson 3 Tutorial Package</span></span>](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
  
