---
title: Implementazione di pacchetti figlio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- child packages
ms.assetid: ab0c09d7-ce2e-487d-a1ed-a4b5adb6cc01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4fa4fa7c523c55c595341c7aee6a530c5918a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714523"
---
# <a name="implementation-of-child-packages"></a><span data-ttu-id="daf37-102">Implementazione di pacchetti figlio</span><span class="sxs-lookup"><span data-stu-id="daf37-102">Implementation of Child Packages</span></span>
  <span data-ttu-id="daf37-103">Quando si implementa il bilanciamento del carico tramite [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], i pacchetti figlio vengono installati su altri server per sfruttare il tempo di CPU o di server disponibile.</span><span class="sxs-lookup"><span data-stu-id="daf37-103">When you implement load balancing using [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], child packages are installed on other servers to take advantage of the available CPU or server time.</span></span> <span data-ttu-id="daf37-104">Per creare ed eseguire i pacchetti figlio è necessario attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="daf37-104">To create and run the child packages requires the following steps:</span></span>  
  
-   <span data-ttu-id="daf37-105">Progettare i pacchetti figlio.</span><span class="sxs-lookup"><span data-stu-id="daf37-105">Designing the child packages.</span></span>  
  
-   <span data-ttu-id="daf37-106">Spostare i pacchetti sul server remoto.</span><span class="sxs-lookup"><span data-stu-id="daf37-106">Moving the packages to the remote server.</span></span>  
  
-   <span data-ttu-id="daf37-107">Creare sul server remoto un processo di SQL Server Agent contenente un passaggio che esegue il pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="daf37-107">Creating a SQL Server Agent Job on the remote server that contains a step that runs the child package.</span></span>  
  
-   <span data-ttu-id="daf37-108">Eseguire il debug e il test del processo di SQL Server Agent e dei pacchetti figlio.</span><span class="sxs-lookup"><span data-stu-id="daf37-108">Testing and debugging the SQL Server Agent Job and child packages.</span></span>  
  
 <span data-ttu-id="daf37-109">Poiché non sono previste limitazioni, durante la progettazione dei pacchetti figlio è possibile inserire qualsiasi funzionalità nei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="daf37-109">When you design the child packages, the packages have no limitations in their design, and you can put in any functionality you desire.</span></span> <span data-ttu-id="daf37-110">Se tuttavia il pacchetto deve accedere a dati, è necessario verificare che il server in cui viene eseguito il pacchetto abbia accesso a tali dati.</span><span class="sxs-lookup"><span data-stu-id="daf37-110">However, if the package accesses data, you must ensure that the server that runs the package has access to the data.</span></span>  
  
 <span data-ttu-id="daf37-111">Per identificare il pacchetto padre che esegue i pacchetti figlio, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] fare clic con il pulsante destro del mouse sul pacchetto in Esplora soluzioni, quindi scegliere **Pacchetto punto di ingresso**.</span><span class="sxs-lookup"><span data-stu-id="daf37-111">To identify the parent package that executes child packages, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] right click the package in Solution Explorer and then click **Entry-point Package**.</span></span>  
  
 <span data-ttu-id="daf37-112">Terminata la progettazione dei pacchetti figlio è necessario distribuirli nei server remoti.</span><span class="sxs-lookup"><span data-stu-id="daf37-112">After the child packages have been designed, the next step is to deploy them on the remote servers.</span></span>  
  
## <a name="moving-the-child-package-to-the-remote-instance"></a><span data-ttu-id="daf37-113">Spostamento dei pacchetti figlio nell'istanza remota</span><span class="sxs-lookup"><span data-stu-id="daf37-113">Moving the Child Package to the Remote Instance</span></span>  
 <span data-ttu-id="daf37-114">Esistono più modi per spostare pacchetti su altri server.</span><span class="sxs-lookup"><span data-stu-id="daf37-114">There are multiple ways to move packages to other servers.</span></span> <span data-ttu-id="daf37-115">È tuttavia consigliabile utilizzare i due metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="daf37-115">The two suggested methods are:</span></span>  
  
