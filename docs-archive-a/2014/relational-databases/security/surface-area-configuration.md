---
title: Configurazione superficie di attacco | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- reducing attackable surface area
- upgrading SQL Server, security
- surface area configuration [SQL Server]
- surface area configuration [SQL Server], about surface area configuration
- attackable surface area [SQL Server]
- installing SQL Server, security
ms.assetid: f741169c-1453-4ad2-830b-bf2be27d712f
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: ef64fbbeb2b8953ff3816db63572b499d42f012e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713980"
---
# <a name="surface-area-configuration"></a><span data-ttu-id="09dde-102">Configurazione superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="09dde-102">Surface Area Configuration</span></span>
  <span data-ttu-id="09dde-103">Nella configurazione predefinita delle nuove installazioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]molte funzionalità non sono abilitate.</span><span class="sxs-lookup"><span data-stu-id="09dde-103">In the default configuration of new installations of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], many features are not enabled.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="09dde-104">installa in modo selettivo e avvia solo le funzionalità e i servizi chiave in modo da ridurre al minimo il numero di funzionalità che potrebbero essere attaccate da un utente malintenzionato.</span><span class="sxs-lookup"><span data-stu-id="09dde-104">selectively installs and starts only key services and features, to minimize the number of features that can be attacked by a malicious user.</span></span> <span data-ttu-id="09dde-105">L'amministratore di sistema può modificare i valori predefiniti al momento dell'installazione e abilitare o disabilitare in modo selettivo le caratteristiche di un'istanza in esecuzione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09dde-105">A system administrator can change these defaults at installation time and also selectively enable or disable features of a running instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="09dde-106">Alcuni componenti, inoltre, potrebbero non essere disponibili durante la connessione da altri computer fino a quando non si configurano i protocolli.</span><span class="sxs-lookup"><span data-stu-id="09dde-106">Additionally, some components may not be available when connecting from other computers until protocols are configured.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09dde-107">Diversamente dalle nuove installazioni, durante un aggiornamento non è disabilitato alcun servizio o caratteristica esistente, ma è possibile applicare opzioni di configurazione della superficie di attacco aggiuntive al termine dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="09dde-107">Unlike new installations, no existing services or features are turned off during an upgrade, but additional surface area configuration options can be applied after the upgrade is completed.</span></span>  
  
## <a name="protocols-connection-and-startup-options"></a><span data-ttu-id="09dde-108">Protocolli e opzioni di connessione e avvio</span><span class="sxs-lookup"><span data-stu-id="09dde-108">Protocols, Connection, and Startup Options</span></span>  
 <span data-ttu-id="09dde-109">Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consente di avviare e arrestare servizi, configurare le opzioni di avvio e abilitare protocolli e altre opzioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="09dde-109">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to start and stop services, configure the startup options, and enable protocols and other connection options.</span></span>  
  
