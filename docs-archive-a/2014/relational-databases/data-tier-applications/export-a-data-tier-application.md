---
title: Esportare un'applicazione livello dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.exportdac.settings.f1
- sql12.swb. exportdac.settings.f1
- sql12.swb.exportdac.welcome.f1
- sql12.swb. exportdac.summary.f1
- sql12.swb.exportdac.progress.f1
- sql12.swb.exportdac.summary.f1
- sql12.swb.exportdac.results.f1
- sql12.swb. exportdac.results.f1
helpviewer_keywords:
- How to [DAC], export
- wizard [DAC], export
- export DAC
- data-tier application [SQL Server], export
ms.assetid: 61915bc5-0f5f-45ac-8cfe-3452bc185558
author: stevestein
ms.author: sstein
ms.openlocfilehash: d5e1bbfc5c38dee5e7f29598086d87b680880641
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636198"
---
# <a name="export-a-data-tier-application"></a><span data-ttu-id="45ae9-102">Esportazione di un'applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="45ae9-102">Export a Data-tier Application</span></span>
  <span data-ttu-id="45ae9-103">L'esportazione di un database o di un'applicazione livello dati distribuita crea un file di esportazione contenente sia le definizioni degli oggetti del database che tutti i dati contenuti nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="45ae9-103">Exporting a deployed data-tier application (DAC) or database creates an export file that includes both the definitions of the objects in the database and all of the data contained in the tables.</span></span> <span data-ttu-id="45ae9-104">Il file di esportazione può quindi essere importato in un'altra istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)]o in [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45ae9-104">The export file can then be imported to another instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or to [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="45ae9-105">Le operazioni di importazione ed esportazione possono essere combinate per eseguire la migrazione di un'applicazione livello dati tra istanze o per creare un backup logico o per creare una copia on-premise di un database distribuito in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45ae9-105">The export-import operations can be combined to migrate a DAC between instances, to create a logical backup, or to create an on-premise copy of a database deployed in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="45ae9-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="45ae9-106">Before You Begin</span></span>  
 <span data-ttu-id="45ae9-107">Il processo di esportazione compila un nuovo file di esportazione dell'applicazione livello dati in due fasi.</span><span class="sxs-lookup"><span data-stu-id="45ae9-107">The export process builds a DAC export file in two stages.</span></span>  
  
1.  <span data-ttu-id="45ae9-108">L'esportazione compila una definizione dell'applicazione livello dati nel file di esportazione (file BACPAC) così come un'operazione di estrazione dell'applicazione livello dati compila una definizione dell'applicazione livello dati in un file del pacchetto di applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="45ae9-108">The export builds a DAC definition in the export file - BACPAC file - in the same way a DAC extract builds a DAC definition in a DAC package file.</span></span> <span data-ttu-id="45ae9-109">La definizione del pacchetto di applicazione livello dati esportata include tutti gli oggetti del database corrente.</span><span class="sxs-lookup"><span data-stu-id="45ae9-109">The exported DAC definition includes all of the objects in the current database.</span></span> <span data-ttu-id="45ae9-110">Se il processo di esportazione viene eseguito su un database distribuito originariamente da un'applicazione livello dati, e le modifiche sono state apportate direttamente al database dopo la distribuzione, la definizione esportata corrisponderà al set di oggetti del database e non alle definizioni dell'applicazione livello dati originale.</span><span class="sxs-lookup"><span data-stu-id="45ae9-110">If the export process is run against a database that was originally deployed from a DAC, and changes were made directly to the database after deployment, the exported definition matches the object set in the database, not what was defined in the original DAC.</span></span>  
  
2.  <span data-ttu-id="45ae9-111">L'esportazione consente di eseguire una copia bulk dei dati da tutte le tabelle del database e di incorporarli nel file di esportazione.</span><span class="sxs-lookup"><span data-stu-id="45ae9-111">The export bulk copies out the data from all of the tables in the database and incorporates the data into the export file.</span></span>  
  
 <span data-ttu-id="45ae9-112">Il processo di esportazione imposta la versione dell'applicazione livello dati su 1.0.0.0 e la descrizione dell'applicazione livello dati nel file di esportazione su una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="45ae9-112">The export process sets the DAC version to 1.0.0.0 and the DAC description in the export file to an empty string.</span></span> <span data-ttu-id="45ae9-113">Se il database è stato distribuito da un'applicazione livello dati, la definizione dell'applicazione livello dati nel file di esportazione conterrà il nome assegnato all'applicazione livello dati originale, in caso contrario il nome dell'applicazione livello dati verrà impostato sul nome del database.</span><span class="sxs-lookup"><span data-stu-id="45ae9-113">If the database was deployed from a DAC, the DAC definition in the export file contains the name given to the original DAC, otherwise the DAC name is set to the database name.</span></span>  
  

