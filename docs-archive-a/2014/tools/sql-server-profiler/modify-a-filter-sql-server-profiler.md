---
title: Modificare un filtro (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], modifying
- modifying filters, modifying
- filters [SQL Server], traces
ms.assetid: 8b317813-4918-4485-b930-77b1951aa00c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5a7bab18952820a3dc49c9479797a411521f8e71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627589"
---
# <a name="modify-a-filter-sql-server-profiler"></a><span data-ttu-id="1a114-102">Modificare un filtro (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="1a114-102">Modify a Filter (SQL Server Profiler)</span></span>
  <span data-ttu-id="1a114-103">Per limitare il numero di eventi raccolti da una traccia, è possibile aggiungere filtri ai modelli di traccia che contengono le definizioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="1a114-103">You add filters to trace templates, which contain the trace definitions, to limit the number of events that are gathered by a trace.</span></span> <span data-ttu-id="1a114-104">La limitazione del numero di eventi raccolti può ridurre gli effetti negativi delle operazioni di traccia sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="1a114-104">Limiting the number of events gathered can reduce the performance effects of tracing.</span></span> <span data-ttu-id="1a114-105">Se si impostano filtri per un modello di traccia e si rileva che il tipo di informazioni raccolte nella traccia non corrisponde a quello desiderato, è possibile modificare il filtro.</span><span class="sxs-lookup"><span data-stu-id="1a114-105">If you set filters for a trace template and find that the trace is not gathering the kind of information that you need, you can edit the filter.</span></span>  
  
### <a name="to-modify-a-filter"></a><span data-ttu-id="1a114-106">Per modificare un filtro</span><span class="sxs-lookup"><span data-stu-id="1a114-106">To modify a filter</span></span>  
  
1.  <span data-ttu-id="1a114-107">In [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]aprire il modello del filtro di traccia da modificare.</span><span class="sxs-lookup"><span data-stu-id="1a114-107">In [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], open the template for the trace filter that you want to modify.</span></span> <span data-ttu-id="1a114-108">Scegliere **Modelli** dal menu **File**e quindi fare clic su **Modifica modello**.</span><span class="sxs-lookup"><span data-stu-id="1a114-108">On the **File** menu, click **Templates**, and then choose **Edit Template**.</span></span>  
  
2.  <span data-ttu-id="1a114-109">Nella scheda **Generale** della finestra di dialogo **Proprietà modello di traccia** selezionare un modello nell'elenco **Seleziona nome modello** .</span><span class="sxs-lookup"><span data-stu-id="1a114-109">In the **General** tab of the **Trace Template Properties** dialog, select a template from the **Select template name** list.</span></span>  
  
3.  <span data-ttu-id="1a114-110">Fare clic sulla scheda **Selezione eventi** .</span><span class="sxs-lookup"><span data-stu-id="1a114-110">Click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="1a114-111">La scheda **Selezione eventi** contiene un controllo griglia,</span><span class="sxs-lookup"><span data-stu-id="1a114-111">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="1a114-112">ovvero una tabella che include tutte le classi di evento tracciabili.</span><span class="sxs-lookup"><span data-stu-id="1a114-112">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="1a114-113">La tabella contiene una riga per ogni classe di evento.</span><span class="sxs-lookup"><span data-stu-id="1a114-113">The table contains one row for each event class.</span></span> <span data-ttu-id="1a114-114">Le classi di evento possono differire leggermente a seconda del tipo e della versione del server cui si è connessi.</span><span class="sxs-lookup"><span data-stu-id="1a114-114">The event classes may differ slightly, depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="1a114-115">Le classi di eventi sono identificate nella colonna **Eventi**della griglia e sono raggruppate per categoria di eventi.</span><span class="sxs-lookup"><span data-stu-id="1a114-115">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="1a114-116">Nelle altre colonne sono elencate le colonne di dati che possono essere restituite per ogni classe di evento.</span><span class="sxs-lookup"><span data-stu-id="1a114-116">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
4.  <span data-ttu-id="1a114-117">Fare clic su **Filtri colonne**.</span><span class="sxs-lookup"><span data-stu-id="1a114-117">Click **Column Filters**.</span></span>  
  
5.  <span data-ttu-id="1a114-118">Nella finestra di dialogo **Modifica filtro** fare clic sul valore accanto all'operatore di confronto da modificare e digitare il nuovo valore oppure eliminarne uno.</span><span class="sxs-lookup"><span data-stu-id="1a114-118">In the **Edit Filter** dialog box, click the value next to the comparison operator that you want to edit, and type the new value or delete a value.</span></span> <span data-ttu-id="1a114-119">È inoltre possibile aggiungere ulteriori filtri.</span><span class="sxs-lookup"><span data-stu-id="1a114-119">You can also add additional filters.</span></span>  
  
6.  <span data-ttu-id="1a114-120">Fare clic su **OK** e salvare il modello.</span><span class="sxs-lookup"><span data-stu-id="1a114-120">Click **OK** and save the template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a114-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a114-121">See Also</span></span>  
 [<span data-ttu-id="1a114-122">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1a114-122">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
