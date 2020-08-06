---
title: Informazioni di riferimento sull'interfaccia utente dell'installazione guidata pacchetti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.deploymentwizard.confirminstallation.f1
- sql12.dts.deploymentwizard.deploydtspackages.f1
- sql12.dts.deploymentwizard.selectinstfolder.f1
- sql12.dts.deploymentwizard.specifytargetsqlserver.f1
- sql12.dts.deploymentwizard.welcome.f1
- sql12.dts.deploymentwizard.finish.f1
- sql12.dts.deploymentwizard.configurepackages.f1
- sql12.dts.deploymentwizard.packagevalidation.f1
helpviewer_keywords:
- Package Installer Wizard
ms.assetid: 6fca44d9-5001-4644-bcf3-c2d10a674b97
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c15b423c66891e799f7f8dcd27682036dce6d8de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713280"
---
# <a name="package-installation-wizard-ui-reference"></a><span data-ttu-id="5c51d-102">Riferimento all'interfaccia utente dell'Installazione guidata pacchetti</span><span class="sxs-lookup"><span data-stu-id="5c51d-102">Package Installation Wizard UI Reference</span></span>
  <span data-ttu-id="5c51d-103">Usare l' **Installazione guidata pacchetti** per distribuire un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , inclusi i pacchetti, i file contenuti ed eventuali dipendenze dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-103">Use the **Package Installation Wizard** to deploy a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, including the packages and miscellaneous files it contains and any package dependencies.</span></span>  
  
 <span data-ttu-id="5c51d-104">Prima di distribuire i pacchetti, è possibile creare configurazioni e distribuirle con i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-104">Before you deploy packages, you can create configurations and then deploy them with the packages.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="5c51d-105">usa le configurazioni per aggiornare in modo dinamico le proprietà di pacchetti e oggetti relativi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5c51d-105">uses configurations to dynamically update properties of packages and package objects at run time.</span></span> <span data-ttu-id="5c51d-106">La stringa di connessione di una connessione OLE DB può essere ad esempio impostata dinamicamente in fase di esecuzione, specificando una configurazione che esegue il mapping di un valore alla proprietà contenente la stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="5c51d-106">For example, the connection string of an OLE DB connection can be set dynamically at run time by providing a configuration that maps a value to the property that contains the connection string.</span></span>  
  
 <span data-ttu-id="5c51d-107">Non è possibile eseguire l'Installazione guidata pacchetti finché non si compila un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e non si crea un'utilità di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5c51d-107">You cannot run the Package Installation Wizard until you build an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and create a deployment utility.</span></span> <span data-ttu-id="5c51d-108">Per altre informazioni, vedere [Distribuzione di pacchetti con l'utilità di distribuzione](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="5c51d-108">For more information, see [Deploy Packages by Using the Deployment Utility](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="5c51d-109">Nelle sezioni seguenti vengono descritte le pagine della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5c51d-109">The following sections describe pages of the wizard.</span></span>  
  
## <a name="welcome-to-the-package-installation-wizard-page"></a><span data-ttu-id="5c51d-110">Pagina dell'Installazione guidata pacchetti</span><span class="sxs-lookup"><span data-stu-id="5c51d-110">Welcome to the Package Installation Wizard Page</span></span>  
 <span data-ttu-id="5c51d-111">L' **Installazione guidata pacchetti** consente di distribuire un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] per cui è stata compilata un'utilità di distribuzione dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-111">Use the **Package Installation Wizard** to deploy an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project for which you built a package deployment utility.</span></span>  
  
 <span data-ttu-id="5c51d-112">**Non visualizzare più questa pagina iniziale**</span><span class="sxs-lookup"><span data-stu-id="5c51d-112">**Do not show this starting page again**</span></span>  
 <span data-ttu-id="5c51d-113">Selezionare questa opzione per ignorare la pagina iniziale quando si esegue nuovamente la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5c51d-113">Select to skip the starting page when you run the wizard again.</span></span>  
  
 <span data-ttu-id="5c51d-114">**Avanti**</span><span class="sxs-lookup"><span data-stu-id="5c51d-114">**Next**</span></span>  
 <span data-ttu-id="5c51d-115">Consente di passare alla pagina successiva della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5c51d-115">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="5c51d-116">**Fine**</span><span class="sxs-lookup"><span data-stu-id="5c51d-116">**Finish**</span></span>  
 <span data-ttu-id="5c51d-117">Consente di passare alla pagina Completamento Installazione guidata pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-117">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="5c51d-118">Utilizzare questa opzione se sono state controllate le scelte effettuate nelle pagine precedenti della procedura guidata e si è certi di avere specificato tutte le opzioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="5c51d-118">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="configure-packages-page"></a><span data-ttu-id="5c51d-119">Pagina Configurazione pacchetti</span><span class="sxs-lookup"><span data-stu-id="5c51d-119">Configure Packages Page</span></span>  
 <span data-ttu-id="5c51d-120">La pagina **Configurazione pacchetti** consente di modificare le configurazioni dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-120">Use the **Configure Packages** page to edit package configurations.</span></span>  
  
