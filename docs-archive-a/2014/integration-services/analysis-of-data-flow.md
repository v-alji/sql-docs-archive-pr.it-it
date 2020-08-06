---
title: Analisi del flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5654cb30-cad2-470c-97b3-59cb331033e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 184b53d3e982cd80d7c9c0909538a751585ae21d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626234"
---
# <a name="analysis-of-data-flow"></a><span data-ttu-id="795cf-102">Analisi del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="795cf-102">Analysis of Data Flow</span></span>
  <span data-ttu-id="795cf-103">È possibile utilizzare la vista [catalog.execution_data_statistics](../relational-databases/statistics/statistics.md) `SSISDB` database per analizzare il flusso di dati dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="795cf-103">You can use the [catalog.execution_data_statistics](../relational-databases/statistics/statistics.md)`SSISDB` database view to analyze the data flow of packages.</span></span> <span data-ttu-id="795cf-104">In questa vista viene visualizzata una riga ogni volta che un componente del flusso di dati invia dati a un componente a valle.</span><span class="sxs-lookup"><span data-stu-id="795cf-104">This view displays a row each time a data flow component sends data to a downstream component.</span></span> <span data-ttu-id="795cf-105">Le informazioni possono essere utilizzate per acquisire una comprensione più approfondita delle righe inviate a ciascun componente.</span><span class="sxs-lookup"><span data-stu-id="795cf-105">The information can be used to gain a deeper understanding of the rows that are sent to each component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="795cf-106">Il livello di registrazione deve essere impostato su **Dettagliato** per acquisire informazioni con la vista catalog.execution_data_statistics.</span><span class="sxs-lookup"><span data-stu-id="795cf-106">The logging level must be set to **Verbose** in order to capture information with the catalog.execution_data_statistics view.</span></span>  
  
 <span data-ttu-id="795cf-107">Nell'esempio seguente viene visualizzato il numero di righe inviate tra i componenti di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="795cf-107">The following example displays the number of rows sent between components of a package.</span></span>  
  
```  
use SSISDB  
select package_name, task_name, source_component_name, destination_component_name, rows_sent  
from catalog.execution_data_statistics  
where execution_id = 132  
order by source_component_name, destination_component_name  
  
```  
  
 <span data-ttu-id="795cf-108">Nell'esempio seguente viene calcolato il numero di righe per millisecondi inviate da ogni componente per un'esecuzione specifica.</span><span class="sxs-lookup"><span data-stu-id="795cf-108">The following example calculates the number of rows per millisecond sent by each component for a specific execution.</span></span> <span data-ttu-id="795cf-109">I valori calcolati sono:</span><span class="sxs-lookup"><span data-stu-id="795cf-109">The calculated values are:</span></span>  
  
-   <span data-ttu-id="795cf-110">**total_rows** : somma di tutte le righe inviate dal componente</span><span class="sxs-lookup"><span data-stu-id="795cf-110">**total_rows** - the sum of all the rows sent by the component</span></span>  
  
-   <span data-ttu-id="795cf-111">**wall_clock_time_ms**: tempo totale di esecuzione trascorso, in millisecondi, per ogni componente</span><span class="sxs-lookup"><span data-stu-id="795cf-111">**wall_clock_time_ms** - the total elapsed execution time, in milliseconds, for each component</span></span>  
  
-   <span data-ttu-id="795cf-112">**num_rows_per_millisecond**: numero di righe per millisecondi inviate da ogni componente</span><span class="sxs-lookup"><span data-stu-id="795cf-112">**num_rows_per_millisecond** - the number of rows per millisecond sent by each component</span></span>  
  
 <span data-ttu-id="795cf-113">La `HAVING` clausola viene utilizzata per evitare un errore di divisione per zero nei calcoli.</span><span class="sxs-lookup"><span data-stu-id="795cf-113">The `HAVING` clause is used to prevent a divide-by-zero error in the calculations.</span></span>  
  
```  
use SSISDB  
select source_component_name, destination_component_name,  
    sum(rows_sent) as total_rows,  
    DATEDIFF(ms,min(created_time),max(created_time)) as wall_clock_time_ms,  
    ((0.0+sum(rows_sent)) / (datediff(ms,min(created_time),max(created_time)))) as [num_rows_per_millisecond]  
from [catalog].[execution_data_statistics]  
where execution_id = 132  
group by source_component_name, destination_component_name  
having (datediff(ms,min(created_time),max(created_time))) > 0  
order by source_component_name desc  
  
```  
  
## <a name="related-tasks"></a><span data-ttu-id="795cf-114">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="795cf-114">Related Tasks</span></span>  
 [<span data-ttu-id="795cf-115">Debug di un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="795cf-115">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
 [<span data-ttu-id="795cf-116">Strumenti per la risoluzione dei problemi relativi all'esecuzione dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="795cf-116">Troubleshooting Tools for Package Execution</span></span>](troubleshooting/troubleshooting-tools-for-package-execution.md)  
  
## <a name="see-also"></a><span data-ttu-id="795cf-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="795cf-117">See Also</span></span>  
 [<span data-ttu-id="795cf-118">Dati nei flussi di dati</span><span class="sxs-lookup"><span data-stu-id="795cf-118">Data in Data Flows</span></span>](data-flow/data-in-data-flows.md)  
  
  
