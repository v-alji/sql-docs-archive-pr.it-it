---
title: Configurare e amministrare un server di report (modalità nativa SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, components
- deploying [Reporting Services], component options
- report servers [Reporting Services], component options
- configuration options [Reporting Services]
- administering Reporting Services
- components [Reporting Services], configuring
- configuring servers [Reporting Services]
ms.assetid: cfec012b-56f1-4346-9814-247acf22351c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5164fd2f9170cb092a45394f64f06d7622253f2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630303"
---
# <a name="configure-and-administer-a-report-server-ssrs-native-mode"></a><span data-ttu-id="c661c-102">Configurare e amministrare un server di report (modalità nativa SSRS)</span><span class="sxs-lookup"><span data-stu-id="c661c-102">Configure and Administer a Report Server (SSRS Native Mode)</span></span>
  <span data-ttu-id="c661c-103">In questo argomento vengono riepilogati gli approcci disponibili per la configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c661c-103">This topic summarizes the approaches that you can use to configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="c661c-104">È inoltre incluso un elenco di argomenti che illustrano come configurare componenti, caratteristiche specifiche o del server.</span><span class="sxs-lookup"><span data-stu-id="c661c-104">It also includes a list of topics that explain how to configure specific components, features, or server capabilities.</span></span> <span data-ttu-id="c661c-105">Per configurare [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], è possibile:</span><span class="sxs-lookup"><span data-stu-id="c661c-105">To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can:</span></span>  
  
-   <span data-ttu-id="c661c-106">Utilizzare Gestione configurazione Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c661c-106">Use the Reporting Services Configuration Manager.</span></span> <span data-ttu-id="c661c-107">Molti degli argomenti di questa sezione contengono informazioni su come configurare caratteristiche specifiche tramite questo strumento.</span><span class="sxs-lookup"><span data-stu-id="c661c-107">Many of the topics in this section contain information about how to configure specific features through this tool.</span></span>  
  
-   <span data-ttu-id="c661c-108">Usare [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] per personalizzare le proprietà del server, attivare la funzionalità Report personali, attivare i log di traccia e impostare valori predefiniti a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="c661c-108">Use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to customize server properties, enable My Reports, enable trace logs, and set site-wide defaults.</span></span> <span data-ttu-id="c661c-109">Per altre informazioni sulle impostazioni del sito, vedere [Server di report di Reporting Services &#40;modalità nativa&#41;](reporting-services-report-server-native-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="c661c-109">For more information about site settings, see [Reporting Services Report Server &#40;Native Mode&#41;](reporting-services-report-server-native-mode.md) for Management Studio.</span></span> <span data-ttu-id="c661c-110">Si noti che è possibile creare ed eseguire uno script che consente di impostare le proprietà del server a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="c661c-110">Note that you can create and run script that sets server properties programmatically.</span></span> <span data-ttu-id="c661c-111">Per altre informazioni, vedere [Utilizzare script per l'esecuzione di attività di distribuzione e di amministrazione](../tools/script-deployment-and-administrative-tasks.md) e [Proprietà di sistema del server di report](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c661c-111">For more information, see [Script Deployment and Administrative Tasks](../tools/script-deployment-and-administrative-tasks.md) and [Report Server System Properties](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md).</span></span>  
  
-   <span data-ttu-id="c661c-112">Utilizzare Gestione report per concedere autorizzazioni per accedere al server di report.</span><span class="sxs-lookup"><span data-stu-id="c661c-112">Use Report Manager to grant permissions to access the report server.</span></span> <span data-ttu-id="c661c-113">Le autorizzazioni vengono assegnate tramite assegnazioni di ruolo definite per ogni account utente o di gruppo.</span><span class="sxs-lookup"><span data-stu-id="c661c-113">Permissions are conveyed through role assignments that you define for each user or group account.</span></span> <span data-ttu-id="c661c-114">Per altre informazioni, vedere [Ruoli e autorizzazioni &#40;Reporting Services&#41;](../security/roles-and-permissions-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="c661c-114">For more information, see [Roles and Permissions &#40;Reporting Services&#41;](../security/roles-and-permissions-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="c661c-115">Modificare i file di configurazione per cambiare le impostazioni delle applicazioni (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="c661c-115">Optionally, modify configuration files to change application settings.</span></span> <span data-ttu-id="c661c-116">Per altre informazioni su ogni file e le linee guida per modificarli, vedere [File di configurazione di Reporting Services](reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="c661c-116">For more information about each file and guidelines for modifying them, see [Reporting Services Configuration Files](reporting-services-configuration-files.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c661c-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c661c-117">In This Section</span></span>  
 [<span data-ttu-id="c661c-118">Configurare gli URL del server di report &#40;Gestione configurazione SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c661c-118">Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
 <span data-ttu-id="c661c-119">Descrive come definire gli URL utilizzati per accedere al servizio del server di report e a Gestione report.</span><span class="sxs-lookup"><span data-stu-id="c661c-119">Describes how to define the URLs used to access the report server and Report Manager.</span></span>  
  
 [<span data-ttu-id="c661c-120">Configurare l'account del servizio del server di report &#40;Gestione configurazione SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c661c-120">Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="c661c-121">Include indicazioni e procedure per la modifica dell'account e delle password dei servizi.</span><span class="sxs-lookup"><span data-stu-id="c661c-121">Provides recommendations and steps on how to modify service account and password.</span></span>  
  
 [<span data-ttu-id="c661c-122">Creare un database del server di report &#40;Gestione configurazione SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c661c-122">Create a Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md)  
 <span data-ttu-id="c661c-123">Descrive come creare un database del server di report necessario per l'archiviazione di oggetti e metadati del server.</span><span class="sxs-lookup"><span data-stu-id="c661c-123">Describes how to create a report server database, required for storing server metadata and objects.</span></span>  
  
 [<span data-ttu-id="c661c-124">Configurare una connessione del database del server di report &#40;Gestione configurazione SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c661c-124">Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md)  
 <span data-ttu-id="c661c-125">Descrive come modificare la stringa di connessione usata dal server di report per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="c661c-125">Describes how to modify the connection string used by the report server to connect to the report server database.</span></span>  
  
 [<span data-ttu-id="c661c-126">Configurare un server di report per il recapito tramite posta elettronica &#40;Configuration Manager SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c661c-126">Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)  
 <span data-ttu-id="c661c-127">Descrive come configurare un server di report in modo da supportare la distribuzione dei report tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c661c-127">Describes how to configure a report server to support e-mail report distribution.</span></span>  
  
 [<span data-ttu-id="c661c-128">Configurare l'account di esecuzione automatica &#40;Gestione configurazione SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c661c-128">Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="c661c-129">Descrive come configurare un account utente per l'esecuzione automatica dei report.</span><span class="sxs-lookup"><span data-stu-id="c661c-129">Describes how to configure a user account to process reports in unattended mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c661c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c661c-130">See Also</span></span>  
 <span data-ttu-id="c661c-131">[Configurare l'accesso Generatore report](configure-report-builder-access.md) </span><span class="sxs-lookup"><span data-stu-id="c661c-131">[Configure Report Builder Access](configure-report-builder-access.md) </span></span>  
 <span data-ttu-id="c661c-132">[File di configurazione di Reporting Services](reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="c661c-132">[Reporting Services Configuration Files](reporting-services-configuration-files.md) </span></span>  
 <span data-ttu-id="c661c-133">[Gestione configurazione Reporting Services &#40;modalità nativa&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="c661c-133">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="c661c-134">[Sicurezza e protezione Reporting Services](../security/reporting-services-security-and-protection.md) </span><span class="sxs-lookup"><span data-stu-id="c661c-134">[Reporting Services Security and Protection](../security/reporting-services-security-and-protection.md) </span></span>  
 [<span data-ttu-id="c661c-135">Server di report di Reporting Services &#40;modalità nativa&#41;</span><span class="sxs-lookup"><span data-stu-id="c661c-135">Reporting Services Report Server &#40;Native Mode&#41;</span></span>](reporting-services-report-server-native-mode.md)  
  
  
