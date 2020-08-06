---
title: Elimina elementi catalogo (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.deleteitems.f1
ms.assetid: b0599e01-6dc3-4484-80d4-022a412e0ebd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d2a1824f2611165c9ae891fcb702418244f3621e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627640"
---
# <a name="delete-catalog-items-management-studio"></a><span data-ttu-id="b1e6d-102">Elimina elementi catalogo (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b1e6d-102">Delete Catalog Items (Management Studio)</span></span>
  <span data-ttu-id="b1e6d-103">Questa pagina consente di eliminare pianificazioni condivise e definizioni di ruolo.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-103">Use this page to delete shared schedules and role definitions.</span></span>  
  
 <span data-ttu-id="b1e6d-104">Se si elimina una pianificazione condivisa utilizzata da più report e sottoscrizioni, nel server di report vengono create singole pianificazioni per ogni report e sottoscrizione da cui è stata utilizzata in precedenza la pianificazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-104">If you delete a shared schedule that is used by multiple reports and subscriptions, the report server will create individual schedules for each report and subscription that previously used the shared schedule.</span></span> <span data-ttu-id="b1e6d-105">Ogni nuova pianificazione conterrà la data, l'ora e il criterio di occorrenza specificati nella pianificazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-105">Each new individual schedule will contain the date, time, and recurrence pattern that was specified in the shared schedule.</span></span> <span data-ttu-id="b1e6d-106">Si noti che in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] non è disponibile una funzionalità di gestione centrale delle singole pianificazioni.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-106">Note that [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not provide central management of individual schedules.</span></span> <span data-ttu-id="b1e6d-107">Se si elimina una pianificazione condivisa, è necessario gestire le informazioni sulla pianificazione per ogni singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-107">If you delete a shared schedule, you will now need to maintain the schedule information for each individual item.</span></span> <span data-ttu-id="b1e6d-108">Prima di eliminare una pianificazione condivisa, utilizzare la pagina [Report](schedule-properties-reports-page.md) per verificare i report da cui attualmente viene utilizzata la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-108">Before deleting a shared schedule, use the [Reports page](schedule-properties-reports-page.md) to determine which reports are currently using the shared schedule.</span></span>  
  
 <span data-ttu-id="b1e6d-109">Per le definizioni di ruolo, è possibile eliminare solo le definizioni non attivamente utilizzate in un'assegnazione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-109">For role definitions, you can only delete those that are not actively used in a role assignment.</span></span> <span data-ttu-id="b1e6d-110">Se si tenta di eliminare un ruolo attualmente in uso, tale ruolo non viene eliminato dal server di report e viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-110">If you try to delete a role that is currently in use, the report server will not delete the role and you will see an error message to that effect.</span></span> <span data-ttu-id="b1e6d-111">Se la pagina contiene una singola definizione di ruolo non attualmente in uso, la definizione viene eliminata quando si fa clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-111">If this page contains a single role definition that is not currently in use, it will be deleted when you click **OK**.</span></span> <span data-ttu-id="b1e6d-112">Se la pagina contiene più ruoli, non è possibile selezionare i ruoli da conservare o da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-112">If this page contains multiple roles, you cannot select which roles to keep or remove.</span></span> <span data-ttu-id="b1e6d-113">Facendo clic su **OK**vengono eliminate tutte le definizioni di ruolo non utilizzate.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-113">All unused role definitions will be deleted when you click **OK**.</span></span>  
  
 <span data-ttu-id="b1e6d-114">Non è possibile annullare un'operazione di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-114">You cannot undo a delete operation.</span></span> <span data-ttu-id="b1e6d-115">Se si desidera recuperare un elemento eliminato, è necessario ricrearlo o ripristinare una copia di backup del database del server di report.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-115">If you want to recover an item that you deleted, you must either recreate it or restore a backup copy of the report server database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b1e6d-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b1e6d-116">Options</span></span>  
 <span data-ttu-id="b1e6d-117">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b1e6d-117">**Name**</span></span>  
 <span data-ttu-id="b1e6d-118">Indica il nome dell'elemento che si sta eliminando.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-118">Specifies the name of the item you are deleting.</span></span>  
  
 <span data-ttu-id="b1e6d-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b1e6d-119">**Type**</span></span>  
 <span data-ttu-id="b1e6d-120">Visualizza il tipo di elemento che si sta eliminando.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-120">Shows the type of item you are deleting.</span></span>  
  
 <span data-ttu-id="b1e6d-121">**Proprietario**</span><span class="sxs-lookup"><span data-stu-id="b1e6d-121">**Owner**</span></span>  
 <span data-ttu-id="b1e6d-122">Visualizza il nome del proprietario.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-122">Shows the name of the owner.</span></span> <span data-ttu-id="b1e6d-123">Nella maggior parte dei casi, si tratta di System.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-123">In most cases, this is System.</span></span>  
  
 <span data-ttu-id="b1e6d-124">**Status**</span><span class="sxs-lookup"><span data-stu-id="b1e6d-124">**Status**</span></span>  
 <span data-ttu-id="b1e6d-125">Visualizza le informazioni sullo stato dell'operazione di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-125">Shows progress information for a delete operation.</span></span>  
  
 <span data-ttu-id="b1e6d-126">**Error (Errore) (Error (Errore)e)**</span><span class="sxs-lookup"><span data-stu-id="b1e6d-126">**Error**</span></span>  
 <span data-ttu-id="b1e6d-127">Visualizza un codice se si verifica un errore durante l'eliminazione di un elemento.</span><span class="sxs-lookup"><span data-stu-id="b1e6d-127">Displays an error code if an error occurs while deleting an item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e6d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1e6d-128">See Also</span></span>  
 <span data-ttu-id="b1e6d-129">[Eliminare un elemento &#40;Management Studio&#41;](delete-an-item-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b1e6d-129">[Delete an Item &#40;Management Studio&#41;](delete-an-item-management-studio.md) </span></span>  
 <span data-ttu-id="b1e6d-130">[Guida sensibile al contesto del server di report in Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="b1e6d-130">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="b1e6d-131">Creare, modificare ed eliminare pianificazioni</span><span class="sxs-lookup"><span data-stu-id="b1e6d-131">Create, Modify, and Delete Schedules</span></span>](../subscriptions/create-modify-and-delete-schedules.md)  
  
  