#### <a name="to-start-sql-server-configuration-manager"></a><span data-ttu-id="09dde-110">Per avviare Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="09dde-110">To start SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="09dde-111">Fare clic sul menu **Start** , scegliere **Tutti i programmi**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Strumenti di configurazione**e quindi **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="09dde-111">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
    -   <span data-ttu-id="09dde-112">Usare l'area **Servizi di SQL Server** per avviare i componenti e configurare le opzioni iniziali automatiche.</span><span class="sxs-lookup"><span data-stu-id="09dde-112">Use the **SQL Server Services** area to start components and configure the automatic starting options.</span></span>  
  
    -   <span data-ttu-id="09dde-113">Usare l'area **Configurazione di rete SQL Server** per abilitare protocolli e opzioni di connessione, ad esempio le porte TCP/IP fisse, o per forzare la crittografia.</span><span class="sxs-lookup"><span data-stu-id="09dde-113">Use the **SQL Server Network Configuration** area to enable connection protocols, and connection options such as fixed TCP/IP ports, or forcing encryption.</span></span>  
  
 <span data-ttu-id="09dde-114">Per altre informazioni, vedere [Gestione configurazione SQL Server](../sql-server-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="09dde-114">For more information, see [SQL Server Configuration Manager](../sql-server-configuration-manager.md).</span></span> <span data-ttu-id="09dde-115">La connettività remota può dipendere anche dalla corretta configurazione di un firewall.</span><span class="sxs-lookup"><span data-stu-id="09dde-115">Remote connectivity can also depend upon the correct configuration of a firewall.</span></span> <span data-ttu-id="09dde-116">Per altre informazioni, vedere [Configurare Windows Firewall per consentire l'accesso a SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="09dde-116">For more information, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
## <a name="enabling-and-disabling-features"></a><span data-ttu-id="09dde-117">Abilitazione e disabilitazione di caratteristiche</span><span class="sxs-lookup"><span data-stu-id="09dde-117">Enabling and Disabling Features</span></span>  
 <span data-ttu-id="09dde-118">L'abilitazione e la disabilitazione delle caratteristiche di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] può essere configurata tramite facet in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09dde-118">Enabling and disabling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features can be configured using facets in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-configure-surface-area-using-facets"></a><span data-ttu-id="09dde-119">Per configurare la superficie di attacco tramite facet</span><span class="sxs-lookup"><span data-stu-id="09dde-119">To configure surface area using facets</span></span>  
  
1.  <span data-ttu-id="09dde-120">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] connettersi a un componente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09dde-120">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] connect to a component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="09dde-121">In Esplora oggetti fare clic con il pulsante destro del mouse sul server, quindi scegliere **Facet**.</span><span class="sxs-lookup"><span data-stu-id="09dde-121">In Object Explorer, right-click the server, and then click **Facets**.</span></span>  
  
3.  <span data-ttu-id="09dde-122">Nella finestra di dialogo **Visualizza facet** espandere l'elenco **Facet** e selezionare il facet **Surface Area Configuration** appropriato tra**Configurazione superficie di attacco**, **Configurazione superficie di attacco per Analysis Services**o **Configurazione superficie di attacco per Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="09dde-122">In the **View Facets** dialog box, expand the **Facet** list, and select the appropriate **Surface Area Configuration** facet (**Surface Area Configuration**, **Surface Area Configuration for Analysis Services**, or **Surface Area Configuration for Reporting Services**).</span></span>  
  
4.  <span data-ttu-id="09dde-123">Nell'area **Proprietà facet** selezionare i valori desiderati per ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="09dde-123">In the **Facet properties** area, select the values that you want for each property.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="09dde-124">Per controllare periodicamente la configurazione di un facet, utilizzare la gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="09dde-124">To periodically check the configuration of a facet, use Policy-Based Management.</span></span> <span data-ttu-id="09dde-125">Per altre informazioni sulla gestione basata su criteri, vedere [Amministrazione di server tramite la gestione basata su criteri](../policy-based-management/administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="09dde-125">For more information about Policy-Based Management, see [Administer Servers by Using Policy-Based Management](../policy-based-management/administer-servers-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="09dde-126">È possibile impostare le opzioni del [!INCLUDE[ssDE](../../includes/ssde-md.md)] anche tramite la stored procedure `sp_configure`.</span><span class="sxs-lookup"><span data-stu-id="09dde-126">You can also set [!INCLUDE[ssDE](../../includes/ssde-md.md)] options using the `sp_configure` stored procedure.</span></span> <span data-ttu-id="09dde-127">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="09dde-127">For more information, see [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
 <span data-ttu-id="09dde-128">Per modificare la proprietà **EnableIntegrated Security** di [!INCLUDE[ssRS](../../includes/ssrs.md)], usare le impostazioni delle proprietà in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09dde-128">To change the **EnableIntegrated Security** property of [!INCLUDE[ssRS](../../includes/ssrs.md)], use the property settings in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="09dde-129">Per modificare la proprietà **Pianificazione eventi e recapito report** e la proprietà **Accesso HTTP e servizi Web** , modificare il file di configurazione **RSReportServer.config** .</span><span class="sxs-lookup"><span data-stu-id="09dde-129">To change the **Schedule events and report delivery** property and the **Web service and HTTP access** property, edit the **RSReportServer.config** configuration file.</span></span>  
  
## <a name="command-prompt-options"></a><span data-ttu-id="09dde-130">Opzioni del prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="09dde-130">Command-prompt Options</span></span>  
 <span data-ttu-id="09dde-131">Usare il cmdlet **Invoke-PolicyEvaluation**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di PowerShell per richiamare i criteri di configurazione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="09dde-131">Use the **Invoke-PolicyEvaluation**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell cmdlet to invoke Surface Area Configuration Policies.</span></span> <span data-ttu-id="09dde-132">Per altre informazioni, vedere [Utilizzo di cmdlet del motore di database](../../database-engine/use-the-database-engine-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="09dde-132">For more information, see [Use the Database Engine cmdlets](../../database-engine/use-the-database-engine-cmdlets.md).</span></span>  
  
## <a name="soap-and-service-broker-endpoints"></a><span data-ttu-id="09dde-133">Endpoint SOAP e di Service Broker</span><span class="sxs-lookup"><span data-stu-id="09dde-133">SOAP and Service Broker Endpoints</span></span>  
 <span data-ttu-id="09dde-134">Per disabilitare gli endpoint, utilizzare la gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="09dde-134">To turn endpoints off, use Policy-Based Management.</span></span> <span data-ttu-id="09dde-135">Per creare e modificare le proprietà degli endpoint, usare [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) e [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="09dde-135">To create and alter the properties of endpoints, use [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) and [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="09dde-136">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="09dde-136">Related Content</span></span>  
 [<span data-ttu-id="09dde-137">Centro sicurezza per il motore di Database di SQL Server e il Database SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="09dde-137">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
 [<span data-ttu-id="09dde-138">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="09dde-138">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
