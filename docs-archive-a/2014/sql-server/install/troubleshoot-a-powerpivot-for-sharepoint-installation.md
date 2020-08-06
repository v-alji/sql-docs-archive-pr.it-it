---
title: Risolvere i problemi relativi a un'installazione di PowerPivot per SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 97bc2ce7-af04-4372-ad79-c96b8c3417ab
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3adc27132d976288c14ac702baae0b842e8aef0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628155"
---
# <a name="troubleshoot-a-powerpivot-for-sharepoint-installation"></a><span data-ttu-id="20bc2-102">Risoluzione dei problemi di un'installazione di PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="20bc2-102">Troubleshoot a PowerPivot for SharePoint Installation</span></span>
  <span data-ttu-id="20bc2-103">Se vengono generati errori anziché le pagine e le caratteristiche previste, effettuare le operazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="20bc2-103">If you get errors instead of the pages and features you expect, do the following.</span></span>  
  
-   <span data-ttu-id="20bc2-104">Esaminare le note sulla versione di SharePoint e di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] per ottenere soluzioni alternative a problemi di installazione noti.</span><span class="sxs-lookup"><span data-stu-id="20bc2-104">Review release notes for both SharePoint and [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to get workarounds for known installation problems.</span></span> <span data-ttu-id="20bc2-105">Le note sulla versione vengono fornite con il supporto di installazione oppure sono disponibili nel sito Microsoft da cui si scarica il software.</span><span class="sxs-lookup"><span data-stu-id="20bc2-105">Release notes are provided with the installation media or on the Microsoft site from which you downloaded the software.</span></span>  
  
    -   <span data-ttu-id="20bc2-106">[Note sulla versione di SQL Server 2014](https://technet.microsoft.com/library/dn169381\(v=sql.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="20bc2-106">[SQL Server 2014 Release Notes](https://technet.microsoft.com/library/dn169381\(v=sql.15\).aspx).</span></span>  
  
-   <span data-ttu-id="20bc2-107">Vedere l'argomento di Wiki di TechNet relativo alla [risoluzione dei problemi nelle installazioni di PowerPivot (e altri componenti aggiuntivi)](https://social.technet.microsoft.com/wiki/contents/articles/13737.troubleshooting-installations-of-powerpivot-and-other-add-ins.aspx).</span><span class="sxs-lookup"><span data-stu-id="20bc2-107">See the Technet wiki topic, [Troubleshooting Installations of PowerPivot (and other add-ins)](https://social.technet.microsoft.com/wiki/contents/articles/13737.troubleshooting-installations-of-powerpivot-and-other-add-ins.aspx).</span></span>  
  
## <a name="issues"></a><span data-ttu-id="20bc2-108">Problemi</span><span class="sxs-lookup"><span data-stu-id="20bc2-108">Issues</span></span>  
  
### <a name="powerpivot-gallery-thumbnail-images-show-as-a-red-x"></a><span data-ttu-id="20bc2-109">Le immagini di anteprima per Raccolta PowerPivot sono visualizzate come una X rossa.</span><span class="sxs-lookup"><span data-stu-id="20bc2-109">PowerPivot Gallery Thumbnail images show as a red X</span></span>  
 <span data-ttu-id="20bc2-110">Una delle cause possibile potrebbe essere che **Integrazione della funzionalità di PowerPivot per le raccolte siti** non è attiva.</span><span class="sxs-lookup"><span data-stu-id="20bc2-110">One Possible cause is the **PowerPivot features Integration for Site Collections** is not active.</span></span> <span data-ttu-id="20bc2-111">Completare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20bc2-111">Complete the following:</span></span>  
  
1.  <span data-ttu-id="20bc2-112">Nella libreria della raccolta PowerPivot fare clic su **Impostazioni sito** dall'icona dell'ingranaggio ![impostazioni di SharePoint](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "Impostazioni di SharePoint") o dall'elenco **Home** .</span><span class="sxs-lookup"><span data-stu-id="20bc2-112">In the PowerPivot Gallery library, click **Site Settings** from either the gear icon ![SharePoint Settings](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint Settings") or the **Home** list.</span></span>  
  
2.  <span data-ttu-id="20bc2-113">Nella sezione **Amministrazione raccolta siti** fare clic su **Funzionalità raccolta siti**.</span><span class="sxs-lookup"><span data-stu-id="20bc2-113">In the **Site Collection Administration** section, click **Site Collection Features**.</span></span>  
  
3.  <span data-ttu-id="20bc2-114">Fare clic su **Funzionalità raccolta siti**.</span><span class="sxs-lookup"><span data-stu-id="20bc2-114">Click **Site Collection Features**.</span></span>  
  
4.  <span data-ttu-id="20bc2-115">Verificare che **Integrazione delle funzionalità di PowerPivot per le raccolte siti** sia **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="20bc2-115">Verify **PowerPivot features Integration for Site Collections** is **Active**.</span></span>  
  
 <span data-ttu-id="20bc2-116">Per ulteriori cause di questo problema, vedere la pagina [relativa alle icone rosse per le icone della raccolta PowerPivot](https://support.microsoft.com/kb/2361559) https://support.microsoft.com/kb/2361559) .</span><span class="sxs-lookup"><span data-stu-id="20bc2-116">For additional causes of this issue, see [PowerPivot Gallery shows Red X's for Icons](https://support.microsoft.com/kb/2361559) (https://support.microsoft.com/kb/2361559).</span></span>  
  
  
