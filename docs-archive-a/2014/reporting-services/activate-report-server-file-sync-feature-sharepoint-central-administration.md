---
title: Attivare la funzionalità Sincronizzazione file del server di report in Amministrazione centrale SharePoint | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 03/06/2017
ms.openlocfilehash: 55feac69da85c7287ea56f4b8245350dd7e69565
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630370"
---
# <a name="activate-the-report-server-file-sync-feature-in-sharepoint-central-administration"></a><span data-ttu-id="627d8-102">Attivare la funzionalità Sincronizzazione file server di report in Amministrazione centrale SharePoint</span><span class="sxs-lookup"><span data-stu-id="627d8-102">Activate the Report Server File Sync Feature in SharePoint Central Administration</span></span>

<span data-ttu-id="627d8-103">La funzionalità Sincronizzazione file server di report di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] prevede l'utilizzo di gestori di eventi di SharePoint per sincronizzare il catalogo del server di report con gli elementi nelle raccolte documenti.</span><span class="sxs-lookup"><span data-stu-id="627d8-103">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Server File Sync feature utilizes SharePoint event handlers to synchronize the report server catalog with items in document libraries.</span></span> <span data-ttu-id="627d8-104">Questa funzionalità è utile quando gli utenti caricano di frequente elementi di report pubblicati direttamente nelle raccolte documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="627d8-104">This feature is beneficial when users frequently upload published report items directly to SharePoint document libraries.</span></span> <span data-ttu-id="627d8-105">Se la funzionalità di sincronizzazione file non è attivata, il contenuto verrà comunque sincronizzato ma non con la stessa frequenza.</span><span class="sxs-lookup"><span data-stu-id="627d8-105">If the file Sync feature isn't activated, content will still be synchronized but not as frequently.</span></span>  
  
<span data-ttu-id="627d8-106">La funzionalità di sincronizzazione file può essere attivata in Amministrazione sito di SharePoint dopo aver installato il componente aggiuntivo [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] per prodotti SharePoint.</span><span class="sxs-lookup"><span data-stu-id="627d8-106">The File Sync feature can be activated in SharePoint Site Administration after you install the [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] Add-in for SharePoint products.</span></span>  
  
<span data-ttu-id="627d8-107">Tale caratteristica può essere attivata e disattivata manualmente per il sito ma non a livello di raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="627d8-107">This feature can be manually activated and deactivated per site but not at the site collection level.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="627d8-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="627d8-108">Prerequisites</span></span>  
 <span data-ttu-id="627d8-109">È necessario installare il componente aggiuntivo [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="627d8-109">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Add-in for SharePoint must be installed.</span></span> <span data-ttu-id="627d8-110">Se il componente aggiuntivo non è installato, la funzionalità di sincronizzazione file non sarà visibile nell'elenco delle funzionalità del sito.</span><span class="sxs-lookup"><span data-stu-id="627d8-110">If the add-in isn't installed, the file sync feature won't be visible in the site feature list.</span></span>  
  
 <span data-ttu-id="627d8-111">Per verificare l'installazione, visualizzare l'elenco delle applicazioni installate nel [!INCLUDE[msCoName](../includes/msconame-md.md)] Pannello di controllo **di**Windows.</span><span class="sxs-lookup"><span data-stu-id="627d8-111">To verify installation, view the list of installed applications in [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows **Control Panel**.</span></span> <span data-ttu-id="627d8-112">Se il componente aggiuntivo [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] è installato, seguire le indicazioni fornite in questo argomento per attivare la caratteristica di sincronizzazione file del server di report.</span><span class="sxs-lookup"><span data-stu-id="627d8-112">If the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Add-in is installed, follow the instructions in this topic to activate the report server file sync feature.</span></span>  
  
### <a name="to-activate-or-deactivate-the-reporting-services-file-sync-feature-on-a-site"></a><span data-ttu-id="627d8-113">Per attivare o disattivare la funzionalità di sincronizzazione file di Reporting Services in un sito</span><span class="sxs-lookup"><span data-stu-id="627d8-113">To activate or deactivate the Reporting Services File Sync feature on a Site</span></span>  
  
1.  <span data-ttu-id="627d8-114">Dalla pagina principale del sito, fare clic sul menu **Azioni sito** e fare clic su **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="627d8-114">From the main page of your site, click the **Site Actions** menu and click **Site Settings**.</span></span>  
  
2.  <span data-ttu-id="627d8-115">In **Azioni sito**fare clic su **Gestisci caratteristiche sito**.</span><span class="sxs-lookup"><span data-stu-id="627d8-115">In the **Site Actions**, click **Manage Site Features**.</span></span>  
  
3.  <span data-ttu-id="627d8-116">Trovare **Sincronizzazione file server di report** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="627d8-116">Find **Report Server File Sync** in the list.</span></span>  
  
4.  <span data-ttu-id="627d8-117">Fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="627d8-117">Click **Activate**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="627d8-118"> Per disattivare la funzionalità di sincronizzazione file del server di report, è possibile seguire la stessa procedura facendo però clic su **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="627d8-118">To deactivate the Report Server file sync feature, you can use the same procedure but click **Deactivate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="627d8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="627d8-119">See Also</span></span>  
 <span data-ttu-id="627d8-120">[Risolvere i problemi relativi alle parti del report &#40;Generatore report e SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="627d8-120">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="627d8-121">[Attivare il server di report e Power View le funzionalità di integrazione in SharePoint](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="627d8-121">[Activate the Report Server and Power View Integration Features in SharePoint](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md) </span></span>  
 <span data-ttu-id="627d8-122">[Installare o disinstallare il componente aggiuntivo Reporting Services per SharePoint &#40;SharePoint 2010 e SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="627d8-122">[Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="627d8-123">Installare o disinstallare il componente aggiuntivo Reporting Services per SharePoint &#40;SharePoint 2010 e SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="627d8-123">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
