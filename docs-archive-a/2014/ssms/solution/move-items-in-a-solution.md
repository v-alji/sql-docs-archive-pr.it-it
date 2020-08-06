---
title: Spostare elementi in una soluzione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- moving items
- solutions [SQL Server Management Studio], item relocation
- relocating items
ms.assetid: b40a24eb-f528-4e70-b26e-5eaf6e0ed1ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: fd0a8a89686c62b4d4d00aea5479bb956fe3011f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714971"
---
# <a name="move-items-in-a-solution"></a><span data-ttu-id="c6448-102">Spostare elementi in una soluzione</span><span class="sxs-lookup"><span data-stu-id="c6448-102">Move Items in a Solution</span></span>
  <span data-ttu-id="c6448-103">Gli elementi nei progetti di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] sono query, connessioni e file esterni.</span><span class="sxs-lookup"><span data-stu-id="c6448-103">Project items in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] projects are Queries, Connections, and Miscellaneous files.</span></span> <span data-ttu-id="c6448-104">In Esplora soluzioni è possibile spostare query e file esterni tra progetti, mentre le connessioni non possono essere spostate.</span><span class="sxs-lookup"><span data-stu-id="c6448-104">You can move Queries and Miscellaneous Files between projects in Solution Explorer, but Connections cannot be moved.</span></span>  
  
### <a name="to-move-items-in-solution-explorer"></a><span data-ttu-id="c6448-105">Per spostare elementi in Esplora soluzioni</span><span class="sxs-lookup"><span data-stu-id="c6448-105">To move items in Solution Explorer</span></span>  
  
1.  <span data-ttu-id="c6448-106">In Esplora soluzioni selezionare l'elemento che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="c6448-106">In Solution Explorer, select the item you want to move.</span></span>  
  
2.  <span data-ttu-id="c6448-107">Scegliere **Taglia** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c6448-107">On the **Edit** menu, click **Cut**.</span></span>  
  
3.  <span data-ttu-id="c6448-108">Sempre in Esplora soluzioni selezionare la destinazione.</span><span class="sxs-lookup"><span data-stu-id="c6448-108">In Solution Explorer, select the destination.</span></span>  
  
4.  <span data-ttu-id="c6448-109">Scegliere **Incolla** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c6448-109">On the **Edit** menu, click **Paste**.</span></span>  
  
 <span data-ttu-id="c6448-110">È possibile spostare elementi trascinando query e file esterni in Esplora soluzioni</span><span class="sxs-lookup"><span data-stu-id="c6448-110">You can move items by dragging Query and Miscellaneous files within Solution Explorer.</span></span> <span data-ttu-id="c6448-111">e visualizzare il risultato dell'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="c6448-111">Dragging allows you to see the outcome of the drag operation.</span></span> <span data-ttu-id="c6448-112">Se si spostano query da un tipo di progetto a un altro, è possibile che tali query vengano considerate file esterni nel progetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c6448-112">Moving queries from one project type to another may cause queries to be considered as miscellaneous files in the target project.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6448-113">Quando si sposta una query connessa, la connessione al progetto di destinazione non viene spostata,</span><span class="sxs-lookup"><span data-stu-id="c6448-113">Moving a connected query does not move the connection to the target project.</span></span> <span data-ttu-id="c6448-114">quindi la query perderà la connessione dopo essere stata spostata nel progetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c6448-114">The query will lose its connection after it is moved to the target project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6448-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6448-115">See Also</span></span>  
 <span data-ttu-id="c6448-116">[Esplora soluzioni](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="c6448-116">[Solution Explorer](solution-explorer.md) </span></span>  
 [<span data-ttu-id="c6448-117">Copiare elementi in una soluzione</span><span class="sxs-lookup"><span data-stu-id="c6448-117">Copy Items in a Solution</span></span>](copy-items-in-a-solution.md)  
  
  
