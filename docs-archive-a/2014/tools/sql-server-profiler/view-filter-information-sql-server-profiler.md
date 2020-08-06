---
title: Visualizzare le informazioni sui filtri (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- displaying filter information
- filters [SQL Server], viewing
- filters [SQL Server], traces
- traces [SQL Server], filters
- viewing filter information
ms.assetid: 8d002dea-376a-452c-b3ca-3e93656ed75f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 931b83f8087d446cfc7b08d9582cbad5b02cf671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626442"
---
# <a name="view-filter-information-sql-server-profiler"></a><span data-ttu-id="e04f6-102">Visualizzare informazioni sui filtri (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="e04f6-102">View Filter Information (SQL Server Profiler)</span></span>
  <span data-ttu-id="e04f6-103">In questo argomento viene descritto come visualizzare i filtri impostati sulle colonne di dati per le classi di evento utilizzando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e04f6-103">This topic describes how to view filters on data columns for event classes by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-view-filter-information"></a><span data-ttu-id="e04f6-104">Per visualizzare informazioni sui filtri</span><span class="sxs-lookup"><span data-stu-id="e04f6-104">To view filter information</span></span>  
  
1.  <span data-ttu-id="e04f6-105">Aprire un file di traccia, una tabella di traccia o uno script SQL e scegliere **Proprietà** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="e04f6-105">Open a trace file, trace table, or SQL script, and on the **File** menu, click **Properties**.</span></span> <span data-ttu-id="e04f6-106">Se si intende modificare un modello di traccia o creare una nuova traccia, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="e04f6-106">If you are editing a trace template or creating a new trace, skip this step.</span></span>  
  
2.  <span data-ttu-id="e04f6-107">Nella scheda **Selezione eventi** fare clic con il pulsante destro del mouse sul nome della colonna di dati relativa al filtro da visualizzare e scegliere **Modifica filtro colonne**.</span><span class="sxs-lookup"><span data-stu-id="e04f6-107">On the **Events Selection** tab, right-click the data column name for the filter you want to view, and click **Edit Column Filter**.</span></span>  
  
3.  <span data-ttu-id="e04f6-108">Nella finestra di dialogo **Modifica filtro** espandere gli operatori di confronto del filtro per visualizzare il valore assegnato al criterio specificato.</span><span class="sxs-lookup"><span data-stu-id="e04f6-108">In the **Edit Filter** dialog box, expand the filter comparison operators to see the assigned value for the specified criterion.</span></span> <span data-ttu-id="e04f6-109">Ripetere i passaggi 2 e 3 per tutte le colonne per le quali si desidera visualizzare le informazioni sui filtri.</span><span class="sxs-lookup"><span data-stu-id="e04f6-109">Repeat Steps 2 and 3 for all columns for which you want to view filter information.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e04f6-110">Gli operatori di confronto per i quali sono disponibili valori assegnati sono formattati in grassetto.</span><span class="sxs-lookup"><span data-stu-id="e04f6-110">Comparison operators with assigned values are formatted bold.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e04f6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e04f6-111">See Also</span></span>  
 [<span data-ttu-id="e04f6-112">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="e04f6-112">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