###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="45ae9-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="45ae9-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="45ae9-115">Un database o un'applicazione livello dati può essere esportata solo da un database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)]o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="45ae9-115">A DAC or database can only be exported from a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span>  
  
 <span data-ttu-id="45ae9-116">Non è possibile esportare un database contenente oggetti non supportati in un'applicazione livello dati o utenti contenuti.</span><span class="sxs-lookup"><span data-stu-id="45ae9-116">You cannot export a database that has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="45ae9-117">Per ulteriori informazioni sui tipi di oggetti supportati in un'applicazione livello dati, vedere [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="45ae9-117">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="45ae9-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="45ae9-118">Permissions</span></span>  
 <span data-ttu-id="45ae9-119">L'esportazione di un'applicazione livello dati richiede almeno le autorizzazioni ALTER ANY LOGIN e VIEW DEFINITION nell'ambito del database, oltre alle autorizzazioni SELECT su **sys.sql_expression_dependencies**.</span><span class="sxs-lookup"><span data-stu-id="45ae9-119">Exporting a DAC requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, as well as SELECT permissions on **sys.sql_expression_dependencies**.</span></span> <span data-ttu-id="45ae9-120">L'esportazione di un'applicazione livello dati può essere effettuata da membri del ruolo predefinito del server securityadmin che sono anche membri del ruolo predefinito del database database_owner nel database dal cui viene esportata l'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="45ae9-120">Exporting a DAC can be done by members of the securityadmin fixed server role who are also members of the database_owner fixed database role in the database from which the DAC is exported.</span></span> <span data-ttu-id="45ae9-121">Possono esportare un'applicazione livello dati anche i membri del ruolo predefinito del server sysadmin o dell'account amministratore di sistema SQL Server predefinito denominato **sa** .</span><span class="sxs-lookup"><span data-stu-id="45ae9-121">Members of the sysadmin fixed server role or the built-in SQL Server system administrator account named **sa** can also export a DAC.</span></span>  
  
##  <a name="using-the-export-data-tier-application-wizard"></a><a name="UsingDeployDACWizard"></a><span data-ttu-id="45ae9-122">Utilizzo della procedura guidata Esporta applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="45ae9-122">Using the Export Data-tier Application Wizard</span></span>  
 <span data-ttu-id="45ae9-123">**Per esportare un'applicazione livello dati tramite una procedura guidata**</span><span class="sxs-lookup"><span data-stu-id="45ae9-123">**To Export a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="45ae9-124">Connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], locale o in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45ae9-124">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], whether on-premise or in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
2.  <span data-ttu-id="45ae9-125">In **Esplora oggetti**espandere il nodo per le istanze da cui esportare l'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="45ae9-125">In **Object Explorer**, expand the node for the instance from which you want to export the DAC.</span></span>  
  
3.  <span data-ttu-id="45ae9-126">Fare clic con il pulsante destro del mouse sul nome del database.</span><span class="sxs-lookup"><span data-stu-id="45ae9-126">Right-click the database name.</span></span>  
  
4.  <span data-ttu-id="45ae9-127">Fare clic su **Attività** e quindi selezionare **Esporta l'applicazione livello dati**.</span><span class="sxs-lookup"><span data-stu-id="45ae9-127">Click **Tasks** and then select **Export Data-tier Application...**</span></span>  
  
5.  <span data-ttu-id="45ae9-128">Completare le finestre di dialogo della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="45ae9-128">Complete the wizard dialogs:</span></span>  
  
    -   [<span data-ttu-id="45ae9-129">Pagina Introduzione</span><span class="sxs-lookup"><span data-stu-id="45ae9-129">Introduction Page</span></span>](#Introduction)  
  
    -   [<span data-ttu-id="45ae9-130">Pagina Impostazioni di esportazione</span><span class="sxs-lookup"><span data-stu-id="45ae9-130">Export Settings Page</span></span>](#Export_settings)  
  
    -   [<span data-ttu-id="45ae9-131">Pagina Convalida</span><span class="sxs-lookup"><span data-stu-id="45ae9-131">Validation Page</span></span>](#Validation)  
  
    -   [<span data-ttu-id="45ae9-132">Pagina Riepilogo</span><span class="sxs-lookup"><span data-stu-id="45ae9-132">Summary Page</span></span>](#Summary)  
  
    -   [<span data-ttu-id="45ae9-133">Pagina di stato</span><span class="sxs-lookup"><span data-stu-id="45ae9-133">Progress Page</span></span>](#Progress)  
  
    -   [<span data-ttu-id="45ae9-134">Pagina Risultati</span><span class="sxs-lookup"><span data-stu-id="45ae9-134">Results Page</span></span>](#Results)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="45ae9-135">Pagina Introduzione</span><span class="sxs-lookup"><span data-stu-id="45ae9-135">Introduction Page</span></span>  
 <span data-ttu-id="45ae9-136">In questa pagina vengono descritti i passaggi per la procedura guidata Esporta l'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="45ae9-136">This page describes the steps for the Export Data-tier Application Wizard.</span></span>  
  
 <span data-ttu-id="45ae9-137">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="45ae9-137">**Options**</span></span>  
  
 <span data-ttu-id="45ae9-138">**Non visualizzare più questa pagina**</span><span class="sxs-lookup"><span data-stu-id="45ae9-138">**Do not show this page again.**</span></span> <span data-ttu-id="45ae9-139">Selezionare la casella di controllo per evitare che la pagina Introduzione venga visualizzata nuovamente in futuro.</span><span class="sxs-lookup"><span data-stu-id="45ae9-139">- Click the check box to stop the Introduction page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="45ae9-140">**Avanti** : consente di passare alla pagina **Selezione pacchetto di applicazione livello dati** .</span><span class="sxs-lookup"><span data-stu-id="45ae9-140">**Next** - Proceeds to the **Select DAC Package** page.</span></span>  
  
 <span data-ttu-id="45ae9-141">**Annulla** : Annulla l'operazione e chiude la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="45ae9-141">**Cancel** - Cancels the operation and closes the Wizard.</span></span>  
  
##  <a name="export-settings-page"></a><a name="Export_settings"></a><span data-ttu-id="45ae9-142">Pagina impostazioni di esportazione</span><span class="sxs-lookup"><span data-stu-id="45ae9-142">Export Settings Page</span></span>  
 <span data-ttu-id="45ae9-143">Utilizzare questa pagina per specificare il percorso in cui creare il file BACPAC.</span><span class="sxs-lookup"><span data-stu-id="45ae9-143">Use this page to specify the location where you want the BACPAC file to be created.</span></span>  
  
-   <span data-ttu-id="45ae9-144">**Salva su disco locale** : crea un file BACPAC in una directory nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="45ae9-144">**Save to local disk** - Creates a BACPAC file in a directory on the local computer.</span></span> <span data-ttu-id="45ae9-145">Fare clic su **Sfoglia** per selezionare un percorso nel computer locale oppure specificare il percorso nell'apposito campo.</span><span class="sxs-lookup"><span data-stu-id="45ae9-145">Click **Browse...** to navigate the local computer, or specify the path in the space provided.</span></span> <span data-ttu-id="45ae9-146">Il nome del percorso deve includere un nome file e l'estensione .bacpac.</span><span class="sxs-lookup"><span data-stu-id="45ae9-146">The path name must include a file name and the .bacpac extension.</span></span>  
  
-   <span data-ttu-id="45ae9-147">**Salva in Azure** : crea un file BACPAC in un contenitore Azure.</span><span class="sxs-lookup"><span data-stu-id="45ae9-147">**Save to Azure** - Creates a BACPAC file in an Azure container.</span></span> <span data-ttu-id="45ae9-148">È necessario connettersi a un contenitore Azure per convalidare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="45ae9-148">You must connect to an Azure container in order to validate this option.</span></span> <span data-ttu-id="45ae9-149">Questa opzione richiede inoltre che si specifichi una directory locale per il file temporaneo.</span><span class="sxs-lookup"><span data-stu-id="45ae9-149">Note that this option also requires that you specify a local directory for the temporary file.</span></span> <span data-ttu-id="45ae9-150">Il file temporaneo verrà creato nel percorso specificato, dove vi rimarrà una volta completata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="45ae9-150">Note that the temporary file will be created at the specified location and will remain there after the operation completes.</span></span>  
  
 <span data-ttu-id="45ae9-151">Per specificare un subset di tabelle da esportare, usare l'opzione **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="45ae9-151">To specify a subset of tables to export, use the **Advanced** option.</span></span>  
  
##  <a name="validation-page"></a><a name="Validation"></a><span data-ttu-id="45ae9-152">Pagina convalida</span><span class="sxs-lookup"><span data-stu-id="45ae9-152">Validation Page</span></span>  
 <span data-ttu-id="45ae9-153">Utilizzare la pagina di convalida per esaminare gli eventuali problemi che bloccano l'operazione.</span><span class="sxs-lookup"><span data-stu-id="45ae9-153">Use the validation page to review any issues that block the operation.</span></span> <span data-ttu-id="45ae9-154">Per continuare, risolvere i problemi che causano il blocco, quindi fare clic su **Ripeti convalida** per assicurarsi che la convalida venga completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="45ae9-154">To continue, resolve blocking issues and then click **Re-run Validation** to ensure that validation is successful.</span></span>  
  
 <span data-ttu-id="45ae9-155">Scegliere **Avanti**per continuare.</span><span class="sxs-lookup"><span data-stu-id="45ae9-155">To continue, click **Next**.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="45ae9-156">Pagina Riepilogo</span><span class="sxs-lookup"><span data-stu-id="45ae9-156">Summary Page</span></span>  
 <span data-ttu-id="45ae9-157">Utilizzare questa pagina per esaminare le impostazioni di origine e destinazione specificate per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="45ae9-157">Use this page to review the specified source and target settings for the operation.</span></span> <span data-ttu-id="45ae9-158">Per completare l'operazione di esportazione usando le impostazioni specificate, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="45ae9-158">To complete the export operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="45ae9-159">Per annullare l'operazione di esportazione e chiudere la procedura guidata, fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="45ae9-159">To cancel the export operation and exit the Wizard, click **Cancel**.</span></span>  
  
##  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="45ae9-160">Pagina Stato</span><span class="sxs-lookup"><span data-stu-id="45ae9-160">Progress Page</span></span>  
 <span data-ttu-id="45ae9-161">In questa pagina viene visualizzato un indicatore di stato che indica lo stato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="45ae9-161">This page displays a progress bar that indicates the status of the operation.</span></span> <span data-ttu-id="45ae9-162">Per visualizzare lo stato dettagliato, fare clic sull'opzione **Visualizza dettagli** .</span><span class="sxs-lookup"><span data-stu-id="45ae9-162">To view detailed status, click the **View details** option.</span></span>  
  
##  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="45ae9-163">Pagina dei risultati</span><span class="sxs-lookup"><span data-stu-id="45ae9-163">Results Page</span></span>  
 <span data-ttu-id="45ae9-164">In questa pagina viene riportato l'esito positivo o negativo dell'operazione di esportazione, indicante i risultati di ogni azione.</span><span class="sxs-lookup"><span data-stu-id="45ae9-164">This page reports the success or failure of the export operation, showing the results of each action.</span></span> <span data-ttu-id="45ae9-165">Ogni azione che ha rilevato un errore avrà un collegamento nella colonna **Risultato** .</span><span class="sxs-lookup"><span data-stu-id="45ae9-165">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="45ae9-166">Fare clic sul collegamento per visualizzare un report dell'errore relativo all'azione.</span><span class="sxs-lookup"><span data-stu-id="45ae9-166">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="45ae9-167">Fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="45ae9-167">Click **Finish** to close the Wizard.</span></span>  
  
##  <a name="using-a-net-framework-application"></a><a name="NetApp"></a><span data-ttu-id="45ae9-168">Uso di un'applicazione .NET Framework</span><span class="sxs-lookup"><span data-stu-id="45ae9-168">Using a .Net Framework Application</span></span>  
 <span data-ttu-id="45ae9-169">**Per esportare un'applicazione livello dati con il metodo Export() in un'applicazione .NET Framework.**</span><span class="sxs-lookup"><span data-stu-id="45ae9-169">**To export a DAC using the Export() method in a .Net Framework application.**</span></span>  
  
 <span data-ttu-id="45ae9-170">Per visualizzare un esempio di codice, scaricare l'applicazione di esempio dell'applicazione livello dati da [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575).</span><span class="sxs-lookup"><span data-stu-id="45ae9-170">To view a code example, download the DAC sample application on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575)</span></span>  
  
1.  <span data-ttu-id="45ae9-171">Creare un oggetto server SMO e impostarlo sull'istanza contenente l'applicazione livello dati da esportare.</span><span class="sxs-lookup"><span data-stu-id="45ae9-171">Create a SMO Server object and set it to the instance that contains the DAC to be exported.</span></span>  
  
2.  <span data-ttu-id="45ae9-172">Aprire un oggetto `ServerConnection` e collegarlo alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="45ae9-172">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="45ae9-173">Utilizzare il metodo `Export` del tipo `Microsoft.SqlServer.Management.Dac.DacStore` per esportare l'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="45ae9-173">Use the `Export` method of the `Microsoft.SqlServer.Management.Dac.DacStore` type to export the DAC.</span></span> <span data-ttu-id="45ae9-174">Specificare il nome dell'applicazione livello dati da esportare e il percorso della cartella in cui salvare il file di esportazione.</span><span class="sxs-lookup"><span data-stu-id="45ae9-174">Specify the name of the DAC to be exported, and the path to the folder where the export file is to be placed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ae9-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45ae9-175">See Also</span></span>  
 <span data-ttu-id="45ae9-176">[Applicazioni livello dati](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="45ae9-176">[Data-tier Applications](data-tier-applications.md) </span></span>  
 [<span data-ttu-id="45ae9-177">Estrarre un'applicazione livello dati da un database</span><span class="sxs-lookup"><span data-stu-id="45ae9-177">Extract a DAC From a Database</span></span>](extract-a-dac-from-a-database.md)  
  
  
