---
title: Risoluzione dei problemi di aggiornamento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Upgrade Advisor [SQL Server], reference
- component issue resolution [Upgrade Advisor]
- resolving upgrade issues
- upgrade blocks [Upgrade Advisor]
- detecting upgrade issues
- finding upgrade issues
- Upgrade Advisor [SQL Server], blocking issues
- configurations preventing upgrading [Upgrade Advisor]
- locating upgrade issues
- blocking issues [Upgrade Advisor]
- issues preventing upgrading [Upgrade Advisor]
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, reference
- analyzing system [Upgrade Advisor], resolving issues
- settings preventing upgrading [Upgrade Advisor]
- upgrade issue reference [Upgrade Advisor]
- identifying upgrade issues
- fixing upgrade issues [Upgrade Advisor]
ms.assetid: 113eb435-8d36-4ed6-9790-b5e4c14809c8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c00b08d40bc8c17013e6af19b5d11b0b7ad78c4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637600"
---
# <a name="resolving-upgrade-issues"></a><span data-ttu-id="4dca3-102">Risoluzione dei problemi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="4dca3-102">Resolving Upgrade Issues</span></span>
  <span data-ttu-id="4dca3-103">Negli argomenti di questa sezione vengono descritti i problemi relativi all'aggiornamento rilevabili e quelli non rilevabili che possono tuttavia influire sull'esecuzione dell'aggiornamento o del post-aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="4dca3-103">The topics in this section describe upgrade issues that can be detected as well as those that cannot be detected, but that might affect the upgrade or post-upgrade experience.</span></span> <span data-ttu-id="4dca3-104">I problemi sono organizzati per componente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dca3-104">The issues are organized by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4dca3-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4dca3-105">In This Section</span></span>  
  
-   [<span data-ttu-id="4dca3-106">Problemi di aggiornamento più recenti</span><span class="sxs-lookup"><span data-stu-id="4dca3-106">Late-Breaking Upgrade Issues</span></span>](../../../2014/sql-server/install/late-breaking-upgrade-issues.md)  
  
-   [<span data-ttu-id="4dca3-107">Problemi di aggiornamento del motore di database</span><span class="sxs-lookup"><span data-stu-id="4dca3-107">Database Engine Upgrade Issues</span></span>](../../../2014/sql-server/install/database-engine-upgrade-issues.md)  
  
-   [<span data-ttu-id="4dca3-108">Problemi di aggiornamento della ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="4dca3-108">Full-Text Search Upgrade Issues</span></span>](../../../2014/sql-server/install/full-text-search-upgrade-issues.md)  
  
-   [<span data-ttu-id="4dca3-109">Problemi di aggiornamento della replica</span><span class="sxs-lookup"><span data-stu-id="4dca3-109">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
-   [<span data-ttu-id="4dca3-110">Problemi di aggiornamento Reporting Services &#40;preparazione aggiornamento&#41;</span><span class="sxs-lookup"><span data-stu-id="4dca3-110">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4dca3-111">Problemi di aggiornamento di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="4dca3-111">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
## <a name="issues-that-prevent-upgrading"></a><span data-ttu-id="4dca3-112">Problemi che impediscono l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="4dca3-112">Issues That Prevent Upgrading</span></span>  
 <span data-ttu-id="4dca3-113">Alcune configurazioni o impostazioni di una versione precedente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono impedire l'esecuzione dell'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dca3-113">A few configurations or settings in a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can prevent you from upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="4dca3-114">Se il programma di installazione rileva questi problemi durante l'installazione di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], il processo di aggiornamento viene arrestato e all'utente viene richiesto di eseguire Preparazione di aggiornamento e di risolvere i problemi che bloccano l'installazione.</span><span class="sxs-lookup"><span data-stu-id="4dca3-114">If Setup detects these issues when you install [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], Setup stops the upgrade process and requests that you run Upgrade Advisor and fix any blocking issues.</span></span>  
  
### [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
 <span data-ttu-id="4dca3-115">Se le attività seguenti sono elencate nel report di aggiornamento del [!INCLUDE[ssDE](../../includes/ssde-md.md)], è necessario eseguire le azioni richieste prima dell'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4dca3-115">If the following tasks are listed on the [!INCLUDE[ssDE](../../includes/ssde-md.md)] upgrade report, you must perform the required actions before you upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]:</span></span>  
  
-   [<span data-ttu-id="4dca3-116">Scollegare il database con ID 32767</span><span class="sxs-lookup"><span data-stu-id="4dca3-116">Detach database ID 32767</span></span>](../../../2014/sql-server/install/detach-database-id-32767.md)  
  
-   [<span data-ttu-id="4dca3-117">Rinominare gli account di accesso con nomi uguali a quelli dei ruoli predefiniti del server</span><span class="sxs-lookup"><span data-stu-id="4dca3-117">Rename logins matching fixed server role names</span></span>](../../../2014/sql-server/install/rename-logins-matching-fixed-server-role-names.md)  
  
-   [<span data-ttu-id="4dca3-118">Rinominare l'utente sys</span><span class="sxs-lookup"><span data-stu-id="4dca3-118">Rename user sys</span></span>](../../../2014/sql-server/install/rename-user-sys.md)  
  
-   [<span data-ttu-id="4dca3-119">Utilizzare sp_rename per rinominare gli indici duplicati</span><span class="sxs-lookup"><span data-stu-id="4dca3-119">Use sp_rename to rename duplicate index name</span></span>](../../../2014/sql-server/install/use-sp-rename-to-rename-duplicate-index-name.md)  
  
## <a name="see-also"></a><span data-ttu-id="4dca3-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dca3-120">See Also</span></span>  
 [<span data-ttu-id="4dca3-121">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="4dca3-121">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
