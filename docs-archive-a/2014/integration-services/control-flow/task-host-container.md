---
title: Contenitore Host delle attività | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.taskhostcontainer.f1
helpviewer_keywords:
- containers [Integration Services], Task Host
- Task Host container
ms.assetid: 7394a2c2-1b07-427d-b94a-9792e7783d35
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4429d564cea0f08d5c2408199a8f1837b38389b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636333"
---
# <a name="task-host-container"></a><span data-ttu-id="02536-102">Host delle attività - contenitore</span><span class="sxs-lookup"><span data-stu-id="02536-102">Task Host Container</span></span>
  <span data-ttu-id="02536-103">Il contenitore host delle attività incapsula una singola attività.</span><span class="sxs-lookup"><span data-stu-id="02536-103">The task host container encapsulates a single task.</span></span> <span data-ttu-id="02536-104">In Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] il contenitore host delle attività non viene configurato separatamente, ma viene configurato quando si impostano le proprietà dell'attività incapsulata.</span><span class="sxs-lookup"><span data-stu-id="02536-104">In [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the task host is not configured separately; instead, it is configured when you set the properties of the task it encapsulates.</span></span> <span data-ttu-id="02536-105">Per altre informazioni sulle attività incapsulate nel contenitore Host delle attività, vedere [Attività di Integration Services](integration-services-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="02536-105">For more information about the tasks that the task host containers encapsulate, see [Integration Services Tasks](integration-services-tasks.md).</span></span>  
  
 <span data-ttu-id="02536-106">Questo contenitore estende al livello delle attività l'utilizzo di gestori di eventi e variabili.</span><span class="sxs-lookup"><span data-stu-id="02536-106">This container extends the use of variables and event handlers to the task level.</span></span> <span data-ttu-id="02536-107">Per altre informazioni, vedere [Gestori eventi di Integration Services &#40;SSIS&#41;](../integration-services-ssis-event-handlers.md) e [Variabili di Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="02536-107">For more information, see [Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) and [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md).</span></span>  
  
## <a name="configuration-of-the-task-host"></a><span data-ttu-id="02536-108">Configurazione dell'Host attività</span><span class="sxs-lookup"><span data-stu-id="02536-108">Configuration of the Task Host</span></span>  
 <span data-ttu-id="02536-109">È possibile impostare le proprietà a livello di codice o nella finestra **Proprietà** di [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02536-109">You can set properties in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or programmatically.</span></span>  
  
 <span data-ttu-id="02536-110">Per informazioni sull'impostazione di queste proprietà in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], vedere [Impostazione delle proprietà di un'attività o di un contenitore](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="02536-110">For information about setting these properties in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
 <span data-ttu-id="02536-111">Per informazioni sull'impostazione di queste proprietà a livello di codice, vedere <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="02536-111">For information about programmatically setting these properties, see <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="02536-112">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="02536-112">Related Tasks</span></span>  
  
-   [<span data-ttu-id="02536-113">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="02536-113">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="02536-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02536-114">See Also</span></span>  
 [<span data-ttu-id="02536-115">Contenitori in Integration Services</span><span class="sxs-lookup"><span data-stu-id="02536-115">Integration Services Containers</span></span>](integration-services-containers.md)  
  
  
