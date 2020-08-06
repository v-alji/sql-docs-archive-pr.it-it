---
title: Filtri ISAPI rilevati nel sito del server di report (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- ISAPI filters
- report servers [Reporting Services], upgrade issues
ms.assetid: dd30560d-9e16-47c7-ba68-a9743a657e4e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: bff1834ddf1b8f90787a47a8fd58a240d2b715d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724396"
---
# <a name="isapi-filters-detected-on-the-report-server-site-upgrade-advisor"></a><span data-ttu-id="c80ba-102">Filtri ISAPI rilevati sul sito del server di report (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="c80ba-102">ISAPI filters detected on the report server site (Upgrade Advisor)</span></span>
  <span data-ttu-id="c80ba-103">Sono stati rilevati uno o più filtri ISAPI per il sito Web che ospita le directory virtuali del server di report e di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="c80ba-103">Upgrade Advisor detected one or more ISAPI filters on the Web site that hosts the report server and Report Manager virtual directories.</span></span> <span data-ttu-id="c80ba-104">I filtri ISAPI non sono supportati in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c80ba-104">ISAPI filters are not supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
||  
|-|  
|<span data-ttu-id="c80ba-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Native.</span><span class="sxs-lookup"><span data-stu-id="c80ba-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native .</span></span>|  
  
## <a name="component"></a><span data-ttu-id="c80ba-106">Componente</span><span class="sxs-lookup"><span data-stu-id="c80ba-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="c80ba-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c80ba-107">Description</span></span>  
 <span data-ttu-id="c80ba-108">Prima di eseguire l'aggiornamento, verificare se i filtri ISAPI per il sito Web sono utilizzati da applicazioni [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c80ba-108">Before upgrading, verify whether the ISAPI filters on the Web site are used by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] applications.</span></span> <span data-ttu-id="c80ba-109">Se il filtro ISAPI non è necessario, è possibile aggiornare il server di report.</span><span class="sxs-lookup"><span data-stu-id="c80ba-109">If you do not require the ISAPI filter, you can upgrade the report server.</span></span> <span data-ttu-id="c80ba-110">Verranno creati gli URL predefiniti, senza il supporto per il filtro ISAPI in esecuzione in IIS.</span><span class="sxs-lookup"><span data-stu-id="c80ba-110">Setup will create the default URLs, without support for the ISAPI filter that runs in IIS.</span></span> <span data-ttu-id="c80ba-111">Se il filtro ISAPI è necessario, non eseguire l'aggiornamento finché non sarà stata trovata un'alternativa per l'hosting del filtro ISAPI, ad esempio utilizzando ISA Server o continuando a ospitare il filtro ISAPI in IIS.</span><span class="sxs-lookup"><span data-stu-id="c80ba-111">If you require the ISAPI filter, do not upgrade until you find an alternative way of hosting the ISAPI filter (for example, using ISA Server or continuing to host the ISAPI filter in IIS).</span></span> <span data-ttu-id="c80ba-112">Il server di report supporta ASP.NET HTTPModules come sostituzione per i filtri ISAPI in scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="c80ba-112">The report server supports ASP.NET HTTPModules as a replacement for ISAPI filters in certain scenarios.</span></span> <span data-ttu-id="c80ba-113">Per ulteriori informazioni, vedere la documentazione di ASP.NET in MSDN.</span><span class="sxs-lookup"><span data-stu-id="c80ba-113">For more information, see the ASP.NET documentation on MSDN.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c80ba-114">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="c80ba-114">Corrective Action</span></span>  
 <span data-ttu-id="c80ba-115">Valutare e utilizzare una soluzione distinta per ospitare i filtri ISAPI richiesti per l'attività di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="c80ba-115">Evaluate and use a separate solution for hosting ISAPI filters required by your deployment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c80ba-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c80ba-116">See Also</span></span>  
 [<span data-ttu-id="c80ba-117">Problemi di aggiornamento Reporting Services &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="c80ba-117">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