-   <span data-ttu-id="daf37-116">Esportazione di pacchetti tramite [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daf37-116">Exporting packages by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="daf37-117">Distribuzione di pacchetti compilando un'utilità di distribuzione per il progetto contenente i pacchetti da distribuire, quindi esecuzione dell'Installazione guidata pacchetti per installare i pacchetti nel file system o in un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daf37-117">Deploying packages by building a deployment utility for the project that contains the packages you want to deploy, and then running the Package Installation Wizard to install the packages to the file system or to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="daf37-118">Per ulteriori informazioni, vedere [distribuzione di pacchetti &#40;&#41;SSIS ](packages/legacy-package-deployment-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="daf37-118">For more information, see [Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md).</span></span>  
  
 <span data-ttu-id="daf37-119">È necessario ripetere la distribuzione su tutti i server remoti che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="daf37-119">You must repeat the deployment to each remote server you want to use.</span></span>  
  
## <a name="creating-the-sql-server-agent-jobs"></a><span data-ttu-id="daf37-120">Creazione dei processi di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="daf37-120">Creating the SQL Server Agent Jobs</span></span>  
 <span data-ttu-id="daf37-121">Dopo la distribuzione dei pacchetti figlio sui vari server, creare un processo di SQL Server Agent su ogni server che contiene un pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="daf37-121">After the child packages have been deployed to the various servers, create a SQL Server Agent job on each server that contains a child package.</span></span> <span data-ttu-id="daf37-122">Il processo di SQL Server Agent deve contenere un passaggio che esegue il pacchetto figlio quando viene chiamato l'agente del processo.</span><span class="sxs-lookup"><span data-stu-id="daf37-122">The SQL Server Agent job contains a step that runs the child package when the job agent is called.</span></span> <span data-ttu-id="daf37-123">I processi di SQL Server Agent non sono processi pianificati, ma eseguono i pacchetti figlio solo quando vengono chiamati dal pacchetto padre.</span><span class="sxs-lookup"><span data-stu-id="daf37-123">The SQL Server Agent jobs are not scheduled jobs; they run the child packages only when they are called by the parent package.</span></span> <span data-ttu-id="daf37-124">Nella notifica dell'esito positivo o negativo restituita al pacchetto padre viene comunicato l'esito positivo o negativo del processo di SQL Server Agent, specificando se la chiamata a SQL Server Agent è avvenuta correttamente, ma non viene indicato l'esito positivo o negativo del pacchetto figlio oppure se quest'ultimo è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="daf37-124">Notification of success or failure of the job back to the parent package reflects the success or failure of the SQL Server Agent job and whether it was called successfully, not the success or failure of the child package or whether it was executed.</span></span>  
  
## <a name="debugging-the-sql-server-agent-jobs-and-child-packages"></a><span data-ttu-id="daf37-125">Debug dei processi di SQL Server Agent e dei pacchetti figlio</span><span class="sxs-lookup"><span data-stu-id="daf37-125">Debugging the SQL Server Agent Jobs and Child Packages</span></span>  
 <span data-ttu-id="daf37-126">Per il test dei processi di SQL Server Agent e dei relativi pacchetti figlio è possibile utilizzare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="daf37-126">You can test the SQL Server Agent jobs and their child packages by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="daf37-127">Esecuzione di ogni pacchetto figlio in Progettazione SSIS, facendo clic su **debug**  /  **Avvia senza eseguire debug**.</span><span class="sxs-lookup"><span data-stu-id="daf37-127">Running each child package in SSIS Designer, by clicking **Debug** / **Start Without Debugging**.</span></span>  
  
-   <span data-ttu-id="daf37-128">Eseguire ogni singolo processo di SQL Server Agent sul relativo computer remoto, tramite [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], per verificare che il pacchetto venga eseguito.</span><span class="sxs-lookup"><span data-stu-id="daf37-128">Running the individual SQL Server Agent job on the remote computer by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to make sure that the package runs.</span></span>  
  
 <span data-ttu-id="daf37-129">Per informazioni su come risolvere i problemi legati all'esecuzione di pacchetti dai processi di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, vedere l'articolo relativo a [un pacchetto SSIS che non viene eseguito quando si chiama il pacchetto SSIS da un passaggio di processo di SQL Server Agent](https://support.microsoft.com/kb/918760) nella [!INCLUDE[msCoName](../includes/msconame-md.md)] Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="daf37-129">For information about how to troubleshoot packages that you run from [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs, see [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760) in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Support Knowledge Base.</span></span>  
  
 <span data-ttu-id="daf37-130">SQL Server Agent verifica l'accesso al sottosistema per un proxy e garantisce l'accesso al proxy a ogni esecuzione del relativo passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="daf37-130">The SQL Server Agent checks subsystem access for a proxy and gives access to the proxy every time the job step runs.</span></span>  
  
 <span data-ttu-id="daf37-131">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]è possibile creare un proxy.</span><span class="sxs-lookup"><span data-stu-id="daf37-131">You can create a proxy in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="daf37-132">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="daf37-132">Related Tasks</span></span>  
  
-   [<span data-ttu-id="daf37-133">Eseguire un pacchetto sul server SSIS mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="daf37-133">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
## <a name="related-content"></a><span data-ttu-id="daf37-134">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="daf37-134">Related Content</span></span>  
  
-   <span data-ttu-id="daf37-135">Intervento sul Blog relativo a [SSIS: accesso alle variabili in un pacchetto padre](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/)in andyleonard. Blog.</span><span class="sxs-lookup"><span data-stu-id="daf37-135">Blog entry, [SSIS: Accessing variables in a parent package](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/), on andyleonard.blog.</span></span>  
  
-   <span data-ttu-id="daf37-136">Articolo, [attività Esegui pacchetto](../integration-services/control-flow/execute-package-task.md).</span><span class="sxs-lookup"><span data-stu-id="daf37-136">Article, [Execute Package Task](../integration-services/control-flow/execute-package-task.md).</span></span>  
  
  
