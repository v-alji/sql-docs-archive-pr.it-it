---
title: Impostazione di un filtro per un punto di interruzione
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint filter
ms.assetid: 7bf1dddd-7b0b-4c47-8a7b-28a5569b4fa5
author: rothja
ms.author: jroth
ms.openlocfilehash: 9fc320397da1bddc0d28191c359c4d311b23e044
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629326"
---
# <a name="specify-a-breakpoint-filter"></a><span data-ttu-id="7d835-102">Impostazione di un filtro per un punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="7d835-102">Specify a Breakpoint Filter</span></span>
  <span data-ttu-id="7d835-103">Un filtro per un punto di interruzione limita il punto di interruzione in modo che agisca solo su computer o processi e thread del sistema operativo specificati.</span><span class="sxs-lookup"><span data-stu-id="7d835-103">A breakpoint filter limits the breakpoint to acting only on specified computers, operating system processes, and threads.</span></span> <span data-ttu-id="7d835-104">I filtri per i punti di interruzione vengono in genere utilizzati per il debug di applicazioni parallele.</span><span class="sxs-lookup"><span data-stu-id="7d835-104">Breakpoint filters are typically used when debugging parallel applications.</span></span>  
  
##  <a name="filter-considerations"></a><a name="BKMK_ActionConsiderations"></a> <span data-ttu-id="7d835-105">Considerazioni sui filtri</span><span class="sxs-lookup"><span data-stu-id="7d835-105">Filter Considerations</span></span>  
 <span data-ttu-id="7d835-106">I filtri per i punti di interruzione non vengono in genere utilizzati con il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] perché gli script e le stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] non sono applicazioni parallele.</span><span class="sxs-lookup"><span data-stu-id="7d835-106">Breakpoint filters are not typically used with the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger because [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts and stored procedures are not parallel applications.</span></span>  
  
#### <a name="to-specify-a-breakpoint-filter"></a><span data-ttu-id="7d835-107">Per specificare un filtro per un punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="7d835-107">To Specify a Breakpoint Filter</span></span>  
  
1.  <span data-ttu-id="7d835-108">Nella finestra dell'editor fare clic con il pulsante destro del mouse sul glifo del punto di interruzione, quindi scegliere **Filtro** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="7d835-108">In the editor window, right-click the breakpoint glyph, and then click **Filter** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="7d835-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="7d835-109">-or-</span></span>  
  
     <span data-ttu-id="7d835-110">Nella finestra **Punti di interruzione** fare clic con il pulsante destro del mouse sul glifo del punto di interruzione, quindi scegliere **Filtro** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="7d835-110">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Filter** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="7d835-111">Nella finestra di dialogo **Filtri punti di interruzione** usare la casella **Filtro** per specificare i computer per nome o i processi e i thread del sistema operativo per nome o numero ID:</span><span class="sxs-lookup"><span data-stu-id="7d835-111">In the **Breakpoint Filters** dialog box, use the **Filter** box to specify computers by name, or operating system processes and threads by either name or ID number:</span></span>  
  
    -   <span data-ttu-id="7d835-112">`MachineName` è il computer che esegue l'istanza del Motore di database.</span><span class="sxs-lookup"><span data-stu-id="7d835-112">`MachineName` is the computer running the instance of the Database Engine.</span></span>  
  
    -   <span data-ttu-id="7d835-113">`ProcessID` e `ProcessName` sono relativi al processo del sistema operativo che esegue l'istanza del Motore di database.</span><span class="sxs-lookup"><span data-stu-id="7d835-113">`ProcessID`, and `ProcessName` are the operating system process running the instance of the Database Engine.</span></span>  
  
    -   <span data-ttu-id="7d835-114">`ThreadID` e `ThreadName` sono relativi al thread del sistema operativo che esegue il batch, la procedura o la funzione [!INCLUDE[tsql](../../includes/tsql-md.md)] nell'istanza del Motore di database.</span><span class="sxs-lookup"><span data-stu-id="7d835-114">`ThreadID` and `ThreadName` are the operating system thread running the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, procedure, or function in the instance of the Database Engine.</span></span>  
  
3.  <span data-ttu-id="7d835-115">Fare clic su **OK** per implementare le modifiche o su **Annulla** per uscire senza applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="7d835-115">Click **OK** to implement the changes, or **Cancel** to exit without applying the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d835-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d835-116">See Also</span></span>  
 <span data-ttu-id="7d835-117">[Impostare una condizione del punto di interruzione](specify-a-breakpoint-condition.md) </span><span class="sxs-lookup"><span data-stu-id="7d835-117">[Specify a Breakpoint Condition](specify-a-breakpoint-condition.md) </span></span>  
 <span data-ttu-id="7d835-118">[Specifica di un numero di passaggi](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="7d835-118">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 [<span data-ttu-id="7d835-119">Specificare un'azione del punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="7d835-119">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)  
