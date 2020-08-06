---
title: Utilizzo di preparazione aggiornamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], when to use
- SQL Server Upgrade Advisor, when to use
- when to use Upgrade Advisor
ms.assetid: 5f26a7b9-1ac2-442c-8316-87b078db3baf
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 75a16e57734493cdd7ac00e7bad3124eb7a99d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628080"
---
# <a name="working-with-upgrade-advisor"></a><span data-ttu-id="5ced3-102">Utilizzo di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="5ced3-102">Working with Upgrade Advisor</span></span>
  <span data-ttu-id="5ced3-103">Per assicurare il corretto completamento dell'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], Preparazione aggiornamento rende disponibile una console centrale per identificare i problemi da risolvere nelle installazioni e prima di eseguire l'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ced3-103">To help ensure that your upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is successful, Upgrade Advisor provides a central console to identify issues to address in your installations before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="5ced3-104">È possibile utilizzare Preparazione aggiornamento per eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ced3-104">You can use Upgrade Advisor to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="5ced3-105">Analizzare i componenti delle versioni precedenti nei server locali o remoti.</span><span class="sxs-lookup"><span data-stu-id="5ced3-105">Analyze previous version's components on local or remote servers.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5ced3-106">Non è possibile analizzare le istanze remote di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ced3-106">You cannot analyze remote instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="5ced3-107">Visualizzare i risultati dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="5ced3-107">View the results of the analysis.</span></span>  
  
 <span data-ttu-id="5ced3-108">In Preparazione aggiornamento sono inclusi un analizzatore e un visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="5ced3-108">Upgrade Advisor includes an analyzer and a viewer.</span></span> <span data-ttu-id="5ced3-109">L'Analisi guidata di Preparazione aggiornamento analizza i componenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="5ced3-109">The Upgrade Advisor Analysis Wizard analyzes the components you select.</span></span> <span data-ttu-id="5ced3-110">L'analizzatore genera quindi report personalizzati sui problemi che è necessario gestire prima che sia possibile eseguire l'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ced3-110">The analyzer then generates custom reports about issues that you must handle before you can upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="5ced3-111">Utilizzare il Visualizzatore report di Preparazione aggiornamento per visualizzare i report personalizzati.</span><span class="sxs-lookup"><span data-stu-id="5ced3-111">You use the Upgrade Advisor Report Viewer to view the custom reports.</span></span> <span data-ttu-id="5ced3-112">Per ulteriori informazioni sul rilevamento dell'analisi di preparazione aggiornamento, vedere [risoluzione dei problemi di aggiornamento](../../../2014/sql-server/install/resolving-upgrade-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5ced3-112">For more information about what Upgrade Advisor analysis detects, see [Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md).</span></span>  
  
 <span data-ttu-id="5ced3-113">Negli argomenti di questa sezione vengono fornite informazioni generali sulle funzionalità di Preparazione aggiornamento e informazioni sull'utilizzo di Preparazione aggiornamento e dei relativi report.</span><span class="sxs-lookup"><span data-stu-id="5ced3-113">The topics in this section provide an overview of Upgrade Advisor functionality and information about how to use Upgrade Advisor and Upgrade Advisor reports.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ced3-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5ced3-114">In This Section</span></span>  
  
|<span data-ttu-id="5ced3-115">Argomento</span><span class="sxs-lookup"><span data-stu-id="5ced3-115">Topic</span></span>|<span data-ttu-id="5ced3-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ced3-116">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5ced3-117">Panoramica di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="5ced3-117">Overview of Upgrade Advisor</span></span>](../../../2014/sql-server/install/overview-of-upgrade-advisor.md)|<span data-ttu-id="5ced3-118">Vengono fornite informazioni generali sul processo di aggiornamento, sull'Analisi guidata di Preparazione aggiornamento e sul Visualizzatore report di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="5ced3-118">Provides an overview of the upgrade process, the Upgrade Advisor Analysis Wizard, and the Upgrade Advisor Report Viewer.</span></span>|  
|[<span data-ttu-id="5ced3-119">Procedure per Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="5ced3-119">Upgrade Advisor How-to Topics</span></span>](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md)|<span data-ttu-id="5ced3-120">Vengono fornite le istruzioni per eseguire le comuni procedure di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="5ced3-120">Provides instructions to perform common Upgrade Advisor procedures.</span></span>|  
|[<span data-ttu-id="5ced3-121">Guida di riferimento all'interfaccia utente di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="5ced3-121">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)|<span data-ttu-id="5ced3-122">Contiene argomenti che vengono visualizzati se si preme il tasto F1 o **si fa clic su?** nelle pagine dell'analisi guidata di preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="5ced3-122">Contains topics that appear if you press the F1 key or click **Help** on the Upgrade Advisor Analysis Wizard pages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ced3-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ced3-123">See Also</span></span>  
 <span data-ttu-id="5ced3-124">[Installazione di preparazione aggiornamento](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="5ced3-124">[Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="5ced3-125">Risoluzione dei problemi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="5ced3-125">Resolving Upgrade Issues</span></span>](../../../2014/sql-server/install/resolving-upgrade-issues.md)  
  
  
