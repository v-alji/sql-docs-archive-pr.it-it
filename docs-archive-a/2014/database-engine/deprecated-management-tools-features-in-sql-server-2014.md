---
title: Funzionalità degli strumenti di gestione deprecate in SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: a08d1354-cc91-4ab7-a73f-3ad815af3d5a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 484e4078e25249e17a1d8b87426a395c3cfa1725
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626260"
---
# <a name="deprecated-management-tools-features-in-sql-server-2014"></a><span data-ttu-id="12ba9-102">Funzionalità degli strumenti di gestione deprecate in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="12ba9-102">Deprecated Management Tools Features in SQL Server 2014</span></span>
  <span data-ttu-id="12ba9-103">In questo argomento vengono descritte le funzionalità deprecate degli strumenti di gestione ancora disponibili in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12ba9-103">This topic describes the deprecated Management Tools features that are still available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="12ba9-104">Tali funzionalità verranno rimosse a partire da una delle prossime versioni di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12ba9-104">These features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="12ba9-105">È consigliabile non usare le funzionalità deprecate nelle nuove applicazioni.</span><span class="sxs-lookup"><span data-stu-id="12ba9-105">Deprecated features should not be used in new applications.</span></span>  
  
|<span data-ttu-id="12ba9-106">Feature</span><span class="sxs-lookup"><span data-stu-id="12ba9-106">Feature</span></span>|<span data-ttu-id="12ba9-107">Fase di deprecazione</span><span class="sxs-lookup"><span data-stu-id="12ba9-107">Deprecation stage</span></span>|  
|-------------|-----------------------|  
|[!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]<span data-ttu-id="12ba9-108">API server registrato</span><span class="sxs-lookup"><span data-stu-id="12ba9-108">Registered Server API</span></span>|<span data-ttu-id="12ba9-109">Annuncio</span><span class="sxs-lookup"><span data-stu-id="12ba9-109">Announcement</span></span>|  
|<span data-ttu-id="12ba9-110">sqlps.exe</span><span class="sxs-lookup"><span data-stu-id="12ba9-110">sqlps.exe</span></span>|<span data-ttu-id="12ba9-111">Avviso</span><span class="sxs-lookup"><span data-stu-id="12ba9-111">Warning</span></span>|  
|<span data-ttu-id="12ba9-112">osql.exe</span><span class="sxs-lookup"><span data-stu-id="12ba9-112">osql.exe</span></span>|<span data-ttu-id="12ba9-113">Avviso</span><span class="sxs-lookup"><span data-stu-id="12ba9-113">Warning</span></span>|  
|<span data-ttu-id="12ba9-114">SQLMail</span><span class="sxs-lookup"><span data-stu-id="12ba9-114">SQLMail</span></span>|<span data-ttu-id="12ba9-115">Avviso</span><span class="sxs-lookup"><span data-stu-id="12ba9-115">Warning</span></span>|  
|<span data-ttu-id="12ba9-116">Classe SMO: classe Microsoft.SQLServer.Management.Smo.Information</span><span class="sxs-lookup"><span data-stu-id="12ba9-116">SMO class: Microsoft.SQLServer.Management.Smo.Information class</span></span>|<span data-ttu-id="12ba9-117">Annuncio</span><span class="sxs-lookup"><span data-stu-id="12ba9-117">Announcement</span></span>|  
|<span data-ttu-id="12ba9-118">Classe SMO: classe Microsoft.SQLServer.Management.Smo.Settings</span><span class="sxs-lookup"><span data-stu-id="12ba9-118">SMO class: Microsoft.SQLServer.Management.Smo.Settings class</span></span>|<span data-ttu-id="12ba9-119">Annuncio</span><span class="sxs-lookup"><span data-stu-id="12ba9-119">Announcement</span></span>|  
|<span data-ttu-id="12ba9-120">Classe SMO: classe Microsoft.SQLServer.Management.Smo.DatabaseOptions</span><span class="sxs-lookup"><span data-stu-id="12ba9-120">SMO Class: Microsoft.SQLServer.Management.Smo.DatabaseOptions class</span></span>|<span data-ttu-id="12ba9-121">Annuncio</span><span class="sxs-lookup"><span data-stu-id="12ba9-121">Announcement</span></span>|  
|<span data-ttu-id="12ba9-122">Classe SMO: proprietà Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger.NotForReplication</span><span class="sxs-lookup"><span data-stu-id="12ba9-122">SMO Class: Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger.NotForReplication property</span></span>|<span data-ttu-id="12ba9-123">Annuncio</span><span class="sxs-lookup"><span data-stu-id="12ba9-123">Announcement</span></span>|  
|<span data-ttu-id="12ba9-124">Sistema del progetto di database, inclusa l'integrazione del controllo del codice sorgente, in SSMS</span><span class="sxs-lookup"><span data-stu-id="12ba9-124">The Database Project System, including source-control integration, in SSMS</span></span>|<span data-ttu-id="12ba9-125">Annuncio</span><span class="sxs-lookup"><span data-stu-id="12ba9-125">Announcement</span></span>|  
|<span data-ttu-id="12ba9-126">Notifiche net send ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span><span class="sxs-lookup"><span data-stu-id="12ba9-126">Net send notifications ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span></span>|<span data-ttu-id="12ba9-127">Annuncio</span><span class="sxs-lookup"><span data-stu-id="12ba9-127">Announcement</span></span>|  
|<span data-ttu-id="12ba9-128">Notifiche con cercapersone ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span><span class="sxs-lookup"><span data-stu-id="12ba9-128">Pager notifications ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span></span>|<span data-ttu-id="12ba9-129">Annuncio</span><span class="sxs-lookup"><span data-stu-id="12ba9-129">Announcement</span></span>|  
|<span data-ttu-id="12ba9-130">Sottosistema ActiveX ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span><span class="sxs-lookup"><span data-stu-id="12ba9-130">The ActiveX subsystem ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span></span>|<span data-ttu-id="12ba9-131">Annuncio</span><span class="sxs-lookup"><span data-stu-id="12ba9-131">Announcement</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12ba9-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12ba9-132">See Also</span></span>  
 [<span data-ttu-id="12ba9-133">Compatibilità con le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="12ba9-133">Backward Compatibility</span></span>](../../2014/getting-started/backward-compatibility.md)  
  
  
