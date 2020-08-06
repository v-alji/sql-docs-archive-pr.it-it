---
title: Problemi di aggiornamento Reporting Services (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Report Manager [Reporting Services], upgrade issues
- Reporting Services, upgrades
- upgrading Reporting Services
- report servers [Reporting Services], upgrade issues
ms.assetid: d9663f25-98d7-4508-ae3c-55a7277211bd
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 569afe735d68a724c0b4cc61ad2b7767088c2b30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637603"
---
# <a name="reporting-services-upgrade-issues-upgrade-advisor"></a><span data-ttu-id="b272e-102">Problemi di aggiornamento di Reporting Services (Preparazione aggiornamento)</span><span class="sxs-lookup"><span data-stu-id="b272e-102">Reporting Services Upgrade Issues (Upgrade Advisor)</span></span>
  <span data-ttu-id="b272e-103">Negli argomenti seguenti vengono descritti i [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] problemi che potrebbero influire sull'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b272e-103">The following topics describe the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] issues that might affect your upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="b272e-104">Vengono illustrate le azioni che è possibile eseguire per ridurre l'effetto di queste modifiche nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="b272e-104">The topics describe actions that you can take to mitigate the effect of these changes on your environment.</span></span>  
  
 <span data-ttu-id="b272e-105">Con Preparazione aggiornamento viene analizzata un'installazione del server di report.</span><span class="sxs-lookup"><span data-stu-id="b272e-105">Upgrade Advisor analyzes a report server installation.</span></span> <span data-ttu-id="b272e-106">Se sono installati solo i componenti client (ad esempio se Progettazione report è l'unico componente di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installato nel computer), non verrà segnalato alcun problema.</span><span class="sxs-lookup"><span data-stu-id="b272e-106">If only client components are installed (for example, if Report Designer is the only [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] component installed on the computer), no issues will be reported.</span></span>  
  
 <span data-ttu-id="b272e-107">A seconda della modalità di configurazione dell'installazione, è possibile che vengano rilevati altri problemi non segnalati da Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b272e-107">Depending on how you configured your installation, you may encounter additional issues that are not reported by Upgrade Advisor.</span></span> <span data-ttu-id="b272e-108">Tali problemi non impediscono il corretto aggiornamento di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], ma possono influire sull'esecuzione di report e applicazioni al termine di un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b272e-108">These issues do not prevent a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] upgrade from succeeding, but they may affect how reports and applications run after an upgrade is finished.</span></span> <span data-ttu-id="b272e-109">Per ulteriori informazioni su questi problemi, vedere "Compatibilità con le versioni precedenti Reporting Services" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b272e-109">To learn about these issues, see "Reporting Services Backward Compatibility" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="b272e-110">Se non è possibile utilizzare il programma di installazione per aggiornare un'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], installare una nuova istanza di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ed eseguire la migrazione dell'installazione esistente alla nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="b272e-110">If you cannot use Setup to upgrade a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation, you can install a new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance and migrate your existing installation to the new instance.</span></span> <span data-ttu-id="b272e-111">Per ulteriori informazioni, vedere l'argomento relativo all'aggiornamento e alla migrazione Reporting Services nella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentazione online di, [aggiornare ed eseguire la migrazione di Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="b272e-111">For more information, see "Upgrade and Migrate Reporting Services" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online, [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
 <span data-ttu-id="b272e-112">Negli argomenti seguenti vengono descritti i problemi noti segnalati da Preparazione aggiornamento e viene illustrato come modificare l'installazione esistente per consentire l'esecuzione di un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b272e-112">The following topics describe known issues that are reported by Upgrade Advisor, and explain how you can modify your existing installation to allow an upgrade to occur.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b272e-113">Per analizzare un'istanza di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è necessario aver installato Preparazione aggiornamento nel server di report.</span><span class="sxs-lookup"><span data-stu-id="b272e-113">Upgrade Advisor must be installed on the report server to analyze an instance of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="b272e-114">non supporta l'analisi remota.</span><span class="sxs-lookup"><span data-stu-id="b272e-114">does not support remote analysis.</span></span>  
>   
>  <span data-ttu-id="b272e-115">Per ulteriori informazioni, vedere [installazione di preparazione aggiornamento](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="b272e-115">For more information, see [Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b272e-116">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b272e-116">In This Section</span></span>  
  
-   [<span data-ttu-id="b272e-117">Certificati client sul sito Web del server di report &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-117">Client certificates on the report server web site &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/client-certificates-on-the-report-server-web-site-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-118">Sono state rilevate estensioni personalizzate nel server di report &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-118">Custom extensions were detected on the report server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/custom-extensions-were-detected-on-the-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-119">Sono stati rilevati elementi del report personalizzati nel server di report &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-119">Custom report items were detected on the report server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/custom-report-items-were-detected-on-the-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-120">Componenti per la compatibilità con le versioni precedenti di IIS non rilevati &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-120">IIS backward compatibility components were not detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/iis-backward-compatibility-components-were-not-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-121">Restrizione degli indirizzi IP rilevata &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-121">IP address restriction detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/ip-address-restriction-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-122">Filtri ISAPI rilevati nel sito del server di report &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-122">ISAPI filters detected on the report server site &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/isapi-filters-detected-on-the-report-server-site-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-123">Sono state rilevate estensioni obsolete nel computer del server di report &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-123">Obsolete extensions were detected on the report server computer &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/obsolete-extensions-were-detected-on-the-report-server-computer-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-124">Il database del server di report non è configurato &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-124">Report server database is not configured &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/report-server-database-is-not-configured-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-125">Il gruppo di servizi Web ReportServer SQL Server 2005 rilevato &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-125">SQL Server 2005 Report Server Web Service group detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/sql-server-2005-report-server-web-service-group-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-126">Le directory virtuali non sono specificate &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-126">Virtual directories are unspecified &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/virtual-directories-are-unspecified-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-127">Il metodo di autenticazione della directory virtuale non è supportato &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-127">Virtual directory has unsupported authentication method &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/virtual-directory-has-unsupported-authentication-method-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-128">Modifiche ai limiti di memoria e CPU per SQL Server Standard ed Enterprise &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-128">Changes to CPU and memory limits for SQL Server Standard and Enterprise &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/cpu-memory-limits-changes-sql-server-standard-enterprise-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-129">Account di dominio necessari per la farm di SharePoint &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-129">Domain accounts required for SharePoint farm &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/domain-accounts-required-for-sharepoint-farm-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-130">Esplorazione diretta del server di report &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-130">Direct Browsing to Report Server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/direct-browsing-to-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-131">Microsoft SharePoint 2007 è installato &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-131">Microsoft SharePoint 2007 is Installed &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/microsoft-sharepoint-2007-is-installed-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-132">Microsoft SQL Server Reporting Services servizio SharePoint Shared è installato side-by-side &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-132">Microsoft SQL Server Reporting Services SharePoint Shared Service is Installed Side by Side &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/sql-server-reporting-services-sharepoint-shared-service-side-by-side-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-133">Regole di confronto di motore di database server incompatibili &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="b272e-133">Incompatible Database Engine Server Collation &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/incompatible-database-engine-server-collation-upgrade-advisor.md)  
  
-   [<span data-ttu-id="b272e-134">Altri problemi di aggiornamento di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b272e-134">Other Reporting Services Upgrade Issues</span></span>](../../../2014/sql-server/install/other-reporting-services-upgrade-issues.md)  
  
  
