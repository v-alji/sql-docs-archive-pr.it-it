---
title: Rendere sicura un'applicazione Web Gestione dati master | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: e360ba3a-e96b-4f85-b588-ed1f767fa973
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8f2ee807c2cd474542f701226d08427ade8279e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722895"
---
# <a name="secure-a-master-data-manager-web-application"></a><span data-ttu-id="bae69-102">Rendere sicura un'applicazione Web Gestione dati master</span><span class="sxs-lookup"><span data-stu-id="bae69-102">Secure a Master Data Manager Web Application</span></span>
  <span data-ttu-id="bae69-103">È possibile rendere sicura l'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] con HTTPS.</span><span class="sxs-lookup"><span data-stu-id="bae69-103">You can secure the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application with HTTPS.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bae69-104">L'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] consente di utilizzare HTTP o HTTPS, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="bae69-104">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application can use either HTTP or HTTPS, but not both.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bae69-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="bae69-105">Prerequisites</span></span>  
 <span data-ttu-id="bae69-106">Per eseguire la procedura:</span><span class="sxs-lookup"><span data-stu-id="bae69-106">To perform the procedure:</span></span>  
  
-   <span data-ttu-id="bae69-107">È necessario essere un amministratore nel server Web in cui è installato [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bae69-107">You must be an administrator on the web server where [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] is installed.</span></span>  
  
-   <span data-ttu-id="bae69-108">È necessario che MDS sia installato nel server Web e che sia presente un'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="bae69-108">MDS must be installed on the web server, and a web application must exist.</span></span> <span data-ttu-id="bae69-109">Per altre informazioni, vedere [Installazione di Master Data Services](install-master-data-services.md) e [Creare un'applicazione Web Gestione dati master &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bae69-109">For more information, see [Install Master Data Services](install-master-data-services.md) and [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
### <a name="to-secure-the-master-data-manager-web-application-with-https"></a><span data-ttu-id="bae69-110">Per rendere sicura l'applicazione Web Gestione dati master con HTTPS</span><span class="sxs-lookup"><span data-stu-id="bae69-110">To secure the Master Data Manager web application with HTTPS</span></span>  
  
1.  <span data-ttu-id="bae69-111">Dopo avere verificato che l'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] sia configurata correttamente con HTTP, creare un certificato in IIS.</span><span class="sxs-lookup"><span data-stu-id="bae69-111">After you have confirmed that the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application is configured correctly with HTTP, create a certificate in IIS.</span></span> <span data-ttu-id="bae69-112">Per altre informazioni, vedere [Configuring Server Certificates in IIS 7](https://technet.microsoft.com/library/cc732230\(WS.10\).aspx)(Configurazione dei certificati del server in IIS 7).</span><span class="sxs-lookup"><span data-stu-id="bae69-112">For more information, see [Configuring Server Certificates in IIS 7](https://technet.microsoft.com/library/cc732230\(WS.10\).aspx).</span></span>  
  
2.  <span data-ttu-id="bae69-113">Nel riquadro **Connessioni** , in **Siti**, fare clic sul sito che ospita l'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bae69-113">In the **Connections** pane, under **Sites**, click the site that hosts the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
3.  <span data-ttu-id="bae69-114">Nel riquadro **Azioni** fare clic su **Binding**.</span><span class="sxs-lookup"><span data-stu-id="bae69-114">In the **Actions** pane, click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="bae69-115">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bae69-115">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="bae69-116">Nell'elenco selezionare **https**.</span><span class="sxs-lookup"><span data-stu-id="bae69-116">From the list, select **https**.</span></span>  
  
6.  <span data-ttu-id="bae69-117">Selezionare il certificato SSL.</span><span class="sxs-lookup"><span data-stu-id="bae69-117">Select the SSL certificate.</span></span>  
  
7.  <span data-ttu-id="bae69-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bae69-118">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="bae69-119">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bae69-119">Optional.</span></span> <span data-ttu-id="bae69-120">Per rimuovere HTTP in modo che gli utenti possano accedere al sito solo tramite HTTPS, fare clic sulla riga con **http**.</span><span class="sxs-lookup"><span data-stu-id="bae69-120">To remove HTTP so that users can access the site with HTTPS only, from the list, click the row with **http**.</span></span> <span data-ttu-id="bae69-121">Fare clic su **Rimuovi** e nella finestra di dialogo di conferma fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="bae69-121">Click **Remove** and on the confirmation dialog box, click **Yes**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="bae69-122">È necessario modificare le configurazioni di basicHttp e wsHttpBinding dopo la rimozione di HTTP.</span><span class="sxs-lookup"><span data-stu-id="bae69-122">You must change basicHttp and wsHttpBinding configurations after removing HTTP.</span></span>  
  
9. <span data-ttu-id="bae69-123">Fare clic su **Chiudi** per chiudere la finestra di dialogo **Binding sito**.</span><span class="sxs-lookup"><span data-stu-id="bae69-123">To close the **Site Bindings** dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="bae69-124">Aprire ora il file di web.config da *unità*: \Programmi\microsoft SQL Server\120\Master Data Services\WebApplication.</span><span class="sxs-lookup"><span data-stu-id="bae69-124">Now open the web.config file from *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\WebApplication.</span></span>  
  
11. <span data-ttu-id="bae69-125">Individuare la stringa `<security mode="Message">` e impostarla su `<security mode="Transport">`.</span><span class="sxs-lookup"><span data-stu-id="bae69-125">Find the string `<security mode="Message">` and change it to `<security mode="Transport">`.</span></span>  
  
12. <span data-ttu-id="bae69-126">Salvare e chiudere il file.</span><span class="sxs-lookup"><span data-stu-id="bae69-126">Save and close the file.</span></span> <span data-ttu-id="bae69-127">Se si verifica un errore, il Controllo dell'account utente potrebbe essere abilitato.</span><span class="sxs-lookup"><span data-stu-id="bae69-127">If you get an error, it could be because you have UAC enabled.</span></span> <span data-ttu-id="bae69-128">Per altre informazioni, vedere [Turn off User Account Control](https://technet.microsoft.com/library/cc709691\(WS.10\).aspx)(Disattivare il controllo dell'account utente).</span><span class="sxs-lookup"><span data-stu-id="bae69-128">For more information, see [Turn off User Account Control](https://technet.microsoft.com/library/cc709691\(WS.10\).aspx).</span></span> <span data-ttu-id="bae69-129">A questo punto, gli utenti dovrebbero poter utilizzare HTTPS per accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="bae69-129">Users should now be able to use HTTPS to access the site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bae69-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bae69-130">See Also</span></span>  
 [<span data-ttu-id="bae69-131">Creare un'applicazione Web Gestione dati master &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bae69-131">Create a Master Data Manager Web Application &#40;Master Data Services&#41;</span></span>](create-a-master-data-manager-web-application-master-data-services.md)  
  
  
