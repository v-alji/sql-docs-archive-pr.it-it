---
title: Attivare l'integrazione delle funzionalità di PowerPivot per le raccolte siti in Amministrazione centrale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 62a27e53-446a-42d7-b5db-c009e02d4904
author: minewiskan
ms.author: owend
ms.openlocfilehash: b565434cba197d04327e833d4ac6eab3caf96646
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714607"
---
# <a name="activate-powerpivot-feature-integration-for-site-collections-in-central-administration"></a><span data-ttu-id="2ab27-102">Attivare l'integrazione delle funzionalità di PowerPivot per le raccolte siti in Amministrazione centrale</span><span class="sxs-lookup"><span data-stu-id="2ab27-102">Activate PowerPivot Feature Integration for Site Collections in Central Administration</span></span>
  <span data-ttu-id="2ab27-103">L'attivazione dell'integrazione della caratteristica PowerPivot per raccolte siti specifiche è obbligatoria se è stata utilizzata l'opzione di installazione Farm esistente per installare SQL Server PowerPivot per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2ab27-103">Activating PowerPivot feature integration for specific site collections is required if you used the Existing Farm installation option to install SQL Server PowerPivot for SharePoint.</span></span> <span data-ttu-id="2ab27-104">Se PowerPivot per SharePoint è stato installato utilizzando l'opzione Nuovo server, è possibile ignorare questa attività perché il programma di installazione di SQL Server ha già attivato l'integrazione della caratteristica PowerPivot per la raccolta siti radice durante la configurazione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2ab27-104">If you installed PowerPivot for SharePoint using the New Server option, you can skip this task because SQL Server Setup already activated PowerPivot feature integration for the root site collection when it configured your deployment.</span></span>  
  
 <span data-ttu-id="2ab27-105">L'attivazione della caratteristica a livello di raccolta siti è necessaria per rendere disponibili pagine e modelli ai siti, incluse le pagine di configurazione per l'aggiornamento dei dati pianificato e le pagine dell'applicazione per Raccolta PowerPivot e raccolte Feed di dati.</span><span class="sxs-lookup"><span data-stu-id="2ab27-105">Feature activation at the site collection level is necessary to make application pages and templates available to your sites, including configuration pages for scheduled data refresh and application pages for PowerPivot Gallery and Data Feed libraries.</span></span>  
  
 <span data-ttu-id="2ab27-106">È necessario attivare l'integrazione PowerPivot per ogni raccolta siti in cui è supportata l'elaborazione di query PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="2ab27-106">You must activate PowerPivot integration for each site collection that supports PowerPivot query processing.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2ab27-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2ab27-107">Prerequisites</span></span>  
 <span data-ttu-id="2ab27-108">È necessario essere un amministratore della raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="2ab27-108">You must be a site collection administrator.</span></span>  
  
## <a name="activate-powerpivot-features"></a><span data-ttu-id="2ab27-109">Attivare le caratteristiche di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="2ab27-109">Activate PowerPivot Features</span></span>  
  
1.  <span data-ttu-id="2ab27-110">Da un sito di SharePoint scegliere **Azioni sito**.</span><span class="sxs-lookup"><span data-stu-id="2ab27-110">On a SharePoint site, click **Site Actions**.</span></span>  
  
     <span data-ttu-id="2ab27-111">Per impostazione predefinita, l'accesso alle applicazioni Web SharePoint viene effettuato tramite la porta 80.</span><span class="sxs-lookup"><span data-stu-id="2ab27-111">By default, SharePoint web applications are accessed through port 80.</span></span> <span data-ttu-id="2ab27-112">Ciò significa che spesso è possibile accedere a un sito di SharePoint immettendo http://\<computer name> per aprire la raccolta siti radice.</span><span class="sxs-lookup"><span data-stu-id="2ab27-112">This means that you can often access a SharePoint site by entering http://\<computer name> to open the root site collection.</span></span>  
  
2.  <span data-ttu-id="2ab27-113">Fare clic su **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="2ab27-113">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="2ab27-114">In Amministrazione raccolta siti selezionare **Caratteristiche raccolta siti**.</span><span class="sxs-lookup"><span data-stu-id="2ab27-114">In Site Collection Administration, click **Site collection features**.</span></span>  
  
4.  <span data-ttu-id="2ab27-115">Scorrere la pagina verso il basso fino a individuare la **funzionalità di raccolta siti di integrazione PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="2ab27-115">Scroll down the page until you find **PowerPivot Integration Site Collection Feature**.</span></span>  
  
5.  <span data-ttu-id="2ab27-116">Fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="2ab27-116">Click **Activate**.</span></span>  
  
6.  <span data-ttu-id="2ab27-117">Ripetere per le raccolte siti aggiuntive aprendo ogni sito e facendo clic su **Azioni sito**.</span><span class="sxs-lookup"><span data-stu-id="2ab27-117">Repeat for additional site collections by opening each site and clicking **Site Actions**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab27-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ab27-118">See Also</span></span>  
 <span data-ttu-id="2ab27-119">[Amministrazione e configurazione del server PowerPivot in Amministrazione centrale](power-pivot-server-administration-and-configuration-in-central-administration.md) </span><span class="sxs-lookup"><span data-stu-id="2ab27-119">[PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span></span>  
 <span data-ttu-id="2ab27-120">[Configurazione iniziale &#40;PowerPivot per SharePoint&#41;](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="2ab27-120">[Initial Configuration &#40;PowerPivot for SharePoint&#41;](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="2ab27-121">Installazione di PowerPivot per SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="2ab27-121">PowerPivot for SharePoint 2010 Installation</span></span>](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
