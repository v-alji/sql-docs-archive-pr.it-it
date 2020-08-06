---
title: Configurare il database e il sito Web per Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
f1_keywords:
- sql12.mds.configmanager.general.f1
ms.assetid: d50863e7-50d9-4ab8-aabb-fd68e2d132a1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: da797bc6f9838a2baab6cc440cc7d778a7a6e186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637960"
---
# <a name="set-up-the-database-and-website-for-master-data-services"></a><span data-ttu-id="016fa-102">Configurare il database e il sito Web per Master Data Services</span><span class="sxs-lookup"><span data-stu-id="016fa-102">Set up the Database and Website for Master Data Services</span></span>
  <span data-ttu-id="016fa-103">Usare [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] per configurare il database e il sito Web per [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS)</span><span class="sxs-lookup"><span data-stu-id="016fa-103">Use the [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to set up the database and website for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS)</span></span>  
  
 <span data-ttu-id="016fa-104">Per configurare il database e il sito Web, completare le attività seguenti.</span><span class="sxs-lookup"><span data-stu-id="016fa-104">To set up the database and website, complete the following tasks.</span></span>  
  
1.  <span data-ttu-id="016fa-105">Creare un database utilizzando la pagina **Configurazione database** in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="016fa-105">Create a database using the **Database Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span>  
  
     <span data-ttu-id="016fa-106">Per informazioni, vedere [pagina Configurazione database &#40;Gestione configurazione Master Data Services&#41;](../../2014/master-data-services/database-configuration-page-master-data-services-configuration-manager.md) e [creazione guidata database &#40;Gestione configurazione Master Data Services&#41;](../../2014/master-data-services/create-database-wizard-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="016fa-106">For information, see [Database Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/database-configuration-page-master-data-services-configuration-manager.md) and [Create Database Wizard &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-database-wizard-master-data-services-configuration-manager.md).</span></span>  
  
2.  <span data-ttu-id="016fa-107">Creare un nuovo sito Web, selezionare il sito Web predefinito o selezionare un altro sito Web esistente usando la pagina **configurazione Web** in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="016fa-107">Create a new website, select the default website, or select another existing website, using the **Web Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="016fa-108">Associare quindi il database MDS all'applicazione Web selezionata o creata.</span><span class="sxs-lookup"><span data-stu-id="016fa-108">Then associate the MDS database with the web application you select or create.</span></span>  
  
     <span data-ttu-id="016fa-109">Per informazioni, vedere la [pagina configurazione Web &#40;Gestione configurazione Master Data Services&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) e la finestra di [dialogo crea sito Web &#40;Gestione configurazione Master Data Services ](../../2014/master-data-services/create-website-dialog-box-master-data-services-configuration-manager.md)&#41;.</span><span class="sxs-lookup"><span data-stu-id="016fa-109">For information, see [Web Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) and [Create Website Dialog Box &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-website-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
3.  <span data-ttu-id="016fa-110">Opzionale Abilitare l'integrazione con Data Quality Services tramite la pagina **configurazione Web** in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="016fa-110">(Optional) Enable integration with Data Quality Services using the **Web Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span>  
  
     <span data-ttu-id="016fa-111">Per ulteriori informazioni, vedere la [pagina configurazione Web &#40;Gestione configurazione Master Data Services&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) e [abilitare l'integrazione di Data Quality Services con Master Data Services](install-windows/enable-data-quality-services-integration-with-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="016fa-111">For more information, see [Web Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) and [Enable Data Quality Services Integration with Master Data Services](install-windows/enable-data-quality-services-integration-with-master-data-services.md).</span></span>  
  
 <span data-ttu-id="016fa-112">È anche possibile usare [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] per specificare le impostazioni per servizi e applicazioni Web associate al database MDS.</span><span class="sxs-lookup"><span data-stu-id="016fa-112">You can also use [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to specify settings for the web applications and services associated with the MDS database.</span></span> <span data-ttu-id="016fa-113">Ad esempio, è possibile specificare la frequenza con cui i dati vengono caricati o quella con cui viene inviata la posta elettronica della convalida.</span><span class="sxs-lookup"><span data-stu-id="016fa-113">For example, you can specify how frequently data is loaded or how often validation emails are sent.</span></span> <span data-ttu-id="016fa-114">Per altre informazioni, vedere [Impostazioni di sistema &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="016fa-114">For more information, see [System Settings &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="016fa-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="016fa-115">See Also</span></span>  
 <span data-ttu-id="016fa-116">[Database Master Data Services](../../2014/master-data-services/master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="016fa-116">[Master Data Services Database](../../2014/master-data-services/master-data-services-database.md) </span></span>  
 [<span data-ttu-id="016fa-117">Applicazione Web Gestione dati master</span><span class="sxs-lookup"><span data-stu-id="016fa-117">Master Data Manager Web Application</span></span>](../../2014/master-data-services/master-data-manager-web-application.md)  
  
  
