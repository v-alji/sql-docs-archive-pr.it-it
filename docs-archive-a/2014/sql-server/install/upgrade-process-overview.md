---
title: Panoramica del processo di aggiornamento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server
- Upgrade Advisor [SQL Server], process description
- SQL Server Upgrade Advisor, process description
- upgrade process [Upgrade Advisor]
ms.assetid: f77ffbab-a195-4124-acce-9c538f7ca9ce
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5da6dc3b3e6d6c7058193801100bf2552bfde7cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726455"
---
# <a name="upgrade-process-overview"></a><span data-ttu-id="1e6a2-102">Panoramica del processo di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="1e6a2-102">Upgrade Process Overview</span></span>
  <span data-ttu-id="1e6a2-103">In questo argomento vengono fornite informazioni sulle procedure consigliate per Preparazione aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] e viene riportato un riepilogo del processo consigliato per eseguire l'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e6a2-103">This topic provides best practice information for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor and a summary of the recommended process for upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="upgrade-process"></a><span data-ttu-id="1e6a2-104">Processo di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="1e6a2-104">Upgrade Process</span></span>  
 <span data-ttu-id="1e6a2-105">I server che eseguono [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] o [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] possono essere aggiornati a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e6a2-105">Servers that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] can be upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="1e6a2-106">Mentre alcuni componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono essere aggiornati sul posto, altri devono essere migrati e altri ancora sono stati sostituiti da nuovi componenti.</span><span class="sxs-lookup"><span data-stu-id="1e6a2-106">Whereas some [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components can be upgraded in place, others must be migrated, and still others have been superseded by new components.</span></span> <span data-ttu-id="1e6a2-107">Ad esempio, a partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) sostituisce Data Transformation Services (DTS) e DTS non è più supportato in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e6a2-107">For example, starting with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) supersedes Data Transformation Services (DTS), and DTS is no longer supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="1e6a2-108">Quando si formula il piano di aggiornamento, è possibile che sia necessario pianificare l'aggiornamento dei pacchetti DTS correnti ai pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e6a2-108">When you formulate your upgrade plan, you might need to plan for updating your current DTS packages to [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages.</span></span>  
  
 <span data-ttu-id="1e6a2-109">Preparazione aggiornamento consente di valutare le installazioni, i componenti e i file correlati correnti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per identificare i problemi noti che si verificano durante e dopo l'aggiornamento o la migrazione a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e6a2-109">Upgrade Advisor enables you to evaluate current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installations, components, and related files to identify known issues that will cause problems both during and after you upgrade or migrate to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="1e6a2-110">Alcuni di questi problemi noti bloccano l'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e6a2-110">A few of these known issues block the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] upgrade.</span></span> <span data-ttu-id="1e6a2-111">Nel report di Preparazione aggiornamento, questi problemi sono identificati come blocchi di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1e6a2-111">In the Upgrade Advisor report, these issues are identified as Upgrade Blockers.</span></span> <span data-ttu-id="1e6a2-112">Prima di eseguire il programma di installazione è necessario risolvere i blocchi di aggiornamento, altrimenti il programma di installazione di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] viene terminato e viene consigliato di eseguire Preparazione aggiornamento per identificare i problemi specifici che bloccano l'esecuzione dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1e6a2-112">If you have not addressed the Upgrade Blockers before you run Setup, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup exits and recommends that you run Upgrade Advisor to identify the specific issues that are blocking the upgrade.</span></span>  
  
 <span data-ttu-id="1e6a2-113">Prima di eseguire l'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], è consigliabile eseguire il backup dei dati e delle impostazioni di sistema ed effettuare le operazioni strategiche come descritto nelle linee guida per il funzionamento definite per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1e6a2-113">As a best practice before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you back up your data and system settings, and take strategic steps as outlined in the operational guidelines defined for your organization.</span></span> <span data-ttu-id="1e6a2-114">Per completare l'aggiornamento, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e6a2-114">Use the following steps to complete the upgrade:</span></span>  
  
1.  <span data-ttu-id="1e6a2-115">Esaminare le informazioni contenute in [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e6a2-115">Review [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="1e6a2-116">Eseguire il backup di dati e impostazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="1e6a2-116">Back up data and system settings.</span></span>  
  
3.  <span data-ttu-id="1e6a2-117">Eseguire Upgrade Advisor.</span><span class="sxs-lookup"><span data-stu-id="1e6a2-117">Run Upgrade Advisor.</span></span>  
  
     <span data-ttu-id="1e6a2-118">I dati o le impostazioni del computer non verranno modificate.</span><span class="sxs-lookup"><span data-stu-id="1e6a2-118">Upgrade Advisor does not modify your data or change settings on your computer.</span></span>  
  
4.  <span data-ttu-id="1e6a2-119">Esaminare i problemi identificati nel report di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1e6a2-119">Review the issues identified in the Upgrade Advisor report.</span></span>  
  
5.  <span data-ttu-id="1e6a2-120">Risolvere eventuali problemi di blocco che potrebbero impedire l'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e6a2-120">Resolve any blocking issues that would prevent you from upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
6.  <span data-ttu-id="1e6a2-121">Risolvere eventuali altri problemi di pre-aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1e6a2-121">Resolve any other pre-upgrade issues.</span></span>  
  
7.  <span data-ttu-id="1e6a2-122">Eseguire Preparazione aggiornamento per verificare che tutti i problemi noti siano stati risolti.</span><span class="sxs-lookup"><span data-stu-id="1e6a2-122">Run Upgrade Advisor to verify that all known issues have been addressed.</span></span>  
  
8.  <span data-ttu-id="1e6a2-123">Eseguire il programma di installazione di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e6a2-123">Run [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup.</span></span>  
  
9. <span data-ttu-id="1e6a2-124">Risolvere eventuali problemi di post-aggiornamento e migrazione.</span><span class="sxs-lookup"><span data-stu-id="1e6a2-124">Resolve any post-upgrade and migration issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e6a2-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e6a2-125">See Also</span></span>  
 <span data-ttu-id="1e6a2-126">[Esecuzione di preparazione aggiornamento &#40;interfaccia utente&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="1e6a2-126">[Running Upgrade Advisor &#40;User Interface&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span></span>  
 <span data-ttu-id="1e6a2-127">[Utilizzo dei report](../../../2014/sql-server/install/using-reports.md) </span><span class="sxs-lookup"><span data-stu-id="1e6a2-127">[Using Reports](../../../2014/sql-server/install/using-reports.md) </span></span>  
 [<span data-ttu-id="1e6a2-128">Uso di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="1e6a2-128">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
