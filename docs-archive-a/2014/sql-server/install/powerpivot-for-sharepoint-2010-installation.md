---
title: PowerPivot per SharePoint 2010 installazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 8d47dde7-c941-4280-a934-e2fe3f9a938f
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ba04dfdc69b1c510a800c062586e45f8873c8e8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635926"
---
# <a name="powerpivot-for-sharepoint-2010-installation"></a><span data-ttu-id="83a96-102">PowerPivot for SharePoint 2010 Installation</span><span class="sxs-lookup"><span data-stu-id="83a96-102">PowerPivot for SharePoint 2010 Installation</span></span>
  [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] <span data-ttu-id="83a96-103">è una raccolta di componenti server che forniscono funzionalità di elaborazione di query e controllo di gestione per le cartelle di lavoro di [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] da pubblicare in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="83a96-103">is a collection of server components that provide query processing and management control over [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks that you publish to SharePoint.</span></span> <span data-ttu-id="83a96-104">I servizi includono il motore di Analysis Services e il servizio di sistema [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83a96-104">Services include the Analysis Services engine and [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83a96-105">Per informazioni relative a [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] e all'installazione con SharePoint Server 2013, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="83a96-105">For information regarding [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] and installation with SharePoint Server 2013, see the following:</span></span>  
>   
>  -   <span data-ttu-id="83a96-106">La sezione "SQL Server 2012 SP1" di [Panoramica dell'installazione di SQL Server manutenzione](../../../2014/sql-server/install/overview-of-sql-server-servicing-installation.md).</span><span class="sxs-lookup"><span data-stu-id="83a96-106">The "SQL Server 2012 SP1" section of [Overview of SQL Server Servicing Installation](../../../2014/sql-server/install/overview-of-sql-server-servicing-installation.md).</span></span>  
  
 <span data-ttu-id="83a96-107">Analysis Services fornisce elaborazione lato server per le cartelle di lavoro di Excel che contengono dati [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83a96-107">Analysis Services provides server-side processing for Excel workbooks that contain [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data.</span></span> <span data-ttu-id="83a96-108">Il servizio di sistema [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] viene utilizzato con Analysis Services, consentendo di aggiungere l'integrazione con SharePoint, il bilanciamento del carico e la gestione delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="83a96-108">[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service works alongside Analysis Services, adding SharePoint integration, load balancing and connection management.</span></span> [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)]<span data-ttu-id="83a96-109">estende Excel Services abbinando la relativa funzionalità di elaborazione dati su larga scala ai servizi di rendering dei dati forniti da Excel.</span><span class="sxs-lookup"><span data-stu-id="83a96-109">extends Excel Services by pairing its large scale data processing capability with the data rendering services that Excel provides.</span></span>  
  
 <span data-ttu-id="83a96-110">Per installare [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)], usare i supporti di installazione di [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83a96-110">To install [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)], use the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]installation media.</span></span>  
  
 <span data-ttu-id="83a96-111">Per istruzioni sugli scenari di distribuzione avanzati, vedere elenco di controllo per la [distribuzione: Reporting Services, Power View e PowerPivot per SharePoint](deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) e [l'elenco di controllo per la distribuzione: scalabilità orizzontale mediante l'aggiunta di server PowerPivot a una farm di SharePoint 2010](../../../2014/sql-server/install/deployment-checklist-scale-out-adding-powerpivot-servers-sharepoint-2010-farm.md).</span><span class="sxs-lookup"><span data-stu-id="83a96-111">For instructions on advanced deployment scenarios, see [Deployment Checklist: Reporting Services, Power View, and PowerPivot for SharePoint](deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) and [Deployment Checklist: Scale-out by adding PowerPivot Servers to a SharePoint 2010 farm](../../../2014/sql-server/install/deployment-checklist-scale-out-adding-powerpivot-servers-sharepoint-2010-farm.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83a96-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="83a96-112">In This Section</span></span>  
 [<span data-ttu-id="83a96-113">Installare PowerPivot per SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="83a96-113">Install PowerPivot for SharePoint 2010</span></span>](../../../2014/sql-server/install/install-powerpivot-for-sharepoint-2010.md)  
  
 [<span data-ttu-id="83a96-114">Installazione del provider OLE DB Analysis Services nei server di SharePoint</span><span class="sxs-lookup"><span data-stu-id="83a96-114">Install the Analysis Services OLE DB Provider on SharePoint Servers</span></span>](../../../2014/sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md)  
  
 [<span data-ttu-id="83a96-115">Installare ADOMD.NET in server front-end Web in cui viene eseguita Amministrazione centrale</span><span class="sxs-lookup"><span data-stu-id="83a96-115">Install ADOMD.NET on Web Front-End Servers Running Central Administration</span></span>](../../../2014/sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md)  
  
 [<span data-ttu-id="83a96-116">Installare Servizi dati di ADO.NET per supportare esportazioni di feed di dati di elenchi SharePoint</span><span class="sxs-lookup"><span data-stu-id="83a96-116">Install ADO.NET Data Services to support data feed exports of SharePoint lists</span></span>](../../../2014/sql-server/install/install-ado-net-data-services-to-support-data-feed-exports-of-sharepoint-lists.md)  
  
 [<span data-ttu-id="83a96-117">Installazione di PowerPivot dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="83a96-117">Install PowerPivot from the Command Prompt</span></span>](../../../2014/sql-server/install/install-powerpivot-from-the-command-prompt.md)  
  
 [<span data-ttu-id="83a96-118">Disinstallare PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="83a96-118">Uninstall PowerPivot for SharePoint</span></span>](../../../2014/sql-server/install/uninstall-power-pivot-for-sharepoint.md)  
  
 [<span data-ttu-id="83a96-119">Ripristino di PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="83a96-119">Repair PowerPivot for SharePoint</span></span>](../../../2014/sql-server/install/repair-powerpivot-for-sharepoint.md)  
  
 [<span data-ttu-id="83a96-120">Configurazione iniziale &#40;PowerPivot per SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="83a96-120">Initial Configuration &#40;PowerPivot for SharePoint&#41;</span></span>](../../../2014/sql-server/install/initial-configuration-powerpivot-for-sharepoint.md)  
  
## <a name="see-also"></a><span data-ttu-id="83a96-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83a96-121">See Also</span></span>  
 [<span data-ttu-id="83a96-122">Amministrazione e configurazione del server PowerPivot in Amministrazione centrale</span><span class="sxs-lookup"><span data-stu-id="83a96-122">PowerPivot Server Administration and Configuration in Central Administration</span></span>](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration)  
  
  
