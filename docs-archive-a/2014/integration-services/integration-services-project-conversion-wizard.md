---
title: Conversione guidata progetto Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.migrationwizard.f1
ms.assetid: a192b094-4d0f-4c21-b911-460ec844a49f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c47dc8ed1d0485a62128be732cc34de1dca35740
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628878"
---
# <a name="integration-services-project-conversion-wizard"></a><span data-ttu-id="75d07-102">Conversione guidata progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="75d07-102">Integration Services Project Conversion Wizard</span></span>
  <span data-ttu-id="75d07-103">Con la **Conversione guidata progetto di Integration Services** è possibile convertire un progetto nel modello di distribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-103">The **Integration Services Project Conversion Wizard** converts a project to the project deployment model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75d07-104">Se nel progetto sono incluse una o più origini dati, queste ultime vengono rimosse al completamento della conversione del progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-104">If the project contains one or more datasources, the datasources are removed when the project conversion is completed.</span></span> <span data-ttu-id="75d07-105">Per creare una connessione a un'origine dati che può essere condivisa dai pacchetti nel progetto, aggiungere una gestione connessione al livello del progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-105">To create a connection to a data source that can be shared by the packages in the project, add a connection manager at the project level.</span></span> <span data-ttu-id="75d07-106">Per altre informazioni, vedere [aggiungere, eliminare o condividere una gestione connessione in un pacchetto](../../2014/integration-services/add-delete-or-share-a-connection-manager-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="75d07-106">For more information, see [Add, Delete, or Share a Connection Manager in a Package](../../2014/integration-services/add-delete-or-share-a-connection-manager-in-a-package.md).</span></span>  
  
 <span data-ttu-id="75d07-107">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="75d07-107">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="75d07-108">Aprire la Conversione guidata progetti di Integration Services</span><span class="sxs-lookup"><span data-stu-id="75d07-108">Open the Integration Services Project Conversion Wizard</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="75d07-109">Impostare le opzioni nella pagina Individua pacchetti</span><span class="sxs-lookup"><span data-stu-id="75d07-109">Set Options on the Locate Packages Page</span></span>](#locate)  
  
-   [<span data-ttu-id="75d07-110">Impostare le opzioni nella pagina Seleziona pacchetti</span><span class="sxs-lookup"><span data-stu-id="75d07-110">Set Options on the Select Packages Page</span></span>](#selectPackages)  
  
-   [<span data-ttu-id="75d07-111">Impostare le opzioni nella pagina Seleziona destinazione</span><span class="sxs-lookup"><span data-stu-id="75d07-111">Set Options on the Select Destination Page</span></span>](#destination)  
  
-   [<span data-ttu-id="75d07-112">Impostare le opzioni nella pagina Specificare le proprietà del progetto</span><span class="sxs-lookup"><span data-stu-id="75d07-112">Set Options on the Specify Project Properties Page</span></span>](#projectProperties)  
  
-   [<span data-ttu-id="75d07-113">Impostare le opzioni nella pagina Aggiorna attività Esegui pacchetto</span><span class="sxs-lookup"><span data-stu-id="75d07-113">Set Options on the Update Execute Package Task Page</span></span>](#executePackage)  
  
-   [<span data-ttu-id="75d07-114">Impostare le opzioni nella pagina Seleziona configurazioni</span><span class="sxs-lookup"><span data-stu-id="75d07-114">Set Options on the Select Configurations Page</span></span>](#configurations)  
  
-   [<span data-ttu-id="75d07-115">Impostare le opzioni nella pagina Crea parametri</span><span class="sxs-lookup"><span data-stu-id="75d07-115">Set Options on the Create Parameters Page</span></span>](#createParameters)  
  
-   [<span data-ttu-id="75d07-116">Impostare le opzioni nella pagina Configura parametri</span><span class="sxs-lookup"><span data-stu-id="75d07-116">Set Options on the Configure Parameters Page</span></span>](#configureParameters)  
  
-   [<span data-ttu-id="75d07-117">Impostare le opzioni nella pagina Verifica</span><span class="sxs-lookup"><span data-stu-id="75d07-117">Set the Options on the Review page</span></span>](#review)  
  
-   [<span data-ttu-id="75d07-118">Impostare le opzioni nella pagina Esegui conversione</span><span class="sxs-lookup"><span data-stu-id="75d07-118">Set the Options on the Perform Conversion</span></span>](#conversion)  
  
##  <a name="open-the-integration-services-project-conversion-wizard"></a><a name="open_dialog"></a><span data-ttu-id="75d07-119">Aprire la conversione guidata progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="75d07-119">Open the Integration Services Project Conversion Wizard</span></span>  
 <span data-ttu-id="75d07-120">Eseguire una delle operazioni seguenti per aprire la **Conversione guidata progetto di Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="75d07-120">Do one of the following to open the **Integration Services Project Conversion** Wizard.</span></span>  
  
-   <span data-ttu-id="75d07-121">Aprire il progetto in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], quindi in Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere **Converti nel modello di distribuzione del progetto**.</span><span class="sxs-lookup"><span data-stu-id="75d07-121">Open the project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], and then in Solution Explorer, right-click the project and click **Convert to Project Deployment Model**.</span></span>  
  
-   <span data-ttu-id="75d07-122">Da Esplora oggetti di [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]fare clic con il pulsante destro del mouse sul nodo **Progetti** e selezionare **Importa pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="75d07-122">From Object Explorer in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], right-click the **Projects** node and select **Import Packages**.</span></span>  
  
 <span data-ttu-id="75d07-123">Le diverse attività di conversione eseguite dalla **Conversione guidata progetto di Integration Services** variano a seconda che la procedura guidata venga eseguita da [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] o da [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75d07-123">Depending on whether you run the **Integration Services Project Conversion Wizard** from [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] or from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], the wizard performs different conversion tasks.</span></span> <span data-ttu-id="75d07-124">Per altre informazioni, vedere [Distribuire progetti nel server Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="75d07-124">For more information, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
##  <a name="set-options-on-the-locate-packages-page"></a><a name="locate"></a><span data-ttu-id="75d07-125">Impostare le opzioni nella pagina Individua pacchetti</span><span class="sxs-lookup"><span data-stu-id="75d07-125">Set Options on the Locate Packages Page</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75d07-126">La pagina **Individua pacchetti** è disponibile solo quando si esegue la procedura guidata da [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75d07-126">The **Locate Packages** page is available only when you run the wizard from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="75d07-127">L'opzione seguente viene visualizzata nella pagina quando si seleziona **File system** nell'elenco a discesa **Origine** .</span><span class="sxs-lookup"><span data-stu-id="75d07-127">The following option displays on the page when you select **File system** in the **Source** drop-down list.</span></span> <span data-ttu-id="75d07-128">Selezionare questa opzione se il pacchetto si trova nel file system.</span><span class="sxs-lookup"><span data-stu-id="75d07-128">Select this option when the package is resides in the file system.</span></span>  
  
 <span data-ttu-id="75d07-129">**Cartella**</span><span class="sxs-lookup"><span data-stu-id="75d07-129">**Folder**</span></span>  
 <span data-ttu-id="75d07-130">Digitare il percorso del pacchetto o passare al pacchetto facendo clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="75d07-130">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="75d07-131">Le opzioni seguenti vengono visualizzate nella pagina quando si seleziona **Archivio pacchetti SSIS** nell'elenco a discesa **Origine**.</span><span class="sxs-lookup"><span data-stu-id="75d07-131">The following options display on the page when you select **SSIS Package Store** in the **Source** drop-down list.</span></span> <span data-ttu-id="75d07-132">Per altre informazioni sull'archiviazione dei pacchetti, vedere [Gestione dei pacchetti &#40;servizio SSIS&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="75d07-132">For more information about the package store, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span>  
  
 <span data-ttu-id="75d07-133">**Server**</span><span class="sxs-lookup"><span data-stu-id="75d07-133">**Server**</span></span>  
 <span data-ttu-id="75d07-134">Digitare il nome del server o selezionare il server.</span><span class="sxs-lookup"><span data-stu-id="75d07-134">Type the server name or select the server.</span></span>  
  
 <span data-ttu-id="75d07-135">**Cartella**</span><span class="sxs-lookup"><span data-stu-id="75d07-135">**Folder**</span></span>  
 <span data-ttu-id="75d07-136">Digitare il percorso del pacchetto o passare al pacchetto facendo clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="75d07-136">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="75d07-137">Le opzioni seguenti vengono visualizzate nella pagina quando si seleziona **Microsoft SQL Server** nell'elenco a discesa **Origine** .</span><span class="sxs-lookup"><span data-stu-id="75d07-137">The following options display on the page when you select **Microsoft SQL Server** in the **Source** drop-down list.</span></span> <span data-ttu-id="75d07-138">Selezionare questa opzione se il pacchetto si trova in Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75d07-138">Select this option when the package resides in Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="75d07-139">**Server**</span><span class="sxs-lookup"><span data-stu-id="75d07-139">**Server**</span></span>  
 <span data-ttu-id="75d07-140">Digitare il nome del server o selezionare il server.</span><span class="sxs-lookup"><span data-stu-id="75d07-140">Type the server name or select the server.</span></span>  
  
 <span data-ttu-id="75d07-141">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="75d07-141">**Use Windows authentication**</span></span>  
 <span data-ttu-id="75d07-142">Tale modalità consente di connettersi tramite un account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="75d07-142">Microsoft Windows Authentication mode allows a user to connect through a Windows user account.</span></span> <span data-ttu-id="75d07-143">Se si utilizza l'autenticazione di Windows non è necessario specificare un nome utente o una password.</span><span class="sxs-lookup"><span data-stu-id="75d07-143">If you use Windows Authentication, you do not need to provide a user name or password.</span></span>  
  
 <span data-ttu-id="75d07-144">**Usa autenticazione SQL Server**</span><span class="sxs-lookup"><span data-stu-id="75d07-144">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="75d07-145">Quando un utente si connette da una connessione non trusted con un nome di account di accesso e una password specificati, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] autentica la connessione controllando se è stato impostato un account di accesso di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e se la password specificata corrisponde a quella registrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="75d07-145">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authenticates the connection by checking to see if a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="75d07-146">Se non è stato impostato alcun account di accesso di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , l'autenticazione non viene completata e viene segnalato un errore all'utente.</span><span class="sxs-lookup"><span data-stu-id="75d07-146">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
 <span data-ttu-id="75d07-147">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="75d07-147">**User name**</span></span>  
 <span data-ttu-id="75d07-148">Specificare un nome utente quando si utilizza l'autenticazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="75d07-148">Specify a user name when you are using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="75d07-149">**Password**</span><span class="sxs-lookup"><span data-stu-id="75d07-149">**Password**</span></span>  
 <span data-ttu-id="75d07-150">Specificare una password quando si utilizza l'autenticazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="75d07-150">Provide the password when you are using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="75d07-151">**Cartella**</span><span class="sxs-lookup"><span data-stu-id="75d07-151">**Folder**</span></span>  
 <span data-ttu-id="75d07-152">Digitare il percorso del pacchetto o passare al pacchetto facendo clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="75d07-152">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
##  <a name="set-options-on-the-select-packages-page"></a><a name="selectPackages"></a><span data-ttu-id="75d07-153">Impostare le opzioni nella pagina Seleziona pacchetti</span><span class="sxs-lookup"><span data-stu-id="75d07-153">Set Options on the Select Packages Page</span></span>  
 <span data-ttu-id="75d07-154">**Nome pacchetto**</span><span class="sxs-lookup"><span data-stu-id="75d07-154">**Package Name**</span></span>  
 <span data-ttu-id="75d07-155">Viene elencato il file del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-155">Lists the package file.</span></span>  
  
 <span data-ttu-id="75d07-156">**Status**</span><span class="sxs-lookup"><span data-stu-id="75d07-156">**Status**</span></span>  
 <span data-ttu-id="75d07-157">Viene indicato se un pacchetto è pronto per la conversione nel modello di distribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-157">Indicates whether a package is ready to convert to the project deployment model.</span></span>  
  
 <span data-ttu-id="75d07-158">**Message**</span><span class="sxs-lookup"><span data-stu-id="75d07-158">**Message**</span></span>  
 <span data-ttu-id="75d07-159">Viene visualizzato un messaggio associato al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-159">Displays a message associated with the package.</span></span>  
  
 <span data-ttu-id="75d07-160">**Password**</span><span class="sxs-lookup"><span data-stu-id="75d07-160">**Password**</span></span>  
 <span data-ttu-id="75d07-161">Viene visualizzata una password associata al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-161">Displays a password associated with the package.</span></span> <span data-ttu-id="75d07-162">Il testo della password è nascosto.</span><span class="sxs-lookup"><span data-stu-id="75d07-162">The password text is hidden.</span></span>  
  
 <span data-ttu-id="75d07-163">**Applica a selezione**</span><span class="sxs-lookup"><span data-stu-id="75d07-163">**Apply to selection**</span></span>  
 <span data-ttu-id="75d07-164">Fare clic per applicare la password nella casella di testo **Password** ai pacchetti selezionati.</span><span class="sxs-lookup"><span data-stu-id="75d07-164">Click to apply the password in the **Password** text box, to the selected package or packages.</span></span>  
  
 <span data-ttu-id="75d07-165">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="75d07-165">**Refresh**</span></span>  
 <span data-ttu-id="75d07-166">Viene aggiornato l'elenco dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="75d07-166">Refreshes the list of packages.</span></span>  
  
##  <a name="set-options-on-the-select-destination-page"></a><a name="destination"></a><span data-ttu-id="75d07-167">Impostare le opzioni nella pagina Seleziona destinazione</span><span class="sxs-lookup"><span data-stu-id="75d07-167">Set Options on the Select Destination Page</span></span>  
 <span data-ttu-id="75d07-168">In questa pagina specificare il nome e il percorso di un nuovo file di distribuzione progetto (con estensione ispac) o selezionare un file esistente.</span><span class="sxs-lookup"><span data-stu-id="75d07-168">On this page, specify the name and path for a new project deployment file (.ispac) or select an existing file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75d07-169">La pagina **Seleziona destinazione** è disponibile solo quando si esegue la procedura guidata da [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75d07-169">The **Select Destination** page is available only when you run the wizard from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="75d07-170">**Percorso di output**</span><span class="sxs-lookup"><span data-stu-id="75d07-170">**Output path**</span></span>  
 <span data-ttu-id="75d07-171">Digitare il percorso del file di distribuzione o passare al file facendo clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="75d07-171">Type the path for the deployment file or navigate to the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="75d07-172">**Nome progetto**</span><span class="sxs-lookup"><span data-stu-id="75d07-172">**Project name**</span></span>  
 <span data-ttu-id="75d07-173">Digitare il nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-173">Type the project name.</span></span>  
  
 <span data-ttu-id="75d07-174">**Livello di protezione**</span><span class="sxs-lookup"><span data-stu-id="75d07-174">**Protection level**</span></span>  
 <span data-ttu-id="75d07-175">Selezionare il livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="75d07-175">Select the protection level.</span></span> <span data-ttu-id="75d07-176">Per altre informazioni, vedere [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="75d07-176">For more information, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
 <span data-ttu-id="75d07-177">**Descrizione progetto**</span><span class="sxs-lookup"><span data-stu-id="75d07-177">**Project description**</span></span>  
 <span data-ttu-id="75d07-178">Digitare una descrizione facoltativa per il progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-178">Type an optional description for the project.</span></span>  
  
##  <a name="set-options-on-the-specify-project-properties-page"></a><a name="projectProperties"></a><span data-ttu-id="75d07-179">Impostare le opzioni nella pagina specifica proprietà del progetto</span><span class="sxs-lookup"><span data-stu-id="75d07-179">Set Options on the Specify Project Properties Page</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75d07-180">La pagina **Specifica proprietà del progetto** è disponibile solo quando si esegue la procedura guidata da [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75d07-180">The **Specify Project Properties** page is available only when you run the wizard from [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="75d07-181">**Nome progetto**</span><span class="sxs-lookup"><span data-stu-id="75d07-181">**Project name**</span></span>  
 <span data-ttu-id="75d07-182">Viene elencato il nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-182">Lists the project name.</span></span>  
  
 <span data-ttu-id="75d07-183">**Livello di protezione**</span><span class="sxs-lookup"><span data-stu-id="75d07-183">**Protection level**</span></span>  
 <span data-ttu-id="75d07-184">Selezionare un livello di protezione per i pacchetti contenuti nel progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-184">Select a protection level for the packages contained in the project.</span></span> <span data-ttu-id="75d07-185">Per altre informazioni sui livelli di protezione, vedere [Controllo dell'accesso per dati sensibili nei pacchetti](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="75d07-185">For more information about protection levels, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
 <span data-ttu-id="75d07-186">**Descrizione progetto**</span><span class="sxs-lookup"><span data-stu-id="75d07-186">**Project description**</span></span>  
 <span data-ttu-id="75d07-187">Digitare una descrizione facoltativa del progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-187">Type an optional project description.</span></span>  
  
##  <a name="set-options-on-the-update-execute-package-task-page"></a><a name="executePackage"></a><span data-ttu-id="75d07-188">Impostare le opzioni nella pagina Aggiorna attività Esegui pacchetto</span><span class="sxs-lookup"><span data-stu-id="75d07-188">Set Options on the Update Execute Package Task Page</span></span>  
 <span data-ttu-id="75d07-189">Aggiornare le attività Esegui pacchetto contenute nei pacchetti al fine di utilizzare un riferimento basato sul progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-189">Update Execute Package Tasks contain in the packages, to use a project-based reference.</span></span> <span data-ttu-id="75d07-190">Per altre informazioni, vedere [Editor attività Esegui pacchetto](../../2014/integration-services/execute-package-task-editor.md).</span><span class="sxs-lookup"><span data-stu-id="75d07-190">For more information, see [Execute Package Task Editor](../../2014/integration-services/execute-package-task-editor.md).</span></span>  
  
 <span data-ttu-id="75d07-191">**Pacchetto padre**</span><span class="sxs-lookup"><span data-stu-id="75d07-191">**Parent Package**</span></span>  
 <span data-ttu-id="75d07-192">Viene elencato il nome del pacchetto tramite cui viene eseguito il pacchetto figlio utilizzando l'attività Esegui pacchetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-192">Lists the name of the package that executes the child package using the Execute Package task.</span></span>  
  
 <span data-ttu-id="75d07-193">**Nome attività**</span><span class="sxs-lookup"><span data-stu-id="75d07-193">**Task name**</span></span>  
 <span data-ttu-id="75d07-194">Viene elencato il nome dell'attività Esegui pacchetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-194">Lists the name of the Execute Package task.</span></span>  
  
 <span data-ttu-id="75d07-195">**Riferimento originale**</span><span class="sxs-lookup"><span data-stu-id="75d07-195">**Original reference**</span></span>  
 <span data-ttu-id="75d07-196">Viene elencato il percorso corrente del pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="75d07-196">Lists the current path of the child package.</span></span>  
  
 <span data-ttu-id="75d07-197">**Assegna riferimento**</span><span class="sxs-lookup"><span data-stu-id="75d07-197">**Assign reference**</span></span>  
 <span data-ttu-id="75d07-198">Selezionare un pacchetto figlio archiviato nel progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-198">Select a child package stored in the project.</span></span>  
  
##  <a name="set-options-on-the-select-configurations-page"></a><a name="configurations"></a><span data-ttu-id="75d07-199">Impostare le opzioni nella pagina Seleziona configurazioni</span><span class="sxs-lookup"><span data-stu-id="75d07-199">Set Options on the Select Configurations Page</span></span>  
 <span data-ttu-id="75d07-200">Selezionare le configurazioni del pacchetto che si desidera sostituire con i parametri.</span><span class="sxs-lookup"><span data-stu-id="75d07-200">Select the package configurations that you want to replace with parameters.</span></span>  
  
 <span data-ttu-id="75d07-201">**Pacchetto**</span><span class="sxs-lookup"><span data-stu-id="75d07-201">**Package**</span></span>  
 <span data-ttu-id="75d07-202">Viene elencato il file del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-202">Lists the package file.</span></span>  
  
 <span data-ttu-id="75d07-203">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="75d07-203">**Type**</span></span>  
 <span data-ttu-id="75d07-204">Viene elencato il tipo di configurazione, ad esempio un file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="75d07-204">Lists the type of configuration, such as an XML configuration file.</span></span>  
  
 <span data-ttu-id="75d07-205">**Stringa di configurazione**</span><span class="sxs-lookup"><span data-stu-id="75d07-205">**Configuration String**</span></span>  
 <span data-ttu-id="75d07-206">Viene elencato il percorso del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="75d07-206">Lists the path of the configuration file.</span></span>  
  
 <span data-ttu-id="75d07-207">**Status**</span><span class="sxs-lookup"><span data-stu-id="75d07-207">**Status**</span></span>  
 <span data-ttu-id="75d07-208">Viene visualizzato un messaggio di stato per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="75d07-208">Displays a status message for the configuration.</span></span> <span data-ttu-id="75d07-209">Fare clic sul messaggio per visualizzare il relativo testo completo.</span><span class="sxs-lookup"><span data-stu-id="75d07-209">Click the message to view the entire message text.</span></span>  
  
 <span data-ttu-id="75d07-210">**Aggiungi configurazioni**</span><span class="sxs-lookup"><span data-stu-id="75d07-210">**Add Configurations**</span></span>  
 <span data-ttu-id="75d07-211">Aggiungere le configurazioni del pacchetto contenute in altri progetti all'elenco delle configurazioni disponibili che si desidera sostituire con i parametri.</span><span class="sxs-lookup"><span data-stu-id="75d07-211">Add package configurations contained in other projects to the list of available configurations that you want to replace with parameters.</span></span> <span data-ttu-id="75d07-212">È possibile selezionare le configurazioni archiviate in un file system o in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="75d07-212">You can select configurations stored in a file system or stored in SQL Server.</span></span>  
  
 <span data-ttu-id="75d07-213">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="75d07-213">**Refresh**</span></span>  
 <span data-ttu-id="75d07-214">Fare clic su questa opzione per aggiornare l'elenco delle configurazioni.</span><span class="sxs-lookup"><span data-stu-id="75d07-214">Click to refresh the list of configurations.</span></span>  
  
 <span data-ttu-id="75d07-215">**Rimuovi configurazioni da tutti i pacchetti dopo la conversione**</span><span class="sxs-lookup"><span data-stu-id="75d07-215">**Remove configurations from all packages after conversion**</span></span>  
 <span data-ttu-id="75d07-216">È consigliabile rimuovere tutte le configurazioni dal progetto selezionando questa opzione.</span><span class="sxs-lookup"><span data-stu-id="75d07-216">It is recommended that you remove all configurations from the project by selecting this option.</span></span>  
  
 <span data-ttu-id="75d07-217">Se non si seleziona questa opzione, vengono rimosse solo le configurazioni selezionate per la sostituzione con i parametri.</span><span class="sxs-lookup"><span data-stu-id="75d07-217">If you don't select this option, only the configurations that you selected to replace with parameters are removed.</span></span>  
  
##  <a name="set-options-on-the-create-parameters-page"></a><a name="createParameters"></a><span data-ttu-id="75d07-218">Impostare le opzioni nella pagina Crea parametri</span><span class="sxs-lookup"><span data-stu-id="75d07-218">Set Options on the Create Parameters Page</span></span>  
 <span data-ttu-id="75d07-219">Selezionare il nome e l'ambito del parametro per ogni proprietà di configurazione.</span><span class="sxs-lookup"><span data-stu-id="75d07-219">Select the parameter name and scope for each configuration property.</span></span>  
  
 <span data-ttu-id="75d07-220">**Pacchetto**</span><span class="sxs-lookup"><span data-stu-id="75d07-220">**Package**</span></span>  
 <span data-ttu-id="75d07-221">Viene elencato il file del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-221">Lists the package file.</span></span>  
  
 <span data-ttu-id="75d07-222">**Nome parametro**</span><span class="sxs-lookup"><span data-stu-id="75d07-222">**Parameter Name**</span></span>  
 <span data-ttu-id="75d07-223">Viene elencato il nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="75d07-223">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="75d07-224">**Ambito**</span><span class="sxs-lookup"><span data-stu-id="75d07-224">**Scope**</span></span>  
 <span data-ttu-id="75d07-225">Selezionare l'ambito del parametro, vale a dire pacchetto o progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-225">Select the scope of the parameter, either package or project.</span></span>  
  
##  <a name="set-options-on-the-configure-parameters-page"></a><a name="configureParameters"></a><span data-ttu-id="75d07-226">Impostare le opzioni nella pagina Configura parametri</span><span class="sxs-lookup"><span data-stu-id="75d07-226">Set Options on the Configure Parameters Page</span></span>  
 <span data-ttu-id="75d07-227">**Nome**</span><span class="sxs-lookup"><span data-stu-id="75d07-227">**Name**</span></span>  
 <span data-ttu-id="75d07-228">Viene elencato il nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="75d07-228">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="75d07-229">**Ambito**</span><span class="sxs-lookup"><span data-stu-id="75d07-229">**Scope**</span></span>  
 <span data-ttu-id="75d07-230">Viene elencato l'ambito del parametro.</span><span class="sxs-lookup"><span data-stu-id="75d07-230">Lists the scope of the parameter.</span></span>  
  
 <span data-ttu-id="75d07-231">**Valore**</span><span class="sxs-lookup"><span data-stu-id="75d07-231">**Value**</span></span>  
 <span data-ttu-id="75d07-232">Viene elencato il valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="75d07-232">Lists the parameter value.</span></span>  
  
 <span data-ttu-id="75d07-233">Fare clic sul pulsante con i puntini di sospensione accanto al campo del valore per configurare le proprietà del parametro.</span><span class="sxs-lookup"><span data-stu-id="75d07-233">Click the ellipsis button next to the value field to configure the parameter properties.</span></span>  
  
 <span data-ttu-id="75d07-234">Nella finestra di dialogo **Imposta dettagli parametri** è possibile modificare il valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="75d07-234">In the **Set Parameter Details** dialog box, you can edit the parameter value.</span></span> <span data-ttu-id="75d07-235">È anche possibile specificare se il valore del parametro deve essere fornito quando si esegue il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-235">You can also specify whether the parameter value must be provided when you run the package.</span></span>  
  
 <span data-ttu-id="75d07-236">È possibile modificare il valore nella pagina **Parametri** della finestra di dialogo **Configura** in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]facendo clic sul pulsante Sfoglia accanto al parametro.</span><span class="sxs-lookup"><span data-stu-id="75d07-236">You can modify value in the **Parameters** page of the **Configure** dialog box in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], by clicking the browse button next to the parameter.</span></span> <span data-ttu-id="75d07-237">Viene visualizzata la finestra di dialogo **Imposta valore parametro** .</span><span class="sxs-lookup"><span data-stu-id="75d07-237">The **Set Parameter Value** dialog box appears.</span></span>  
  
 <span data-ttu-id="75d07-238">Nella finestra di dialogo **Imposta dettagli parametri** sono inoltre elencati il tipo di dati del valore del parametro e l'origine del parametro.</span><span class="sxs-lookup"><span data-stu-id="75d07-238">The **Set Parameter Details** dialog box also lists the data type of the parameter value and the origin of the parameter.</span></span>  
  
##  <a name="set-the-options-on-the-review-page"></a><a name="review"></a><span data-ttu-id="75d07-239">Impostare le opzioni nella pagina Verifica</span><span class="sxs-lookup"><span data-stu-id="75d07-239">Set the Options on the Review page</span></span>  
 <span data-ttu-id="75d07-240">Utilizzare la pagina **Verifica** per confermare le opzioni selezionate per la conversione del progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-240">Use the **Review** page to confirm the options that you've selected for the conversion of the project.</span></span>  
  
 <span data-ttu-id="75d07-241">**Indietro**</span><span class="sxs-lookup"><span data-stu-id="75d07-241">**Previous**</span></span>  
 <span data-ttu-id="75d07-242">Fare clic su questo pulsante per modificare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="75d07-242">Click to change an option.</span></span>  
  
 <span data-ttu-id="75d07-243">**Converti**</span><span class="sxs-lookup"><span data-stu-id="75d07-243">**Convert**</span></span>  
 <span data-ttu-id="75d07-244">Fare clic su questa opzione per convertire il progetto nel modello di distribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-244">Click to convert the project to the project deployment model.</span></span>  
  
##  <a name="set-the-options-on-the-perform-conversion"></a><a name="conversion"></a><span data-ttu-id="75d07-245">Impostare le opzioni nella conversione di esecuzione</span><span class="sxs-lookup"><span data-stu-id="75d07-245">Set the Options on the Perform Conversion</span></span>  
 <span data-ttu-id="75d07-246">Nella pagina Esegui conversione viene mostrato lo stato della conversione del progetto.</span><span class="sxs-lookup"><span data-stu-id="75d07-246">The Perform Conversion page shows status of the project conversion.</span></span>  
  
 <span data-ttu-id="75d07-247">**Azione**</span><span class="sxs-lookup"><span data-stu-id="75d07-247">**Action**</span></span>  
 <span data-ttu-id="75d07-248">Viene elencato un passaggio specifico della conversione.</span><span class="sxs-lookup"><span data-stu-id="75d07-248">Lists a specific conversion step.</span></span>  
  
 <span data-ttu-id="75d07-249">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="75d07-249">**Result**</span></span>  
 <span data-ttu-id="75d07-250">Viene elencato lo stato di ogni passaggio della conversione.</span><span class="sxs-lookup"><span data-stu-id="75d07-250">Lists the status of each conversion step.</span></span> <span data-ttu-id="75d07-251">Fare clic sul messaggio di stato per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="75d07-251">Click the status message for more information.</span></span>  
  
 <span data-ttu-id="75d07-252">La conversione del progetto non viene salvata fino al salvataggio del progetto in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75d07-252">The project conversion is not saved until the project is saved in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="75d07-253">**Salvare il report**</span><span class="sxs-lookup"><span data-stu-id="75d07-253">**Save report**</span></span>  
 <span data-ttu-id="75d07-254">Fare clic su questa opzione per salvare un riepilogo della conversione del progetto in un file con estensione xml.</span><span class="sxs-lookup"><span data-stu-id="75d07-254">Click to save a summary of the project conversion in an .xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75d07-255">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75d07-255">See Also</span></span>  
 [<span data-ttu-id="75d07-256">Distribuire progetti nel server Integration Services</span><span class="sxs-lookup"><span data-stu-id="75d07-256">Deploy Projects to Integration Services Server</span></span>](../../2014/integration-services/deploy-projects-to-integration-services-server.md)  
  
  
