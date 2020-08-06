---
title: Creare e gestire prospettive (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.perspectivedb.f1
ms.assetid: 2a411c2b-2820-4086-ad7f-ce6a941fefc7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6d0029ff61aa05e2e83f34833c3d0af17ddb3beb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625003"
---
# <a name="create-and-manage-perspectives-ssas-tabular"></a><span data-ttu-id="efd6f-102">Creare e gestire prospettive (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="efd6f-102">Create and Manage Perspectives (SSAS Tabular)</span></span>
  <span data-ttu-id="efd6f-103">Le prospettive consentono di definire subset visualizzabili di un modello in grado di offrire punti di vista mirati, specifici di un'attività aziendale o di un'applicazione del modello.</span><span class="sxs-lookup"><span data-stu-id="efd6f-103">Perspectives define viewable subsets of a model that provide focused, business-specific, or application-specific viewpoints of the model.</span></span> <span data-ttu-id="efd6f-104">Nelle attività di questo argomento vengono descritte le modalità di creazione e gestione delle prospettive tramite la finestra di dialogo **Prospettive** in Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="efd6f-104">The tasks in this topic describe how to create and manage perspectives by using the **Perspectives** dialog box in the model designer.</span></span>  
  
 <span data-ttu-id="efd6f-105">In questo argomento sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="efd6f-105">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="efd6f-106">Per aggiungere una prospettiva</span><span class="sxs-lookup"><span data-stu-id="efd6f-106">To add a perspective</span></span>](#bkmk_add)  
  
-   [<span data-ttu-id="efd6f-107">Per modificare una prospettiva</span><span class="sxs-lookup"><span data-stu-id="efd6f-107">To edit a perspective</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="efd6f-108">Per rinominare una prospettiva</span><span class="sxs-lookup"><span data-stu-id="efd6f-108">To rename a perspective</span></span>](#bkmk_rename)  
  
-   [<span data-ttu-id="efd6f-109">Per eliminare una prospettiva</span><span class="sxs-lookup"><span data-stu-id="efd6f-109">To delete a perspective</span></span>](#bkmk_delete)  
  
-   [<span data-ttu-id="efd6f-110">Per copiare una prospettiva</span><span class="sxs-lookup"><span data-stu-id="efd6f-110">To copy a perspective</span></span>](#bkmk_copy)  
  
## <a name="tasks"></a><span data-ttu-id="efd6f-111">Attività</span><span class="sxs-lookup"><span data-stu-id="efd6f-111">Tasks</span></span>  
 <span data-ttu-id="efd6f-112">Per creare prospettive si utilizzerà la finestra di dialogo **Prospettive** in cui è possibile aggiungere, modificare, eliminare, copiare e visualizzare prospettive.</span><span class="sxs-lookup"><span data-stu-id="efd6f-112">To create perspectives, you will use the **Perspectives** dialog box, where you can add, edit, delete, copy, and view perspectives.</span></span> <span data-ttu-id="efd6f-113">Per visualizzare la finestra di dialogo **Prospettive** , in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]fare clic sul menu **Modello** , quindi scegliere **Prospettive**.</span><span class="sxs-lookup"><span data-stu-id="efd6f-113">To view the **Perspectives** dialog box, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click on the **Model** menu, and then click **Perspectives**.</span></span>  
  
###  <a name="to-add-a-perspective"></a><a name="bkmk_add"></a> <span data-ttu-id="efd6f-114">Per aggiungere una prospettiva</span><span class="sxs-lookup"><span data-stu-id="efd6f-114">To add a perspective</span></span>  
  
-   <span data-ttu-id="efd6f-115">Per aggiungere una nuova prospettiva, fare clic su **Nuova prospettiva**.</span><span class="sxs-lookup"><span data-stu-id="efd6f-115">To add a new perspective, click **New Perspective**.</span></span> <span data-ttu-id="efd6f-116">È possibile selezionare e deselezionare gli oggetti campo da includere e fornire un nome per la nuova prospettiva.</span><span class="sxs-lookup"><span data-stu-id="efd6f-116">You can then check and uncheck field objects to be included and provide a name for the new perspective.</span></span>  
  
     <span data-ttu-id="efd6f-117">Se si crea una prospettiva vuota con tutti i campi dell'oggetto campo, un utente che utilizza questa prospettiva visualizzerà un elenco di campi vuoto.</span><span class="sxs-lookup"><span data-stu-id="efd6f-117">If you create an empty perspective with all of the field object fields, then a user using this perspective will see an empty Field List.</span></span> <span data-ttu-id="efd6f-118">Le prospettive devono contenere almeno una tabella e una colonna.</span><span class="sxs-lookup"><span data-stu-id="efd6f-118">Perspectives should contain at least one table and column.</span></span>  
  
###  <a name="to-edit-a-perspective"></a><a name="bkmk_edit"></a><span data-ttu-id="efd6f-119">Per modificare una prospettiva</span><span class="sxs-lookup"><span data-stu-id="efd6f-119">To edit a perspective</span></span>  
  
-   <span data-ttu-id="efd6f-120">Per modificare una prospettiva, selezionare e deselezionare i campi nella colonna della prospettiva, che consente di aggiungere e rimuovere oggetti campo dalla prospettiva.</span><span class="sxs-lookup"><span data-stu-id="efd6f-120">To modify a perspective, check and uncheck fields in the perspective's column, which adds and removes field objects from the perspective.</span></span>  
  
###  <a name="to-rename-a-perspective"></a><a name="bkmk_rename"></a><span data-ttu-id="efd6f-121">Per rinominare una prospettiva</span><span class="sxs-lookup"><span data-stu-id="efd6f-121">To rename a perspective</span></span>  
  
-   <span data-ttu-id="efd6f-122">Quando si passa il mouse sull'intestazione di colonna di una prospettiva (il nome della prospettiva), viene visualizzato il pulsante **Rinomina** .</span><span class="sxs-lookup"><span data-stu-id="efd6f-122">When you hover over a perspective's column header (the name of the perspective), the **Rename** button appears.</span></span> <span data-ttu-id="efd6f-123">Per rinominare la prospettiva, fare clic su **Rinomina**, quindi immettere un nuovo nome o modificare quello esistente.</span><span class="sxs-lookup"><span data-stu-id="efd6f-123">To rename the perspective, click **Rename**, and then enter a new name or edit the existing name.</span></span>  
  
###  <a name="to-delete-a-perspective"></a><a name="bkmk_delete"></a><span data-ttu-id="efd6f-124">Per eliminare una prospettiva</span><span class="sxs-lookup"><span data-stu-id="efd6f-124">To delete a perspective</span></span>  
  
-   <span data-ttu-id="efd6f-125">Quando si passa il mouse sull'intestazione di colonna di una prospettiva (il nome della prospettiva), viene visualizzato il pulsante **Elimina** .</span><span class="sxs-lookup"><span data-stu-id="efd6f-125">When you hover over a perspective's column header (the name of the perspective), the **Delete** button appears.</span></span> <span data-ttu-id="efd6f-126">Per eliminare la prospettiva, fare clic sul pulsante **Elimina** , quindi scegliere **Sì** nella finestra di conferma.</span><span class="sxs-lookup"><span data-stu-id="efd6f-126">To delete the perspective, click the **Delete** button, and then click **Yes** in the confirmation window.</span></span>  
  
###  <a name="to-copy-a-perspective"></a><a name="bkmk_copy"></a><span data-ttu-id="efd6f-127">Per copiare una prospettiva</span><span class="sxs-lookup"><span data-stu-id="efd6f-127">To copy a perspective</span></span>  
  
-   <span data-ttu-id="efd6f-128">Quando si passa il mouse sull'intestazione di colonna di una prospettiva, viene visualizzato il pulsante **copia** .</span><span class="sxs-lookup"><span data-stu-id="efd6f-128">When you hover over a perspective's column header, the **Copy** button appears.</span></span> <span data-ttu-id="efd6f-129">Per creare una copia di tale prospettiva, fare clic sul pulsante **Copia** .</span><span class="sxs-lookup"><span data-stu-id="efd6f-129">To create a copy of that perspective, click the **Copy** button.</span></span> <span data-ttu-id="efd6f-130">Una copia della prospettiva selezionata viene aggiunta come nuova prospettiva a destra delle prospettive esistenti.</span><span class="sxs-lookup"><span data-stu-id="efd6f-130">A copy of the selected perspective is added as a new perspective to the right of existing perspectives.</span></span> <span data-ttu-id="efd6f-131">Il nome della nuova prospettiva viene ereditato dalla prospettiva copiata e alla fine del nome viene accodata un'annotazione *- Copy* .</span><span class="sxs-lookup"><span data-stu-id="efd6f-131">The new perspective inherits the name of the copied perspective and a *- Copy* annotation is appended to the end of the name.</span></span> <span data-ttu-id="efd6f-132">Se, ad esempio, viene creata una copia della prospettiva *Sales* , la nuova prospettiva viene denominata *Sales-Copy*.</span><span class="sxs-lookup"><span data-stu-id="efd6f-132">For example, if a copy of the *Sales* perspective is created, the new perspective is called *Sales - Copy*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efd6f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efd6f-133">See Also</span></span>  
 <span data-ttu-id="efd6f-134">[Prospettive &#40;SSAS tabulare&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="efd6f-134">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="efd6f-135">Gerarchie &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="efd6f-135">Hierarchies &#40;SSAS Tabular&#41;</span></span>](hierarchies-ssas-tabular.md)  
  
  
