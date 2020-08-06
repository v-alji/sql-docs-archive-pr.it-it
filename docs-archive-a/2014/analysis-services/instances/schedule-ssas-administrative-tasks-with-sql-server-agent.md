---
title: Pianificare le attività amministrative di SSAS con SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2d1484b3-51d9-48a0-93d2-0c3e4ed22b87
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c78fa5fcebc0589ba863163b93ad2d10731b75a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716928"
---
# <a name="schedule-ssas-administrative-tasks-with-sql-server-agent"></a><span data-ttu-id="ecbed-102">Pianificare attività amministrative SSAS con SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="ecbed-102">Schedule SSAS Administrative Tasks with SQL Server Agent</span></span>
  <span data-ttu-id="ecbed-103">Usando il servizio SQL Server Agent, è possibile pianificare l'esecuzione delle attività amministrative di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] nell'ordine e agli orari necessari.</span><span class="sxs-lookup"><span data-stu-id="ecbed-103">Using the SQL Server Agent service, you can schedule [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] administrative tasks to run in the order and times that you need.</span></span> <span data-ttu-id="ecbed-104">Le attività pianificate consentono di automatizzare processi eseguiti in cicli regolari o prevedibili.</span><span class="sxs-lookup"><span data-stu-id="ecbed-104">Scheduled tasks help you automate processes that run on regular or predictable cycles.</span></span> <span data-ttu-id="ecbed-105">È possibile pianificare l'esecuzione di attività amministrative, ad esempio l'elaborazione di cubi, nei periodi in cui l'attività aziendale è ridotta.</span><span class="sxs-lookup"><span data-stu-id="ecbed-105">You can schedule administrative tasks, such as cube processing, to run during times of slow business activity.</span></span> <span data-ttu-id="ecbed-106">È inoltre possibile determinare l'ordine di esecuzione delle attività creando passaggi di processo in un processo di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="ecbed-106">You can also determine the order in which tasks run by creating job steps within a SQL Server Agent job.</span></span> <span data-ttu-id="ecbed-107">È possibile ad esempio elaborare un cubo ed eseguirne quindi un backup.</span><span class="sxs-lookup"><span data-stu-id="ecbed-107">For example, you can process a cube and then perform a backup of the cube.</span></span>  
  
 <span data-ttu-id="ecbed-108">I passaggi di processo consentono di controllare il flusso dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ecbed-108">Job steps give you control over flow of execution.</span></span> <span data-ttu-id="ecbed-109">Se uno dei processi ha esito negativo, è possibile configurare SQL Server Agent per continuare a eseguire le attività rimanenti o per arrestare l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ecbed-109">If one job fails, you can configure SQL Server Agent to continue to run the remaining tasks or to stop execution.</span></span> <span data-ttu-id="ecbed-110">È inoltre possibile configurare SQL Server Agent per l'invio di notifiche relative all'esito positivo o negativo dell'esecuzione di un processo.</span><span class="sxs-lookup"><span data-stu-id="ecbed-110">You can also configure SQL Server Agent to send notifications about the success or failure of job execution.</span></span>  
  
 <span data-ttu-id="ecbed-111">In questo argomento è disponibile una procedura dettagliata che illustra due modalità di utilizzo di SQL Server Agent per eseguire script XMLA.</span><span class="sxs-lookup"><span data-stu-id="ecbed-111">This topic is a walkthrough that shows two ways of using SQL Server Agent to run XMLA script.</span></span> <span data-ttu-id="ecbed-112">Nel primo esempio viene dimostrato come pianificare l'elaborazione di una singola dimensione.</span><span class="sxs-lookup"><span data-stu-id="ecbed-112">The first example demonstrates how to schedule processing of a single dimension.</span></span> <span data-ttu-id="ecbed-113">Nel secondo esempio viene illustrato come combinare attività di elaborazione in uno singolo script eseguito in una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="ecbed-113">Example two shows how to combine processing tasks into a single script that runs on a schedule.</span></span> <span data-ttu-id="ecbed-114">Per completare la procedura dettagliata, è necessario soddisfare i requisiti riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="ecbed-114">To complete this walkthrough, you will need to meet the following prerequisites.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ecbed-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ecbed-115">Prerequisites</span></span>  
 <span data-ttu-id="ecbed-116">È necessario che il servizio SQL Server Agent sia installato.</span><span class="sxs-lookup"><span data-stu-id="ecbed-116">SQL Server Agent service must be installed.</span></span>  
  
 <span data-ttu-id="ecbed-117">Per impostazione predefinita, i processi vengono eseguiti con l'account del servizio.</span><span class="sxs-lookup"><span data-stu-id="ecbed-117">By default, jobs run under the service account.</span></span> <span data-ttu-id="ecbed-118">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] l'account predefinito per SQL Server Agent è NT Service\SQLAgent $ \<instancename> .</span><span class="sxs-lookup"><span data-stu-id="ecbed-118">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the default account for SQL Server Agent is NT Service\SQLAgent$\<instancename>.</span></span> <span data-ttu-id="ecbed-119">Per eseguire un backup o un'attività di elaborazione, è necessario utilizzare un account amministratore di sistema nell'istanza di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ecbed-119">To perform a backup or processing task, this account must be a system administrator on the Analysis Services instance.</span></span> <span data-ttu-id="ecbed-120">Per ulteriori informazioni, vedere [concedere le autorizzazioni di amministratore del Server &#40;Analysis Services&#41;](grant-server-admin-rights-to-an-analysis-services-instance.md).</span><span class="sxs-lookup"><span data-stu-id="ecbed-120">For more information, see [Grant Server Administrator Permissions &#40;Analysis Services&#41;](grant-server-admin-rights-to-an-analysis-services-instance.md).</span></span>  
  
 <span data-ttu-id="ecbed-121">È consigliabile utilizzare un database di test.</span><span class="sxs-lookup"><span data-stu-id="ecbed-121">You should also have a test database to work with.</span></span> <span data-ttu-id="ecbed-122">È possibile distribuire il database di esempio multidimensionale AdventureWorks o un progetto dell'esercitazione multidimensionale di Analysis Services da utilizzare in questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="ecbed-122">You can deploy the AdventureWorks multidimensional sample database or a project from the Analysis Services multidimensional tutorial to use in this walkthrough.</span></span> <span data-ttu-id="ecbed-123">Per altre informazioni, vedere [Installare dati di esempio e progetti per l'esercitazione di modellazione multidimensionale di Analysis Services](../install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="ecbed-123">For more information, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](../install-sample-data-and-projects.md).</span></span>  
  
