---
title: SQL Server Agent log shipping categoria di processi causa l'esito negativo dell'aggiornamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server Agent]
- job categories [SQL Server Agent]
ms.assetid: ef05ce53-c6ce-42ec-9df8-46c951626424
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2f5947e8fc8d459388fe35d86c75666e25b5d907
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726459"
---
# <a name="sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail"></a><span data-ttu-id="ef51d-102">La categoria di processi per il log shipping di SQL Server Agent impedisce il completamento dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="ef51d-102">SQL Server Agent log shipping job category causes upgrade to fail</span></span>
  <span data-ttu-id="ef51d-103">Il processo di aggiornamento non verrà completato se esiste una categoria di processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent denominata Log shipping.</span><span class="sxs-lookup"><span data-stu-id="ef51d-103">The upgrade process will fail if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job category named Log Shipping exists.</span></span>  
  
## <a name="component"></a><span data-ttu-id="ef51d-104">Componente</span><span class="sxs-lookup"><span data-stu-id="ef51d-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ef51d-105">Agent</span><span class="sxs-lookup"><span data-stu-id="ef51d-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="ef51d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef51d-106">Description</span></span>  
 <span data-ttu-id="ef51d-107">Esiste una categoria di processi di sistema denominata Log shipping.</span><span class="sxs-lookup"><span data-stu-id="ef51d-107">There is a system job category named Log Shipping.</span></span> <span data-ttu-id="ef51d-108">Se una delle installazioni da aggiornare contiene già una categoria di processi creata dall'utente denominata Log shipping, sarà necessario rinominarla prima dell'aggiornamento. In caso contrario, l'aggiornamento non verrà completato.</span><span class="sxs-lookup"><span data-stu-id="ef51d-108">If an installation that is being upgraded already contains a user-created job category named Log Shipping, you must rename the job category before you upgrade; otherwise, the upgrade process will fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef51d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef51d-109">See Also</span></span>  
 <span data-ttu-id="ef51d-110">[Il log shipping non viene eseguito dopo l'aggiornamento](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md) </span><span class="sxs-lookup"><span data-stu-id="ef51d-110">[Log shipping will not run after upgrading](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md) </span></span>  
 <span data-ttu-id="ef51d-111">[L'aggiornamento modificherà l'account proxy utente SQL Server Agent al UpgradedProxyAccount temporaneo](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span><span class="sxs-lookup"><span data-stu-id="ef51d-111">[Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span></span>  
 [<span data-ttu-id="ef51d-112">Problemi di aggiornamento di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="ef51d-112">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
