---
title: Modifica della posizione di un punto di interruzione
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint location
ms.assetid: 5c28e411-0377-4210-a7ce-2a5c13dcdf74
author: rothja
ms.author: jroth
ms.openlocfilehash: 919e62d53d5c9e8898bf1d49c4b5e5aa4c0ed107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623120"
---
# <a name="edit-a-breakpoint-location"></a><span data-ttu-id="65c51-102">Modifica della posizione di un punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="65c51-102">Edit a Breakpoint Location</span></span>
  <span data-ttu-id="65c51-103">La posizione del punto di interruzione specifica la riga e il carattere in cui si trova il punto di interruzione in un file di script [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65c51-103">The breakpoint location specifies the line and character where the breakpoint resides in a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="65c51-104">È possibile modificare la posizione del punto di interruzione per spostare il punto di interruzione in un'altra posizione nello script o in uno script diverso.</span><span class="sxs-lookup"><span data-stu-id="65c51-104">You can edit the breakpoint location to move the breakpoint to another location in the script, or to a different script.</span></span>  
  
## <a name="editing-a-location"></a><span data-ttu-id="65c51-105">Modifica di una posizione</span><span class="sxs-lookup"><span data-stu-id="65c51-105">Editing a Location</span></span>  
 <span data-ttu-id="65c51-106">Quando si modifica la posizione di un punto di interruzione, il punto di interruzione viene spostato nella nuova posizione, insieme a tutte le proprietà esistenti, ad esempio un numero di passaggi o una condizione.</span><span class="sxs-lookup"><span data-stu-id="65c51-106">When you edit a breakpoint location, the breakpoint moves to the new location, carrying with it all of the existing properties, such as a hit count or condition.</span></span>  
  
#### <a name="to-edit-a-breakpoint-location"></a><span data-ttu-id="65c51-107">Per modificare la posizione di un punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="65c51-107">To Edit a Breakpoint Location</span></span>  
  
1.  <span data-ttu-id="65c51-108">Nella finestra dell'editor fare clic con il pulsante destro del mouse sul glifo del punto di interruzione, quindi scegliere **Posizione** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="65c51-108">In the editor window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="65c51-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="65c51-109">-or-</span></span>  
  
     <span data-ttu-id="65c51-110">Nella finestra **Punti di interruzione** fare clic con il pulsante destro del mouse sul glifo del punto di interruzione e quindi scegliere **Posizione** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="65c51-110">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="65c51-111">Nella finestra di dialogo **Punto di interruzione del file** modificare **File** per specificare un nuovo file, **Riga** per specificare una nuova riga o **Carattere** per specificare una nuova posizione all'interno della riga.</span><span class="sxs-lookup"><span data-stu-id="65c51-111">In the **File Breakpoint** dialog box, edit **File** to specify a new file, **Line** to specify a new line, or **Character** to specify a new location within the line.</span></span> <span data-ttu-id="65c51-112">Se il nuovo file specificato è già aperto in una finestra dell'editor di query, il punto di interruzione viene spostato in tale finestra.</span><span class="sxs-lookup"><span data-stu-id="65c51-112">If the new file you specify is already open in a query editor window, the breakpoint is moved to that editor window.</span></span> <span data-ttu-id="65c51-113">Se il file non è aperto, viene aperta una nuova finestra dell'editor, il file viene caricato e il punto di interruzione viene spostato nella nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="65c51-113">If the file is not opened, a new editor window is opened, the file is loaded in, and the breakpoint moved to the new location.</span></span>  
  
     <span data-ttu-id="65c51-114">L'opzione **Il codice sorgente può essere diverso dalla versione originale** non ha effetto nel caso di debug di [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65c51-114">The **Allow the source code to be different from the original version** option has no effect when debugging [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c51-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65c51-115">See Also</span></span>  
 <span data-ttu-id="65c51-116">[Specificare un numero di passaggi](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="65c51-116">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 <span data-ttu-id="65c51-117">[Specificare un'azione del punto di interruzione](specify-a-breakpoint-action.md) </span><span class="sxs-lookup"><span data-stu-id="65c51-117">[Specify a Breakpoint Action](specify-a-breakpoint-action.md) </span></span>  
 <span data-ttu-id="65c51-118">[Specificare una condizione del punto di interruzione](specify-a-breakpoint-condition.md) </span><span class="sxs-lookup"><span data-stu-id="65c51-118">[Specify a Breakpoint Condition](specify-a-breakpoint-condition.md) </span></span>  
 [<span data-ttu-id="65c51-119">Specificare un filtro per un punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="65c51-119">Specify a Breakpoint Filter</span></span>](specify-a-breakpoint-filter.md)  
