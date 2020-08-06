---
title: Attivare il server di report e Power View le funzionalità di integrazione in SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c7f64a54-c555-4d31-bf99-3abe57dc8626
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af5f544e959c039b0bdb85d63d0b94917254d78a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636594"
---
# <a name="activate-the-report-server-and-power-view-integration-features-in-sharepoint"></a><span data-ttu-id="a24fa-102">Attivare le funzionalità di integrazione per Power View e server di report in SharePoint</span><span class="sxs-lookup"><span data-stu-id="a24fa-102">Activate the Report Server and Power View Integration Features in SharePoint</span></span>
  <span data-ttu-id="a24fa-103">Le [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] funzionalità della raccolta siti vengono in genere attivate per impostazione predefinita dopo l'installazione del [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] componente aggiuntivo per prodotti SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a24fa-103">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] site collection features are usually activated by default after you install the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] Add-in for SharePoint products.</span></span> <span data-ttu-id="a24fa-104">In alcune situazioni sarà necessario attivare manualmente le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a24fa-104">In some situations you will need to manually activate the features.</span></span>  
  
 <span data-ttu-id="a24fa-105">Se si installa il componente aggiuntivo di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] per Prodotti SharePoint 2010 dopo l'installazione del prodotto SharePoint, la funzionalità di integrazione del server di report e la funzionalità di integrazione di Power View saranno attivate solo per le raccolte siti radice.</span><span class="sxs-lookup"><span data-stu-id="a24fa-105">If you install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint 2010 Products after the installation of the SharePoint product, then the Report Server integration feature and the Power View integration feature will only be activated for root site collections.</span></span> <span data-ttu-id="a24fa-106">Per le altre raccolte siti, sarà necessario attivare manualmente le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a24fa-106">For other site collections, you will need to manually activate the features.</span></span> <span data-ttu-id="a24fa-107">Ad esempio, se è presente una raccolta siti **http://[nome server]/sites/[nome raccolta siti]** , sarà necessario attivare manualmente le funzionalità delle raccolte siti di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a24fa-107">For example if you have a site collection of **http://[my server name]/sites/[site collection name]** you will need to manually activate the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] site collection features.</span></span>  
  
 <span data-ttu-id="a24fa-108">Se non è presente alcuna raccolta siti radice, il componente aggiuntivo [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] registra un messaggio simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="a24fa-108">When there is no root site collection, the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in will log a message similar to the following.</span></span>  
  
 <span data-ttu-id="a24fa-109">"L'applicazione Web SharePoint 80 non dispone della raccolta siti radice"</span><span class="sxs-lookup"><span data-stu-id="a24fa-109">"SharePoint web app 80 does not have root site collection"</span></span>  
  
 <span data-ttu-id="a24fa-110">Il messaggio verrà trovato nel log di installazione del componente aggiuntivo, denominato "RS_SP_ #. log" dove # è un numero incrementale.</span><span class="sxs-lookup"><span data-stu-id="a24fa-110">The message will be found in the add-in installation log, named "RS_SP_#.log" where # is an incrementing number.</span></span> <span data-ttu-id="a24fa-111">Il file di log verrà trovato nella cartella temporanea utenti correnti, ad esempio C:\Users \\ [nome utente] \AppData\Local\Temp. Per ulteriori informazioni sulle opzioni di registrazione con il componente aggiuntivo, vedere [installare o disinstallare il componente aggiuntivo Reporting Services per sharepoint &#40;sharepoint 2010 e sharepoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="a24fa-111">The log file will be found in the current users Temp folder, for example C:\Users\\[user name]\AppData\Local\Temp. For more information on logging options with the add-in, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span>  
  
 <span data-ttu-id="a24fa-112">In questo argomento</span><span class="sxs-lookup"><span data-stu-id="a24fa-112">In this topic:</span></span>  
  
