---
title: Oggetto Avvisi di SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Alerts object
- SQLAgent:Alerts
ms.assetid: e5e37f74-ee88-46d0-ad8f-71fd1b1fa64a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9aa6fa871730af8cf129b3ea6b0aa4f1853d7e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626056"
---
# <a name="sql-server-agent-alerts-object"></a><span data-ttu-id="acf59-102">Oggetto Avvisi di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="acf59-102">SQL Server Agent, Alerts Object</span></span>
  <span data-ttu-id="acf59-103">L'oggetto prestazione **Avvisi** di SQL Server Agent include contatori delle prestazioni che contengono informazioni sugli avvisi di questo servizio.</span><span class="sxs-lookup"><span data-stu-id="acf59-103">The SQL Server Agent **Alerts** performance object contains performance counters that report information about SQL Server Agent alerts.</span></span> <span data-ttu-id="acf59-104">Nella tabella seguente sono elencati i contatori inclusi nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="acf59-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="acf59-105">Nella tabella seguente sono elencati i contatori **SQLAgent:Avvisi** .</span><span class="sxs-lookup"><span data-stu-id="acf59-105">The table below contains the **SQLAgent:Alerts** counters.</span></span>  
  
|<span data-ttu-id="acf59-106">Nome</span><span class="sxs-lookup"><span data-stu-id="acf59-106">Name</span></span>|<span data-ttu-id="acf59-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="acf59-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="acf59-108">**Avvisi attivati**</span><span class="sxs-lookup"><span data-stu-id="acf59-108">**Activated alerts**</span></span>|<span data-ttu-id="acf59-109">Questo contatore indica il numero totale di avvisi attivati da SQL Server Agent dopo l'ultimo riavvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="acf59-109">This counter reports the total number of alerts that SQL Server Agent has activated since the last time that SQL Server Agent restarted.</span></span>|  
|<span data-ttu-id="acf59-110">**Avvisi attivati/minuto**</span><span class="sxs-lookup"><span data-stu-id="acf59-110">**Alerts activated/minute**</span></span>|<span data-ttu-id="acf59-111">Questo contatore indica il numero di avvisi attivati da SQL Server Agent nell'ultimo minuto.</span><span class="sxs-lookup"><span data-stu-id="acf59-111">This counter reports the number of alerts that SQL Server Agent activated within the last minute.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="acf59-112">Per usare questo oggetto di SQL Server Agent, è necessario che gli utenti siano membri del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="acf59-112">To use this SQL Server Agent object, users must be a member of the **sysadmin** fixed server role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf59-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acf59-113">See Also</span></span>  
 <span data-ttu-id="acf59-114">[Avvisi](../../ssms/agent/alerts.md) </span><span class="sxs-lookup"><span data-stu-id="acf59-114">[Alerts](../../ssms/agent/alerts.md) </span></span>  
 <span data-ttu-id="acf59-115">[Utilizzo degli oggetti prestazioni](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="acf59-115">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="acf59-116">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="acf59-116">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
