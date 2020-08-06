---
title: Associare un'applicazione Web e un database Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: ccb25672-f71d-4135-b548-f50eb45d8fa5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 01afde6aea5065a51cb9e7ae5dc4151e9f1e9fc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713231"
---
# <a name="associate-a-master-data-services-database-and-web-application"></a><span data-ttu-id="60a5a-102">Associare un'applicazione Web e un database Master Data Services</span><span class="sxs-lookup"><span data-stu-id="60a5a-102">Associate a Master Data Services Database and Web Application</span></span>
  <span data-ttu-id="60a5a-103">Associare l'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] a un database [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] per specificare il database da usare per le operazioni Web.</span><span class="sxs-lookup"><span data-stu-id="60a5a-103">Associate your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application with a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database to specify the database to use for web operations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="60a5a-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="60a5a-104">Prerequisites</span></span>  
  
-   [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] <span data-ttu-id="60a5a-105">deve essere installato nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="60a5a-105">must be installed on the local computer.</span></span> <span data-ttu-id="60a5a-106">Per altre informazioni, vedere [Install Master Data Services](install-master-data-services.md)(Installare Master Data Services).</span><span class="sxs-lookup"><span data-stu-id="60a5a-106">For more information, see [Install Master Data Services](install-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="60a5a-107">È necessario che sia disponibile un'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] locale.</span><span class="sxs-lookup"><span data-stu-id="60a5a-107">A local [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application must exist.</span></span> <span data-ttu-id="60a5a-108">Per altre informazioni, vedere [Creare un'applicazione Web Gestione dati master &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="60a5a-108">For more information, see [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="60a5a-109">È necessario che sia disponibile un database [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] locale o remoto.</span><span class="sxs-lookup"><span data-stu-id="60a5a-109">Either a local or remote [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database must exist.</span></span> <span data-ttu-id="60a5a-110">Per altre informazioni, vedere [Creare un database Master Data Services](create-a-master-data-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="60a5a-110">For more information, see [Create a Master Data Services Database](create-a-master-data-services-database.md).</span></span>  
  
### <a name="to-associate-a-master-data-services-database-and-web-application"></a><span data-ttu-id="60a5a-111">Per associare un'applicazione Web e un database Master Data Services</span><span class="sxs-lookup"><span data-stu-id="60a5a-111">To associate a Master Data Services database and web application</span></span>  
  
1.  <span data-ttu-id="60a5a-112">Aprire [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60a5a-112">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="60a5a-113">Nel riquadro sinistro fare clic su **Configurazione Web**.</span><span class="sxs-lookup"><span data-stu-id="60a5a-113">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="60a5a-114">Nell'elenco **Sito Web** della pagina **Configurazione Web**, in **Applicazione Web** selezionare il sito Web in cui è inclusa l'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60a5a-114">On the **Web Configuration** page, under **Web application**, from the **Website** list, select the website that contains your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
4.  <span data-ttu-id="60a5a-115">Nella casella **Applicazione Web** selezionare l'applicazione Web in cui è ospitato [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60a5a-115">In the **Web application** box, select the web application that hosts [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>  
  
5.  <span data-ttu-id="60a5a-116">In **Associare l'applicazione al database**fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="60a5a-116">Under **Associate Application with Database**, click **Select**.</span></span> <span data-ttu-id="60a5a-117">Verrà visualizzata la finestra di dialogo **Connetti al database** .</span><span class="sxs-lookup"><span data-stu-id="60a5a-117">The **Connect to Database** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="60a5a-118">Specificare le informazioni di connessione per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che ospita il database [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] e fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="60a5a-118">Specify connection information for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database, and click **Connect**.</span></span>  
  
7.  <span data-ttu-id="60a5a-119">Nell'elenco **Database Master Data Services** selezionare il database che si desidera associare all'applicazione Web, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="60a5a-119">From the **Master Data Services database** list, select the database you want to associate the web application with and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="60a5a-120">In **Associare l'applicazione al database**verificare che l'istanza e le informazioni del database siano corrette, quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="60a5a-120">Under **Associate Application with Database**, verify that the instance and database information are correct, and then click **Apply**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="60a5a-121">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="60a5a-121">Next Steps</span></span>  
  
-   <span data-ttu-id="60a5a-122">L'accesso a livello di programmazione ai servizi Web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] , viene abilitato automaticamente durante la creazione dell'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="60a5a-122">Programmatic access to [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web services is automatically enabled when the web application is created.</span></span> <span data-ttu-id="60a5a-123">Per consentire agli sviluppatori di accedere ai metadati del servizio al fine di generare in modo semplice classi proxy per l'accesso a livello di codice, abilitare la pubblicazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="60a5a-123">To let developers access the service metadata to easily generate proxy classes for programmatic access, enable metadata publishing.</span></span> <span data-ttu-id="60a5a-124">Per altre informazioni, vedere [Creare le classi proxy del servizio Web Gestione dati master](../develop/create-master-data-manager-web-service-proxy-classes.md).</span><span class="sxs-lookup"><span data-stu-id="60a5a-124">For more information, see [Create Master Data Manager Web Service Proxy Classes](../develop/create-master-data-manager-web-service-proxy-classes.md).</span></span>  
  
-   <span data-ttu-id="60a5a-125">Aggiungere utenti e gruppi a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60a5a-125">Add users and groups to [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="60a5a-126">Se a nessun utente o gruppo è stato concesso l'accesso a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], è necessario aprire [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] utilizzando le credenziali di amministratore del sistema [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60a5a-126">If no users or groups have been granted access to [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], you must open [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] using the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] system administrator credentials.</span></span> <span data-ttu-id="60a5a-127">Per altre informazioni, vedere [Amministratori &#40;Master Data Services&#41;](../administrators-master-data-services.md) e [Utenti e gruppi &#40;Master Data Services&#41;](../users-and-groups-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="60a5a-127">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md) and [Users and Groups &#40;Master Data Services&#41;](../users-and-groups-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60a5a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60a5a-128">See Also</span></span>  
 <span data-ttu-id="60a5a-129">[Installa Master Data Services](install-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="60a5a-129">[Install Master Data Services](install-master-data-services.md) </span></span>  
 [<span data-ttu-id="60a5a-130">Pagina Configurazione Web &#40;Gestione configurazione Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="60a5a-130">Web Configuration Page &#40;Master Data Services Configuration Manager&#41;</span></span>](../web-configuration-page-master-data-services-configuration-manager.md)  
  
  
