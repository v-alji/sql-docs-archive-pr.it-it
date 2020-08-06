---
title: Creare un'applicazione Web Gestione dati master (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 241d46d7-8008-47f6-bebd-0dfff1cc856a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fd81188b499850397aa8ffd2e40cfcb91c648288
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625425"
---
# <a name="create-a-master-data-manager-web-application-master-data-services"></a><span data-ttu-id="6e62b-102">Creare un'applicazione Web Gestione dati master (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6e62b-102">Create a Master Data Manager Web Application (Master Data Services)</span></span>
  <span data-ttu-id="6e62b-103">L'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] offre un'interfaccia per gli utenti, affinché possano usare i dati master, e per gli amministratori, perché possano configurare e amministrare MDS.</span><span class="sxs-lookup"><span data-stu-id="6e62b-103">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application provides an interface for users to work with master data and for administrators to configure and administer MDS.</span></span>  
  
 <span data-ttu-id="6e62b-104">Un'applicazione Web deve essere contenuta sempre da un sito web.</span><span class="sxs-lookup"><span data-stu-id="6e62b-104">A web application must always be contained by a website.</span></span> <span data-ttu-id="6e62b-105">Per creare un'applicazione Web, è necessario effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e62b-105">To create a web application, you must either:</span></span>  
  
-   <span data-ttu-id="6e62b-106">Utilizzare il sito Web predefinito e quindi creare l'applicazione Web,</span><span class="sxs-lookup"><span data-stu-id="6e62b-106">Use the Default website and then create the web application,</span></span>  
  
-   <span data-ttu-id="6e62b-107">Utilizzare il sito Web esistente e quindi creare l'applicazione Web oppure</span><span class="sxs-lookup"><span data-stu-id="6e62b-107">Use an existing website and then create the web application, or</span></span>  
  
