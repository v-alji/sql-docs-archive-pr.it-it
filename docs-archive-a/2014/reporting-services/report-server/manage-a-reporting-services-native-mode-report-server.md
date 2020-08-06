---
title: Gestire un server di report in modalità nativa di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Configuration tool
- configuration options [Reporting Services]
- report servers [Reporting Services], configuring
ms.assetid: 6ca03a09-d6a8-4c93-ba12-1c99dcbfb618
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d44a9329074a20c04f878c055674ea563b297f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630283"
---
# <a name="manage-a-reporting-services-native-mode-report-server"></a><span data-ttu-id="c3314-102">Gestione di un server di report in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="c3314-102">Manage a Reporting Services Native Mode Report Server</span></span>
  <span data-ttu-id="c3314-103">In questa sezione sono disponibili le procedure per la configurazione di un'istanza del server di report in modalità nativa utilizzando Gestione configurazione Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c3314-103">This section contains procedures for configuring a native mode report server instance using the Reporting Services Configuration Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3314-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c3314-104">In This Section</span></span>  
 <span data-ttu-id="c3314-105">Gli argomenti di questa sezione sono organizzati in categorie per consentire un'individuazione ancora più semplice delle indicazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="c3314-105">The topics in this section are organized into categories so that you can more easily find the instructions you want.</span></span> <span data-ttu-id="c3314-106">Nella prima sezione sono inclusi gli argomenti per le attività di configurazione di base per un server di report in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="c3314-106">The first section contains topics for basic configuration tasks for a native mode report server.</span></span> <span data-ttu-id="c3314-107">Nella seconda sezione sono inclusi gli argomenti relativi alla configurazione avanzata.</span><span class="sxs-lookup"><span data-stu-id="c3314-107">The second section contains advanced configuration topics.</span></span> <span data-ttu-id="c3314-108">Nella terza sezione sono inclusi gli argomenti per la configurazione di un server di report eseguito in modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c3314-108">The third section contains topics for configuring a report server to run in SharePoint integrated mode.</span></span>  
  
