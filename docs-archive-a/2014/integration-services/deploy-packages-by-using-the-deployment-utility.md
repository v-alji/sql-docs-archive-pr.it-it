---
title: Distribuire pacchetti con l'utilità di distribuzione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], installing
- installing packages
- dependencies [Integration Services]
- deploying packages [Integration Services], installing
ms.assetid: eaf4b56e-2023-4d17-971c-703031da758c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a09ad307dc0215fca679cfb1ef5a37031f951caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718623"
---
# <a name="deploy-packages-by-using-the-deployment-utility"></a><span data-ttu-id="16893-102">Distribuzione di pacchetti con l'utilità di distribuzione</span><span class="sxs-lookup"><span data-stu-id="16893-102">Deploy Packages by Using the Deployment Utility</span></span>
  <span data-ttu-id="16893-103">Se è stata compilata un'utilità di distribuzione per l'installazione di pacchetti di un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in un computer diverso da quello in cui l'utilità è stata compilata, è prima necessario copiare la cartella di distribuzione nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="16893-103">When you have built a deployment utility to install packages from an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project on a different computer than the one on which the deployment utility was built, you must first copy the deployment folder to the destination computer.</span></span>  
  
 <span data-ttu-id="16893-104">Il percorso di tale cartella è specificato nella proprietà DeploymentOutputPath del progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] per il quale è stata creata l'utilità di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="16893-104">The path of the deployment folder is specified in the DeploymentOutputPath property of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project for which you created the deployment utility.</span></span> <span data-ttu-id="16893-105">Il percorso predefinito è bin\Deployment relativo al progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16893-105">The default path is bin\Deployment, relative to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="16893-106">Per altre informazioni, vedere [Creazione di un'utilità di distribuzione](../../2014/integration-services/create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="16893-106">For more information, see [Create a Deployment Utility](../../2014/integration-services/create-a-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="16893-107">Per installare i pacchetti è possibile utilizzare Installazione guidata pacchetti,</span><span class="sxs-lookup"><span data-stu-id="16893-107">You use the Package Installation Wizard to install the packages.</span></span> <span data-ttu-id="16893-108">che può essere avviata facendo doppio clic sul file dell'utilità di distribuzione, dopo aver copiato la cartella di distribuzione sul server.</span><span class="sxs-lookup"><span data-stu-id="16893-108">To launch the wizard, double-click the deployment utility file after you have copied the deployment folder to the server.</span></span> <span data-ttu-id="16893-109">Il file è denominato \<project name>.SSISDeploymentManifest ed è disponibile nella cartella di distribuzione nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="16893-109">This file is named \<project name>.SSISDeploymentManifest, and can be found in the deployment folder on the destination computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16893-110">In base alla versione del pacchetto che si distribuisce, è possibile rilevare un errore se versioni diverse di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sono state installate in modalità side-by-side.</span><span class="sxs-lookup"><span data-stu-id="16893-110">Depending on the version of the package that you are deploying, you might encounter an error if you have different versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] installed side-by-side.</span></span> <span data-ttu-id="16893-111">Questo errore può verificarsi perché l'estensione del file SSISDeploymentManifest è uguale per tutte le versioni di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16893-111">This error can occur because the .SSISDeploymentManifest file name extension is the same for all versions of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="16893-112">Se si fa doppio clic sul file viene chiamato il programma di installazione (dtsinstall.exe) della versione di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]installata più di recente, che potrebbe non corrispondere a quella del file dell'utilità di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="16893-112">Double-clicking the file calls the installer (dtsinstall.exe) for the most recently installed version of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], which might not be the same version as the deployment utility file.</span></span> <span data-ttu-id="16893-113">Per evitare tale problema, eseguire la versione corretta di dtsinstall.exe dalla riga di comando e specificare il percorso del file dell'utilità di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="16893-113">To work around this problem, run the correct version of dtsinstall.exe from the command line, and provide the path of the deployment utility file.</span></span>  
  
 <span data-ttu-id="16893-114">L'Installazione guidata pacchetti consente di eseguire in modo semplificato i passaggi necessari per l'installazione di pacchetti nel file system o in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16893-114">The Package Installation Wizard guides you through the steps to install packages to the file system or to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="16893-115">È possibile configurare l'installazione nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="16893-115">You can configure the installation in the following ways:</span></span>  
  
-   <span data-ttu-id="16893-116">Specificando il tipo di posizione e la posizione per l'installazione dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="16893-116">Choosing the location type and location to install the packages.</span></span>  
  
-   <span data-ttu-id="16893-117">Specificando la posizione per l'installazione delle dipendenze dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="16893-117">Choosing location to install package dependencies.</span></span>  
  
-   <span data-ttu-id="16893-118">Convalidando i pacchetti dopo l'installazione nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="16893-118">Validating the packages after they are installed on the target server.</span></span>  
  
 <span data-ttu-id="16893-119">Le dipendenze basate su file per i pacchetti vengono sempre installate nel file system.</span><span class="sxs-lookup"><span data-stu-id="16893-119">The file-based dependencies for packages are always installed to the file system.</span></span> <span data-ttu-id="16893-120">Se si installa un pacchetto nel file system, le dipendenze vengono installate nella stessa cartella specificata per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="16893-120">If you install a package to the file system, the dependencies are installed in the same folder as the one that you specify for the package.</span></span> <span data-ttu-id="16893-121">Se si installa un pacchetto in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], è possibile specificare la cartella in cui archiviare le dipendenze basate su file.</span><span class="sxs-lookup"><span data-stu-id="16893-121">If you install a package to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can specify the folder in which to store the file-based dependencies.</span></span>  
  
 <span data-ttu-id="16893-122">Se il pacchetto include configurazioni che si desidera modificare per l'utilizzo nel computer di destinazione, è possibile aggiornare i valori delle proprietà tramite la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="16893-122">If the package includes configurations that you want to modify for use on the destination computer, you can update the values of the properties by using the wizard.</span></span>  
  
 <span data-ttu-id="16893-123">Oltre a installare pacchetti eseguendo l'Installazione guidata pacchetti, è possibile copiare e spostare pacchetti tramite l'utilità del prompt dei comandi **dtutil** .</span><span class="sxs-lookup"><span data-stu-id="16893-123">In addition to installing packages by using the Package Installation Wizard, you can copy and move packages by using the **dtutil** command prompt utility.</span></span> <span data-ttu-id="16893-124">Per altre informazioni, vedere [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="16893-124">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
### <a name="to-deploy-packages-to-an-instance-of-sql-server"></a><span data-ttu-id="16893-125">Per distribuire pacchetti in un'istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="16893-125">To deploy packages to an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="16893-126">Aprire la cartella di distribuzione del computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="16893-126">Open the deployment folder on the target computer.</span></span>  
  
2.  <span data-ttu-id="16893-127">Fare doppio clic sul file di manifesto \<project name>.SSISDeploymentManifest per avviare l'Installazione guidata pacchetti.</span><span class="sxs-lookup"><span data-stu-id="16893-127">Double-click the manifest file, \<project name>.SSISDeploymentManifest, to start the Package Installation Wizard.</span></span>  
  
3.  <span data-ttu-id="16893-128">Nella pagina **Distribuzione pacchetti SSIS** selezionare l'opzione **Distribuzione di SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="16893-128">On the **Deploy SSIS Packages** page, select the **SQL Server deployment** option.</span></span>  
  
4.  <span data-ttu-id="16893-129">Facoltativamente, selezionare **Convalida pacchetti dopo l'installazione** per convalidare i pacchetti dopo che sono stati installati nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="16893-129">Optionally, select **Validate packages after installation** to validate packages after they are installed on the target server.</span></span>  
  
5.  <span data-ttu-id="16893-130">Nella pagina **Impostazione istanza di SQL Server di destinazione** specificare l'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in cui installare i pacchetti e selezionare una modalità di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="16893-130">On the **Specify Target SQL Server** page, specify the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to install the packages to and select an authentication mode.</span></span> <span data-ttu-id="16893-131">Se si seleziona l'Autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , è necessario specificare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="16893-131">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and a password.</span></span>  
  
6.  <span data-ttu-id="16893-132">Nella pagina **Selezione cartella di installazione** specificare la cartella del file system in cui installare i pacchetti e le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="16893-132">On the **Select Installation Folder** page, specify the folder in the file system for the package dependencies that will be installed.</span></span>  
  
7.  <span data-ttu-id="16893-133">Se il pacchetto include configurazioni, è possibile modificarle aggiornando i valori dell'elenco **Valore** nella pagina Configurazione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="16893-133">If the package includes configurations, you can edit configurations by updating values in the **Value** list on the Configure Packages page.</span></span>  
  
8.  <span data-ttu-id="16893-134">Se è stata impostata la convalida dei pacchetti dopo l'installazione, esaminare i risultati della convalida dei pacchetti distribuiti.</span><span class="sxs-lookup"><span data-stu-id="16893-134">If you elected to validate packages after installation, view the validation results of the deployed packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16893-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16893-135">See Also</span></span>  
 [<span data-ttu-id="16893-136">Distribuzione di pacchetti &#40;&#41;SSIS</span><span class="sxs-lookup"><span data-stu-id="16893-136">Package Deployment &#40;SSIS&#41;</span></span>](packages/legacy-package-deployment-ssis.md)  
  
  
