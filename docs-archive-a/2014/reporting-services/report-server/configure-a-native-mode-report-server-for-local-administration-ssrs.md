---
title: Configurare un server di report in modalità nativa per gli amministratori locali (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- UAC
- installing Reporting Services
- Windows Vista
- Localhost
- windows server 2008
- Vista
ms.assetid: 312c6bb8-b3f7-4142-a55f-c69ee15bbf52
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad53f293ef825a382d9e39b58527a36ef291687a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630312"
---
# <a name="configure-a-native-mode-report-server-for-local-administration-ssrs"></a><span data-ttu-id="ea5da-102">Configurare un server di report in modalità nativa per gli amministratori locali (SSRS)</span><span class="sxs-lookup"><span data-stu-id="ea5da-102">Configure a Native Mode Report Server for Local Administration (SSRS)</span></span>
  <span data-ttu-id="ea5da-103">Per la distribuzione di un server di report [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in uno dei seguenti sistemi operativi sono necessarie ulteriori operazioni di configurazione se si desidera amministrare localmente un'istanza del server di report.</span><span class="sxs-lookup"><span data-stu-id="ea5da-103">Deploying a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server on one of the following operating systems requires more configuration steps if you want to administer the report server instance locally.</span></span> <span data-ttu-id="ea5da-104">Questo argomento spiega come configurare il server di report per l'amministrazione locale.</span><span class="sxs-lookup"><span data-stu-id="ea5da-104">This topic explains how to configure the report server for local administration.</span></span> <span data-ttu-id="ea5da-105">Se il server di report non è stato ancora installato o configurato, vedere [installare SQL Server 2014 dall'installazione guidata &#40;&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) e [gestire un server di report Reporting Services in modalità nativa](manage-a-reporting-services-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="ea5da-105">If you have not yet installed or configured the report server, see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) and [Manage a Reporting Services Native Mode Report Server](manage-a-reporting-services-native-mode-report-server.md).</span></span>  
  
||  
|-|  
|<span data-ttu-id="ea5da-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  Modalità nativa di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea5da-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
-   [!INCLUDE[winblue_server_2](../../includes/winblue-server-2-md.md)]  
  
-   [!INCLUDE[winblue_client_2](../../includes/winblue-client-2-md.md)]  
  
-   [!INCLUDE[win8](../../includes/win8-md.md)]  
  
-   [!INCLUDE[win8srv](../../includes/win8srv-md.md)]  
  
-   [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)]  
  
-   [!INCLUDE[win7](../../includes/win7-md.md)]  
  
-   [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)]  
  
 <span data-ttu-id="ea5da-107">Poiché i sistemi operativi menzionati rimuovono le autorizzazioni, i membri del gruppo Administrators locale eseguono la maggior parte delle applicazioni come se utilizzassero l'account utente standard.</span><span class="sxs-lookup"><span data-stu-id="ea5da-107">Because the noted operating systems limit permissions, members of the local Administrators group run most applications as if they are using the Standard User account.</span></span>  
  
 <span data-ttu-id="ea5da-108">Benché questa prassi migliori la sicurezza complessiva del sistema, impedisce l'utilizzo delle assegnazioni di ruolo predefinite create da Reporting Services per gli amministratori locali.</span><span class="sxs-lookup"><span data-stu-id="ea5da-108">While this practice improves the overall security of your system, it prevents you from using the predefined, built-in role assignments that Reporting Services creates for local administrators.</span></span>  
  
-   [<span data-ttu-id="ea5da-109">Panoramica delle modifiche di configurazione</span><span class="sxs-lookup"><span data-stu-id="ea5da-109">Overview of Configuration Changes</span></span>](#bkmk_configuraiton_overview)  
  
-   [<span data-ttu-id="ea5da-110">Per configurare l'amministrazione locale del server di report e Gestione report</span><span class="sxs-lookup"><span data-stu-id="ea5da-110">To Configure Local Report Server and Report Manager Administration</span></span>](#bkmk_configure_local_server)  
  
-   [<span data-ttu-id="ea5da-111">Per configurare SQL Server Management Studio (SSMS) per l'amministrazione locale del server di report</span><span class="sxs-lookup"><span data-stu-id="ea5da-111">To Configure SQL Server Management Studio (SSMS) for local report server administration</span></span>](#bkmk_configure_ssms)  
  
-   [<span data-ttu-id="ea5da-112">Per configurare SQL Server Data Tools BI (SSDT) per la pubblicazione in un server di report locale</span><span class="sxs-lookup"><span data-stu-id="ea5da-112">To Configure SQL Server Data Tools BI (SSDT) to Publish to a Local Report Server</span></span>](#bkmk_configure_ssdt)  
  
-   [<span data-ttu-id="ea5da-113">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ea5da-113">Additional Information</span></span>](#bkmk_addiitonal_informaiton)  
  
##  <a name="overview-of-configuration-changes"></a><a name="bkmk_configuraiton_overview"></a><span data-ttu-id="ea5da-114">Panoramica delle modifiche di configurazione</span><span class="sxs-lookup"><span data-stu-id="ea5da-114">Overview of Configuration Changes</span></span>  
 <span data-ttu-id="ea5da-115">Le seguenti modifiche di configurazione consentono di configurare il server in modo tale da utilizzare autorizzazioni utente standard per le gestione del contenuto e le operazioni del server di report:</span><span class="sxs-lookup"><span data-stu-id="ea5da-115">The following configuration changes configure the server so that you can use standard user permissions to manage report server content and operations:</span></span>  
  
-   <span data-ttu-id="ea5da-116">Aggiungere gli URL di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ai siti attendibili.</span><span class="sxs-lookup"><span data-stu-id="ea5da-116">Add [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLs to trusted sites.</span></span> <span data-ttu-id="ea5da-117">Per impostazione predefinita, nei sistemi operativi seguenti Internet Explorer viene eseguito in **modalità protetta**. Questa funzionalità impedisce alle richieste del browser di accedere a processi di alto livello in esecuzione nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="ea5da-117">By default, Internet Explorer running on the listed operating systems runs in **Protected Mode**, a feature that blocks browser requests from reaching high-level processes that run on the same computer.</span></span> <span data-ttu-id="ea5da-118">È possibile disabilitare la modalità protetta per le applicazioni del server di report aggiungendo le applicazioni come Siti attendibili.</span><span class="sxs-lookup"><span data-stu-id="ea5da-118">You can disable protected mode for the report server applications by adding them as Trusted Sites.</span></span>  
  
-   <span data-ttu-id="ea5da-119">Creare assegnazioni di ruolo che concedono all'amministratore del server di report l'autorizzazione necessaria per gestire il contenuto e le operazioni senza dover utilizzare la funzionalità **Esegui come amministratore** in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ea5da-119">Create role assignments that grant you, the report server administrator, permission to manage content and operations without having to use the **Run as administrator** feature on Internet Explorer.</span></span> <span data-ttu-id="ea5da-120">Creando assegnazioni di ruolo per l'account utente di Windows, è possibile accedere a un server di report con le autorizzazioni Gestione contenuto e Amministratore sistema tramite assegnazioni di ruolo esplicite che sostituiscono le assegnazioni di ruolo predefinite create da Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="ea5da-120">By creating role assignments for your Windows user account, you gain access to a report server with Content Manager and System Administrator permissions through explicit role assignments that replace the predefined, built-in role assignments that Reporting Services creates.</span></span>  
  
##  <a name="to-configure-local-report-server-and-report-manager-administration"></a><a name="bkmk_configure_local_server"></a><span data-ttu-id="ea5da-121">Per configurare il server di report locale e l'amministrazione di Gestione report</span><span class="sxs-lookup"><span data-stu-id="ea5da-121">To Configure Local Report Server and Report Manager Administration</span></span>  
 <span data-ttu-id="ea5da-122">Se si sta esplorando un server di report locale e vengono visualizzati errori simili ai seguenti, completare i passaggi di configurazione riportati in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="ea5da-122">Complete the configuration steps in this section if you are browsing to a local report server and you see errors similar to the following:</span></span>  
  
-   <span data-ttu-id="ea5da-123">L'utente `'Domain\[user name]`' non dispone delle autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="ea5da-123">User `'Domain\[user name]`' does not have required permissions.</span></span> <span data-ttu-id="ea5da-124">Verificare che siano state concesse autorizzazioni sufficienti e che le restrizioni di Controllo account utente di Windows siano state gestite.</span><span class="sxs-lookup"><span data-stu-id="ea5da-124">Verify that sufficient permissions have been granted and Windows User Account Control (UAC) restrictions have been addressed.</span></span>  
  
###  <a name="trusted-site-settings-in-the-browser"></a><a name="bkmk_site_settings"></a><span data-ttu-id="ea5da-125">Impostazioni sito attendibili nel browser</span><span class="sxs-lookup"><span data-stu-id="ea5da-125">Trusted Site Settings in the Browser</span></span>  
  
1.  <span data-ttu-id="ea5da-126">Aprire una finestra del browser utilizzando autorizzazioni Esegui come amministratore.</span><span class="sxs-lookup"><span data-stu-id="ea5da-126">Open a browser window with Run as administrator permissions.</span></span> <span data-ttu-id="ea5da-127">Dal menu **Start** scegliere **Tutti i programmi**, fare clic con il pulsante destro del mouse su **Internet Explorer**e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-127">From the **Start** menu, click **All Programs**, right-click **Internet Explorer**, and select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ea5da-128">Fare clic su **Consenti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="ea5da-128">Click **Allow** to continue.</span></span>  
  
3.  <span data-ttu-id="ea5da-129">Nell'indirizzo URL immettere l'URL di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="ea5da-129">In the URL address, enter the Report Manager URL.</span></span> <span data-ttu-id="ea5da-130">Per istruzioni, vedere [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea5da-130">For instructions, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="ea5da-131">Fare clic su **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-131">Click **Tools**.</span></span>  
  
5.  <span data-ttu-id="ea5da-132">Fare clic su **Opzioni Internet**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-132">Click **Internet Options**.</span></span>  
  
6.  <span data-ttu-id="ea5da-133">Fare clic su **Security**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-133">Click **Security**.</span></span>  
  
7.  <span data-ttu-id="ea5da-134">Fare clic su **Siti attendibili**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-134">Click **Trusted Sites**.</span></span>  
  
8.  <span data-ttu-id="ea5da-135">Fare clic su **Siti**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-135">Click **Sites**.</span></span>  
  
9. <span data-ttu-id="ea5da-136">Aggiungere `http://<your-server-name>`.</span><span class="sxs-lookup"><span data-stu-id="ea5da-136">Add `http://<your-server-name>`.</span></span>  
  
10. <span data-ttu-id="ea5da-137">Se non si usa HTTPS per il sito predefinito, deselezionare la casella di controllo **Richiedi verifica server (https:) per tutti i siti compresi nell'area** .</span><span class="sxs-lookup"><span data-stu-id="ea5da-137">Clear the check box **Require server certification (https:) for all sites in this zone** if you are not using HTTPS for the default site.</span></span>  
  
11. <span data-ttu-id="ea5da-138">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-138">Click **Add**.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
###  <a name="report-manager-folder-settings"></a><a name="bkmk_configure_folder_settings"></a> <span data-ttu-id="ea5da-139">Impostazioni cartella Gestione report)</span><span class="sxs-lookup"><span data-stu-id="ea5da-139">Report Manager Folder Settings</span></span>  
  
1.  <span data-ttu-id="ea5da-140">Nella home page di Gestione report fare clic su **Impostazioni cartella**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-140">In Report Manager, on the Home page, click **Folder Settings**.</span></span>  
  
2.  <span data-ttu-id="ea5da-141">Nella pagina Impostazioni cartella fare clic su **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-141">In the Folder Settings page, click **Security**.</span></span>  
  
3.  <span data-ttu-id="ea5da-142">Fare clic su **Nuova assegnazione ruolo**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-142">Click **New Role Assignment**.</span></span>  
  
4.  <span data-ttu-id="ea5da-143">Nel campo **Nome gruppo o utente** digitare l'account utente di Windows utilizzando il formato: `<domain>\<user>`.</span><span class="sxs-lookup"><span data-stu-id="ea5da-143">In the **Group or user name** field, type your Windows user account in this format: `<domain>\<user>`.</span></span>  
  
5.  <span data-ttu-id="ea5da-144">Selezionare **Gestione contenuto**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-144">Select **Content Manager**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
###  <a name="report-manager-site-settings"></a><a name="bkmk_configure_site_settings"></a> <span data-ttu-id="ea5da-145">Impostazioni sito Gestione report</span><span class="sxs-lookup"><span data-stu-id="ea5da-145">Report Manager Site Settings</span></span>  
  
1.  <span data-ttu-id="ea5da-146">Aprire il browser con i privilegi di amministratore e accedere a Gestione report, `http://<server name>/reports`.</span><span class="sxs-lookup"><span data-stu-id="ea5da-146">Open your browser with administrative privileges and browse to report manager, `http://<server name>/reports`.</span></span>  
  
2.  <span data-ttu-id="ea5da-147">Fare clic su **Impostazioni sito** nell'angolo superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="ea5da-147">Click **Site Settings** in the upper corner of the Home page.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="ea5da-148">**Nota:** de l'opzione **Impostazioni sito** non è visualizzata, chiudere e riaprire il browser e accedere a Gestione report con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="ea5da-148">**Note:** If you do not see the **Site Settings** option, close and reopen your browser and browse to report manager with administrative privileges.</span></span>  
  
3.  <span data-ttu-id="ea5da-149">Fare clic su **sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-149">Click **security**.</span></span>  
  
4.  <span data-ttu-id="ea5da-150">Fare clic su **Nuova assegnazione ruolo**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-150">Click **New Role Assignment**.</span></span>  
  
5.  <span data-ttu-id="ea5da-151">Nel campo **Nome gruppo o utente** digitare l'account utente di Windows utilizzando il formato: `<domain>\<user>`.</span><span class="sxs-lookup"><span data-stu-id="ea5da-151">In the **Group or user name** field, type your Windows user account in this format: `<domain>\<user>`.</span></span>  
  
6.  <span data-ttu-id="ea5da-152">Selezionare **Amministratore sistema**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-152">Select **System Administrator**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="ea5da-153">Chiudere Gestione report.</span><span class="sxs-lookup"><span data-stu-id="ea5da-153">Close Report Manager.</span></span>  
  
9. <span data-ttu-id="ea5da-154">Riaprire Gestione report in Internet Explorer senza usare le autorizzazioni **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-154">Re-open Report Manager in Internet Explorer, without using **Run as administrator**.</span></span>  
  
##  <a name="to-configure-sql-server-management-studio-ssms-for-local-report-server-administration"></a><a name="bkmk_configure_ssms"></a><span data-ttu-id="ea5da-155">Per configurare SQL Server Management Studio (SSMS) per l'amministrazione locale del server di report</span><span class="sxs-lookup"><span data-stu-id="ea5da-155">To Configure SQL Server Management Studio (SSMS) for local report server administration</span></span>  
 <span data-ttu-id="ea5da-156">Per impostazione predefinita, non è possibile accedere a tutte le proprietà dei server di report in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] a meno che non si esegua [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="ea5da-156">By default, you cannot access all of the report server properties available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] unless you start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
 <span data-ttu-id="ea5da-157">**Per configurare proprietà e assegnazioni dei ruoli di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]** , pertanto, non è necessario avviare [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] con autorizzazioni elevate tutte le volte:</span><span class="sxs-lookup"><span data-stu-id="ea5da-157">**To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]** role properties and role assignments so you do not need to start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with elevated permissions each time:</span></span>  
  
-   <span data-ttu-id="ea5da-158">Dal menu **Start** scegliere **Tutti i programmi**e **SQL Server 2014**, fare clic con il pulsante destro del mouse su **[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]** e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-158">From the **Start** menu, click **All Programs**, click **SQL Server 2014**, right-click **[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**, and then click **Run as administrator**.</span></span>  
  
-   <span data-ttu-id="ea5da-159">Connessione al server [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] locale.</span><span class="sxs-lookup"><span data-stu-id="ea5da-159">Connect to your local [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] server.</span></span>  
  
-   <span data-ttu-id="ea5da-160">Nel nodo **Sicurezza** fare clic su **Ruoli a livello di sistema**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-160">In the **Security** node, click **System Roles**.</span></span>  
  
-   <span data-ttu-id="ea5da-161">Fare clic con il pulsante destro del mouse su **Amministratore sistema** e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-161">Right-click **System Administrator** and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="ea5da-162">Nella pagina **Proprietà ruolo a livello di sistema** , selezionare **Visualizzazione delle proprietà del server di report**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-162">In the **System Role Properties** page, select **View report server properties**.</span></span> <span data-ttu-id="ea5da-163">Selezionare le altre proprietà che si desidera associare ai membri del ruolo degli amministratori di sistema.</span><span class="sxs-lookup"><span data-stu-id="ea5da-163">Select any other properties you want associated with members of the system administrators role.</span></span>  
  
-   <span data-ttu-id="ea5da-164">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-164">Click **OK**.</span></span>  
  
-   <span data-ttu-id="ea5da-165">Chiudere [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea5da-165">Close [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]</span></span>  
  
-   <span data-ttu-id="ea5da-166">Per aggiungere un utente al ruolo di sistema "amministratore di sistema", vedere la sezione [Impostazioni sito Gestione report](#bkmk_configure_site_settings) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ea5da-166">To add a user to the system role "system administrator", see the [Report Manager Site Settings](#bkmk_configure_site_settings) section earlier in this topic.</span></span>  
  
 <span data-ttu-id="ea5da-167">Quando si apre [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e non si seleziona esplicitamente **Esegui come amministratore** si ha accesso alle proprietà del server di report.</span><span class="sxs-lookup"><span data-stu-id="ea5da-167">Now when you open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and do not explicitly select **Run as administrator** you have access to the report server properties.</span></span>  
  
##  <a name="to-configure-sql-server-data-tools-bi-ssdt-to-publish-to-a-local-report-server"></a><a name="bkmk_configure_ssdt"></a><span data-ttu-id="ea5da-168">Per configurare SQL Server Data Tools BI (SSDT) per la pubblicazione in un server di report locale</span><span class="sxs-lookup"><span data-stu-id="ea5da-168">To Configure SQL Server Data Tools BI (SSDT) to Publish to a Local Report Server</span></span>  
 <span data-ttu-id="ea5da-169">Se è stato installato [!INCLUDE[SSDTDev11](../../includes/ssdtdev11-md.md)] in uno dei sistemi operativi indicati nella prima sezione di questo argomento e si vuole che SSDT interagisca con un server di report in modalità nativa locale, si verificheranno problemi di autorizzazione a meno che non si apra [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] con autorizzazioni elevate o si configurino ruoli di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="ea5da-169">If you installed [!INCLUDE[SSDTDev11](../../includes/ssdtdev11-md.md)] on one of the operating systems listed in the first section of this topic, and you want SSDT to interact with a local Native mode report server, you will experiences permission errors unless you open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] with elevated permissions or configure reporting services roles.</span></span> <span data-ttu-id="ea5da-170">Ad esempio, se non si dispone di autorizzazioni sufficienti, si verificheranno problemi simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea5da-170">For example, if you do not have sufficient permissions, you experience issues similar to the following:</span></span>  
  
-   <span data-ttu-id="ea5da-171">Quando si tenta di distribuire elementi dei report nel server di report del computer, viene visualizzato un messaggio di errore simile al seguente nella finestra **Elenco errori** :</span><span class="sxs-lookup"><span data-stu-id="ea5da-171">When you attempt to deploy report items to the local report server, you see an error message similar to the following in the **Error List** window:</span></span>  
  
    -   <span data-ttu-id="ea5da-172">Le autorizzazioni concesse all'utente 'Dominio\\<nome utente\>' non sono sufficienti per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="ea5da-172">The permissions granted to user 'Domain\\<user name\>' are insufficient for performing this operation.</span></span>  
  
 <span data-ttu-id="ea5da-173">**Per eseguire con autorizzazioni elevate tutte le volte che si apre SSDT:**</span><span class="sxs-lookup"><span data-stu-id="ea5da-173">**To run with elevated permissions each time you open SSDT:**</span></span>  
  
1.  <span data-ttu-id="ea5da-174">Dalla schermata Start digitare `sql server` e quindi fare clic con il pulsante destro del mouse su **SQL Server Data Tools per Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-174">From the start screen, type `sql server` and then right-click **SQL Server Data Tools for Visual Studio**.</span></span> <span data-ttu-id="ea5da-175">Fare clic su **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-175">Click **Run as administrator**</span></span>  
  
     <span data-ttu-id="ea5da-176">**Oppure**, in sistemi operativi precedenti:</span><span class="sxs-lookup"><span data-stu-id="ea5da-176">**Or**, on older operating systems:</span></span>  
  
     <span data-ttu-id="ea5da-177">Dal menu **Start** fare clic su **Tutti i programmi**, selezionare **SQL Server 2014**, fare clic con il pulsante destro del mouse su **SQL Server Data Tools**, quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-177">From the **Start** menu, click **All Programs**, click **SQL Server 2014**, right-click **SQL Server Data Tools**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ea5da-178">Fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-178">Click **Continue**.</span></span>  
  
3.  <span data-ttu-id="ea5da-179">Fare clic su **Esegui programma**.</span><span class="sxs-lookup"><span data-stu-id="ea5da-179">Click **Run Program**.</span></span>  
  
 <span data-ttu-id="ea5da-180">Sarà ora possibile distribuire report o altri elementi in un server di report locale.</span><span class="sxs-lookup"><span data-stu-id="ea5da-180">You should now be able to deploy reports and other items to a local report server.</span></span>  
  
 <span data-ttu-id="ea5da-181">**Per configurare proprietà e assegnazioni dei ruoli di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , pertanto, non è necessario avviare SSDT con autorizzazioni elevate tutte le volte:**</span><span class="sxs-lookup"><span data-stu-id="ea5da-181">**To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] role assignments so you do not need to start SSDT with elevated permissions each time:**</span></span>  
  
-   <span data-ttu-id="ea5da-182">Vedere le sezioni [Impostazioni cartella Gestione report)](#bkmk_configure_folder_settings) e [Impostazioni sito Gestione report](#bkmk_configure_site_settings) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ea5da-182">See the [Report Manager Folder Settings](#bkmk_configure_folder_settings) and [Report Manager Site Settings](#bkmk_configure_site_settings) sections earlier in this topic.</span></span>  
  
##  <a name="additional-information"></a><a name="bkmk_addiitonal_informaiton"></a><span data-ttu-id="ea5da-183">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ea5da-183">Additional Information</span></span>  
 <span data-ttu-id="ea5da-184">Un passaggio di configurazione aggiuntivo e comune correlato all'amministrazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] consiste nell'aprire la porta 80 in Windows Firewall per consentire l'accesso al computer del server di report.</span><span class="sxs-lookup"><span data-stu-id="ea5da-184">An additional and common configuration step related to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] administration is to open port 80 in Windows Firewall to allow access to the report server computer.</span></span> <span data-ttu-id="ea5da-185">Per istruzioni, vedere [Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="ea5da-185">For instructions, see [Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea5da-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea5da-186">See Also</span></span>  
 [<span data-ttu-id="ea5da-187">Gestire un server di report in modalità nativa di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ea5da-187">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
