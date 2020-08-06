---
title: 'Passaggio 1: Creazione di cartelle di lavoro e variabili di ambiente | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 45091ba2-ea3d-4399-9814-489d812b42cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 63308d406e230538e5ca8b90dbb55bb802759bd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628853"
---
# <a name="step-1-creating-working-folders-and-environment-variables"></a><span data-ttu-id="958b7-102">Passaggio 1: Creazione di cartelle di lavoro e variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="958b7-102">Step 1: Creating Working Folders and Environment Variables</span></span>
  <span data-ttu-id="958b7-103">In questa attività si procederà alla creazione della cartella di lavoro C:\DeploymentTutorial e delle nuove variabili di ambiente`DataTransfer` e `LoadXMLData`che verranno utilizzate nelle attività successive dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="958b7-103">In this task, you will create the working folder (C:\DeploymentTutorial) and the new system environment variables (`DataTransfer` and `LoadXMLData`) that you will use in later tutorial tasks.</span></span>  
  
 <span data-ttu-id="958b7-104">La cartella di lavoro si trova nella radice dell'unità C.</span><span class="sxs-lookup"><span data-stu-id="958b7-104">The working folder is at the root of the C drive.</span></span> <span data-ttu-id="958b7-105">È comunque possibile utilizzare un'unità o un percorso diverso, se necessario.</span><span class="sxs-lookup"><span data-stu-id="958b7-105">If you must use a different drive or location, you can do that.</span></span> <span data-ttu-id="958b7-106">In questo caso, sarà tuttavia necessario prendere nota del percorso e quindi utilizzarlo ogni volta che nell'esercitazione si fa riferimento al percorso della cartella di lavoro DeploymentTutorial.</span><span class="sxs-lookup"><span data-stu-id="958b7-106">However, you need to note this location and then use it wherever the tutorial refers to the location of the DeploymentTutorial working folder.</span></span>  
  
 <span data-ttu-id="958b7-107">In una lezione successiva i pacchetti salvati nel file system verranno distribuiti nella tabella sysssispackages del database msdb di[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="958b7-107">In a later lesson, you will deploy packages that are saved to the file system to the sysssispackages table in the msdb[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="958b7-108">La situazione ideale è quella in cui i pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] vengono distribuiti in un altro computer.</span><span class="sxs-lookup"><span data-stu-id="958b7-108">Ideally you will deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to a different computer.</span></span> <span data-ttu-id="958b7-109">In caso contrario, è comunque possibile acquisire una notevole familiarità con le procedure illustrate in questa esercitazione distribuendo i pacchetti in un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="958b7-109">If that is not possible, you can still learn a lot from doing this tutorial by deploying the packages to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that is on the local computer.</span></span> <span data-ttu-id="958b7-110">Alle variabili di ambiente utilizzate nel computer locale e in quello di destinazione vengono assegnati i medesimi nomi, ma valori diversi.</span><span class="sxs-lookup"><span data-stu-id="958b7-110">The environment variables that are used on the local and destination computers have the same variable names, but different values are stored in the variables.</span></span> <span data-ttu-id="958b7-111">Nel computer locale il valore della variabile di ambiente `DataTransfer` fa ad esempio riferimento alla cartella C:\DeploymentTutorial, mentre in quello di destinazione la stessa variabile `DataTransfer` fa riferimento alla cartella C:\DeploymentTutorialInstall.</span><span class="sxs-lookup"><span data-stu-id="958b7-111">For example, on the local computer, the value of the environment variable `DataTransfer` references the C:\DeploymentTutorial folder, whereas on the target computer the environment variable `DataTransfer` references the C:\DeploymentTutorialInstall folder.</span></span>  
  
 <span data-ttu-id="958b7-112">Se si prevede di eseguire la distribuzione nel computer locale, è necessario creare un unico set di variabili di ambiente. Per poter eseguire la distribuzione locale sarà comunque necessario impostare le variabili di ambiente sui valori appropriati.</span><span class="sxs-lookup"><span data-stu-id="958b7-112">If you plan to deploy to the local computer, you need to create only one set of environment variables; however, you will need to update the value of the environment variables to an appropriate value before you do the local deployment.</span></span>  
  
 <span data-ttu-id="958b7-113">Se si prevede di distribuire i pacchetti in un altro computer, è necessario creare due set di variabili di ambiente, uno per il computer locale e uno per quello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="958b7-113">If you plan to deploy the packages to a different computer, you must create two sets of environment variables: one set for the local computer, and one set for the destination computer.</span></span> <span data-ttu-id="958b7-114">È possibile creare subito le variabili per il computer di origine e successivamente quelle per il computer di destinazione. Per poter installare i pacchetti nel computer di destinazione, è tuttavia necessario che in quest'ultimo siano disponibili la cartella e le variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="958b7-114">You can create only the variables for the source computer now, and create the variables for the destination computer later, but you must have both the folder and environment variables available on the destination computer before you can install the packages on that computer.</span></span>  
  
### <a name="to-create-the-local-working-folder"></a><span data-ttu-id="958b7-115">Per creare la cartella di lavoro locale</span><span class="sxs-lookup"><span data-stu-id="958b7-115">To create the local working folder</span></span>  
  
1.  <span data-ttu-id="958b7-116">Fare clic con il pulsante destro del mouse sul menu Start e quindi scegliere Esplora.</span><span class="sxs-lookup"><span data-stu-id="958b7-116">Right-click the Start menu, and click Explore.</span></span>  
  
2.  <span data-ttu-id="958b7-117">Fare clic su **Disco locale (C:)** .</span><span class="sxs-lookup"><span data-stu-id="958b7-117">Click **Local Disk (C:)**.</span></span>  
  
3.  <span data-ttu-id="958b7-118">Scegliere **Nuovo** dal menu **File**e fare clic su **Cartella**.</span><span class="sxs-lookup"><span data-stu-id="958b7-118">On the **File** menu, point to **New**, and then click **Folder**.</span></span>  
  
4.  <span data-ttu-id="958b7-119">Rinominare la nuova cartella in `DeploymentTutorial` .</span><span class="sxs-lookup"><span data-stu-id="958b7-119">Rename New Folder to `DeploymentTutorial`.</span></span>  
  
### <a name="to-create-local-environment-variables"></a><span data-ttu-id="958b7-120">Per creare le variabili di ambiente locali</span><span class="sxs-lookup"><span data-stu-id="958b7-120">To create local environment variables</span></span>  
  
1.  <span data-ttu-id="958b7-121">Fare clic sul menu **Start** e scegliere **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="958b7-121">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="958b7-122">In Pannello di controllo fare doppio clic su **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="958b7-122">In Control Panel, double-click **System**.</span></span>  
  
3.  <span data-ttu-id="958b7-123">Nella finestra di dialogo **Proprietà del sistema** fare clic sulla scheda **Avanzate** e quindi fare clic **su Variabili d'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="958b7-123">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="958b7-124">Nel riquadro **Variabili di sistema** della finestra di dialogo **Variabili d'ambiente** fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="958b7-124">In the **Environment Variables** dialog box, in the **System variables** frame, click **New**.</span></span>  
  
5.  <span data-ttu-id="958b7-125">Nella finestra di dialogo **nuova variabile di sistema** Digitare `DataTransfer` nella casella **nome variabile** e `C:\DeploymentTutorial\datatransferconfig.dtsconfig` nella casella **valore variabile** .</span><span class="sxs-lookup"><span data-stu-id="958b7-125">In the **New System Variable** dialog box, type `DataTransfer` in the **Variable name** box, and `C:\DeploymentTutorial\datatransferconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
6.  <span data-ttu-id="958b7-126">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="958b7-126">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="958b7-127">Fare nuovamente clic su **nuovo** e digitare `LoadXMLData` nella casella **nome variabile** e `C:\DeploymentTutorial\loadxmldataconfig.dtsconfig` nella casella **valore variabile** .</span><span class="sxs-lookup"><span data-stu-id="958b7-127">Click **New** again, and type `LoadXMLData` in the **Variable name** box, and `C:\DeploymentTutorial\loadxmldataconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
8.  <span data-ttu-id="958b7-128">Fare clic su **OK** per chiudere la finestra di dialogo **Variabili d'ambiente** .</span><span class="sxs-lookup"><span data-stu-id="958b7-128">Click **OK** to exit the **Environment Variables** dialog box.</span></span>  
  
9. <span data-ttu-id="958b7-129">Fare clic su **OK** per chiudere la finestra di dialogo **Proprietà del sistema** .</span><span class="sxs-lookup"><span data-stu-id="958b7-129">Click **OK** to exit the **System Properties** dialog box.\</span></span>  
  
10. <span data-ttu-id="958b7-130">Facoltativamente, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="958b7-130">Optionally, restart your computer.</span></span> <span data-ttu-id="958b7-131">Se non si riavvia il computer, il nome della nuova variabile non verrà visualizzato nella Configurazione guidata pacchetto, ma sarà comunque possibile utilizzarla.</span><span class="sxs-lookup"><span data-stu-id="958b7-131">If you do not restart the computer, the name of the new variable will not be displayed in the Package Configuration Wizard, but you can still use it.</span></span>  
  
### <a name="to-create-destination-environment-variables"></a><span data-ttu-id="958b7-132">Per creare le variabili d'ambiente di destinazione</span><span class="sxs-lookup"><span data-stu-id="958b7-132">To create destination environment variables</span></span>  
  
1.  <span data-ttu-id="958b7-133">Fare clic sul menu **Start** e scegliere **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="958b7-133">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="958b7-134">In Pannello di controllo fare doppio clic su **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="958b7-134">In Control Panel, double-click **System**.</span></span>  
  
3.  <span data-ttu-id="958b7-135">Nella finestra di dialogo **Proprietà del sistema** fare clic sulla scheda **Avanzate** e quindi fare clic **su Variabili d'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="958b7-135">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="958b7-136">Nel riquadro **Variabili di sistema** della finestra di dialogo **Variabili d'ambiente** fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="958b7-136">In the **Environment Variables** dialog box, in **System variables** frame, click **New**.</span></span>  
  
5.  <span data-ttu-id="958b7-137">Nella finestra di dialogo **nuove variabili di sistema** Digitare `DataTransfer` nella casella **nome variabile** e `C:\DeploymentTutorialInstall\datatransferconfig.dtsconfig` nella casella **valore variabile** .</span><span class="sxs-lookup"><span data-stu-id="958b7-137">In the **New System Variables** dialog box, type `DataTransfer` in the **Variable name** box, and `C:\DeploymentTutorialInstall\datatransferconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
6.  <span data-ttu-id="958b7-138">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="958b7-138">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="958b7-139">Fare nuovamente clic su **nuovo** e digitare `LoadXMLData` nella casella **nome variabile** e `C:\DeploymentTutorialInstall\loadxmldataconfig.dtsconfig` nella casella **valore variabile** .</span><span class="sxs-lookup"><span data-stu-id="958b7-139">Click **New** again, and type `LoadXMLData` in the **Variable name** box, and `C:\DeploymentTutorialInstall\loadxmldataconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
8.  <span data-ttu-id="958b7-140">Fare clic su **OK** per chiudere la finestra di dialogo **Variabili d'ambiente** .</span><span class="sxs-lookup"><span data-stu-id="958b7-140">Click **OK** to exit the **Environment Variables** dialog box.</span></span>  
  
9. <span data-ttu-id="958b7-141">Fare clic su **OK** per chiudere la finestra di dialogo **Proprietà del sistema** .</span><span class="sxs-lookup"><span data-stu-id="958b7-141">Click **OK** to exit the **System Properties** dialog box.\</span></span>  
  
10. <span data-ttu-id="958b7-142">Facoltativamente, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="958b7-142">Optionally, restart your computer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="958b7-143">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="958b7-143">Next Task in Lesson</span></span>  
 [<span data-ttu-id="958b7-144">Passaggio 2: Creazione del progetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="958b7-144">Step 2: Creating the Deployment Project</span></span>](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
<span data-ttu-id="958b7-145">![Integration Services icona (piccola)](media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="958b7-145">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="958b7-146">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="958b7-146">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="958b7-147">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="958b7-147">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="958b7-148">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="958b7-148">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
