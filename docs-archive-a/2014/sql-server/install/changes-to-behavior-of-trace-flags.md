---
title: Modifiche al comportamento dei flag di traccia | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- trace flags [SQL Server], behavior changes
ms.assetid: d739df96-2659-4383-8e10-194657632526
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11d71e8401f6b870aaeb3f64f4145b509e3a3fe0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628220"
---
# <a name="changes-to-behavior-of-trace-flags"></a><span data-ttu-id="55393-102">Modifiche al comportamento dei flag di traccia</span><span class="sxs-lookup"><span data-stu-id="55393-102">Changes to behavior of trace flags</span></span>
  <span data-ttu-id="55393-103">I flag di traccia globali impostati da una sessione diventano immediatamente effettivi nelle altre sessioni.</span><span class="sxs-lookup"><span data-stu-id="55393-103">Global trace flags set by a session take effect in other sessions immediately.</span></span> <span data-ttu-id="55393-104">Alcuni flag di traccia di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] non esistono in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55393-104">Some trace flags from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] do not exist in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="55393-105">Componente</span><span class="sxs-lookup"><span data-stu-id="55393-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="55393-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55393-106">Description</span></span>  
 <span data-ttu-id="55393-107">Si consiglia di disabilitare tutti i flag di traccia prima di eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="55393-107">We recommend that you disable all trace flags before you upgrade.</span></span> <span data-ttu-id="55393-108">I flag di traccia che modificano la disponibilità o le modalità di recupero del database potrebbero impedire al [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] di di aggiornare correttamente l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55393-108">Trace flags that modify the database availability or recovery modes might prevent the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] from successfully upgrading your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="55393-109">È possibile attivare i flag di traccia dopo avere verificato che sono necessari e sono ancora validi in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55393-109">You can enable the trace flags after you verify that the trace flags are required and are still valid in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="55393-110">Se è necessario riabilitare i flag di traccia, eseguire test aggiuntivi sull'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55393-110">If you must re-enable trace flags, you should perform additional tests on your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="55393-111">supporta flag di traccia a livello di sessione e globale.</span><span class="sxs-lookup"><span data-stu-id="55393-111">supports global and session level trace flags.</span></span> <span data-ttu-id="55393-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] i flag di traccia possono essere specificati come locali o globali utilizzando un argomento aggiuntivo (-1) nel comando DBCC TRACEON.</span><span class="sxs-lookup"><span data-stu-id="55393-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], trace flags can be specified as either local or global by using an additional argument (-1) in the DBCC TRACEON command.</span></span> <span data-ttu-id="55393-113">Se questo argomento non viene specificato, il valore predefinito è locale.</span><span class="sxs-lookup"><span data-stu-id="55393-113">If this argument is not specified, the default value is local.</span></span>  
  
 <span data-ttu-id="55393-114">Inoltre, in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] , un flag di traccia impostato nella sessione a non diventa automaticamente effettivo in una sessione B già esistente. Questo flag di traccia viene invece applicato solo dopo la prima volta che un flag di traccia viene impostato nella sessione B. Questo comportamento è non deterministico in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] e è deterministico in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive, in cui i flag di traccia globali impostati nella sessione a vengono impostati immediatamente in altre sessioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="55393-114">Also, in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], a trace flag set in session A does not automatically take effect in an already existing session B. Instead, this trace flag takes effect only after the first time any trace flag is set in session B. This behavior is nondeterministic in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] and is deterministic in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions, where global trace flags set in session A are set immediately in other concurrent sessions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55393-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55393-115">See Also</span></span>  
 <span data-ttu-id="55393-116">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="55393-116">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="55393-117">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="55393-117">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
