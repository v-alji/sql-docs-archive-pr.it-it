---
title: Configurare un firewall per l'accesso al server di report | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- firewall systems [Reporting Services]
- configuring servers [Reporting Services]
ms.assetid: 04dae07a-a3a4-424c-9bcb-a8000e20dc93
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b578c980522d24f5a24a73fdfd080ec425335aac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630313"
---
# <a name="configure-a-firewall-for-report-server-access"></a><span data-ttu-id="dacde-102">Configurare un firewall per l'accesso al server di report</span><span class="sxs-lookup"><span data-stu-id="dacde-102">Configure a Firewall for Report Server Access</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="dacde-103">Alle applicazioni del server di report e ai report pubblicati si accede tramite URL che specificano un indirizzo IP, una porta e una directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="dacde-103">Report server applications and published reports are accessed through URLs that specify an IP address, port, and virtual directory.</span></span> <span data-ttu-id="dacde-104">Se Windows Firewall è abilitato, la porta configurata per l'utilizzo da parte del server di report è probabilmente chiusa.</span><span class="sxs-lookup"><span data-stu-id="dacde-104">If Windows Firewall is turned on, the port that the report server is configured to use is most likely closed.</span></span> <span data-ttu-id="dacde-105">Il fatto che una porta possa essere chiusa viene indicato dalla visualizzazione di una pagina Web vuota in seguito alla richiesta di un report o dalla visualizzazione di una pagina vuota quando si tenta di aprire Gestione report da un computer client remoto.</span><span class="sxs-lookup"><span data-stu-id="dacde-105">Indications that a port might be closed are the appearance of a blank Web page after requesting a report, or a blank page when you attempt to open Report Manager from a remote client computer.</span></span>  
  
 <span data-ttu-id="dacde-106">Per aprire una porta, è necessario utilizzare l'utilità Windows Firewall nel computer server di report.</span><span class="sxs-lookup"><span data-stu-id="dacde-106">To open a port, you must use the Windows Firewall utility on the report server computer.</span></span> <span data-ttu-id="dacde-107">Poiché le porte non verranno aperte automaticamente da Reporting Services, è necessario eseguire questa operazione manualmente.</span><span class="sxs-lookup"><span data-stu-id="dacde-107">Reporting Services will not open ports for you; you must perform this step manually.</span></span>  
  
 <span data-ttu-id="dacde-108">Per impostazione predefinita, il server di report è in attesa delle richieste HTTP sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="dacde-108">By default, the report server listens for HTTP requests on port 80.</span></span> <span data-ttu-id="dacde-109">Di conseguenza, le indicazioni seguenti includono passaggi in cui viene specificata tale porta.</span><span class="sxs-lookup"><span data-stu-id="dacde-109">As such, the following instructions include steps that specify that port.</span></span> <span data-ttu-id="dacde-110">Se gli URL del server di report sono stati configurati per l'utilizzo di una porta diversa, è necessario specificare questo numero di porta quando si utilizzano le indicazioni fornite di seguito.</span><span class="sxs-lookup"><span data-stu-id="dacde-110">If you configured the report server URLs to use a different port, you must specify that port number when following the instructions below.</span></span>  
  
 <span data-ttu-id="dacde-111">Se si accede ai database relazionali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in computer esterni o se il database del server di report si trova in un'istanza esterna di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è necessario aprire le porte 1433 e 1434 nel computer esterno.</span><span class="sxs-lookup"><span data-stu-id="dacde-111">If you are accessing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relational databases on external computers, or if the report server database is on an external [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, you must open port 1433 and 1434 on the external computer.</span></span> <span data-ttu-id="dacde-112">Per altre informazioni, vedere [Configurare Windows Firewall per l'accesso al motore di database](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dacde-112">For more information, see [Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="dacde-113">Per altre informazioni sulle impostazioni predefinite di Windows Firewall e per una descrizione delle porte TCP che interessano [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]e [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], vedere [Configurare Windows Firewall per consentire l'accesso a SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dacde-113">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dacde-114">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="dacde-114">Prerequisites</span></span>  
 <span data-ttu-id="dacde-115">In queste indicazioni si presuppone che sia già stato configurato l'account del servizio, sia già stato creato il database del server di report e che siano già stati configurati gli URL per il servizio Web ReportServer e per Gestione report.</span><span class="sxs-lookup"><span data-stu-id="dacde-115">These instructions assume that you already configured the service account, created the report server database, and configured URLs for the Report Server Web service and Report Manager.</span></span> <span data-ttu-id="dacde-116">Per altre informazioni, vedere [Gestione di un server di report in modalità nativa](manage-a-reporting-services-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="dacde-116">For more information, see [Manage a Reporting Services Native Mode Report Server](manage-a-reporting-services-native-mode-report-server.md).</span></span>  
  
 <span data-ttu-id="dacde-117">È inoltre necessario avere verificato la possibilità di accedere al server di report tramite una connessione del browser all'istanza locale del server di report.</span><span class="sxs-lookup"><span data-stu-id="dacde-117">You should also have verified that the report server is accessible over a local Web browser connection to the local report server instance.</span></span> <span data-ttu-id="dacde-118">Questo passaggio consente di stabilire che si dispone di un'installazione funzionante.</span><span class="sxs-lookup"><span data-stu-id="dacde-118">This step establishes that you have a working installation.</span></span> <span data-ttu-id="dacde-119">Prima di procedere all'apertura delle porte, è necessario verificare la corretta configurazione dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="dacde-119">You should verify that the installation is configured correctly before you begin opening ports.</span></span> <span data-ttu-id="dacde-120">Per completare questo passaggio in Windows Server, è inoltre necessario avere aggiunto il server di report all'area dei siti attendibili.</span><span class="sxs-lookup"><span data-stu-id="dacde-120">To complete this step on  Windows Server, you must have also added the report server site to Trusted Sites.</span></span> <span data-ttu-id="dacde-121">Per altre informazioni, vedere [Configurare un server di report in modalità nativa per gli amministratori locali &#40;SSRS&#41;](configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dacde-121">For more information, see [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span></span>  
  
## <a name="opening-ports-in-windows-firewall"></a><span data-ttu-id="dacde-122">Apertura di porte in Windows Firewall</span><span class="sxs-lookup"><span data-stu-id="dacde-122">Opening Ports in Windows Firewall</span></span>  
 <span data-ttu-id="dacde-123">A seconda della versione di Windows Firewall in uso, è necessario seguire indicazioni distinte.</span><span class="sxs-lookup"><span data-stu-id="dacde-123">There are separate instructions for different versions of Windows Firewall.</span></span>  
  
#### <a name="to-open-port-80-on-windows-7-windows-server-2008-r2-windows-server-2012-and-2012-r2"></a><span data-ttu-id="dacde-124">Per aprire la porta 80 in Windows 7, Windows Server 2008 R2 o Windows Server 2012 e 2012 R2</span><span class="sxs-lookup"><span data-stu-id="dacde-124">To open port 80 on Windows 7, Windows Server 2008 R2, Windows Server 2012 and 2012 R2</span></span>  
  
1.  <span data-ttu-id="dacde-125">Fare clic sul menu **Start** , scegliere **Pannello di controllo**, **Sistema e sicurezza**e quindi **Windows Firewall**.</span><span class="sxs-lookup"><span data-stu-id="dacde-125">From the **Start** menu, click **Control Panel**, click **System and Security**, and then click **Windows Firewall**.</span></span> <span data-ttu-id="dacde-126">Il Pannello di controllo non è configurato per la visualizzazione per 'Categorie': è sufficiente selezionare **Windows Firewall**.</span><span class="sxs-lookup"><span data-stu-id="dacde-126">Control Panel is not configured for 'Category' view, you only need to select **Windows Firewall.**</span></span>  
  
2.  <span data-ttu-id="dacde-127">Fare clic su **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="dacde-127">Click **Advanced Settings**.</span></span>  
  
3.  <span data-ttu-id="dacde-128">Fare clic su **Regole connessioni in entrata**.</span><span class="sxs-lookup"><span data-stu-id="dacde-128">Click **Inbound Rules.**</span></span>  
  
4.  <span data-ttu-id="dacde-129">Fare clic su **Nuova regola** nella finestra **Azioni\*\*\*\*.**</span><span class="sxs-lookup"><span data-stu-id="dacde-129">Click **New Rule** in the **Actions** window **.**</span></span>  
  
5.  <span data-ttu-id="dacde-130">Fare clic su **Tipo di regola** in **Porta**.</span><span class="sxs-lookup"><span data-stu-id="dacde-130">Click **Rule Type** of **Port.**</span></span>  
  
6.  <span data-ttu-id="dacde-131">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="dacde-131">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="dacde-132">Nella pagina **Protocollo e porte** selezionare **TCP**.</span><span class="sxs-lookup"><span data-stu-id="dacde-132">On the **Protocol and Ports** page click **TCP**.</span></span>  
  
8.  <span data-ttu-id="dacde-133">Selezionare **Porte locali specifiche** e digitare il valore **80**.</span><span class="sxs-lookup"><span data-stu-id="dacde-133">Select **Specific Local Ports** and type a value of **80**.</span></span>  
  
9. <span data-ttu-id="dacde-134">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="dacde-134">Click **Next**.</span></span>  
  
10. <span data-ttu-id="dacde-135">Nella pagina **Azione** fare clic su **Consenti la connessione**.</span><span class="sxs-lookup"><span data-stu-id="dacde-135">On the **Action** page click **Allow the connection**.</span></span>  
  
11. <span data-ttu-id="dacde-136">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="dacde-136">Click **Next**.</span></span>  
  
12. <span data-ttu-id="dacde-137">Nella pagina **Profilo** fare clic sulle opzioni appropriate per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="dacde-137">On the **Profile** page click the appropriate options for your environment.</span></span>  
  
13. <span data-ttu-id="dacde-138">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="dacde-138">Click **Next**.</span></span>  
  
14. <span data-ttu-id="dacde-139">Nella pagina **Nome** immettere un nome di**ReportServer (TCP sulla porta 80)**</span><span class="sxs-lookup"><span data-stu-id="dacde-139">On the **Name** page enter a name of**ReportServer (TCP on port 80)**</span></span>  
  
15. <span data-ttu-id="dacde-140">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="dacde-140">Click **Finish**.</span></span>  
  
16. <span data-ttu-id="dacde-141">Riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="dacde-141">Restart the computer.</span></span>  
  
#### <a name="to-open-port-80-on-windows-vista-or-windows-server-2008"></a><span data-ttu-id="dacde-142">Per aprire la porta 80 in Windows Vista o Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="dacde-142">To open port 80 on Windows Vista or Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="dacde-143">Dal menu **Start** fare clic su **Pannello di controllo**, fare clic su **sicurezza**e quindi su **Windows Firewall**.</span><span class="sxs-lookup"><span data-stu-id="dacde-143">From the **Start** menu, click **Control Panel**, click **Security**, and then click **Windows Firewall**.</span></span>  
  
2.  <span data-ttu-id="dacde-144">Fare clic su **Consenti programma con Windows Firewall**.</span><span class="sxs-lookup"><span data-stu-id="dacde-144">Click **Allow a program through Windows Firewall**.</span></span>  
  
3.  <span data-ttu-id="dacde-145">Fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="dacde-145">Click **Continue**.</span></span>  
  
4.  <span data-ttu-id="dacde-146">Nella scheda eccezioni fare clic su **Aggiungi porta**.</span><span class="sxs-lookup"><span data-stu-id="dacde-146">On the Exceptions tab, click **Add Port**.</span></span>  
  
5.  <span data-ttu-id="dacde-147">In nome digitare **ReportServer (TCP sulla porta 80)**.</span><span class="sxs-lookup"><span data-stu-id="dacde-147">In Name, type **ReportServer (TCP on port 80)**.</span></span>  
  
6.  <span data-ttu-id="dacde-148">In numero porta digitare **80**.</span><span class="sxs-lookup"><span data-stu-id="dacde-148">In Port number, type **80**.</span></span>  
  
7.  <span data-ttu-id="dacde-149">Verificare che sia selezionato **TCP** .</span><span class="sxs-lookup"><span data-stu-id="dacde-149">Verify that **TCP** is selected.</span></span>  
  
8.  <span data-ttu-id="dacde-150">Fare clic su **Cambia ambito**.</span><span class="sxs-lookup"><span data-stu-id="dacde-150">Click **Change Scope**.</span></span>  
  
9. <span data-ttu-id="dacde-151">Fare clic su **rete personale (subnet)**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dacde-151">Click **My network (subnet) only**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="dacde-152">Scegliere **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="dacde-152">Click **OK** to close the dialog box.</span></span>  
  
11. <span data-ttu-id="dacde-153">Riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="dacde-153">Restart the computer.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dacde-154">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="dacde-154">Next Steps</span></span>  
 <span data-ttu-id="dacde-155">Dopo avere aperto la porta e prima di verificare che gli utenti remoti possano accedere al server di report sulla porta aperta, è necessario concedere accesso utente al server di report tramite assegnazioni di ruolo in Home e a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="dacde-155">After you open the port and before you confirm whether remote users can access the report server on the port that you open, you must grant user access to the report server through role assignments on Home and at the site level.</span></span> <span data-ttu-id="dacde-156">Pur aprendo correttamente una porta, è possibile che le connessioni del server di report non vengano effettuate se gli utenti non dispongono di autorizzazioni sufficienti.</span><span class="sxs-lookup"><span data-stu-id="dacde-156">You can open a port correctly and still have report server connections fail if users do not have sufficient permissions.</span></span> <span data-ttu-id="dacde-157">Per altre informazioni, vedere [Concedere l'accesso utente a un server di report &#40;Gestione report&#41;](../security/grant-user-access-to-a-report-server.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dacde-157">For more information, see [Grant User Access to a Report Server &#40;Report Manager&#41;](../security/grant-user-access-to-a-report-server.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="dacde-158">È inoltre possibile verificare che la porta sia aperta correttamente avviando Gestione report in un computer diverso.</span><span class="sxs-lookup"><span data-stu-id="dacde-158">You can also verify that the port is opened correctly by starting Report Manager on a different computer.</span></span> <span data-ttu-id="dacde-159">Per altre informazioni, vedere [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dacde-159">For more information, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dacde-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dacde-160">See Also</span></span>  
 <span data-ttu-id="dacde-161">[Configurare l'account del servizio del server di report &#40;Gestione configurazione SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="dacde-161">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="dacde-162">[Configurare gli URL del server di report &#40;Gestione configurazione SSRS&#41;](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="dacde-162">[Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="dacde-163">[Creazione di un database del server di report &#40;Configuration Manager SSRS&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="dacde-163">[Create a Report Server Database  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="dacde-164">[Configurare l'account del servizio del server di report &#40;Gestione configurazione SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="dacde-164">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="dacde-165">Gestire un server di report in modalità nativa di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="dacde-165">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
