---
title: Convalidare le guide di piano dopo l'aggiornamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], validating after upgrade
ms.assetid: a55ebd88-6f58-454d-b1c4-991b88add522
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18cc0f93ddec46025f659bcb9489bfff3ca846ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716263"
---
# <a name="validate-plan-guides-after-upgrade"></a><span data-ttu-id="58278-102">Convalidare le guide di piano dopo l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="58278-102">Validate Plan Guides After Upgrade</span></span>
  <span data-ttu-id="58278-103">Quando si aggiorna l'applicazione a una nuova versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è consigliabile valutare nuovamente e testare le definizioni delle guide di piano.</span><span class="sxs-lookup"><span data-stu-id="58278-103">We recommend re-evaluating and testing plan guide definitions when you upgrade your application to a new release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="58278-104">I requisiti di ottimizzazione delle prestazioni e la funzionalità di individuazione delle corrispondenze delle guide di piano possono cambiare.</span><span class="sxs-lookup"><span data-stu-id="58278-104">Performance tuning requirements and plan guide matching behavior may change.</span></span> <span data-ttu-id="58278-105">Anche se una guida di piano non valida non farà in modo che una query non riesca, il piano è compilato senza utilizzare la guida di piano e potrebbe non essere la migliore scelta.</span><span class="sxs-lookup"><span data-stu-id="58278-105">Although an invalid plan guide will not cause a query to fail, the plan is compiled without using the plan guide and may not be the best choice.</span></span> <span data-ttu-id="58278-106">Dopo aver aggiornato un database a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], si consiglia di eseguire le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="58278-106">After upgrading a database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="58278-107">Eseguire la convalida delle guide di piano esistenti usando la funzione [sys.fn_validate_plan_guide](/sql/relational-databases/system-functions/sys-fn-validate-plan-guide-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="58278-107">Validate existing plan guides by using the [sys.fn_validate_plan_guide](/sql/relational-databases/system-functions/sys-fn-validate-plan-guide-transact-sql) function.</span></span>  
  
-   <span data-ttu-id="58278-108">Usare gli eventi estesi per eseguire il monitoraggio di piani fuorviati per determinati periodo di tempo usando l'evento [Plan Guide Unsuccessful](../event-classes/plan-guide-unsuccessful-event-class.md) .</span><span class="sxs-lookup"><span data-stu-id="58278-108">Use extended events to monitor for misguided plans for some period of time by using the [Plan Guide Unsuccessful](../event-classes/plan-guide-unsuccessful-event-class.md) event.</span></span>  
  
  