-   <span data-ttu-id="6e62b-108">Creare un nuovo sito Web mediante il quale viene creata automaticamente un'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="6e62b-108">Create a new website, which automatically creates a web application.</span></span>  
  
 <span data-ttu-id="6e62b-109">Dopo aver creato l'applicazione Web, associarla al database [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e62b-109">After you create the web application, you associate it with the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6e62b-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6e62b-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="6e62b-111">Per informazioni sui requisiti del computer in cui è ospitata l'applicazione Web, vedere [Requisiti dell'applicazione Web &#40;Master Data Services&#41;](web-application-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6e62b-111">For information about the requirements for the computer that hosts the web application, see [Web Application Requirements &#40;Master Data Services&#41;](web-application-requirements-master-data-services.md).</span></span>  
  
## <a name="to-create-a-master-data-manager-web-application-in-a-new-website"></a><span data-ttu-id="6e62b-112">Per creare un'applicazione Web Gestione dati master in un nuovo sito Web</span><span class="sxs-lookup"><span data-stu-id="6e62b-112">To create a Master Data Manager web application in a new website</span></span>  
 <span data-ttu-id="6e62b-113">Quando si crea un nuovo sito Web, l'applicazione Web radice è l'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e62b-113">When you create a new website, the root web application is the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="6e62b-114">Inoltre, l'applicazione Web viene aggiunta a un nuovo pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6e62b-114">The web application is also added to a new application pool.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e62b-115">Se si segue questa procedura, non è possibile specificare un percorso virtuale e un alias dell'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e62b-115">If you follow this procedure, you cannot specify a virtual path and alias of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="6e62b-116">Se si vuole specificare un percorso virtuale e un alias per [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], è necessario creare un'applicazione Web in un sito Web esistente che non sia già configurato come applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e62b-116">If you want to specify a virtual path and alias for [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], you must create a web application in an existing website that is not already configured as a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
 <span data-ttu-id="6e62b-117">Inoltre [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] supporta la creazione di siti solo con associazioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="6e62b-117">Additionally, [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] supports creating sites with HTTP bindings only.</span></span> <span data-ttu-id="6e62b-118">Per aggiungere un'associazione HTTPS, creare un nuovo sito e un'applicazione in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] , quindi vedere [Rendere sicura un'applicazione Web Gestione dati master](secure-a-master-data-manager-web-application.md) .</span><span class="sxs-lookup"><span data-stu-id="6e62b-118">To add an HTTPS binding, create a new site and application in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] and then see [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md) for more information.</span></span>  
  
#### <a name="to-create-a-master-data-manager-web-application-in-a-new-website"></a><span data-ttu-id="6e62b-119">Per creare un'applicazione Web Gestione dati master in un nuovo sito Web</span><span class="sxs-lookup"><span data-stu-id="6e62b-119">To create a Master Data Manager web application in a new website</span></span>  
  
1.  <span data-ttu-id="6e62b-120">Aprire [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e62b-120">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="6e62b-121">Nel riquadro sinistro fare clic su **Configurazione Web**.</span><span class="sxs-lookup"><span data-stu-id="6e62b-121">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="6e62b-122">Nell'elenco Sito Web della pagina **Configurazione Web** selezionare **Crea nuovo sito Web**.</span><span class="sxs-lookup"><span data-stu-id="6e62b-122">On the **Web Configuration** page, in the Website list, select **Create new website**.</span></span>  
  
4.  <span data-ttu-id="6e62b-123">Nella finestra di dialogo **Crea sito Web** specificare le informazioni per un nuovo sito Web.</span><span class="sxs-lookup"><span data-stu-id="6e62b-123">On the **Create Website** dialog box, specify information for a new website.</span></span> <span data-ttu-id="6e62b-124">Per altre informazioni sulle opzioni dell'interfaccia utente nella finestra di dialogo, vedere [Finestra di dialogo Crea sito Web &#40;Gestione configurazione Master Data Services&#41;](../create-website-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6e62b-124">For more information about the user interface (UI) options in the dialog box, see [Create Website Dialog Box &#40;Master Data Services Configuration Manager&#41;](../create-website-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
5.  <span data-ttu-id="6e62b-125">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e62b-125">Click **OK**.</span></span>  
  
## <a name="to-create-a-master-data-manager-web-application-in-an-existing-website"></a><span data-ttu-id="6e62b-126">Per creare un'applicazione Gestione dati master in un sito Web esistente</span><span class="sxs-lookup"><span data-stu-id="6e62b-126">To create a Master Data Manager web application in an existing website</span></span>  
 <span data-ttu-id="6e62b-127">Quando si crea un'applicazione Web in un sito Web esistente, è possibile scegliere il percorso virtuale e l'alias dell'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="6e62b-127">When you create a web application in an existing website, you can choose the virtual path and alias of the web application.</span></span> <span data-ttu-id="6e62b-128">L'applicazione Web viene aggiunta a un nuovo pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6e62b-128">The web application is added to a new application pool.</span></span>  
  
#### <a name="to-create-a-master-data-manager-web-application-in-an-existing-website"></a><span data-ttu-id="6e62b-129">Per creare un'applicazione Gestione dati master in un sito Web esistente</span><span class="sxs-lookup"><span data-stu-id="6e62b-129">To create a Master Data Manager web application in an existing website</span></span>  
  
1.  <span data-ttu-id="6e62b-130">Aprire [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e62b-130">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="6e62b-131">Nel riquadro sinistro fare clic su **Configurazione Web**.</span><span class="sxs-lookup"><span data-stu-id="6e62b-131">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="6e62b-132">Nell'elenco **Sito Web** della pagina **Configurazione Web** selezionare il sito Web in cui si vuole creare l'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e62b-132">On the **Web Configuration** page, from the **Website** list, select the website in which you want to create the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
4.  <span data-ttu-id="6e62b-133">Fare clic su **Crea applicazione**.</span><span class="sxs-lookup"><span data-stu-id="6e62b-133">Click **Create Application**.</span></span>  
  
5.  <span data-ttu-id="6e62b-134">Nella finestra di dialogo **Crea applicazione Web** specificare le informazioni per una nuova applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="6e62b-134">On the **Create Web Application** dialog box, specify information for a new web application.</span></span> <span data-ttu-id="6e62b-135">Per altre informazioni sulle opzioni dell'interfaccia utente nella finestra di dialogo, vedere [Finestra di dialogo Crea applicazione Web &#40;Gestione configurazione Master Data Services&#41;](../create-web-application-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6e62b-135">For more information about the user interface (UI) options in the dialog box, see [Create Web Application Dialog Box &#40;Master Data Services Configuration Manager&#41;](../create-web-application-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
6.  <span data-ttu-id="6e62b-136">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e62b-136">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6e62b-137">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6e62b-137">Next Steps</span></span>  
  
-   <span data-ttu-id="6e62b-138">Associare l'applicazione Web a un database [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e62b-138">Associate the web application with a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="6e62b-139">Per altre informazioni, vedere [Associare un'applicazione Web e un database Master Data Services](associate-a-master-data-services-database-and-web-application.md).</span><span class="sxs-lookup"><span data-stu-id="6e62b-139">For more information, see [Associate a Master Data Services Database and Web Application](associate-a-master-data-services-database-and-web-application.md).</span></span>  
  
-   <span data-ttu-id="6e62b-140">Facoltativamente, configurare il sito Web in cui è ospitata l'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] per usare un'associazione HTTPS se si vuole crittografare il contenuto con Secure Sockets Layer (SSL).</span><span class="sxs-lookup"><span data-stu-id="6e62b-140">Optionally, configure the website that hosts the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application to use an HTTPS binding if you want to encrypt content by using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="6e62b-141">Per configurare il certificato server per il server Web nonché un'associazione HTTPS e le impostazioni SSL per il sito, è necessario utilizzare uno strumento di Internet Information Services (IIS), ad esempio Gestione IIS.</span><span class="sxs-lookup"><span data-stu-id="6e62b-141">You must use an Internet Information Services (IIS) tool, such as IIS Manager, to configure the server certificate for the web server, and to configure an HTTPS binding and the SSL settings for the site.</span></span> <span data-ttu-id="6e62b-142">Per altre informazioni, vedere [Rendere sicura un'applicazione Web Gestione dati master](secure-a-master-data-manager-web-application.md).</span><span class="sxs-lookup"><span data-stu-id="6e62b-142">For more information, see [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e62b-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e62b-143">See Also</span></span>  
 [<span data-ttu-id="6e62b-144">Installazione di Master Data Services</span><span class="sxs-lookup"><span data-stu-id="6e62b-144">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
