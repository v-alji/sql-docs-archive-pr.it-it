---
title: Cmdlet di PowerShell per Reporting Services modalità SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7835bc97-2827-4215-b0dd-52f692ce5e02
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b20ad870fd8a9cd7f220eebb2b954d7a88a10c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726576"
---
# <a name="powershell-cmdlets-for-reporting-services-sharepoint-mode"></a><span data-ttu-id="d8e79-102">Cmdlet di PowerShell per la modalità SharePoint di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d8e79-102">PowerShell cmdlets for Reporting Services SharePoint Mode</span></span>
  <span data-ttu-id="d8e79-103">Quando si installa la [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] modalità SharePoint di, i cmdlet di PowerShell vengono installati per supportare i server di report in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d8e79-103">When you install [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode, PowerShell cmdlets are installed to support report Servers in SharePoint mode.</span></span> <span data-ttu-id="d8e79-104">I cmdlets riguardano tre categorie di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d8e79-104">The cmdlets cover three categories of functionality.</span></span>  
  
-   <span data-ttu-id="d8e79-105">Installazione del proxy e del servizio SharePoint Shared di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-105">Installation of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint shared service and proxy.</span></span>  
  
-   <span data-ttu-id="d8e79-106">Provisioning e gestione delle applicazioni di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e dei proxy associati.</span><span class="sxs-lookup"><span data-stu-id="d8e79-106">Provisioning and management of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications and associated proxies.</span></span>  
  
-   <span data-ttu-id="d8e79-107">Gestione delle funzionalità di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , ad esempio estensioni e chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="d8e79-107">Management of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features, for example extensions and encryption keys.</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../includes/applies-md.md)]<span data-ttu-id="d8e79-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="d8e79-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint Mode</span></span>|  
  
 <span data-ttu-id="d8e79-109">**In questo argomento sono contenute le sezioni seguenti:**</span><span class="sxs-lookup"><span data-stu-id="d8e79-109">**This topic contains the following:**</span></span>  
  