### <a name="basic-configuration"></a><span data-ttu-id="c3314-109">Configurazione di base</span><span class="sxs-lookup"><span data-stu-id="c3314-109">Basic Configuration</span></span>  
 [<span data-ttu-id="c3314-110">Gestione configurazione Reporting Services &#40;modalità nativa&#41;</span><span class="sxs-lookup"><span data-stu-id="c3314-110">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
 <span data-ttu-id="c3314-111">Viene indicata la procedura per avviare lo strumento di configurazione di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c3314-111">Provides steps for starting the Reporting Services Configuration tool.</span></span>  
  
 [<span data-ttu-id="c3314-112">Configurare l'account del servizio del server di report &#40;Gestione configurazione SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c3314-112">Configure a Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="c3314-113">Viene illustrato come specificare le informazioni relative ad account e password per il servizio del server di report.</span><span class="sxs-lookup"><span data-stu-id="c3314-113">Explains how to specify account and password information for the Report Server service.</span></span>  
  
 [<span data-ttu-id="c3314-114">Registrare un nome dell'entità servizio &#40;SPN&#41; per un server di report</span><span class="sxs-lookup"><span data-stu-id="c3314-114">Register a Service Principal Name &#40;SPN&#41; for a Report Server</span></span>](register-a-service-principal-name-spn-for-a-report-server.md)  
 <span data-ttu-id="c3314-115">Viene illustrato come registrare manualmente un SPN per un server di report eseguito tramite un account utente di dominio in una rete che utilizza l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="c3314-115">Explains how to manually register an SPN for a report server that runs under a domain user account on a network that uses Kerberos authentication.</span></span>  
  
 [<span data-ttu-id="c3314-116">Configurare un URL &#40;Gestione configurazione SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c3314-116">Configure a URL  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-a-url-ssrs-configuration-manager.md)  
 <span data-ttu-id="c3314-117">Viene illustrato come configurare uno o più URL utilizzati per accedere al servizio Web ReportServer e a Gestione report.</span><span class="sxs-lookup"><span data-stu-id="c3314-117">Explains how to establish one or more URLs used to access the Report Server Web service and Report Manager.</span></span>  
  
 [<span data-ttu-id="c3314-118">Creare un database del server di report in modalità nativa &#40;Gestione configurazione SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c3314-118">Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md)  
 <span data-ttu-id="c3314-119">Illustra le procedure per creare un database del server di report.</span><span class="sxs-lookup"><span data-stu-id="c3314-119">Provides steps for creating a report server database.</span></span> <span data-ttu-id="c3314-120">Questa procedura è obbligatoria per la distribuzione di un'installazione di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c3314-120">This step is required for deploying a Reporting Services installation.</span></span>  
  
### <a name="advanced-or-optional-configuration"></a><span data-ttu-id="c3314-121">Configurazione avanzata o facoltativa</span><span class="sxs-lookup"><span data-stu-id="c3314-121">Advanced or Optional Configuration</span></span>  
 [<span data-ttu-id="c3314-122">Configurare una distribuzione con scalabilità orizzontale di un server di report in modalità nativa &#40;Gestione configurazione SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c3314-122">Configure a Native Mode Report Server Scale-Out Deployment &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md)  
 <span data-ttu-id="c3314-123">Viene indicata la procedura per la configurazione di più server di report in modo che condividano un database del server di report.</span><span class="sxs-lookup"><span data-stu-id="c3314-123">Provides steps for configuring multiple report servers to share a report server database.</span></span>  
  
 [<span data-ttu-id="c3314-124">Configurare un server di report per il recapito tramite posta elettronica &#40;Configuration Manager SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c3314-124">Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)  
 <span data-ttu-id="c3314-125">Illustra le procedure per configurare un server di report per la distribuzione tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c3314-125">Provides steps for configuring a report server for e-mail distribution.</span></span>  
  
 [<span data-ttu-id="c3314-126">Configurare un firewall per l'accesso al server di report</span><span class="sxs-lookup"><span data-stu-id="c3314-126">Configure a Firewall for Report Server Access</span></span>](configure-a-firewall-for-report-server-access.md)  
 <span data-ttu-id="c3314-127">Viene illustrato come aprire le porte utilizzate per le richieste in ingresso e le risposte in uscita da un server di report.</span><span class="sxs-lookup"><span data-stu-id="c3314-127">Explains how to open ports used for inbound requests and outbound responses from a report server.</span></span>  
  
 [<span data-ttu-id="c3314-128">Configurare un server di report in modalità nativa per gli amministratori locali &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c3314-128">Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;</span></span>](configure-a-native-mode-report-server-for-local-administration-ssrs.md)  
 <span data-ttu-id="c3314-129">Vengono descritti i passaggi aggiuntivi richiesti per connettersi a Gestione report o a un server di report usando http://localhost.</span><span class="sxs-lookup"><span data-stu-id="c3314-129">Describes additional steps required to connect to Report Manager or a report server using http://localhost.</span></span>  
  
 [<span data-ttu-id="c3314-130">Configurare un server di report per l'amministrazione remota</span><span class="sxs-lookup"><span data-stu-id="c3314-130">Configure a Report Server for Remote Administration</span></span>](configure-a-report-server-for-remote-administration.md)  
 <span data-ttu-id="c3314-131">Viene illustrato come configurare un'istanza remota del server di report a cui connettersi e da configurare per un computer diverso.</span><span class="sxs-lookup"><span data-stu-id="c3314-131">Explains how to configure a remote report server instance so that you can connect to and configure it from a different computer.</span></span>  
  
 [<span data-ttu-id="c3314-132">Abilitare o disabilitare le funzionalità di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c3314-132">Turn Reporting Services Features On or Off</span></span>](turn-reporting-services-features-on-or-off.md)  
 <span data-ttu-id="c3314-133">Viene illustrato come rimuovere le caratteristiche non utilizzate da un'installazione di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c3314-133">Explains how to remove unused features in a Reporting Services installation.</span></span>  
  
 [<span data-ttu-id="c3314-134">Abilita errori remoti &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c3314-134">Enable Remote Errors &#40;Reporting Services&#41;</span></span>](enable-remote-errors-reporting-services.md)  
 <span data-ttu-id="c3314-135">Viene illustrato come impostare le proprietà di un server di report in modo da restituire ulteriori informazioni sulle condizioni di errore che si verificano nei server remoti.</span><span class="sxs-lookup"><span data-stu-id="c3314-135">Explains how to set server properties on a report server to return additional information about error conditions that occur on remote servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3314-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3314-136">See Also</span></span>  
 <span data-ttu-id="c3314-137">[Configurare e amministrare un server di report &#40;modalità nativa SSRS&#41;](configure-and-administer-a-report-server-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="c3314-137">[Configure and Administer a Report Server &#40;SSRS Native Mode&#41;](configure-and-administer-a-report-server-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="c3314-138">Configurazione e amministrazione di un server di report &#40;modalità SharePoint di Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c3314-138">Configuration and Administration of a Report Server &#40;Reporting Services SharePoint Mode&#41;</span></span>](../configure-administer-report-server-reporting-services-sharepoint-mode.md)  
  
  
