---
title: Monitoraggio attività | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Activity Monitor [SQL Server]
ms.assetid: 1e6c430d-3a2a-468e-a3d5-ef5459c36c15
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 71fd0d1172b4fcd5739a3af1a60246cc7dce3b93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723735"
---
# <a name="activity-monitor"></a><span data-ttu-id="a848d-102">Monitoraggio attività</span><span class="sxs-lookup"><span data-stu-id="a848d-102">Activity Monitor</span></span>
  <span data-ttu-id="a848d-103">Monitoraggio attività consente di visualizzare informazioni sui processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e sul modo in cui questi processi influiscono sull'istanza corrente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a848d-103">Activity Monitor displays information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes and how these processes affect the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="benefits-of-activity-monitor"></a><span data-ttu-id="a848d-104">Vantaggi di Monitoraggio attività</span><span class="sxs-lookup"><span data-stu-id="a848d-104">Benefits of Activity Monitor</span></span>  
 <span data-ttu-id="a848d-105">Monitoraggio attività è una finestra di documento a schede con i riquadri espandibili e comprimibili seguenti: **Panoramica**, **attività utente attive**, **attese risorse**, **i/O file di dati**e **query recenti con costo elevato**.</span><span class="sxs-lookup"><span data-stu-id="a848d-105">Activity Monitor is a tabbed document window that has the following expandable and collapsible panes: **Overview**, **Active User Tasks**, **Resource Waits**, **Data File I/O**, and **Recent Expensive Queries**.</span></span> <span data-ttu-id="a848d-106">Quando un riquadro è espanso, Monitoraggio attività esegue una query sull'istanza per ottenere informazioni.</span><span class="sxs-lookup"><span data-stu-id="a848d-106">When any pane is expanded, Activity Monitor queries the instance for information.</span></span> <span data-ttu-id="a848d-107">Quando un riquadro è compresso, significa che tutte le relative attività di query sono arrestate.</span><span class="sxs-lookup"><span data-stu-id="a848d-107">When a pane is collapsed, all querying activity stops for that pane.</span></span> <span data-ttu-id="a848d-108">È anche possibile espandere uno o più riquadri contemporaneamente per visualizzare diversi tipi di attività sull'istanza.</span><span class="sxs-lookup"><span data-stu-id="a848d-108">You can also expand one or more panes at the same time to view different kinds of activity on the instance.</span></span>  
  
 <span data-ttu-id="a848d-109">Per le colonne incluse nei riquadri **attività utente attive**, **attese risorse**, **i/O file di dati**e **query recenti con costo elevato** , è possibile personalizzare la visualizzazione nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a848d-109">For the columns that are included in the **Active User Tasks**, **Resource Waits**, **Data File I/O**, and **Recent Expensive Queries** panes, you can customize the display in the following ways:</span></span>  
  
1.  <span data-ttu-id="a848d-110">Per ridisporre l'ordine delle colonne, fare clic sull'intestazione di colonna e trascinarla in un altro punto della barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="a848d-110">To rearrange the order of the columns, click the column heading and drag it to another location in the heading ribbon.</span></span>  
  
2.  <span data-ttu-id="a848d-111">Per ordinare una colonna, fare clic sul relativo nome.</span><span class="sxs-lookup"><span data-stu-id="a848d-111">To sort a column, click the column name.</span></span>  
  
3.  <span data-ttu-id="a848d-112">Per applicare un filtro in base a una o più colonne, fare clic sulla freccia a discesa nell'intestazione della colonna, quindi selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a848d-112">To filter on one or more columns, click the drop-down arrow in the column heading, and then select a value.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a848d-113">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="a848d-113">Related Tasks</span></span>  
 <span data-ttu-id="a848d-114">Per un'introduzione a Monitoraggio attività, utilizzare le attività riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="a848d-114">Use the following tasks to get started with Activity Monitor:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a848d-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a848d-115">**Description**</span></span>|<span data-ttu-id="a848d-116">**Argomento**</span><span class="sxs-lookup"><span data-stu-id="a848d-116">**Topic**</span></span>|  
|<span data-ttu-id="a848d-117">Viene descritto come aprire Monitoraggio attività e come impostare l'intervallo di aggiornamento di Monitoraggio attività.</span><span class="sxs-lookup"><span data-stu-id="a848d-117">Describes how to open Activity Monitor and how to set the Activity Monitor refresh interval.</span></span>|[<span data-ttu-id="a848d-118">Aprire Monitoraggio attività &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a848d-118">Open Activity Monitor &#40;SQL Server Management Studio&#41;</span></span>](../performance-monitor/open-activity-monitor-sql-server-management-studio.md)|  
|<span data-ttu-id="a848d-119">Collegamenti agli argomenti relativi alle prestazioni del server e al monitoraggio delle attività.</span><span class="sxs-lookup"><span data-stu-id="a848d-119">Links to topics for server performance and activity monitoring.</span></span>|[<span data-ttu-id="a848d-120">Monitoraggio delle prestazioni e dell'attività del server</span><span class="sxs-lookup"><span data-stu-id="a848d-120">Server Performance and Activity Monitoring</span></span>](../performance/server-performance-and-activity-monitoring.md)|  
  
  
