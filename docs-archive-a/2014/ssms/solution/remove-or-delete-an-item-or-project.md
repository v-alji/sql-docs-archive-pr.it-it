---
title: Rimuovere o eliminare un elemento o un progetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting project items
- projects [SQL Server Management Studio], item removal
- removing project items
ms.assetid: 3fd92434-70f5-466e-bef0-7e0fd73ddb1c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 679911f15d6c47f4274180602a5376c4ec03c77b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627019"
---
# <a name="remove-or-delete-an-item-or-project"></a><span data-ttu-id="b9066-102">Rimozione o eliminazione di un elemento o di un progetto</span><span class="sxs-lookup"><span data-stu-id="b9066-102">Remove or Delete an Item or Project</span></span>
  <span data-ttu-id="b9066-103">Gli elementi nei progetti di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] sono query, connessioni e file esterni.</span><span class="sxs-lookup"><span data-stu-id="b9066-103">Project items in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] projects are Queries, Connections, and Miscellaneous files.</span></span> <span data-ttu-id="b9066-104">È possibile rimuovere dalla soluzione query di progetto e file esterni senza cancellare i file dall'archivio.</span><span class="sxs-lookup"><span data-stu-id="b9066-104">You can remove project queries and miscellaneous files from your solution without erasing the files from storage.</span></span> <span data-ttu-id="b9066-105">Rimuovere un progetto o un elemento quando non è utile nella soluzione corrente, ma si desidera includerlo in un'altra soluzione.</span><span class="sxs-lookup"><span data-stu-id="b9066-105">Remove a project or item when it is not useful in the current solution but you want to include it in another solution.</span></span>  
  
### <a name="to-remove-a-project-item"></a><span data-ttu-id="b9066-106">Per rimuovere un elemento di progetto</span><span class="sxs-lookup"><span data-stu-id="b9066-106">To remove a project item</span></span>  
  
1.  <span data-ttu-id="b9066-107">In Esplora soluzioni selezionare l'elemento del progetto che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="b9066-107">In Solution Explorer, select the project item you want to remove.</span></span>  
  
2.  <span data-ttu-id="b9066-108">Scegliere **Rimuovi** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b9066-108">On the **Edit** menu, click **Remove**.</span></span>  
  
3.  <span data-ttu-id="b9066-109">Nella finestra di conferma fare clic su **Rimuovi** per rimuovere l'elemento dal progetto.</span><span class="sxs-lookup"><span data-stu-id="b9066-109">On the confirmation dialog, click **Remove** to remove the item from the project.</span></span>  
  
 <span data-ttu-id="b9066-110">Un elemento rimosso rimane comunque nel file system.</span><span class="sxs-lookup"><span data-stu-id="b9066-110">A removed item still exists on the file system.</span></span> <span data-ttu-id="b9066-111">È pertanto possibile aggiungerlo alla soluzione originale o a un'altra soluzione.</span><span class="sxs-lookup"><span data-stu-id="b9066-111">Therefore, you can add a removed item to its original solution or to another solution.</span></span>  
  
#### <a name="to-remove-a-project"></a><span data-ttu-id="b9066-112">Per rimuovere un progetto</span><span class="sxs-lookup"><span data-stu-id="b9066-112">To remove a project</span></span>  
  
1.  <span data-ttu-id="b9066-113">In Esplora soluzioni selezionare il progetto che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="b9066-113">In Solution Explorer, select the project you want to remove.</span></span>  
  
2.  <span data-ttu-id="b9066-114">Scegliere **Rimuovi** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b9066-114">On the **Edit** menu, click **Remove**.</span></span>  
  
3.  <span data-ttu-id="b9066-115">Nella finestra di conferma fare clic su **OK**per rimuovere il progetto dalla soluzione.</span><span class="sxs-lookup"><span data-stu-id="b9066-115">On the confirmation dialog, click **OK**, to remove the project from the solution.</span></span>  
  
 <span data-ttu-id="b9066-116">È possibile eliminare un progetto in modo definitivo. In questo caso è necessario prima rimuovere dalle soluzioni di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tutti i riferimenti al progetto e quindi utilizzare Esplora risorse di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows per eliminare definitivamente i file associati dall'archivio.</span><span class="sxs-lookup"><span data-stu-id="b9066-116">You can delete a project permanently, but you first need to remove any references to the project from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solutions, and then use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Explorer to permanently delete the associated files from storage.</span></span>  
  
#### <a name="to-delete-a-project"></a><span data-ttu-id="b9066-117">Per eliminare un progetto</span><span class="sxs-lookup"><span data-stu-id="b9066-117">To delete a project</span></span>  
  
1.  <span data-ttu-id="b9066-118">In Esplora soluzioni rimuovere dalla soluzione il progetto che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="b9066-118">In Solution Explorer, remove the project you want to delete from the solution.</span></span>  
  
2.  <span data-ttu-id="b9066-119">In Esplora risorse individuare e selezionare i file associati al progetto o all'elemento da eliminare.</span><span class="sxs-lookup"><span data-stu-id="b9066-119">In Windows Explorer, locate and select the files associated with the project or item you want to delete.</span></span>  
  
3.  <span data-ttu-id="b9066-120">Scegliere **Elimina** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="b9066-120">On the **File** menu, click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9066-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9066-121">See Also</span></span>  
 <span data-ttu-id="b9066-122">[Esplora soluzioni](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="b9066-122">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="b9066-123">[Aggiungere nuovi elementi a un progetto](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="b9066-123">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="b9066-124">Aggiungere elementi esistenti a un progetto</span><span class="sxs-lookup"><span data-stu-id="b9066-124">Add Existing Items to a Project</span></span>](add-existing-items-to-a-project.md)  
  
  
