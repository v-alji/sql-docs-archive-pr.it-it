---
title: Creare le classi proxy del servizio Web Gestione dati master | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 8bdab026-a0c0-41f3-9d36-f3919c23247f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c4f25d749f829357f6541f14073e654bade27215
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638434"
---
# <a name="create-master-data-manager-web-service-proxy-classes"></a><span data-ttu-id="717b8-102">Creare le classi proxy del servizio Web Gestione dati master</span><span class="sxs-lookup"><span data-stu-id="717b8-102">Create Master Data Manager Web Service Proxy Classes</span></span>
  <span data-ttu-id="717b8-103">Il servizio Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] consente di utilizzare a livello di codice le caratteristiche di [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] da qualsiasi computer che può accedere al sito Web di [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="717b8-103">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web service lets you make programmatic use of the features of [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] from any computer that can access your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web site.</span></span> <span data-ttu-id="717b8-104">Prima di iniziare a scrivere il codice per accedere al servizio Web, è necessario generare le classi proxy.</span><span class="sxs-lookup"><span data-stu-id="717b8-104">Before you can start writing code to access the web service, you must generate proxy classes.</span></span> <span data-ttu-id="717b8-105">La classe proxy principale utilizzata per eseguire le operazioni del servizio Web è la classe <xref:Microsoft.MasterDataServices.ServiceClient>, che implementa l'interfaccia <xref:Microsoft.MasterDataServices.IService>.</span><span class="sxs-lookup"><span data-stu-id="717b8-105">The main proxy class you use to perform web service operations is the <xref:Microsoft.MasterDataServices.ServiceClient> class, which implements the <xref:Microsoft.MasterDataServices.IService> interface.</span></span>  
  
## <a name="enable-web-service-metadata-publishing"></a><span data-ttu-id="717b8-106">Abilitare la pubblicazione dei metadati del servizio Web</span><span class="sxs-lookup"><span data-stu-id="717b8-106">Enable Web Service Metadata Publishing</span></span>  
 <span data-ttu-id="717b8-107">Prima di generare le classi proxy, è necessario abilitare la pubblicazione dei metadati del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="717b8-107">Before you can generate proxy classes, you must enable web service metadata publishing.</span></span> <span data-ttu-id="717b8-108">A tale scopo, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="717b8-108">Follow these steps to do this:</span></span>  
  
1.  <span data-ttu-id="717b8-109">Aprire il file Web.config di [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="717b8-109">Open the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] Web.config file in a text editor.</span></span> <span data-ttu-id="717b8-110">Il file Web.config si trova nella cartella WebApplication del percorso di installazione di [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="717b8-110">This file is in the WebApplication folder of the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] installation path.</span></span>  
  
2.  <span data-ttu-id="717b8-111">Trovare la `mdsWsHttpBehavior` sezione in **\<serviceBehaviors>** .</span><span class="sxs-lookup"><span data-stu-id="717b8-111">Find the `mdsWsHttpBehavior` section under **\<serviceBehaviors>**.</span></span> <span data-ttu-id="717b8-112">Per l' **\<serviceMetadata>** elemento, impostare `httpGetEnabled` su `true` .</span><span class="sxs-lookup"><span data-stu-id="717b8-112">For the **\<serviceMetadata>** element, set `httpGetEnabled` to `true`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="717b8-113">Se si desidera abilitare servizi Web tramite Secure Sockets Layer (SSL), impostare invece `httpsGetEnabled` su `true` nella sezione `mdsWsHttpBehavior` del file web.config.</span><span class="sxs-lookup"><span data-stu-id="717b8-113">If you want to enable Web services over Secure Sockets Layer (SSL), set `httpsGetEnabled` to `true` in the `mdsWsHttpBehavior` section of the web.config file.</span></span> <span data-ttu-id="717b8-114">È inoltre necessario modificare `mdsWsHTTPBinding` in modo tale che sia configurato per SSL e impostare come commento la sezione non SSL.</span><span class="sxs-lookup"><span data-stu-id="717b8-114">You also need to change `mdsWsHTTPBinding` so that it is configured for SSL, as well, and comment out the non-SSL section.</span></span>  
  
3.  <span data-ttu-id="717b8-115">Salvare le modifiche apportate al file.</span><span class="sxs-lookup"><span data-stu-id="717b8-115">Save changes to the file.</span></span>  
  
4.  <span data-ttu-id="717b8-116">Testare la pubblicazione dei metadati passando all'URL del servizio, ad esempio: http://yourserver/MDS/service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="717b8-116">Test metadata publishing by browsing to the service URL, for example: http://yourserver/MDS/service/service.svc.</span></span> <span data-ttu-id="717b8-117">Se la pubblicazione dei metadati è abilitata, viene visualizzata una pagina che inizia con</span><span class="sxs-lookup"><span data-stu-id="717b8-117">If metadata publishing is enabled, a page is displayed that begins with</span></span>   
    <span data-ttu-id="717b8-118">"È stato creato un servizio".</span><span class="sxs-lookup"><span data-stu-id="717b8-118">"You have created a service."</span></span>  
  
## <a name="creating-proxy-classes-by-using-visual-studio"></a><span data-ttu-id="717b8-119">Creazione di classi proxy tramite Visual Studio</span><span class="sxs-lookup"><span data-stu-id="717b8-119">Creating Proxy Classes by Using Visual Studio</span></span>  
 <span data-ttu-id="717b8-120">Se è installato Visual Studio 2010, il modo più semplice per generare le classi proxy è aggiungere un **Riferimento al servizio** al progetto.</span><span class="sxs-lookup"><span data-stu-id="717b8-120">If you have Visual Studio 2010 installed, the simplest way to generate proxy classes is to add a **Service Reference** to your project.</span></span> <span data-ttu-id="717b8-121">L'indirizzo del riferimento al servizio è l'URL dell'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] aggiunto a /service/service.svc,</span><span class="sxs-lookup"><span data-stu-id="717b8-121">The address of the service reference is the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, appended with /service/service.svc.</span></span> <span data-ttu-id="717b8-122">Ad esempio: http://yourserver/MDS/service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="717b8-122">For example: http://yourserver/MDS/service/service.svc.</span></span> <span data-ttu-id="717b8-123">Per altre informazioni, vedere [Procedura: Aggiungere, aggiornare o rimuovere un riferimento al servizio](https://go.microsoft.com/fwlink/?LinkId=221167).</span><span class="sxs-lookup"><span data-stu-id="717b8-123">For more information, see [How to: Add, Update, or Remove a Service Reference](https://go.microsoft.com/fwlink/?LinkId=221167).</span></span>  
  
## <a name="creating-proxy-classes-by-using-svcutilexe"></a><span data-ttu-id="717b8-124">Creazione di classi proxy tramite Svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="717b8-124">Creating Proxy Classes by Using Svcutil.exe</span></span>  
 <span data-ttu-id="717b8-125">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)] Per avere Svcutil.exe nel computer in uso, è necessario che sia installato il Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="717b8-125">You must have either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows SDK installed in order to have Svcutil.exe on your computer.</span></span> <span data-ttu-id="717b8-126">Se si utilizza [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], per eseguire il comando sarà necessario utilizzare il prompt dei comandi di [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="717b8-126">If you use [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], you must use the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] command prompt to run the command.</span></span> <span data-ttu-id="717b8-127">Per altre informazioni, vedere [Strumento ServiceModel Metadata Utility (Svcutil.exe)](https://go.microsoft.com/fwlink/?LinkId=165027) e [Generazione di un client WCF dai metadati del servizio](https://go.microsoft.com/fwlink/?LinkId=164821).</span><span class="sxs-lookup"><span data-stu-id="717b8-127">For more information, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://go.microsoft.com/fwlink/?LinkId=165027) and [Generating a WCF Client from Service Metadata](https://go.microsoft.com/fwlink/?LinkId=164821).</span></span>  
  
 <span data-ttu-id="717b8-128">Per creare un set di classi proxy in C# tramite Svcutil.exe, utilizzare un comando analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="717b8-128">To create a set of C# proxy classes by using Svcutil.exe, use a command such as the following:</span></span>  
  
```  
svcutil.exe http://<server_name:port>/<virtual_path>/Service/Service.svc   
/out:<proxy_name>.cs /messageContract /tcv:Version35   
/noconfig /ct:System.Collections.ObjectModel.Collection`1   
/namespace:*,Microsoft.MasterDataServices  
```  
  
 <span data-ttu-id="717b8-129">Dove:</span><span class="sxs-lookup"><span data-stu-id="717b8-129">Where:</span></span>  
  
-   <span data-ttu-id="717b8-130">*servername*:*port* corrispondono al nome del computer e al numero della porta del computer host di [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="717b8-130">*servername*:*port* are the computer name and port number of the computer that hosts [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="717b8-131">*virtual_path* è il percorso virtuale di [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] in Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="717b8-131">*virtual_path* is the virtual path of [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] in Internet Information Services (IIS).</span></span>  
  
-   <span data-ttu-id="717b8-132">*proxy_name* è il nome del file proxy generato.</span><span class="sxs-lookup"><span data-stu-id="717b8-132">*proxy_name* is the name for the generated proxy file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="717b8-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="717b8-133">See Also</span></span>  
 [<span data-ttu-id="717b8-134">Operazioni del servizio Web per categoria &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="717b8-134">Categorized Web Service Operations &#40;Master Data Services&#41;</span></span>](categorized-web-service-operations-master-data-services.md)  
  
  