## <a name="example-1-processing-a-dimension-in-a-scheduled-task"></a><span data-ttu-id="ecbed-124">Esempio 1: Elaborazione di una dimensione in un'attività pianificata</span><span class="sxs-lookup"><span data-stu-id="ecbed-124">Example 1: Processing a dimension in a scheduled task</span></span>  
 <span data-ttu-id="ecbed-125">In questo esempio viene illustrato come creare e pianificare un processo che elabora una dimensione.</span><span class="sxs-lookup"><span data-stu-id="ecbed-125">This example demonstrates how to create and schedule a job that processes a dimension.</span></span>  
  
 <span data-ttu-id="ecbed-126">Un'attività pianificata di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] è uno script XMLA incorporato in un processo di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="ecbed-126">An [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] scheduled task is an XMLA script that is embedded into a SQL Server Agent job.</span></span> <span data-ttu-id="ecbed-127">L'esecuzione di questo processo è pianificata per l'esecuzione negli orari e con la frequenza desiderati.</span><span class="sxs-lookup"><span data-stu-id="ecbed-127">This job is scheduled to run at desired times and frequency.</span></span> <span data-ttu-id="ecbed-128">Poiché SQL Server Agent è un componente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], per la creazione e la pianificazione di un'attività amministrativa verranno utilizzati sia il Motore di database che [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ecbed-128">Because the SQL Server Agent is part of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you work with both the Database Engine and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to create and schedule an administrative task.</span></span>  
  
###  <a name="create-a-script-for-processing-a-dimension-in-a-sql-server-agent-job"></a><a name="bkmk_CreateScript"></a><span data-ttu-id="ecbed-129">Creare uno script per l'elaborazione di una dimensione in un processo di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="ecbed-129">Create a script for processing a dimension in a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="ecbed-130">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]connettersi a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecbed-130">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="ecbed-131">Aprire una cartella di database e individuare una dimensione.</span><span class="sxs-lookup"><span data-stu-id="ecbed-131">Open a database folder and find a dimension.</span></span> <span data-ttu-id="ecbed-132">Fare clic con il pulsante destro del mouse sulla dimensione e scegliere **Elabora**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-132">Right-click the dimension and select **Process**.</span></span>  
  
2.  <span data-ttu-id="ecbed-133">Nella finestra di dialogo \*\*\*\* di elaborazione, in **Elenco oggetti** verificare che l’opzione per la colonna **Opzioni elaborazione**sia **Elaborazione completa**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-133">In the **Process Dimension** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span> <span data-ttu-id="ecbed-134">In caso contrario, in **Opzioni elaborazione**fare clic sull'opzione e quindi selezionare **Elaborazione completa** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="ecbed-134">If it is not, under **Process Options**, click the option, and then select **Process Full** from the drop-down list.</span></span>  
  
3.  <span data-ttu-id="ecbed-135">Fare clic su **Script**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-135">Click **Script**.</span></span>  
  
     <span data-ttu-id="ecbed-136">Questo passaggio apre una finestra **Query XML** contenente lo script XMLA che elabora la dimensione.</span><span class="sxs-lookup"><span data-stu-id="ecbed-136">This step opens an **XML Query** window that contains the XMLA script that processes the dimension.</span></span>  
  
4.  <span data-ttu-id="ecbed-137">Nella finestra di dialogo **Elaborazione dimensione** fare clic su **Annulla** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ecbed-137">In the **Process Dimension** dialog box, click **Cancel** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="ecbed-138">Nella finestra **Query XMLA** selezionare lo script XMLA, fare clic con il pulsante destro del mouse su tale script e scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-138">In the **XMLA Query** window, highlight the XMLA script, right-click the highlighted script, and select **Copy**.</span></span>  
  
     <span data-ttu-id="ecbed-139">In questo passaggio lo script XMLA viene copiato negli Appunti di Windows.</span><span class="sxs-lookup"><span data-stu-id="ecbed-139">This step copies the XMLA script to the Windows Clipboard.</span></span> <span data-ttu-id="ecbed-140">È possibile lasciare lo script XMLA negli Appunti o incollarlo nel Blocco note o un altro editor di testo.</span><span class="sxs-lookup"><span data-stu-id="ecbed-140">You can leave the XMLA script in the Clipboard or paste it into Notepad or another text editor.</span></span> <span data-ttu-id="ecbed-141">Di seguito è riportato un esempio di script XMLA.</span><span class="sxs-lookup"><span data-stu-id="ecbed-141">The following is an example of the XMLA script.</span></span>  
  
    ```  
    <Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
     <Parallel>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <DimensionID>Dim Account</DimensionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
     </Parallel>  
    </Batch>  
    ```  
  
###  <a name="create-and-schedule-the-dimension-processing-job"></a><a name="bkmk_ProcessJob"></a><span data-ttu-id="ecbed-142">Creare e pianificare il processo di elaborazione della dimensione</span><span class="sxs-lookup"><span data-stu-id="ecbed-142">Create and schedule the dimension processing job</span></span>  
  
1.  <span data-ttu-id="ecbed-143">Connettersi a un'istanza del motore di database e quindi aprire Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="ecbed-143">Connect to an instance of the Database Engine and then open Object Explorer.</span></span>  
  
2.  <span data-ttu-id="ecbed-144">Espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-144">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="ecbed-145">Fare clic con il pulsante destro del mouse su **Processi** e selezionare **Nuovo processo**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-145">Right-click **Jobs** and select **New Job**.</span></span>  
  
4.  <span data-ttu-id="ecbed-146">Nella finestra di dialogo **Nuovo processo** immettere il nome del processo nella casella **Nome**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-146">In the **New Job** dialog box, enter a job name in **Name**.</span></span>  
  
5.  <span data-ttu-id="ecbed-147">In **Selezione pagina**selezionare **Passaggi**e quindi fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-147">Under **Select a page**, select **Steps**, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="ecbed-148">Nella finestra di dialogo **Nuovo passaggio di processo** immettere il nome del passaggio nella casella **Nome passaggio**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-148">In the **New Job Step** dialog box, enter a step name in **Step Name**.</span></span>  
  
7.  <span data-ttu-id="ecbed-149">In **Server**Digitare **localhost** per un'istanza predefinita di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e \*\*localhost \\ \*\* \<*instance name*> per un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="ecbed-149">In **Server**, type **localhost** for a default instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and **localhost\\**\<*instance name*> for a named instance.</span></span>  
  
     <span data-ttu-id="ecbed-150">Se si eseguirà il processo da un computer remoto, utilizzare il nome del server e il nome dell'istanza in cui il processo verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="ecbed-150">If you will be running the job from a remote computer, use the server name and instance name where the job will run.</span></span> <span data-ttu-id="ecbed-151">Utilizzare il formato \<*server name*> per un'istanza predefinita e il \<*server name*> \\ < *nome dell'istanza*> per un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="ecbed-151">Use the format \<*server name*> for a default instance, and \<*server name*>\\<*instance name*> for a named instance.</span></span>  
  
8.  <span data-ttu-id="ecbed-152">In **Tipo**selezionare **Comando di SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-152">In **Type**, select **SQL Server Analysis Services Command**.</span></span>  
  
9. <span data-ttu-id="ecbed-153">In **Comando**fare clic con il pulsante destro del mouse e scegliere **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-153">In **Command**, right-click and select **Paste**.</span></span> <span data-ttu-id="ecbed-154">Lo script XMLA generato nel passaggio precedente verrà visualizzato nella finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="ecbed-154">The XMLA script that you generated in the previous step should appear in the command window.</span></span>  
  
10. <span data-ttu-id="ecbed-155">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-155">Click **OK**.</span></span>  
  
11. <span data-ttu-id="ecbed-156">In **Selezione pagina**fare clic su **Pianificazioni**e quindi su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-156">Under **Select a page**, click **Schedules**, and then click **New**.</span></span>  
  
12. <span data-ttu-id="ecbed-157">Nella finestra di dialogo **Nuova pianificazione processo** immettere il nome della pianificazione nella casella **Nome**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-157">In the **New Job Schedule** dialog box, enter a schedule name in **Name**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ecbed-158">In questo passaggio viene creata una pianificazione per domenica alle 12.00 AM.</span><span class="sxs-lookup"><span data-stu-id="ecbed-158">This step creates a schedule for Sunday at 12:00 AM.</span></span> <span data-ttu-id="ecbed-159">Nel passaggio successivo verrà illustrato come eseguire manualmente il processo.</span><span class="sxs-lookup"><span data-stu-id="ecbed-159">The next step shows you how to manually execute the job.</span></span> <span data-ttu-id="ecbed-160">È inoltre possibile specificare una pianificazione che esegue il processo mentre viene monitorato.</span><span class="sxs-lookup"><span data-stu-id="ecbed-160">You can also specify a schedule that executes the job when you are monitoring it.</span></span>  
  
13. <span data-ttu-id="ecbed-161">Nella finestra di dialogo **Nuovo processo** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-161">In the **New Job** dialog box, click **OK**.</span></span>  
  
14. <span data-ttu-id="ecbed-162">In **Esplora oggetti**espandere **Processi**, fare clic con il pulsante destro del mouse sul processo creato e quindi selezionare **Inizia processo al passaggio**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-162">In **Object Explorer**, expand **Jobs**, right-click the job you created, and then select **Start Job at Step**.</span></span>  
  
     <span data-ttu-id="ecbed-163">Poiché il processo include un solo passaggio, verrà eseguito immediatamente.</span><span class="sxs-lookup"><span data-stu-id="ecbed-163">Because the job has only one step, the job executes immediately.</span></span> <span data-ttu-id="ecbed-164">Se il processo è costituito da più di un passaggio, è possibile selezionare quello da cui dovrà iniziare il processo.</span><span class="sxs-lookup"><span data-stu-id="ecbed-164">If the job contains more than one step, you can select the step at which the job should start.</span></span>  
  
15. <span data-ttu-id="ecbed-165">Al termine del processo fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-165">When the job finishes, click **Close**.</span></span>  
  
## <a name="example-2-batch-processing-a-dimension-and-a-partition-in-a-scheduled-task"></a><span data-ttu-id="ecbed-166">Esempio 2: Elaborazione batch di una dimensione e una partizione in un'attività pianificata</span><span class="sxs-lookup"><span data-stu-id="ecbed-166">Example 2: Batch processing a dimension and a partition in a scheduled task</span></span>  
 <span data-ttu-id="ecbed-167">Le procedure in questo esempio dimostrano come creare e pianificare un processo per l'elaborazione batch di una dimensione database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e contemporaneamente per l'elaborazione di una partizione del cubo che dipende dalla dimensione per l'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="ecbed-167">The procedures in this example demonstrate how to create and schedule a job that batch processes an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database dimension, and at the same time to process a  cube partition that depends on the dimension for aggregation.</span></span> <span data-ttu-id="ecbed-168">Per altre informazioni sull'elaborazione batch di oggetti di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vedere [Elaborazione batch &#40;Analysis Services&#41;](../multidimensional-models/batch-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ecbed-168">For more information about batch processing of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Batch Processing &#40;Analysis Services&#41;](../multidimensional-models/batch-processing-analysis-services.md).</span></span>  
  
###  <a name="create-a-script-for-batch-processing-a-dimension-and-partition-in-a-sql-server-agent-job"></a><a name="bkmk_BatchProcess"></a><span data-ttu-id="ecbed-169">Creare uno script per l'elaborazione batch di una dimensione e una partizione in un processo di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="ecbed-169">Create a script for batch processing a dimension and partition in a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="ecbed-170">Usando lo stesso database, espandere **Dimensioni**, fare clic con il pulsante destro del mouse sulla dimensione **Customer** e scegliere **Elabora**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-170">Using the same database, expand **Dimensions**, right-click the **Customer** dimension, and select **Process**.</span></span>  
  
2.  <span data-ttu-id="ecbed-171">Nella finestra di dialogo **Elaborazione dimensione** , nella colonna **Opzioni elaborazione** di **Elenco oggetti**, verificare che l'opzione per la colonna sia **Elaborazione completa**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-171">In the **Process Dimension** dialog box, in **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span>  
  
3.  <span data-ttu-id="ecbed-172">Fare clic su **Script**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-172">Click **Script**.</span></span>  
  
     <span data-ttu-id="ecbed-173">Questo passaggio apre una finestra **Query XML** contenente lo script XMLA che elabora la dimensione.</span><span class="sxs-lookup"><span data-stu-id="ecbed-173">This step opens an **XML Query** window that contains the XMLA script that processes the dimension.</span></span>  
  
4.  <span data-ttu-id="ecbed-174">Nella finestra di dialogo **Elaborazione dimensione** fare clic su **Annulla** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ecbed-174">In the **Process Dimension** dialog box, click **Cancel** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="ecbed-175">Espandere **Cubi**, **Adventure Works**, **Gruppi di misure**, **Internet Sales**e **Partizioni**, fare clic con il pulsante destro del mouse sull'ultima partizione nell'elenco e quindi scegliere **Elabora**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-175">Expand **Cubes**, expand **Adventure Works**, expand **Measure Groups**, expand **Internet Sales**, expand **Partitions**, right-click the last partition in the list, and then select **Process**.</span></span>  
  
6.  <span data-ttu-id="ecbed-176">Nella finestra di dialogo **Elaborazione partizione** , nella colonna **Opzioni elaborazione** di **Elenco oggetti**, verificare che l'opzione per la colonna sia **Elaborazione completa**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-176">In the **Process Partition** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span>  
  
7.  <span data-ttu-id="ecbed-177">Fare clic su **Script**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-177">Click **Script**.</span></span>  
  
     <span data-ttu-id="ecbed-178">Questo passaggio apre una seconda finestra **Query XML** contenente lo script XMLA che elabora la partizione.</span><span class="sxs-lookup"><span data-stu-id="ecbed-178">This step opens a second **XML Query** window that contains the XMLA script that processes the partition.</span></span>  
  
8.  <span data-ttu-id="ecbed-179">Nella finestra di dialogo **Elabora partizione** fare clic su **Annulla** per chiudere l'editor.</span><span class="sxs-lookup"><span data-stu-id="ecbed-179">In the **Process Partition** dialog box, click **Cancel** to close the editor.</span></span>  
  
     <span data-ttu-id="ecbed-180">In questa fase è necessario unire i due script e assicurarsi che la dimensione venga elaborata per prima.</span><span class="sxs-lookup"><span data-stu-id="ecbed-180">At this point you must merge the two scripts, and ensure that the dimension is processed first.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="ecbed-181">Se la partizione viene elaborata per prima, la successiva elaborazione della dimensione farà sì che la partizione rimanga in uno stato non elaborato.</span><span class="sxs-lookup"><span data-stu-id="ecbed-181">If the partition is processed first, the subsequent dimension processing causes the partition to become unprocessed.</span></span> <span data-ttu-id="ecbed-182">La partizione richiederebbe quindi una seconda elaborazione per raggiungere uno stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="ecbed-182">The partition would then require a second processing to reach a processed state.</span></span>  
  
9. <span data-ttu-id="ecbed-183">Nella finestra **Query XMLA** contenente lo script XMLA che elabora la partizione selezionare il codice all'interno dei tag `Batch` e `Parallel` , fare clic con il pulsante destro del mouse su tale script e scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-183">In the **XMLA Query** window that contains the XMLA script that processes the partition, highlight the code inside the `Batch` and `Parallel` tags, right-click the highlighted script, and select **Copy**.</span></span>  
  
    ```  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID> Adventure Works DW Multidimensional</DatabaseID>  
          <CubeID>Adventure Works</CubeID>  
          <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
          <PartitionID> Internet_Sales_2004</PartitionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
    ```  
  
10. <span data-ttu-id="ecbed-184">Aprire la finestra **Query XMLA** contenente lo script XMLA che elabora la dimensione.</span><span class="sxs-lookup"><span data-stu-id="ecbed-184">Open the **XMLA Query** window that contains the XMLA script that processes the dimension.</span></span> <span data-ttu-id="ecbed-185">Fare clic con il pulsante destro del mouse all'interno dello script a sinistra del tag `</Process>` e scegliere **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-185">Right-click within the script to the left of the `</Process>` tag and select **Paste**.</span></span>  
  
     <span data-ttu-id="ecbed-186">Nell'esempio seguente viene illustrato lo script XMLA modificato.</span><span class="sxs-lookup"><span data-stu-id="ecbed-186">The following example shows the revised XMLA script.</span></span>  
  
    ```  
    <Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
     <Parallel>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <DimensionID>Dim Customer</DimensionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <CubeID>Adventure Works</CubeID>  
          <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
          <PartitionID>Internet_Sales_2004</PartitionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
     </Parallel>  
    </Batch>  
    ```  
  
11. <span data-ttu-id="ecbed-187">Selezionare lo script XMLA modificato, fare clic con il pulsante destro del mouse su tale script e scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-187">Highlight the revised XMLA script, right-click the highlighted script, and select **Copy.**</span></span>  
  
12. <span data-ttu-id="ecbed-188">In questo passaggio lo script XMLA viene copiato negli Appunti di Windows.</span><span class="sxs-lookup"><span data-stu-id="ecbed-188">This step copies the XMLA script to the Windows Clipboard.</span></span> <span data-ttu-id="ecbed-189">È possibile lasciare lo script XMLA negli Appunti, salvarlo su un file o incollarlo nel Blocco note o un altro editor di testo.</span><span class="sxs-lookup"><span data-stu-id="ecbed-189">You can leave the XMLA script in the Clipboard, save it to a file, or paste it into Notepad or another text editor.</span></span>  
  
###  <a name="create-and-schedule-the-batch-processing-job"></a><a name="bkmk_Scheduling"></a><span data-ttu-id="ecbed-190">Creare e pianificare il processo di elaborazione batch</span><span class="sxs-lookup"><span data-stu-id="ecbed-190">Create and schedule the batch processing job</span></span>  
  
1.  <span data-ttu-id="ecbed-191">Connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]e quindi aprire Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="ecbed-191">Connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then open Object Explorer.</span></span>  
  
2.  <span data-ttu-id="ecbed-192">Espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-192">Expand **SQL Server Agent**.</span></span> <span data-ttu-id="ecbed-193">Avviare il servizio, se non è già in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ecbed-193">Start the service if is not running.</span></span>  
  
3.  <span data-ttu-id="ecbed-194">Fare clic con il pulsante destro del mouse su **Processi** e selezionare **Nuovo processo**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-194">Right-click **Jobs** and select **New Job**.</span></span>  
  
4.  <span data-ttu-id="ecbed-195">Nella finestra di dialogo **Nuovo processo** immettere il nome del processo nella casella **Nome**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-195">In the **New Job** dialog box, enter a job name in **Name**.</span></span>  
  
5.  <span data-ttu-id="ecbed-196">In **Passaggi**fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-196">In **Steps**, click **New**.</span></span>  
  
6.  <span data-ttu-id="ecbed-197">Nella finestra di dialogo **Nuovo passaggio di processo** immettere il nome del passaggio nella casella **Nome passaggio**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-197">In the **New Job Step** dialog box, enter a step name in **Step Name**.</span></span>  
  
7.  <span data-ttu-id="ecbed-198">In **Tipo**selezionare **Comando di SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-198">In **Type**, select **SQL Server Analysis Services Command**.</span></span>  
  
8.  <span data-ttu-id="ecbed-199">In **Esegui come**selezionare **Account del servizio SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-199">In **Run as**, select the **SQL Server Agent Service Account**.</span></span> <span data-ttu-id="ecbed-200">Tenere presente, secondo quanto indicato nella sezione Prerequisiti, che questo account deve disporre di autorizzazioni amministrative su Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ecbed-200">Recall from the Prerequisites section that this account must have administrative permissions on Analysis Services.</span></span>  
  
9. <span data-ttu-id="ecbed-201">In **Server**specificare il nome del server dell'istanza di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ecbed-201">In **Server**, specify the server name of the Analysis Services instance.</span></span>  
  
10. <span data-ttu-id="ecbed-202">In **Comando**fare clic con il pulsante destro del mouse e scegliere **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-202">In **Command**, right-click and select **Paste**.</span></span>  
  
11. <span data-ttu-id="ecbed-203">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-203">Click **OK**.</span></span>  
  
12. <span data-ttu-id="ecbed-204">Nella pagina **Pianificazioni** fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-204">In the **Schedules** page, click **New**.</span></span>  
  
13. <span data-ttu-id="ecbed-205">Nella finestra di dialogo **Nuova pianificazione processo** immettere il nome della pianificazione nella casella **Nome**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-205">In the **New Job Schedule** dialog box, enter a schedule name in **Name**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ecbed-206">In questo passaggio viene creata una pianificazione per domenica alle 12.00 AM.</span><span class="sxs-lookup"><span data-stu-id="ecbed-206">This step creates a schedule for Sunday at 12:00 AM.</span></span> <span data-ttu-id="ecbed-207">Nel passaggio successivo verrà illustrato come eseguire manualmente il processo.</span><span class="sxs-lookup"><span data-stu-id="ecbed-207">The next step shows you how to manually execute the job.</span></span> <span data-ttu-id="ecbed-208">È inoltre possibile selezionare una pianificazione che eseguirà il processo mentre viene monitorato.</span><span class="sxs-lookup"><span data-stu-id="ecbed-208">You can also select a schedule which will execute the job when you are monitoring it.</span></span>  
  
14. <span data-ttu-id="ecbed-209">Scegliere **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ecbed-209">Click **OK** to close the dialog box.</span></span>  
  
15. <span data-ttu-id="ecbed-210">In **Esplora oggetti**espandere **Processi**, fare clic con il pulsante destro del mouse sul processo creato e scegliere **Inizia processo al passaggio**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-210">In **Object Explorer**, expand **Jobs**, right-click the job you created, and select **Start Job at Step**.</span></span>  
  
     <span data-ttu-id="ecbed-211">Poiché il processo include un solo passaggio, verrà eseguito immediatamente.</span><span class="sxs-lookup"><span data-stu-id="ecbed-211">Because the job has only one step, the job executes immediately.</span></span> <span data-ttu-id="ecbed-212">Se il processo è costituito da più di un passaggio, è possibile selezionare quello da cui dovrà iniziare il processo.</span><span class="sxs-lookup"><span data-stu-id="ecbed-212">If the job contains more than one step, you can select the step at which the job should start.</span></span>  
  
16. <span data-ttu-id="ecbed-213">Al termine del processo fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="ecbed-213">When the job finishes, click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecbed-214">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecbed-214">See Also</span></span>  
 <span data-ttu-id="ecbed-215">[Opzioni e impostazioni di elaborazione &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="ecbed-215">[Processing Options and Settings &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md) </span></span>  
 [<span data-ttu-id="ecbed-216">Creare script per le attività amministrative in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ecbed-216">Script Administrative Tasks in Analysis Services</span></span>](../script-administrative-tasks-in-analysis-services.md)  
  
  
