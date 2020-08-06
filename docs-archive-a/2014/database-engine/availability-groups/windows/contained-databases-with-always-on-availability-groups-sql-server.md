---
title: Database indipendenti con Gruppi di disponibilità Always On (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- contained database [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: cacce3ae-e940-4566-8298-6607c4268e74
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 74c8a0b41ee7224dad83fb41691a4898c15b7b38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624366"
---
# <a name="contained-databases-with-always-on-availability-groups-sql-server"></a><span data-ttu-id="41abf-102">Database indipendenti con Gruppi di disponibilità Always On (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="41abf-102">Contained Databases with Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="41abf-103">In questo argomento vengono fornite informazioni sull'utilizzo di un database indipendente con [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41abf-103">This topic contains information about the using a contained database with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="41abf-104">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="41abf-104">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="41abf-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="41abf-105">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="41abf-106">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="41abf-106">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="41abf-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="41abf-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="41abf-108">Prima di aggiungere un database indipendente a un gruppo di disponibilità, verificare che l'opzione del server `contained database authentication` sia impostata su `1` in ogni istanza del server in cui è ospitata una replica di disponibilità per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="41abf-108">Before adding a contained database to an availability group, ensure that the `contained database authentication` server option is set to `1` on every server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="41abf-109">Per altre informazioni, vedere [Opzione di configurazione del server contained database authentication](../../configure-windows/contained-database-authentication-server-configuration-option.md) e [Opzioni di configurazione del server &#40;SQL Server&#41;](../../configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="41abf-109">For more information, see [contained database authentication Server Configuration Option](../../configure-windows/contained-database-authentication-server-configuration-option.md) and [Server Configuration Options &#40;SQL Server&#41;](../../configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="41abf-110">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="41abf-110">Related Tasks</span></span>  
  
-   [<span data-ttu-id="41abf-111">Opzioni di configurazione del server &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="41abf-111">Server Configuration Options &#40;SQL Server&#41;</span></span>](../../configure-windows/server-configuration-options-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="41abf-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41abf-112">See Also</span></span>  
 <span data-ttu-id="41abf-113">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="41abf-113">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="41abf-114">Database indipendenti</span><span class="sxs-lookup"><span data-stu-id="41abf-114">Contained Databases</span></span>](../../../relational-databases/databases/contained-databases.md)  
  
  