-   [<span data-ttu-id="a24fa-113">Per attivare le funzionalità di raccolta siti di integrazione per Power View e server di report</span><span class="sxs-lookup"><span data-stu-id="a24fa-113">To Activate the Report Server and Power View Integration Site Collection Features:</span></span>](#bkmk_features)  
  
-   [<span data-ttu-id="a24fa-114">Per attivare o disattivare la funzionalità Raccolta siti di amministrazione centrale di Reporting Services:</span><span class="sxs-lookup"><span data-stu-id="a24fa-114">To Activate or Deactivate Reporting Services Central Administration Site Collection Feature:</span></span>](#bkmk_centraladmin)  
  
##  <a name="to-activate-the-report-server-and-power-view-integration-site-collection-features"></a><a name="bkmk_features"></a><span data-ttu-id="a24fa-115">Per attivare il server di report e le funzionalità di raccolta siti di integrazione Power View:</span><span class="sxs-lookup"><span data-stu-id="a24fa-115">To Activate the Report Server and Power View Integration Site Collection Features:</span></span>  
  
1.  <span data-ttu-id="a24fa-116">Aprire il browser al sito dove si desidera che le funzionalità [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] siano attive.</span><span class="sxs-lookup"><span data-stu-id="a24fa-116">Open your browser to the site where you want the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features active.</span></span>  
  
2.  <span data-ttu-id="a24fa-117">Fare clic su **Azioni sito**.</span><span class="sxs-lookup"><span data-stu-id="a24fa-117">Click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="a24fa-118">Fare clic su **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="a24fa-118">Click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="a24fa-119">Fare clic su **Funzionalità raccolta siti** nel gruppo Amministrazione raccolta siti</span><span class="sxs-lookup"><span data-stu-id="a24fa-119">Click **Site Collection Features** in the Site Collection Administration Group.</span></span>  
  
5.  <span data-ttu-id="a24fa-120">Individuare **Funzionalità di integrazione Server report** o **Funzionalità di integrazione Power View** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a24fa-120">Find **Report Server Integration Feature** or **Power View Integration Feature** in the list.</span></span>  
  
6.  <span data-ttu-id="a24fa-121">Fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="a24fa-121">Click **Activate**.</span></span>  
  
 <span data-ttu-id="a24fa-122">Per disattivare le funzionalità, è possibile utilizzare la stessa procedura facendo clic su **Disattiva** anziché su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="a24fa-122">To deactivate the features, you can use the same procedure, but click **Deactivate** rather than **Activate.**</span></span>  
  
##  <a name="to-activate-or-deactivate-reporting-services-central-administration-site-collection-feature"></a><a name="bkmk_centraladmin"></a><span data-ttu-id="a24fa-123">Per attivare o disattivare Reporting Services funzionalità raccolta siti di amministrazione centrale:</span><span class="sxs-lookup"><span data-stu-id="a24fa-123">To Activate or Deactivate Reporting Services Central Administration Site Collection Feature:</span></span>  
  
1.  <span data-ttu-id="a24fa-124">Aprire il browser alla pagina Amministrazione centrale SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a24fa-124">Open your browser to SharePoint Central Administration.</span></span>  
  
2.  <span data-ttu-id="a24fa-125">Fare clic su **Azioni sito**.</span><span class="sxs-lookup"><span data-stu-id="a24fa-125">Click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="a24fa-126">Fare clic su **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="a24fa-126">Click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="a24fa-127">Fare clic su **Funzionalità raccolta siti** nel gruppo Amministrazione raccolta siti</span><span class="sxs-lookup"><span data-stu-id="a24fa-127">Click **Site Collection Features** in the Site Collection Administration Group.</span></span>  
  
5.  <span data-ttu-id="a24fa-128">Individuare **Funzionalità Amministrazione centrale del server di report** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a24fa-128">Find **Report Server Central Administration Feature** in the list.</span></span>  
  
6.  <span data-ttu-id="a24fa-129">Fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="a24fa-129">Click **Activate**.</span></span>  
  
 <span data-ttu-id="a24fa-130">Per disattivare la funzionalità, è possibile utilizzare la stessa procedura facendo tuttavia clic su **Disattiva** anziché su **Attiva.**</span><span class="sxs-lookup"><span data-stu-id="a24fa-130">To deactivate the feature, you can use the same procedure, but click **Deactivate** rather than **Activate.**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a24fa-131">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a24fa-131">Next Steps</span></span>  
 <span data-ttu-id="a24fa-132">Dopo aver attivato la funzionalità, è possibile continuare con l'integrazione del server.</span><span class="sxs-lookup"><span data-stu-id="a24fa-132">After the feature is activated, you can continue with server integration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24fa-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a24fa-133">See Also</span></span>  
 [<span data-ttu-id="a24fa-134">Installare o disinstallare il componente aggiuntivo Reporting Services per SharePoint &#40;SharePoint 2010 e SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="a24fa-134">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
