---
title: Annulla estrazioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourcControl.UndoCheckDialog
helpviewer_keywords:
- checking out files
- checkout source controls [SQL Server]
- undoing checkouts
ms.assetid: a6596b20-3aa5-4dc4-a4c5-3649f1f5a20e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ff6e6041b59caa75bf7f8530d915db48e0379338
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624305"
---
# <a name="undo-checkouts"></a><span data-ttu-id="01307-102">Annullare estrazioni</span><span class="sxs-lookup"><span data-stu-id="01307-102">Undo Checkouts</span></span>
  <span data-ttu-id="01307-103">È possibile utilizzare il comando **Annulla estrazione** per annullare un'estrazione esistente.</span><span class="sxs-lookup"><span data-stu-id="01307-103">You can use the **Undo Checkout** command to cancel an existing checkout.</span></span> <span data-ttu-id="01307-104">che risulta particolarmente utile quando è necessario eseguire il rollback delle modifiche dopo avere modificato e salvato un file.</span><span class="sxs-lookup"><span data-stu-id="01307-104">This is particularly useful when you have modified and saved a file, and then later need to roll back your changes.</span></span>  
  
 <span data-ttu-id="01307-105">A seconda delle opzioni impostate nella finestra di dialogo **Annulla estrazione avanzata opzioni** , l'ambiente Studio lascia la copia di lavoro dell'elemento sul disco locale o la sostituisce con la versione più recente controllata dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="01307-105">Depending on the options you set in the **Undo Checkout Advanced Options** dialog box, the Studio environment either leaves the working copy of the item on your local disk or replaces it with the latest source-controlled version.</span></span> <span data-ttu-id="01307-106">Se l'elemento è stato modificato all'esterno del contesto del sistema di controllo del codice sorgente, è possibile che la versione recuperata non sia quella più recente.</span><span class="sxs-lookup"><span data-stu-id="01307-106">If someone has modified the item outside the context of the source control system, the retrieved version may not be the latest one.</span></span>  
  
### <a name="to-undo-a-checkout"></a><span data-ttu-id="01307-107">Per annullare un'estrazione</span><span class="sxs-lookup"><span data-stu-id="01307-107">To undo a checkout</span></span>  
  
1.  <span data-ttu-id="01307-108">In Esplora soluzioni selezionare il progetto.</span><span class="sxs-lookup"><span data-stu-id="01307-108">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="01307-109">Scegliere **controllo del codice sorgente**dal menu **file** , quindi fare clic su **Annulla estrazione**.</span><span class="sxs-lookup"><span data-stu-id="01307-109">On the **File** menu, point to **Source Control**, and then click **Undo Checkout**.</span></span>  
  
3.  <span data-ttu-id="01307-110">Nella finestra di dialogo **Annulla estrazione** selezionare le opzioni appropriate e quindi fare clic sul pulsante **Annulla estrazione** .</span><span class="sxs-lookup"><span data-stu-id="01307-110">In the **Undo Checkout** dialog box, select the appropriate options, and then click the **Undo Checkout** button.</span></span>  
  
     <span data-ttu-id="01307-111">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="01307-111">**Columns**</span></span>  
     <span data-ttu-id="01307-112">Consente di specificare le colonne da visualizzare e il relativo ordine.</span><span class="sxs-lookup"><span data-stu-id="01307-112">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="01307-113">**Visualizzazione semplice**</span><span class="sxs-lookup"><span data-stu-id="01307-113">**Flat View**</span></span>  
     <span data-ttu-id="01307-114">Consente di visualizzare gli elementi come elenchi semplici sotto la relativa connessione del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="01307-114">Display the items as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="01307-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="01307-115">**Name**</span></span>  
     <span data-ttu-id="01307-116">Consente di visualizzare i nomi degli elementi per i quali annullare l'estrazione.</span><span class="sxs-lookup"><span data-stu-id="01307-116">Displays the names of the items for which to undo the checkout.</span></span> <span data-ttu-id="01307-117">Accanto agli elementi viene visualizzata la casella di controllo selezionata.</span><span class="sxs-lookup"><span data-stu-id="01307-117">Items appear with the check boxes next to them selected.</span></span> <span data-ttu-id="01307-118">Se non si desidera annullare l'estrazione di un elemento, deselezionare la casella di controllo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="01307-118">If you do not want to undo the checkout of an item, clear its check box.</span></span>  
  
     <span data-ttu-id="01307-119">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="01307-119">**Options**</span></span>  
     <span data-ttu-id="01307-120">Consente di visualizzare le opzioni di annullamento dell'estrazione specifiche del plug-in del controllo del codice sorgente quando si fa clic sulla freccia a destra del pulsante.</span><span class="sxs-lookup"><span data-stu-id="01307-120">Displays source control plug-in-specific undo checkout options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="01307-121">**Sort**</span><span class="sxs-lookup"><span data-stu-id="01307-121">**Sort**</span></span>  
     <span data-ttu-id="01307-122">Consente di eseguire l'ordinamento delle colonne visualizzate.</span><span class="sxs-lookup"><span data-stu-id="01307-122">Sort the order of the display columns.</span></span>  
  
     <span data-ttu-id="01307-123">**Visualizzazione albero**</span><span class="sxs-lookup"><span data-stu-id="01307-123">**Tree View**</span></span>  
     <span data-ttu-id="01307-124">Consente di visualizzare la gerarchie di cartelle e di elementi per gli elementi di cui si sta annullando l'estrazione.</span><span class="sxs-lookup"><span data-stu-id="01307-124">Display the folder and item hierarchy for items on which you are reversing the checkout.</span></span>  
  
     <span data-ttu-id="01307-125">**Annulla estrazione**</span><span class="sxs-lookup"><span data-stu-id="01307-125">**Undo Checkout**</span></span>  
     <span data-ttu-id="01307-126">Consente di annullare l'estrazione, eliminando le eventuali modifiche apportate al file estratto.</span><span class="sxs-lookup"><span data-stu-id="01307-126">Revert the checkout, discarding any changes to the checked-out file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01307-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01307-127">See Also</span></span>  
 <span data-ttu-id="01307-128">[Estrai file](../../2014/database-engine/check-out-files.md) </span><span class="sxs-lookup"><span data-stu-id="01307-128">[Check Out Files](../../2014/database-engine/check-out-files.md) </span></span>  
 [<span data-ttu-id="01307-129">Gestione delle estrazioni</span><span class="sxs-lookup"><span data-stu-id="01307-129">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
