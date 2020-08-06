---
title: Creare un database Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 8373bb35-f0f9-4c3c-a53c-dfaa2ce567ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9ee90ac5d02489da3b411b12389e949ff3136287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625424"
---
# <a name="create-a-master-data-services-database"></a><span data-ttu-id="6f06f-102">Creare un database Master Data Services</span><span class="sxs-lookup"><span data-stu-id="6f06f-102">Create a Master Data Services Database</span></span>
  <span data-ttu-id="6f06f-103">Creare un database [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] quando è necessario un nuovo database per supportare l'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] e il servizio Web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6f06f-103">Create a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database when you need a new database to support the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application and [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6f06f-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6f06f-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="6f06f-105">Per informazioni sui requisiti del computer che ospita il database, vedere [Requisiti del database &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6f06f-105">For information about the requirements for the computer that hosts the database, see [Database Requirements &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span></span>  
  
### <a name="to-create-a-master-data-services-database"></a><span data-ttu-id="6f06f-106">Per creare un database Master Data Services</span><span class="sxs-lookup"><span data-stu-id="6f06f-106">To create a Master Data Services database</span></span>  
  
1.  <span data-ttu-id="6f06f-107">Aprire [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f06f-107">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="6f06f-108">Nel riquadro sinistro fare clic su **Configurazione database**.</span><span class="sxs-lookup"><span data-stu-id="6f06f-108">In the left pane, click **Database Configuration**.</span></span>  
  
3.  <span data-ttu-id="6f06f-109">Nella pagina **Configurazione database** fare clic su **Crea database**.</span><span class="sxs-lookup"><span data-stu-id="6f06f-109">On the **Database Configuration** page, click **Create Database**.</span></span>  
  
4.  <span data-ttu-id="6f06f-110">Completare la procedura guidata **Crea database** per creare e configurare il database.</span><span class="sxs-lookup"><span data-stu-id="6f06f-110">Complete the **Create Database** wizard to create and configure the database.</span></span> <span data-ttu-id="6f06f-111">Per altre informazioni sulle opzioni dell'interfaccia utente nella procedura guidata, vedere [Procedura guidata Crea database &#40;Gestione configurazione Master Data Services&#41;](../create-database-wizard-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6f06f-111">For information about the user interface (UI) options in the wizard, see [Create Database Wizard &#40;Master Data Services Configuration Manager&#41;](../create-database-wizard-master-data-services-configuration-manager.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6f06f-112">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6f06f-112">Next Steps</span></span>  
  
-   <span data-ttu-id="6f06f-113">Configurare le impostazioni di sistema per il database e l'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="6f06f-113">Configure system settings for the database and web application.</span></span> <span data-ttu-id="6f06f-114">Per altre informazioni, vedere [Impostazioni di sistema &#40;Master Data Services&#41;](../system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6f06f-114">For more information, see [System Settings &#40;Master Data Services&#41;](../system-settings-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="6f06f-115">Creare un'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] da associare al database.</span><span class="sxs-lookup"><span data-stu-id="6f06f-115">Create a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application to associate with this database.</span></span> <span data-ttu-id="6f06f-116">Per altre informazioni, vedere [Creare un'applicazione Web Gestione dati master &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6f06f-116">For more information, see [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="6f06f-117">Configurare un piano di manutenzione per il backup del database e dei log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="6f06f-117">Configure a maintenance plan to back up the database and transaction logs.</span></span> <span data-ttu-id="6f06f-118">Per altre informazioni, vedere [Requisiti del database &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6f06f-118">For more information, see [Database Requirements &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f06f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f06f-119">See Also</span></span>  
 [<span data-ttu-id="6f06f-120">Installazione di Master Data Services</span><span class="sxs-lookup"><span data-stu-id="6f06f-120">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