-   [<span data-ttu-id="d8e79-110">Riepilogo cmdlet</span><span class="sxs-lookup"><span data-stu-id="d8e79-110">Cmdlet Summary</span></span>](#bkmk_cmdlet_sum)  
  
-   [<span data-ttu-id="d8e79-111">Cmdlet del servizio condiviso e del proxy</span><span class="sxs-lookup"><span data-stu-id="d8e79-111">Shared Service and Proxy Cmdlets</span></span>](#bkmk_sharedservice_cmdlets)  
  
-   [<span data-ttu-id="d8e79-112">Cmdlet dell'applicazione di servizio e del proxy</span><span class="sxs-lookup"><span data-stu-id="d8e79-112">Service Application and Proxy Cmdlets</span></span>](#bkmk_serviceapp_cmdlets)  
  
-   [<span data-ttu-id="d8e79-113">Cmdlet di Reporting Services funzionalità personalizzata</span><span class="sxs-lookup"><span data-stu-id="d8e79-113">Reporting Services Custom Functionality Cmdlets</span></span>](#bkmk_ssrsfeatures_cmdlets)  
  
-   [<span data-ttu-id="d8e79-114">Esempi di base</span><span class="sxs-lookup"><span data-stu-id="d8e79-114">Basic Samples</span></span>](#bkmk_basic_samples)  
  
-   [<span data-ttu-id="d8e79-115">Esempi dettagliati</span><span class="sxs-lookup"><span data-stu-id="d8e79-115">Detailed Samples</span></span>](#bkmk_detailedsamples)  
  
    -   [<span data-ttu-id="d8e79-116">Creare un proxy e un'applicazione di servizio Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d8e79-116">Create a Reporting Services service application and proxy</span></span>](#bkmk_example_create_service_application)  
  
    -   [<span data-ttu-id="d8e79-117">Rivedere e aggiornare un'estensione per il recapito di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d8e79-117">Review and update a Reporting Services delivery extension</span></span>](#bkmk_example_delivery_extension)  
  
    -   [<span data-ttu-id="d8e79-118">Ottenere e impostare le proprietà del database dell'applicazione Reporting Service, ad esempio timeout database</span><span class="sxs-lookup"><span data-stu-id="d8e79-118">Get and set properties of the Reporting Servicea application database, for example database timeout</span></span>](#bkmk_example_db_properties)  
  
    -   [<span data-ttu-id="d8e79-119">Elencare le estensioni per i dati di Reporting Services-modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="d8e79-119">List reporting services data extensions - SharePoint mode</span></span>](#bkmk_example_list_data_extensions)  
  
    -   [<span data-ttu-id="d8e79-120">Modificare ed elencare i proprietari di sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="d8e79-120">Change and list subscription owners</span></span>](#bkmk_change_subscription_owner)  
  
##  <a name="cmdlet-summary"></a><a name="bkmk_cmdlet_sum"></a><span data-ttu-id="d8e79-121">Riepilogo cmdlet</span><span class="sxs-lookup"><span data-stu-id="d8e79-121">Cmdlet Summary</span></span>  

 <span data-ttu-id="d8e79-122">Per eseguire i cmdlet è necessario aprire la shell di gestione SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d8e79-122">To run the cmdlets you need to open the SharePoint Management Shell.</span></span> <span data-ttu-id="d8e79-123">È anche possibile usare l'editor dell'interfaccia utente grafica incluso in Microsoft Windows, **Windows PowerShell Integrated Scripting Environment (ISE)**.</span><span class="sxs-lookup"><span data-stu-id="d8e79-123">You can also use the graphical user interface editor that is included with Microsoft Windows, **Windows PowerShell Integrated Scripting Environment (ISE)**.</span></span> <span data-ttu-id="d8e79-124">Per altre informazioni, vedere [Starting Windows PowerShell on Windows Server (Avvio di Windows PowerShell su Windows Server)](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d8e79-124">For more information, see [Starting Windows PowerShell on Windows Server](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell).</span></span> <span data-ttu-id="d8e79-125">Nei riepiloghi dei cmdlet seguenti, i riferimenti ai database dell'applicazione di servizio, fanno riferimento a tutti i database creati e usati da un' [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="d8e79-125">In the following cmdlet summaries, the references to service application 'databases', refer to all of the databases created and used by a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="d8e79-126">Sono inclusi i database di configurazione, di avvisi e temporaneo.</span><span class="sxs-lookup"><span data-stu-id="d8e79-126">This includes the configuration, alerting, and temp databases.</span></span>  

  
 <span data-ttu-id="d8e79-127">Se quando si digitano gli esempi di PowerShell si visualizza un messaggio di errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d8e79-127">If you see an error message similar to the following when you type the PowerShell examples:</span></span>  
  
-   <span data-ttu-id="d8e79-128">Install-SPRSService: Termine 'Install-SPRSService' non riconosciuto come</span><span class="sxs-lookup"><span data-stu-id="d8e79-128">Install-SPRSService : The term 'Install-SPRSService' is not recognized as the</span></span>  
    <span data-ttu-id="d8e79-129">nome di cmdlet, funzione, programma eseguibile o file script.</span><span class="sxs-lookup"><span data-stu-id="d8e79-129">name of a cmdlet, function, script file, or operable program.</span></span> <span data-ttu-id="d8e79-130">Verificare l'ortografia del nome, che il percorso sia incluso e corretto, quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="d8e79-130">Check the spelling of the name, or if a path was included, verify that the path is correct and try again.</span></span>  
  
 <span data-ttu-id="d8e79-131">Si è verificato uno dei problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8e79-131">One of the following issues is occurring:</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="d8e79-132">, pertanto non sono presenti i cmdlet di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-132">SharePoint mode is not installed and therefore the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] cmdlets are not installed.</span></span>  
  
-   <span data-ttu-id="d8e79-133">Il comando di PowerShell è stato eseguito in Windows PowerShell o Windows PowerShell ISE anziché nella shell di gestione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d8e79-133">You ran the PowerShell command in Windows PowerShell or Windows PowerShell ISE instead of the SharePoint Management Shell.</span></span> <span data-ttu-id="d8e79-134">Utilizzare la shell di gestione di SharePoint o aggiungere lo snap-in SharePoint alla finestra di Windows PowerShell con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d8e79-134">Use the SharePoint Management shell or add the SharePoint Snap-in to the Windows PowerShell window with the following command:</span></span>  
  
    ```powershell
    Add-PSSnapin Microsoft.SharePoint.PowerShell  
    ```  
  
 <span data-ttu-id="d8e79-135">Per ulteriori informazioni, vedere [utilizzare Windows PowerShell per amministrare SharePoint 2013](https://technet.microsoft.com/library/ee806878.aspx) ( https://technet.microsoft.com/library/ee806878.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d8e79-135">For more information see [Use Windows PowerShell to administer SharePoint 2013](https://technet.microsoft.com/library/ee806878.aspx) (https://technet.microsoft.com/library/ee806878.aspx).</span></span>  
  
#### <a name="to-open-the-sharepoint-management-shell-and-run-cmdlets"></a><span data-ttu-id="d8e79-136">Per aprire la shell di gestione di SharePoint ed eseguire i cmdlet</span><span class="sxs-lookup"><span data-stu-id="d8e79-136">To Open the SharePoint Management Shell and run cmdlets</span></span>  
  
1.  <span data-ttu-id="d8e79-137">Fare clic sul menu **Start** .</span><span class="sxs-lookup"><span data-stu-id="d8e79-137">Click the **Start** button</span></span>  
  
2.  <span data-ttu-id="d8e79-138">Fare clic sul gruppo **Prodotti Microsoft SharePoint** .</span><span class="sxs-lookup"><span data-stu-id="d8e79-138">Click the **Microsoft SharePoint Products** group.</span></span>  
  
3.  <span data-ttu-id="d8e79-139">Fare clic su **Shell di gestione SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d8e79-139">Click the **SharePoint Management Shell**.</span></span>  
  
 <span data-ttu-id="d8e79-140">Per visualizzare le informazioni della Guida relative alla riga di comando per un cmdlet, usare il comando PowerShell "Get-Help" al prompt dei comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8e79-140">To view command line help for a cmdlet use the PowerShell 'Get-Help' command at the PowerShell command prompt.</span></span> <span data-ttu-id="d8e79-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d8e79-141">For example:</span></span>  
  
 `Get-Help Get-SPRSServiceApplicationServers`  
  
###  <a name="shared-service-and-proxy-cmdlets"></a><a name="bkmk_sharedservice_cmdlets"></a> <span data-ttu-id="d8e79-142">Cmdlet del servizio condiviso e del proxy</span><span class="sxs-lookup"><span data-stu-id="d8e79-142">Shared Service and Proxy Cmdlets</span></span>  
 <span data-ttu-id="d8e79-143">Nella tabella seguente sono elencati i cmdlet di PowerShell per il servizio SharePoint Shared di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-143">The following table contains the PowerShell cmdlets for the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint shared service.</span></span>  
  
|<span data-ttu-id="d8e79-144">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d8e79-144">Cmdlet</span></span>|<span data-ttu-id="d8e79-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8e79-145">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d8e79-146">Install-SPRSService</span><span class="sxs-lookup"><span data-stu-id="d8e79-146">Install-SPRSService</span></span>|<span data-ttu-id="d8e79-147">Installa e registra, o disinstalla, il servizio SharePoint Shared di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-147">Installs and registers, or uninstalls, the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] shared service.</span></span> <span data-ttu-id="d8e79-148">Queste operazioni possono essere eseguite solo nel computer in cui è installato SQL Server [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d8e79-148">This can be done only on the machine that has an installation of SQL Server [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="d8e79-149">Per l'installazione, vengono eseguite due operazioni:</span><span class="sxs-lookup"><span data-stu-id="d8e79-149">For installation, two operations occur:</span></span><br /><br /> <span data-ttu-id="d8e79-150">1) il [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] servizio viene installato nella farm.</span><span class="sxs-lookup"><span data-stu-id="d8e79-150">1) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is installed in the farm.</span></span><br /><br /> <span data-ttu-id="d8e79-151">2) l' [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] istanza del servizio viene installata nel computer corrente.</span><span class="sxs-lookup"><span data-stu-id="d8e79-151">2) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service instance is installed to the current machine.</span></span><br /><br /> <span data-ttu-id="d8e79-152">Per la disinstallazione, vengono eseguite due operazioni:</span><span class="sxs-lookup"><span data-stu-id="d8e79-152">For Uninstallation, two operations occur:</span></span><br /><span data-ttu-id="d8e79-153">1) il [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] servizio viene disinstallato dal computer corrente.</span><span class="sxs-lookup"><span data-stu-id="d8e79-153">1) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is uninstalled from the current machine.</span></span><br /><span data-ttu-id="d8e79-154">2) il [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] servizio viene disinstallato dalla farm.</span><span class="sxs-lookup"><span data-stu-id="d8e79-154">2) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is uninstalled from the farm.</span></span><br /><br /> <br /><br /> <span data-ttu-id="d8e79-155">NOTA: se nella farm sono presenti altri computer in cui è installato il servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] oppure se nella farm sono ancora in esecuzione applicazioni di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , viene visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="d8e79-155">NOTE: If there are any other machines in the farm that have the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service installed, or if there are still [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications running in the farm, a warning message is displayed.</span></span>|  
|<span data-ttu-id="d8e79-156">Install-SPRSServiceProxy</span><span class="sxs-lookup"><span data-stu-id="d8e79-156">Install-SPRSServiceProxy</span></span>|<span data-ttu-id="d8e79-157">Installa e registra, o disinstalla, il proxy del servizio Reporting Services nella farm di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d8e79-157">Installs and registers, or uninstalls, the Reporting Services service proxy in the SharePoint farm.</span></span>|  
|<span data-ttu-id="d8e79-158">Get-SPRSProxyUrl</span><span class="sxs-lookup"><span data-stu-id="d8e79-158">Get-SPRSProxyUrl</span></span>|<span data-ttu-id="d8e79-159">Ottiene gli URL per l'accesso al servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-159">Gets the URL(s) for accessing the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="d8e79-160">Get-SPRSServiceApplicationServers</span><span class="sxs-lookup"><span data-stu-id="d8e79-160">Get-SPRSServiceApplicationServers</span></span>|<span data-ttu-id="d8e79-161">Ottiene tutti i server nella farm di SharePoint locale contenenti un'installazione del servizio SharePoint Shared di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-161">Gets all servers in the local SharePoint farm that contain an installation of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] shared service.</span></span> <span data-ttu-id="d8e79-162">Questo cmdlet è utile per gli aggiornamenti di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , per determinare i server in cui viene eseguito il servizio condiviso e pertanto devono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="d8e79-162">This cmdlet is useful for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] upgrades, to determine which servers run the shared service and therefore need to be upgraded.</span></span>|  
  
###  <a name="service-application-and-proxy-cmdlets"></a><a name="bkmk_serviceapp_cmdlets"></a> <span data-ttu-id="d8e79-163">Cmdlet dell'applicazione di servizio e del proxy</span><span class="sxs-lookup"><span data-stu-id="d8e79-163">Service Application and Proxy Cmdlets</span></span>  
 <span data-ttu-id="d8e79-164">Nella tabella seguente sono elencati i cmdlet di PowerShell per le applicazioni di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e i proxy associati.</span><span class="sxs-lookup"><span data-stu-id="d8e79-164">The following table contains the PowerShell cmdlets for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications and their associated proxies.</span></span>  
  
|<span data-ttu-id="d8e79-165">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d8e79-165">cmdlet</span></span>|<span data-ttu-id="d8e79-166">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8e79-166">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d8e79-167">Get-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="d8e79-167">Get-SPRSServiceApplication</span></span>|<span data-ttu-id="d8e79-168">Ottiene uno o più oggetti dell'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-168">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application objects.</span></span>|  
|<span data-ttu-id="d8e79-169">New-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="d8e79-169">New-SPRSServiceApplication</span></span>|<span data-ttu-id="d8e79-170">Crea una nuova applicazione di servizio Reporting Services e i database associati.</span><span class="sxs-lookup"><span data-stu-id="d8e79-170">Create a new Reporting Services service application and associated databases.</span></span><br /><br /> <span data-ttu-id="d8e79-171">Parametro LogonType: consente di specificare se nel server di report viene utilizzato un account del pool di applicazioni SSRS o un account di accesso di SQL Server per accedere al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="d8e79-171">LogonType Parameter: Specifies if the report server uses the SSRS Application Pool account or a SQL Server login to access the report server database.</span></span> <span data-ttu-id="d8e79-172">I possibili valori sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8e79-172">It can be one of the following:</span></span><br /><br /> <span data-ttu-id="d8e79-173">0 Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="d8e79-173">0 Windows Authentication</span></span><br /><br /> <span data-ttu-id="d8e79-174">1 SQL Server</span><span class="sxs-lookup"><span data-stu-id="d8e79-174">1 SQL Server</span></span><br /><br /> <span data-ttu-id="d8e79-175">2 Account pool applicazioni (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="d8e79-175">2 Application Pool Account (default)</span></span>|  
|<span data-ttu-id="d8e79-176">Remove-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="d8e79-176">Remove-SPRSServiceApplication</span></span>|<span data-ttu-id="d8e79-177">Rimuove l'applicazione di servizio Reporting Services specificata.</span><span class="sxs-lookup"><span data-stu-id="d8e79-177">Removes the specified Reporting Services service application.</span></span> <span data-ttu-id="d8e79-178">Vengono rimossi anche i database associati.</span><span class="sxs-lookup"><span data-stu-id="d8e79-178">This will also remove the associated databases.</span></span>|  
|<span data-ttu-id="d8e79-179">Set-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="d8e79-179">Set-SPRSServiceApplication</span></span>|<span data-ttu-id="d8e79-180">Modifica le proprietà di un'applicazione di servizio Reporting Services esistente.</span><span class="sxs-lookup"><span data-stu-id="d8e79-180">Edits the properties of an existing Reporting Services service application.</span></span>|  
|<span data-ttu-id="d8e79-181">New-SPRSServiceApplicationProxy</span><span class="sxs-lookup"><span data-stu-id="d8e79-181">New-SPRSServiceApplicationProxy</span></span>|<span data-ttu-id="d8e79-182">Crea un nuovo proxy dell'applicazione di servizio Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d8e79-182">Creates a new Reporting Services service application proxy.</span></span>|  
|<span data-ttu-id="d8e79-183">Get-SPRSServiceApplicationProxy</span><span class="sxs-lookup"><span data-stu-id="d8e79-183">Get-SPRSServiceApplicationProxy</span></span>|<span data-ttu-id="d8e79-184">Ottiene uno o più proxy dell'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-184">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application proxies.</span></span>|  
|<span data-ttu-id="d8e79-185">Dismount-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="d8e79-185">Dismount-SPRSDatabase</span></span>|<span data-ttu-id="d8e79-186">Smonta i database dell'applicazione di servizio per un'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-186">Dismounts the service application databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="d8e79-187">Remove-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="d8e79-187">Remove-SPRSDatabase</span></span>|<span data-ttu-id="d8e79-188">Rimuove i database dell'applicazione di servizio per un'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-188">Remove the service application databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="d8e79-189">Set-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="d8e79-189">Set-SPRSDatabase</span></span>|<span data-ttu-id="d8e79-190">Imposta le proprietà dei database associati a un'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-190">Sets the properties of the databases associated to a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="d8e79-191">Mount-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="d8e79-191">Mount-SPRSDatabase</span></span>|<span data-ttu-id="d8e79-192">Monta i database per un'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-192">Mounts databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="d8e79-193">New-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="d8e79-193">New-SPRSDatabase</span></span>|<span data-ttu-id="d8e79-194">Crea nuovi database dell'applicazione di servizio per l'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] specificata.</span><span class="sxs-lookup"><span data-stu-id="d8e79-194">Create new service application databases for the specified [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="d8e79-195">Get-SPRSDatabaseCreationScript</span><span class="sxs-lookup"><span data-stu-id="d8e79-195">Get-SPRSDatabaseCreationScript</span></span>|<span data-ttu-id="d8e79-196">Visualizza lo script di creazione del database per un'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-196">Outputs the database creation script to the screen for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="d8e79-197">È quindi possibile eseguire lo script in SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="d8e79-197">You can then run the script in SQL Server Management Studio.</span></span>|  
|<span data-ttu-id="d8e79-198">Get-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="d8e79-198">Get-SPRSDatabase</span></span>|<span data-ttu-id="d8e79-199">Ottiene uno o più database dell'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-199">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application databases.</span></span> <span data-ttu-id="d8e79-200">Usare il comando per ottenere l'ID del database dell'applicazione di servizio in modo da potere usare il cmdlet Set-SPRSDatabase per modificare le proprietà, ad esempio `querytimeout`.</span><span class="sxs-lookup"><span data-stu-id="d8e79-200">Use the command to get the ID of service application database so you can use the Set-SPRSDatabase comdlet to modify properties, for example the `querytimeout`.</span></span> <span data-ttu-id="d8e79-201">Vedere l'esempio nell'argomento [Ottenere e impostare le proprietà del database dell'applicazione Reporting Service, ad esempio timeout database](#bkmk_example_db_properties).</span><span class="sxs-lookup"><span data-stu-id="d8e79-201">See the example in this topic, [Get and set properties of the Reporting Servicea application database, for example database timeout](#bkmk_example_db_properties).</span></span>|  
|<span data-ttu-id="d8e79-202">Get-SPRSDatabaseRightsScript</span><span class="sxs-lookup"><span data-stu-id="d8e79-202">Get-SPRSDatabaseRightsScript</span></span>|<span data-ttu-id="d8e79-203">Visualizza lo script diritti del database per un'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-203">Outputs the database rights script to the screen for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="d8e79-204">Vengono richiesti l'utente desiderato e il database, quindi viene restituita l'istruzione Transact-SQL che è possibile eseguire per modificare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="d8e79-204">It will prompt for desired user and database then returns transact SQL you can run to modify permissions.</span></span> <span data-ttu-id="d8e79-205">È quindi possibile eseguire lo script in SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="d8e79-205">You can then run this script in SQL Server Management Studio.</span></span>|  
|<span data-ttu-id="d8e79-206">Get-SPRSDatabaseUpgradeScript</span><span class="sxs-lookup"><span data-stu-id="d8e79-206">Get-SPRSDatabaseUpgradeScript</span></span>|<span data-ttu-id="d8e79-207">Visualizza uno script di aggiornamento del database.</span><span class="sxs-lookup"><span data-stu-id="d8e79-207">Outputs a database upgrade script to the screen.</span></span> <span data-ttu-id="d8e79-208">Lo script consente di aggiornare i database dell'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] alla versione del database dell'installazione di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] corrente.</span><span class="sxs-lookup"><span data-stu-id="d8e79-208">The script will upgrade [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application databases to the database version of the current [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] installation.</span></span>|  
  
###  <a name="reporting-services-custom-functionality-cmdlets"></a><a name="bkmk_ssrsfeatures_cmdlets"></a><span data-ttu-id="d8e79-209">Cmdlet di Reporting Services funzionalità personalizzata</span><span class="sxs-lookup"><span data-stu-id="d8e79-209">Reporting Services Custom Functionality Cmdlets</span></span>  
  
|<span data-ttu-id="d8e79-210">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d8e79-210">Cmdlet</span></span>|<span data-ttu-id="d8e79-211">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8e79-211">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d8e79-212">Update-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="d8e79-212">Update-SPRSEncryptionKey</span></span>|<span data-ttu-id="d8e79-213">Aggiorna la chiave di crittografia per l'applicazione di servizio Reporting Services specificata ed esegue di nuovo la crittografia dei dati.</span><span class="sxs-lookup"><span data-stu-id="d8e79-213">Updates the encryption key for the specified Reporting Services service application and re-encrypts its data.</span></span>|  
|<span data-ttu-id="d8e79-214">Restore-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="d8e79-214">Restore-SPRSEncryptionKey</span></span>|<span data-ttu-id="d8e79-215">Ripristina una chiave di crittografia di cui in precedenza è stato eseguito il backup per un'applicazione di servizio Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d8e79-215">Restores a previously backed up encryption key for a Reporting Services service application.</span></span>|  
|<span data-ttu-id="d8e79-216">Remove-SPRSEncryptedData</span><span class="sxs-lookup"><span data-stu-id="d8e79-216">Remove-SPRSEncryptedData</span></span>|<span data-ttu-id="d8e79-217">Elimina i dati crittografati per l'applicazione di servizio Reporting Services specificata.</span><span class="sxs-lookup"><span data-stu-id="d8e79-217">Delete the encrypted data for the specified Reporting Services service application.</span></span>|  
|<span data-ttu-id="d8e79-218">Backup-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="d8e79-218">Backup-SPRSEncryptionKey</span></span>|<span data-ttu-id="d8e79-219">Esegue il backup della chiave di crittografia per l'applicazione di servizio Reporting Services specificata.</span><span class="sxs-lookup"><span data-stu-id="d8e79-219">Backs up the encryption key for the specified Reporting Services service application.</span></span>|  
|<span data-ttu-id="d8e79-220">New-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="d8e79-220">New-SPRSExtension</span></span>|<span data-ttu-id="d8e79-221">Registra una nuova estensione con un'applicazione di servizio Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d8e79-221">Registers a new extension with a Reporting Services service application.</span></span>|  
|<span data-ttu-id="d8e79-222">Set-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="d8e79-222">Set-SPRSExtension</span></span>|<span data-ttu-id="d8e79-223">Imposta le proprietà di un'estensione di Reporting Services esistente.</span><span class="sxs-lookup"><span data-stu-id="d8e79-223">Sets the properties of an existing Reporting Services extension.</span></span>|  
|<span data-ttu-id="d8e79-224">Remove-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="d8e79-224">Remove-SPRSExtension</span></span>|<span data-ttu-id="d8e79-225">Rimuove un'estensione da un'applicazione di servizio Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d8e79-225">Removes an extension from a Reporting Services service application.</span></span>|  
|<span data-ttu-id="d8e79-226">Get-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="d8e79-226">Get-SPRSExtension</span></span>|<span data-ttu-id="d8e79-227">Ottiene una o più estensioni di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] per un'applicazione di servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-227">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] extensions for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span><br /><br /> <span data-ttu-id="d8e79-228">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="d8e79-228">Valid values are:</span></span><br /><br /> <span data-ttu-id="d8e79-229">**Recapito**</span><span class="sxs-lookup"><span data-stu-id="d8e79-229">**Delivery**</span></span><br /><br /> <span data-ttu-id="d8e79-230">**DeliveryUI**</span><span class="sxs-lookup"><span data-stu-id="d8e79-230">**DeliveryUI**</span></span><br /><br /> <span data-ttu-id="d8e79-231">**Rendering**</span><span class="sxs-lookup"><span data-stu-id="d8e79-231">**Render**</span></span><br /><br /> <span data-ttu-id="d8e79-232">**Dati**</span><span class="sxs-lookup"><span data-stu-id="d8e79-232">**Data**</span></span><br /><br /> <span data-ttu-id="d8e79-233">**Sicurezza**</span><span class="sxs-lookup"><span data-stu-id="d8e79-233">**Security**</span></span><br /><br /> <span data-ttu-id="d8e79-234">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="d8e79-234">**Authentication**</span></span><br /><br /> <span data-ttu-id="d8e79-235">**EventProcessing**</span><span class="sxs-lookup"><span data-stu-id="d8e79-235">**EventProcessing**</span></span><br /><br /> <span data-ttu-id="d8e79-236">**ReportItems**</span><span class="sxs-lookup"><span data-stu-id="d8e79-236">**ReportItems**</span></span><br /><br /> <span data-ttu-id="d8e79-237">**Designer**</span><span class="sxs-lookup"><span data-stu-id="d8e79-237">**Designer**</span></span><br /><br /> <span data-ttu-id="d8e79-238">**ReportItemDesigner**</span><span class="sxs-lookup"><span data-stu-id="d8e79-238">**ReportItemDesigner**</span></span><br /><br /> <span data-ttu-id="d8e79-239">**ReportItemConverter**</span><span class="sxs-lookup"><span data-stu-id="d8e79-239">**ReportItemConverter**</span></span><br /><br /> <span data-ttu-id="d8e79-240">**ReportDefinitionCustomization**</span><span class="sxs-lookup"><span data-stu-id="d8e79-240">**ReportDefinitionCustomization**</span></span>|  
|<span data-ttu-id="d8e79-241">Get-SPRSSite</span><span class="sxs-lookup"><span data-stu-id="d8e79-241">Get-SPRSSite</span></span>|<span data-ttu-id="d8e79-242">Ottiene i siti di SharePoint in base all'eventuale abilitazione della funzionalità "ReportingService".</span><span class="sxs-lookup"><span data-stu-id="d8e79-242">Gets the SharePoint sites based on whether the "ReportingService" feature is enabled.</span></span> <span data-ttu-id="d8e79-243">Per impostazione predefinita, vengono restituiti i siti in cui la funzionalità "ReportingService" è abilitata.</span><span class="sxs-lookup"><span data-stu-id="d8e79-243">By default, sites that enable the "ReportingService" feature are returned.</span></span>|  
  
##  <a name="basic-samples"></a><a name="bkmk_basic_samples"></a><span data-ttu-id="d8e79-244">Esempi di base</span><span class="sxs-lookup"><span data-stu-id="d8e79-244">Basic Samples</span></span>  
 <span data-ttu-id="d8e79-245">Restituire un elenco di cmdlet contenenti "SPRS" nel nome.</span><span class="sxs-lookup"><span data-stu-id="d8e79-245">Return a list of cmdlets that contain 'SPRS' in the name.</span></span> <span data-ttu-id="d8e79-246">Si tratta dell'elenco completo dei cmdlet di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-246">This will be the full list of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] cmdlets.</span></span>  
  
```powershell
Get-command -noun *SPRS*  
```  
  
 <span data-ttu-id="d8e79-247">In alternativa, con un livello leggermente maggiore di dettaglio, inoltrare tramite pipe in un file di testo denominato commandlist.txt.</span><span class="sxs-lookup"><span data-stu-id="d8e79-247">Or with a little more detail, piped to a text file named commandlist.txt</span></span>  
  
```powershell
Get-Command -Noun *SPRS* | Select name, definition | Format-List | Out-File c:\commandlist.txt  
```  
  
 <span data-ttu-id="d8e79-248">Installare il proxy del servizio e il servizio SharePoint di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-248">Install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint service and service proxy.</span></span>  
  
```powershell
Install-SPRSService  
```  
  
```powershell
Install-SPRSServiceProxy  
```  
  
 <span data-ttu-id="d8e79-249">Avviare il servizio [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e79-249">Start the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service</span></span>  
  
```powershell
Get-SPServiceInstance -all | where {$_.TypeName -like "SQL Server Reporting*"} | Start-SPServiceInstance  
```  
  
 <span data-ttu-id="d8e79-250">Digitare il comando seguente dalla Shell di gestione di SharePoint per ottenere un elenco filtrato di righe del file di log.</span><span class="sxs-lookup"><span data-stu-id="d8e79-250">Type the following command from the SharePoint Management Shell to return a filtered list of rows from the a log file.</span></span> <span data-ttu-id="d8e79-251">Con il comando verranno filtrate le righe contenenti "ssrscustomactionerror".</span><span class="sxs-lookup"><span data-stu-id="d8e79-251">The command will filter for lines that contain "ssrscustomactionerror".</span></span> <span data-ttu-id="d8e79-252">In questo esempio viene analizzato il file di log creato al momento dell'installazione di rssharepoint.msi.</span><span class="sxs-lookup"><span data-stu-id="d8e79-252">This example is looking at the log file created when the rssharepoint.msi was installed.</span></span>  
  
```powershell
Get-Content -Path C:\Users\testuser\AppData\Local\Temp\rs_sp_0.log | Select-String "ssrscustomactionerror"  
```  
  
##  <a name="detailed-samples"></a><a name="bkmk_detailedsamples"></a><span data-ttu-id="d8e79-253">Esempi dettagliati</span><span class="sxs-lookup"><span data-stu-id="d8e79-253">Detailed Samples</span></span>  
 <span data-ttu-id="d8e79-254">Oltre agli esempi seguenti, vedere la sezione "script di Windows PowerShell" nell'argomento [script di Windows PowerShell per i passaggi 1-4](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md#bkmk_full_script).</span><span class="sxs-lookup"><span data-stu-id="d8e79-254">In addition to the following samples, see the section "Windows PowerShell Script" in the topic [Windows PowerShell script for Steps 1-4](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md#bkmk_full_script).</span></span>  
  
###  <a name="create-a-reporting-services-service-application-and-proxy"></a><a name="bkmk_example_create_service_application"></a><span data-ttu-id="d8e79-255">Creare un'applicazione di servizio Reporting Services e un proxy</span><span class="sxs-lookup"><span data-stu-id="d8e79-255">Create a Reporting Services service application and proxy</span></span>  
 <span data-ttu-id="d8e79-256">Questo script di esempio consente di completare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8e79-256">This sample script completes the following tasks:</span></span>  
  
1.  <span data-ttu-id="d8e79-257">Creare un proxy e un'applicazione di servizio Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d8e79-257">Create a Reporting Services service application and proxy.</span></span> <span data-ttu-id="d8e79-258">Per lo script si presuppone che il pool di applicazioni "My App Pool" esista già.</span><span class="sxs-lookup"><span data-stu-id="d8e79-258">The script assumes the application pool "My App Pool" already exists.</span></span>  
  
2.  <span data-ttu-id="d8e79-259">Aggiungere il proxy al gruppo di proxy predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d8e79-259">Add the proxy to the default proxy group</span></span>  
  
3.  <span data-ttu-id="d8e79-260">Concedere all'applicazione di servizio l'accesso al database del contenuto dell'applicazione Web sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="d8e79-260">Grant the service app access to the port 80 web app's content database.</span></span> <span data-ttu-id="d8e79-261">Lo script presuppone che il sito " http://sitename " esista già.</span><span class="sxs-lookup"><span data-stu-id="d8e79-261">The script assumes site "http://sitename" already exists.</span></span>  
  
```powershell
# Create service application and service application proxy  
$appPool = Get-SPServiceApplicationPool "My App Pool"  
$serviceApp = New-SPRSServiceApplication "My RS Service App" -ApplicationPool $appPool  
$serviceAppProxy = New-SPRSServiceApplicationProxy -Name "My RS Service App Proxy" -ServiceApplication $serviceApp  
  
# Add service application proxy to default proxy group.  Any web application that uses the default proxy group will now be able to use this service application.  
Get-SPServiceApplicationProxyGroup -default | Add-SPServiceApplicationProxyGroupMember -Member $serviceAppProxy  
  
# Grant application pool account access to the port 80 web application's content database.  
$webApp = Get-SPWebApplication "http://sitename"  
$appPoolAccountName = $appPool.ProcessAccount.LookupName()  
$webApp.GrantAccessToProcessIdentity($appPoolAccountName)
```  
  
###  <a name="review-and-update-a-reporting-services-delivery-extension"></a><a name="bkmk_example_delivery_extension"></a><span data-ttu-id="d8e79-262">Esaminare e aggiornare un'estensione per il recapito Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d8e79-262">Review and update a Reporting Services delivery extension</span></span>  
 <span data-ttu-id="d8e79-263">Nell'esempio di script di PowerShell seguente viene aggiornata la configurazione dell'estensione per il recapito tramite posta elettronica del server di report per l'applicazione di servizio denominata `My RS Service App`.</span><span class="sxs-lookup"><span data-stu-id="d8e79-263">The following PowerShell script example, updates the configuration for the report server e-mail delivery extension for the service application named `My RS Service App`.</span></span> <span data-ttu-id="d8e79-264">Aggiornare i valori per il server SMTP (`<email server name>`) e l'alias di posta elettronica FROM (`<your FROM email address>`).</span><span class="sxs-lookup"><span data-stu-id="d8e79-264">Update the values for the SMTP server (`<email server name>`) and the FROM email alias (`<your FROM email address>`).</span></span>  
  
```powershell
$app = Get-SPRSServiceApplication -Name "My RS Service App"  
$emailCfg = Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml
$emailXml = [xml]$emailCfg
$emailXml.SelectSingleNode("//SMTPServer").InnerText = "<email server name>"  
$emailXml.SelectSingleNode("//SendUsing").InnerText = "2"  
$emailXml.SelectSingleNode("//SMTPAuthenticate").InnerText = "2"  
$emailXml.SelectSingleNode("//From").InnerText = '<your FROM email address>'  
Set-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" -ExtensionConfiguration $emailXml.OuterXml  
```  
  
 <span data-ttu-id="d8e79-265">Nell'esempio precedente, se non si conosce il nome esatto dell'applicazione di servizio, è possibile riscrivere la prima istruzione per ottenere l'applicazione di servizio in base a una ricerca del nome parziale.</span><span class="sxs-lookup"><span data-stu-id="d8e79-265">In the above example if you did not know the exact name of the service application, you could rewrite the first statement to get the service application based on a search of the partial name.</span></span> <span data-ttu-id="d8e79-266">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d8e79-266">For example:</span></span>  
  
```powershell
$app = Get-SPRSServiceApplication | Where {$_.name -like " ssrs_testapp *"}  
```  
  
 <span data-ttu-id="d8e79-267">Lo script seguente restituisce i valori di configurazione correnti per l'estensione per il recapito via posta elettronica del server di report per l'applicazione di servizio denominata "Reporting Services Application".</span><span class="sxs-lookup"><span data-stu-id="d8e79-267">The following script will return the current configuration values for the report server e-mail delivery extension for the service application named "Reporting Services Application".</span></span> <span data-ttu-id="d8e79-268">Il primo passaggio consente di impostare il valore della variabile $app sull'oggetto applicazione di servizio denominato "My RS Service App"</span><span class="sxs-lookup"><span data-stu-id="d8e79-268">The first step sets the value of the variable $app to the object of the service application that has a name of " My RS Service App "</span></span>  
  
 <span data-ttu-id="d8e79-269">La seconda istruzione consente di ottenere l'estensione per il recapito "Report Server Email" per l'oggetto applicazione di servizio nella variabile $app e di selezionare configurationXML</span><span class="sxs-lookup"><span data-stu-id="d8e79-269">The second statement will Get the 'Report Server Email' delivery extension for the service application object in variable $app, and select the configurationXML</span></span>  
  
```powershell
$app = Get-SPRSServiceapplication -Name "Reporting Services Application"  
Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
```  
  
 <span data-ttu-id="d8e79-270">È inoltre possibile riscrivere le due istruzioni sopra riportate come un'unica istruzione:</span><span class="sxs-lookup"><span data-stu-id="d8e79-270">You can also rewrite the above two statements as one:</span></span>  
  
```powershell
Get-SPRSServiceApplication -Name "Reporting Services Application" | Get-SPRSExtension -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
```  
  
###  <a name="get-and-set-properties-of-the-reporting-servicea-application-database-for-example-database-timeout"></a><a name="bkmk_example_db_properties"></a><span data-ttu-id="d8e79-271">Ottenere e impostare le proprietà del database dell'applicazione Reporting Service, ad esempio timeout database</span><span class="sxs-lookup"><span data-stu-id="d8e79-271">Get and set properties of the Reporting Servicea application database, for example database timeout</span></span>  
 <span data-ttu-id="d8e79-272">L'esempio seguente restituisce innanzitutto un elenco dei database e delle proprietà in modo da potere determinare il GUID del database da fornire al comando set.</span><span class="sxs-lookup"><span data-stu-id="d8e79-272">The following example first returns a list of the databases and properties so you can determine the database guid (ID) that you then supply to the set command.</span></span> <span data-ttu-id="d8e79-273">Per un elenco completo delle proprietà, usare `Get-SPRSDatabase | format-list`.</span><span class="sxs-lookup"><span data-stu-id="d8e79-273">For a full list of the properties, use `Get-SPRSDatabase | format-list`.</span></span>  
  
```powershell
Get-SPRSDatabase | Select id, querytimeout,connectiontimeout, status, server, ServiceInstance
```  
  
 <span data-ttu-id="d8e79-274">Di seguito è riportato un esempio dell'output.</span><span class="sxs-lookup"><span data-stu-id="d8e79-274">The following is an example of the output.</span></span> <span data-ttu-id="d8e79-275">Determinare l'ID del database da modificare e usare l'ID nel cmdlet SET.</span><span class="sxs-lookup"><span data-stu-id="d8e79-275">Determine the ID for the database you want to modify and use the ID in the SET cmdlet.</span></span>  
  
-   `Id                : 56f8d1bc-cb04-44cf-bd41-a873643c5a14`  
  
     `QueryTimeout      : 120`  
  
     `ConnectionTimeout : 15`  
  
     `Status            : Online`  
  
     `Server            : SPServer Name=uetestb01`  
  
     `ServiceInstance   : SPDatabaseServiceInstance`  
  
```powershell
Set-SPRSDatabase -Identity 56f8d1bc-cb04-44cf-bd41-a873643c5a14 -QueryTimeout 300  
```  
  
 <span data-ttu-id="d8e79-276">Per verificare il valore impostato, eseguire di nuovo il cmdlet GET.</span><span class="sxs-lookup"><span data-stu-id="d8e79-276">To verify the value is set, run the GET cmdlet again.</span></span>  
  
```powershell
Get-SPRSDatabase -Identity 56f8d1bc-cb04-44cf-bd41-a873643c5a14 | Select id, querytimeout,connectiontimeout, status, server, ServiceInstance  
```  
  
###  <a name="list-reporting-services-data-extensions---sharepoint-mode"></a><a name="bkmk_example_list_data_extensions"></a><span data-ttu-id="d8e79-277">Elencare le estensioni per i dati di Reporting Services-modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="d8e79-277">List reporting services data extensions - SharePoint mode</span></span>  
 <span data-ttu-id="d8e79-278">L'esempio seguente esegue il ciclo di ogni applicazione di servizio di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] ed elenca le estensioni per i dati per ogni applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8e79-278">The following example loops through each [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application and lists the current data extensions for each.</span></span>  
  
```powershell
$apps = Get-SPRSServiceApplication  
foreach ($app in $apps)
{  
Write-host -ForegroundColor "yellow" Service App Name $app.Name  
Get-SPRSExtension -identity $app -ExtensionType "Data" | select name, extensiontype | Format-Table -AutoSize  
}  
```  
  
 <span data-ttu-id="d8e79-279">**Output di esempio:**</span><span class="sxs-lookup"><span data-stu-id="d8e79-279">**Example output:**</span></span>  
  
-   `Name           ExtensionType`  
  
     `----           -------------`  
  
     `SQL                     Data`  
  
     `SQLAZURE                Data`  
  
     `SQLPDW                  Data`  
  
     `OLEDB                   Data`  
  
     `OLEDB-MD                Data`  
  
     `ORACLE                  Data`  
  
     `ODBC                    Data`  
  
     `XML                     Data`  
  
     `SHAREPOINTLIST          Data`  
  
###  <a name="change-and-list-subscription-owners"></a><a name="bkmk_change_subscription_owner"></a><span data-ttu-id="d8e79-280">Modificare ed elencare i proprietari delle sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="d8e79-280">Change and list subscription owners</span></span>  
 <span data-ttu-id="d8e79-281">Vedere [Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d8e79-281">See [Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8e79-282">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8e79-282">See Also</span></span>  
 <span data-ttu-id="d8e79-283">[Usare PowerShell per modificare ed elencare i proprietari delle sottoscrizioni Reporting Services ed eseguire una sottoscrizione](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="d8e79-283">[Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md) </span></span>  
 <span data-ttu-id="d8e79-284">[Elenco di controllo: usare PowerShell per verificare PowerPivot per SharePoint](https://docs.microsoft.com/analysis-services/instances/install-windows/checklist-use-powershell-to-verify-power-pivot-for-sharepoint) </span><span class="sxs-lookup"><span data-stu-id="d8e79-284">[CheckList: Use PowerShell to Verify PowerPivot for SharePoint](https://docs.microsoft.com/analysis-services/instances/install-windows/checklist-use-powershell-to-verify-power-pivot-for-sharepoint) </span></span>  
 [<span data-ttu-id="d8e79-285">Script di PowerShell di gestione di SharePoint nel sito CodePlex</span><span class="sxs-lookup"><span data-stu-id="d8e79-285">CodePlex SharePoint Management PowerShell scripts</span></span>](https://sharepointpsscripts.codeplex.com/)   