### <a name="options"></a><span data-ttu-id="5c51d-121">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5c51d-121">Options</span></span>  
 <span data-ttu-id="5c51d-122">**File di configurazione**</span><span class="sxs-lookup"><span data-stu-id="5c51d-122">**Configuration file**</span></span>  
 <span data-ttu-id="5c51d-123">Consente di modificare il contenuto di un file di configurazione selezionando il file dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="5c51d-123">Edit the contents of a configuration file by selecting the file from the list.</span></span>  
  
 <span data-ttu-id="5c51d-124">**Argomenti correlati:** [Creazione di configurazioni dei pacchetti](../../2014/integration-services/create-package-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="5c51d-124">**Related Topics:** [Create Package Configurations](../../2014/integration-services/create-package-configurations.md)</span></span>  
  
 <span data-ttu-id="5c51d-125">**Percorso**</span><span class="sxs-lookup"><span data-stu-id="5c51d-125">**Path**</span></span>  
 <span data-ttu-id="5c51d-126">Indica il percorso della proprietà da configurare.</span><span class="sxs-lookup"><span data-stu-id="5c51d-126">View the path of the property to be configured.</span></span>  
  
 <span data-ttu-id="5c51d-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5c51d-127">**Type**</span></span>  
 <span data-ttu-id="5c51d-128">Indica il tipo di dati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="5c51d-128">View the data type of the property.</span></span>  
  
 <span data-ttu-id="5c51d-129">**Valore**</span><span class="sxs-lookup"><span data-stu-id="5c51d-129">**Value**</span></span>  
 <span data-ttu-id="5c51d-130">Consente di specificare il valore della configurazione.</span><span class="sxs-lookup"><span data-stu-id="5c51d-130">Specify the value of the configuration.</span></span>  
  
 <span data-ttu-id="5c51d-131">**Avanti**</span><span class="sxs-lookup"><span data-stu-id="5c51d-131">**Next**</span></span>  
 <span data-ttu-id="5c51d-132">Consente di passare alla pagina successiva della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5c51d-132">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="5c51d-133">**Fine**</span><span class="sxs-lookup"><span data-stu-id="5c51d-133">**Finish**</span></span>  
 <span data-ttu-id="5c51d-134">Consente di passare alla pagina Completamento Installazione guidata pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-134">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="5c51d-135">Utilizzare questa opzione se sono state controllate le scelte effettuate nelle pagine precedenti della procedura guidata e si è certi di avere specificato tutte le opzioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="5c51d-135">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="confirm-installation-page"></a><span data-ttu-id="5c51d-136">Pagina Conferma installazione</span><span class="sxs-lookup"><span data-stu-id="5c51d-136">Confirm Installation Page</span></span>  
 <span data-ttu-id="5c51d-137">La pagina **Conferma installazione** consente di avviare l'installazione dei pacchetti, visualizzare lo stato e visualizzare informazioni che verranno usate dalla procedura guidata per l'installazione dei file dal progetto specificato.</span><span class="sxs-lookup"><span data-stu-id="5c51d-137">Use the **Confirm Installation** page to start the installation of packages, to view the status, and to view the information that the wizard will use to install files from the specified project.</span></span>  
  
 <span data-ttu-id="5c51d-138">**Avanti**</span><span class="sxs-lookup"><span data-stu-id="5c51d-138">**Next**</span></span>  
 <span data-ttu-id="5c51d-139">Consente di installare i pacchetti e le relative dipendenze, quindi di passare alla pagina successiva della procedura al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="5c51d-139">Install the packages and their dependencies and go to the next wizard page when installation is completed.</span></span>  
  
 <span data-ttu-id="5c51d-140">**Status**</span><span class="sxs-lookup"><span data-stu-id="5c51d-140">**Status**</span></span>  
 <span data-ttu-id="5c51d-141">Mostra lo stato dell'installazione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5c51d-141">Shows the progress of the package installation.</span></span>  
  
 <span data-ttu-id="5c51d-142">**Fine**</span><span class="sxs-lookup"><span data-stu-id="5c51d-142">**Finish**</span></span>  
 <span data-ttu-id="5c51d-143">Consente di passare alla pagina Completamento Installazione guidata pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-143">Go to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="5c51d-144">Utilizzare questa opzione se sono state controllate le scelte effettuate nelle pagine precedenti della procedura guidata e si è certi di avere specificato tutte le opzioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="5c51d-144">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all the required options.</span></span>  
  
## <a name="deploy-ssis-packages-page"></a><span data-ttu-id="5c51d-145">Pagina Distribuzione pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="5c51d-145">Deploy SSIS Packages Page</span></span>  
 <span data-ttu-id="5c51d-146">Usare la pagina **Distribuzione pacchetti SSIS** per specificare il percorso d'installazione dei pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e delle relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="5c51d-146">Use the **Deploy SSIS Packages** page to specify where to install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages and their dependencies.</span></span>  
  
### <a name="options"></a><span data-ttu-id="5c51d-147">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5c51d-147">Options</span></span>  
 <span data-ttu-id="5c51d-148">**Distribuzione nel file system**</span><span class="sxs-lookup"><span data-stu-id="5c51d-148">**File system deployment**</span></span>  
 <span data-ttu-id="5c51d-149">Consente di distribuire i pacchetti e le dipendenze in una cartella specificata del file system.</span><span class="sxs-lookup"><span data-stu-id="5c51d-149">Deploy packages and dependencies in a specified folder in the file system.</span></span>  
  
 <span data-ttu-id="5c51d-150">**Distribuzione in SQL Server**</span><span class="sxs-lookup"><span data-stu-id="5c51d-150">**SQL Server deployment**</span></span>  
 <span data-ttu-id="5c51d-151">Consente di distribuire i pacchetti e le dipendenze in un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c51d-151">Deploy packages and dependencies in an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5c51d-152">Usare questa opzione se [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] condivide i pacchetti tra i server.</span><span class="sxs-lookup"><span data-stu-id="5c51d-152">Use this option if [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shares packages between servers.</span></span> <span data-ttu-id="5c51d-153">Le eventuali dipendenze dei pacchetti vengono installate nella cartella specificata del file system.</span><span class="sxs-lookup"><span data-stu-id="5c51d-153">Any package dependencies are installed in the specified folder in the file system.</span></span>  
  
 <span data-ttu-id="5c51d-154">**Convalida pacchetti dopo l'installazione**</span><span class="sxs-lookup"><span data-stu-id="5c51d-154">**Validate packages after installation**</span></span>  
 <span data-ttu-id="5c51d-155">Consente di specificare se convalidare i pacchetti dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="5c51d-155">Indicate whether to validate packages after installation.</span></span>  
  
 <span data-ttu-id="5c51d-156">**Avanti**</span><span class="sxs-lookup"><span data-stu-id="5c51d-156">**Next**</span></span>  
 <span data-ttu-id="5c51d-157">Consente di passare alla pagina successiva della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5c51d-157">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="5c51d-158">**Fine**</span><span class="sxs-lookup"><span data-stu-id="5c51d-158">**Finish**</span></span>  
 <span data-ttu-id="5c51d-159">Consente di passare alla pagina Completamento Installazione guidata pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-159">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="5c51d-160">Utilizzare questa opzione se sono state controllate le scelte effettuate nelle pagine precedenti della procedura guidata e si è certi di avere specificato tutte le opzioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="5c51d-160">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="packages-validation-page"></a><span data-ttu-id="5c51d-161">Pagina Convalida pacchetti</span><span class="sxs-lookup"><span data-stu-id="5c51d-161">Packages Validation Page</span></span>  
 <span data-ttu-id="5c51d-162">Usare la pagina **Convalida pacchetti** per visualizzare lo stato e i risultati della convalida dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-162">Use the **Packages Validation** page to view the progress and results of the package validation.</span></span>  
  
 <span data-ttu-id="5c51d-163">**Avanti**</span><span class="sxs-lookup"><span data-stu-id="5c51d-163">**Next**</span></span>  
 <span data-ttu-id="5c51d-164">Consente di passare alla pagina successiva della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5c51d-164">Go to the next page in the wizard.</span></span>  
  
## <a name="select-installation-folder-page"></a><span data-ttu-id="5c51d-165">Pagina Selezione cartella di destinazione</span><span class="sxs-lookup"><span data-stu-id="5c51d-165">Select Installation Folder Page</span></span>  
 <span data-ttu-id="5c51d-166">Usare la pagina **Selezione cartella di installazione** per specificare la cartella del file system in cui installare i pacchetti e le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="5c51d-166">Use the **Select Installation Folder** page to specify the file system folder in which to install the packages and their dependencies.</span></span>  
  
### <a name="options"></a><span data-ttu-id="5c51d-167">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5c51d-167">Options</span></span>  
 <span data-ttu-id="5c51d-168">**Cartella**</span><span class="sxs-lookup"><span data-stu-id="5c51d-168">**Folder**</span></span>  
 <span data-ttu-id="5c51d-169">Consente di specificare il percorso e la cartella in cui copiare il pacchetto e le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="5c51d-169">Specify the path and folder in which to copy the package and its dependencies.</span></span>  
  
 <span data-ttu-id="5c51d-170">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="5c51d-170">**Browse**</span></span>  
 <span data-ttu-id="5c51d-171">Consente di selezionare la cartella di destinazione utilizzando la finestra di dialogo **Sfoglia cartella** .</span><span class="sxs-lookup"><span data-stu-id="5c51d-171">Browse to the target folder by using the **Browse For Folder** dialog box.</span></span>  
  
 <span data-ttu-id="5c51d-172">**Avanti**</span><span class="sxs-lookup"><span data-stu-id="5c51d-172">**Next**</span></span>  
 <span data-ttu-id="5c51d-173">Consente di passare alla pagina successiva della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5c51d-173">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="5c51d-174">**Fine**</span><span class="sxs-lookup"><span data-stu-id="5c51d-174">**Finish**</span></span>  
 <span data-ttu-id="5c51d-175">Consente di passare alla pagina Completamento Installazione guidata pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-175">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="5c51d-176">Utilizzare questa opzione se sono state controllate le scelte effettuate nelle pagine precedenti della procedura guidata e si è certi di aver specificato tutte le opzioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="5c51d-176">Use this option if you have backtracked through the wizard pages to revise your choices and if have specified all of the required options.</span></span>  
  
## <a name="specify-target-sql-server-page"></a><span data-ttu-id="5c51d-177">Pagina Impostazione istanza di SQL Server di destinazione</span><span class="sxs-lookup"><span data-stu-id="5c51d-177">Specify Target SQL Server Page</span></span>  
 <span data-ttu-id="5c51d-178">Usare la pagina **Impostazione istanza di SQL Server di destinazione** per specificare le opzioni per la distribuzione del pacchetto in un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c51d-178">Use the **Specify Target SQL Server** page to specify options for deploying the package to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="options"></a><span data-ttu-id="5c51d-179">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5c51d-179">Options</span></span>  
 <span data-ttu-id="5c51d-180">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="5c51d-180">**Server name**</span></span>  
 <span data-ttu-id="5c51d-181">Consente di specificare il nome del server in cui distribuire i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-181">Specify the name of the server to deploy the packages to.</span></span>  
  
 <span data-ttu-id="5c51d-182">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="5c51d-182">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="5c51d-183">Consente di specificare se utilizzare l'autenticazione di Windows per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="5c51d-183">Specify whether to use Windows Authentication to log on to the server.</span></span> <span data-ttu-id="5c51d-184">Per una maggiore sicurezza è consigliabile utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="5c51d-184">Windows Authentication is recommended for better security.</span></span>  
  
 <span data-ttu-id="5c51d-185">**Usa autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="5c51d-185">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="5c51d-186">Consente di specificare se il pacchetto deve utilizzare l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="5c51d-186">Specify whether the package should use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to log on to the server.</span></span> <span data-ttu-id="5c51d-187">Se si usa l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , è necessario specificare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="5c51d-187">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="5c51d-188">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="5c51d-188">**User name**</span></span>  
 <span data-ttu-id="5c51d-189">Consente di specificare un nome utente.</span><span class="sxs-lookup"><span data-stu-id="5c51d-189">Specify a user name.</span></span>  
  
 <span data-ttu-id="5c51d-190">**Password**</span><span class="sxs-lookup"><span data-stu-id="5c51d-190">**Password**</span></span>  
 <span data-ttu-id="5c51d-191">Consente di specificare una password.</span><span class="sxs-lookup"><span data-stu-id="5c51d-191">Specify a password.</span></span>  
  
 <span data-ttu-id="5c51d-192">**Percorso pacchetto**</span><span class="sxs-lookup"><span data-stu-id="5c51d-192">**Package path**</span></span>  
 <span data-ttu-id="5c51d-193">Consente di specificare il nome della cartella logica o immettere "/" per la cartella predefinita.</span><span class="sxs-lookup"><span data-stu-id="5c51d-193">Specify the name of the logical folder, or enter "/" for the default folder.</span></span>  
  
 <span data-ttu-id="5c51d-194">Per selezionare la cartella nella finestra di dialogo **Pacchetto SSIS** , fare clic su Sfoglia (...). Tuttavia, la finestra di dialogo non consente di selezionare la cartella predefinita.</span><span class="sxs-lookup"><span data-stu-id="5c51d-194">To select the folder in the **SSIS Package** dialog box, click browse (...). However, the dialog box does not provide a means to select the default folder.</span></span> <span data-ttu-id="5c51d-195">Se si desidera utilizzare la cartella predefinita, è necessario immettere "/" nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="5c51d-195">If you want to use the default folder, you have to enter "/" in the text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c51d-196">Se non si immette un percorso del pacchetto valido, viene visualizzato il messaggio di errore seguente: "Uno o più argomenti non sono validi."</span><span class="sxs-lookup"><span data-stu-id="5c51d-196">If you do not enter a valid package path, the following error message appears: "One or more arguments are invalid."</span></span>  
  
 <span data-ttu-id="5c51d-197">**Usa l'archiviazione su server per la crittografia**</span><span class="sxs-lookup"><span data-stu-id="5c51d-197">**Rely on server storage for encryption**</span></span>  
 <span data-ttu-id="5c51d-198">Selezionare questa opzione per usare le funzionalità di sicurezza del [!INCLUDE[ssDE](../includes/ssde-md.md)] per proteggere i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-198">Select to use security features of the [!INCLUDE[ssDE](../includes/ssde-md.md)] to help secure the packages.</span></span>  
  
 <span data-ttu-id="5c51d-199">**Avanti**</span><span class="sxs-lookup"><span data-stu-id="5c51d-199">**Next**</span></span>  
 <span data-ttu-id="5c51d-200">Consente di passare alla pagina successiva della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5c51d-200">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="5c51d-201">**Fine**</span><span class="sxs-lookup"><span data-stu-id="5c51d-201">**Finish**</span></span>  
 <span data-ttu-id="5c51d-202">Consente di passare alla pagina Completamento Installazione guidata pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-202">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="5c51d-203">Utilizzare questa opzione se sono state controllate le scelte effettuate nelle pagine precedenti della procedura guidata e si è certi di avere specificato tutte le opzioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="5c51d-203">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="finish-the-package-installation-page"></a><span data-ttu-id="5c51d-204">Pagina Completamento Installazione guidata pacchetti</span><span class="sxs-lookup"><span data-stu-id="5c51d-204">Finish the Package Installation Page</span></span>  
 <span data-ttu-id="5c51d-205">Usare la pagina **Completamento Installazione guidata pacchetti** per visualizzare un riepilogo dei risultati dell'installazione dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c51d-205">Use the **Finish the Package Installation Wizard** page to view a summary of the package installation results.</span></span> <span data-ttu-id="5c51d-206">In questa pagina sono specificati dettagli quali il nome del progetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] distribuito, i pacchetti installati, i file di configurazione e il percorso di installazione.</span><span class="sxs-lookup"><span data-stu-id="5c51d-206">This page provides details such as the name of the deployed [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, the packages that were installed, the configuration files, and the installation location.</span></span>  
  
 <span data-ttu-id="5c51d-207">**Fine**</span><span class="sxs-lookup"><span data-stu-id="5c51d-207">**Finish**</span></span>  
 <span data-ttu-id="5c51d-208">Fare clic su **Fine**per uscire dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5c51d-208">Exit the wizard by clicking **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c51d-209">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c51d-209">See Also</span></span>  
 [<span data-ttu-id="5c51d-210">Distribuzione di pacchetti &#40;&#41;SSIS</span><span class="sxs-lookup"><span data-stu-id="5c51d-210">Package Deployment &#40;SSIS&#41;</span></span>](packages/legacy-package-deployment-ssis.md)  
  
  
